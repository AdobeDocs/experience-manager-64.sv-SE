---
title: Koppla granskare som skickar in svar till ett formulär
seo-title: Koppla granskare som skickar in svar till ett formulär
description: Lär dig hur du associerar granskare som skickar in svar med ett formulär i AEM Forms. Associerade granskare granskar ett formulär som skickats via formulärportalen.
seo-description: Lär dig hur du associerar granskare som skickar in svar med ett formulär i AEM Forms. Associerade granskare granskar ett formulär som skickats via formulärportalen.
uuid: 66834c2b-ae70-4a6e-ae8e-07d0e38de06b
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 7c39383b-b430-40a1-9bcb-f5aaccb616ad
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Koppla granskare som skickar in svar till ett formulär {#associating-submission-reviewers-with-a-form}

När du skapar ett formulär kan du ange vilka användare som ska granska inskickade formulär via formulärportalen och ge feedback. Din organisation kan samla in feedback och omarbeta de inskickade formulären.

Med AEM Forms kan du koppla en granskargrupp till ett formulär. Användare som läggs till i en granskningsgrupp i ett formulär kan se inskickade formulär och ge feedback.

Granskningsgrupper som tilldelats ett formulär kan bara granska inskickade svar från det angivna formuläret.

## Förutsättning {#prerequisite}

### Aktivera gruppegenskap för granskare som skickar in formulär med hjälp av schemaredigeraren för metadata {#enabling-submission-reviewer-groups-property-for-adaptive-forms-using-metadata-schema-editor}

Om du vill associera en granskargrupp med ett formulär redigerar du metadatarammet för anpassningsbara formulär. Som standard kan du inte lägga till en granskningsgrupp i ett skickat formulär.

Så här redigerar du metadataschema:

1. I redigeringsläget, under Experience Manager, klickar du på **[!UICONTROL Verktyg > Resurser > Metadata Schemas]**.
1. Gå till **[!UICONTROL Formulär > Formulär som har skapats i AEM]** på sidan Schemaformulär.

   Sidans URL är:

   ```
   https://<hostname>:<port>/mnt/overlay/dam/gui/content/metadataschemaeditor/
    schemalist.html/dam/content/schemaeditors/forms/forms/
    aem-authored
   ```

1. Välj **[!UICONTROL Adaptivt formulär]** och klicka på **[!UICONTROL Redigera]**.
1. Klicka på **[!UICONTROL Avancerat]** på sidan Redigera formulär.
1. Dra och släpp komponenten **[!UICONTROL Single Line Text]** under Build Form (Skapa formulär) på fliken Avancerat.
1. Markera den tillagda textkomponenten för att se dess inställningar.

   Under Inställningar anger du `./jcr:content/metadata/form-submission-reviewer-group` i fältet Koppla till egenskap.

   Fältet för gruppen Skicka granskare i de avancerade egenskaperna för ditt adaptiva formulär aktiveras med det namn du anger under Fältetikett.

## Koppla granskare som skickar in svar till ett formulär {#associating-submission-reviewers-with-a-form-1}

Om du vill associera granskare med ett anpassat formulär skapar du en granskargrupp och lägger till användare. Lägg till den skapade granskargruppen under fältet för att skicka in formulär i formulärets avancerade egenskaper.\
Med användargrupper kan du associera olika uppsättningar av granskare med olika anpassningsbara formulär. Den här funktionen förhindrar att obehöriga skickar in granskningar.

Innan du utför följande steg ska du läsa [Förutsättning](/help/forms/using/adding-reviewers-form.md#prerequisite).

Om du vill skapa en grupp och lägga till medlemmar i den går du till **[!UICONTROL Verktyg > Åtgärder > Skydd > Grupper]**.\
Mer information finns i [Användaradministration och -tjänster](/help/sites-administering/security.md).\
Se till att du lägger till gruppen som du skapar som medlem i den körklara användargruppen: Skicka **blanketter till granskare**. Användargruppen levereras med AEM Forms och ser till att användare läggs till som granskare.

Så här associerar du användargrupper med ett anpassat formulär:

1. I redigeringsläget går du till **[!UICONTROL Formulär > Formulär och dokument]**.
1. Använd alternativet **[!UICONTROL Välj]** för att välja ett anpassat formulär och klicka på **[!UICONTROL Visa egenskaper]**.
1. Klicka på **[!UICONTROL Redigera]** i fönstret Egenskaper i formuläret och klicka sedan på **[!UICONTROL ADVANCED]**.
1. Ange gruppen i gruppfältet för granskare som ska skicka in och klicka på **[!UICONTROL Klar]**.

   Fältet för granskningsgruppen som ska skickas visas med det namn som du angav i det redigerade metadataschemat för anpassade formulär.

>[!NOTE]
>
>Replikera användare och formulär för att säkerställa tillgänglighet för användare och formulär i fjärrimplementeringen av AEM Forms.
>
>Se till att alla användare replikeras som granskningsmedlemmar i användargrupperna i fjärrimplementeringen.

