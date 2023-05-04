---
title: Visa komponenter baserat på den mall som används
seo-title: Displaying components based on the template used
description: När du skapar ett formulär ska du lära dig hur du kan aktivera komponenter i sidofältet baserat på den valda mallen.
seo-description: When you create a form, learn how you can enable components in the sidebar based on the template selected.
uuid: 4e87f400-fb45-413d-9be8-72edbe99f210
contentOwner: sashanka
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: customization
content-type: reference
discoiquuid: 940e45b4-dbf1-4207-bd4a-cf677d645fb4
exl-id: a4cee2e6-a56f-4355-8176-b3ed7478a775
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 1%

---

# Visa komponenter baserat på den mall som används {#displaying-components-based-on-the-template-used}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

När en formulärförfattare skapar ett anpassat formulär med en [mall](/help/forms/using/template-editor.md)kan formulärförfattaren se och använda specifika komponenter som är baserade på mallprinciper. Du kan ange en innehållsprincip för mallar där du kan välja en grupp komponenter som formulärförfattaren ser när formuläret skapas.

## Ändra innehållsprincipen för en mall {#changing-the-content-policy-of-a-template}

När du skapar en mall skapas den under `/conf` i innehållsdatabasen. Baserat på de mappar du har skapat i `/conf` -katalog, sökvägen till mallen är: `/conf/<your-folder>/settings/wcm/templates/<your-template>`.

Följ de här stegen för att visa komponenterna i sidofältet baserat på en malls innehållsprincip:

1. Öppna CRXDE lite.

   URL: `https://<server>:<port>/crx/de/index.jsp`

1. I CRXDE navigerar du till mappen där mallen skapas.

   Till exempel: `/conf/<your-folder>/`

1. I CRXDE navigerar du till: `/conf/<your-folder>/settings/wcm/policies/fd/af/layouts/gridFluidLayout/`

   Om du vill välja en grupp komponenter krävs en ny innehållsprincip. Om du vill skapa en ny princip kopierar och klistrar du in standardprincipen och byter namn på den.

   Sökvägen till standardinnehållsprincipen är: `/conf/<your-folder>/settings/wcm/policies/fd/af/layouts/gridFluidLayout/default`

   I `gridFluidLayout` mapp, kopiera och klistra in standardprincipen och döp om den. Till exempel, `myPolicy`.

   ![Kopierar standardprinciper](assets/crx-default1.png)

1. Välj den nya profilen som du skapar och välj **komponenter** egenskap på den högra panelen med text `string[]`.

   När du markerar och öppnar komponentegenskapen visas dialogrutan Redigera komponenter. I dialogrutan Redigera komponenter kan du lägga till eller ta bort komponentgrupper med **+** och **-** knappar. Du kan lägga till komponentgrupper som innehåller komponenter som du vill att författarna ska använda.

   ![Lägga till eller ta bort komponenter i profilen](assets/add-components-list1.png)

   När du har lagt till en komponentgrupp klickar du på **OK** för att uppdatera listan och sedan klicka på **Spara alla** ovanför adressfältet för CRXDE och uppdatera.

1. I mallen ändrar du innehållsprincipen från standard till den nya profilen som du skapade. ( `myPolicy` i det här exemplet.)

   I CRXDE navigerar du till `/conf/<your-folder>/settings/wcm/templates/<your-template>/policies/jcr:content/guideContainer/rootPanel/items`.

   I `cq:policy` egenskap, ändra `default` till det nya principnamnet ( `myPolicy`).

   ![Uppdaterad princip för mallinnehåll](assets/updated-policy.png)

   När du skapar ett formulär som du skapar med hjälp av mallen kan du se de komponenter som lagts till i sidofältet.
