---
title: Konfigurera SSL i Windows Vista
seo-title: Configuring SSL on Windows Vista
description: Lär dig hur du konfigurerar SSL i Windows Vista.
seo-description: Learn how to configure SSL on Windows Vista.
uuid: 20bfcefb-ec84-4c55-bceb-6af106d883d7
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_ssl
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 667645a0-53d0-4f9b-a0ba-cc7e366a23a1
exl-id: 8eee2ed2-8263-47f2-b928-214fd9ab5f6e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# Konfigurera SSL i Windows Vista {#configuring-ssl-on-windows-vista}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Om du vill konfigurera SSL på Windows Vista™ behöver du ett SSL-certifikat med RSA-nycklar för autentisering. Du kan använda Java-nyckelverktyget för att skapa certifikatet.

>[!NOTE]
>
>Windows Vista fungerar inte med DSA-nycklar.

Du kan köra nyckelverktyget med ett enda kommando som innehåller all information som krävs för att skapa certifikatet och nyckelbehållaren.

**Skapa ett SSL-certifikat**

1. I en kommandotolk går du till *[JAVA HOME]*/bin och skriv följande kommando för att skapa certifikatet och nyckelbehållaren:

   `keytool -genkey -keyalg RSA -dname "CN=`*Värdnamn* `, OU=`*Gruppnamn* `, O=`*Företag* `,L=`*Ort******Namn* `, S=`*Läge* `, C=`*Landskod* `" -alias`*&quot;LC Cert&quot;* `-keypass` `*key*`*_**lösenord* `-keystore`*keystorename* `.keystore`

   >[!NOTE]
   >
   >Ersätt *[JAVA_HOME] med den katalog där JDK är installerat och ersätt texten i kursiv stil med värden som motsvarar din miljö.*

1. Typ `changeit` som lösenord. Det här lösenordet är standard för en Java-installation och systemadministratören kan ha ändrat det.
