---
title: Skapa en interaktiv kommunikation
seo-title: Skapa en interaktiv kommunikation
description: 'Skapa en interaktiv kommunikation med redigeraren för interaktiv kommunikation. Använd dra-och-släpp-funktionen för att bygga den interaktiva kommunikationen och förhandsgranska både utskrift och webb på olika enhetstyper. '
seo-description: 'Skapa en interaktiv kommunikation med redigeraren för interaktiv kommunikation. Använd dra-och-släpp-funktionen för att bygga den interaktiva kommunikationen och förhandsgranska både utskrift och webb på olika enhetstyper. '
uuid: b98e9a49-cef2-42f2-b484-8765b859895b
topic-tags: interactive-communications
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: c106aa41-cbc0-4daf-9ac6-6c0d23710010
translation-type: tm+mt
source-git-commit: 73d0dea62c294bea435364fb9c6892d80751d90d
workflow-type: tm+mt
source-wordcount: '3013'
ht-degree: 0%

---


# Skapa en interaktiv kommunikation  {#create-an-interactive-communication}

Skapa en interaktiv kommunikation med redigeraren för interaktiv kommunikation. Använd dra-och-släpp-funktionen för att bygga den interaktiva kommunikationen och förhandsgranska både utskrift och webb på olika enhetstyper.

## Översikt {#overview}

Interactive Communications centraliserar och hanterar framtagning, sammanställning och leverans av personaliserade och interaktiva korrespondenser. Använd utskrift som överordnad kanal för webben och minimera arbetet med att duplicera webbutdata i den interaktiva kommunikationen.

### Förutsättningar {#prerequisites}

Nedan följer några förutsättningar för att skapa en interaktiv kommunikation:

* Skapa en [formulärdatamodell](/help/forms/using/data-integration.md) som innehåller testdata eller med en faktisk datakälla, till exempel en instans av Microsoft® Dynamics.
* Kontrollera att du har [dokumentfragmenten](/help/forms/using/document-fragments.md).
* Kontrollera att du har [mallar för utskrift och webbkanal](/help/forms/using/web-channel-print-channel.md).
* Kontrollera att du har rätt [tema](/help/forms/using/themes.md) för webbkanalen.

## Skapa interaktiv kommunikation {#createic}

1. Logga in på AEM författarinstans och navigera till **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]**.
1. Tryck **[!UICONTROL Create]** och välj **[!UICONTROL Interactive Communication]**. Sidan Skapa interaktiv kommunikation visas.

   ![create-interactive-communication](assets/create-interactive-communication.png)

1. Ange följande information. :

   * **[!UICONTROL Title]**: Ange titeln på den interaktiva kommunikationen.
   * **[!UICONTROL Name*]**: Namnet på den interaktiva kommunikationen hämtas från den titel du anger. Redigera den om det behövs.
   * **[!UICONTROL Description]**: Ange en beskrivning av den interaktiva kommunikationen.
   * **[!UICONTROL Form Data Model*]**: Bläddra och välj formulärdatamodellen. Mer information om formulärdatamodell finns i [AEM Forms-dataintegrering](/help/forms/using/data-integration.md).
   * **[!UICONTROL Prefill Service]**: Välj förifyllningstjänsten för att hämta data och fylla i interaktiv kommunikation i förväg.
   * **[!UICONTROL Post Process Type]**: Du kan välja AEM eller Forms-arbetsflöde som ska utlösas när den interaktiva kommunikationen skickas. Välj vilken typ av arbetsflöde som ska utlösas.
   * **[!UICONTROL Post Process]**: Välj namnet på arbetsflödet som ska utlösas. När du väljer AEM arbetsflöde ska du ange bilagesökväg, layoutsökväg, PDF-sökväg, sökväg till utskriften och webbdatasökväg.
   * **[!UICONTROL Tags]**: Markera taggarna som ska användas i den interaktiva kommunikationen. Du kan också skriva in ett nytt/anpassat taggnamn och trycka på Retur för att skapa det.
   * **[!UICONTROL Author]**:Författarnamnet hämtas automatiskt från den inloggade användarens användarnamn.
   * **[!UICONTROL Publish Date:]** Ange det datum då den interaktiva kommunikationen ska publiceras.
   * **[!UICONTROL Unpublish Date]**: Ange det datum då den interaktiva kommunikationen ska avpubliceras.

