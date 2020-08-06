---
title: Innehållsfragment – ta bort överväganden
seo-title: Innehållsfragment – ta bort överväganden
description: Innehållsfragment – ta bort överväganden
seo-description: Innehållsfragment – ta bort överväganden
uuid: b4161a0e-7e17-4547-9bdd-cf3b1d0d7d63
contentOwner: aheimoz
topic-tags: content-fragments
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: eaf65bdd-9091-4985-90bd-5eb2148965e3
translation-type: tm+mt
source-git-commit: 3fa80e73fb6e9400fbeba29d80aa57e080b6f333
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 12%

---


# Innehållsfragment – ta bort överväganden {#content-fragments-delete-considerations}

>[!CAUTION]
>
>Vissa funktioner för innehållsfragment kräver att [AEM 6.4 Service Pack 2 (6.4.2.0) eller senare](/help/release-notes/sp-release-notes.md)används.

## Behörigheter - ta bort eller inte ta bort {#permissions-delete-or-not-delete}

Möjligheten att ta bort innehåll är kraftfull, men potentiellt känslig, och många branscher måste begränsa och styra hur dessa behörigheter distribueras.

När det gäller borttagningsbehörigheter måste innehållsfragment beaktas på två nivåer:

1. **Innehållsfragmentet som en enskild enhet.**

   * **Användningsfall**: En användare som behöver redigera/uppdatera ett innehållsfragment - **och ta bort ett helt fragment**.
   * **Behörigheter**: Behörigheten [Ta bort](/help/sites-administering/security.md#actions) kan [tilldelas via användar- och/eller grupphantering](/help/sites-administering/security.md#managing-permissions).

1. **De flera underenheter som utgör ett innehållsfragment. till exempel variationer, undernoder.**

   Den grundläggande åtgärden i redigeraren för innehållsfragment kräver att sådana tillfälliga underelement kan tas bort. t.ex. vid manipulering av variationer, även när du redigerar metadata eller hanterar associerat innehåll.

   * **Användningsfall**: En användare som behöver redigera/uppdatera ett innehållsfragment - **utan att kunna ta bort ett helt fragment**.
   * **Behörigheter**: Se [Behörigheter krävs endast](content-fragments-delete.md#permissions-required-for-editor-functionality-only)för redigeringsfunktionen.

>[!NOTE]
>
>When a user does not have any [Delete](/help/sites-administering/security.md#actions) permissions, the Content Fragment editor operates in *read-only* mode.

>[!NOTE]
>
>Se även [Granska åtgärder för användarhantering i AEM](/help/sites-administering/audit-user-management-operations.md).

## Behörigheter krävs endast för redigeringsfunktionen {#permissions-required-for-editor-functionality-only}

Användare som behöver redigera/uppdatera ett innehållsfragment, **utan att kunna ta bort ett helt fragment**, måste tilldelas specifika behörigheter, eftersom grundläggande användning av redigeraren för innehållsfragment kräver att tillfälliga underelement kan tas bort.

t.ex. vid manipulering av variationer, även när du redigerar metadata eller hanterar associerat innehåll.

>[!NOTE]
>
>De borttagningsbehörigheter som krävs för att redigera/uppdatera ett innehållsfragment ingår i borttagningsbehörigheten som [tilldelats via användar- och/eller grupphantering](/help/sites-administering/security.md#managing-permissions).

Behörigheterna som behövs för att redigera/uppdatera ett fragment måste tillämpas på antingen noden som innehåller innehållsfragmentet eller på en lämplig överordnad nod (på alla nivåer under `/content/dam`). När den tilldelas till en sådan överordnad nod tillämpas behörigheterna på alla noder i den grenen.

En mapp som till exempel kommer att innehålla alla innehållsfragment, till exempel:

* `/content/dam/contentfragments`

>[!CAUTION]
>
>Det går också att ange behörigheter för `/content/dam` eftersom alla innehållsfragment lagras här.
>
>Den här åtgärden tillämpar dock samma borttagningsbehörigheter på *alla* andra resurstyper.

Behörigheten som krävs för att en viss användare och/eller grupp ska kunna redigera/uppdatera ett innehållsfragment är:

>[!NOTE]
>
>I den här listan visas alla behörigheter som krävs, inte bara borttagningsbehörighet.

* För noderna eller mapparna för innehållsfragment:

   * `jcr:addChildNodes`, `jcr:modifyProperties`

* För noden `jcr:content` för alla innehållsfragment:

   * `jcr:addChildNodes`, `jcr:modifyProperties` och `jcr:removeChildNodes`

* För alla noder under `jcr:content` alla innehållsfragment:

   * `jcr:addChildNodes`, `jcr:modifyProperties` och `jcr:removeChildNodes`, `jcr:removeNode`

Dessa `remove` behörigheter måste [administreras via åtkomstkontrollistor i CRXDE Lite](/help/sites-administering/user-group-ac-admin.md#access-right-management).

Behörigheterna `add` och `modify` behörigheterna kan också administreras i CRXDE Lite eller med konsolen för användarhantering.

Definitionen av en grupps `remove` behörigheter `content-authors-no-delete`:

![cf-delete-03](assets/cf-delete-03.png)

