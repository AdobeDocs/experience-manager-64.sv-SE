---
title: Loggfiler
seo-title: Loggfiler
description: Händelser som körnings- eller startfel registreras i programserverns loggfiler, som kan öppnas med valfri textredigerare.
seo-description: Händelser som körnings- eller startfel registreras i programserverns loggfiler, som kan öppnas med valfri textredigerare.
uuid: 6ed9fdcd-ff02-4b35-893f-09261a6a557a
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_aem_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: cf140483-470f-4bff-8870-304207508aab
translation-type: tm+mt
source-git-commit: d04e08e105bba2e6c92d93bcb58839f1b5307bd8

---


# Loggfiler {#log-files}

Händelser som körnings- eller startfel registreras i programserverns loggfiler. Om du har problem med att distribuera till programservern kan du använda loggfilerna för att hitta problemet. Du kan öppna loggfilerna med valfri textredigerare.

(JBoss) Följande loggfiler finns i `*[appserver root]*/server/*[server]*/log` katalogen:

* boot.log
* server.log.*[yyyy-mm-dd]*
* server.log

(WebLogic) Domänloggfiler finns i katalogen *[appserverdomain]* och serverloggfiler finns i katalogen *[appserverdomain]/servers/[appserver name]/logs *:

* access.log
* *[appserver name]*.log
* *[appserver name]*.out.*[inkrementellt tal]*

(WebSphere) Följande loggfiler finns i katalogen *[appserver root]*/profiles/default/logs/*[appserver name]* :

* SystemError.log
* SystemOut.log
* StartServer.log

