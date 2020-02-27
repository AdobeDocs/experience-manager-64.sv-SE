---
title: Referens för arbetsflödessteg
seo-title: Referens för arbetsflödessteg
description: 'null'
seo-description: 'null'
uuid: 72a64495-d1b1-49e7-8257-d6b2ed36961c
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: 25f0e0f7-9570-4748-81cb-ccec6492c0b4
translation-type: tm+mt
source-git-commit: 1ebe1e871767605dd4295429c3d0b4de4dd66939

---


# Referens för arbetsflödessteg{#workflow-step-reference}

Arbetsflödesmodeller består av en serie steg av olika typer. Beroende på typ kan dessa steg konfigureras och utökas med parametrar och skript för att ge den funktionalitet och kontroll som du behöver.

>[!NOTE]
>
>I det här avsnittet beskrivs de vanliga arbetsflödesstegen.
>
>För modulspecifika steg, se även:
>
>* [Stegreferens för arbetsflöde för AEM Forms](/help/forms/using/aem-forms-workflow-step-reference.md)
>* [Bearbeta resurser med mediehanterare och arbetsflöden](/help/assets/media-handlers.md)
>



## Stegegenskaper {#step-properties}

Varje stegkomponent har en dialogruta för **[!UICONTROL stegegenskaper]** där du kan definiera och redigera de egenskaper som behövs.

### Stegegenskaper - fliken Allmänt {#step-properties-common-tab}

En kombination av följande egenskaper är tillgängliga för de flesta arbetsflödesstegkomponenter på fliken **[!UICONTROL Allmänt]** i dialogrutan Egenskaper:

* **[!UICONTROL Titel]**

   Stegets titel.

* **[!UICONTROL Beskrivning]**

   En beskrivning av steget.

* **[!UICONTROL Arbetsflödesfas]**

   En nedrullningsbar väljare som använder en [scen](/help/sites-developing/workflows.md#workflow-stages) i steget.

* **[!UICONTROL Timeout]**

   Den period efter vilken steget&quot;har gått ut&quot;.

   Du kan välja mellan: **[!UICONTROL Av]**, **[!UICONTROL Omedelbar]**, **[!UICONTROL 1h]**, **[!UICONTROL 6h]**, **[!UICONTROL 12h]******,¥24h¥.

* **[!UICONTROL Timeout-hanterare]**

   Den hanterare som ska styra arbetsflödet när steget går ut; till exempel:

   `Auto Advancer`

* **[!UICONTROL Avancerad hanterare]**

   Välj det här alternativet om du vill att arbetsflödet automatiskt ska gå vidare till nästa steg efter körningen. Om du inte väljer det här alternativet måste implementeringsskriptet hantera arbetsflödets utveckling.

#### Stegegenskaper - fliken Användare/grupp {#step-properties-user-group-tab}

Följande egenskaper är tillgängliga för många arbetsflödesstegkomponenter på fliken **[!UICONTROL Användare/grupp]** i dialogrutan Egenskaper:

* **[!UICONTROL Meddela användare via e-post]**

   * Du kan meddela deltagare genom att skicka ett e-postmeddelande när arbetsflödet når steget.
   * Om det här alternativet är aktiverat skickas ett e-postmeddelande till den användare som definieras av egenskapen **[!UICONTROL Användare/grupp]** eller till varje medlem i gruppen om en grupp har definierats.

* **[!UICONTROL Användare/grupp]**

   * I en listruta kan du navigera och välja en användare eller grupp.
   * Om du tilldelar ett steg till en viss användare kan bara den här användaren utföra en åtgärd på steget.
   * Om du tilldelar steget till en hel grupp kommer alla användare i gruppen att få åtgärden i sin **[!UICONTROL arbetsflödesinkorg]** när arbetsflödet når det här steget.
   * Mer information finns i [Delta i arbetsflöden](/help/sites-authoring/workflows-participating.md) .

## OCH dela {#and-split}

Med **[!UICONTROL OCH Dela]** skapas en delning i arbetsflödet, varefter båda grenarna blir aktiva. Du kan lägga till arbetsflödessteg i varje gren efter behov. I det här steget kan du införa flera bearbetningssökvägar i arbetsflödet. Du kan t.ex. tillåta att vissa granskningssteg utförs parallellt, vilket sparar tid.

![wf-26](assets/wf-26.png)

### AND Split - Configuration {#and-split-configuration}

* Redigera **[!UICONTROL OCH dela]** -egenskaperna:

   * **[!UICONTROL Delningsnamn]**: Ange ett namn för förklarande ändamål.
   * Ange antalet filialer som krävs. 2, 3, 4 eller 5.

* Lägg till arbetsflödessteg i grenarna efter behov.

   ![wf-27](assets/wf-27.png)

## Behållarsteg {#container-step}

Ett **[!UICONTROL behållarsteg]** startar en annan arbetsflödesmodell som körs som ett underordnat arbetsflöde.

Med den här **[!UICONTROL behållaren]]**kan du återanvända arbetsflödesmodeller för att implementera vanliga stegsekvenser. En arbetsflödesmodell för översättning kan till exempel användas i flera redigeringsarbetsflöden.