1. Tryck på **[!UICONTROL Next]**. Skärmen där du anger utskrifts- och webbkanalsinformation visas.
1. Ange följande:

   * **[!UICONTROL Print]**: Välj det här alternativet om du vill generera tryckkanalen för interaktiv kommunikation.
   * **[!UICONTROL Print Template*:]** Bläddra och välj en XDP-fil som utskriftsmall.
   * **[!UICONTROL Use Print As Master For Web Channel:]** Välj det här alternativet om du vill skapa webbkanalen synkroniserad med utskriftskanalen. Om du använder en utskriftskanal som överordnad för webbkanalen kan du säkerställa att innehållet och databindningen för webbkanalen hämtas från utskriftskanalen och att ändringarna som görs i utskriftskanalen återspeglas i webbkanalen när du trycker på Synkronisera. Författarna kan dock bryta arvet för specifika komponenter i webbkanalen efter behov. Mer information finns i [Synkronisera webbkanal med skrivarkanal](/help/forms/using/create-interactive-communication.md#synchronize).
   * **[!UICONTROL Web:]** Välj det här alternativet om du vill generera webbkanalen eller responsiva utdata för interaktiv kommunikation.
   * **[!UICONTROL Interactive Communication Web Template*:]** Bläddra och välj webbmallen.
   * **[!UICONTROL Theme]** och **[!UICONTROL Select Theme*]**: Bläddra och välj temat för att utforma webbkanalen för den interaktiva kommunikationen. Mer information finns i [Teman i AEM Forms](/help/forms/using/themes.md).

   Mer information om utskriftskanaler och webbkanaler finns i [Skriva ut kanal och webbkanal](/help/forms/using/web-channel-print-channel.md).

1. Tryck på **[!UICONTROL Create]**. Interaktiv kommunikation skapas och en varningsruta visas. Tryck för **[!UICONTROL Edit]** att börja skapa innehållet i den interaktiva kommunikationen enligt beskrivningen i [Lägg till innehåll med hjälp av användargränssnittet](#step2)för utveckling av interaktiv kommunikation. Du kan också trycka **[!UICONTROL Done]** och välja att redigera den interaktiva kommunikationen senare.

## Lägga till innehåll i interaktiv kommunikation {#step2}

När du har skapat en interaktiv kommunikation kan du använda redigeringsgränssnittet för interaktiv kommunikation för att skapa dess innehåll.

Mer information om gränssnittet för utveckling av interaktiv kommunikation finns i Introduktion [till redigering](/help/forms/using/introduction-interactive-communication-authoring.md)av interaktiv kommunikation.

1. Utvecklingsgränssnittet för interaktiv kommunikation startas när du trycker på Redigera enligt [Skapa interaktiv kommunikation](#createic). Du kan också navigera till en befintlig Interactive Communication-resurs på AEM, markera den och trycka på **[!UICONTROL Edit]** för att starta redigeringsgränssnittet för interaktiv kommunikation.

   Som standard visas den tryckta kanalen i den interaktiva kommunikationen, om inte den interaktiva kommunikationen bara är för webbkanaler. I utskriftskanalen i den interaktiva kommunikationen visas målområdena, som de är tillgängliga i den valda XDP/utskriftskanalmallen. I dessa målområden och fält kan du lägga till komponenter eller resurser.

1. Markera kanalen Skriv ut och välj **[!UICONTROL Components]** fliken. Följande komponenter är tillgängliga i utskriftskanalen:

   | **Komponent** | **Funktionalitet** |
   |---|---|
   | Diagram | Lägger till ett diagram som du kan använda i interaktiv kommunikation för visuell representation av tvådimensionella data som hämtats från en formulärdatamodellsamling. Mer information finns i [Använda diagram i interaktiv kommunikation](/help/forms/using/chart-component-interactive-communications.md). |
   | Dokumentfragment | Gör att du kan lägga till en återanvändbar komponent, som text, lista eller villkor, i en interaktiv kommunikation. Den tillagda komponenten kan antingen vara formulärdatamodellbaserad eller utan någon formulärdatamodell. |
   | Bild | Gör att du kan infoga en bild. |

   Dra och släpp komponenterna i din interaktiva kommunikation och konfigurera dem efter behov.

1. När utskriftskanalen är markerad går du till fliken och tillämpar filtret för att bara visa de resurser som du vill se. **[!UICONTROL Assets]**

   Med hjälp av Assets-webbläsaren kan du även dra och släppa resurser direkt till målområdena för interaktiv kommunikation.

   ![assets-documents](assets/assets-docfragments.png)

1. Dra och släpp dokumentfragmenten i den interaktiva kommunikationen. Här följer de typer av dokumentfragment som du kan använda i tryckkanalen i den interaktiva kommunikationen.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Dokumentfragmenttyp</strong></td> 
   <td><strong>Exempelsyfte</strong></td> 
  </tr> 
  <tr> 
   <td><a href="/help/forms/using/texts-interactive-communications.md" target="_blank">Text</a></td> 
   <td>Text för att lägga till adress, mottagarens e-postadress och brödtext i brevet </td> 
  </tr> 
  <tr> 
   <td><a href="/help/forms/using/conditions-interactive-communications.md" target="_blank">Villkor</a></td> 
   <td>Villkor för att lägga till lämplig rubrikbild i kommunikationen baserat på typen av princip: Standard eller Premium. <br /> </td> 
  </tr> 
  <tr> 
   <td>Lista</td> 
   <td>Grupp med dokumentfragment, inklusive text, villkor, andra listor och bilder. <br /> </td> 
  </tr> 
 </tbody> 
</table>

Mer information om dokumentfragment finns i [Dokumentfragment](/help/forms/using/document-fragments.md).

1. Om du vill ställa in bindning för variabler trycker du på en variabel och väljer ![configure_icon](assets/configure_icon.png) (Configure). Sedan ställer du in bindningsegenskaperna på egenskapspanelen i sidlisten.

   * **[!UICONTROL None]**: Agenten fyller i variabelns värde.
   * **[!UICONTROL Text Fragment]**: Om du väljer det här alternativet kan du bläddra och markera ett textdokumentfragment vars innehåll återges i fältet. Endast textdokumentfragment kan bindas till variabler som inte har några variabler inuti.
   * **[!UICONTROL Data Model Object]**: Välj en formulärdatamodellsegenskap vars värde är ifyllt i fältet.

   Du kan också välja att konfigurera det relevanta textdokumentfragmentet. På egenskapspanelen visas en lista med variabler i textdokumentfragmentet. Du kan trycka på ![Redigera](assets/edit.png) bredvid ett variabelnamn för att visa variabelns inställningar för redigering.

1. Om du vill lägga till en tabell med utskriftskanalen markerad använder du filtret på fliken **[!UICONTROL Assets]** så att endast Layoutfragment visas. Dra och släpp önskat layoutfragment till Interactive Communication. Ett layoutfragment är baserat på en XDP och kan användas för att skapa grafiska layouter eller statiska och dynamiska tabeller i interaktiv kommunikation som fylls i med dynamiska data.

   Exempel: En layouttabell med information om bruttopremie, lojalitetsrabatt % och tillgänglighet för assistans vid nödsituationer för gamla och nya policyer.

   Mer information om layoutfragment finns i [Dokumentfragment](/help/forms/using/document-fragments.md).

1. När utskriftskanalen är markerad tillämpar du filtret på visningsbilderna på fliken **[!UICONTROL Assets]** . Dra-och-släpp de bilder som behövs till Interactive Communication, t.ex. företagslogotyp.

   Hantera dessutom följande i den interaktiva kommunikationen:

   * [Lägga till och konfigurera diagram](/help/forms/using/chart-component-interactive-communications.md)
   * [Synkronisera webbkanalen med utskriftskanalen](/help/forms/using/create-interactive-communication.md#synchronize)

      * Automatisk synkronisering
      * Avbryt arv
      * Återaktivera arv
      * Synkronisera
   * [Bifogade filer och biblioteksåtkomst](/help/forms/using/create-interactive-communication.md#attachmentslibrary)
   * [Egenskaper för XDP-/layoutfält](/help/forms/using/create-interactive-communication.md#xdplayoutfieldproperties)
   * [Lägga till regler i komponenter](/help/forms/using/create-interactive-communication.md#rules)


1. Växla till **[!UICONTROL Web Channel]**. Webbkanalen visas i redigeraren för interaktiv kommunikation. När du byter från Print-kanalen till Web channel för första gången sker den automatiska synkroniseringen. Mer information finns i [Synkronisera webbkanal från utskriftskanalen](/help/forms/using/create-interactive-communication.md#synchronize).

   Eftersom vi använder Skriv ut som överordnad för webben i det här exemplet synkroniseras platshållarna för utskriftskanalen, innehållet och databindningen till webbkanalen. Du kan dock ändra och anpassa det specifika innehållet i webbkanalen efter behov.

   ![webbkanalresurser](assets/webchannelassets.png)

1. Om du vill lägga till fler komponenter i webbkanalen trycker du på **[!UICONTROL Components]**. Dra och släpp komponenter i webbkanalen i din interaktiva kommunikation efter behov och fortsätt att konfigurera dem.

   | Komponenter | Funktionalitet |
   |---|---|
   | Diagram | Lägger till ett diagram som du kan använda i interaktiv kommunikation för visuell representation av tvådimensionella data som hämtats från en formulärdatamodellsamling. Mer information finns i [Använda diagramkomponent](/help/forms/using/chart-component-interactive-communications.md). |
   | Dokumentfragment | Gör att du kan lägga till en återanvändbar komponent, text, lista eller villkor i en interaktiv kommunikation. Den återanvändbara komponenten som du lägger till i en interaktiv kommunikation kan antingen vara modellbaserad i form av formulärdata eller utan någon formulärdatamodell. |
   | Bild | Gör att du kan infoga en bild. |
   | Panel | Panelkomponenten är en platshållare för att gruppera andra komponenter och styr hur en grupp komponenter, som dragspelspanel och tabbar, placeras i det interaktiva meddelandet. Med en panelkomponent kan du också göra en grupp komponenter repeterbara för slutanvändaren, t.ex. i flera poster som krävs för att fylla i inloggningsuppgifter. |
   | Tabell | Lägger till en tabell där du kan ordna data i rader och kolumner. |
   | Målområde | Infogar ett målområde i en webbkanal för att ordna de webbkanalsspecifika komponenterna. Målområdet är en ren behållare som gör att du kan gruppera webbkanalsspecifika komponenter. |
   | Text | Lägger till RTF i webbkanalen i en interaktiv kommunikation. Text kan också använda formulärdatamodellsobjekt för att göra innehållet dynamiskt. |

1. Infoga resurser i webbkanalen efter behov.

   Du kan [förhandsgranska den interaktiva kommunikationen](#previewic) och se hur utskrifts- och webbutdata för den interaktiva kommunikationen ser ut och fortsätta att göra de ändringar som behövs.

## Förhandsgranska interaktiv kommunikation {#previewic}

Du kan använda alternativet för **[!UICONTROL Preview]** att utvärdera utseendet på den interaktiva kommunikationen. Webbkanalen i Interactive Communication erbjuder också ett alternativ för att emulera upplevelsen av en interaktiv kommunikation för olika enheter. Exempel: iPhone, iPad och Desktop. Du kan använda alternativen för både **[!UICONTROL Preview]** och **[!UICONTROL Emulator]** linjalen ![](assets/ruler.png) tillsammans för att förhandsgranska webbutdata för enheter med olika skärmstorlekar. Exempeldata i förhandsgranskningen fylls i från den angivna formulärdatamodellen.

1. Markera kanalen (tryck eller webb) om du vill förhandsgranska och trycka på Förhandsgranska. Interaktiv kommunikation visas.

   >[!NOTE]
   >
   >Förhandsgranskningen fylls i med den angivna formulärdatamodellens exempeldata. Mer information om hur du förhandsgranskar interaktiv kommunikation med vissa andra data eller använder förifyllningstjänsten finns i [Använda formulärdatamodell](/help/forms/using/using-form-data-model.md) och [Arbeta med formulärdatamodell](/help/forms/using/work-with-form-data-model.md).

1. För webbkanalen använder du ![linjalen](assets/ruler.png) för att visa hur den interaktiva kommunikationen ser ut på olika enheter.

   ![webchannelPreview](assets/webchannelpreview.png)

Dessutom kan du [förbereda och skicka interaktiv kommunikation med hjälp av agentgränssnittet](/help/forms/using/prepare-send-interactive-communication.md).

## Konfigurera egenskaper i interaktiv kommunikation  {#configuring-properties-in-interactive-communication}

### Bifogade filer och biblioteksåtkomst {#attachmentslibrary}

I utskriftskanalen kan du konfigurera bilagor och biblioteksåtkomst så att agenten kan hantera bilagor i agentgränssnittet för den interaktiva kommunikationen:

1. Markera dokumentbehållaren i utskriftskanalen och tryck på **[!UICONTROL Properties]**.

   ![dokumentbehållareegenskaper](assets/documentcontainerproperties.png)

   Panelen Egenskaper visas i sidofältet.

   ![egenskaperbilagor](assets/propertiesattachments.png)

1. Expandera **[!UICONTROL Attachments]** och ange följande egenskaper:

   * **[!UICONTROL Allow Library Access]**: Välj det här alternativet om du vill aktivera biblioteksåtkomst för agenten i agentens användargränssnitt. Om det här alternativet är aktiverat kan agenten lägga till filer från biblioteket när den interaktiva kommunikationen förbereds.
   * **[!UICONTROL Allow Re-Ordering Of Attachments]**: Välj det här alternativet om du vill att agenten ska kunna ändra ordningen på de bifogade filerna med interaktiv kommunikation.
   * **[!UICONTROL Max Number Of Attachments Allowed]**: Ange det maximala antalet bilagor som tillåts med den interaktiva kommunikationen.
   * **[!UICONTROL Files To Be Attached]**: Tryck **[!UICONTROL Add]** och bläddra för att välja filer som ska bifogas och ange följande:

      * **[!UICONTROL Attach This File To Document By Default]**: Du kan ändra det här alternativet om bara bilagan inte är obligatorisk.
      * **[!UICONTROL Mandatory:]** Agenten kan inte ta bort den bifogade filen i agentens användargränssnitt.

   ![bifogade filer](assets/attachfiles.png)

1. Tryck på **[!UICONTROL Done]**.

### Egenskaper för XDP-/layoutfält {#xdplayoutfieldproperties}

1. Håll muspekaren över ett fält som är inbyggt i kanalmallen för utskrift när du redigerar Print-kanalen i en interaktiv kommunikation och välj ![configure_icon](assets/configure_icon.png) (Konfigurera).

   Dialogrutan Egenskaper visas i sidlisten.

   ![xdpfieldProperties](assets/xdpfieldproperties.png)

1. Ange följande:

   * **[!UICONTROL Name]**: JCR-nodnamn.
   * **[!UICONTROL Title]**: Ange en titel som ska visas för agenten i agentgränssnittet och i dokumentbehållarträdet.
   * **[!UICONTROL Binding Type]**: Välj en av följande bindningstyper för fältet.

      * Ingen: Agenten fyller i egenskapens värde.
      * Textfragment: Om du väljer det här alternativet kan du bläddra och markera ett textdokumentfragment vars innehåll återges i fältet.
      * Datamodellobjekt: Välj en formulärdatamodellsegenskap vars värde är ifyllt i fältet.
   * **[!UICONTROL Default Values]**: Med standardvärdet säkerställs att fältet inte är tomt när det inte finns något värde från det angivna datamodellsobjektet eller textfragmentet. Om databindningstypen inte är någon fylls standardvärdet i i förväg i fältet.
   * **[!UICONTROL Editable By Agent]**: Välj det här alternativet om agenten ska kunna redigera värdet i fältet i agentens användargränssnitt. Den här inställningen gäller inte om bindningstypen är Textfragment.
   * **[!UICONTROL Label]**: Ange en textsträng som visas med fältet till agenten i agentens användargränssnitt. Den här inställningen gäller inte om bindningstypen är Textfragment.
   * **[!UICONTROL Tooltip]**: Ange en textsträng som ska visas när muspekaren förs till agenten i agentgränssnittet. Den här inställningen gäller inte om bindningstypen är Textfragment.
   * **[!UICONTROL Required]**: Välj att göra fältet obligatoriskt för agenten. Den här inställningen gäller inte om bindningstypen är Textfragment.
   * **[!UICONTROL Allow multiple lines]**: Markera det här fältet om du vill tillåta flera textrader som inmatning i fältet. Den här inställningen gäller inte om bindningstypen är Textfragment.


1. Tryck på ![made_icon](assets/done_icon.png).

## Tillämpa regler på komponenter för interaktiv kommunikation {#rules}

Om du vill villkoralisera komponenter eller innehåll i den interaktiva kommunikationen trycker du på komponenten/delen av innehållet och väljer ![createruleicon](assets/createruleicon.png) (Create Rule) för att starta regelredigeraren.

Mer information finns i:

* [Regelredigeraren](/help/forms/using/rule-editor.md)
* [Introduktion till utveckling av interaktiv kommunikation](/help/forms/using/introduction-interactive-communication-authoring.md)

## Använda tabeller {#tables}

### Dynamiska tabeller i interaktiv kommunikation {#dynamic-tables-in-interactive-communication}

Du kan lägga till dynamiska tabeller i interaktiv kommunikation med hjälp av layoutfragment. I följande steg används ett exempel på en kreditkortssats för att illustrera hur ett layoutfragment används för att skapa en dynamisk tabell i ett interaktivt meddelande.

1. Kontrollera att det layoutfragment som krävs för att skapa tabellen är tillgängligt i AEM.
1. Dra och släpp ett layoutfragment (med en tabell med flera kolumner) i ett målområde från resursläsaren i utskriftskanalen i din interaktiva kommunikation.

   ![lf_dragdrop](assets/lf_dragdrop.png)

   En tabell visas i layoutområdet Interaktiv kommunikation.

   ![lf_dragdrop_table](assets/lf_dragdrop_table.png)

1. Ange databindning för alla celler i tabellen. Om du vill skapa en repeterbar rad infogar du egenskaper för formulärdatamodell i raden som tillhör en gemensam samlingsegenskap.

   1. Tryck på en cell i tabellen och välj ![configure_icon](assets/configure_icon.png) (Configure).

      Dialogrutan Egenskaper visas i sidlisten.

      ![lf_cell_properties](assets/lf_cell_properties.png)

   1. Konfigurera egenskaperna:

      * **[!UICONTROL Name]**: JCR-nodnamn.
      * **[!UICONTROL Title]**: Ange en titel som ska visas i Interactive Communication Editor.
      * **[!UICONTROL Binding Type]**&amp;ast;: Välj en av följande bindningstyper för fältet.

         * **[!UICONTROL None]**
         * **[!UICONTROL Data model object]**: En formulärdatamodellegenskaps värde fylls i i fältet.
      * **[!UICONTROL Data Model Object]**: Den formulärdatamodellsegenskap vars värde är ifyllt i fältet.
      * **[!UICONTROL Default Value]**: Med standardvärdet säkerställs att fältet inte är tomt när det inte finns något värde från det angivna datamodellsobjektet. Standardvärdet är förifyllt i fältet.
      * **[!UICONTROL Editable By Agent]**: Välj det här alternativet om agenten ska kunna redigera värdet i fältet i agentens användargränssnitt.
   1. Tryck på ![made_icon](assets/done_icon.png).



1. Förhandsgranska den interaktiva kommunikationen för att se tabellen renderas med data.

   ![lf_preview](assets/lf_preview.png)

### Enbart tabeller för webbkanaler {#web-channel-only-tables}

Du kan skapa en dynamisk tabell bara för webbkanaler i en interaktiv kommunikation med hjälp av en datamodellegenskap av typen samling. En sådan tabell är en representation av en samlingsegenskaps underordnade egenskaper. Du kan bara redigera formateringsegenskaperna för de olika cellerna i tabellen.

1. Växla till webbkanalen och välj sedan att visa webbläsaren Datakällor.
1. Dra och släpp en samlingsegenskap i ett delformulär.

   En tabell skapas i delformuläret.

1. Förhandsgranska tabellen i webbförhandsgranskningen av den interaktiva kommunikationen.

## Synkronisera webbkanal med utskriftskanal {#synchronize}

När du väljer Skriv ut som Överordnad för webbkanal när du skapar en interaktiv kommunikation, skapas webbkanalen synkroniserat med utskriftskanalen och webbkanalens innehåll och databindning hämtas från utskriftskanalen och ändringarna som görs i utskriftskanalen visas i webbkanalen när du trycker på Synkronisera.

Författarna kan dock bryta arvet för komponenter i webbkanalen efter behov.
![printweb_2-3](assets/printweb_2-3.png)[Klicka för att förstora](assets/printweb_2-3.png)

![Tryck- och webbkanaler i Interactive Communication Editor](assets/printweb_2-1.png)

### Automatisk synkronisering {#auto-sync}

Om du använder Print channel som överordnad för webbkanalen och byter till webbkanalen från Print-kanalen, sker automatisk synkronisering. Den automatiska synkroniseringen tar in platshållare, innehåll och databindning till webbkanalen från utskriftskanalen. Beroende på komplexiteten och innehållet i din interaktiva kommunikation kan automatisk synkronisering ta lite tid.

>[!NOTE]
>
>Synkronisering av kanalerna synkroniserar endast dokumentfragment, bilder, villkor, listor och layoutfragment från tryckkanalen till webbkanalen. Delformulären eller de överordnade noderna som innehåller sådana element synkroniseras inte.

### Avbryt arv {#cancel-inheritance}

I webbkanalen är komponenterna inbäddade i målområdena.

Hovra över det relevanta målområdet i webbkanalen och välj ![avbryt arv](assets/cancelinheritance.png) (avbryt arv) och tryck sedan på **[!UICONTROL Yes]** i dialogrutan Avbryt arv.

Arvet av komponenterna i målområdet avbryts och nu kan du redigera dem efter behov.

### Återaktivera arv {#re-enable-inheritance}

Om du har avbrutit arvet av en komponent i webbkanalen kan du aktivera den igen. Om du vill återaktivera arv håller du pekaren över gränsen för det relevanta målområdet, som innehåller komponenten, och trycker på ![återaktivera arv](assets/reenableinheritance.png).

Dialogrutan Återställ arv visas.

![återarv](assets/revertinheritance.png)

Välj **[!UICONTROL Synchronize The Page After Reverting Inheritance]**. Välj det här alternativet om du vill synkronisera hela den interaktiva kommunikationen. Om du inte markerar det här alternativet synkroniseras bara det relevanta målområdet när arvet återställs.

Tryck på **[!UICONTROL Yes]**.

### Synkronisera {#synchronize-1}

Om du använder Skriv ut som Överordnad för webbkanal och gör ändringar i utskriftskanalen kan du trycka på Synkronisera för att lägga till de nya ändringarna i webbkanalen.

1. Synkronisera webbkanalen med Print channel genom att trycka **[!UICONTROL Synchronize]**.

   Dialogrutan Synkronisera innehåll från Överordnad kanal visas.

   ![synchronizecontentfrommasterchannel](assets/synchronizecontentfrommasterchannel.png)

1. Tryck på något av följande:

   * **[!UICONTROL Discard Changes]**: Ignorerar alla ändringar som gjorts i webbkanalen oavsett vilka ändringar som gjorts i webbkanalen.
   * **[!UICONTROL Keep Changes]**: Synkroniserar endast innehåll för de målområden där arv inte avbryts.

