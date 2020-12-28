---
title: Konfigurera RTE för produktion av tillgängliga platser
seo-title: Konfigurera RTE för produktion av tillgängliga platser
description: Lär dig hur du konfigurerar AEM RTF-redigerare för att skapa tillgängliga webbplatser.
seo-description: Lär dig hur du konfigurerar AEM RTF-redigerare för att skapa tillgängliga webbplatser.
uuid: 87539fee-3ecc-49f4-af3d-8dde72399c28
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: ff0f006d-461c-4cc4-b6eb-d665f3f3b498
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---


# Konfigurerar RTE för produktion av tillgängliga platser {#configuring-rte-for-producing-accessible-sites}

AEM har stöd för båda:

* standardfunktioner för tillgänglighet, inklusive alternativ text för bilder
* samt andra funktioner som du kan komma åt när du skapar innehåll med komponenter som använder textredigeraren (RTE)

>[!NOTE]
>
>* [Snabbguide till WCAG 2.0](/help/managing/qg-wcag.md)
>* [Skapa tillgängligt innehåll (WCAG 2.0-överensstämmelse)](/help/sites-authoring/creating-accessible-content.md)


Innehållsförfattare kan använda funktionerna i RTE för att tillhandahålla hjälpmedelsinformation när de lägger till innehåll på en sida. Det kan vara att lägga till strukturinformation via rubriker och styckeelement.

