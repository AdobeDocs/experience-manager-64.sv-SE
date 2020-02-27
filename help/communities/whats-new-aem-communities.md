---
title: Nyheter i AEM 6.4 Communities
seo-title: Nyheter i AEM 6.4 Communities
description: 'null'
seo-description: 'null'
uuid: e4bf343c-59cd-48ac-bee4-85db109e4c65
contentOwner: mgulati
discoiquuid: 3e3c867f-afb0-4402-94f4-16e1a556ddee
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c

---


# Nyheter i AEM 6.4 Communities {#what-s-new-in-aem-communities}

AEM Communities erbjuder ett ramverk för företag att samarbeta med partners, kunder och anställda. Det ger sociala funktioner till webbplatsstrukturen och hjälper företag att engagera och förmedla kunskap till sina intressenter för att förbättra deras varumärke på det sätt de vill.

AEM 6.4 Communities innehåller funktioner som förbättrar användarupplevelserna och förenklar rutinuppgifterna för communityadministratörer, moderatorer och chefer.

Läs vidare för att få en snabb introduktion till nya funktioner och förbättringar. Se även [versionsinformation](../release-notes/communities-release-notes.md)för AEM 6.4 Communities. AEM 6.4 Communities-dokumentation finns på [AEM 6.4 Communities User Guide](home.md).

## Hantera undergrupper eller samhällsgrupper {#managing-sub-communities-or-community-groups}

Med AEM Communities kan communityadministratörer skapa grupper och undergrupper på communitysajten med hjälp av fördefinierade mallar i redigeringsmiljön. Dessa grupper fungerar som undergrupper, som kan ärva många konfigurationer, som teman och format från den överordnade webbplatsen. Dessa grupper kan dock skilja sig från den överordnade platsen, till exempel med en annan uppsättning gruppmoderatorer eller variera i säkerhetsnivån. Dessa grupper fungerar som fristående, fullt utvecklade minicommunityer som ytterligare förstärks av följande förbättringar.

### Skapa flerspråkiga grupper i ett enda steg {#create-multi-locale-groups-in-single-step}

Som en del av en communitywebbplats kan flerspråkiga grupper skapas i en enda åtgärd. **[!UICONTROL Det här är praktiskt om det finns fler tillgängliga fält för communitygruppsspråk]** på sidan **[!UICONTROL Gruppmall]** , som du kan använda när du skapar en [ny community-grupp](groups.md) på en communitywebbplats.

![flerspråkig grupp-1](assets/multilingualgroup-1.png)

Om du vill skapa sådana grupper behöver du bara navigera till gruppsamlingen för den önskade communitywebbplatsen från webbplatskonsolen. Skapa en grupp och ange önskade språk i fältet **[!UICONTROL Ytterligare tillgängliga språk för communitygrupper]** på sidan **[!UICONTROL Gruppmall]** för användargrupper.

### Ta bort communitygrupper från gruppkonsolen {#delete-community-groups-from-groups-console}

