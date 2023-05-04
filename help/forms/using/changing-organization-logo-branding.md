---
title: Ändra organisationslogotyp för varumärken
seo-title: Changing the organization logo for branding
description: Om du vill märka ut AEM Forms arbetsyta anger du din organisations logotyp genom att anpassa standardlogotypen.
seo-description: To brand AEM Forms workspace provide the logo of your organization by customizing the default logo.
uuid: f0c340ee-2e54-4bb0-9c30-383cc1bbadb8
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 2c651302-f4ef-4211-b897-f5942ed0ffb1
exl-id: 890e98af-0491-4b59-9a9b-6c245db54f0f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# Ändra organisationslogotyp för varumärken {#changing-the-organization-logo-for-branding}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Organisationslogotypen visas i det övre vänstra hörnet på arbetsytan i AEM Forms. Uppdatera logotypen genom att följa [Allmänna steg för anpassning av AEM Forms arbetsyta](/help/forms/using/generic-steps-html-workspace-customization.md#generic-steps-for-html-workspace-customization) och därefter följande steg.

1. Skapa en logotyp och ge filen namnet `NewWorkspace.png`. Placera bildfilen i mappen /apps/ws/images med en WebDAV-klient.

   >[!NOTE]
   >
   >Den rekommenderade storleken på logotypbilden är 218 px × 20 px.

   >[!NOTE]
   >
   >Mer information om WebDAV-åtkomst finns i [https://dev.day.com/docs/en/crx/current/how_to/webdav_access.html](https://docs.adobe.com/docs/en/crx/current/how_to/webdav_access.html).

1. Referera till den nya logotypbilden i formatmallen på /apps/ws/css/newStyle.css genom att lägga till följande format.

   ```css
   #logo {
   
          background: url(../images/NewWorkspace.png) no-repeat 14px 11px; 
         }
   ```
