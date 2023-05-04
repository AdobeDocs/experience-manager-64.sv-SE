---
title: Importera och exportera konfigurationsfilen
seo-title: Importing and exporting the configuration file
description: Lär dig hur du importerar och exporterar konfigurationsfilen för att redigera serverinställningar eller konfigurera en annan AEM för formulär.
seo-description: Learn how to import and export the configuration file in order to edit server preferences or configure another AEM forms product instance.
uuid: 32e8a709-2d7c-4740-9533-d53aa751bc58
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_user_management
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: c1636537-f7dc-48d8-a3f0-9052bcd28b62
exl-id: dbad776a-60fd-4fcc-ba2a-a2f379f5462c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---

# Importera och exportera konfigurationsfilen {#importing-and-exporting-the-configuration-file}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Använd sidan Manuell konfiguration för att hämta en kopia av konfigurationsinställningarna i XML-format. Inställningarna i den här filen styr alla serverinställningar. Du kan sedan redigera filen och överföra den tillbaka till servern. Du kan också använda filen för att konfigurera en annan instans AEM formulär.

För att undvika säkerhetsrisker inkluderas inte det binda lösenordsvärdet för katalogservern i en exporterad konfigurationsfil. Uppdatera lösenordet i XML-filen innan du importerar filen till ett nytt system.

>[!NOTE]
>
>Om du importerar konfigurationsfilen konfigureras AEM formulär baserat på informationen i filen. Det är bara systemadministratörer eller konsulter som känner till AEM och XML som kan ändra konfigurationsfilen. De kan behöva redigera konfigurationsfilen, till exempel för att konfigurera om en skadad inställning.

**Exportera konfigurationsinformationen**

1. I administrationskonsolen klickar du på Inställningar > Användarhantering > Konfiguration > Importera och exportera konfigurationsfiler.
1. Klicka på Exportera. Om du använder Microsoft Internet Explorer uppmanas du att ange var filen ska sparas. Om du använder Firefox sparas filen på skrivbordet.

**Importera konfigurationsinformation**

1. I administrationskonsolen klickar du på Inställningar > Användarhantering > Konfiguration > Importera och exportera konfigurationsfiler.
1. Klicka på Bläddra för att hitta konfigurationsfilen, klicka på Importera och sedan på OK.