Du kan [konfigurera och anpassa dessa funktioner genom att konfigurera RTE-plugin-program](#configuring-the-plugin-features) för komponenten. Med plugin-programmet `paraformat` kan du till exempel lägga till ytterligare semantiska element på blocknivå, inklusive att utöka antalet rubriknivåer som stöds utöver de grundläggande `H1`, `H2` och `H3` som finns som standard.

RTE finns i en mängd komponenter från både det beröringsaktiverade och det klassiska användargränssnittet. Den primära komponenten för att använda RTE är **Text**-komponenten.

Komponenten **Text** i AEM är tillgänglig för både det beröringsaktiverade och det klassiska användargränssnittet. I följande bilder visas textredigeraren med ett intervall av plugin-program aktiverade, inklusive `paraformat`:

* Komponenten **Text** i det beröringsaktiverade användargränssnittet:

   ![Textkomponent (RTE) i helskärmsläge i det beröringsaktiverade användargränssnittet.](assets/chlimage_1-206.png)

* Komponenten **Text** i det klassiska användargränssnittet:

   ![Dialogrutan Redigera (RTE) för textkomponenten i det klassiska användargränssnittet.](assets/chlimage_1-207.png)

>[!NOTE]
>
>Det finns skillnader mellan de RTE-funktioner som är tillgängliga i det klassiska användargränssnittet och det pekaktiverade användargränssnittet. Mer information finns i
>
>* [Plugins och deras funktioner](/help/sites-administering/rich-text-editor.md#aboutplugins)
>* [Plugin-program och deras funktioner - användargränssnittet aktiverat för pekfunktioner](/help/sites-administering/rich-text-editor.md#aboutplugins)

>



## Konfigurera plug-in-funktioner {#configuring-the-plugin-features}

Fullständiga anvisningar om hur du konfigurerar textredigeraren finns på sidan [Konfigurera textredigeraren](/help/sites-administering/rich-text-editor.md). Detta täcker alla frågor, inklusive de viktigaste stegen:

* [Plugins och deras funktioner](/help/sites-administering/rich-text-editor.md#aboutplugins)
* [Konfigurationsplatser](/help/sites-administering/rich-text-editor.md#understand-the-configuration-paths-and-locations)
* [Aktivera ett plugin-program och konfigurera egenskapen features](/help/sites-administering/rich-text-editor.md#enable-rte-functionalities-by-activating-plug-ins)
* [Konfigurera övriga funktioner i textredigeringsprojektet](/help/sites-administering/rich-text-editor.md#enable-rte-functionalities-by-activating-plug-ins)

Genom att konfigurera ett plugin-program i rätt `rtePlugins`-undergren i CRXDE Lite (se följande bild) kan du aktivera alla eller specifika funktioner för det plugin-programmet.

![CRXDE Lite med exempelplugin-programmet ratePlugin.](assets/chlimage_1-208.png)

### Exempel - Ange tillgängliga styckeformat i fältet RTE-markering {#example-specifying-paragraph-formats-available-in-rte-selection-field}

Nya semantiska blockformat kan göras tillgängliga för markering genom att:

1. Beroende på vilken RTE du använder kan du bestämma och navigera till [konfigurationsplatsen](/help/sites-administering/rich-text-editor.md#understand-the-configuration-paths-and-locations).
1. [Aktivera fältet](/help/sites-administering/rich-text-editor.md) för val av stycken; genom  [att aktivera plugin-programmet](/help/sites-administering/rich-text-editor.md#enable-rte-functionalities-by-activating-plug-ins).
1. [Ange de format du vill ha i fältet](/help/sites-administering/rich-text-editor.md) Stycke.
1. Styckeformaten är sedan tillgängliga för innehållsförfattaren från markeringsfälten i textredigeraren. De kan nås:

   * Använda ikonen för stycke ([pilbåge](https://en.wikipedia.org/wiki/Pilcrow)) i det beröringsaktiverade gränssnittet:

   ![Styckeikon (pilbåge).](do-not-localize/chlimage_1-7.png)

   * Använda fältet **Format** (nedrullningsbar väljare) i det klassiska användargränssnittet.


Eftersom strukturella element är tillgängliga i textredigeraren via alternativen för styckeformat, är AEM en bra grund för utveckling av hjälpmedelsanpassat innehåll. Innehållsförfattare kan inte använda textredigeraren för att formatera teckenstorlek, färger eller andra relaterade attribut, vilket förhindrar att textbunden formatering skapas. I stället måste de markera lämpliga strukturella element, t.ex. rubriker, och använda globala format som du väljer med alternativet Format. Detta garanterar ren markering, fler alternativ för användare som bläddrar med egna formatmallar och korrekt strukturerat innehåll.

## Användning av funktionen för källredigering {#use-of-the-source-edit-feature}

I vissa fall måste innehållsförfattare granska och justera HTML-källkoden som skapats med RTE. En del innehåll som skapats i en textredigerare kan till exempel kräva ytterligare kod för att säkerställa överensstämmelse med WCAG 2.0. Detta kan du göra med alternativet [källredigering](/help/sites-administering/rich-text-editor.md#aboutplugins) i textredigeringsprogrammet. Du kan ange [ `sourceedit`-funktionen i `misctools`-plugin](/help/sites-administering/rich-text-editor.md#aboutplugins).

>[!CAUTION]
>
>Använd funktionen `sourceedit` noggrant. Skrivfel och/eller funktioner som inte stöds kan orsaka fler problem.

## Lägger till stöd för ytterligare HTML-element och attribut {#adding-support-for-additional-html-elements-and-attributes}

Om du vill utöka tillgänglighetsfunktionerna i AEM ytterligare kan du utöka de befintliga komponenterna baserat på RTE (till exempel **Text** och **Tabell**-komponenterna) med ytterligare element och attribut.

Följande procedur visar hur du utökar komponenten **Table** med elementet **Caption** som ger information om en datatabell till hjälpmedelstekniker:

### Exempel - Lägga till bildtexten i dialogrutan Tabellegenskaper {#example-adding-the-caption-to-the-table-properties-dialog}

I konstruktorn för `TablePropertiesDialog` lägger du till ytterligare ett textinmatningsfält som används för att redigera bildtexten. Observera att `itemId` måste anges till `caption` (d.v.s. DOM-attributets namn) för att innehållet ska hanteras automatiskt.

I **Tabell** måste du uttryckligen ange eller ta bort attributet till/från DOM-elementet. Värdet skickas av dialogrutan i `config`-objektet. Observera att DOM-attribut bör anges/tas bort med motsvarande `CQ.form.rte.Common`-metoder ( `com` är en genväg för `CQ.form.rte.Common`) för att undvika vanliga fel i webbläsarimplementeringar.

>[!NOTE]
>
>Den här proceduren passar bara för det klassiska användargränssnittet.

### Steg för steg-instruktioner {#step-by-step-instructions}

1. Starta CRXDE Lite. Till exempel: [http://localhost:4502/crx/de/](http://localhost:4502/crx/de/)
1. Kopiera:

   `/libs/cq/ui/widgets/source/widgets/form/rte/commands/Table.js`

   till:

   `/apps/cq/ui/widgets/source/widgets/form/rte/commands/Table.js`

   >[!NOTE]
   >
   >Du kan behöva skapa mellanliggande mappar om de inte redan finns.

1. Kopiera:

   `/libs/cq/ui/widgets/source/widgets/form/rte/plugins/TablePropertiesDialog.js`

   till:

   `/apps/cq/ui/widgets/source/widgets/form/rte/plugins/TablePropertiesDialog.js`.

1. Öppna följande fil för redigering (öppna med dubbelklick):

   `/apps/cq/ui/widgets/source/widgets/form/rte/plugins/TablePropertiesDialog.js`

1. I metoden `constructor`, före radläsningen:

   ```
   var dialogRef = this;
   ```

   Lägg till följande kod:

   ```
   editItems.push({
       "itemId": "caption",
       "name": "caption",
       "xtype": "textfield",
       "fieldLabel": CQ.I18n.getMessage("Caption"),
       "value": (this.table && this.table.caption ? this.table.caption.textContent : "")
   });
   ```

1. Öppna följande fil:

   `/apps/cq/ui/widgets/source/widgets/form/rte/commands/Table.js`.

1. Lägg till följande kod i slutet av metoden `transferConfigToTable`:

   ```
   /**
    * Adds Caption Element
   */
   var captionElement;
   if (dom.firstChild && dom.firstChild.tagName.toLowerCase() == "caption")
   {
      captionElement = dom.firstChild;
   }
   if (config.caption)
   {
       var captionTextNode = document.createTextNode(config.caption)
       if (captionElement)
       {
          dom.replaceNode(captionElement.firstChild,captionTextNode);
       } else
       {
           captionElement = document.createElement("caption");
           captionElement.appendChild(captionTextNode);
           if (dom.childNodes.length>0)
           {
              dom.insertBefore(captionElement, dom.firstChild);
           } else
           {
              dom.appendChild(captionElement);
           }
       }
   } else if (captionElement)
   {
     dom.removeChild(captionElement);
   }
   ```

1. Spara ändringarna med **Spara alla**

>[!NOTE]
>
>Ett oformaterat textfält är inte den enda typen av indata som tillåts för bildtextelementets värde. Alla ExtJS-widgetar som innehåller bildtextens värde via metoden `getValue()` kan användas.
>
>Om du vill lägga till redigeringsfunktioner för ytterligare element och attribut måste du se till att båda:
>
>* Egenskapen `itemId` för varje motsvarande fält anges till namnet på lämpligt DOM-attribut (`TablePropertiesDialog`).
>* Attributet anges och/eller tas bort explicit i DOM-elementet (`Table`).

