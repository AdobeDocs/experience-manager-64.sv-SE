---
title: Bästa tillvägagångssätt för att hantera resurser med AEM
description: Identifiera och följ de bästa metoderna som förbättrar systemstabilitet och prestanda vid inläsning, beroende på [!DNL Experience Manager] resursdriftsättning och funktioner som används för att importera och bearbeta resurser.
contentOwner: AG
feature: Asset Management
role: Architect,Admin
exl-id: e2ab924b-53cb-4011-8c0a-9e8e59dd2f16
source-git-commit: d750c852b6367d753d18be57c8910bf5671fd5e8
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Metodtips för [!DNL Experience Manager] Assets {#best-practices-for-assets}

Adobe Experience Manager Assets är en viktig del i att leverera högkvalitativa digitala marknadsföringsupplevelser som bidrar till att uppnå affärsmålen genom att öka innehållets hastighet. Om du arbetar med ett stort antal resurser inom [!DNL Assets] eller regelbundet/regelbundet överför flera resurser, inklusive videor och dynamiska media, är det viktigt att optimera upplevelsen av den digitala resurshanteringen för att systemet ska bli effektivt.

Beroende på hur du har positionerat [!DNL Assets] för din organisation och vilka funktioner du använder för att hantera resurser, generera återgivningar och ta fram metadata, blir det betydligt bättre att identifiera och följa vedertagna metoder inom olika områden och prestanda vid inläsning.

När du har granskat följande handböcker får du de kunskaper och verktyg du behöver för att skapa och hantera ett resurshanteringssystem för företag som passar dina behov.

* [Prestandajusteringsguide ](performance-tuning-guidelines.md)
för resurserInnehåller en uppsättning metodtips som kan följas när som helst i implementeringen, även när du är klar, för att säkerställa att du får ut så mycket som möjligt av systemet.
* [Guide ](assets-sizing-guide.md)
för storleksändring av resurserNär du gör uppskattningar för en resursimplementering är det viktigt att se till att det finns tillräckligt med resurser tillgängliga när det gäller lagring av resurser, processor, minne, IO och nätverkets genomströmning. Om du ändrar storlek på många av dessa objekt måste du förstå hur många resurser som läses in i systemet. Den här guiden innehåller bästa praxis som hjälper till att fastställa effektiva mått för beräkning av den infrastruktur och de resurser som krävs för att distribuera [!DNL Experience Manager]-resurser samt ett storleksbedömningsverktyg.
* [Migreringsguide ](assets-migration-guide.md)
för resurserOm du vill migrera resurser från ditt äldre system till  [!DNL Experience Manager] Assets finns det flera steg som ska övervägas för att effektivisera migreringsprocessen. Migreringsguiden innehåller metodtips om de åtgärder du utför för att överföra resurserna till [!DNL Experience Manager] på ett fasvis sätt. Detta inkluderar att lägga till metadata, generera återgivningar och aktivera resurser för publicering av distributionen.
* [Resurser ](assets-network-considerations.md)
för nätverksaspekterNär  [!DNL Experience Manager] distributionen hanteras är det viktigt att förstå nätverkstopologin för att förstå nätverksprestanda, identifiera kontrollpunkter och beskriva den förväntade användarupplevelsen. Dokumentet Assets Network Considerations behandlar nätverksaspekter när du utformar din [!DNL Experience Manager]-resursdistribution.
* [Handbok ](assets-monitoring-best-practices.md)
för tillgångsövervakningNär  [!DNL Experience Manager] distributionen är klar bör du övervaka vissa uppgifter och systemet i allmänhet för att säkerställa systemintegriteten och effektiviteten i åtgärderna. Övervakningsguiden innehåller bästa praxis för övervakning av olika aspekter av ditt system.
* (Föråldrat) [Guide för avlastning av resurser](assets-offloading-best-practices.md)
Att hantera stora filer och köra arbetsflöden i [!DNL Experience Manager] Resurser kan ta mycket processorkraft, minne och I/O-resurser i anspråk. Genom att avlasta dessa uppgifter kan du minska kostnaderna för processor, minne och IO-belastning. Handboken för avlastning av resurser innehåller rekommenderade användningsfall och bästa praxis för avlastning av resurser.
* [[!DNL Experience Manager] bästa praxis för datorprogram](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app-best-practices.html)
   [!DNL Experience Manager] datorprogrammet länkar din DAM-lösning (Digital Asset Management) till skrivbordet så att du kan öppna de filer som finns i  [!DNL Experience Manager] webbgränssnittet direkt på skrivbordet. [!DNL Experience Manager] datorappens lättanvända arbetsflöde aktiveras med hjälp av nätverksdelningsteknik som finns i operativsystemen. I den här guiden förklaras de viktigaste funktionerna och den rekommenderade användningen av [!DNL Experience Manager]-datorprogrammet.
* [[!DNL Experience Manager] och integrering med Creative Cloud ](aem-cc-integration-best-practices.md)
de bästa sättenDu kan integrera  [!DNL Experience Manager] driftsättningen med Creative Cloud på flera sätt. Om du följer några metodtips för att effektivisera arbetsflödena för integrering och överföring av resurser blir det effektivare. Den här guiden innehåller metodtips om hur du integrerar [!DNL Experience Manager]-resurser med Adobe Creative Cloud.
* (Föråldrat) [[!DNL Experience Manager] till Creative Cloud för att dela metodtips](aem-cc-folder-sharing-best-practices.md)
Du kan konfigurera [!DNL Experience Manager] så att användare i DAM kan dela mappar med Creative Cloud-användare, så att de är tillgängliga som delade mappar i tjänsten Creative Cloud Assets. Funktionen kan användas för utbyte av filer mellan kreativa team och DAM-användare. I den här guiden beskrivs de bästa sätten att utnyttja funktionen [!DNL Experience Manager] för delning av Creative Cloud-mappar.
