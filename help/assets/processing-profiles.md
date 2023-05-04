---
title: Profiler för bearbetning av metadata, bilder och video
description: En profil med en uppsättning regler runt alternativen som ska tillämpas på resurser som överförs till en mapp. Ange vilken metadataprofil och videokodningsprofil som ska användas för de videoresurser som du överför. För bildresurser kan du även ange vilken bildprofil som ska användas för bildresurser så att de beskärs på rätt sätt.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
feature: Workflow,Asset Management,Renditions
role: User,Admin
exl-id: 78d76b4f-a46c-4ffc-b772-ed925eb8e34c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1358'
ht-degree: 2%

---

# Om profiler för att bearbeta metadata, bilder och videoklipp {#profiles-for-processing-metadata-images-and-videos}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

En profil är ett recept på vilka alternativ som ska användas för resurser som överförs till en mapp. Du kan till exempel ange vilken metadataprofil och videokodningsprofil som ska användas för videoresurser som du överför. Eller vilken bildprofil som ska användas för bildresurser så att de beskärs ordentligt.

Dessa regler kan omfatta tillägg av metadata, smart beskärning av bilder eller etablering av videokodningsprofiler. I AEM kan du skapa tre typer av profiler som beskrivs närmare på följande länkar:

* [Metadataprofiler](metadata-profiles.md)
* [Bildprofiler](image-profiles.md)
* [Videoprofiler](video-profiles.md)

Du måste ha administratörsbehörighet för att skapa, redigera och ta bort metadata-, bild- eller videoprofiler.

När du har skapat metadata-, bild- eller videoprofilen tilldelar du den till en eller flera mappar som du använder som mål för nyligen överförda resurser.

