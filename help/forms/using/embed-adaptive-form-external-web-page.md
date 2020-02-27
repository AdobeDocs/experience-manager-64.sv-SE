---
title: Bädda in anpassningsbara formulär på en extern webbsida
seo-title: Bädda in anpassningsbara formulär på en extern webbsida
description: Lär dig bädda in ett anpassat formulär på en extern webbsida
seo-description: Lär dig bädda in ett adaptivt formulär på en extern HTML-webbsida
uuid: c612ca3b-62f7-4021-939b-e0c05dbbf0d7
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: author
discoiquuid: b99c7b93-ba05-42ee-9ca8-0079e15d8602
translation-type: tm+mt
source-git-commit: 7a5fb38ada7e7ad76525449e35f64b133aa5e39f

---


# Bädda in anpassningsbara formulär på en extern webbsida{#embed-adaptive-form-in-external-web-page}

Lär dig bädda in ett anpassat formulär på en extern webbsida

Du kan [bädda in anpassningsbara formulär på AEM Sites](/help/forms/using/embed-adaptive-form-aem-sites.md) -sidan eller på en webbsida som är värd utanför AEM. Det inbäddade adaptiva formuläret fungerar fullt ut och användarna kan fylla i och skicka formuläret utan att behöva lämna sidan. Det hjälper användaren att stanna kvar i sitt sammanhang för andra element på webbsidan och interagera med formuläret samtidigt.

## Förutsättningar {#prerequisites}

Utför följande steg innan du bäddar in ett anpassat formulär på en extern webbplats:

