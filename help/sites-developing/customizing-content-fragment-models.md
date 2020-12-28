---
title: PUBLICERA INTE, MEN ANPASSA INTE DELETE-modeller FÖR innehållsfragment
seo-title: Anpassa modeller för innehållsfragment
description: Content Fragment Models kan anpassas och utökas.
seo-description: Content Fragment Models kan anpassas och utökas.
page-status-flag: de-activated
uuid: 5bcfb5d8-37d4-4a0e-882d-bc8a1bac6ba7
contentOwner: aheimoz
discoiquuid: 208225ee-9052-4a45-9cfd-f8d27d4d70ed
noindex: true
translation-type: tm+mt
source-git-commit: b61c20c65ceade0153f5cd04fbedfd02e919d483
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---


# PUBLICERA INTE, MEN ANPASSA INTE DELETE-modeller för innehållsfragment{#do-not-publish-but-do-not-delete-customizing-content-fragment-models}

Redigeraren för innehållsfragmentmodellen är en guide baserad på `Formbuilder`, ärvd från:

`granite/ui/components/foundation/form/formbuilder`

Komponenten har de verktyg som krävs för att återge gränssnittet för dra och släpp i modellredigeraren, komplett med datatyper och egenskaper för varje.

## Platser {#locations}

Modeller sparas och skapas under `/conf`, under en mapp som har egenskapen [Content Fragment Models](/help/assets/content-fragments-models.md#enable-content-fragment-models) aktiverad. Den här inställningen finns även i **konfigurationsegenskaperna** som du kommer åt via **[konfigurationsläsaren](/help/sites-administering/configurations.md)**.

1. Navigera till webbläsaren via **Verktyg**, **Allmänt**, **Konfigurationsläsaren**
Till exempel: 
`http://localhost:4502/libs/granite/configurations/content/view.html/conf`

1. Välj lämplig konfiguration i webbläsaren och sedan **Egenskaper** i verktygsfältet.

   Egenskaperna för `global`: `http://localhost:4502/libs/granite/configurations/content/edit.html/conf/global`

I modellkonsolen visas alla mappar med egenskapen **Content Fragment Models**. Navigera via **Verktyg**, **Resurser**, **Modeller för innehållsfragment**; till exempel `http://localhost:4502/libs/dam/cfm/models/console/content/models.html/conf`.

En användare kan [skapa en innehållsfragmentmodell](/help/assets/content-fragments-models.md#creating-a-content-fragment-model) med guiden **Skapa modell** (med **Skapa** från konsolen).

>[!CAUTION]
>
>Du ***får*** inte ändra något i `/libs`-sökvägen.
>
>Detta beror på att innehållet i `/libs` skrivs över nästa gång du uppgraderar din instans (och kan skrivas över när du använder en snabbkorrigering eller ett funktionspaket).

## Modellens struktur {#structure-of-a-model}

Guiden skapar en post med den här strukturen:

![cf-54](assets/cf-54.png)

* `../settings/dam/cfm/models`

   Alla modeller sparas under undermappar till den här mappen.

* `jcr:content`

   Varje modell innehåller en `jcr:content`-nod som:

   * innehåller informationsegenskaper om modellen som `jcr:title`, `lastModified`, `lastModifiedBy`
   * har vanligtvis `sling:ResourceType` av `dam/cfm/models/console/components/data/entity/default`,

      med `sling:ResourceSuperType` av `dam/cfm/models/console/components/data/entity`

* `model`

   Noden `model` innehåller egenskapen `dataTypesConfig` som används för att avgöra vilka datatyper som används i modellredigeraren.

* `items`

   Under noden `items` sparas alla datatyper som läggs till i modellen (som om de dras och släpps i modellredigeraren). Varje objekt får ett slumpmässigt nodnamn, men för att innehållsfragmentredigeraren ska kunna arbeta med den här modellen måste varje objekt ha en `name`-egenskap. På den här noden sparas dessutom alla konfigurationsegenskaper för en viss datatyp, inklusive de standardegenskaper som behövs för att återge komponenterna.

>[!CAUTION]
>
>Alla datatyper som dras och släpps i en modellredigerare, och som sådana instansierade, måste **ha** egenskapen `name` angiven av användaren.
>
>Detta visas som **Egenskapsnamn&amp;ast;** på fliken **Egenskaper** i modellredigeraren.

## Modellredigerarens struktur {#structure-of-the-model-editor}

**Modellredigeraren för innehållsfragment** har två delar:

* Panelen Förhandsgranska, eller vyn, till vänster, där du kan släppa objekt. Det:

   * Visar en förhandsgranskning av den **datatyp** som har instansierats.
   * Tillåter beställning i modellredigeraren.

* Flikarna **Datatyper**/**Egenskaper** i panelen till höger. Det:

   * Visar en lista med datatyper som kan dras och instansieras.
   * I modellredigeraren finns listan här:

      `/libs/settings/dam/cfm/models/formbuilderconfig/datatypes`

      <!-- Please uncomment when file is used
      This node contains all the data types currently supported in the model editor. For more information on how to configure the data types, see [Customizing Data Types for Content Fragment Models](/help/sites-developing/customizing-content-fragment-model-data-types.md).
      -->

   * Alla återgivna datatyper har två skripttaggar som när de instansieras utgör vyn (komponenten som återges på vänster sida) och fliken **Egenskaper**, som definierar de egenskaper som en användare kan definiera för en viss komponent.

>[!CAUTION]
>
>Du ***får*** inte ändra något i `/libs`-sökvägen.
>
>Detta beror på att innehållet i `/libs` skrivs över nästa gång du uppgraderar din instans (och kan skrivas över när du använder en snabbkorrigering eller ett funktionspaket).

<!-- Please uncomment when files are used
The properties on the right side define a form that is submitted directly into JCR under `/conf`; see the path in the example [Structure of a Model](/help/sites-developing/customizing-content-fragment-models.md#structure-of-a-model).
-->

När en datatyp instansieras skapas HTML-indata för varje egenskap som komponenten behöver återges i ett innehållsfragment. De innehåller till exempel:

* **Egenskapsnamn &amp;ast;** (  `name`) - fungerar som en identifierare för komponenter

* **Återge som** (  `metaType`) - typ som komponenten ska återges som

* **Description** (  `fieldDescription`) - description of the component in the Content Fragment

* och andra.

