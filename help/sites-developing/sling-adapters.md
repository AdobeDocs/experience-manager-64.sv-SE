---
title: Använda Sling-adaptrar
seo-title: Using Sling Adapters
description: Sling erbjuder ett adaptermönster för att enkelt översätta objekt som implementerar gränssnittet Adaptable
seo-description: Sling offers an Adapter pattern to conveniently translate objects that implement the Adaptable interface
uuid: 07f66a33-072d-49e1-8e67-8b80a6a9072a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: c081b242-67e4-4820-9bd3-7e4495df459e
exl-id: 7780d04d-418e-494c-85c3-76bef5f35690
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1753'
ht-degree: 0%

---

# Använda Sling-adaptrar{#using-sling-adapters}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

[Sling](https://sling.apache.org) erbjuder [Adaptermönster](https://sling.apache.org/site/adapters.html) att enkelt översätta objekt som implementerar [Adaptiv](https://sling.apache.org/apidocs/sling5/org/apache/sling/api/adapter/Adaptable.html#adaptTo%28java.lang.Class%29) gränssnitt. Det här gränssnittet innehåller en allmän [customiTo()](https://sling.apache.org/apidocs/sling5/org/apache/sling/api/adapter/Adaptable.html#adaptTo%28java.lang.Class%29) metod som översätter objektet till den klasstyp som skickas som argument.

Om du till exempel vill översätta ett Resource-objekt till motsvarande Node-objekt kan du bara göra följande:

```java
Node node = resource.adaptTo(Node.class);
```

## Användningsexempel {#use-cases}

Det finns följande användningsområden:

* Få implementeringsspecifika objekt.

   En JCR-baserad implementering av den generiska [`Resource`](https://sling.apache.org/apidocs/sling5/org/apache/sling/api/resource/Resource.html) -gränssnittet ger åtkomst till underliggande JCR [`Node`](https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html).

* Skapa genvägar för objekt som kräver att interna kontextobjekt skickas.

   Till exempel den JCR-baserade [`ResourceResolver`](https://sling.apache.org/apidocs/sling5/org/apache/sling/api/resource/ResourceResolver.html) innehåller en referens till begäran [`JCR Session`](https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Session.html)som i sin tur behövs för många objekt som ska fungera baserat på den begärandesessionen, som [`PageManager`](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/PageManager.html) eller [`UserManager`](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/UserManager.html).

* Genväg till tjänster.

   Ett sällsynt fall - `sling.getService()` är också enkelt.

### Null-returvärde {#null-return-value}

`adaptTo()` kan returnera null.

Det finns olika orsaker till detta, bland annat:

* implementeringen saknar stöd för måltypen
* en adapterfabrik som hanterar det här ärendet är inte aktivt (t.ex. på grund av saknad tjänstreferens)
* internt villkor misslyckades
* tjänsten är inte tillgänglig

Det är viktigt att du hanterar skiftläget null på ett smidigt sätt. Vid jsp-återgivning kan det vara acceptabelt att jsp misslyckas om det resulterar i en tom del av innehållet.

### Cachelagring {#caching}

För att förbättra prestanda kan implementeringar cachelagra objektet som returneras från en `obj.adaptTo()` ring. Om `obj` är samma, returnerade objekt är samma.

Denna cachelagring utförs för alla `AdapterFactory` baserade fall.

Det finns dock ingen allmän regel - objektet kan vara antingen en ny eller en befintlig instans. Det innebär att du inte kan förlita dig på något av beteendena. Därför är det viktigt, särskilt inom `AdapterFactory`att objekt kan återanvändas i det här scenariot.

### Så här fungerar det {#how-it-works}

Det finns olika sätt att `Adaptable.adaptTo()` kan implementeras:

* själva objektet, implementera själva metoden och mappa till vissa objekt.
* Av en [`AdapterFactory`](https://sling.apache.org/apidocs/sling5/org/apache/sling/api/adapter/AdapterFactory.html), som kan mappa godtyckliga objekt.

   Objekten måste fortfarande implementera `Adaptable` gränssnitt och måste utöka [`SlingAdaptable`](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/adapter/SlingAdaptable.html) (som klarar `adaptTo` till en central adapterhanterare).

   Det gör att du kan lägga in kopplingar i `adaptTo` mekanism för befintliga klasser, som `Resource`.

* En kombination av båda.

I det första fallet kan javadocs visa vad `adaptTo-targets` är möjliga. Detta är dock ofta inte möjligt för vissa underklasser, t.ex. JCR-baserade resurser. I det senare fallet ska `AdapterFactory` är vanligtvis en del av de privata klasserna i ett paket och därför inte exponeras i ett klient-API, och inte heller listas i javadocs. Teoretiskt sett skulle det vara möjligt att få tillgång till alla `AdapterFactory` implementeringar från [OSGi](/help/sites-deploying/configuring-osgi.md) runtime-modulen för tjänster och se hur deras&quot;adaptable&quot;-konfigurationer (källor och mål) ser ut, men inte för att mappa dem till varandra. I slutändan beror detta på den interna logiken, som måste dokumenteras. Denna referens.

## Referens {#reference}

### Sling {#sling}

[**Resurs**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html) anpassar sig till:

<table> 
 <tbody> 
  <tr> 
   <td><a href="https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html">Nod</a></td> 
   <td>Om detta är en JCR-nodbaserad resurs eller en JCR-egenskap som refererar till en nod.</td> 
  </tr> 
  <tr> 
   <td><a href="https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Property.html">Egenskap</a></td> 
   <td>Om detta är en JCR-egenskapsbaserad resurs.</td> 
  </tr> 
  <tr> 
   <td><a href="https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Item.html">Objekt</a></td> 
   <td>Om detta är en JCR-baserad resurs (nod eller egenskap).</td> 
  </tr> 
  <tr> 
   <td><a href="https://java.sun.com/j2se/1.5.0/docs/api//java/util/Map.html">Karta</a></td> 
   <td>Returnerar en karta över egenskaperna, om detta är en JCR-nodbaserad resurs (eller annan resurs som stöder värdekartor).</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ValueMap.html">ValueMap</a></td> 
   <td>Returnerar en användbar karta över egenskaperna, om detta är en JCR-nodbaserad resurs (eller annan resurs som stöder värdekartor). Kan också uppnås (enklare) genom att använda<br /> <code><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ResourceUtil.html#getvaluemap%28org.apache.sling.api.resource.resource%29">ResourceUtil.getValueMap(Resource)</a></code> (hanterar gemener, etc.).</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/inherit/InheritanceValueMap.html">ArvValueMap</a></td> 
   <td>Utökning av <a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ValueMap.html">ValueMap</a> som gör det möjligt att ta hänsyn till resurshierarkin när du söker efter egenskaper.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/PersistableValueMap.html">PersistableValueMap</a></td> 
   <td>Om detta är en JCR-nodbaserad resurs och användaren har behörighet att ändra egenskaper på den noden.<br /> Obs! flera beständiga kartor delar inte sina värden.</td> 
  </tr> 
  <tr> 
   <td><a href="https://java.sun.com/j2se/1.5.0/docs/api/java/io/InputStream.html">InputStream</a></td> 
   <td>Returnerar det binära innehållet i en "fil"<code>nt:resource</code></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td><code>AuthorizableResourceProvider</code><code>org.apache.sling.jackrabbit.usermanager</code><code>/system/userManager</code></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td><code>cq:Page</code><code>cq:PseudoPage</code></td></tr><tr><td></td><td><code>cq:Component</code></td></tr><tr><td></td><td><code>cq:Page</code></td></tr><tr><td></td><td><code>cq:Template</code></td></tr><tr><td></td><td><code>cq:Page</code></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td><code>cq:Tag</code></td></tr><tr><td></td><td><code>cq:Preferences</code></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td><code>cq:ContentSyncConfig</code></td></tr><tr><td></td><td><code>cq:ContentSyncConfig</code></td></tr></tbody></table>

[**ResursResolver**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ResourceResolver.html) anpassar sig till:

<table> 
 <tbody> 
  <tr> 
   <td><a href="https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Session.html">Session</a></td> 
   <td>JCR-sessionen för begäran, om det här är en JCR-baserad resurslösare (standard).</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/PageManager.html">PageManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/components/ComponentManager.html">ComponentManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/designer/Designer.html">Designer</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/dam/api/AssetManager.html">AssetManager</a></td> 
   <td>Baserat på JCR-sessionen, om detta är en JCR-baserad resurslösare.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/tagging/TagManager.html">TagManager</a></td> 
   <td>Baserat på JCR-sessionen, om detta är en JCR-baserad resurslösare.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/UserManager.html">UserManager</a></td> 
   <td>Baserat på JCR-sessionen, om detta är en JCR-baserad resurslösare och om användaren har behörighet att komma åt UserManager.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/jackrabbit/api/security/user/Authorizable.html">Auktoriserbar</a> </td> 
   <td>Den aktuella användaren.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/jackrabbit/api/security/user/User.html">Användare</a><br /> </td> 
   <td>Den aktuella användaren.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/privileges/PrivilegeManager.html">PrivilegeManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/preferences/Preferences.html">Inställningar</a></td> 
   <td>Inställningar för den aktuella användaren (baserat på JCR-session om detta är en JCR-baserad resurslösare).</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/preferences/PreferencesService.html">PreferencesService</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/auth/pin/PinManager.html">PinManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/search/QueryBuilder.html">QueryBuilder</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html">Externalizer</a></td> 
   <td>För att göra absoluta URL:er externaliserade, även med objektet request.<br /> </td> 
  </tr> 
 </tbody> 
</table>

[**SlingHttpServletRequest**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/SlingHttpServletRequest.html) anpassar sig till:

Inga mål ännu, men implementerar Adaptable och kan användas som källa i en anpassad AdapterFactory.

[**SlingHttpServletResponse**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/SlingHttpServletResponse.html) anpassar sig till:

<table> 
 <tbody> 
  <tr> 
   <td><a href="https://java.sun.com/j2se/1.5.0/docs/api/org/xml/sax/ContentHandler.html">ContentHandler</a><br /> (XML)</td> 
   <td>Om det här är ett svarsalternativ.</td> 
  </tr> 
 </tbody> 
</table>

#### WCM {#wcm}

[**Sida**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/Page.html) anpassar sig till:

<table> 
 <tbody> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html">Resurs</a><br /> </td> 
   <td>Sidans resurs.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/LabeledResource.html">EtiketteradResurs</a></td> 
   <td>Etiketterad resurs (== this).</td> 
  </tr> 
  <tr> 
   <td><a href="https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html">Nod</a></td> 
   <td>Sidans nod.</td> 
  </tr> 
  <tr> 
   <td>...</td> 
   <td>Allt som sidans resurs kan anpassas till.</td> 
  </tr> 
 </tbody> 
</table>

[**Komponent**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/components/Component.html) anpassar sig till:

| [Resurs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html) | Komponentens resurs. |
|---|---|
| [EtiketteradResurs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/LabeledResource.html) | Etiketterad resurs (== this). |
| [Nod](https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) | Komponentens nod. |
| ... | Allt som komponentens resurs kan anpassas till. |

[**Mall**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/Template.html) anpassar sig till:

<table> 
 <tbody> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html">Resurs</a><a href="https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html"><br /> </a></td> 
   <td>Mallens resurs.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/LabeledResource.html">EtiketteradResurs</a></td> 
   <td>Etiketterad resurs (== this).</td> 
  </tr> 
  <tr> 
   <td><a href="https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html">Nod</a></td> 
   <td>Nod för den här mallen.</td> 
  </tr> 
  <tr> 
   <td>...</td> 
   <td>Allt som mallens resurs kan anpassas till.</td> 
  </tr> 
 </tbody> 
</table>

#### Dokumentskydd {#security}

[**Auktoriserbar**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/Authorizable.html), [**Användare**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/User.html) och [**Grupp**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/Group.html) anpassa till:

| [Nod](https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) | Returnerar hemnoden för användaren/gruppen. |
|---|---|
| [ReplicationStatus](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/replication/ReplicationStatus.html) | Returnerar replikeringsstatusen för användarens/gruppens hemnod. |

#### DAM {#dam}

[**Tillgång**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/dam/api/Asset.html) anpassar sig till:

| [Resurs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html) | Resurs för tillgången. |
|---|---|
| [Nod](https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) | Nod för resursen. |
| ... | Allt som resursen kan anpassas till. |

#### Taggar {#tagging}

[**Tagg**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/tagging/Tag.html) anpassar sig till:

| [Resurs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html) | Resurs för taggen. |
|---|---|
| [Nod](https://www.adobe.io/experience-manager/reference-materials/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) | Taggens nod. |
| ... | Allt som taggens resurs kan anpassas till. |

#### Övriga {#other}

Dessutom ger Sling/JCR/OCM ` [AdapterFactory](https://sling.apache.org/site/adapters.html#Adapters-AdapterFactory)` för anpassad OCM ([Mappning av objektinnehåll](https://jackrabbit.apache.org/object-content-mapping.html)).
