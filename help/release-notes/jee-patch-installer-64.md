---
title: AEM Forms JEE Patch Installer
description: AEM Forms JEE Patch Installer
uuid: e709871b-c04c-43bb-a7d0-45e89fbd3d44
content-type: reference
discoiquuid: 83bace08-1d4f-4192-a634-c7c4879963d8
exl-id: ce5300ce-03f4-4e7b-bc5b-01a9968ebe06
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 0%

---

# AEM Forms JEE Patch Installer {#aem-forms-jee-patch-installer}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>[Kontakta supporten](https://www.adobe.com/account/sign-in.supportportal.html) för mer information eller för att få plåstret.

## Om installationsprogrammet för korrigeringsfilen {#about-the-patch-installer}

Installationsprogrammet för AEM 6.4 Forms JEE patch innehåller alla åtgärdade fel för alla komponenter i AEM 6.4 Forms JEE som är tillgängliga till dess att den här korrigeringen släppts. Se de senaste  [Versionsinformation om ackumulerat korrigeringspaket](cfp-release-notes.md) för en fullständig lista över åtgärdade problem.

## Krav för att installera korrigeringen {#prerequisites-to-installing-the-patch}

* AEM 6.4 Forms

## Installera och konfigurera korrigeringen {#installing-and-configuring-the-patch}

1. Säkerhetskopiera &lt;*AEM_forms_root*>/distribuera mapp. Det krävs om du bestämmer dig för att avinstallera snabbkorrigeringen.
1. Stoppa programservern.
1. Extrahera arkivfilen för patch-installationsprogrammet till hårddisken.
1. I katalogen som namnges enligt det operativsystem som du använder:

   * **Windows**
Navigera till rätt katalog på installationsmediet eller mappen på hårddisken där du kopierade installationsprogrammet och dubbelklicka på 
`aemforms64_cfp_install.exe` -fil.

      * (32-bitars Windows) `Windows\Disk1\InstData\VM`
      * (64-bitars Windows) `Windows_64Bit`\ `Disk1\InstData\VM`
   * **Linux, Solaris, AIX**
Navigera till rätt katalog och skriv i en kommandotolk 
`./aem64_cfp_install.bin`.

      * (Linux) `Linux/Disk1/InstData/NoVM`
      * (Solaris) `Solaris/Disk1/InstData/NoVM`
      * (AIX)

         ```
         AIX/Disk1/InstData/VM
         ```
   Då startas en installationsguide som vägleder dig genom installationen.

1. På introduktionspanelen klickar du på **[!UICONTROL Next]**.
1. Kontrollera att den standardplats som visas är korrekt för din befintliga installation på skärmen Välj installationsmapp, eller klicka på **[!UICONTROL Browse]** för att välja en alternativ mapp där AEM är installerad och klicka på **[!UICONTROL Next]**.

1. Läs Quick Fix Patch Summary-informationen och klicka på **[!UICONTROL Next]**.
1. Läs mer i Sammanfattning av förinstallation och klicka på **[!UICONTROL Install]**.
1. När installationen är klar klickar du på **[!UICONTROL Next]**så att snabbkorrigeringsuppdateringarna kan tillämpas på dina installerade filer.
1. [Endast Windows] Utför något av följande steg:

   * Avmarkera alternativet Starta Configuration Manager innan du klickar på Klar. Kör Configuration Manager senare med `ConfigurationManager.bat` filen finns i `[aem-forms root]\configurationManager\bin`. Använda `ConfigurationManager.bat` hjälper dig att undvika att uppdatera namn på axel.jar-namn i .lax-filer manuellt
   * Avmarkera alternativet Starta Configuration Manager innan du klickar på Klar. Innan du kör konfigurationshanteraren med **ConfigurationManager.exe** eller **ConfigurationManager_IPv6.exe**, navigera till *&lt;aemforms_install_dir>\configurationManager\bin* katalog och uppdatering **axis.jar** till **axis-1.4.1.1.jar** i följande filer:

      * ConfigurationManager.lax
      * ConfigurationManager_IPv6.lax

1. (Endast Unix-baserad) Kryssrutan Starta Configuration Manager är markerad som standard. Klicka **[!UICONTROL Done]** för att köra Configuration Manager.

   Om du vill köra Configuration Manager senare avmarkerar du alternativet Starta Configuration Manager innan du klickar på Klar. Du kan starta Configuration Manager senare med rätt skript i `[AEM_forms_root]/configurationManager/bin` katalog.

1. Beroende på programservern väljer du ett av följande dokument och följer instruktionerna i *Konfigurera och distribuera AEM formulär* -avsnitt.

   * [Installera och distribuera AEM formulär för JBoss](http://www.adobe.com/go/learn_aemforms_installJBoss_64)
   * [Installera och distribuera AEM formulär för WebSphere](http://www.adobe.com/go/learn_aemforms_installWebSphere_64)
   * [Installera och distribuera AEM för WebLogic](http://www.adobe.com/go/learn_aemforms_installWebLogic_64)

1. (Endast JBoss) När du har installerat korrigeringen och konfigurerat servern tar du bort tmp och arbetskataloger för JBoss-programservern.

## Konfigurationer efter distributionen {#post-deployment-configurations}

### SAML-konfigurationer {#saml-configurations}

Om du har konfigurerat SAML-autentisering och har problem med stora IDP-metadata gör du följande när du har installerat korrigeringen:

1. Ange följande systemegenskap på programservern:\
   `um.saml.enable.large.xml=true`

1. Starta om servern.
1. Ta bort befintliga SAML-autentiseringsproviders och lägg till dem igen för befintliga domäner enligt beskrivningen i SAML-inställningarna.

## Påverkade moduler {#impacted-modules}

* Dokumenttjänster
* Dokumentsäkerhet
* Foundation JEE
* PDFG-tjänst

[Kontakta supporten](https://www.adobe.com/account/sign-in.supportportal.html)
