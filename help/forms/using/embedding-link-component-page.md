---
title: Bädda in länkkomponent på en sida
seo-title: Embedding link component in a page
description: Du kan använda länkkomponenten för att länka ett adaptivt dokument eller ett adaptivt formulär från vilken sida som helst.
seo-description: You can use the link component to link an adaptive document or an adaptive form from any page.
uuid: fde56b5f-634c-406f-a026-875f972f7c8f
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: publish
discoiquuid: a4a36e73-3f7a-4173-8807-931f26daa35a
exl-id: eb816a35-0773-4eda-95b2-1d351c71be8b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 0%

---

# Bädda in länkkomponent på en sida{#embedding-link-component-in-a-page}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Förutsättningar {#prerequisites}

Länkkomponenten är medlem i kategorin Dokumenttjänster. Kontrollera att kategorin Dokumenttjänster är synlig i AEM. Om kategorin inte finns med i listan följer du de steg som anges på [Aktivera komponenterna i formulärportalen](/help/forms/using/enabling-forms-portal-components.md).

## Länkkomponent {#link-component}

Med länkkomponenten kan formulärportalförfattare skapa en länk till ett anpassat formulär var som helst på en sida. Komponenten Link är tillgänglig i avsnittet Document Services i komponentwebbläsaren.

Utför följande steg för att lägga till en länkkomponent på sidan:

1. Dra **Länk** på sidan. Markera komponenten och tryck på ![cmppr](assets/cmppr.png). Dialogrutan Redigera länkkomponent öppnas.

   ![edit-link-component](assets/edit-link-component.png)

1. I **Visa** anger du följande:

   * **Länkbeskrivning**: Länka text eller bildtext för länken.
   * **Länkverktygstips**: Verktygstips för länken.
   * **Layoutmall**: Mall för layout för länkkomponenten.

1. Öppna **Resursinformation** och ange resursens typ. En resurs kan vara en **formulär**. Beroende på vilken typ av resurs som valts visas alternativen nedan:

   * **Resurssökväg**: Databassökväg där resursen lagras.
   * **Återgivningstyp**: Återgivningsformatet PDF, HTML eller Auto. Återgivningstypen Auto identifierar användarmiljön och återger formuläret som HTML eller PDF. Om formuläret till exempel nås från en mobil enhet återges formuläret i HTML av återgivningstypen Auto.
   * **Skicka URL:**  URL till den server där formulärdata skickas.
   * **HTML-profil**: Profil för att återge formuläret som HTML.
   * **PDF-profil**: Profil för återgivning av formuläret som PDF-dokument.

1. Öppna **Avancerat** -fliken. Du kan ange ytterligare parametrar i nyckelvärdepar-formatet. När användaren klickar på länken skickas dessa ytterligare parametrar tillsammans med formuläret.

   Tryck **Klar** för att spara konfigurationen.

## Bästa tillvägagångssätt för att använda länkkomponenten {#best-practices-for-using-link-component-br}

* Se till att du väljer PDF som återgivningstyp om den sökväg som anges i Formulärsökväg pekar på ett dokument som har PDF som tillåtet återgivningsformat.
* Skicka-URL för ett formulär kan anges på flera ställen och prioritetsordningen är följande:

   1. Skicka-URL som är inbäddad i formuläret (med Skicka-knappen) har högsta prioritet.
   1. Skicka-URL som nämns i Forms Manager har medelhög prioritet.
   1. Överförings-URL som anges i formulärportalen har lägst prioritet.
