---
title: Tagga användargenererat innehåll
seo-title: Tagging User Generated Content
description: Taggning av användargenererat innehåll (UGC) är hur communitymedlemmar kan hjälpa andra medlemmar att söka efter innehåll
seo-description: Tagging of user generated content (UGC) is how community members can help other members search for content
uuid: ce125d7c-6fc1-44c7-9f67-eca6f599d8e3
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 1cc8ce66-2c03-44e4-9ddd-8d6944d85c99
role: Admin
exl-id: 834df392-df38-498c-9e2a-489484e20e0a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Tagga användargenererat innehåll {#tagging-user-generated-content}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

Taggning av användargenererat innehåll (UGC) är det sätt på vilket communitymedlemmar kan hjälpa andra medlemmar att söka efter innehåll.

Taggar används oftast av författare och administratörer i författarmiljön. Taggning av UGC är unik eftersom UGC-taggar används av communitymedlemmar i publiceringsmiljön.

Taggnamnutrymmen och taxonomier är samma för båda programmen.

## Funktioner i Communities {#communities-features}

AEM Communities-funktionerna som kan konfigureras för att tillåta taggning är

* [Blogg](blog-feature.md)
* [Kalender](calendar.md)
* [Filbibliotek](file-library.md)
* [Forum](forum.md#configuretheaddedforum)
* [Frågor och svar](working-with-qna.md)

## Administrera taggar {#administering-tags}

Se [Administrera taggar](../../help/sites-administering/tags.md#tagging-console) för att skapa och hantera taggnamnutrymmen och taxonomier.

Se [Tagg Essentials](tag.md) för utvecklarinformation.

Se [Använda molnet för sociala taggar](tagcloud.md) för att lägga till en komponent i Social Tag Cloud på en sida för att underlätta sökning efter publicerad UGC med de använda taggarna.

### Taggbehörigheter {#tag-permissions}

Standardbehörigheterna är inställda på att inte tillåta att taggnamnutrymmen kan läsas av alla i publiceringsmiljön.

Eftersom taggar används i UGC i publiceringsmiljön måste läsbehörighet aktiveras för communitymedlemmar för att de ska kunna markera taggar som ska användas.

Se [Ange taggbehörigheter](../../help/sites-administering/tags.md#setting-tag-permissions).

Så här visas det i CRXDE när en administratör tillämpar läsbehörigheter på `/etc/tag/discussions` för gruppen `*Community Engage Members*`.

![chlimage_1-74](assets/chlimage_1-74.png)
