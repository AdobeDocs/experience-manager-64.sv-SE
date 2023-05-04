---
title: Integrera AEM med Microsoft Office SharePoint Server
seo-title: Integrating AEM forms workspace with Microsoft Office SharePoint Server
description: Du kan integrera AEM arbetsyta med Microsoft Office SharePoint Server.
seo-description: You can integrate AEM forms workspace with Microsoft Office SharePoint Server.
uuid: d43396d4-117f-47ea-91e4-10ee96107bc8
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: 1bada670-3e0e-40f4-b9be-8b090df910be
exl-id: 43149456-8ff8-4ce1-9c51-1d950f60ff5d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 0%

---

# Integrera AEM med Microsoft Office SharePoint Server {#integrating-aem-forms-workspace-with-microsoft-office-sharepoint-server}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

**- Krav**

**Nödvändig kunskap**
Innan du kan lägga till AEM Forms Workspace på SharePoint Server måste du ha tillgång till SharePoint Server med rätt behörighet och du måste känna till URL:en för att få tillgång till Workspace. Stegen nedan förutsätter att du har kunskap om SharePoint Server. Mer information om webbdelar i SharePoint Server finns i Webbdelar i Windows SharePoint Services.

**Användarnivå**
Början

Du kan använda AEM Forms Workspace som en webbdel i Microsoft Office SharePoint Server (till exempel Microsoft Office SharePoint Server 2007). Användare har tillgång till AEM Forms Workspace genom att ansluta till din SharePoint Server via en webbläsare för att ge en enhetlig upplevelse. I den här artikeln får du lära dig de grundläggande stegen för att visa AEM Forms Workspace som en webbdel i Microsoft Office SharePoint Server. Du kan utföra stegen som beskrivs i den här artikeln för att ge en enhetlig upplevelse så att användare som ansluter till din SharePoint-server kan komma åt AEM Forms Workspace från samma port.

>[!NOTE]
>
>Stegen i den här artikeln är specifika för Microsoft SharePoint Server 2007. Du kan också konfigurera HTML Workspace med andra versioner av Microsoft SharePoint som stöds.

## Integrera AEM Forms Workspace med Microsoft Office SharePoint Server 2007 {#integrate-aem-forms-workspace-with-microsoft-office-sharepoint-server}

Så här integrerar du AEM Forms Workspace i en webbdel:

1. I en webbläsare navigerar du till SharePoint webbplats, t.ex. https://*[myMOSSserver]:*44299/default.aspx där *[myMOSSserver]* är namnet eller IP-adressen för SharePoint-servern.

   >[!NOTE]
   >
   >44299 är standardportnumret för SharePoint-servern. Portnumret beror på din installation av SharePoint Server.

1. Klicka på uppe till höger på webbsidan **Webbplatsåtgärder** och markera **Redigera sida**.
1. Klicka på **Lägga till en webbdel** -knappen.
1. I dialogrutan Lägg till webbdelar - webbsida, under Övriga, väljer du **Webbdel för sidvisning** och sedan klicka **Lägg till**.
1. I rutan Webbdel för sidvisningsprogrammet klickar du på **redigera** och markera **Ändra delad webbdel**.

   >[!NOTE]
   >
   >Rutan Webbdel för sidvisningsprogrammet visas under **Lägga till en webbdel** som du klickade på i steg 3 enligt bilden nedan (bild 1):

   ![Sidvisningsprogramwebbdelen i Microsoft Office SharePoint-servern.](assets/page-viewer-web-part-box-in-microsoft-office-sharepoint-server.png)

   **Bild:** *The Page Viewer Web Part box in Microsoft Office SharePoint server.*

1. Utför följande åtgärder på sidan för sidvisningsprogrammet:

   1. I rutan Länk skriver du URL:en för AEM Forms Workspace, till exempel https://*[AEM_forms_Server]:*8080/lc/ws där *[AEM_forms_Server]* representerar IP-adressen eller namnet AEM formulärservern.
   1. Klicka **Utseende** och ändra höjd, bredd och titel så att du kan se hela användargränssnittet för arbetsytan. Du kan till exempel ange höjd och bredd till 6 tum respektive 11 tum.
   1. Klicka **Testa länk**. Ett nytt webbläsarfönster visas med arbetsytan.
   1. (Valfritt) Klicka på **Layout** och ändra layouten för arbetsytan i webbdelen.
   1. (Valfritt) Klicka på **Avancerat** och ändra andra inställningar, t.ex. beskrivningen och om arbetsytan kan minimeras eller stängas i webbdelen.

      Klicka **Använd**.

1. Klicka **Avsluta redigeringsläget** och verifiera att du har åtkomst till arbetsytan.

När du är klar med stegen ovan ser din SharePoint-webbplats ut ungefär som på följande bild (bild 2):

![AEM Forms Workspace integrerat med Microsoft Office SharePoint Server](assets/aem-forms-workspace.jpg)

**Bild:** *AEM Forms Workspace integrerat med Microsoft Office SharePoint Server*
