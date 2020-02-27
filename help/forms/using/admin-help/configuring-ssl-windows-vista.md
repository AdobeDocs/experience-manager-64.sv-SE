---
title: Konfigurera SSL i Windows Vista
seo-title: Konfigurera SSL i Windows Vista
description: Lär dig hur du konfigurerar SSL i Windows Vista.
seo-description: Lär dig hur du konfigurerar SSL i Windows Vista.
uuid: 20bfcefb-ec84-4c55-bceb-6af106d883d7
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_ssl
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 667645a0-53d0-4f9b-a0ba-cc7e366a23a1
translation-type: tm+mt
source-git-commit: d04e08e105bba2e6c92d93bcb58839f1b5307bd8

---


# Konfigurera SSL i Windows Vista {#configuring-ssl-on-windows-vista}

Om du vill konfigurera SSL på Windows Vista™ behöver du ett SSL-certifikat med RSA-nycklar för autentisering. Du kan använda Java-nyckelverktyget för att skapa certifikatet.

>[!NOTE]
>
>Windows Vista fungerar inte med DSA-nycklar.

Du kan köra nyckelverktyget med ett enda kommando som innehåller all information som krävs för att skapa certifikatet och nyckelbehållaren.

**Skapa ett SSL-certifikat**

1. I en kommandotolk går du till *[JAVA HOME]*/bin och skriver följande kommando för att skapa certifikatet och nyckelbehållaren:

   `keytool -genkey -keyalg RSA -dname "CN=`*Värdnamn *`, OU=`*Gruppnamn* `, O=`*Företag *`,L=`*Ort****** Namn* `, S=`*Delstat *`, C=`** `" -alias`**`-keypass``*key*`**`-keystore`** Landskod¥&quot;LC Cert&quot;¥*_*password¥keystorename `.keystore`

   >[!NOTE]
   >
   >Ersätt *[JAVA_HOME]med katalogen där JDK är installerat och ersätt texten i kursiv stil med värden som motsvarar din miljö.*

1. Ange `changeit` som lösenord. Det här lösenordet är standard för en Java-installation och systemadministratören kan ha ändrat det.

