---
title: Konfigurerar e-post
seo-title: Configuring Email
description: E-postkonfiguration för Communities
seo-description: Email configuration for Communities
uuid: e8422cc2-1594-43b0-b587-82825636cec1
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: b4d38e45-eaa0-4ace-a885-a2e84fdfd5a1
pagetitle: Configuring Email
role: Admin
exl-id: 0a0222e7-ca30-4603-94ad-582005b2de11
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 1%

---

# Konfigurerar e-post {#configuring-email}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

AEM Communities använder e-post för

* [Communities-meddelanden](notifications.md)
* [Communities-prenumerationer](subscriptions.md)

E-postfunktionen fungerar inte som standard eftersom den kräver en specifikation av en SMTP-server och en SMTP-användare.

>[!CAUTION]
>
>E-post för meddelanden och prenumerationer får endast konfigureras på [primär utgivare](deploy-communities.md#primary-publisher).

## Standardkonfiguration för e-posttjänst {#default-mail-service-configuration}

Standardtjänsten för e-post krävs för både meddelanden och prenumerationer.

* På den primära utgivaren
* Inloggad med administratörsbehörighet
* Öppna [Webbkonsol](../../help/sites-deploying/configuring-osgi.md)

   * Till exempel: [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* Leta reda på `Day CQ Mail Service`
* Markera redigeringsikonen

Detta baseras på dokumentationen till [Konfigurerar e-postmeddelande](../../help/sites-administering/notification.md), men med en skillnad i det fältet `"From" address` är *not* krävs och ska lämnas tom.

Till exempel (ifylld med värden endast för illustrationsändamål):

![chlimage_1-98](assets/chlimage_1-98.png)

* **[!UICONTROL SMTP server host name]**: *(obligatoriskt)* SMTP-servern som ska användas.

* **[!UICONTROL SMTP server port]** *(obligatoriskt)* SMTP-serverporten måste vara 25 eller högre.

* **[!UICONTROL SMTP user]**: *(obligatoriskt)* SMTP-användaren.

* **[!UICONTROL SMTP password]**: *(obligatoriskt)* SMTP-användarens lösenord.

* **[!UICONTROL "From" address]**: Lämna tomt
* **[!UICONTROL SMTP use SSL]**: Om det här alternativet är markerat skickas säker e-post. Kontrollera att porten är inställd på 465 eller som krävs för SMTP-servern.
* **[!UICONTROL Debug email]**: Om det här alternativet är markerat aktiveras loggning av SMTP-serverinteraktioner.

## AEM Communities e-postkonfiguration {#aem-communities-email-configuration}

När [standardtjänst för e-post](#default-mail-service-configuration) är konfigurerad, de två befintliga instanserna av `AEM Communities Email Reply Configuration` OSGi-konfigurationen, som ingår i versionen, blir funktionell.

Endast prenumerationsinstansen behöver konfigureras ytterligare när svar tillåts via e-post.

1. ` [email](#configuration-for-notifications)` instance

   för meddelanden, som inte har stöd för e-post med svar, och som inte ska ändras

1. ` [subscriptions-email](#configuration-for-subscriptions)` instance

   kräver konfiguration för att fullständigt aktivera skapande av post från svars-e-post

Så här når du instanserna för webbgruppskonfigurationen:

* På den primära utgivaren
* Inloggad med administratörsbehörighet
* Öppna [Webbkonsol](../../help/sites-deploying/configuring-osgi.md)

   * Till exempel: [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* Sök `AEM Communities Email Reply Configuration`

![chlimage_1-99](assets/chlimage_1-99.png)

### Konfiguration för meddelanden {#configuration-for-notifications}

Instansen av `AEM Communities Email Reply Configuration` OSGi-konfigurationen med e-postadressen Name är avsedd för meddelandefunktionen. Den här funktionen inkluderar inte e-postsvar.

Den här konfigurationen bör inte ändras.

* Leta reda på `AEM Communities Email Reply Configuration`
* Markera redigeringsikonen
* Verifiera **Namn** är `email`

* Verifiera **Skapa inlägg från svarsmejl** är `unchecked`

![chlimage_1-100](assets/chlimage_1-100.png)

### Konfiguration för prenumerationer {#configuration-for-subscriptions}

För webbgruppsprenumerationer är det möjligt att aktivera eller inaktivera möjligheten för en medlem att publicera innehåll genom att svara på ett e-postmeddelande.

* Leta reda på `AEM Communities Email Reply Configuration`
* Markera redigeringsikonen
* Verifiera **Namn** är `subscriptions-email`

![chlimage_1-101](assets/chlimage_1-101.png)

* **[!UICONTROL Name]** : *(obligatoriskt)* `subscriptions-email`. Redigera inte.

* **[!UICONTROL Create post from reply email]**: Om det här alternativet är markerat kan den som tar emot e-postprenumerationen posta innehåll genom att skicka ett svar. Standard är markerat.
* **[!UICONTROL Add tracked id to header]**: Standard är `Reply-To`.

* **[!UICONTROL Maximum length of Subject]**: Om spårar-ID läggs till på ämnesraden är detta den maximala längden för motivet, exklusive spårade ID, efter vilken det trimmas. Observera att detta bör vara så litet som möjligt för att undvika att spårad ID-information går förlorad. Standardvärdet är 200.
* **[!UICONTROL Email "From" address]**: *(obligatoriskt)* Adress som e-postmeddelanden ska levereras från. Troligen samma **SMTP-användare** har angetts för [standardtjänst för e-post](#configuredefaultmailservice). Standard är `no-reply@example.com`.

* **[!UICONTROL Reply-to-Delimiter]**: Om spårar-ID läggs till i svarshuvudet används den här avgränsaren. Standard är `+` (plustecken).

* **[!UICONTROL Tracker Id prefix in subject]**: Om spårar-ID läggs till på ämnesraden används det här prefixet. Standard är `post#`.

* **[!UICONTROL Tracker id prefix in message body]**: Om spårar-ID läggs till i meddelandetexten används det här prefixet. Standard är `Please do not remove this:`.

* **[!UICONTROL Email as HTML]**: Om det här alternativet är markerat anges innehållstypen för e-post som `"text/html;charset=utf-8"`. Standard är markerat.

* **[!UICONTROL Default user name]**: Det här namnet används för användare utan namn. Standard är `no-reply@example.com`.

* **[!UICONTROL Templates root path]**: E-postmeddelandet skapas med en mall som lagras på den här rotsökvägen. Standard är `/etc/community/templates/subscriptions-email`.

## Konfigurera avsökningsimporteraren {#configure-polling-importer}

För att e-postmeddelandet ska kunna hämtas till databasen måste du konfigurera en avsökningsimportör och konfigurera dess egenskaper i databasen manuellt.

### Lägg till ny avsökningsimportör {#add-new-polling-importer}

* På den primära utgivaren
* Inloggad med administratörsbehörighet
* Bläddra till avsökningsimportkonsolen.. [http://localhost:4503/etc/importers/polling.html](http://localhost:4503/etc/importers/polling.html)
* Välj **[!UICONTROL Add]**

![chlimage_1-102](assets/chlimage_1-102.png)

* **[!UICONTROL Type]**: *(obligatoriskt)* Dra ned för att välja `POP3 (over SSL).`

* **[!UICONTROL URL]**: *(obligatoriskt)* Servern för utgående e-post. Till exempel, `pop.gmail.com:995/INBOX?username=community-emailgmail.com&password=****`

* **[!UICONTROL Import to Path]**&amp;ast;: *(obligatoriskt)* Ange till `/content/usergenerated/mailFolder/postEmails`
genom att gå till 
`postEmails`mapp och markera **OK**

* **[!UICONTROL Update Interval in Seconds]**: *(valfritt)* E-postservern som konfigurerats för standardtjänsten för e-post kan ha krav på uppdateringsintervallvärdet. Gmail kan till exempel kräva ett intervall av `300`.

* **[!UICONTROL Login]**: *(valfritt)*

* **[!UICONTROL Password]**: *(valfritt)*

* Välj **[!UICONTROL OK]**

### Justera protokoll för ny avsökningsimportör {#adjust-protocol-for-new-polling-importer}

När den nya avsökningskonfigurationen har sparats är det nödvändigt att ändra egenskaperna för prenumerationens e-postimporterare ytterligare för att ändra protokollet från `POP3` till `emailreply`

Använda [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* På den primära utgivaren
* Inloggad med administratörsbehörighet
* Bläddra till [https://&lt;server>:&lt;port>/crx/de/index.jsp#/etc/importer/polling](http://localhost:4503/crx/de/index.jsp#/etc/importers/polling)
* Välj den nya konfigurationen
* Ändra följande egenskaper

   * **feedType**: ersätt `pop3s` med **`emailreply`**
   * **källa**: ersätta källans protokoll `pop3s://` med **`emailreply://`**

![chlimage_1-103](assets/chlimage_1-103.png)

De röda trianglarna anger de ändrade egenskaperna. Spara ändringarna:

* Välj **[!UICONTROL Save All]**
