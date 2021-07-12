---
title: Tagga användargenererat innehåll
seo-title: Tagga användargenererat innehåll
description: Taggning av användargenererat innehåll (UGC) är hur communitymedlemmar kan hjälpa andra medlemmar att söka efter innehåll
seo-description: Taggning av användargenererat innehåll (UGC) är hur communitymedlemmar kan hjälpa andra medlemmar att söka efter innehåll
uuid: ce125d7c-6fc1-44c7-9f67-eca6f599d8e3
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 1cc8ce66-2c03-44e4-9ddd-8d6944d85c99
role: Admin
exl-id: 834df392-df38-498c-9e2a-489484e20e0a
source-git-commit: 3c050c33a384d586d74bd641f7622989dc1d6b22
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# Tagga användargenererat innehåll {#tagging-user-generated-content}

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

Mer utvecklarinformation finns i [Tagga viktiga](tag.md).

Se [Använda molnet för sociala taggar](tagcloud.md) för att lägga till en komponent i molnet för sociala taggar på en sida för att underlätta sökning efter publicerad UGC med de taggar som används.

### Taggbehörigheter {#tag-permissions}

Standardbehörigheterna är inställda på att inte tillåta att taggnamnutrymmen kan läsas av alla i publiceringsmiljön.

Eftersom taggar används i UGC i publiceringsmiljön måste läsbehörighet aktiveras för communitymedlemmar för att de ska kunna markera taggar som ska användas.

Se [Ange taggbehörigheter](../../help/sites-administering/tags.md#setting-tag-permissions).

Så här visas det i CRXDE när en administratör tillämpar läsbehörigheter på `/etc/tag/discussions` för gruppen `*Community Engage Members*`.

![chlimage_1-74](assets/chlimage_1-74.png)
