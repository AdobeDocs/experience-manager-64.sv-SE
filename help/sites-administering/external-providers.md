---
title: Analyser med externa leverantörer
seo-title: Analyser med externa leverantörer
description: Lär dig mer om Analytics med externa leverantörer.
seo-description: Lär dig mer om Analytics med externa leverantörer.
uuid: bea8ec38-a190-46f9-a5fa-8d65321fdf20
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: bf8fd156-4be9-43f8-8948-cf7f91c25f1b
translation-type: tm+mt
source-git-commit: f1a5e4c5c8411e10887efab517115fee0fd1890a
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---


# Analyser med externa leverantörer{#analytics-with-external-providers}

Analyser kan ge dig viktig och intressant information om hur webbplatsen används.

Det finns olika färdiga konfigurationer för integrering med rätt tjänst, till exempel:

* [Adobe Analytics](/help/sites-administering/adobeanalytics.md)
* [Adobe Target](/help/sites-administering/target.md)

Du kan också konfigurera din egen instans av **generiska analysfragment** för att definiera en ny tjänstkonfiguration.

Informationen samlas sedan in med små kodfragment som läggs till på webbsidorna. Till exempel:

>[!CAUTION]
>
>Skript får inte omslutas av `script`-taggar.

```
var _gaq = _gaq || [];
_gaq.push(['_setAccount', 'UA-XXXXX-X']);
_gaq.push(['_trackPageview']);

(function() {
    var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
    ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'https://www') + '.google-analytics.com/ga.js';
    var s = document.getElementsByTagName('script')[0]; s.parentNode.insertBefore(ga, s);
})();
```

Sådana fragment gör det möjligt att samla in data och generera rapporter. De faktiska data som samlas in beror på providern och vilket kodfragment som används. Exempel på statistik är:

* hur många besökare som helst
* hur många sidor som besöktes
* söktermer som används
* landningssidor

>[!CAUTION]
>
>Demonsplatsen Geometrixx-Outdoor är konfigurerad så att attributen i Sidegenskaper läggs till i HTML-källkoden (precis ovanför `</html>`-sluttaggen) i motsvarande `js`-skript.
>
>
>Om din egen `/apps` inte ärver från standardsidkomponenten ( `/libs/foundation/components/page`) måste du (eller dina utvecklare) se till att motsvarande `js`-skript inkluderas, till exempel genom att ta med `cq/cloudserviceconfigs/components/servicescomponents` eller använda en liknande mekanism.
>
>
>Utan detta kommer ingen av tjänsterna (Generic, Analytics, Target, etc.) att fungera.

## Skapa en ny tjänst med ett allmänt kodfragment {#creating-a-new-service-with-a-generic-snippet}

För den grundläggande konfigurationen:

1. Öppna konsolen **Verktyg**.

1. Expandera **Konfigurationer av Cloud Services** från den vänstra rutan.

1. Dubbelklicka på **Generic Analytics-kodfragment** för att öppna sidan:

   ![analytics_genericoverview](assets/analytics_genericoverview.png)

1. Klicka på + för att lägga till en ny konfiguration med dialogrutan. åtminstone tilldela ett namn, till exempel Google Analytics:

   ![analytics_addconfig](assets/analytics_addconfig.png)

1. Klicka på **Skapa** så öppnas dialogrutan för kodfragment omedelbart - klistra in lämpligt javascript-fragment i fältet:

   ![analytics_snippet](assets/analytics_snippet.png)

1. Klicka på **OK** för att spara.

## Använda din nya tjänst på sidor {#using-your-new-service-on-pages}

När du har skapat tjänstkonfigurationen behöver du nu konfigurera de sidor som krävs för att använda den:

1. Navigera till sidan.

1. Öppna **Sidegenskaperna** från sidesparken och sedan fliken **Cloud Services**.

1. Klicka på **Lägg till tjänst** och välj sedan önskad tjänst; till exempel **Generic Analytics-kodfragment**:

   ![analytics_selectService](assets/analytics_selectservice.png)

1. Klicka på **OK** för att spara.

1. Du återgår till fliken **Cloud Services**. **Kodavsnittet för allmän analys** visas nu med meddelandet `Configuration reference missing`. Använd listrutan för att välja en specifik tjänstinstans; till exempel google-analys:

   ![analytics_selectspecificservice](assets/analytics_selectspecificservice.png)

1. Klicka på **OK** för att spara.

   Utdraget visas nu om du visar sidans sidkälla.

   Efter en lämplig tidsperiod kan du visa den statistik som har samlats in.

   >[!NOTE]
   >
   >Om konfigurationen är kopplad till en sida som har underordnade sidor, ärvs tjänsten även av dessa sidor.