* Publicera det adaptiva formuläret på AEM Publish-instansen.
* Skapa eller identifiera en webbsida på din webbplats som värd för det adaptiva formuläret. Kontrollera att webbsidan kan [läsa jQuery-filer från ett CDN](https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js) eller ha en lokal kopia av jQuery inbäddad. jQuery krävs för att återge ett anpassat formulär.
* När AEM-servern och webbsidan finns på olika domäner utför du de steg som anges i avsnittet och [aktiverar AEM Forms för att skicka adaptiva formulär till en domänövergripande webbplats](#cross-domain-sites).
* [Konfigurera omvänd proxy](#reveseproxy) för att aktivera kommunikation mellan extern sida och AEM Forms-server.

## Bädda in anpassat formulär {#embed-adaptive-form}

Du kan bädda in ett anpassat formulär genom att infoga några rader med JavaScript på webbsidan. API:t i koden skickar en HTTP-begäran till AEM-servern för adaptiva formulärresurser och injicerar det adaptiva formuläret i den angivna formulärbehållaren. Här är ett exempel på kod för att bädda in ett adaptivt formulär på en extern sida. Använd inte koden som den är i en produktionsmiljö. Anpassa koden så att den passar webbplatsen, som att använda en iFrame för webbplatser som använder sin egen version av jQuery. Genom att använda iFrame undviker du konflikter i jQuery-versioner:


1. Bädda in följande kod på en webbsida på webbplatsen:

   ```
   
   
<!doctype html>
<html>
  <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>Det här är webbsidans titel!</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
  </head>
  <body>
  <div class="customafsection"/>
    <p>Detta avsnitt ersätts med den anpassningsbara formen.</p>


    &lt;script>
    var options = {path:&quot;/content/forms/af/locbasic.html&quot;, dataRef:&quot;&quot;, themepath:&quot;&quot;, CSS_Selector:&quot;.customafsection&quot;};
    alert(options.path);
    var loadAdaptiveForm = function(options){
    //alert(options.path);
    if(options.path) {
    // options.path hänvisar till publicerings-URL:en adaptiv form
    // Exempel: http:myserver:4503/content/forms/af/ABC, där ABC är den adaptiva formen
    / Anm: Om AEM-servern körs på en kontextsökväg måste URL:en för adaptiva formulär innehålla
    kontextsökvägen = options.path;
    path += &quot;/jcr:content/guideContainer.html&quot;;
    $.ajax({
    url : sökväg,
    typ: &quot;GET&quot;,
    data: {
    // Ange att wcmmode ska vara
    disabledwcmmode: &quot;disabled&quot;
    // Ange eventuell
    datareferens// &quot;dataRef&quot;: options.dataRef
    // Ange ett annat tema för formulärobjektet
    // &quot;themeOverride&quot;: options.themepath
    },
    async: false,
    success: function (data) {
    // Om jquery läses in, anger du den inre HTML-koden för behållaren
    // Om jquery inte läses in, använder du API:er från dokumentet för att ställa in den inre HTML-koden, men dessa API:er utvärderar inte script-taggen i HTML5 enligt specifikationen
    /// Exempel: document.getElementById().
    innerHTMLif(window.$ &amp;&amp; options.CSS_Selector){
    // HTML API of jquery extraherar taggarna, uppdaterar DOM och utvärderar koden som är inbäddad i script-taggen.
    $(options.CSS_Selector).html(data);
    }
    },
    fel: function (data) {
    // any error handler
    }
    });
    } else {
    if (typeof(console) !== &quot;undefined&quot;) {
    console.log(&quot;Path of Adaptive Form not specified to loadAdaptiveForm&quot;);
    }
    }
    }(options);
    
    &lt;/script>
</body>
</html>
   ```

1. I den inbäddade koden:

   * Ändra värdet för `options.path` variabeln med sökvägen för den anpassningsbara formulärets publicerings-URL. Om AEM-servern körs på en kontextsökväg kontrollerar du att URL:en innehåller kontextsökvägen. Ovanstående kod och adaptiv kod finns till exempel på samma formulärserver, så i exemplet används kontextsökvägen för det adaptiva formuläret /content/forms/af/locbasic.html.
   * Ersätt `options.dataRef` med attribut som ska skickas med URL:en. Du kan använda dataref-variabeln för att [förifylla ett anpassat formulär](/help/forms/using/prepopulate-adaptive-form-fields.md).
   * Ersätt `options.themePath` med sökvägen till ett annat tema än det som har konfigurerats i det adaptiva formuläret. Du kan också ange temats sökväg med hjälp av attributet request.
   * `CSS_Selector` är CSS-väljaren för formulärbehållaren där det adaptiva formuläret är inbäddat. Klassen .customafsection css är till exempel CSS-väljaren i exemplet ovan.

Det anpassningsbara formuläret är inbäddat på webbsidan. Observera följande i den inbäddade adaptiva formen:

* Sidhuvud och sidfot i det ursprungliga anpassningsbara formuläret inkluderas inte i det inbäddade formuläret.
* Utkast och skickade formulär finns på fliken Utkast och inskickningar i Forms Portal.
* Skicka-åtgärden som konfigurerats på det ursprungliga adaptiva formuläret behålls i det inbäddade formuläret.
* Anpassningsbara formulärregler behålls och fungerar fullt ut i det inbäddade formuläret.
* Upplevelsemål och A/B-tester som konfigurerats i det ursprungliga adaptiva formuläret fungerar inte i det inbäddade formuläret.
* Om Adobe Analytics är konfigurerat på originalformuläret hämtas analysdata till Adobe Analytics-servern. Den är dock inte tillgänglig i Forms Analytics-rapporten.

## Konfigurera omvänd proxy {#reveseproxy}

Den externa webbsidan som bäddar in det adaptiva formuläret skickar begäranden till AEM-servern, som vanligtvis sitter bakom brandväggen i ett privat nätverk. För att säkerställa att förfrågningarna dirigeras till AEM-servern på ett säkert sätt bör du konfigurera en omvänd proxyserver.

Låt oss titta på ett exempel på hur du kan konfigurera en omvänd Apache 2.4-proxyserver utan dispatcher. I det här exemplet kommer du att vara värd för AEM-servern med `/forms` kontextsökväg och mappning `/forms` för den omvända proxyn. Den ser till att alla förfrågningar om Apache- `/forms` servern dirigeras till AEM-instansen. Den här topologin minskar antalet regler i dispatcherlagret som alla begäranden som föregås av dirigering till AEM-servern. `/forms`

1. Öppna `httpd.conf` konfigurationsfilen och avkommentera följande kodrader. Du kan också lägga till de här kodraderna i filen.

   ```
   LoadModule proxy_html_module modules/mod_proxy_html.so 
    LoadModule proxy_http_module modules/mod_proxy_http.so
   ```

1. Ställ in proxyregler genom att lägga till följande kodrader i `httpd-proxy.conf` konfigurationsfilen.

   ```
   ProxyPass /forms https://[AEM_Instance]/forms 
    ProxyPassReverse /forms https://[AEM_Instance]/forms
   ```

   Ersätt `[AEM_Instance`] med AEM-serverns publicerings-URL i reglerna.

Om du inte monterar AEM-servern på en kontextsökväg, kommer proxyreglerna i Apache-lagret att vara följande:

```java
ProxyPass /content https://<AEM_Instance>/content
ProxyPass /etc https://<AEM_Instance>/etc
ProxyPass /etc.clientlibs https://<AEM_Instance>/etc.clientlibs
# CSRF Filter
ProxyPass /libs/granite/csrf/token.json https://<AEM_Instance>/libs/granite/csrf/token.json
  
ProxyPassReverse /etc https://<AEM_Instance>/etc
ProxyPassReverse /etc.clientlibs https://<AEM_Instance>/etc.clientlibs
# written for thank you page and other URL present in AF during redirect
ProxyPassReverse /content https://<AEM_Instance>/content
```

>[!NOTE]
>
>Om du konfigurerar någon annan topologi måste du vitlista överförings-, förifyllnings- och andra URL-adresser i dispatcherlagret.

## God praxis {#best-practices}

Tänk på följande när du bäddar in ett anpassat formulär på en webbsida:

* Kontrollera att formateringsreglerna som definieras i webbsidans CSS inte är i konflikt med formulärobjektets CSS. För att undvika konflikterna kan du återanvända webbsidans CSS i det adaptiva formulärtemat med hjälp av AEM-klientbiblioteket. Mer information om hur du använder klientbiblioteket i adaptiva formulärteman finns i [Teman i AEM-formulär](/help/forms/using/themes.md).
* Låt formulärbehållaren på webbsidan använda hela fönsterbredden. Det ser till att CSS-reglerna som konfigurerats för mobila enheter fungerar utan ändringar. Om formulärbehållaren inte får hela fönsterbredden måste du skriva anpassad CSS så att formuläret kan anpassas till olika mobila enheter.
* Använd ` [getData](https://helpx.adobe.com/experience-manager/6-3/forms/javascript-api/GuideBridge.html)` API för att hämta XML- eller JSON-representationen av formulärdata i klienten.
* Använd ` [unloadAdaptiveForm](https://helpx.adobe.com/experience-manager/6-3/forms/javascript-api/GuideBridge.html)` API för att ta bort det adaptiva formuläret från HTML DOM.
* Ange huvudet för åtkomstkontrollens ursprung när du skickar svar från AEM-servern.

## Aktivera AEM Forms för att skicka adaptiva formulär till en domänövergripande webbplats {#cross-domain-sites}

1. På AEM-författarinstansen går du till AEM Web Console Configuration Manager på `http://[server]:[port]/system/console/configMgr`.
1. Leta reda på och öppna **filterkonfigurationen för** Apache Sling Referrer.
1. I fältet **Tillåtna värdar** anger du den domän där webbsidan finns. Det gör att värden kan göra POST-begäranden till AEM-servern. Du kan också använda reguljära uttryck för att ange en serie externa programdomäner.