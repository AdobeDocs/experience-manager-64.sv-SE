---
title: AEM Forms JEE Patch Installer
description: AEM Forms JEE Patch Installer
uuid: e709871b-c04c-43bb-a7d0-45e89fbd3d44
content-type: reference
discoiquuid: 83bace08-1d4f-4192-a634-c7c4879963d8
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---


# AEM Forms JEE Patch Installer {#aem-forms-jee-patch-installer}

>[!NOTE]
>
>[Kontakta ](https://www.adobe.com/account/sign-in.supportportal.html) supporten om du vill ha mer information eller vill få korrigeringen.

## Om installationsprogrammet för korrigeringsfilen {#about-the-patch-installer}

Installationsprogrammet för AEM 6.4 Forms JEE patch innehåller alla åtgärdade problem för alla komponenter i AEM 6.4 Forms JEE som är tillgängliga till dess att den här korrigeringen släppts. I den senaste [Versionsinformationen om Cumulative Fix Pack](cfp-release-notes.md) finns en fullständig lista över åtgärdade problem.

## Krav för att installera korrigeringen {#prerequisites-to-installing-the-patch}

* AEM 6.4 Forms

## Installera och konfigurera korrigeringen {#installing-and-configuring-the-patch}

1. Säkerhetskopiera mappen &lt;*AEM_forms_root*/deploy. Det krävs om du bestämmer dig för att avinstallera snabbkorrigeringen.
1. Stoppa programservern.
1. Extrahera arkivfilen för patch-installationsprogrammet till hårddisken.
1. I katalogen som namnges enligt det operativsystem som du använder:

   * ****
WindowsNavigera till rätt katalog på installationsmediet eller mappen på hårddisken där du kopierade installationsprogrammet och dubbelklicka på 
`aemforms64_cfp_install.exe` -fil.

      * (32-bitars Windows) `Windows\Disk1\InstData\VM`
      * (64-bitars Windows) `Windows_64Bit`\ `Disk1\InstData\VM`
   * **Linux, Solaris,**
AIXNavigate to the appropriate directory, and from a command prompt, type 
`./aem64_cfp_install.bin`.

      * (Linux) `Linux/Disk1/InstData/NoVM`
      * (Solaris) `Solaris/Disk1/InstData/NoVM`
      * (AIX)

         ```
         AIX/Disk1/InstData/VM
         ```
   Då startas en installationsguide som vägleder dig genom installationen.

1. Klicka på **[!UICONTROL Next]** på introduktionspanelen.
1. På skärmen Välj installationsmapp kontrollerar du att den standardplats som visas är korrekt för den befintliga installationen, eller klickar på **[!UICONTROL Browse]** och väljer den alternativa mapp där AEM formulär är installerade. Klicka sedan på **[!UICONTROL Next]**.

1. Läs Quick Fix Patch Summary-informationen och klicka på **[!UICONTROL Next]**.
1. Läs informationen i Sammanfattning av förinstallation och klicka på **[!UICONTROL Install]**.
1. När installationen är klar klickar du på **[!UICONTROL Next]**för att snabbkorrigera de installerade filerna.
1. [Windows ] endastUtför något av följande steg:

   * Avmarkera alternativet Starta Configuration Manager innan du klickar på Klar. Kör Configuration Manager senare med filen `ConfigurationManager.bat` som finns i `[aem-forms root]\configurationManager\bin`. Med `ConfigurationManager.bat` slipper du uppdatera namn på axel.jar i .lax-filer manuellt
   * Avmarkera alternativet Starta Configuration Manager innan du klickar på Klar. Innan du kör konfigurationshanteraren med **ConfigurationManager.exe** eller **ConfigurationManager_IPv6.exe** går du till *&lt;AEMForms_Install_Dir>\configurationManager\bin*-katalog och uppdaterar **axis.jar** till **axis-1.4.1.1.1.1.1.1.1.1.1 .jar** i följande filer:

      * ConfigurationManager.lax
      * ConfigurationManager_IPv6.lax

1. (Endast Unix-baserad) Kryssrutan Starta Configuration Manager är markerad som standard. Klicka på **[!UICONTROL Done]** för att köra Configuration Manager.

   Om du vill köra Configuration Manager senare avmarkerar du alternativet Starta Configuration Manager innan du klickar på Klar. Du kan starta Configuration Manager senare med lämpligt skript i katalogen `[AEM_forms_root]/configurationManager/bin`.

1. Beroende på vilken programserver du använder väljer du ett av följande dokument och följer instruktionerna i *Konfigurera och distribuera AEM*-avsnittet.

   * [Installera och distribuera AEM formulär för JBoss](http://www.adobe.com/go/learn_aemforms_installJBoss_64)
   * [Installera och distribuera AEM formulär för WebSphere](http://www.adobe.com/go/learn_aemforms_installWebSphere_64)
   * [Installera och distribuera AEM för WebLogic](http://www.adobe.com/go/learn_aemforms_installWebLogic_64)

1. (Endast JBoss) När du har installerat korrigeringen och konfigurerat servern tar du bort tmp och arbetskataloger för JBoss-programservern.

## Konfigurationer efter distribution {#post-deployment-configurations}

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
