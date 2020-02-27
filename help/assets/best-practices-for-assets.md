---
title: Bästa tillvägagångssätt för att hantera resurser med AEM
description: Identifiera och följ de bästa metoderna som förbättrar systemstabilitet och prestanda vid inläsning, beroende på driftsättning av AEM Assets och funktioner som används för att importera och bearbeta resurser.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0e0e2aa693c30c8e1ef1033b936b82d83e5b348e

---


# Metodtips för AEM Assets {#best-practices-for-assets}

Adobe Experience Manager Assets (AEM) Assets är en viktig del i att leverera digitala marknadsföringsupplevelser av hög kvalitet som bidrar till att uppnå affärsmålen genom att öka innehållets hastighet. Om du arbetar med ett stort antal resurser i AEM Assets eller regelbundet/regelbundet överför flera resurser, inklusive videor och dynamiska media, är det viktigt att optimera din digitala resurshantering för att systemet ska bli effektivt.

Beroende på hur du har positionerat AEM Assets för din organisation och vilka funktioner du använder när det gäller tillgångsintag, återgivningsgenerering och metadataextrahering, kan det vara bra att identifiera och följa vedertagna metoder inom olika områden, vilket förbättrar systemets stabilitet och prestanda vid inläsning.

När du har granskat följande handböcker får du de kunskaper och verktyg du behöver för att skapa och hantera ett resurshanteringssystem för företag som passar dina behov.

* [Prestandajusteringsguide](performance-tuning-guidelines.md)för resurser innehåller en uppsättning metodtips som kan följas när som helst i implementeringen, även när du är klar, för att säkerställa att du får ut så mycket som möjligt av systemet.
* [Handbok](assets-sizing-guide.md)för storleksändring av resurser När du gör uppskattningar för en resursimplementering är det viktigt att se till att det finns tillräckligt med resurser tillgängliga när det gäller lagring av resurser, processor, minne, IO och nätverkets genomströmning. Om du ändrar storlek på många av dessa objekt måste du förstå hur många resurser som läses in i systemet. Den här guiden innehåller metodtips som hjälper dig att fastställa effektiva mått för beräkning av den infrastruktur och de resurser som krävs för att driftsätta AEM Assets samt ett storleksbedömningsverktyg.
* [Migreringsguide](assets-migration-guide.md)för resurser Om du vill migrera resurser från ditt äldre system till AEM Resurser finns det flera steg som ska övervägas för att effektivisera migreringsprocessen. Migreringsguiden innehåller metodtips för de uppgifter du utför för att överföra resurserna till AEM på ett fasvis sätt. Detta inkluderar att lägga till metadata, generera återgivningar och aktivera resurser för publicering av distributionen.
* [Resurser för nätverksaspekter](assets-network-considerations.md)När AEM-distribution hanteras är det viktigt att förstå nätverkstopologin för att förstå nätverksprestanda, identifiera kontrollpunkter och beskriva den förväntade användarupplevelsen. Dokumentet Assets Network Considerations behandlar nätverksaspekter när du utformar din AEM Asset-distribution.
* [Handbok](assets-monitoring-best-practices.md)för övervakning av resurser När AEM-distributionen är genomförd bör du övervaka vissa uppgifter och systemet i allmänhet för att säkerställa systemintegriteten och effektiviteten i åtgärderna. Övervakningsguiden innehåller bästa praxis för övervakning av olika aspekter av ditt system.
* (Föråldrat) Funktioner som avlastningsguide [](assets-offloading-best-practices.md)för hantering av stora filer och arbetsflöden i AEM Assets kan förbruka mycket processorkraft, minne och I/O-resurser. Genom att avlasta dessa uppgifter kan du minska kostnaderna för processor, minne och IO-belastning. Handboken för avlastning av resurser innehåller rekommenderade användningsfall och bästa praxis för avlastning av resurser.
* [AEM-datorappens bästa praxis](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app-best-practices.html)AEM-datorappen länkar din DAM-lösning (Digital Asset Management) till din dator så att du kan öppna de filer som är tillgängliga i AEM Web UI direkt på skrivbordet. Det lättanvända arbetsflödet i AEM-skrivbordsappen aktiveras med hjälp av nätverksdelningsteknik från operativsystemen på datorn. I den här guiden förklaras de viktigaste funktionerna och den rekommenderade användningen av AEM-datorprogrammet.
* [Bästa praxis](aem-cc-integration-best-practices.md)för integrering med AEM och Creative CloudDu kan integrera din AEM-distribution med Creative Cloud på flera sätt. Om du följer några metodtips för att effektivisera arbetsflödena för integrering och överföring av resurser blir det effektivare. Den här guiden innehåller metodtips om hur du integrerar AEM Assets med Adobe Creative Cloud.
* (Föråldrat) [AEM till Creative Cloud-mappen där metodtips](aem-cc-folder-sharing-best-practices.md)för att dela med dig av dem kan du konfigurera AEM så att användare i DAM kan dela mappar med Creative Cloud-användare (CC), så att de är tillgängliga som delade mappar i Creative Cloud Assets-tjänsten. Funktionen kan användas för utbyte av filer mellan kreativa team och DAM-användare. I den här guiden beskrivs de bästa sätten att utnyttja funktionen för delning av AEM-mappar i Creative Cloud.