Ett viktigt koncept för användning av profiler i [!DNL Experience Manager] Resurser är att de tilldelas mappar. I en profil finns inställningar i form av metadataprofiler, tillsammans med videoprofiler eller bildprofiler. De här inställningarna bearbetar innehållet i en mapp tillsammans med någon av dess undermappar. Därför har hur du namnger filer och mappar, hur du ordnar undermappar och hur du hanterar filerna i dessa mappar stor betydelse för hur resurserna bearbetas av en profil. Genom att använda konsekventa och lämpliga namngivningsstrategier för filer och mappar tillsammans med god metadatapraxis kan du få ut det mesta av din digitala resurssamling och se till att rätt filer bearbetas med rätt profil. Ett exempel finns i [ordna resurser med hjälp av mappar](organize-assets.md#organize-using-folders).

>[!NOTE]
>
>Resurser som du flyttar från en mapp till en annan bearbetas inte om. Anta till exempel att du har Mapp 1 som har tilldelats profilen A och Mapp 2 som har profilen B tilldelad. Om du flyttar resurser från Mapp 1 till Mapp 2 behåller de flyttade resurserna sin ursprungliga bearbetning från Mapp 1.
>
>Detsamma gäller även när du flyttar resurser mellan två mappar som har samma profil tilldelad.

## Bearbeta resurser i en mapp {#reprocessing-assets}

>[!NOTE]
>
>Gäller för *Dynamic Media - Scene7-läge* endast i [!DNL Experience Manager] 6.4.7.0 eller senare.

Du kan bearbeta resurser i en mapp som redan har en befintlig bearbetningsprofil som du senare ändrade.

Anta att du har skapat en bildprofil och tilldelat den till en mapp. Bildobjekt som du överförde till mappen fick automatiskt bildprofilen tillämpad på resurserna. Men senare bestämmer du dig för att lägga till en ny smart beskärningsproportion i profilen. I stället för att nu ha markerat och laddat upp resurserna till mappen igen kör du bara *Scene7: Bearbeta resurser igen* arbetsflöde.

Du kan köra arbetsflödet för ombearbetning på en resurs som bearbetningen misslyckades för första gången. Även om du inte har redigerat en bearbetningsprofil eller använt en bearbetningsprofil kan du ändå köra arbetsflödet för ombearbetning på en mapp med resurser när som helst.

Du kan också justera batchstorleken för arbetsflödet för ombearbetning från standardvärdet 50 resurser upp till 1 000 resurser. När du kör _Scene7: Bearbeta resurser igen_ arbetsflödet i en mapp grupperas resurserna i grupper och skickas sedan till Dynamic Media-servern för bearbetning. Efter bearbetning uppdateras metadata för varje resurs i hela gruppuppsättningen AEM. Om batchstorleken är mycket stor kan bearbetningen fördröjas. Om gruppstorleken är för liten kan det orsaka för många rundresor till Dynamic Media-servern.

Se [Justera batchstorleken för arbetsflödet för ombearbetning](#adjusting-load).

>[!NOTE]
>
>Om du utför en massmigrering av resurser från Dynamic Media Classic till AEM måste du aktivera migreringsreplikeringsagenten på Dynamic Media-servern. När migreringen är klar kontrollerar du att agenten är inaktiverad. Migreringens publiceringsagent måste inaktiveras på Dynamic Media-servern så att arbetsflödet för ombearbetning fungerar som förväntat.

<!-- Batch size is the number of assets that are amalgamated into a single IPS (Dynamic Media’s Image Production System) job. When you run the Scene7: Reprocess Assets workflow, the job is triggered on IPS. The number of IPS jobs that are triggered is based on the total number of assets in the folder, divided by the batch size. For example, suppose you had a folder with 150 assets and a batch size of 50. In this case, three IPS jobs are triggered. The assets are updated when the entire batch size (50 in our example) is processed in IPS. The job then moves onto the next IPS job and so on until complete. If you increase the batch size, you may notice a longer delay with assets getting updated. -->

**Så här bearbetar du resurser i en mapp**:

1. I AEM navigerar du från sidan Resurser till en mapp med resurser som har en bearbetningsprofil tilldelad och för vilken du vill tillämpa **Scene7: Bearbeta resurs igen** arbetsflöde,

   Mappar som redan har tilldelats en bearbetningsprofil visas genom att profilens namn visas direkt under mappnamnet i kortvyn.

1. Välj en mapp.

   * Arbetsflödet hanterar alla filer i den valda mappen rekursivt.
   * Om det finns en eller flera undermappar med resurser i den markerade huvudmappen bearbetas alla resurser i mapphierarkin igen.
   * Som en god vana bör du undvika att köra det här arbetsflödet på en mapphierarki som har fler än 1 000 resurser.

1. Klicka på **[!UICONTROL Timeline]** i listrutan nära sidans övre vänstra hörn.
1. I närheten av det nedre vänstra hörnet av sidan klickar du på ikonen för kundvagnen ( **^** ) .

   ![Bearbeta resursarbetsflöde 1](/help/assets/assets/reprocess-assets1.png)

1. Klicka på **[!UICONTROL Start Workflow]**.
1. Från **[!UICONTROL Start Workflow]** nedrullningsbar lista, välja **[!UICONTROL Scene7: Reprocess Assets]**.
1. (Valfritt) I dialogrutan **Ange arbetsflödets titel** anger du ett namn för arbetsflödet. Du kan använda namnet för att referera till arbetsflödesinstansen, om det behövs.

   ![Bearbeta resurser 2](/help/assets/assets/reprocess-assets2.png)

1. Klicka **[!UICONTROL Start]** och sedan klicka **[!UICONTROL Confirm]**.

   Om du vill övervaka arbetsflödet eller kontrollera förloppet går du till [!DNL Experience Manager] huvudkonsolsidan, klicka på **[!UICONTROL Tools > Workflow]**. Välj ett arbetsflöde på sidan Arbetsflödesinstanser. Klicka på **[!UICONTROL Open History]**. Du kan också avsluta, göra uppehåll i eller byta namn på ett valt arbetsflöde från samma sida för arbetsflödesinstanser.

### Justera batchstorleken för arbetsflödet för ombearbetning {#adjusting-load}

(Valfritt) Standardbatchstorleken i ombearbetningsarbetsflödet är 50 resurser per jobb. Den optimala batchstorleken styrs av den genomsnittliga tillgångsstorleken och de Mime-typer av resurser som ombearbetningen körs på. Ett högre värde innebär att du kommer att ha många filer i ett och samma ombearbetningsjobb. Bearbetningsbanderollen förblir alltså aktiverad [!DNL Experience Manager] resurser under en längre tid. Om den genomsnittliga filstorleken är liten-1 MB eller mindre-Adobe rekommenderar du att du ökar värdet till flera hundra, men aldrig mer än 1 000. Om den genomsnittliga filstorleken är stor-hundratals megabyte-Adobe rekommenderar du att du minskar gruppstorleken upp till 10.

**Om du vill justera batchstorleken för arbetsflödet för ombearbetning**

1. I Experience Manager trycker du på **[!UICONTROL Adobe Experience Manager]** för att komma åt den globala navigeringskonsolen och sedan på **[!UICONTROL Tools]** (hammarikon) > **[!UICONTROL Workflow > Models]**.
1. På sidan Arbetsflödesmodeller i kortvyn eller listvyn väljer du **[!UICONTROL Scene7: Reprocess Assets]**.

   ![Workflow Models page with Scene7: Arbetsflödet för att bearbeta resurser som valts i kortvyn](/help/assets/assets-dm/reprocess-assets7.png)

1. Klicka på i verktygsfältet **[!UICONTROL Edit]**. En ny flik i webbläsaren öppnar Scene7: Sidan med arbetsflödesmodellen Återbearbeta resurser.
1. På Scene7: Återbearbeta arbetsflödessidan Resurser, i det övre högra hörnet, tryck **[!UICONTROL Edit]** för att låsa upp arbetsflödet.
1. Öppna verktygsfältet genom att välja Scene7 Batch Upload-komponenten i arbetsflödet och tryck sedan på **[!UICONTROL Configure]** i verktygsfältet.

   ![Komponenten Scene7 Batch Upload](/help/assets/assets-dm/reprocess-assets8.png)

1. På **[!UICONTROL Batch Upload to Scene7–Step Properties]** anger du följande:
   * I **[!UICONTROL Title]** och **[!UICONTROL Description]** textfält, ange en ny titel och beskrivning för jobbet, om så önskas.
   * Välj **[!UICONTROL Handler Advance]** om hanteraren går vidare till nästa steg.
   * I **[!UICONTROL Timeout]** anger du timeout för extern process (sekunder).
   * I **[!UICONTROL Period]** anger du ett avsökningsintervall (sekunder) som ska testas för att den externa processen ska slutföras.
   * I **[!UICONTROL Batch field]** anger du det maximala antalet resurser (50-1000) som ska bearbetas i ett batchbearbetningsjobb för en Dynamic Media-server.
   * Välj **[!UICONTROL Advance on timeout]** om du vill fortsätta när tidsgränsen nås. Avmarkera alternativet om du vill fortsätta till inkorgen när tidsgränsen nås.

   ![Egenskaper, dialogruta](/help/assets/assets-dm/reprocess-assets3.png)

1. I det övre högra hörnet av **[!UICONTROL Batch Upload to Scene7–Step Properties]** dialogruta, tryck **[!UICONTROL Done]**.

1. I det övre högra hörnet av Scene7: Återbearbeta arbetsflödesmodellsidan Resurser, tryck **[!UICONTROL Sync]**. När du ser **[!UICONTROL Synced]**, är arbetsflödets körningsmodell synkroniserad och klar att bearbeta om resurser i en mapp.

   ![Synkronisera arbetsflödesmodellen](/help/assets/assets-dm/reprocess-assets1.png)

1. Stäng webbläsarfliken som visar Scene7: Arbetsflödesmodellen Återbearbeta resurser.

<!-- 1. Return to the browser tab that has the open Workflow Models page, then press **Esc** to exit the selection.
1. In the upper-left corner of the page, tap **[!UICONTROL Adobe Experience Manager]** to access the global navigation console, then tap the **[!UICONTROL Tools]** (hammer) icon > **[!UICONTROL General > CRXDE Lite]**.
1. In the folder tree on the left side of the CRXDE Lite page, navigate to the following location:

   `/conf/global/settings/workflow/models/scene7_reprocess_assets/jcr:content/flow/reprocess/metaData`

   ![CRXDE Lite](/help/assets/assets/workflow-models9.png)

1. On the right side of the CRXDE Lite page, in the lower portion, enter the following name, type, and value in its respective field:
    * **[!UICONTROL Name]**: `reprocess-batch-size`
    * **[!UICONTROL Type]**: `Long`
    * **[!UICONTROL Value]**: enter a default value (50-1000) for the batch size
1. In the lower-right corner, tap **[!UICONTROL Add]**. The new property appears as the following:

    ![Saving the new property](/help/assets/assets/workflow-models10.png)

1. On the menu bar of the CRXDE Lite page, tap **[!UICONTROL Save All]**.
1. In the upper-left corner of the page, tap **[!UICONTROL CRXDE Lite]** to return to the main [!DNL Experience Manager] console
1. Repeat steps 1-7 to re-synchronize the new batch size to the Scene7: Reprocess Assets workflow model. -->
