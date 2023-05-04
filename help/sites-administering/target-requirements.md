---
title: Krav för integrering med Adobe Target
seo-title: Prerequisites for Integrating with Adobe Target
description: Läs om förutsättningarna för integrering med Adobe Target.
seo-description: Find out about the prerequisites for integrating with Adobe Target.
uuid: 88be6a97-c964-4e42-a3a2-ed9b2c9ee49e
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: a84fd0ab-0bcd-48cf-bba3-fb29308fa0f8
exl-id: f47e5c6a-ed52-4493-83bd-73e5e693d117
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# Krav för integrering med Adobe Target{#prerequisites-for-integrating-with-adobe-target}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Som en del av [integrering av AEM och Adobe Target](/help/sites-administering/target.md)måste du registrera dig hos Adobe Target, konfigurera replikeringsagenten och säkra aktivitetsinställningar på publiceringsnoden.

## Registrering hos Adobe Target {#registering-with-adobe-target}

För att kunna integrera AEM med Adobe Target måste du ha ett giltigt Adobe Target-konto. Det här kontot måste minst ha **godkännare **nivå-behörigheter. När du registrerar dig hos Adobe Target får du en klientkod. Du behöver klientkoden och inloggningsnamnet och lösenordet för Adobe Target för att kunna ansluta AEM till Adobe Target.

Klientkoden identifierar Adobe Target-kundkontot när Adobe Target-servern anropas.

>[!NOTE]
>
>Ditt konto måste också aktiveras av Target-teamet för att integreringen ska kunna användas.
>
>
>Om så inte är fallet, kontakta [Adobe Target kundtjänst](https://experienceleague.adobe.com/docs/target/using/cmp-resources-and-contact-information.html).

## Aktivera målreplikeringsagenten {#enabling-the-target-replication-agent}

Test och Target [replikeringsagent](/help/sites-deploying/replication.md) måste vara aktiverat på författarinstansen. Observera att den här replikeringsagenten inte är aktiverad som standard om du använde [nosamplingContent](/help/sites-deploying/configure-runmodes.md#using-samplecontent-and-nosamplecontent) körningsläge för installation av AEM. Mer information om hur du skyddar din produktionsmiljö finns i [Säkerhetschecklista](/help/sites-administering/security-checklist.md).

1. På AEM startsida klickar du på **verktyg** > **Distribution** > **Replikering**.
1. Klicka eller tryck **Agenter på författare**.
1. Klicka eller tryck på **Test och Target (test och target)** replikeringsagent och klicka eller tryck sedan på **Redigera**.
1. Välj alternativet Aktiverad och klicka eller tryck sedan på **OK**.

   >[!NOTE]
   >
   >När du konfigurerar replikeringsagenten Test och Target finns det i **Transport** -tabben, anges URI som standard till **tnt:///**. Ersätt inte denna URI med **https://admin.testandtarget.omniture.com**.
   >
   >Observera att om du försöker testa anslutningen med **tnt:///**, genereras ett fel. Detta är förväntat eftersom denna URI endast är avsedd för internt bruk och inte ska användas med **Testanslutning**.

## Skydda noden Aktivitetsinställningar {#securing-the-activity-settings-node}

Du måste skydda noden för aktivitetsinställningar **cq:ActivitySettings** på publiceringsinstansen så att den inte är tillgänglig för vanliga användare. Noden för aktivitetsinställningar ska bara vara tillgänglig för tjänsten som hanterar aktivitetssynkroniseringen till Adobe Target.

The **cq:ActivitySettings** noden är tillgänglig i CRXDE lite under `/content/campaigns/*nameofbrand*`* *under aktiviteterna jcr:content node;* *till exempel `/content/campaign/we-retail/master/myactivity/jcr:content/cq:ActivitySettings`. Den här noden skapas bara efter att du har angett en komponent som mål.

The **cq:ActivitySettings** nod under aktivitetens jcr:innehåll skyddas av följande åtkomstkontrollistor:

* Neka alla för alla
* Tillåt jcr:read,rep:write för&quot;target-activity-authors&quot; (författaren är medlem i den här gruppen utanför rutan)
* Tillåt jcr:read,rep:write för &quot;target service&quot;

Dessa inställningar ser till att normala användare inte har tillgång till nodegenskaperna. Använd samma åtkomstkontrollista vid författare och publicering. Se [Användaradministration och -säkerhet](/help/sites-administering/security.md) för mer information.

## Konfigurera AEM externaliserare {#configuring-the-aem-externalizer}

När du redigerar en aktivitet i Adobe Target pekar URL:en på **localhost** såvida du inte ändrar URL:en på AEM författarnod.

Så här konfigurerar du AEM externalizer:

1. Navigera till OSGi-webbkonsolen på **https://&lt;server>:&lt;port>/system/console/configMgr.**
1. Sök **Day CQ Link Externalizer** och ange författarnodens domän.

   ![chlimage_1-120](assets/chlimage_1-120.png)
