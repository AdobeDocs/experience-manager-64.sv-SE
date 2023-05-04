---
title: Använda regeluppsättningar för att omforma URL:er
description: Du kan distribuera regeluppsättningar i Dynamic Media för att omvandla URL:er. Regeluppsättningar är instruktioner skrivna i ett skriptspråk (t.ex. JavaScript) som utvärderar XML-data och utför vissa åtgärder om dessa data uppfyller vissa villkor.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
exl-id: f0cd3a75-03ed-40a9-b336-8a782f3cfe69
feature: Rulesets
role: Admin,User,Developer
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 3%

---

# Använda regeluppsättningar för att omforma URL:er {#using-rulesets-to-transform-urls}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan distribuera regeluppsättningar i Dynamic Media för att omvandla URL:er. Regeluppsättningar är instruktioner skrivna i ett skriptspråk (t.ex. JavaScript) som utvärderar XML-data och utför vissa åtgärder om dessa data uppfyller vissa villkor. Varje regel består av minst ett villkor och minst en åtgärd. En regel utvärderar XML-data mot villkoren, och om ett villkor är uppfyllt utförs rätt åtgärd. Exempel på regeluppsättningar är följande:

* Lägga till ett MIME-typsuffix. Många tjänster och webbplatser kräver bildsuffix, som att lägga till `.jpg` till en URL.
* Skapa en mappsökväg till URL:en för sökmotoroptimering.

   Se [Hur Adobe Dynamic Media Classic stöder SEO](/help/assets/assets/s7_seo.pdf).

* Lägga till metadata i URL:en för sökmotoroptimering.

   Se [Hur Adobe Dynamic Media Classic stöder SEO](/help/assets/assets/s7_seo.pdf).

* Ställa in innehållets disposition för att utlösa en hämtning.
* Förenkla bildhanteringen genom att ange URL:er för personalisering. Till exempel: `rgb{XX,YY,ZZ}` i RTF-klart `\redXX\greenYY\blueZZ`

* Begär att vissa tecken ska kodas, till exempel `$`, `{`och `}`och vissa tecken som ska avkodas mot ImageServer. Facebook fungerar till exempel inte så bra med URL:er som innehåller specialtecken.

   Se [Ta bort specialtecken från URL-adresser](https://helpx.adobe.com/experience-manager/scene7/kb/base/scene7-rulesets/remove-special-characters-urls.html).

I Dynamic Media-sammanhang kan webbplatser som använder ett XML-baserat system för att hantera resursinformation överföra XML-filer till Dynamic Media. Du kan ange en av dessa filer som förbearbetningsregeluppsättningsfil för Dynamic Media-resurser. Den här filen omstrukturerar URL-protokollets standardformat så att det uppfyller affärslogiken i system som integreras med Dynamic Media. Du anger en XML-fil som ska fungera som sökväg till definitionsfilen för regeluppsättningen.

>[!CAUTION]
>
>Var försiktig när du använder linjaler. kan de förhindra att Dynamic Media-innehåll visas på din webbplats.

Det finns exempellinjaler som kan hjälpa dig att skapa en egen linjaluppsättning.\
Se [Referens för regeluppsättning](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/rule-set-reference/c-rule-set-reference.html).

Precis som när du skapar alla regeluppsättningar måste du se till att XML-filen är giltig innan du överför den med ett XML-valideringsprogram som xmlvalid.\
Se även [Felsökningsregeluppsättningar](https://helpx.adobe.com/experience-manager/scene7/kb/base/scene7-rulesets/scene7-ruleset-troubleshooting.html).

Kontrollera också först att du testar regeluppsättningen i en staging-miljö som inte påverkar produktionsmiljön.\
Produktionsmiljöer och staging-miljöer kräver normalt olika inloggningar.

Se [Adobe Dynamic Media Classic-datorprogram för inloggningsinformation](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#sign-in-dmc-app).

<!-- * **NA staging environment** login page: [https://s7sps1-staging.scene7.com/IpsWeb/](https://s7sps1-staging.scene7.com/IpsWeb/)
* **EMEA staging environment** login page: [https://s7sps3-staging.scene7.com/IpsWeb/](https://s7sps3-staging.scene7.com/IpsWeb/)
* **JAPAC staging environment** login page: [https://s7sps5-staging.scene7.com/IpsWeb/](https://s7sps5-staging.scene7.com/IpsWeb/) -->

Se även [Använda&quot;resurs&quot; i stället för&quot;is&quot;-bild i en regeluppsättning](https://helpx.adobe.com/experience-manager/scene7/kb/base/scene7-rulesets/ruleset-asset-instead-image.html).

**Så här distribuerar du XML-regeluppsättningar:**

1. Logga in på [Dynamic Media Classic desktop application](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#sign-in-dmc-app).

   Dina autentiseringsuppgifter och din inloggning tillhandahölls av Adobe vid tidpunkten för etableringen. Om du inte har den här informationen kontaktar du teknisk support.

1. Överför regeluppsättningsfilen genom att göra följande:

   * Klicka på i fältet Global navigering **[!UICONTROL Upload]**.
   * På **[!UICONTROL Upload]** sida, nära det övre vänstra hörnet, klicka **[!UICONTROL Browse]**.
   * I **[!UICONTROL Open]** bläddra till regeluppsättningsfilen (XML).
   * Markera filen och klicka sedan på **[!UICONTROL Open]**.
   * Till höger på sidan **[!UICONTROL Upload]** väljer du en målmapp för regeluppsättningsfilen.
   * Långt ned på sidan ser du till att **[!UICONTROL Publish After Uploading]** är markerad.
   * Klicka på längst ned till höger på sidan **[!UICONTROL Submit Upload]**.
   * Klicka på i fältet Global navigering **[!UICONTROL Jobs]** för att kontrollera överföringsjobbets status. När **[!UICONTROL Status]** kolumn på **[!UICONTROL Job]** fortsätter sidan till nästa steg.

1. Klicka på i navigeringsfältet uppe på sidan **[!UICONTROL Setup > Application Setup > Publish Setup > Image Server]**.
1. På sidan **[!UICONTROL Image Server Publish]**, under gruppen **[!UICONTROL Catalog Management]**, letar du upp **[!UICONTROL Rule Set Definition File Path]** och klickar sedan på **[!UICONTROL Select]**.
1. På sidan **[!UICONTROL Select Rule Set Definition File (XML)]** bläddrar du till regeluppsättningsfilen och klickar sedan på **[!UICONTROL Select]** i den nedre högra hörnet av sidan.
1. Klicka på i det nedre högra hörnet på sidan Inställningar **[!UICONTROL Close]**.
1. Kör ett Image Server-publiceringsjobb.

   Regeluppsättningsvillkoren tillämpas på begäranden till Dynamic Media Image-servrar.

   Om du gör ändringar i regeluppsättningsfilen tillämpas ändringarna omedelbart när du överför och publicerar den uppdaterade regeluppsättningsfilen igen.