AEM 6.4 Communities innehåller ikonen Ta bort grupp för befintliga communitygrupper i communitygruppssamlingen i Community Sites console. Detta aktiverar [gruppborttagning](groups.md#deleting-the-group) med ett klick, tillsammans med borttagning av alla objekt som är kopplade (till exempel innehåll och användarmedlemskap) till gruppen.

![ta bort](assets/deletegrp.png)

### Skapa och tilldela aktiveringsresurser inom grupper {#create-and-assign-enablement-resources-within-groups}

Utbildningsmaterial kan nu skapas, hanteras och publiceras för en viss uppsättning målgruppsmedlemmar. På grund av att det finns katalog- och tilldelningsfunktioner för communitygrupper (och inte bara för hela communitywebbplatsen) kan aktiveringsansvariga [tilldela aktiveringsresurser](resource.md) och utbildningsvägar till en liten mängd personer också.

![tilldelningskatalog](assets/assignmentcatalog.png)

## Modererar användargenererat innehåll {#moderating-user-generated-content}

AEM 6.4 Communities har fått få förbättringar vad gäller moderering, som är avgörande för att underlätta den dagliga användningen för moderatorer i communityn.

### Automatisk identifiering av skräppost {#automatic-spam-detection}

Ny motor för skräppostavkänning hjälper till att filtrera bort oönskat och oombett användargenererat innehåll på communitywebbplatser eller grupper. När den här funktionen är aktiverad kan en del användargenererat innehåll markeras som skräppost eller Inte skräppost baserat på en fördefinierad uppsättning skräppostord. Moderatorerna kan agera vidare på innehållet för att neka eller tillåta att det visas på publiceringsinstansen. Dessa modereringsåtgärder kan utföras internt eller via en masmodereringskonsol.

![spamdetection-1](assets/spamdetection-1.png)

[Spam Detector](moderate-ugc.md#spam-detection) hittar och flaggar ett visst användargenererat innehåll med 90 % precision. Den här funktionen är dock inte aktiverad som standard. För att kunna aktivera det måste communityadministratörer navigera till configMgr på system/konsol och lägga till skräppostprocess.

![spamprocess-1](assets/spamprocess-1.png)

### Nya filter (besvarat/obesvarat) för QnA {#new-answered-unanswered-filters-for-qna}

AEM 6.4 lägger till två [nya filter](moderation.md#filter-rail), som heter Answered och Not Answered for QnA questions, i masmodereringskonsolen. Dessa filter är tillgängliga under Status i Filterspår.

![status](assets/statuses.png)

När du väljer status Besvarat visas alla besvarade frågor för moderatorn i innehållsområdet. Om du bara väljer status Inte besvarat kommer moderatorn att se allt innehåll (för alla innehållstyper) förutom de besvarade frågorna, eftersom egenskapen som är ansvarig för den besvarade frågan inte finns för frågor som inte besvarats och annat innehåll som forumämne, bloggartikel eller kommentarer.

### Kontrollfilter för bokmärken {#bookmark-moderation-filters}

Med AEM Communities kan man [bokmärka de fördefinierade modereringsfiltren](moderation.md#filter-rail) på modereringskonsolen. Dessa sparade bokmärken kan granskas senare och delas med andra användare.

Användarna behöver bara välja önskade filter från filterkanalen i modereringskonsolen för att visa den filtrerade UGC:n och bokmärka filtren i sina webbläsare. Dessa filter läggs till i slutet av URL-strängen och kan därför delas, återanvändas och granskas senare.

## Hantera communityplatser {#managing-community-sites}

AEM 6.4 Communities innehåller förbättringar av webbplatshanteringen, som gör det enkelt för webbplatsadministratörer att skapa, hantera och ta bort ett flertal communitysajter på olika språk.

### Skapa communitysajter för flera språk i ett enda steg {#create-multi-locale-community-sites-in-one-step}

Med AEM Communities kan man skapa [flerspråkiga communitysajter](create-site.md) i en enda åtgärd. Det här är möjligt på grund av att det finns flera språk att välja mellan i fältet **[!UICONTROL Baskråk]** för communitywebbplats på sidan **[!UICONTROL Webbplatsmall]** , samtidigt som en ny communitywebbplats skapas från webbplatskonsolen.

![multilocalesite](assets/multilocalesite.png)

Användarna kan välja konfigurationsmappar, branding och många andra konfigurationer samtidigt för alla dessa webbplatser.

### Ta bort communitywebbplatser från webbplatskonsolen {#delete-community-sites-from-sites-console}

AEM 6.4 Communities innehåller ikonen Ta bort plats på befintliga communitysajter i community-konsolen. Detta gör att du kan [ta bort platsen](create-site.md) och tillhörande objekt med ett klick.

![webbplatseråtgärder](assets/siteactions.png)

## Hantera användargenererat innehåll och användarprofiler {#managing-ugc-and-user-profiles}

AEM Communities skyddar användarnas data i centrum för användarupplevelsen och ger tillgång till API: [er som är färdiga](user-ugc-management-service.md) och [exempelservrar](https://github.com/Adobe-Marketing-Cloud/aem-communities-ugc-migration/tree/master/bundles/communities-ugc-management-servlet). Dessa API:er hjälper till att hantera (massborttagning och bulkexport) användargenererat innehåll och ta bort användarprofiler, och är avgörande för att hantera EU GDPR-kompatibilitetsbegäranden.

## Vad som har ändrats {#what-s-changed}

* Captcha-verifiering, när du skapar en ny community-webbplats, är inte längre tillgängligt i körklart läge i AEM 6.4 Communities. Webbplatsen Communities kan dock anpassas så att den innehåller [Google Component reCAPTCHA](https://helpx.adobe.com/experience-manager/using/aem_recaptcha.html) för bättre säkerhet.
* Alternativet att överföra en anpassad CSS har tagits bort från communitywebbplatserna och grupptemat.
* Ikonerna Endast innehåll och Sök har lagts till i filterraden i gränssnittet för massmoderering.
* Filtret Sökväg för innehåll har lagts till i filterraden i gränssnittet för massmoderering.
* Växla till gruppläge och Avsluta gruppläge har tagits bort från gränssnittet för massmoderering. Om du vill växla till flervalsläge klickar du på ikonen Markera ( ![markering](assets/selecticon.png)) på ett inlägg, som visas när du hovrar över det med musen (skrivbordet) eller trycker och håller ett finger på inlägget (mobilen).
