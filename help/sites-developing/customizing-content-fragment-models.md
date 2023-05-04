---
title: PUBLICERA INTE, MEN ANPASSA INTE DELETE-modeller FÖR innehållsfragment
seo-title: Customizing Content Fragment Models
description: Content Fragment Models kan anpassas och utökas.
seo-description: Content Fragment Models can be customized and extended.
page-status-flag: de-activated
uuid: 5bcfb5d8-37d4-4a0e-882d-bc8a1bac6ba7
contentOwner: AEM Docs
discoiquuid: 208225ee-9052-4a45-9cfd-f8d27d4d70ed
noindex: true
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 0%

---


# PUBLICERA INTE, MEN ANPASSA INTE DELETE-modeller FÖR innehållsfragment{#do-not-publish-but-do-not-delete-customizing-content-fragment-models}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Redigeraren för innehållsfragmentmodellen är en guide baserad på `Formbuilder`, ärvs från:

`granite/ui/components/foundation/form/formbuilder`

Komponenten har de verktyg som krävs för att återge gränssnittet för dra och släpp i modellredigeraren, komplett med datatyper och egenskaper för varje.

## Platser {#locations}

Modeller sparas och skapas under `/conf`, under en mapp som har [Egenskapen Content Fragment Models](/help/assets/content-fragments-models.md#enable-content-fragment-models) aktiverat. Den här inställningen kan även visas i dialogrutan **Konfigurationsegenskaper**, kan du nå från **[Konfigurationsläsaren](/help/sites-administering/configurations.md)**.

1. Navigera till webbläsaren via **verktyg**, **Allmänt**, **Konfigurationsläsaren**
Till exempel: 
`http://localhost:4502/libs/granite/configurations/content/view.html/conf`

1. Välj lämplig konfiguration i webbläsaren och sedan **Egenskaper** i verktygsfältet.

   Egenskaperna för `global`: `http://localhost:4502/libs/granite/configurations/content/edit.html/conf/global`

I modellkonsolen finns alla mappar med **Modeller för innehållsfragment** -egenskapen visas. Navigera via **verktyg**, **Resurser**, **Modeller för innehållsfragment**; till exempel `http://localhost:4502/libs/dam/cfm/models/console/content/models.html/conf`.

En användare kan [skapa en innehållsfragmentmodell](/help/assets/content-fragments-models.md#creating-a-content-fragment-model) med **Skapa modell** guide (använda **Skapa** från konsolen).

>[!CAUTION]
>
>Du ***måste*** ändrar ingenting i `/libs` bana.
>
>Detta beror på innehållet i `/libs` skrivs över nästa gång du uppgraderar din instans (och kan skrivas över när du använder en snabbkorrigering eller ett funktionspaket).

## Modellens struktur {#structure-of-a-model}

Guiden skapar en post med den här strukturen:

![cf-54](assets/cf-54.png)

* `../settings/dam/cfm/models`

   Alla modeller sparas under undermappar till den här mappen.

* `jcr:content`

   Varje modell innehåller en `jcr:content` nod som:

   * innehåller informationsegenskaper om modellen som `jcr:title`, `lastModified`, `lastModifiedBy`
   * har `sling:ResourceType` av `dam/cfm/models/console/components/data/entity/default`,

      med `sling:ResourceSuperType` av `dam/cfm/models/console/components/data/entity`

* `model`

   The `model` noden innehåller en egenskap `dataTypesConfig`, används för att avgöra vilka datatyper som används i modellredigeraren.

* `items`

   Under `items` noden sparas alla datatyper som läggs till i modellen (som om de dras och släpps i modellredigeraren). Varje objekt får ett slumpmässigt nodnamn, men för att innehållsfragmentredigeraren ska kunna arbeta med den här modellen måste varje objekt ha ett `name` -egenskap. På den här noden sparas dessutom alla konfigurationsegenskaper för en viss datatyp, inklusive de standardegenskaper som behövs för att återge komponenterna.

>[!CAUTION]
>
>Alla datatyper som dras och släpps i en modellredigerare, och som sådana instansierade, **måste** har `name` användarens egenskapsindata.
>
>Detta ses som **Egenskapsnamn &amp;ast;** i **Egenskaper** fliken i modellredigeraren.

## Modellredigerarens struktur {#structure-of-the-model-editor}

The **Modellredigerare för innehållsfragment** har två delar:

* Panelen Förhandsgranska, eller vyn, till vänster, där du kan släppa objekt. Det:

   * Visar en förhandsgranskning av **Datatyp** som instansieras.
   * Tillåter beställning i modellredigeraren.

* The **Datatyper**/**Egenskaper** i panelen till höger. Det:

   * Visar en lista med datatyper som kan dras och instansieras.
   * I modellredigeraren finns listan här:

      `/libs/settings/dam/cfm/models/formbuilderconfig/datatypes`

      <!-- Please uncomment when file is used
      This node contains all the data types currently supported in the model editor. For more information on how to configure the data types, see [Customizing Data Types for Content Fragment Models](/help/sites-developing/customizing-content-fragment-model-data-types.md).
      -->

   * Alla återgivna datatyper har två skripttaggar som när de instansieras kommer att formge vyn (komponenten som återges på vänster sida) och **Egenskaper** som definierar de egenskaper som en användare kan definiera för en viss komponent.

>[!CAUTION]
>
>Du ***måste*** ändrar ingenting i `/libs` bana.
>
>Detta beror på innehållet i `/libs` skrivs över nästa gång du uppgraderar din instans (och kan skrivas över när du använder en snabbkorrigering eller ett funktionspaket).

<!-- Please uncomment when files are used
The properties on the right side define a form that is submitted directly into JCR under `/conf`; see the path in the example [Structure of a Model](/help/sites-developing/customizing-content-fragment-models.md#structure-of-a-model).
-->

När en datatyp instansieras skapas HTML-indata för varje egenskap som komponenten behöver återges i ett innehållsfragment. De innehåller till exempel:

* **Egenskapsnamn &amp;ast;** ( `name`) - fungerar som en identifierare för komponenter

* **Återge som** ( `metaType`) - typ som komponenten ska återges som

* **Beskrivning** ( `fieldDescription`) - beskrivning av komponenten i Content Fragment

* och andra.

