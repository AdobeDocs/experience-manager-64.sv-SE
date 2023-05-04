---
title: Bästa tillvägagångssätt för att hantera resurser med AEM
description: Identifiera och följ de bästa metoderna som förbättrar systemstabilitet och prestanda vid inläsning, beroende på [!DNL Experience Manager] Resursinstallation och funktioner som används för att importera och bearbeta resurser.
contentOwner: AG
feature: Asset Management
role: Architect,Admin
exl-id: e2ab924b-53cb-4011-8c0a-9e8e59dd2f16
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---

# Bästa tillvägagångssätt för [!DNL Experience Manager] Resurser {#best-practices-for-assets}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets är en viktig del i att leverera högkvalitativa digitala marknadsföringsupplevelser som bidrar till att uppnå affärsmålen genom att öka innehållets hastighet. Om du arbetar med ett stort antal resurser i [!DNL Assets] eller regelbundet/regelbundet ladda upp många olika resurser, inklusive videor och dynamiska medier, och det är avgörande att optimera upplevelsen av digital resurshantering för att systemet ska bli effektivt.

Beroende på hur du har placerat [!DNL Assets] för din organisation och de funktioner du använder när det gäller tillgångsintag, renderingsgenerering och metadataextrahering. Genom att identifiera och följa bästa praxis inom olika områden förbättras systemets stabilitet och prestanda avsevärt vid inläsning.

När du har granskat följande handböcker får du de kunskaper och verktyg du behöver för att skapa och hantera ett resurshanteringssystem för företag som passar dina behov.

* [Prestandajusteringsguide för resurser](performance-tuning-guidelines.md)
Innehåller en uppsättning metodtips som kan följas när som helst i implementeringen, även när du är klar, för att säkerställa att du får ut så mycket som möjligt av systemet.
* [Guide för resursstorlek](assets-sizing-guide.md)
När du skapar uppskattningar för en resursimplementering är det viktigt att se till att det finns tillräckliga resurser tillgängliga när det gäller lagring av resurser, processor, minne, IO och nätverksgenomströmning. Om du ändrar storlek på många av dessa objekt måste du förstå hur många resurser som läses in i systemet. Den här guiden innehåller bästa praxis som hjälper till att fastställa effektiva mått för beräkning av den infrastruktur och de resurser som krävs för driftsättning [!DNL Experience Manager] Resurser och ett verktyg för storleksändring.
* [Guide för resursmigrering](assets-migration-guide.md)
Om du vill migrera resurser från ditt äldre system till [!DNL Experience Manager] Resurser, det finns flera steg att tänka på för att effektivisera migreringsprocessen. Migreringsguiden innehåller bästa praxis för de uppgifter du utför för att överföra resurser till [!DNL Experience Manager] på ett fasvis sätt. Detta inkluderar att lägga till metadata, generera återgivningar och aktivera resurser för publicering av distributionen.
* [Resurser för nätverksaspekter](assets-network-considerations.md)
Vid hantering [!DNL Experience Manager] driftsättning, att förstå nätverkstopologin är viktigt för att förstå nätverksprestanda, identifiera chokepoints och beskriva den förväntade användarupplevelsen. Dokumentet Assets Network Considerations diskuterar nätverksaspekter när du designar [!DNL Experience Manager] Resursdistribution.
* [Resursövervakningsguide](assets-monitoring-best-practices.md)
Efter [!DNL Experience Manager] distribueras bör du övervaka vissa uppgifter och systemet i allmänhet för att säkerställa systemintegriteten och effektiviteten i åtgärderna. Övervakningsguiden innehåller bästa praxis för övervakning av olika aspekter av ditt system.
* (Föråldrat) [Guide för avlastning av resurser](assets-offloading-best-practices.md)
Hantera stora filer och arbetsflöden i [!DNL Experience Manager] Resurser kan förbruka mycket processorkraft, minne och I/O-resurser. Genom att avlasta dessa uppgifter kan du minska kostnaderna för processor, minne och IO-belastning. Handboken för avlastning av resurser innehåller rekommenderade användningsfall och bästa praxis för avlastning av resurser.
* [[!DNL Experience Manager] bästa praxis för datorprogram](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app-best-practices.html)
   [!DNL Experience Manager] datorprogrammet länkar din DAM-lösning (Digital Asset Management) till skrivbordet så att du kan öppna de filer som finns i [!DNL Experience Manager] webbgränssnitt direkt på skrivbordet. [!DNL Experience Manager] datorappens lättanvända arbetsflöde aktiveras med hjälp av nätverksdelningsteknik som finns i operativsystemen. Den här guiden förklarar viktiga funktioner och rekommenderar användning av [!DNL Experience Manager] datorprogram.
* [[!DNL Experience Manager] och bästa praxis för integrering med Creative Cloud](aem-cc-integration-best-practices.md)
Du kan integrera dina [!DNL Experience Manager] driftsättning med Creative Cloud på flera sätt. Om du följer några metodtips för att effektivisera arbetsflödena för integrering och överföring av resurser blir det effektivare. Den här guiden innehåller metodtips om integrering [!DNL Experience Manager] Assets with Adobe Creative Cloud.
* (Föråldrat) [[!DNL Experience Manager] till Creative Cloud-mapp för utbyte av bästa praxis](aem-cc-folder-sharing-best-practices.md)
Du kan konfigurera [!DNL Experience Manager] så att användare i DAM kan dela mappar med Creative Cloud-användare, så att de är tillgängliga som delade mappar i tjänsten Creative Cloud Assets. Funktionen kan användas för utbyte av filer mellan kreativa team och DAM-användare. I den här guiden förklaras de bästa sätten att utnyttja [!DNL Experience Manager] till Creative Cloud mappdelning.
