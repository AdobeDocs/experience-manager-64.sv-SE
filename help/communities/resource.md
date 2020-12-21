---
title: Skapa och tilldela aktiveringsresurser
seo-title: Skapa och tilldela aktiveringsresurser
description: Lägg till aktiveringsresurser
seo-description: Lägg till aktiveringsresurser
uuid: da940242-0c9b-4ad8-8880-61fd41461c3b
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 8fe97181-600e-42ac-af25-d5d4db248740
translation-type: tm+mt
source-git-commit: 28948f1f8678512f8fc970a4289cb01cde86c5c2
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 4%

---


# Skapa och tilldela aktiveringsresurser {#create-and-assign-enablement-resources}

## Lägg till en aktiveringsresurs {#add-an-enablement-resource}

Så här lägger du till en aktiveringsresurs på den nya communitywebbplatsen:

* På författarinstansen
   * Till exempel [http://localhost:4502/](http://localhost:4503/)
* Logga in som systemadministratör
* Välj **Communities > [Resources](resources.md)** från global navigering

   ![chlimage_1-199](assets/chlimage_1-199.png)
   ![chlimage_1-200](assets/chlimage_1-200.png)
* Välj den community där aktiveringsresurser läggs till
   * Välj `Enablement Tutorial`
* Välj ` Create` på menyn
* Välj **[!UICONTROL Resource]**

![chlimage_1-201](assets/chlimage_1-201.png)

### Grundläggande information {#basic-info}

Fyll i grundläggande information för resursen:

* **[!UICONTROL Site Name]**: ange namnet på den valda communitywebbplatsen: Självstudiekurs om aktivering
* **[!UICONTROL Resource Name&ast;]**: Ski Lesson 1
* **[!UICONTROL Tags]**: Självstudiekurs: Idrott/skidåkning
* **[!UICONTROL Show in Catalog]**: På
* **[!UICONTROL Description]**: Snön snurrar för nybörjare
* **[!UICONTROL Add Image]**: Lägg till en bild som representerar resursen för medlemmen i uppdragsvyn
   ![chlimage_1-202](assets/chlimage_1-202.png)
* Välj **[!UICONTROL Next]**

### Lägg till innehåll {#add-content}

Det ser ut som om flera resurser kan väljas, men bara en är tillåten.

Välj `'+' icon` i det övre högra hörnet för att börja välja resursen genom att identifiera källan.

![chlimage_1-203](assets/chlimage_1-203.png) ![chlimage_1-204](assets/chlimage_1-204.png)

Överför en resurs. Om det är en videoresurs kan du antingen överföra en anpassad bild som ska visas innan videon börjar spelas upp eller tillåta att en miniatyrbild genereras från videon (kan ta några minuter - det är inte nödvändigt att vänta).

![chlimage_1-205](assets/chlimage_1-205.png)

* select **[!UICONTROL Next]**

### Inställningar {#settings}

* **[!UICONTROL Social Settings]**
Lämna standardinställningarna så att eleverna kan kommentera och betygsätta aktiveringsresurser.
* **[!UICONTROL Due Date]**

   *(Valfritt)*  Ett datum då uppdraget ska vara slutfört kan väljas.
* **[!UICONTROL Resource Author]**

   *(Valfritt)* Lämna tomt.
* **[!UICONTROL Resource Contact&ast;]**

   *(Obligatoriskt)* Använd listrutan för att välja medlem  `Quinn Harper`.
* **[!UICONTROL Resource Expert]**

   *(Valfritt)* Lämna tomt.
   **Obs**: Om användare eller grupper inte visas kontrollerar du att de har lagts till i  `Community Enable Members` gruppen och  ** sparats i publiceringsinstansen.
   ![chlimage_1-206](assets/chlimage_1-206.png)
* Välj **[!UICONTROL Next]**

### Uppdrag {#assignments}

* **[!UICONTROL Add Assignees]**
Låt vara unset eftersom den här aktiveringsresursen läggs till i en utbildningsväg. Om en elev tilldelas till den enskilda aktiveringsresursen samt en learningsökväg som innehåller aktiveringsresursen, tilldelas eleven till aktiveringsresursen två gånger.

![chlimage_1-207](assets/chlimage_1-207.png)

* Välj **[!UICONTROL Create]**

![chlimage_1-208](assets/chlimage_1-208.png)

Resursen har skapats och återgår till resurskonsolen med den nyligen skapade resursen markerad. Från den här konsolen går det att publicera, lägga till deltagare och ändra andra inställningar.

Om du vill överföra en ny version av aktiveringsresursen rekommenderar vi att du skapar en ny resurs och sedan avregistrerar medlemmar från den gamla versionen och registrerar dem i den nya versionen.

### Publicera resursen {#publish-the-resource}

Innan registrerare kan se den tilldelade kursen måste den publiceras:

* Markera världen `Publish`ikon

Aktiveringen har bekräftats med ett meddelande:

![chlimage_1-209](assets/chlimage_1-209.png)

## Lägg till en andra aktiveringsresurs {#add-a-second-enablement-resource}

Upprepa stegen ovan för att skapa och publicera en andra relaterad aktiveringsresurs som en inlärningsväg skapas från.

![chlimage_1-210](assets/chlimage_1-210.png)

**Publicera** den andra resursen.

Gå tillbaka till självstudiekursen om aktivering av dess resurser.

*Tips: Uppdatera sidan om båda resurserna inte visas.*

![chlimage_1-211](assets/chlimage_1-211.png)

## Lägg till en utbildningssökväg {#add-a-learning-path}

En inlärningsväg är en logisk gruppering av aktiveringsresurser som utgör en kurs.

* Välj `+ Create` från resurskonsolen
* Välj **[!UICONTROL Learning Path]**

![chlimage_1-212](assets/chlimage_1-212.png)

Lägg till **[!UICONTROL Basic Info]**:

* **[!UICONTROL Learning Path Name]**: Ski-lektioner
* **[!UICONTROL Tags]**: Självstudiekurs: Skickar
* **[!UICONTROL Show in Catalog]**: lämna ej markerat
* **[!UICONTROL Upload an image]** för att visa utbildningssökvägen i resurskonsolen

![chlimage_1-213](assets/chlimage_1-213.png)

* Välj **[!UICONTROL Next]**

Hoppa över nästa panel eftersom det inte finns några nödvändiga inlärningsvägar att lägga till.

* Välj **[!UICONTROL Next]**

På panelen Lägg till resurser

* Välj `+ Add Resources` för att välja de två skidlesionsresurserna som ska läggas till i inlärningsvägen

   Obs! Endast **publicerade** resurser kan markeras.

>[!NOTE]
>
>Du kan bara välja resurser på samma nivå som utbildningsvägen. För en inlärningsväg som skapats i en grupp är t.ex. endast resurserna på gruppnivå tillgängliga. för en inlärningsväg som skapats på en community-webbplats finns resurserna på den webbplatsen tillgängliga för tillägg till inlärningsvägen.

* Välj **[!UICONTROL Submit]**.

![chlimage_1-214](assets/chlimage_1-214.png) ![chlimage_1-215](assets/chlimage_1-215.png)

* Välj **[!UICONTROL Next]**

![chlimage_1-216](assets/chlimage_1-216.png)

* **[!UICONTROL Add Assignees]**
Använd listrutan för att välja 
`Community Ski Class` grupp, som bör omfatta medlemmar  `Riley Taylor` och  `Sidney Croft.`

* **[!UICONTROL Learning Path Contact&ast;]**

   *(Obligatoriskt)* Använd listrutan för att välja medlem  `Quinn Harper`.

* Välj **[!UICONTROL Create]**

![chlimage_1-217](assets/chlimage_1-217.png)

Utbildningssökvägen har skapats och återgår till resurskonsolen med den nya utbildningssökvägen markerad. Från den här konsolen går det att publicera, lägga till deltagare och ändra andra inställningar.

**Publicera** utbildningsvägen.

