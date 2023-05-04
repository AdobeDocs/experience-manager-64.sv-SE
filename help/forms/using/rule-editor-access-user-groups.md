---
title: Bevilja regelredigeraråtkomst för valda användargrupper
seo-title: Grant rule editor access to select user groups
description: Bevilja begränsad åtkomst till regelredigeraren för att välja användargrupper.
seo-description: Grant restricted access to rule editor to select user groups.
uuid: 3d982858-b2b5-4370-a9d7-5a95842a7897
content-type: reference
topic-tags: adaptive_forms, develop
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 6bd58e37-085e-4057-8200-1404d54f41cc
feature: Adaptive Forms
exl-id: 5e2960f2-b172-48a7-bba3-4561a5f9c7bc
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---

# Bevilja regelredigeraråtkomst för valda användargrupper {#grant-rule-editor-access-to-select-user-groups}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

Du kan ha olika typer av användare med olika kunskaper som fungerar med Adaptive Forms. Expertanvändare kan ha rätt kunskaper för att arbeta med skript och komplexa regler, men det kan finnas grundläggande användare som bara behöver arbeta med layout och grundläggande egenskaper i anpassade formulär.

Med AEM Forms kan du begränsa regelredigeringsåtkomsten till användare baserat på deras roll eller funktion. I inställningarna för den adaptiva Forms-konfigurationstjänsten kan du ange [användargrupper](/help/sites-administering/security.md) som kan visa och komma åt regelredigeraren.

## Ange användargrupper som kan komma åt regelredigeraren {#specify-user-groups-that-can-access-rule-editor}

1. Logga in på AEM Forms som administratör.
1. Klicka på i författarinstansen ![adobeexperienceManager](assets/adobeexperiencemanager.png)Adobe Experience Manager > Verktyg ![hammare](assets/hammer.png) > Åtgärder > Webbkonsol. Webbkonsolen öppnas i ett nytt fönster.

   ![1](assets/1.png)

1. I webbkonsolfönstret letar du upp och klickar på **[!UICONTROL Adaptive Form and Interactive Communication Web Channel Configuration]**. **[!UICONTROL Adaptive Form and Interactive Communication Web Channel Configuration]** visas. Ändra inga värden och klicka **[!UICONTROL Save]**.

   Filen /apps/system/config/com.adobe.aemds.guide.service.impl.AdaptiveFormConfigurationServiceImpl.config skapas i CRX-databasen.

1. Logga in på CRXDE som administratör. Öppna filen /apps/system/config/com.adobe.aemds.guide.service.impl.AdaptiveFormConfigurationServiceImpl.config för redigering.
1. Använd följande egenskap för att ange namnet på en grupp som kan komma åt regelredigeraren (till exempel RuleEditorsUserGroup) och klicka på **Spara alla**.

   `af.ruleeditor.custom.groups=["RuleEditorsUserGroup"]`

   Om du vill aktivera åtkomst för flera grupper anger du en lista med kommasepererade värden:

   `af.ruleeditor.custom.groups=["RuleEditorsUserGroup", "PermittedUserGroup"]`

   ![create-user](assets/create-user.png)

   När en användare som inte är en del av den angivna användargruppen (här trycker RuleEditorsUserGroup) på ett fält visas nu ikonen Redigera regel ( ![edit-rules1](assets/edit-rules1.png)) finns inte i komponentverktygsfältet:

   ![componentsstoolbarwithre](assets/componentstoolbarwithre.png)

   Komponentverktygsfältet så som det visas för en användare med regelredigeringsåtkomst

   ![componentsstoolbarwithout](assets/componentstoolbarwithoutre.png)

   Komponentverktygsfältet så synligt som det är för en användare utan åtkomst till regelredigeraren

   Instruktioner om hur du lägger till användare i grupper finns i [Användaradministration och -säkerhet](/help/sites-administering/security.md).
