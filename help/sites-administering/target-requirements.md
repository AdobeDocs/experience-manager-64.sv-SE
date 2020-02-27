---
title: Krav för integrering med Adobe Target
seo-title: Krav för integrering med Adobe Target
description: Läs om förutsättningarna för integrering med Adobe Target.
seo-description: Läs om förutsättningarna för integrering med Adobe Target.
uuid: 88be6a97-c964-4e42-a3a2-ed9b2c9ee49e
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: a84fd0ab-0bcd-48cf-bba3-fb29308fa0f8
translation-type: tm+mt
source-git-commit: 152f60a7c9579d89cca5dc326679dc5a08d4dd5f

---


# Krav för integrering med Adobe Target{#prerequisites-for-integrating-with-adobe-target}

Som en del av [integreringen av AEM och Adobe Target](/help/sites-administering/target.md)måste du registrera dig hos Adobe Target, konfigurera replikeringsagenten och säkra aktivitetsinställningar på publiceringsnoden.

## Registrering med Adobe Target {#registering-with-adobe-target}

För att kunna integrera AEM med Adobe Target måste du ha ett giltigt Adobe Target-konto. Det här kontot måste minst ha **godkännare **nivå-behörigheter. När du registrerar dig hos Adobe Target får du en klientkod. Du behöver klientkoden och inloggningsnamnet och lösenordet för Adobe Target för att ansluta AEM till Adobe Target.

Klientkoden identifierar Adobe Target-kundkontot när Adobe Target-servern anropas.

>[!NOTE]
>
>Ditt konto måste också aktiveras av Target-teamet för att integreringen ska kunna användas.
>
>
>Om så inte är fallet, kontakta kundtjänst [för](https://marketing.adobe.com/resources/help/en_US/target/target/r_problem.html)Adobe Target.

## Aktivera målreplikeringsagenten {#enabling-the-target-replication-agent}

Test- och Target- [replikeringsagenten](/help/sites-deploying/replication.md) måste vara aktiverad på författarinstansen. Observera att den här replikeringsagenten inte är aktiverad som standard om du använde körningsläget för [nosamplingsinnehåll](/help/sites-deploying/configure-runmodes.md#using-samplecontent-and-nosamplecontent) för att installera AEM. Mer information om hur du skyddar din produktionsmiljö finns i [Säkerhetschecklistan](/help/sites-administering/security-checklist.md).

1. På AEM-startsidan klickar eller trycker du på **Verktyg** > **Distribution** > **Replikering**.
1. Klicka eller tryck på **Agents On Author**.
1. Klicka på eller tryck på replikeringsagenten för **Test och Target (test och target)** och klicka eller tryck sedan på **Redigera**.
1. Välj alternativet Aktiverad och klicka eller tryck sedan på **OK**.

   >[!NOTE]
   >
   >När du konfigurerar replikeringsagenten Test och Target, på fliken **Transport** , anges URI som standard till **tnt:///**. Ersätt inte denna URI med **https://admin.testandtarget.omniture.com**.
   >
   >Observera att om du försöker testa anslutningen med **tnt:///** genereras ett fel. Detta är förväntat eftersom denna URI endast är avsedd för internt bruk och inte ska användas med **Test Connection**.

## Skydda noden Aktivitetsinställningar {#securing-the-activity-settings-node}

Du måste skydda aktivitetsinställningsnoden **cq:ActivitySettings** i publiceringsinstansen så att den inte är tillgänglig för vanliga användare. Noden för aktivitetsinställningar ska endast vara tillgänglig för tjänsten som hanterar aktivitetssynkroniseringen till Adobe Target.

**Noden** cq:ActivitySettings`/content/campaigns/*nameofbrand*` finns i CRXDE-klassen under *** under aktivitetsnoden jcr:content; *till exempel `/content/campaign/we-retail/master/myactivity/jcr:content/cq:ActivitySettings`. Den här noden skapas bara efter att du har angett en komponent som mål.

Noden **cq:ActivitySettings** under aktivitetens jcr:content skyddas av följande åtkomstkontrollistor:

* Neka alla för alla
* Tillåt jcr:read,rep:write för&quot;target-activity-authors&quot; (författaren är medlem i den här gruppen utanför rutan)
* Tillåt jcr:read,rep:write för &quot;target service&quot;

Dessa inställningar ser till att normala användare inte har tillgång till nodegenskaperna. Använd samma åtkomstkontrollista vid författare och publicering. Mer information finns i [Användaradministration och -säkerhet](/help/sites-administering/security.md) .

## Konfigurera AEM-externalizer {#configuring-the-aem-externalizer}

När du redigerar en aktivitet i Adobe Target pekar URL:en mot **localhost** såvida du inte ändrar URL:en på AEM-författarnoden.

Så här konfigurerar du AEM-externalizer:

1. Gå till OSGi-webbkonsolen på **https://&lt;server>:&lt;port>/system/console/configMgr.**
1. Hitta **Day CQ Link Externalizer** och ange författarnodens domän.

   ![chlimage_1-120](assets/chlimage_1-120.png)

