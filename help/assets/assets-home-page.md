---
title: '[!DNL Experience Manager Assets] Home Page Experience'
description: Anpassa startsidan för Assets för en rik välkomstskärm, inklusive en ögonblicksbild av nyligen gjorda aktiviteter kring resurser.
contentOwner: AG
feature: Developer Tools,Asset Management
role: Admin,User
exl-id: f47c6da7-aa21-4f49-9c66-2a8091e19561
source-git-commit: cc6de21180c9fff74f7d64067db82f0c11ac9333
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 1%

---

# [!DNL Adobe Experience Manager Assets] Home Page Experience {#aem-assets-home-page-experience}

Anpassa startsidan för [!DNL Experience Manager Assets] för en rik välkomstskärm, inklusive en ögonblicksbild av nyligen gjorda aktiviteter kring resurser.

På startsidan för [!DNL Adobe Experience Manager Assets] finns en omfattande och personlig välkomstskärm, som innehåller en ögonblicksbild av de senaste aktiviteterna, till exempel resurser som nyligen har visats eller överförts.

Hemsidan för Resurser är inaktiverad som standard. Så här aktiverar du den:

1. Klicka på **[!UICONTROL Tools > Operation > Web Console]** om du vill komma åt Configuration Manager.[!DNL Experience Manager]
1. Öppna tjänsten **Day CQ DAM Event Recorder**.
1. Välj **[!UICONTROL Enable this service]** för att aktivera aktivitetsinspelning.

   ![chlimage_1-250](assets/chlimage_1-250.png)

1. I listan **Händelsetyper** väljer du vilka händelser som ska registreras och sparar ändringarna.

   >[!CAUTION]
   >
   >Om du aktiverar alternativen Visa, Visa projekt och Samlingar, ökar antalet inspelade händelser avsevärt.

1. Öppna tjänsten **[!UICONTROL DAM Asset Home Page Feature Flag]** från Configuration Manager `https://[AEM_server]:[port]/system/console/configMgr`.
1. Välj alternativet **[!UICONTROL isEnabled.name]** för att aktivera funktionen Assets Home page. Spara ändringarna.

   ![chlimage_1-251](assets/chlimage_1-251.png)

1. Öppna dialogrutan **[!UICONTROL User Preferences]** och välj **[!UICONTROL Enable Assets Home Page]**. Spara ändringarna.

   ![user_preferences](assets/user_preferences.png)

När du har aktiverat startsidan för Resurser navigerar du till användargränssnittet för Resurser från navigeringssidan.

![home_page](assets/home_page.png)

Tryck/klicka på **[!UICONTROL Click here to configure your experience link]** för att lägga till ditt användarnamn, din bakgrundsbild och din profilbild.

Hemsidan för Assets innehåller följande avsnitt:

* Välkomstavsnitt
* Widget Section

**Välkomstavsnitt**

Om din profil finns visas ett välkomstmeddelande adresserat till dig i välkomstavsnittet. Dessutom visas din profilbild och en välkomstbild (om den redan är konfigurerad).

Om din profil är ofullständig visas ett allmänt välkomstmeddelande och en platshållare för din profilbild i välkomstavsnittet.

**Widget Section**

Det här avsnittet visas under välkomstavsnittet och visar widgetar som inte finns i kartongen under följande avsnitt:

* Aktivitet
* Senaste
* Upptäck

**Aktivitet**: I det här avsnittet visar  **widgeten** Min aktivitet de senaste aktiviteterna som utförts av den inloggade användaren med resurser (inklusive resurser utan återgivningar), till exempel överföringar, hämtningar, skapande av resurser, redigeringar, kommentarer, anteckningar och delningar.

**Senaste**: Widgeten  **Senast** visad i det här avsnittet visar nyligen använda enheter som den inloggade användaren har använt, inklusive mappar, samlingar och projekt.

**Upptäck**: I  **** Newwidgeten under det här avsnittet visas de resurser och återgivningar som nyligen har överförts till  [!DNL Assets] instansen.

Aktivera tjänsten **DAM Event Renge** från Configuration Manager om du vill aktivera rensning av användaraktivitetsdata. När du har aktiverat den här tjänsten tas aktiviteter av den inloggade användaren som överskrider ett angivet nummer bort av systemet.

Välkomstskärmen innehåller enkla navigeringshjälpmedel, t.ex. ikoner i verktygsfältet för att komma åt mappar, samlingar och kataloger.

>[!NOTE]
>
>Om du aktiverar tjänsterna Day CQ DAM Event Recorder och DAM Event Rensa ökas skrivåtgärderna till JCR och sökindexering, vilket avsevärt ökar inläsningen på [!DNL Experience Manager]-servern. Ytterligare belastning på [!DNL Experience Manager]-servern kan påverka dess prestanda.

>[!CAUTION]
>
>Att hämta in, filtrera och rensa användaraktiviteter som krävs för Assets hemsida medför höga prestanda. Därför bör administratörer konfigurera hemsidan effektivt för målanvändare.
>
>Adobe rekommenderar att administratörer och användare som utför gruppåtgärder undviker att använda funktionen Startsida för resurser för att förhindra att användaraktiviteter ökar. Dessutom kan administratörer exkludera inspelningsaktiviteter för specifika användare genom att konfigurera **Day CQ DAM Event Recorder** från Configuration Manager.
>
>Om du använder funktionen rekommenderar Adobe att du schemalägger tömningsfrekvensen baserat på serverinläsningen.