![wf-28](assets/wf-28.png)

### Behållarsteg - konfiguration {#container-step-configuration}

Om du vill konfigurera steget redigerar du och använder följande flikar:

* [**[!UICONTROL Vanliga]**](#step-properties-common-tab)
* **[!UICONTROL Behållare]**

   * **[!UICONTROL Delarbetsflöde]**: Välj arbetsflödet som ska startas.

## Gå till steg {#goto-step}

Med **[!UICONTROL Gå till steg]** kan du ange nästa steg i arbetsflödesmodellen som ska köras, beroende på resultatet av ett ECMAScript:

* `true`: Gå-steget **** slutförs och arbetsflödesmotorn kör det angivna steget.

* `false`: Stegsteget **** Gå till slutförs och den normala routningslogiken avgör nästa steg som ska köras.

Med **[!UICONTROL Gå till steg]** kan du implementera avancerade routningsstrukturer i dina arbetsflödesmodeller. Om du till exempel vill implementera en slinga kan du definiera **[!UICONTROL Gå till steg]** så att ett föregående steg körs i arbetsflödet, där skriptet utvärderar ett slingvillkor.

### Gå till steg - konfiguration {#goto-step-configuration}

Om du vill konfigurera steget redigerar du och använder följande flikar:

* [**[!UICONTROL Vanliga]**](#step-properties-common-tab)
* **[!UICONTROL Process]**

   * **[!UICONTROL Stegen att gå till]]**: Välj det steg som ska köras.
   * **[!UICONTROL Skriptsökväg]**: Sökvägen till ECMAScript som avgör om **[!UICONTROL Goto Step]** ska köras eller inte.
   * **[!UICONTROL Skript]**: Det ECMAScript som avgör om **[!UICONTROL Goto Step]** ska köras.

>[!CAUTION]
>
>Ange antingen **[!UICONTROL skriptsökvägen]** eller **[!UICONTROL skriptet]**. Båda alternativen kan inte användas samtidigt. Om du anger värden för båda egenskaperna används **[!UICONTROL skriptsökvägen]** i steget.

#### Simulera en for-slinga {#simulating-a-for-loop}

När du simulerar en for-slinga måste du behålla antalet upprepningar av slingor som har inträffat:

* Antalet representerar vanligtvis ett index med objekt som hanteras i arbetsflödet.
* Antalet utvärderas som avslutningskriterier för slingan.

Om du till exempel vill implementera ett arbetsflöde som utför en åtgärd på flera JCR-noder kan du använda en loopräknare som index för noderna. Om du vill behålla antalet lagrar du ett `integer` värde i datamappningen för arbetsflödesinstansen. Använd skriptet för **[!UICONTROL Gå till steg]** om du vill öka antalet samt jämföra antalet med avslutningskriterierna.

```
function check(){
   var count=0;
   var keyname="loopcount"
   try{
      if (workflowData.getMetaDataMap().containsKey(keyname)){ 
        log.info("goto script: found loopcount key");
        count= parseInt(workflowData.getMetaDataMap().get(keyname))+1;
      } 
 
     workflowData.getMetaDataMap().put(keyname,count);
 
     }catch(err) {
         log.info(err.message);
         return false;
    }
   if (parseInt(count) <7){
       return true;
   } else {
      return false;
   }
}
```

## ELLER Dela {#or-split}

Med **[!UICONTROL ELLER Dela]** skapas en delning i arbetsflödet, varefter endast en gren är aktiv. I det här steget kan du lägga in sökvägar för villkorlig bearbetning i arbetsflödet. Du kan lägga till arbetsflödessteg i varje gren efter behov.

>[!NOTE]
>
>Mer information om hur du skapar en OR-delning finns i: [https://helpx.adobe.com/experience-manager/using/aem64_workflow_servlet.html](https://helpx.adobe.com/experience-manager/using/aem64_workflow_servlet.html)

![wf-29](assets/wf-29.png)

### Eller delad - konfiguration {#or-split-configuration}

* Redigera egenskaperna **[!UICONTROL ELLER Dela]** :

   * **[!UICONTROL Vanliga]**

      * Ange antalet filialer som krävs. 2, 3, 4 eller 5.
   * **[!UICONTROL Gren:*x*>]**

      * **[!UICONTROL Skriptsökväg]**: Sökvägen till en fil som innehåller skriptet.
      * **[!UICONTROL Skript]**: Lägg till skriptet i rutan.
      * **[!UICONTROL Standardflöde]**: Standardförgreningen följs när flera förgreningar utvärderas som true. Du kan bara ange en gren som standard.
   >[!NOTE]
   >
   >Det finns en separat flik för varje gren:
   >
   >* Skriptet för varje gren utvärderas en i taget.
   >* Förgreningarna utvärderas från vänster till höger.
   >* Det första skriptet som utvärderas till true körs.
   >* Om ingen gren utvärderas till true, går arbetsflödet inte framåt.


   >[!CAUTION]
   >
   >Ange antingen **[!UICONTROL skriptsökvägen]** eller **[!UICONTROL skriptet]**. Båda alternativen kan inte användas samtidigt. Om du anger värden för båda egenskaperna används **[!UICONTROL skriptsökvägen]** i steget.

   >[!NOTE]
   >
   >Se [Definiera en regel för en OR-delning](/help/sites-developing/workflows-models.md#example-defining-a-rule-for-an-or-split).

* Lägg till arbetsflödessteg i grenarna efter behov.

## Deltagarsteg och väljare {#participant-steps-and-choosers}

### Deltagarsteg {#participant-step}

Med ett **[!UICONTROL deltagarsteg]** kan du tilldela ägarskap för en viss åtgärd. Arbetsflödet fortsätter bara när användaren har bekräftat steget manuellt. Detta används när du vill att någon ska vidta en åtgärd i arbetsflödet; till exempel ett granskningssteg.

Även om det inte är direkt relaterat måste användarauktorisering beaktas när en åtgärd tilldelas. användaren måste ha åtkomst till sidan som är arbetsflödets nyttolast.

#### Deltagarsteg - konfiguration {#participant-step-configuration}

Om du vill konfigurera steget redigerar du och använder följande flikar:

* [**[!UICONTROL Vanliga]**](#step-properties-common-tab)
* [**[!UICONTROL Användare/grupp]**](#step-properties-user-group-tab)

>[!NOTE]
>
>Arbetsflödesinitieraren meddelas alltid när:
>
>* Arbetsflödet är slutfört (färdigt).
>* Arbetsflödet avbryts (avslutas).
>



>[!NOTE]
>
>Vissa egenskaper måste konfigureras för att e-postmeddelanden ska kunna aktiveras. Du kan också anpassa e-postmallen eller lägga till en e-postmall för ett nytt språk. Se [Konfigurera e-postmeddelanden](/help/sites-administering/notification.md) för att konfigurera e-postmeddelanden i AEM.

### Steg för dialogdeltagare {#dialog-participant-step}

Använd ett **[!UICONTROL dialogdeltagarsteg]** för att samla in information från användaren som är tilldelad arbetsposten. Det här steget är användbart när du vill samla in små mängder data som används senare i arbetsflödet.

När du är klar med steget innehåller dialogrutan **[!UICONTROL Fullständig arbetsuppgift]** de fält som du har definierat i dialogrutan. De data som samlas in i fälten lagras i noder i arbetsflödets nyttolast. Efterföljande arbetsflödessteg kan sedan läsa värdet från databasen.

Om du vill konfigurera steget anger du vilken grupp eller användare som arbetsposten ska tilldelas till och sökvägen till dialogrutan.

#### Steg för dialogdeltagare - konfiguration {#dialog-participant-step-configuration}

Om du vill konfigurera steget redigerar du och använder följande flikar:

* [**[!UICONTROL Vanliga]**](#step-properties-common-tab)
* [**[!UICONTROL Användare/grupp]**](#step-properties-user-group-tab)
* **[!UICONTROL Dialog]**

   * **[!UICONTROL-dialogsökväg**: Sökvägen till dialognoden i den [dialogruta som du skapar](#dialog-participant-step-creating-a-dialog).

#### Steg för dialogdeltagare - Skapa en dialogruta{#dialog-participant-step-creating-a-dialog}

Så här skapar du en dialogruta:

* Bestäm var de resulterande data ska [lagras i nyttolasten](#dialog-participant-step-storing-data-in-the-payload).
* [Definiera dialogrutan. Detta innefattar att definiera de fält som används för att samla in (och spara) data](#dialog-participant-step-dialog-definition).

#### Steg för dialogdeltagare - lagra data i nyttolasten {#dialog-participant-step-storing-data-in-the-payload}

Du kan lagra widgetdata i arbetsflödets nyttolast eller i arbetsobjektets metadata. Formatet för widgetnodens egenskap avgör var data lagras. `name` Det är den här noden.

* **[!UICONTROL Lagra data med nyttolasten]**

   * Om du vill lagra widgetdata som en egenskap för arbetsflödets nyttolast använder du följande format för värdet för namnegenskapen för widgetnoden:

      `./jcr:content/nodename`

   * Data lagras i nyttolastnodens `nodename` egenskap. Om noden inte innehåller den egenskapen skapas egenskapen.
   * När den lagras med nyttolasten skriver efterföljande användning av dialogrutan med samma nyttolast över egenskapens värde.

* **[!UICONTROL Lagra data med arbetsobjektet]**

   * Om du vill lagra widgetdata som en egenskap för arbetsobjektets metadata använder du följande format för värdet för egenskapen name:

      `nodename`

   * Data lagras i arbetsobjektets `nodename` egenskap `metadata`. Data bevaras om dialogrutan sedan används med samma nyttolast.

#### Steg för dialogdeltagare - Dialogrutedefinition {#dialog-participant-step-dialog-definition}

1. **[!UICONTROL Dialogrutans struktur]**

   Dialogrutorna för Dialog Deltagare-steg liknar dialogrutor som du skapar för redigeringskomponenter. De lagras under:

   `/apps/myapp/workflow/dialogs`

   Dialogrutor för det pekaktiverade standardgränssnittet har följande nodstruktur:

   ```xml
   newComponent (cq:Component)
     |- cq:dialog (nt:unstructured)
       |- content 
         |- layout 
           |- items 
             |- column 
               |- items 
                 |- component0
                 |- component1
                 |- ...
   ```

   >[!NOTE]
   >
   >Mer information finns i [Skapa och konfigurera en dialogruta](/help/sites-developing/developing-components.md#creating-and-configuring-a-dialog).

1. **[!UICONTROL Dialogrutans sökvägsegenskap]**

   Steget för **[!UICONTROL dialogdeltagare]** har egenskapen **[!UICONTROL Dialogsökväg]** (tillsammans med egenskaperna för ett [deltagarsteg](#participant-step)). Värdet för egenskapen **[!UICONTROL Dialogsökväg]** är sökvägen till `dialog` noden i dialogrutan.

   Dialogrutan finns till exempel i en komponent med namnet `EmailWatch` som lagras i noden:

   `/apps/myapp/workflows/dialogs`

   För det beröringsaktiverade användargränssnittet används följande värde för egenskapen **[!UICONTROL Dialog Path]** :

   `/apps/myapp/workflow/dialogs/EmailWatch/cq:dialog`

   ![wf-30](assets/wf-30.png)

1. **Exempeldialogrutedefinition**

   Följande XML-kodfragment representerar en dialogruta som lagrar ett `String` värde i `watchEmail` -noden för nyttolastinnehållet. Titelnoden representerar [TextField](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/granite-ui/api/jcr_root/libs/granite/ui/components/coral/foundation/form/textfield/index.html) -komponenten:

   ```xml
   jcr:primaryType="nt:unstructured" 
       jcr:title="Watcher Email Address Dialog" 
       sling:resourceType="cq/gui/components/authoring/dialog">
       <content jcr:primaryType="nt:unstructured"
           sling:resourceType="granite/ui/components/foundation/container">
           <layout jcr:primaryType="nt:unstructured" 
               margin="false" 
               sling:resourceType="granite/ui/components/foundation/layouts/fixedcolumns"
           />
           <items jcr:primaryType="nt:unstructured">
               <column jcr:primaryType="nt:unstructured"
                   sling:resourceType="granite/ui/components/foundation/container">
                   <items jcr:primaryType="nt:unstructured">
                       <title jcr:primaryType="nt:unstructured" 
                           fieldLabel="Notification Email Address" 
                           name="./jcr:content/watchEmails"
                           sling:resourceType="granite/ui/components/foundation/form/textfield"
                       />
                   </items>
               </column>
           </items>
       </content>
   </cq:dialog>
   ```

   Det här exemplet kommer, när det gäller det beröringskänsliga användargränssnittet, att resultera i en dialogruta som:

   ![chlimage_1-177](assets/chlimage_1-177.png)

### Dynamiskt deltagarsteg {#dynamic-participant-step}

Komponenten **[!UICONTROL Dynamic Participant Step]** liknar **[!UICONTROL Deltagarsteg]** med skillnaden att deltagaren väljs automatiskt vid körning.

Om du vill konfigurera steget väljer du en **[!UICONTROL deltagarväljare]** som identifierar deltagaren som arbetsposten ska tilldelas till, tillsammans med en dialogruta.

#### Dynamiskt deltagarsteg - konfiguration {#dynamic-participant-step-configuration}

Om du vill konfigurera steget redigerar du och använder följande flikar:

* [**[!UICONTROL Vanliga]**](#step-properties-common-tab)
* **[!UICONTROL Väljare för deltagare]**

   * **[!UICONTROL Väljare]**: Namnet på den [deltagarväljare som du skapar](#dynamic-participant-step-developing-the-participant-chooser).
   * **[!UICONTROL Argument]**: Alla obligatoriska argument.
   * **[!UICONTROL E-post]**: Anger om ett e-postmeddelande ska skickas till användaren.

* **[!UICONTROL Dialog]**

   * **[!UICONTROL Dialogrutans sökväg]**: Sökvägen till dialognoden i den [dialogruta som du skapar (som med steget **för** dialogdeltagare)](#dialog-participant-step-creating-a-dialog).

#### Dynamiskt deltagarsteg - Utveckla deltagarväljaren {#dynamic-participant-step-developing-the-participant-chooser}

Du skapar deltagarväljaren. Därför kan du använda valfri urvalslogik eller valfria villkor. Din deltagarväljare kan t.ex. välja den användare (i en grupp) som har minst arbetsobjekt. Du kan skapa valfritt antal deltagaralternativ som du kan använda med olika instanser av **komponenten Dynamic Deltagare Step *]*i dina arbetsflödesmodeller.

Skapa en OSGi-tjänst eller ett ECMAScript-skript som väljer en användare att tilldela arbetsposten till.

* **[!UICONTROL ECMAscript]**

   Skript måste innehålla en funktion med namnet getParticipant som returnerar ett användar-ID som ett `String` värde. Lagra dina egna skript i till exempel `/apps/myapp/workflow/scripts` mappen eller en undermapp.

   Ett exempelskript ingår i en standard-AEM-instans:

   `/libs/workflow/scripts/initiator-participant-chooser.ecma`

   >[!CAUTION]
   >
   >Du *får* inte ändra något i `/libs` banan.
   >
   >
   >Detta beror på att innehållet i `/libs` skrivs över nästa gång du uppgraderar din instans (och kan skrivas över när du använder en snabbkorrigering eller ett funktionspaket).

   Det här skriptet väljer arbetsflödesinitieraren som deltagare:

   ```
   function getParticipant() {
       return workItem.getWorkflow().getInitiator();
   }
   ```

   >[!NOTE]
   >
   >Komponenten **[!UICONTROL Arbetsflödesinitierarens deltagarväljare]** utökar det **[!UICONTROL dynamiska deltagarsteget]** och använder det här skriptet som stegimplementering.

* **[!UICONTROL OSGi-tjänst]**

   Tjänsterna måste implementera [gränssnittet com.day.cq.workflow.exec.ParticipantStepChooser](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/workflow/exec/ParticipantStepChooser.html) . Gränssnittet definierar följande medlemmar:

   * `SERVICE_PROPERTY_LABEL` fält: Använd det här fältet för att ange namnet på deltagarväljaren. Namnet visas i en lista över tillgängliga deltagarval i egenskaperna för **[!UICONTROL dynamiskt deltagarsteg]** .
   * `getParticipant` metod: Returnerar det dynamiskt lösta huvud-ID:t som ett `String` värde.
   >[!CAUTION]
   >
   >Metoden returnerar det dynamiskt matchade huvud-ID:t. `getParticipant` Detta kan vara ett grupp-ID eller användar-ID.
   >
   >
   >Ett grupp-ID kan dock bara användas för ett **[!UICONTROL deltagarsteg]** när en lista med deltagare returneras. För ett **[!UICONTROL dynamiskt deltagarsteg]** returneras en tom lista som inte kan användas för delegering.

   Om du vill göra implementeringen tillgänglig för komponenter i **[!UICONTROL Dynamic Participant Step]** lägger du till din Java-klass i ett OSGi-paket som exporterar tjänsten och distribuerar paketet till AEM-servern.

   >[!NOTE]
   >
   >**[!UICONTROL Slumpmässig deltagarväljare]** är en exempeltjänst som väljer en slumpmässig användare ( `com.day.cq.workflow.impl.process.RandomParticipantChooser`). Stegexemplet **[!UICONTROL Slumpmässig]** deltagarväljare utökar det **[!UICONTROL dynamiska deltagarsteget]** och använder den här tjänsten som stegimplementering.

#### Dynamiskt deltagarsteg - Exempel på deltagarväljartjänst {#dynamic-participant-step-example-participant-chooser-service}

Följande Java-klass implementerar `ParticipantStepChooser` gränssnittet. Klassen returnerar namnet på deltagaren som initierade arbetsflödet. Koden använder samma logik som exempelskriptet ( `initator-participant-chooser.ecma`) använder.

Anteckningen anger `@Property` värdet för `SERVICE_PROPERTY_LABEL` fältet till `Workflow Initiator Participant Chooser`.

```java
package com.adobe.example;

import org.apache.felix.scr.annotations.Component;
import org.apache.felix.scr.annotations.Properties;
import org.apache.felix.scr.annotations.Property;
import org.apache.felix.scr.annotations.Service;
import org.osgi.framework.Constants;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

import com.adobe.granite.workflow.WorkflowException;
import com.adobe.granite.workflow.WorkflowSession;
import com.adobe.granite.workflow.exec.ParticipantStepChooser;
import com.adobe.granite.workflow.exec.WorkItem;
import com.adobe.granite.workflow.metadata.MetaDataMap;

@Component
@Service
@Properties({
        @Property(name = Constants.SERVICE_DESCRIPTION, value = "An example implementation of a dynamic participant chooser."),
        @Property(name = ParticipantStepChooser.SERVICE_PROPERTY_LABEL, value = "Workflow Initiator Participant Chooser (service)") })
public class InitiatorParticipantChooser implements ParticipantStepChooser {

 private Logger logger = LoggerFactory.getLogger(this.getClass());

 public String getParticipant(WorkItem arg0, WorkflowSession arg1,
   MetaDataMap arg2) throws WorkflowException {

  String initiator = arg0.getWorkflow().getInitiator();
  logger.info("Assigning Dynamic Participant Step work item to {}",initiator);

  return initiator;
 }
}
```

I dialogrutan **[!UICONTROL Egenskaper för dynamiskt deltagarsteg]** inkluderar listan **[!UICONTROL Deltagarväljare]** objektet `Workflow Initiator Participant Chooser (script)`, som representerar den här tjänsten.

&quot;När arbetsflödesmodellen startas visar loggen ID:t för den användare som initierade arbetsflödet och som tilldelats arbetsposten. I det här exemplet startade `admin` användaren arbetsflödet.

`13.09.2015 15:48:53.037 *INFO* [10.176.129.223 [1347565733037] POST /etc/workflow/instances HTTP/1.1] com.adobe.example.InitiatorParticipantChooser Assigning Dynamic Participant Step work item to admin`

### Steg för formulärdeltagare {#form-participant-step}

Steget **[!UICONTROL Formulärdeltagare]** visar ett formulär när arbetsuppgiften öppnas. När användaren fyller i och skickar formuläret lagras fältdata i noderna i arbetsflödets nyttolast.

Om du vill konfigurera steget anger du vilken grupp eller användare som arbetsposten ska tilldelas till och sökvägen till formuläret.

>[!CAUTION]
>
>Det här avsnittet handlar om [Forms-avsnittet i Foundation Components för sidredigering](/help/sites-authoring/default-components-foundation.md#form).

#### Steg för formulärdeltagare - Konfiguration {#form-participant-step-configuration}

Om du vill konfigurera steget redigerar du och använder följande flikar:

* [**[!UICONTROL Vanliga]**](#step-properties-common-tab)
* [**[!UICONTROL Användare/grupp]**](#step-properties-user-group-tab)
* **[!UICONTROL Formulär]**

   * **[!UICONTROL-formulärsökväg**: Sökvägen till det [formulär du skapar](#form-participant-step-creating-the-form).

#### Steg för formulärdeltagare - Skapa formuläret {#form-participant-step-creating-the-form}

Skapa ett formulär som ska användas med ett steg **[!UICONTROL för]** formulärdeltagare som vanligt. Formulär för ett steg för formulärdeltagare måste dock ha följande konfigurationer:

* Egenskapen **[!UICONTROL Åtgärdstyp]** måste vara inställd på **[!UICONTROL Start av formulär]** -komponenten `Edit Workflow Controlled Resource(s)`.

* Komponenten **[!UICONTROL Början av formulär]** måste ha ett värde för `Form Identifier` egenskapen.

* Formulärkomponenterna måste ha egenskapen **Elementnamn** inställd på sökvägen till noden där fältdata lagras. Sökvägen måste hitta en nod i arbetsflödets nyttolastinnehåll. Värdet har följande format:

   `./jcr:content/path_to_node`

* Formuläret måste innehålla en **[!UICONTROL komponent för att skicka]** arbetsflöden. Du konfigurerar inga egenskaper för komponenten.

Arbetsflödets krav avgör var fältdata ska lagras. Fältdata kan till exempel användas för att konfigurera egenskaper för sidinnehåll. Följande värde för egenskapen **[!UICONTROL Elementnamn]** lagrar fältdata som värdet för `redirectTarget` egenskapen för `jcr:content` noden:

`./jcr:content/redirectTarget`

I följande exempel används fältdata som innehåll i en **[!UICONTROL Text]** -komponent på nyttolastsidan:

`./jcr:content/par/text_3/text`

&quot;Det första exemplet kan användas för alla sidor som `cq:Page` komponenten återger. Det andra exemplet kan bara användas när nyttolastsidan innehåller en **Text** -komponent med ID `text_3`.

Formuläret kan finnas var som helst i databasen, men arbetsflödesanvändare måste ha behörighet att läsa formuläret.

### Slumpmässig deltagarväljare {#random-participant-chooser}

Steget **[!UICONTROL Slumpmässig deltagarväljare]** är en deltagarväljare som tilldelar det genererade arbetsobjektet till en användare som väljs slumpmässigt från en lista.

![wf-31](assets/wf-31.png)

#### Slumpmässig deltagarväljare - konfiguration {#random-participant-chooser-configuration}

Om du vill konfigurera steget redigerar du och använder följande flikar:

* [**[!UICONTROL Vanliga]**](#step-properties-common-tab)
* **[!UICONTROL Argument]**

   * **[!UICONTROL Deltagare]**: Anger listan med användare som är tillgängliga för markering. Om du vill lägga till en användare i listan klickar du på **[!UICONTROL Lägg till objekt]** och skriver hemsökvägen för användarnoden eller användar-ID:t. Användarnas ordning påverkar inte sannolikheten att tilldelas en arbetsuppgift.

### Väljare för deltagare i arbetsflödesinitieraren {#workflow-initiator-participant-chooser}

Steget **[!UICONTROL Arbetsflödesinitierarens deltagarväljare]** är en deltagarväljare som tilldelar det genererade arbetsobjektet till användaren som startade arbetsflödet. Det finns inga andra egenskaper att konfigurera än de **[!UICONTROL gemensamma]** egenskaperna.

#### Väljare för deltagare i arbetsflödesinitiering - Konfiguration {#workflow-initiator-participant-chooser-configuration}

Om du vill konfigurera steget redigerar du på följande flikar:

* [**[!UICONTROL Vanliga]**](#step-properties-common-tab)

## Processsteg {#process-step}

Ett **[!UICONTROL processteg]** kör ett ECMAScript eller anropar en OSGi-tjänst för att utföra automatisk bearbetning.

![wf-32](assets/wf-32.png)

### Processsteg - Konfiguration {#process-step-configuration}

Om du vill konfigurera steget redigerar du och använder följande flikar:

* [**[!UICONTROL Vanliga]**](#step-properties-common-tab)
* **[!UICONTROL Process]**

   * **[!UICONTROL Process]**: Processimplementeringen som ska köras. Använd listrutan för att välja ECMAScript- eller OSGi-tjänsten. Mer information om:

      * Standardtjänsterna ECMAScripts och OSGi, se [Inbyggda processer för processteg](/help/sites-developing/workflows-process-ref.md).
      * Skapa ECMAScript för ett **[!UICONTROL processteg]** , se [Implementera ett processteg med ett ECMAScript](/help/sites-developing/workflows-customizing-extending.md#using-ecmascript).
      * Skapa OSGi-tjänster för ett **[!UICONTROL processteg]** , se [Implementera ett processteg med en Java-klass](/help/sites-developing/workflows-customizing-extending.md#implementing-a-process-step-with-a-java-class).
   * **[!UICONTROL Handler Advance]**:Välj det här alternativet om du vill att arbetsflödet automatiskt ska gå vidare till nästa steg efter körningen. Om du inte väljer det här alternativet måste implementeringsskriptet hantera arbetsflödets utveckling.
   * **[!UICONTROL Argument]**: Argument som ska skickas till processen.


