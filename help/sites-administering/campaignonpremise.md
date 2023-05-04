---
title: Integrera med Adobe Campaign Classic
seo-title: Integrating with Adobe Campaign Classic
description: Lär dig integrera AEM med Adobe Campaign Classic
seo-description: Learn how to integrate AEM with Adobe Campaign Classic
uuid: 3c998b0e-a885-4aa9-b2a4-81b86f9327d3
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: df94dd1b-1b65-478b-a28d-81807a8084b1
exl-id: af980042-2c54-4015-b35e-cc9d417e6e82
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2292'
ht-degree: 0%

---

# Integrera med Adobe Campaign Classic{#integrating-with-adobe-campaign-classic}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>I den här dokumentationen beskrivs hur du integrerar AEM med Adobe Campaign Classic, den lokala lösningen. Om du använder Adobe Campaign Standard finns mer information i [Integrera med Adobe Campaign Standard](/help/sites-administering/campaignstandard.md) för dessa instruktioner.

Med Adobe Campaign kan ni hantera e-postinnehåll och formulär direkt i Adobe Experience Manager.

Om du vill använda båda lösningarna samtidigt måste du först konfigurera dem så att de ansluter till varandra. Detta inbegriper konfigurationssteg i både Adobe Campaign och Adobe Experience Manager. Dessa steg beskrivs i detalj i det här dokumentet.

När du arbetar med Adobe Campaign i AEM kan du skicka e-post via Adobe Campaign och det beskrivs på [Arbeta med Adobe Campaign](/help/sites-authoring/campaign.md). Det innefattar även att använda formulär på AEM sidor för att hantera data.

