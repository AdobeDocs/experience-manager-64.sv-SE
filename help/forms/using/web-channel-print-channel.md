---
title: Skriva ut kanal och webbkanal
seo-title: Skriva ut kanal och webbkanal
description: Importera utskriftskanalmallar samt skapa och aktivera webbkanalsmallar
seo-description: Importera utskriftskanalmallar samt skapa och aktivera webbkanalsmallar
uuid: 19e6ffab-00d2-4084-9ee7-9643b11eb6c6
topic-tags: interactive-communications
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 71bba66a-3cac-445b-9941-aa4bcf9b2160
translation-type: tm+mt
source-git-commit: 73d0dea62c294bea435364fb9c6892d80751d90d

---


# Skriva ut kanal och webbkanal {#print-channel-and-web-channel}

Importera utskriftskanalmallar samt skapa och aktivera webbkanalsmallar

Interaktiv kommunikation kan levereras via två kanaler: tryck och webb. Tryckkanalen används för att skapa PDF-filer och pappersdokument, t.ex. ett utskrivet brev som påminnelse om betalning av försäkringspremier, medan webbkanalen används för att leverera onlineupplevelser, t.ex. kreditkortsutdrag på en webbplats.

Författare av interaktiv kommunikation kan återanvända resurser som dokumentfragment och bilder för att skapa både utskrifts- och webbversioner av interaktiv kommunikation.

En av förutsättningarna för att [skapa en interaktiv kommunikation](/help/forms/using/create-interactive-communication.md) är att mallarna för utskrift och/eller webbkanal är tillgängliga på servern. Mallförfattare skapar webbkanalsmallen i själva AEM, men utskriftskanalmallen XDP skapas i Adobe Forms Designer och överförs till servern.

## Utskriftskanal {#printchannel}

Utskriftskanalen i en interaktiv kommunikation använder XFA-formulärmallen, XDP. En XDP har utformats i Adobe Forms Designer. Mer information om hur du skapar utskriftskanalmallar finns i [Layoutdesign](/help/forms/using/layout-design-details.md). Om du vill använda en utskriftskanalmall i din interaktiva kommunikation måste du överföra mallen till AEM Forms-servern.

### Ladda upp utskriftskanalmall för interaktiv kommunikation {#upload-interactive-communication-print-channel-template}

Om du vill överföra mallen måste du vara medlem i gruppen formulär-användare. Följ de här stegen för att överföra utskriftskanalmallen (XDP) till AEM Forms:

1. Välj **[!UICONTROL Formulär]** > **[!UICONTROL Formulär och dokument]**.

1. Tryck på **[!UICONTROL Skapa]** > **[!UICONTROL Filöverföring]**.

   Navigera och välj lämplig utskriftskanalmall (XDP) och tryck på **[!UICONTROL Öppna]**.

## Webbkanal {#web-channel}

Mallförfattare och administratörer kan skapa, redigera och aktivera webbmallar. Om du vill att andra användare ska kunna skapa webbmallar måste du ge dem behörighet. Mer information finns i Administrera [för](/help/sites-administering/user-group-ac-admin.md)användar-, grupp- och åtkomsträttigheter.

### Redigerar webbkanalsmall {#authoring-web-channel-template}

Om du vill skapa en webbkanalmall måste du först skapa en mallmapp. När du har skapat en webbmall i en mallmapp måste du aktivera mallen så att formuläranvändarna kan skapa en webbkanal för en interaktiv kommunikation som är baserad på mallen.

Så här skapar du en webbkanalsmall:

1. Skapa en mallmapp om du vill behålla dina webbmallar för interaktiv kommunikation, om du inte redan har en. Mer information finns i Mallmappar i [Sidmallar - redigerbar](/help/sites-developing/page-templates-editable.md).

   1. Tryck på **[!UICONTROL Tools]** ![tools-1](assets/tools-1.png) > **[!UICONTROL Configuration Browser]**.
   1. Tryck på **[!UICONTROL Skapa]** på sidan Configuration Browser.
   1. I dialogrutan Skapa konfiguration anger du en rubrik för mappen, markerar **[!UICONTROL Redigerbara mallar]** och trycker på **[!UICONTROL Skapa]**.

      Mappen skapas och visas på sidan Konfigurationsläsare.

1. Navigera till rätt mallmapp och skapa en webbmall.

   1. Navigera till rätt mallmapp genom att välja **[!UICONTROL Verktyg]** > **[!UICONTROL Mallar > Mapp]**.
   1. Tryck på **[!UICONTROL Skapa]**.
   1. Välj **[!UICONTROL Interaktiv kommunikation - webbkanal]** och tryck på **[!UICONTROL Nästa]**.
   1. Ange en malltitel och beskrivning och tryck sedan på **[!UICONTROL Skapa]**.

      Mallen skapas och en dialogruta visas.

   1. Tryck på **[!UICONTROL Öppna]** för att öppna mallen som du har skapat i mallredigeraren.

      Mallredigeraren visas.

      ![webbkanalmall](assets/webchanneltemplate.png)

      När du skapar eller redigerar en mall finns det olika aspekter som mallskaparen kan definiera. Att skapa eller redigera en mall liknar att skapa sidor. Mer information finns i Redigera mallar - mallskapare när du [skapar sidmallar](/help/sites-authoring/templates.md).

1. Aktivera mallen om du vill tillåta att den här mallen används för att skapa interaktiv kommunikation.

   1. Tryck på **[!UICONTROL Verktyg]** ![- 1](assets/tools-1.png) > **[!UICONTROL Mallar]**.
   1. Navigera till rätt mall, markera den och tryck på **[!UICONTROL Aktivera]** . I varningsmeddelandet trycker du på **[!UICONTROL Aktivera]**.

      Mallen är aktiverad och dess status visas som Aktiverad. Nu kan du skapa en interaktiv kommunikation där du kan använda den nya webbkanalsmallen.

### Skriv ut kanal som master för webbkanal {#print-channel-as-master-for-web-channel}

När du skapar en interaktiv kommunikation kan författare välja det här alternativet för att skapa webbkanalen synkroniserat med utskriftskanalen. Om du använder en tryckkanal som huvudkanal för webbkanalen kan du säkerställa att innehållet, arvet och databindningen för webbkanalen hämtas från tryckkanalen och att ändringarna som görs i den kan återspeglas i webbkanalen. De som skapar interaktiv kommunikation får dock bryta arvet för specifika komponenter i webbkanalen efter behov.

![printweb_2-2](assets/printweb_2-2.png)

