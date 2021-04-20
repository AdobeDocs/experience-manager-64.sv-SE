---
title: Bästa tillvägagångssätt för att hantera resurser med AEM
description: Identifiera och följ de bästa metoderna som förbättrar systemets stabilitet och prestanda under belastningen, beroende på AEM Assets driftsättning och funktioner som används för att importera och bearbeta resurser.
contentOwner: AG
feature: Asset Management
role: Architect,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 0%

---


# Bästa tillvägagångssätt för AEM Assets {#best-practices-for-assets}

Adobe Experience Manager (AEM) Assets är en viktig del i att leverera högkvalitativa digitala marknadsföringsupplevelser som bidrar till att uppnå affärsmålen genom att öka innehållets hastighet. Om du arbetar med ett stort antal mediefiler inom AEM Assets eller regelbundet/regelbundet överför flera mediefiler, inklusive videor och dynamiska media, är det viktigt att optimera upplevelsen av den digitala resurshanteringen för att systemet ska bli effektivt.

Beroende på hur du har placerat ut AEM Assets för din organisation och vilka funktioner du använder när det gäller tillgångsintag, återgivningsgenerering och metadataextrahering, kan det vara bra att identifiera och följa vedertagna metoder inom olika områden och förbättra systemets stabilitet och prestanda vid inläsning.

När du har granskat följande handböcker får du de kunskaper och verktyg du behöver för att skapa och hantera ett resurshanteringssystem för företag som passar dina behov.

* [Prestandajusteringsguide ](performance-tuning-guidelines.md)
för resurserInnehåller en uppsättning metodtips som kan följas när som helst i implementeringen, även när du är klar, för att säkerställa att du får ut så mycket som möjligt av systemet.
* [Guide ](assets-sizing-guide.md)
för storleksändring av resurserNär du gör uppskattningar för en resursimplementering är det viktigt att se till att det finns tillräckligt med resurser tillgängliga när det gäller lagring av resurser, processor, minne, IO och nätverkets genomströmning. Om du ändrar storlek på många av dessa objekt måste du förstå hur många resurser som läses in i systemet. Den här guiden innehåller metodtips som hjälper dig att fastställa effektiva mått för beräkning av den infrastruktur och de resurser som krävs för att driftsätta AEM Assets samt ett storleksbedömningsverktyg.
* [Migreringsguide ](assets-migration-guide.md)
för resurserOm du vill migrera resurser från ditt äldre system till AEM Assets finns det flera steg som ska övervägas för att effektivisera migreringsprocessen. Migreringsguiden innehåller metodtips om de åtgärder du utför för att ta AEM resurser in på ett fasvis sätt. Detta inkluderar att lägga till metadata, generera återgivningar och aktivera resurser för publicering av distributionen.
* [Resurser för ](assets-network-considerations.md)
nätverkshänsynNär AEM hanteras är det viktigt att förstå nätverkstopologin för att förstå nätverksprestanda, identifiera kontrollpunkter och beskriva den förväntade användarupplevelsen. Dokumentet Assets Network Considerations behandlar nätverksaspekter när du utformar din AEM Assets-distribution.
* [Handbok ](assets-monitoring-best-practices.md)
för tillgångsövervakningNär AEM har distribuerats bör du övervaka vissa uppgifter och systemet i allmänhet för att säkerställa systemintegriteten och effektiviteten i åtgärderna. Övervakningsguiden innehåller bästa praxis för övervakning av olika aspekter av ditt system.
* (Föråldrat) [Guide för avlastning av resurser](assets-offloading-best-practices.md)
Att hantera stora filer och arbetsflöden i AEM Assets kan ta mycket processorkraft, minne och I/O-resurser i anspråk. Genom att avlasta dessa uppgifter kan du minska kostnaderna för processor, minne och IO-belastning. Handboken för avlastning av resurser innehåller rekommenderade användningsfall och bästa praxis för avlastning av resurser.
* [AEM bästa ](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app-best-practices.html)
praxis för datorprogramAEM-datorprogrammet länkar din DAM-lösning (Digital Asset Management) till skrivbordet så att du kan öppna de filer som finns i det AEM webbgränssnittet direkt på skrivbordet. AEM lättanvända arbetsflöde aktiveras med hjälp av nätverksdelningsteknik från operativsystemen. I den här guiden förklaras de viktigaste funktionerna och den rekommenderade användningen av AEM datorprogram.
* [Bästa ](aem-cc-integration-best-practices.md)
praxis för integrering av AEM och Creative CloudDu kan integrera din AEM med Creative Cloud på flera sätt. Om du följer några metodtips för att effektivisera arbetsflödena för integrering och överföring av resurser blir det effektivare. Denna guide innehåller metodtips om hur man integrerar AEM Assets med Adobe Creative Cloud.
* (Föråldrat) [AEM till Creative Cloud-mappen där metodtips för att dela med sig av ](aem-cc-folder-sharing-best-practices.md)
Du kan konfigurera AEM så att användare i DAM kan dela mappar med användare i Creative Cloud (CC) så att de är tillgängliga som delade mappar i tjänsten Creative Cloud Assets. Funktionen kan användas för utbyte av filer mellan kreativa team och DAM-användare. I den här guiden beskrivs de bästa sätten att utnyttja funktionen för delning av AEM till Creative Cloud-mappar.
