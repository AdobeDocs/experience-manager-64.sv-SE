---
title: Arbeta med formulär i AEM Forms-arbetsytan
seo-title: Arbeta med formulär i AEM Forms-arbetsytan
description: En formuläruppsättning är en samling HTML5-formulär som grupperats och presenteras som en enda formuläruppsättning för slutanvändarna. Lär dig hur du kan arbeta med formuläruppsättningar på arbetsytan i AEM Forms.
seo-description: En formuläruppsättning är en samling HTML5-formulär som grupperats och presenteras som en enda formuläruppsättning för slutanvändarna. Lär dig hur du kan arbeta med formuläruppsättningar på arbetsytan i AEM Forms.
uuid: 77f81465-bd60-4aee-8507-585fe08adb78
contentOwner: vishgupt
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: c1793e2e-413c-4b6f-b96b-09e011f06263
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Arbeta med formulär i AEM Forms-arbetsytan {#working-with-formsets-in-aem-forms-workspace}

En formuläruppsättning är en samling HTML5-formulär som grupperats och presenteras som en enda formuläruppsättning för slutanvändarna. När slutanvändarna börjar fylla i en formuläruppsättning, överförs de smidigt från ett formulär till ett annat. Formuläruppsättningen kan sedan skickas med bara ett klick. Mer information om formuläruppsättningar och hur du konfigurerar dem finns i [Formulär i AEM-formulär](/help/forms/using/formset-in-aem-forms.md).

Arbetsytan i AEM Forms har stöd för formatuppsättningar. Med formuläruppsättningar kan flera formulär som är kopplade till en tjänst eller process grupperas för att automatisera en affärsprocess och presenteras för slutanvändarna. I ett sådant scenario kan användarna fylla i hela uppsättningen som ett och det finns inget behov av att arkivera, skicka och spåra enskilda formulär eller processer.

## Koppla en formuläruppsättning till startpunkten i en AEM Forms-arbetsyteapp {#attaching-a-formset-to-startpoint-in-an-aem-forms-workspace-app-br}

1. Skapa affärsprocessarbetsflödet i Workbench. Mer information finns i [Workbench-hjälpen](https://www.adobe.com/go/learn_aemforms_workbench_63).
1. Välj **Använd en CRX-resurs** i Presentation &amp; Data i processegenskaperna för startpunkten.

   ![1-1](assets/1-1.png)

1. Klicka på ![Bläddra](assets/browse.png) (Bläddra) intill resurssökvägen för CRX. Dialogrutan Välj formulärresurs visas.

   ![2](assets/2.png)

1. Klicka på fliken **Formuläruppsättning** , markera den aktuella formuppsättningen i listan och klicka sedan på **OK**.

1. Distribuera programmet efter uppdatering av andra relevanta processegenskaper.

## Använda format på arbetsytan i AEM Forms {#using-formset-in-nbsp-aem-forms-workspace}

När ett formulär har kopplats till en startpunkt kan startpunkten anropas från arbetsytan i AEM Forms, precis som vilken startpunkt som helst.

De åtgärder som stöds för formulär via arbetsytan i AEM Forms är:

* Spara som utkast
* Lås
* Abandon
* Skicka
* Lägg till bifogade filer
* Lägg till anteckningar
* Flytta mellan formulär i en formuläruppsättning med knapparna Bakåt eller Nästa

![3-1](assets/3-1.png)

>[!NOTE]
>
>Om du vill förbättra prestandan när du flyttar från föregående och nästa formulär i en formuläruppsättning, ska du använda alla arbetsyteknappar (Bakåt, Nästa, Spara, Skicka och ... (Mer) inaktiveras tills det aktuella formuläret återges fullständigt.

