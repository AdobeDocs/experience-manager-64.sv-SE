---
title: AEM Assets Home Page Experience
description: Anpassa startsidan för AEM Assets för en rik välkomstskärm, inklusive en ögonblicksbild av nyligen gjorda aktiviteter kring resurser.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1

---


# AEM Assets Home Page Experience {#aem-assets-home-page-experience}

Anpassa startsidan för AEM Assets för en rik välkomstskärm, inklusive en ögonblicksbild av nyligen gjorda aktiviteter kring resurser.

Adobe Experience Manager Assets Home page (AEM) Assets Home page (startsidan för Adobe Experience Manager Assets) ger en rik och personlig välkomstskärm, som innehåller en ögonblicksbild av nyligen använda aktiviteter, till exempel resurser som nyligen har visats eller överförts.

Hemsidan för Resurser är inaktiverad som standard. Så här aktiverar du den:

1. Du öppnar AEM Configuration Manager genom att klicka på **[!UICONTROL Verktyg > Åtgärd > Webbkonsol]**.
1. Öppna tjänsten **Day CQ DAM Event Recorder** .
1. Välj **[!UICONTROL Aktivera den här tjänsten]** för att aktivera aktivitetsinspelning.

   ![chlimage_1-250](assets/chlimage_1-250.png)

1. I listan **Händelsetyper** väljer du vilka händelser som ska registreras och sparar ändringarna.

   >[!CAUTION]
   >
   >Om du aktiverar alternativen Visa, Visa projekt och Samlingar, ökar antalet inspelade händelser avsevärt.

1. Öppna **[!UICONTROL DAM-filens flagga]** för funktionsflagga på startsidan för resurser från Configuration Manager `https://[AEM_server]:[port]/system/console/configMgr`.
1. Välj alternativet **[!UICONTROL isEnabled.name]** för att aktivera funktionen Assets Home page. Spara ändringarna.

   ![chlimage_1-251](assets/chlimage_1-251.png)

1. Öppna dialogrutan **[!UICONTROL Användarinställningar]** och välj **[!UICONTROL Aktivera startsidan]** för resurser. Spara ändringarna.

   ![user_preferences](assets/user_preferences.png)

När du har aktiverat startsidan för Resurser navigerar du till användargränssnittet för Resurser från navigeringssidan.

![home_page](assets/home_page.png)

Tryck/klicka på **[!UICONTROL Klicka här för att konfigurera din upplevelselänk]** för att lägga till ditt användarnamn, din bakgrundsbild och din profilbild.

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

**Aktivitet**: I det här avsnittet visas widgeten **Min aktivitet** nyligen utförda aktiviteter som utförts av den inloggade användaren med resurser (inklusive resurser utan återgivningar), till exempel överföringar av resurser, hämtningar, skapande av resurser, redigeringar, kommentarer, anteckningar och delningar.

**Senaste**: Widgeten **Senast visade** under det här avsnittet visar nyligen använda enheter som den inloggade användaren har använt, inklusive mappar, samlingar och projekt.

**Upptäck**: Widgeten **Nytt** under det här avsnittet visar resurser och återgivningar som nyligen har överförts till AEM Assets-instansen.

Om du vill aktivera rensning av användaraktivitetsdata aktiverar du tjänsten **** DAM Event Rensa från Configuration Manager. När du har aktiverat den här tjänsten tas aktiviteter av den inloggade användaren som överskrider ett angivet nummer bort av systemet.

Välkomstskärmen innehåller enkla navigeringshjälpmedel, t.ex. ikoner i verktygsfältet för att komma åt mappar, samlingar och kataloger.

>[!NOTE]
>
>Om du aktiverar tjänsterna Day CQ DAM Event Recorder och DAM Event Rensa ökas skrivåtgärderna till JCR och sökindexering, vilket avsevärt ökar belastningen på AEM-servern. Den extra belastningen på AEM-servern kan påverka dess prestanda.

>[!CAUTION]
>
>Att hämta in, filtrera och rensa användaraktiviteter som krävs för Assets hemsida medför höga prestanda. Därför bör administratörer konfigurera hemsidan effektivt för målanvändare.
>
>Adobe rekommenderar att administratörer och användare som utför gruppåtgärder undviker att använda funktionen Startsida för resurser för att förhindra att användaraktiviteter ökar. Dessutom kan administratörer exkludera inspelningsaktiviteter för specifika användare genom att konfigurera **Dag CQ DAM Event Recorder** från Configuration Manager.
>
>Om du använder funktionen rekommenderar Adobe att du schemalägger tömningsfrekvensen baserat på serverbelastningen.
