---
title: Aktivera bilagor för ett HTML5-formulär
seo-title: Enabling attachments for an HTML5 form
description: Som standard är bilagesupport för HTML5-formulär inaktiverat.
seo-description: By default, the attachment support for HTML5 forms is disabled.
uuid: 2c62ac3e-4b27-46c7-a61d-a805fb5d26fb
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 8eebfcd6-0597-44ed-b718-bf9a1baa6c12
feature: Mobile Forms
exl-id: 82a843c4-5cb2-4f5e-ad4d-cf2e9ea6cdb8
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# Aktivera bilagor för ett HTML5-formulär {#enabling-attachments-for-an-html-form}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan överföra, förhandsgranska och skicka bilagor med HTML5-formulär. Som standard är stöd för bifogade filer inaktiverat. Så här aktiverar du stöd för bifogade filer:

1. Skapa en [egen profil](/help/forms/using/custom-profile.md) with multiselect string property `mfAttachmentOptions`.
1. Ange egenskaper i den anpassade profilen `fileSizeLimit`, `multiSelect`och `buttonTex`det om du vill konfigurera alternativ för widgeten för bifogade filer. Om det behövs kan du även ange fler anpassade egenskaper.

1. Använd följande konfigurationer i den anpassade profilen:

   * **multiSelect** -> true eller false (true som standard)
   * **fileSizeLimit** -> value_in_mb (say 5) (2 MB som standard)
   * **buttonText** -> Knapptext för popup-fönster (&quot;Bifoga&quot; som standard)
   * **acceptera** -> filtyper som ska accepteras (&quot;audio/&amp;ast;, video/&amp;ast;, image/&amp;ast;, text/&amp;ast;, .pdf&quot; som standard)

   >[!NOTE]
   >
   >I Microsoft Internet Explorer 9 kan användare bifoga filer som är större än den angivna gränsen. Det är ett känt problem.

1. Använd [metadataredigerare](/help/forms/using/manage-form-metadata.md) för att välja den anpassade profil som du har skapat ovan för formulär i HTML 5.
1. Rendera formulärmallen med en anpassad profil och ikonen för bilagor visas i formulärverktygsfältet.

   >[!NOTE]
   >
   >Formulärportalen har en anpassad profil med funktioner för utkast och bilagor aktiverade. Mer information om **Spara som utkast** profil, se [Spara HTML5-formulär som utkast](/help/forms/using/saving-html5-form-draft.md).

1. Klicka på ikonen för bifogade filer, så visas en dialogruta för val av bifogade filer. Bläddra och markera den bifogade filen och klicka på **Bifoga**.

   >[!NOTE]
   >
   >Om du vill förhandsgranska en bifogad fil klickar du på namnet på den bifogade filen.

   >[!NOTE]
   >
   >Filförhandsvisningsalternativet är inte tillgängligt för anonyma användare.

## Bifogad filinlämningsformat {#attachment-submission-format}

När bilagor är aktiverade skickar HTML5-formuläret multipart-data. Flerdelsdata har två delar **dataXml** och **bilagor**.

>[!NOTE]
>
>För bakåtkompatibilitet, om `mfAllowAttachments`om alternativet är inaktiverat, skickar inte HTML5-formulären multipart-data. Det skickar enkel data xml i **application/xml** format.

Om flaggan mfAllowAttachments är aktiverad visas [skicka tjänstproxytjänst](/help/forms/using/service-proxy.md) skickar också multipart-data med dataXml och bilagor.
