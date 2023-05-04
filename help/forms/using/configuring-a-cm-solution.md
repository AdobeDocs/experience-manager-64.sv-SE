---
title: Konfigurera en Correspondence Management-lösning
seo-title: Configuring a Correspondence Management solution
description: Lär dig hur du definierar en URL för en författarinstans för återställning av författarinstansversion och definierar publiceringsinstansens URL för aktiveringshanteraren för den offentliga instansen.
seo-description: Learn how to define an author instance URL for the author instance version restore and define the Publish instance URL for public instance activation manager.
uuid: 76b25004-fe47-44d7-9bed-7c0fd963306b
topic-tags: correspondence-management
content-type: reference
products: SG_EXPERIENCEMANAGER/6.3/FORMS
discoiquuid: 186ca75c-638b-4057-826e-cd5d56aa0397
feature: Correspondence Management
exl-id: a062957d-a526-4c4b-bbc5-0cda8ab007a3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Konfigurera en Correspondence Management-lösning {#configuring-a-correspondence-management-solution}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Definiera författarinstansens URL för VersionRestoreManagerImpl {#defining-author-instance-url-for-versionrestoremanagerimpl}

Följ de här stegen för att definiera en URL för författarinstansen för återställning av författarinstansversion:

1. Gå till *https://:&lt;publishhost>:&lt;publishport>/lc/system/console/configMgr*. Logga in med autentiseringsuppgifter för OSGi Management Console. Standardautentiseringsuppgifterna är admin/admin.
1. Sök och klicka på **[!UICONTROL Edit]** -ikonen bredvid **[!UICONTROL com.adobe.livecycle.content.activate.impl.VersionRestoreManagerImpl.name]** inställning.
1. I **[!UICONTROL VersionRestoreManager Author URL]** anger du URL:en till författarinstansen av VersionRestoreManager.

   **URL-sträng**:

   `https://<hostname>:<port>:/libs/fd/fdm/content/crud/lc.content.remote.activate.VersionRestoreManager`

   >[!NOTE]
   >
   >Om det finns flera författarinstanser (grupperade) som föregås av en belastningsutjämnare anger du URL:en till belastningsutjämnaren i dialogrutan **[!UICONTROL VersionRestoreManager Author URL]** fält.

1. Klicka på **[!UICONTROL Save]**.

## Definiera publiceringsinstansens URL för ActivationManagerImpl (hanteraren för aktivering av offentlig instans) {#defining-the-publish-instance-url-for-activationmanagerimpl-public-instance-activation-manager}

Följ de här stegen för att definiera publiceringsinstansens URL för aktiveringshanteraren för den offentliga instansen:

1. Gå till *https://:&lt;authorhost>:&lt;authorport>/lc/system/console/configMgr*. Logga in med autentiseringsuppgifter för OSGi Management Console. Standardautentiseringsuppgifterna är admin/admin.
1. Sök och klicka på **[!UICONTROL Edit]** -ikonen bredvid **[!UICONTROL com.adobe.livecycle.content.activate.impl.ActivationManagerImpl.name]** inställning.
1. I **[!UICONTROL ActivationManager Publish URL]** anger du URL:en för åtkomst till Publish-instansen ActivationManager. Du kan ange följande URL:er.

   * **URL för belastningsutjämnare (rekommenderas)**: Ange URL för belastningsutjämnare om du har en webbserver som fungerar som belastningsutjämnare framför publiceringsservergruppen (flera icke-klustrade publiceringsinstanser).
   * **Publicera instans-URL**: Ange en URL för publiceringsinstans. Om du har en enda publiceringsinstans eller webbservern där publiceringsgruppen finns är den inte tillgänglig från författarmiljön på grund av begränsningar. Om den angivna publiceringsinstansen är nere finns det en reservmekanism att hantera på författarsidan.
   * **URL-sträng**:

      `https://<hostname>:<port>:/libs/fd/fdm/content/crud/lc.content.remote.activate.activationManager`

1. Klicka på **[!UICONTROL Save]**.

Mer information om hur du konfigurerar Correspondence Management finns i [Egenskaper för konfiguration av korrespondenshantering](https://helpx.adobe.com/aem-forms/6-2/cm-configuration-properties.html).
