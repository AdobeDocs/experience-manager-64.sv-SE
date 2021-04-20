---
title: Koppla granskare som skickar in svar till ett formulär
seo-title: Koppla granskare som skickar in svar till ett formulär
description: Lär dig hur du associerar granskare med ett formulär i AEM Forms. Associerade granskare granskar ett formulär som skickats via formulärportalen.
seo-description: Lär dig hur du associerar granskare med ett formulär i AEM Forms. Associerade granskare granskar ett formulär som skickats via formulärportalen.
uuid: 66834c2b-ae70-4a6e-ae8e-07d0e38de06b
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 7c39383b-b430-40a1-9bcb-f5aaccb616ad
feature: Adaptive Forms
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---


# Koppla granskare som skickar in svar till ett formulär {#associating-submission-reviewers-with-a-form}

När du skapar ett formulär kan du ange vilka användare som ska granska inskickade formulär via formulärportalen och ge feedback. Din organisation kan samla in feedback och omarbeta de inskickade formulären.

Med AEM Forms kan du associera en granskargrupp med ett formulär. Användare som läggs till i en granskningsgrupp i ett formulär kan se inskickade formulär och ge feedback.

Granskningsgrupper som tilldelats ett formulär kan bara granska inskickade svar från det angivna formuläret.

## Förutsättning {#prerequisite}

### Aktiverar gruppegenskap för inskickande granskare för adaptiva formulär med metadataschemats redigerare {#enabling-submission-reviewer-groups-property-for-adaptive-forms-using-metadata-schema-editor}

Om du vill associera en granskargrupp med ett formulär redigerar du metadatarammet för anpassningsbara formulär. Som standard kan du inte lägga till en granskningsgrupp i ett skickat formulär.

Så här redigerar du metadataschema:

1. Klicka på **[!UICONTROL Tools > Assets > Metadata Schemas]** under Experience Manager i redigeringsläget.
1. Gå till **[!UICONTROL Forms > Forms Authored in AEM]** på Forms-sidan Schema.

   Sidans URL är:

   ```
   https://<hostname>:<port>/mnt/overlay/dam/gui/content/metadataschemaeditor/
    schemalist.html/dam/content/schemaeditors/forms/forms/
    aem-authored
   ```

1. Välj **[!UICONTROL Adaptive Form]** och klicka på **[!UICONTROL Edit]**.
1. Klicka på **[!UICONTROL Advanced]** på sidan Redigera formulär.
1. Dra och släpp **[!UICONTROL Single Line Text]**-komponenten som finns under Skapa formulär på fliken Avancerat.
1. Markera den tillagda textkomponenten för att se dess inställningar.

   Under Inställningar anger du `./jcr:content/metadata/form-submission-reviewer-group` i fältet Mappa till egenskap.

   Fältet för gruppen Skicka granskare i de avancerade egenskaperna för ditt adaptiva formulär aktiveras med det namn du anger under Fältetikett.

## Koppla granskare som skickar in svar till ett formulär {#associating-submission-reviewers-with-a-form-1}

Om du vill associera granskare med ett anpassat formulär skapar du en granskargrupp och lägger till användare. Lägg till den skapade granskargruppen under fältet för att skicka in formulär i formulärets avancerade egenskaper.\
Med användargrupper kan du associera olika uppsättningar av granskare med olika anpassningsbara formulär. Den här funktionen förhindrar att obehöriga skickar in granskningar.

Innan du utför följande steg ska du läsa [Krav](/help/forms/using/adding-reviewers-form.md#prerequisite).

Om du vill skapa en grupp och lägga till medlemmar i den går du till **[!UICONTROL Tools > Operations > Security > Groups]**.\
Mer information finns i [Användaradministration och -tjänster](/help/sites-administering/security.md).\
Se till att du lägger till gruppen som du skapar som medlem i den körklara användargruppen: **forms-submit-reviewers**. Den här användargruppen levereras med AEM Forms och ser till att användare läggs till som granskare.

Så här associerar du användargrupper med ett anpassat formulär:

1. Navigera till **[!UICONTROL Forms > Forms & Documents]** i redigeringsläget.
1. Använd alternativet **[!UICONTROL Select]** för att välja ett anpassat formulär och klicka på **[!UICONTROL View Properties]**.
1. Klicka på **[!UICONTROL Edit]** i fönstret Egenskaper för formuläret och klicka sedan på **[!UICONTROL ADVANCED]**.
1. Ange gruppen i gruppfältet för granskare som ska skicka in och klicka på **[!UICONTROL Done]**.

   Fältet för granskningsgruppen som ska skickas visas med det namn som du angav i det redigerade metadataschemat för anpassade formulär.

>[!NOTE]
>
>Replikera användare och formulär för att säkerställa att de är tillgängliga för användare och formulär vid fjärrimplementeringen av AEM Forms.
>
>Se till att alla användare replikeras som granskningsmedlemmar i användargrupperna i fjärrimplementeringen.

