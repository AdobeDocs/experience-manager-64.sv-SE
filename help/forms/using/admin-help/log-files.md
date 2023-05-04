---
title: Loggfiler
seo-title: Log files
description: Händelser som körnings- eller startfel registreras i programserverns loggfiler, som kan öppnas med valfri textredigerare.
seo-description: Events such as run-time or startup errors are recorded to the application server log files, which can be  opened using any text editor.
uuid: 6ed9fdcd-ff02-4b35-893f-09261a6a557a
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_aem_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: cf140483-470f-4bff-8870-304207508aab
exl-id: acce13aa-864c-4999-be5c-6d49b99d5459
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 0%

---

# Loggfiler {#log-files}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Händelser som körnings- eller startfel registreras i programserverns loggfiler. Om du har problem med att distribuera till programservern kan du använda loggfilerna för att hitta problemet. Du kan öppna loggfilerna med valfri textredigerare.

(JBoss) Följande loggfiler finns i `*[appserver root]*/server/*[server]*/log` katalog:

* boot.log
* server.log.*[yyyy-mm-dd]*
* server.log

(WebLogic) Domänloggfiler finns i *[appserverdomain]* -katalogen och serverloggfilerna finns i *[appserverdomain]/servrar/[appserver name]/logs *katalog:

* access.log
* *[appserver name]*.log
* *[appserver name]*.out.*[inkrementellt tal]*

(WebSphere) Följande loggfiler finns i *[appserver root]*/profiles/default/logs/*[appserver name]* katalog:

* SystemErr.log
* SystemOut.log
* StartServer.log
