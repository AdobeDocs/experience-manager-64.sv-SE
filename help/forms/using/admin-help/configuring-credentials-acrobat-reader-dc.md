---
title: Konfigurera autentiseringsuppgifter för användning med Acrobat Reader DC-tillägg
seo-title: Configuring credentials for use with Acrobat Reader DC extensions
description: Lär dig hur du konfigurerar autentiseringsuppgifter för användning med Acrobat Reader DC-tillägg.
seo-description: Learn how to configure credentials for use with Acrobat Reader DC extensions.
uuid: 9210e6c9-6f5c-402d-b355-b104cdffd5eb
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 5bb32fb1-4b6e-412f-aa16-f60db9dcaba1
exl-id: 40c2e205-0115-4ebe-ab24-66c8ee0663fa
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 0%

---

# Konfigurera autentiseringsuppgifter för användning med Acrobat Reader DC-tillägg{#configuring-credentials-for-use-with-acrobat-reader-dc-extensions}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Om du vill använda användningsbehörighet för PDF-dokument konfigurerar du AEM formulär med en giltig inloggningsinformation för Acrobat Reader DC-tillägg. En autentiseringsuppgift kan ha konfigurerats under installationen av AEM formulär. Om du inte konfigurerade dina autentiseringsuppgifter för Acrobat Reader DC-tillägg när du kör Configuration Manager, eller om du behöver importera en ny eller ersättande autentiseringsuppgift, kan du göra det med hjälp av sidorna Pålitlighetslagerhantering.

Om du använder en utvärderingsreferens ersätter du den med en produktionsautentiseringsuppgift när du flyttar till produktionsmiljön. Om du vill uppdatera en inloggningsinformation som har gått ut eller utvärdera den tar du först bort den gamla Acrobat Reader DC-tilläggsinformationen.

Mer information om hur du hämtar en inloggningsinformation finns i [Förbereder installation av AEM (Single Server)](https://www.adobe.com/go/learn_aemforms_prepareInstallsingle_63).

Trust Store kan innehålla fler än en Acrobat Reader DC-tilläggsreferens. Du måste ange en av dessa autentiseringsuppgifter som standardautentiseringsuppgifter för Reader Extensions. Standardautentiseringsuppgifterna används när en Workbench-användare inte kan avgöra vilka autentiseringsuppgifter som ska användas när processen skapas. Dessa regler gäller för standardautentiseringsuppgifter:

* Om du importerar en autentiseringsuppgift för Acrobat Reader DC-tillägg och Trust Store inte innehåller några andra autentiseringsuppgifter för Acrobat Reader DC-tillägg anges den som standard.
* Om du importerar en autentiseringsuppgift för Acrobat Reader DC-tillägg med standardalternativet markerat tas standardtypen bort från en befintlig standardautentiseringsuppgift. De importerade autentiseringsuppgifterna blir standard.
* Du kan inte ta bort en standardautentiseringsuppgift för Acrobat Reader DC-tillägg. Om du vill ta bort standardautentiseringsuppgifterna anger du först en annan autentiseringsuppgift som standard. Ett undantag till den här regeln är att om det bara finns en autentiseringsuppgift kan du ta bort den även om den är standard.
* Du kan inte uppdatera en standardautentiseringsuppgift för Acrobat Reader DC-tillägg.

>[!NOTE]
>
>Du kan också importera och ta bort autentiseringsuppgifter via programmering. (Se [Programmera med AEM](https://www.adobe.com/go/learn_aemforms_programming_63).)

## Importera autentiseringsuppgifter för Acrobat Reader DC-tillägg {#import-a-acrobat-reader-dc-extensions-credential}

1. I administrationskonsolen klickar du på Inställningar > Lita på arkivhantering > Lokala autentiseringsuppgifter.
1. Klicka på Importera och välj Acrobat Reader DC extensions Credential under Trust Store Type.
1. (Valfritt) Om du vill ange att den här autentiseringsuppgiften är standardautentiseringsuppgiften som används med Acrobat Reader DC-tillägg väljer du Standard.
1. Ange en identifierare för autentiseringsuppgifterna i rutan Alias. Den här identifieraren används som visningsnamn för autentiseringsuppgifterna i Acrobat Reader DC-tillägg. Det här aliaset används även för att få åtkomst till autentiseringsuppgifter via programmering med AEM formulär SDK.

   >[!NOTE]
   >
   >Aliasnamnet konverteras automatiskt till versaler för visning. Aliasnamnet är inte skiftlägeskänsligt när du refererar till det i en process.

1. Klicka på Välj fil för att leta upp autentiseringsuppgifterna, skriv lösenordet för autentiseringsuppgifterna och klicka sedan på OK.

   Om felmeddelandet&quot;Det gick inte att importera autentiseringsuppgifter på grund av felaktigt filformat eller felaktigt lösenord&quot; visas kontrollerar du att lösenordet är giltigt.

## Ta bort autentiseringsuppgifter för Acrobat Reader DC-tillägg {#remove-a-acrobat-reader-dc-extensions-credential}

1. I administrationskonsolen klickar du på Inställningar > Lita på arkivhantering > Lokala autentiseringsuppgifter.
1. Markera autentiseringsuppgifterna och klicka på Ta bort.

## Ersätta autentiseringsuppgifter för Acrobat Reader DC-tillägg {#replace-a-acrobat-reader-dc-extensions-credential}

1. I administrationskonsolen klickar du på Inställningar > Lita på arkivhantering > Lokala autentiseringsuppgifter.
1. Observera det befintliga autentiseringsuppgiftens alias, markera det och klicka på Ta bort.
1. Importera de nya autentiseringsuppgifterna med exakt samma aliasnamn.
