---
title: Kompatibilitetspaket
seo-title: Compatibility Package
description: 'Genom att installera kompatibilitetspaketet på AEM Forms 6.4 kan du använda Correspondence Management-resurser från AEM Forms 6.3 och inaktuella adaptiva formulärmallar och sidor. '
seo-description: Installing the Compatibility package on AEM Forms 6.4 allows you to use the Correspondence Management assets from AEM Forms 6.3 and deprecated adaptive forms templates and pages
uuid: e50b1ff9-c357-422a-8da8-a791ff805317
contentOwner: gtalwar
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management, installing
geptopics: SG_AEMFORMS/categories/jee
discoiquuid: 38a80992-2eda-4535-89af-0de34b1a9686
role: Admin
exl-id: 0bfa0e65-c4cd-4c37-b42b-bff1b777a7be
source-git-commit: e608249c3f95f44fdc14b100910fa11ffff5ee32
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 0%

---

# Installera kompatibilitetspaket {#compatibility-package}

Genom att installera kompatibilitetspaketet på AEM Forms 6.4 kan du använda Correspondence Management-resurser från AEM Forms 6.3 och inaktuella adaptiva formulärmallar och sidor.

## Översikt {#overview}

Interaktiv kommunikation är standardmetoden och rekommenderas för att skapa kundkommunikation i AEM Forms 6.4. Om du vill fortsätta använda bokstäverna från AEM 6.3 Forms och AEM 6.2 Forms måste du installera [AEMFD-kompatibilitetspaketet](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/forms-updates/aem-forms-releases.html).

Med AEMFD-kompatibilitetspaketet kan du använda följande resurser från AEM Forms 6.3 och 6.2 i AEM Forms 6.4:

* Dokumentfragment som skapats i AEM Forms 6.3 och 6.2
* Bokstäver
* Dataordlistor
* Mallar och sidor för anpassade formulär har tagits bort

Mer information finns i [Resurser som gjorts kompatibla med AEM Forms 6.4 genom att installera Kompatibilitetspaketet](/help/forms/using/compatibility-package.md#assetsmadecompatible).

## Lägg till stöd för AEM Forms 6.3- och 6.2-material i AEM Forms 6.4 {#add-support-for-aem-forms-and-assets-in-aem-forms}

När du har utfört en uppgradering gör du följande för att installera AEMFD-kompatibilitetspaketet och göra dina resurser kompatibla med 6.4:

Kontrollera att du har [AEM Kompatibilitetspaket](/help/sites-deploying/backward-compatibility.md) förinstallerat.

1. Installera [Kompatibilitetspaketet](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/forms-updates/aem-forms-releases.html).

   Mer information om hur du överför och installerar paketet finns i [Arbeta med paket](/help/sites-administering/package-manager.md).

1. Starta om servern när loggarna har stabiliserats.
1. Använd flyttningsverktyget för att göra dina resurser kompatibla med 6.4.

   Mer information finns i [migreringsverktyget](/help/forms/using/migration-utility.md).

## Resurser som gjorts kompatibla med AEM Forms 6.4 genom att installera kompatibilitetspaketet {#assetsmadecompatible}

Genom att installera Kompatibilitetspaketet kan du göra följande resurser och mallar kompatibla med AEM Forms 6.4:

* Correspondence Management Assets från AEM 6.3 och tidigare

   * [Bokstäver](/help/forms/using/create-letter.md)
   * [Dataordlistor](/help/forms/using/data-dictionary.md)
   * Dokumentfragment

* Mallar som inte längre används för anpassningsbara formulär

   * /libs/fd/af/templates/blankTemplate2
   * /libs/fd/af/templates/simpleEnrollmentTemplate
   * /libs/fd/af/templates/simpleEnrollmentTemplate2
   * /libs/fd/af/templates/surveyTemplate
   * /libs/fd/af/templates/surveyTemplate2
   * /libs/fd/af/templates/tabbedEnrollmentTemplate
   * /libs/fd/af/templates/tabbedEnrollmentTemplate2
   * /libs/fd/afaddon/templates/advancedEnrollmentTemplate
   * /libs/fd/afaddon/templates/advancedEnrollmentTemplate2

* Sidor med adaptiva formulär har tagits bort:

   * /libs/fd/af/components/page/survey
   * /libs/fd/af/components/page/tabbedenrollment
   * /libs/fd/afaddon/components/page/advancedRotering
