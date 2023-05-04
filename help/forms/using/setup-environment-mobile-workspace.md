---
title: Konfigurera miljö för AEM Forms-program
seo-title: Set up environment for AEM Forms app
description: Maskinvara, programvara och licenser för att bygga och driftsätta AEM Forms-appen.
seo-description: Hardware, software, and licenses to build and deploy the AEM Forms app.
uuid: 0c8f5259-8e9f-45ce-ade4-e14f1a41c0de
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 72c3a451-fa57-4b12-8d25-fc2e6fa98adb
exl-id: 5c60d1a6-a4a2-4131-81e6-e39a5ab07dcf
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---

# Konfigurera miljö för AEM Forms-program {#set-up-environment-for-aem-forms-app}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du behöver följande maskinvara, programvara och licenser för att skapa och distribuera AEM Forms-appen:

## För Windows-enheter {#for-windows-devices}

* Microsoft Windows 8.1 eller Windows 10
* Microsoft Visual Studio 2015
* Microsoft Visual Studio Tools for Apache Cordova

## För iOS-enheter {#for-ios-devices}

* Intel-baserad Apple Mac med Mac OS X 10.9.5 eller senare
* iOS SDK 8.4 eller senare
* Xcode-version: Xcode 6.4 för OS X eller senare
* Medlemskap i iOS Developer Enterprise Program
* Enterprise-certifikat för distribution av interna iOS-appar
* Apple iPad med iOS 8.4 eller senare

## För Android-enheter {#for-android-devices}

* Android Development Toolkit (ADT bundle) som kan hämtas från [https://developer.android.com/sdk/index.html](https://developer.android.com/sdk/index.html)
* Om miljön är konfigurerad på ett MAC-system bör ADT installeras i mappen Program.
* Om ADT är installerat på någon annan plats i MAC, eller om miljön är konfigurerad för ett Windows-system, måste ADT SDK-sökvägen uppdateras i `local.properties` fil som är tillgänglig i `src\android` i den extraherade källarkivet `mobileworkspace-src.zip`. I den här filen pekar du på `sdk.dir` variabel till ADT SDK-plats på skrivbordet.

>[!NOTE]
>
>Adobe-lc-mobileworkspace-src.zip innehåller PhoneGap SDK 5.0. Kontrollera att PhoneGap SDK inte är förinstallerat.
