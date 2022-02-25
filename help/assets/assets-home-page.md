---
title: '"[!DNL Experience Manager Assets] Home Page Experience"'
description: Anpassa startsidan för Assets för en rik välkomstskärm, inklusive en ögonblicksbild av nyligen gjorda aktiviteter kring resurser.
contentOwner: AG
feature: Developer Tools,Asset Management
role: Admin,User
exl-id: f47c6da7-aa21-4f49-9c66-2a8091e19561
source-git-commit: d9cfb5376210234b3b05877509c273c52d9cecf3
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 1%

---

# [!DNL Adobe Experience Manager Assets] Home Page Experience {#aem-assets-home-page-experience}

Anpassa [!DNL Experience Manager Assets] Startsida för en rik välkomstskärm, inklusive en ögonblicksbild av nyligen gjorda aktiviteter kring resurser.

The [!DNL Adobe Experience Manager Assets] Hemsidan innehåller en omfattande och personlig välkomstskärm, som innehåller en ögonblicksbild av de senaste aktiviteterna, till exempel resurser som nyligen visats eller överförts.

Hemsidan för Resurser är inaktiverad som standard. Så här aktiverar du den:

1. För åtkomst [!DNL Experience Manager] Configuration Manager, klicka på **[!UICONTROL Tools > Operation > Web Console]**.
1. Öppna **Dagens CQ DAM-inspelning** service.
1. Välj **[!UICONTROL Enable this service]** för att aktivera aktivitetsinspelning.

   ![chlimage_1-250](assets/chlimage_1-250.png)

1. Från **Händelsetyper** markerar du de händelser som ska spelas in och sparar ändringarna.

   >[!CAUTION]
   >
   >Om du aktiverar alternativen Visa, Visa projekt och Samlingar, ökar antalet inspelade händelser avsevärt.

1. Öppna **[!UICONTROL DAM Asset Home Page Feature Flag]** tjänst från Configuration Manager `https://[AEM_server]:[port]/system/console/configMgr`.
1. Välj **[!UICONTROL isEnabled.name]** för att aktivera funktionen Assets Home page. Spara ändringarna.

   ![chlimage_1-251](assets/chlimage_1-251.png)

1. Öppna **[!UICONTROL User Preferences]** och väljer **[!UICONTROL Enable Assets Home Page]**. Spara ändringarna.

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

**Aktivitet**: Under det här avsnittet **Min aktivitet** widgeten visar de senaste aktiviteterna som den inloggade användaren har utfört med resurser (inklusive resurser utan återgivningar), till exempel överföringar av resurser, hämtningar, skapande av resurser, redigeringar, kommentarer, anteckningar och delningar.

**Senaste**: The **Senast visade** widgeten under det här avsnittet visar nyligen använda entiteter av den inloggade användaren, inklusive mappar, samlingar och projekt.

**Upptäck**: The **Nytt** visas resurser och återgivningar som nyligen har överförts till [!DNL Assets] -instans.

Aktivera alternativet **Tjänsten DAM Event Rensa** från Configuration Manager. När du har aktiverat den här tjänsten tas aktiviteter av den inloggade användaren som överskrider ett angivet nummer bort av systemet.

Välkomstskärmen innehåller enkla navigeringshjälpmedel, t.ex. ikoner i verktygsfältet för att komma åt mappar, samlingar och kataloger.

>[!NOTE]
>
>Om du aktiverar tjänsten Dag CQ DAM Event Recorder och DAM Event Rensa ökas skrivåtgärderna till JCR och sökindexering, vilket ökar inläsningen på [!DNL Experience Manager] server. Ytterligare belastning på [!DNL Experience Manager] kan påverka serverns prestanda.

>[!CAUTION]
>
>Att hämta in, filtrera och rensa användaraktiviteter som krävs för Assets hemsida medför höga prestanda. Därför bör administratörer konfigurera hemsidan effektivt för målanvändare.
>
>Adobe rekommenderar att administratörer och användare som utför gruppåtgärder undviker att använda funktionen Startsida för resurser för att förhindra att användaraktiviteter ökar. Dessutom kan administratörer utesluta inspelningsaktiviteter för specifika användare genom att konfigurera **Dagens CQ DAM-inspelning** från Configuration Manager.
>
>Om du använder funktionen rekommenderar Adobe att du schemalägger tömningsfrekvensen baserat på serverinläsningen.
