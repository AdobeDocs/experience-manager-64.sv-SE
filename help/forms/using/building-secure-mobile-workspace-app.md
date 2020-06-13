---
title: Bygga en säker AEM Forms-app för iOS
seo-title: Bygga en säker AEM Forms-app för iOS
description: Steg för att skapa en säker AEM Forms-app.
seo-description: Steg för att skapa en säker AEM Forms-app.
uuid: 6c4b160f-4d0c-4976-9609-9196795b6c8e
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 90cd8ba5-4f47-4074-bc54-6a7bb8afe256
translation-type: tm+mt
source-git-commit: 5e764edb3d8ed98542c50b80cac40776c886ccf5
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---


# Bygga en säker AEM Forms-app för iOS {#building-a-secure-aem-forms-app-for-ios}

Du måste arkivera Xcode-projektet för AEM Forms-appen för att skapa installationsprogrammet (en IPA-fil) och en egenskapslista (en .plist-fil). Egenskapslistfilen innehåller konfigurationsinformation för det värdbaserade interna programmet, till exempel namnet och appens värdplats. Mer information om egenskapslistfiler finns i [Om egenskapslistefiler](https://developer.apple.com/library/ios/#documentation/general/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html).

1. Logga in på följande webbplats:

   [https://developer.apple.com/account/ios/identifier/bundle](https://developer.apple.com/account/ios/identifier/bundle)

1. Skapa ett program-ID. Mer information om hur du skapar ett program-ID finns i [Skapa och konfigurera program-ID:n](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/MaintainingProfiles/MaintainingProfiles.html).
1. Om du vill konfigurera källidentifieraren för iOS-programmet för din app klickar du på **[!UICONTROL Configure App ID]**.
1. Längst ned på webbsidan väljer du **[!UICONTROL Enable for Data Protection]**. Ange alternativ för dataskydd.

   Klicka på **[!UICONTROL Done]**.

1. Navigera till Provisioning->Distribution och skapa en ny profil med det program-ID som konfigurerats i steg 3.
1. Hämta och lägg till provisioneringsprofilen i Xcode och iPad.
1. Logga in på en Mac-dator som har Xcode och iOS SDK installerat och konfigurerat.
1. Öppna `AEM Forms.xcodeproj` projektet i Xcode.
1. Klicka **[!UICONTROL AEM Forms]** under **[!UICONTROL TARGETS]**, markera **[!UICONTROL AEM Forms]**. Välj **[!UICONTROL Build Settings]** fliken, leta upp **[!UICONTROL Code Signing Entitlement]** avsnittet och välj **[!UICONTROL LC Enterprise]** alternativet i listrutan Tillstånd.
1. Leta reda på och öppna `LC Enterprise.entitlements` filen i Xcode för redigering. **Lägg till samma nyckel/värde-par som i provisioneringsprofilen under **XCode-berättigandena.
1. Klicka på **[!UICONTROL Build Settings]** fliken **[!UICONTROL All]** och sedan på **[!UICONTROL Combined]**.
1. From the **[!UICONTROL Settings]** list, expand **[!UICONTROL Code Signing]**.
1. Välj **[!UICONTROL Code Signing Identity]** lämplig signatur. Se till att samma signatur är markerad för **[!UICONTROL Debug]**, **[!UICONTROL Release]** och **[!UICONTROL Any iOS SDK]**.
1. Under **[!UICONTROL PROJECT]** väljer du **[!UICONTROL AEM Forms]** och ser till att rätt signatur är vald för **[!UICONTROL Code Signing Identity]**, **[!UICONTROL Debug]** och **[!UICONTROL Release]** **[!UICONTROL Any iOS SDK]**.
1. Bygg och distribuera appen AEM Forms. Detaljerade anvisningar om hur du skapar och distribuerar appen AEM Forms finns i [Skapa installationsprogrammet för appen](setup-xcode-project-build-installer.md#build-the-installer-for-the-mobile-workspace-app)AEM Forms.
