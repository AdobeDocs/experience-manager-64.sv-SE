---
title: Omstrukturering av formulärarkiv i AEM 6.4
seo-title: Omstrukturering av formulärarkiv i AEM 6.4
description: Lär dig hur du gör de ändringar som krävs för att migrera till den nya databasstrukturen i AEM 6.4 for Forms.
seo-description: Lär dig hur du gör de ändringar som krävs för att migrera till den nya databasstrukturen i AEM 6.4 for Forms.
uuid: e60830d4-23ca-4be9-941a-ee4abe4786a6
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
discoiquuid: 1ce9a622-5968-407f-a74b-d325a2bff669
translation-type: tm+mt
source-git-commit: 7b39a715166eeefdf20eb22a4449068ff1ed0e42

---


# Omstrukturering av formulärarkiv i AEM 6.4{#forms-repository-restructuring-in-aem}

Som beskrivs på den överordnade [databasomstruktureringen på sidan AEM 6.4](/help/sites-deploying/repository-restructuring.md) bör kunder som uppgraderar till AEM 6.4 använda den här sidan för att bedöma arbetsinsatsen i samband med databasändringar som påverkar AEM Forms-lösningen. Vissa ändringar kräver arbete under uppgraderingsprocessen för AEM 6.4, medan andra kan skjutas upp till en uppgradering av version 6.5.

**Med 6.4-uppgradering**

* [Diverse](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#misc)

**Före 6.5-uppgradering**

* [Konfiguration av EchoSign-molntjänst](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#echosign-cloud-service-configuration)
* [Recaptcha Cloud-tjänstkonfigurationer](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#recaptcha-cloud-service-configurations)
* [Konfigurationer av Typekit Cloud-tjänster](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#typekit-cloud-service-configurations)
* [Diverse](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md#misc)

## Med 6.4-uppgradering {#with-upgrade}

### Diverse {#misc}

| **Föregående plats** | `/etc/clientlibs/fd/fp` |
|---|---|
| **Ny plats(er)** | `/libs/fd/fp/components` |
| **Omstruktureringsvägledning** | Alla explicita referenser i anpassad kod till den äldre platsen måste uppdateras till den nya platsen. |
| **Anteckningar** | Dessa klientbibliotek får inte ändras eller utökas. |

| **Föregående plats** | `/etc/clientlibs/fd/rte` |
|---|---|
| **Ny plats(er)** | `/libs/fd/rte` |
| **Omstruktureringsvägledning** | För resurser i klientlibs som kan refereras med absoluta sökvägar måste du använda nyare sökvägar i nya resurser. |
| **Anteckningar** | Ej tillämpligt |

| **Föregående plats** | `/etc/clientlibs/fd/af` |
|---|---|
| **Ny plats(er)** | `/libs/fd/af/authoring/clientlibs` |
| **Omstruktureringsvägledning** | För resurser i klientlibs som kan refereras med absoluta sökvägar måste du använda nyare sökvägar i nya resurser. |
| **Anteckningar** | Ej tillämpligt |

| **Föregående plats** | `/etc/clientlibs/fd/xfaforms` |
|---|---|
| **Ny plats(er)** | `/libs/fd/xfaforms/clientlibs/` |
| **Omstruktureringsvägledning** | För resurser i klientlibs som kan refereras med absoluta sökvägar måste du använda nyare sökvägar i nya resurser. |
| **Anteckningar** | Ej tillämpligt |

| **Föregående plats** | `/etc/clientlibs/fd/af` |
|---|---|
| **Ny plats(er)** | `/libs/fd/af/runtime/clientlibs` |
| **Omstruktureringsvägledning** | För resurser i klientlibs som kan refereras med absoluta sökvägar måste du använda nyare sökvägar i nya resurser. |
| **Anteckningar** | Ej tillämpligt |

| **Föregående plats** | `/etc/clientlibs/fd/af` |
|---|---|
| **Ny plats(er)** | `/libs/fd/af/runtime/clientlibs` |
| **Omstruktureringsvägledning** | För resurser i klientlibs som kan refereras med absoluta sökvägar måste du använda nyare sökvägar i nya resurser. |
| **Anteckningar** | Ej tillämpligt |

| **Föregående plats** | `/etc/clientlibs/fd/expeditor` |
|---|---|
| **Ny plats(er)** | `/libs/fd/expeditor/clientlibs` |
| **Omstruktureringsvägledning** | För resurser i klientlibs som kan refereras med absoluta sökvägar måste du använda nyare sökvägar i nya resurser. |
| **Anteckningar** | Ej tillämpligt |

| **Föregående plats** | `/etc/clientlibs/fd/fmaddon` |
|---|---|
| **Ny plats(er)** | `/libs/fd/fmaddon` |
| **Omstruktureringsvägledning** | Att ändra dessa klientlibs har aldrig rekommenderats eller fått stöd. Om du har gjort ändringar i dessa klientlibs bör de återställas till AEM-koden. |
| **Anteckningar** | Ej tillämpligt |

| **Föregående plats** | `/etc/aep` |
|---|---|
| **Ny plats(er)** | `/var/fd/content/annotations` |
| **Omstruktureringsvägledning** | Att ändra dessa klientlibs har aldrig rekommenderats eller fått stöd. Om du har gjort ändringar i dessa klientlibs bör de återställas till AEM-koden. |
| **Anteckningar** | Ej tillämpligt |

## Före 6.5-uppgradering {#prior-to-upgrade}

### Konfiguration av EchoSign-molntjänst {#echosign-cloud-service-configuration}

| **Föregående plats** | `/etc/cloudservices/echosign` |
|---|---|
| **Ny plats(er)** | `/conf/<tenant>/settings/cloudconfigs/echosign` |
| **Omstruktureringsvägledning** | Verktyget [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) som ska aktiveras från användargränssnittet för formulärmigrering. |
| **Anteckningar** | Ej tillämpligt |

### Recaptcha Cloud-tjänstkonfigurationer {#recaptcha-cloud-service-configurations}

| **Föregående plats** | `/etc/cloudservices/recaptcha` |
|---|---|
| **Ny plats(er)** | `/conf/<tenant>/settings/cloudconfigs/recaptcha` |
| **Omstruktureringsvägledning** | Verktyget [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) som ska aktiveras från användargränssnittet för formulärmigrering. |
| **Anteckningar** | Ej tillämpligt |

### Konfigurationer av Typekit Cloud-tjänster {#typekit-cloud-service-configurations}

| **Föregående plats** | `/etc/cloudservices/typekit` |
|---|---|
| **Ny plats(er)** | `/conf/<tenant>/settings/cloudconfigs/typekit` |
| **Omstruktureringsvägledning** | Verktyget [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) som ska aktiveras från användargränssnittet för formulärmigrering. |
| **Anteckningar** | Ej tillämpligt |

### Diverse {#misc-1}

| **Föregående plats** | `/etc/cloudservices/fdm` |
|---|---|
| **Ny plats(er)** | `/conf/<tenant>/settings/cloudconfigs/fdm` |
| **Omstruktureringsvägledning** | Verktyget [Lazy Content Migration](/help/sites-deploying/lazy-content-migration.md) som ska aktiveras från användargränssnittet för formulärmigrering. |
| **Anteckningar** | Ej tillämpligt |

| **Föregående plats** | `/etc/designs/fd/fp` |
|---|---|
| **Ny plats(er)** | `/libs/fd/fp` |
| **Omstruktureringsvägledning** | Alla referenser till mallarna /etc ska så småningom uppdateras så att de pekar på sina `/libs` motsvarigheter. |
| **Anteckningar** | Ej tillämpligt |

