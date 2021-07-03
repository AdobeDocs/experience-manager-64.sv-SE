---
title: Bästa metoder för effektiv översättning av resurser
description: Bästa tillvägagångssätt för effektiv hantering av resurser för att synkronisera olika översatta versioner och effektivisera översättningsarbetsflöden.
contentOwner: AG
feature: Översättning
role: User,Admin
exl-id: 15162b80-ddef-4ec0-9db6-36695c93ebb1
source-git-commit: 5d96c09ef764b02e08dcdf480da1ee18f4d9a30c
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---

# Bästa tillvägagångssätt för att översätta resurser effektivt {#best-practices-for-translating-assets-efficiently}

Adobe Experience Manager (AEM) Assets stöder flerspråkiga arbetsflöden för att översätta binära filer, metadata och taggar för digitala resurser till flera språkområden och för att hantera översatta resurser. Mer information finns i [Flerspråkiga resurser](multilingual-assets.md).

För effektiv hantering av resurser, för att säkerställa att olika översatta versioner förblir synkroniserade, skapar du [språkkopior](preparing-assets-for-translation.md) av resurserna innan du kör översättningsarbetsflöden.

En språkkopia av en resurs eller en grupp av resurser är ett språkjämlikt (eller en version av resursen/resurserna på ett modersmål) med en liknande innehållshierarki.

Varje språkkopia är en oberoende resurs. Därför kan en översättning av resurser till flera språkområden drastiskt öka storleken på CRX-databasen. Om du till exempel översätter resurser med en kombinerad storlek på 10 GB till två språk kan databasstorleken öka med ungefär 20 GB (10 GB för varje språk).

Resurbinärfiler upptar mycket större lagringsutrymme jämfört med metadata och taggar. Om översättning av metadata och taggar bara har ditt syfte utelämnar du därför att översätta binärfilerna. Du kan behålla den ursprungliga kopian av binärfilerna i databasen för association med metadata och taggar översatta till olika språkområden. Genom att behålla en enda kopia av binärfiler, i stället för flera översatta versioner, minimeras påverkan på databasstorleken.

File Data Store och Amazon S3 Data Store tillhandahåller en lagringsinfrastruktur som passar bäst för dessa scenarier. De här lagringsdatabaserna lagrar en enda kopia av resursbinärfiler (inklusive återgivningar) som kan delas av metadata och taggar på flera språkområden. Databasstorleken påverkas därför inte om du skapar kopior av resurser och översätter metadata och taggar.

Du kan också göra några konfigurationsändringar i ett par arbetsflöden och översättningsintegrationsramverket för att ytterligare effektivisera processen.

1. Gör något av följande:

   * [Konfigurera arkiv för fildata](/help/sites-deploying/data-store-config.md)
   * [Konfigurera Amazon S3-datalagret](/help/sites-deploying/data-store-config.md)

1. Inaktivera arbetsflödet [DAM MetaData Writeback](/help/sites-administering/workflow-offloader.md#disable-offloading)

   Som namnet antyder skriver arbetsflödet *DAM Metadata Writeback* om metadata till den binära filen. Eftersom metadata ändras efter översättning, genereras en annan binär fil för en språkkopia när du skriver tillbaka den till den binära filen.

   >[!NOTE]
   >
   >Om du inaktiverar arbetsflödet *DAM MetaData Writeback* inaktiveras skrivningen XMP metadata för objektbinärfiler. Därför sparas inte längre framtida metadataändringar i resurserna. Utvärdera konsekvenserna innan du inaktiverar arbetsflödet.

1. Aktivera arbetsflödet *Ange senaste ändringsdatum*.

   Arbetsflödet *DAM MetaData Writeback* konfigurerar det senaste ändringsdatumet för en resurs. Eftersom du inaktiverar det här arbetsflödet i steg 2 kan AEM Assets inte längre hålla det senaste ändrade datumet för mediefiler uppdaterat. Aktivera därför arbetsflödet *Ange senaste ändringsdatum* för att säkerställa att de senaste ändrade datumen för resurser är uppdaterade. Resurser med inaktuella senast ändrade datum kan orsaka fel.

1. [Konfigurera ](/help/sites-administering/tc-tic.md) ramverket för översättningsintegrering så att översättningen av resursbinärfiler avbryts. Avmarkera alternativet &quot;Översätt resurser&quot; på fliken Resurser för att stoppa översättningen av resurbinärfiler.
1. Översätt metadata/taggar för resurser med [arbetsflöden för flerspråkiga resurser](multilingual-assets.md).