Dessutom kan följande ämnen vara av intresse vid integrering av AEM med [Adobe Campaign](https://helpx.adobe.com/support/campaign/classic.html):

* [Metodtips för e-postmallar](/help/sites-administering/best-practices-for-email-templates.md)
* [Felsöka Adobe Campaign-integreringen](/help/sites-administering/troubleshooting-campaignintegration.md)

Om du utökar integreringen med Adobe Campaign kanske du vill se följande sidor:

* [Skapa anpassade tillägg](/help/sites-developing/extending-campaign-extensions.md)
* [Skapa anpassade formulärmappningar](/help/sites-developing/extending-campaign-form-mapping.md)

## Arbetsflöde för integrering med AEM och Adobe Campaign {#aem-and-adobe-campaign-integration-workflow}

I det här avsnittet beskrivs ett typiskt arbetsflöde mellan AEM och Adobe Campaign när du skapar kampanjer och levererar innehåll.

Det typiska arbetsflödet omfattar följande och beskrivs i detalj:

1. Börja bygga en kampanj (både i Adobe Campaign och AEM).
1. Innan du länkar innehållet och leveransen kan du anpassa innehållet i AEM och skapa en leverans i Adobe Campaign.
1. Länka innehåll och leverans i Adobe Campaign.

### Börja bygga din kampanj {#start-building-your-campaign}

Du börjar skapa en kampanj när som helst. Innan ni länkar innehållet är AEM och AC oberoende Det innebär att marknadsförarna kan börja skapa kampanjer och målinriktning i Adobe Campaign, medan de som skapar innehåll arbetar med designen i AEM.

### Innan innehåll och leverans länkas {#before-linking-content-and-delivery}

Innan du länkar innehållet och skapar en leveransfunktion måste du göra följande:

**I AEM**

* Anpassa med personaliseringsfälten i **Text och personalisering** komponent

**I Adobe Campaign**

* Skapa en leverans av typen **aemContent**

### Länka innehåll och ange leverans {#linking-content-and-setting-delivery}

När du har förberett innehållet för länkning och leverans bestämmer du exakt hur och var innehållet ska länkas.

Alla dessa steg utförs i Adobe Campaign.

1. Ange vilken AEM som ska användas.
1. Synkronisera innehållet genom att klicka på knappen Synkronisera.
1. Öppna innehållsväljaren för att välja innehåll.

### Om du inte har använt AEM tidigare {#if-you-are-new-to-aem}

Om du inte har använt AEM tidigare kan följande länkar vara bra att förstå AEM:

* [AEM](/help/sites-deploying/deploy.md)
* [Förstå replikeringsagenter](/help/sites-deploying/replication.md)
* [Söka efter och arbeta med loggfiler](/help/sites-deploying/monitoring-and-maintaining.md#working-with-audit-records-and-log-files)
* [Introduktion till AEM](/help/sites-deploying/platform.md)

## Konfigurera Adobe Campaign {#configuring-adobe-campaign}

När du konfigurerar Adobe Campaign ingår följande:

1. Installera AEM integreringspaket i Adobe Campaign.
1. Konfigurera ett externt konto.
1. Verifierar att AEMResourceTypeFilter har konfigurerats korrekt.

Det finns dessutom avancerade konfigurationer som du kan göra, bland annat:

* Hantera innehållsblock
* Hantera personaliseringsfält

Se [Avancerade konfigurationer](#advanced-configurations).

>[!NOTE]
>
>För att kunna utföra dessa åtgärder måste du ha **administration** i Adobe Campaign.

### Förutsättningar {#prerequisites}

Kontrollera att du har följande element i förväg:

* [En AEM](/help/sites-deploying/deploy.md#getting-started)
* [En AEM publiceringsinstans](/help/sites-deploying/deploy.md#author-and-publish-installs)
* [En Adobe Campaign Classic-instans](https://helpx.adobe.com/support/campaign/classic.html) - inklusive en klient och en server
* Internet Explorer 11

>[!NOTE]
>
>Om du kör en version som är tidigare än Adobe Campaign Classic build 8640 kan du läsa [uppgraderingsdokumentation](https://docs.campaign.adobe.com/doc/AC6.1/en/PRO_Updating_Adobe_Campaign_Upgrading.html) för mer information. Observera att både klienten och databasen måste uppgraderas till samma bygge.

>[!CAUTION]
>
>Åtgärder som anges i [Konfigurera Adobe Campaign](#configuring-adobe-campaign) och [Konfigurera Adobe Experience Manager](#configuring-adobe-experience-manager) -avsnitt är nödvändiga för att integreringsfunktionerna mellan AEM och Adobe Campaign ska fungera korrekt.

### Installera AEM integreringspaket {#installing-the-aem-integration-package}

Du måste installera **AEM** i Adobe Campaign. Så här gör du:

1. Gå till den Adobe Campaign-instans som du vill länka till AEM.
1. Välj *verktyg* > *Avancerat* > *Importera paket...*.

   ![chlimage_1-132](assets/chlimage_1-132.png)

1. Klicka **Installera ett standardpaket** väljer du **AEM** paket.

   ![chlimage_1-133](assets/chlimage_1-133.png)

1. Klicka **Nästa** och sedan **Starta**.

   Paketet innehåller **aemserver** -operator som ska användas för att ansluta AEM till Adobe Campaign.

   >[!CAUTION]
   >
   >Som standard är ingen säkerhetszon konfigurerad för den här operatorn. Om du vill ansluta till Adobe Campaign via AEM måste du välja en.
   >
   >I **serverConf.xml** -filen, **allowUserPassword** den valda säkerhetszonens attribut måste anges till **true** för att auktorisera AEM att ansluta till Adobe Campaign via inloggning/lösenord.
   >
   >Vi rekommenderar starkt att du skapar en säkerhetszon som är dedikerad till AEM för att undvika säkerhetsproblem. Mer information finns i [Installationsguide](https://docs.campaign.adobe.com/doc/AC/en/INS_Additional_configurations_Configuring_Campaign_server.html).

   ![chlimage_1-134](assets/chlimage_1-134.png)

### Konfigurera ett AEM externt konto {#configuring-an-aem-external-account}

Du måste konfigurera ett externt konto som gör att du kan ansluta Adobe Campaign till din AEM.

>[!NOTE]
>
>* När du installerar **AEM** paket skapas ett externt AEM. Du kan konfigurera anslutningen till AEM från den eller skapa en ny.
>* I AEM måste du ange lösenordet för kampanjens fjärranvändare. Du måste ange det här lösenordet för att kunna ansluta Adobe Campaign till AEM. Logga in som administratör och i användaradministrationskonsolen, sök efter användaren som är kampanjfjärrmedlem och klicka på **Ange lösenord**.
>


Så här konfigurerar du ett externt AEM:

1. Gå till **Administration** > **Plattform** > **Externa konton** nod.
1. Skapa ett nytt externt konto och välj **AEM** typ.
1. Ange åtkomstparametrarna för AEM-utvecklingsinstansen: serveradressen samt det ID och lösenord som används för att ansluta till den här instansen. Lösenordet för användarkontot för kampanj-api är detsamma som för användaren som du angav ett lösenord för i AEM.

   >[!NOTE]
   >
   >Kontrollera att serveradressen **not** i ett avslutande snedstreck. Skriv till exempel `https://yourserver:4502` i stället för `https://yourserver:4502/`

   ![chlimage_1-135](assets/chlimage_1-135.png) ![chlimage_1-136](assets/chlimage_1-136.png)

1. Se till att **Aktiverad** är markerad.

### Verifiera alternativet AEMResourceTypeFilter {#verifying-the-aemresourcetypefilter-option}

The **AEMResourceTypeFilter** används för att filtrera olika typer av AEM som kan användas i Adobe Campaign. På så sätt kan Adobe Campaign hämta AEM som är särskilt utformade för att endast användas i Adobe Campaign.

Detta alternativ bör vara förkonfigurerat; Men om du ändrar det här alternativet kan det leda till att integreringen inte fungerar.

Verifiera **AEMResourceTypeFilter** är konfigurerat:

1. Gå till **Plattform** >**Alternativ**.
1. I **AEMResourceTypeFilter** kontrollerar du att sökvägarna är korrekta. Fältet måste innehålla värdet:

   **mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter**

   I vissa fall är värdet följande:

   **mcm/campaign/components/newsletter**

   ![chlimage_1-137](assets/chlimage_1-137.png)

## Konfigurera Adobe Experience Manager {#configuring-adobe-experience-manager}

För att konfigurera AEM måste du göra följande:

* Konfigurera replikering mellan instanser.
* Koppla AEM till Adobe Campaign via Cloud Services.
* Konfigurera externaliseraren.

### Konfigurera replikering mellan AEM instanser {#configuring-replication-between-aem-instances}

Innehåll som skapas från AEM-författarinstansen skickas först till publiceringsinstansen. Du måste publicera så att bilderna i nyhetsbrevet är tillgängliga för publiceringsinstansen och för mottagarna av nyhetsbrevet. Replikeringsagenten måste därför konfigureras att replikera från AEM till den AEM publiceringsinstansen.

>[!NOTE]
>
>Om du inte vill använda replikerings-URL:en utan i stället använda den offentliga URL:en kan du ange **Offentlig URL** i följande konfigurationsinställning i OSGi (**AEM logotyp** >  **verktyg** ikon >  **Operationer** > **Webbkonsol** > **OSGi-konfiguration** > **AEM Campaign Integration - Configuration**):
**Offentlig URL:** com.day.cq.mcm.campaign.impl.IntegrationConfigImpl#aem.mcm.campaign.publicUrl

Det här steget är också nödvändigt för att replikera vissa redigeringsinstanskonfigurationer till publiceringsinstansen.

Så här konfigurerar du replikering mellan AEM instanser:

1. Välj **AEM logotyp**> **verktyg** ikon > **Distribution** > **Replikering** > **Agenter på författare** och sedan klicka **Standardagent**.

   ![chlimage_1-138](assets/chlimage_1-138.png)

   >[!NOTE]
   Undvik att använda localhost (d.v.s. en lokal kopia av AEM) när du konfigurerar integreringen med Adobe Campaign, såvida inte både publicerings- och författarinstansen finns på samma dator.

1. Tryck eller klicka **Redigera** väljer du **Transport** -fliken.
1. Konfigurera URI genom att ersätta **localhost** med IP-adressen eller adressen till den AEM publiceringsinstansen.

   ![chlimage_1-139](assets/chlimage_1-139.png)

### Ansluta AEM till Adobe Campaign {#connecting-aem-to-adobe-campaign}

Innan ni kan använda AEM och Adobe Campaign tillsammans måste ni etablera en länk mellan båda lösningarna så att de kan kommunicera.

1. Anslut till AEM.
1. Välj **AEM logotyp** > **verktyg** ikon > **Distribution** > **Cloud Services** sedan **Konfigurera nu** i Adobe Campaign.

   ![chlimage_1-140](assets/chlimage_1-140.png)

1. Skapa en ny konfiguration genom att ange en **Titel** och klicka **Skapa** eller välj den befintliga konfiguration som du vill länka till din Adobe Campaign-instans.
1. Redigera konfigurationen så att den matchar parametrarna för din Adobe Campaign-instans.

   * **Användarnamn**: **aemserver**, som används av paketoperatorn Adobe Campaign AEM Integration för att skapa länken mellan de två lösningarna.
   * **Lösenord**: Lösenord för operatorn Adobe Campaign aemserver. Du kan behöva ange lösenordet för den här operatorn igen direkt i Adobe Campaign.
   * **API-slutpunkt**: Adobe Campaign instans-URL.

1. Välj **Anslut till Adobe Campaign** och klicka **OK**.

   ![chlimage_1-141](assets/chlimage_1-141.png)

   >[!NOTE]
   Efter [skapa e-post och publicera den](/help/sites-authoring/campaign.md)måste du publicera konfigurationen på nytt på din publiceringsinstans.

   ![chlimage_1-142](assets/chlimage_1-142.png)

>[!NOTE]
Om anslutningen misslyckas kontrollerar du följande:
* Du kan stöta på ett certifikatproblem när du använder en säker anslutning till en Adobe Campaign-instans (https). Du måste lägga till Adobe Campaign-instanscertifikatet i **cacerts** fil med AEM JDK.
* En säkerhetszon måste konfigureras för [aemserver, operator](#connecting-aem-to-adobe-campaign) i Adobe Campaign. I **serverConf.xml** -filen, **allowUserPassword** säkerhetszonens attribut måste anges till **true** för att auktorisera AEM till Adobe Campaign i inloggnings-/lösenordsläge.
>
Se även [Felsöka integrationen mellan AEM och Adobe Campaign](/help/sites-administering/troubleshooting-campaignintegration.md).

### Konfigurera externaliseraren {#configuring-the-externalizer}

Du måste [konfigurera externaliseraren](/help/sites-developing/externalizer.md) i AEM på din författarinstans. Externalizer är en OSGi-tjänst som gör att du kan omvandla en resurssökväg till en extern och absolut URL. Den här tjänsten tillhandahåller en central plats för att konfigurera dessa externa URL:er och skapa dem.

Se [Konfigurera externaliseraren](/help/sites-developing/externalizer.md) för allmänna instruktioner. Kontrollera att du har konfigurerat publiceringsservern på `https://<host>:<port>/system/console/configMgr/com.day.cq.commons.impl.ExternalizerImpl`inte peka på `localhost:4503` till en server som kan nås av Adobe Campaign-konsolen.

Om den pekar på `localhost:4503` eller någon annan server som Adobe Campaign inte kan nå visas inte bilderna på Adobe Campaign-konsolen.

![chlimage_1-143](assets/chlimage_1-143.png)

## Avancerade konfigurationer {#advanced-configurations}

Du kan även utföra några avancerade konfigurationer, som:

* Hantera personaliseringsfält och -block.
* Inaktivera ett personaliseringsblock.
* Hantera måltilläggsdata.

### Hantera fält och block för personalisering {#managing-personalization-fields-and-blocks}

De fält och block som är tillgängliga för att lägga till personalisering i ditt e-postinnehåll i AEM hanteras av Adobe Campaign.

En standardlista har angetts men kan ändras. Du kan också lägga till eller dölja fält och block för personalisering.

#### Lägga till ett anpassningsfält {#adding-a-personalization-field}

Om du vill lägga till ett nytt anpassningsfält till de som redan är tillgängliga måste du utöka Adobe Campaign **nms:seedMember** schema enligt följande:

>[!CAUTION]
Fältet som du måste lägga till måste redan ha lagts till via ett mottagarschematillägg (**nms:mottagare**). Mer information finns i [Konfiguration](https://docs.campaign.adobe.com/doc/AC6.1/en/CFG_Editing_schemas_Editing_schemas.html) guide.

1. Gå till **Administration** > **Konfiguration** > **Datamodeller** i Adobe Campaign.
1. Välj **Nytt**.

   ![chlimage_1-144](assets/chlimage_1-144.png)

1. I popup-fönstret väljer du **Utöka data i tabellen med hjälp av ett tilläggsschema** och klicka **Nästa**.

   ![chlimage_1-145](assets/chlimage_1-145.png)

1. Ange de olika parametrarna för det utökade schemat:

   * **Schema**: välj **nms:seedMember** schema. De andra fälten i fönstret fylls i automatiskt.
   * **Namnutrymme**: anpassa namnområdet för det utökade schemat.

1. Redigera XML-koden för schemat för att ange fältet som du vill lägga till där. Mer information om hur du utökar scheman i Adobe Campaign finns i [Konfigurationsguide](https://docs.campaign.adobe.com/doc/AC6.1/en/CFG_Editing_schemas_Extending_a_schema.html).
1. Spara ditt schema och uppdatera sedan Adobe Campaign-databasstrukturen via **verktyg** > **Avancerat** > **Uppdatera databasstruktur** -menyn i konsolen.
1. Koppla från och återanslut sedan till Adobe Campaign-konsolen för att spara ändringarna. Det nya fältet visas nu i listan med anpassningsfält som är tillgängliga i AEM.

#### Exempel {#example}

Lägga till en **Registreringsnummer** måste du ha följande element:

* The **nms:mottagare** schematillägg namngivet **cus:mottagare** innehåller:

```xml
<element desc="Recipient table (profiles)" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">

  <attribute dataPolicy="smartCase" desc="Recipient registration number" 
  label="Registration Number"
  length="50" name="registrationNumber" type="string"/>

</element>
```

The **nms:seedMember** schematillägg namngivet **cus:seedMember** innehåller:

```xml
<element desc="Seed to insert in the export files" img="nms:unknownad.png" label="Seed addresses" labelSingular="Seed" name="seedMember">

  <element name="custom_nms_recipient">
    <attribute name="registrationNumber" 
    template="cus:recipient:recipient/@registrationNumber"/>
  </element>

</element>
```

The **Registreringsnummer** -fältet är nu en del av de tillgängliga personaliseringsfälten:

![chlimage_1-146](assets/chlimage_1-146.png)

#### Dölja ett personaliseringsfält {#hiding-a-personalization-field}

Om du vill dölja ett personaliseringsfält bland dem som redan finns måste du utöka Adobe Campaign **nms:seedMember** schemat enligt informationen i [Lägga till ett anpassningsfält](#adding-a-personalization-field) -avsnitt. Använd följande steg:

1. Kopiera fältet som du vill ta från **nms:seedMember** schema i utökat schema (**cus:seedMember** till exempel).
1. Lägg till **advanced=&quot;true&quot;** XML-attribut till fältet. Det visas inte längre i listan med anpassningsfält som är tillgängliga i AEM.

   Om du till exempel vill dölja **Mellannamn** fält, **cud:seedMember** schemat måste innehålla följande element:

   ```xml
   <element desc="Seed to insert in the export files" img="nms:unknownad.png" label="Seed addresses" labelSingular="Seed" name="seedMember">
   
     <element name="custom_nms_recipient">
       <attribute advanced="true" name="middleName"/>
     </element>
   
   </element>
   ```

### Inaktivera ett personaliseringsblock {#deactivating-a-personalization-block}

Så här inaktiverar du ett personaliseringsblock bland de tillgängliga:

1. Gå till **Resurser** > **Campaign Management** > **Personaliseringsblock** i Adobe Campaign.
1. Markera det anpassningsblock som du vill inaktivera i AEM.
1. Rensa **Synligt på anpassningsmenyerna** och spara ändringarna. Blocket visas inte längre i listan med anpassningsblock som är tillgängliga i Adobe Campaign.

   ![chlimage_1-147](assets/chlimage_1-147.png)

### Hantera måltilläggsdata {#managing-target-extension-data}

Du kan också infoga måltilläggsdata för personalisering. Måltilläggsdata (kallas även&quot;måldata&quot;) kommer från att till exempel ha berikat eller lagt till data i en fråga i ett kampanjarbetsflöde. Mer information finns i [Skapa frågor](https://docs.campaign.adobe.com/doc/AC/en/PTF_Creating_queries_About_queries_in_Campaign.html) och [Förbättra data](https://docs.campaign.adobe.com/doc/AC/en/WKF_Use_cases_Enriching_data.html) -avsnitt.

>[!NOTE]
Data i målet är bara tillgängliga om det AEM innehållet synkroniseras med en Adobe Campaign-leverans. Se [Synkronisera innehåll som skapats i AEM med en leverans från Adobe Campaign](/help/sites-authoring/campaign.md#synchronizing-content-created-in-aem-with-a-delivery-from-adobe-campaign-classic).

![chlimage_1-148](assets/chlimage_1-148.png)
