---
title: Experience Fragments
seo-title: Experience Fragments
description: 'null'
seo-description: 'null'
uuid: be1aceef-eb6e-47e5-a920-be5cc6de6191
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 1fe58af0-3005-46fc-8717-5d32557947ed
translation-type: tm+mt
source-git-commit: 6f6952686446359485f180050219a12db9d3969a

---


# Experience Fragments{#experience-fragments}

Ett Experience Fragment är en grupp med en eller flera komponenter, inklusive innehåll och layout, som kan refereras till på sidor. De kan innehålla alla komponenter.

An Experience Fragment:

* Är en del av en upplevelse (sida).
* Kan användas på flera sidor.
* Är baserad på en mall (endast redigerbar) för att definiera struktur och komponenter.
* Består av en eller flera komponenter, med layout, i ett styckesystem.
* Kan innehålla andra upplevelsefragment.
* Kan kombineras med andra komponenter (inklusive andra Experience Fragments) för att skapa en komplett sida (upplevelse).
* Kan ha olika variationer, som kan dela innehåll och/eller komponenter.
* Kan delas upp i byggstenar som kan användas i flera varianter av fragmentet.

Du kan använda Experience Fragments:

* Om en författare vill återanvända delar (ett fragment av en upplevelse) av en sida måste de kopiera och klistra in det fragmentet. Att skapa och underhålla dessa klipp-och-klistra-upplevelser är tidskrävande och leder ofta till användarfel. Upplevelsefragment eliminerar behovet av att kopiera/klistra in.
* För att stödja headless CMS-fallstudier. Författare vill bara använda AEM för att skapa, men inte för att leverera till kunden. Ett system/kontaktyta från tredje part skulle förbruka upplevelsen och sedan leverera till slutanvändaren.

>[!NOTE]
>
>Skrivåtkomst för upplevelsefragment kräver att användarkontot är registrerat i gruppen:
>
>`experience-fragments-editors`
>
>Kontakta systemadministratören om du har problem.

## När ska ni använda upplevelsefragment? {#when-should-you-use-experience-fragments}

Experience Fragments ska användas:

* När ni vill återanvända upplevelser.

   * Upplevelser som återanvänds med samma eller liknande innehåll

* När du använder AEM som en innehållsleveransplattform för tredje part.

   * Alla lösningar som vill använda AEM som plattform för innehållsleverans
   * Bädda in innehåll i kontaktpunkter från tredje part

* Om du har en upplevelse med olika variationer eller renderingar.

   * Kanal- eller kontextspecifika varianter
   * Upplevelser som är bra att gruppera (till exempel en kampanj med olika upplevelser i olika kanaler)

* När ni använder Omnichannel Commerce.

   * Dela e-handelsrelaterat innehåll i sociala medier i stor skala
   * Göra kontaktytor transaktionella

## Organisera dina upplevelsefragment {#organizing-your-experience-fragments}

Det rekommenderas att
* använda mappar för att ordna dina upplevelsefragment,

* [konfigurera tillåtna mallar för dessa mappar](#configure-allowed-templates-folder).

Om du skapar mappar kan du:

* skapa en meningsfull struktur för era Experience Fragments, t.ex. efter klassificering

   >[!NOTE]
   >
   >Det är inte nödvändigt att anpassa strukturen för dina Experience Fragments till sidstrukturen på din plats.

* [allokera tillåtna mallar på mappnivå](#configure-allowed-templates-folder)

   >[!NOTE]
   >
   >Du kan använda [mallredigeraren](/help/sites-authoring/templates.md) för att skapa en egen mall.

I följande exempel visas Experience Fragments som är strukturerade enligt `Contributors`. Den struktur som används visar också hur andra funktioner, som Multi Site Management (inklusive språkkopior), kan användas.

>[!CAUTION]
>
>Följande skärmbild togs från WKND-webbplatsen med Adobe Experience Manager som en molntjänst.

![Mappar för Experience Fragments](assets/xf-folders.png)

## Skapa och konfigurera en mapp för dina Experience Fragments {#creating-and-configuring-a-folder-for-your-experience-fragments}

Om du vill skapa och konfigurera en mapp för dina Experience Fragments bör du:

1. [Skapa en mapp](/help/sites-authoring/managing-pages.md#creating-a-new-folder).

1. [Konfigurera tillåtna Experience Fragment-mallar för den mappen](#configure-allowed-templates-folder).

>[!NOTE]
>
>Det går också att konfigurera [tillåtna mallar för din instans](#configure-allowed-templates-instance), men den här metoden rekommenderas **inte** eftersom värdena kan skrivas över vid uppgradering.

### Konfigurera tillåtna mallar för mappen {#configure-allowed-templates-folder}

>[!NOTE]
>
>Det här är den rekommenderade metoden för att ange **[!UICONTROL tillåtna mallar]**, eftersom värdena inte skrivs över vid uppgradering.

1. Navigera till önskad **[!UICONTROL Experience Fragments]** -mapp.

1. Markera mappen och välj sedan **[!UICONTROL Egenskaper]**.

1. Ange det reguljära uttrycket för hämtning av de mallar som krävs i fältet **[!UICONTROL Tillåtna mallar]** .

   Exempel:
   `/conf/(.*)/settings/wcm/templates/experience-fragment(.*)?`

   ![Upplevelsefragmentegenskaper - tillåtna mallar](assets/xf-folders-templates.png)

1. Välj **[!UICONTROL Spara och stäng]**.

### Konfigurera tillåtna mallar för din instans {#configure-allowed-templates-instance}

>[!CAUTION]
>
>Du bör inte ändra **[!UICONTROL Tillåtna mallar]** med den här metoden eftersom de angivna mallarna kan skrivas över vid uppgradering.
>
>Använd den här dialogrutan endast i informationssyfte.

1. Navigera till **[!UICONTROL Experience Fragments]** -konsolen.

1. Välj **[!UICONTROL konfigurationsalternativ]**:

   ![Knappen Konfiguration](assets/xf-folders-18.png)

1. Ange de mallar som krävs i dialogrutan **[!UICONTROL Konfigurera Experience Fragments]** :

   ![Konfigurera Experience Fragments](assets/xf-folders-19.png)

1. Välj **[!UICONTROL Spara]**.

## Skapa ett upplevelsefragment {#creating-an-experience-fragment}

Så här skapar du ett Experience Fragment:

1. Välj **[!UICONTROL Experience Fragments]** i Global Navigation.

   ![screen_shot_2018-04-05at92221am1](assets/screen_shot_2018-04-05at92221am1.png)

1. Navigera till önskad mapp och välj **[!UICONTROL Skapa]**.

1. Välj **[!UICONTROL Experience Fragment]** för att öppna guiden **[!UICONTROL Skapa Experience Fragment]** .

   Välj önskad **[!UICONTROL mall]** och sedan **[!UICONTROL Nästa]**:

   ![xf-authoring-02](assets/xf-authoring-02.png)


1. Ange **[!UICONTROL egenskaper]** för Experience Fragment.

   En **[!UICONTROL titel]** är obligatorisk. Om **[!UICONTROL namnet]** lämnas tomt hämtas det från **[!UICONTROL titeln]**.

   ![xf-authoring-03](assets/xf-authoring-03.png)

1. Klicka på **[!UICONTROL Skapa]**.

   Ett meddelande visas. Välj:

   * **[!UICONTROL Klart]** att återgå till konsolen
   * **[!UICONTROL Öppna]** för att öppna fragmentredigeraren

## Redigera din upplevelsefragment {#editing-your-experience-fragment}

Experience Fragment Editor har funktioner som liknar den vanliga sidredigeraren. Mer information om hur du använder sidinnehåll finns i [Redigera sidinnehåll](/help/sites-authoring/editing-content.md) .

Följande exempelprocedur visar hur du skapar ett teaser för en produkt:

1. Dra och släpp en **[!UICONTROL kategoriläsare]** från [komponentwebbläsaren](/help/sites-authoring/author-environment-tools.md#components-browser).

   ![xf-authoring-04](assets/xf-authoring-04.png)

1. Välj **[!UICONTROL Konfigurera](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste)**i komponentverktygsfältet.
1. Lägg till **[!UICONTROL resursen]** och definiera **[!UICONTROL egenskaperna]** efter behov.
1. Bekräfta definitionerna med **[!UICONTROL Klar]** (kryssikon).
1. Lägg till fler komponenter efter behov.

## Skapa en upplevelsefragmentvariant {#creating-an-experience-fragment-variation}

Ni kan skapa olika upplevelsefragment beroende på era behov:

1. Öppna fragmentet för [redigering](/help/sites-authoring/experience-fragments.md#editing-your-experience-fragment).
1. Öppna fliken **[!UICONTROL Variationer]** .

   ![xf-authoring-06](assets/xf-authoring-06.png)

1. **Med Skapa** kan du skapa:

   * **[!UICONTROL Variation]**
   * **[!UICONTROL Variation som live-copy]**.

1. Definiera de nödvändiga egenskaperna:

   * **[!UICONTROL Mall]**
   * **[!UICONTROL Titel]**
   * **[!UICONTROL Namn]**; om det lämnas tomt kommer det att härledas från titeln
   * **[!UICONTROL Beskrivning]**
   * **[!UICONTROL Variationstaggar]**
   ![xf-authoring-06](assets/xf-authoring-07.png)

1. Bekräfta med **[!UICONTROL Klar]** (bock-ikon) så visas den nya varianten på panelen:

   ![xf-authoring-08](assets/xf-authoring-08.png)

## Använda ditt Experience Fragment {#using-your-experience-fragment}

Nu kan du använda din Experience Fragment när du redigerar dina sidor:

1. Öppna en sida för redigering.

   Till exempel: [http://localhost:4502/editor.html/content/we-retail/language-masters/en/products/men.html](http://localhost:4502/editor.html/content/we-retail/language-masters/en/products/men.html)

1. Skapa en instans av Experience Fragment-komponenten genom att dra komponenten från komponentwebbläsaren till sidstyckesystemet:

   ![xf-authoring-09](assets/xf-authoring-09.png)

1. Lägg till den faktiska Experience Fragment-funktionen i komponentinstansen. antingen:

   * Dra det önskade fragmentet från Resursläsaren och släpp det på komponenten
   * Välj **[!UICONTROL Konfigurera]** i komponentverktygsfältet och ange vilket fragment som ska användas, bekräfta med **Klar** (tick)
   ![xf-authoring-10](assets/xf-authoring-10.png)

   >[!NOTE]
   >
   >Redigera i komponentverktygsfältet fungerar som ett kortkommando för att öppna fragmentet i fragmentredigeraren.

## Building Blocks {#building-blocks}

Du kan välja en eller flera komponenter för att skapa en byggsten för återvinning i fragmentet:

### Skapa ett byggblock {#creating-a-building-block}

Så här skapar du ett nytt byggblock:

1. Välj de komponenter som du vill återanvända i Experience Fragment-redigeraren:

   ![xf-authoring-12](assets/xf-authoring-12.png)

1. Välj **[!UICONTROL Konvertera till byggblock]** i komponentverktygsfältet:

   ![xf-authoring-13-icon](assets/xf-authoring-13-icon.png)

   Exempel:

   ![xf-authoring-13](assets/xf-authoring-13.png)

1. Ange namnet på **[!UICONTROL byggblocket]** och bekräfta med **[!UICONTROL Konvertera]**:

   ![xf-authoring-14](assets/xf-authoring-14.png)

1. **Byggblocket** visas på fliken och kan markeras i styckesystemet:

   ![xf-authoring-15](assets/xf-authoring-15.png)

### Hantera ett byggblock {#managing-a-building-block}

Byggblocket visas på fliken **[!UICONTROL Byggblock]** . Följande åtgärder är tillgängliga för varje block:

* Gå till mallsida: öppna mallvarianten på en ny flik
* Byt namn på
* Ta bort

![xf-authoring-16](assets/xf-authoring-16.png)

### Använda ett byggblock {#using-a-building-block}

Du kan dra byggblocket till styckesystemet för vilket fragment som helst, precis som med vilken komponent som helst.

## The Plain HTML Rendition {#the-plain-html-rendition}

Med hjälp av väljaren i URL:en kan du komma åt den vanliga HTML-återgivningen. `.plain.`

Det här är tillgängligt från webbläsaren, men det främsta syftet är att tillåta andra program (till exempel webbprogram från tredje part, anpassade mobilimplementeringar) att komma åt innehållet i Experience Fragment direkt, med enbart URL:en.

Den rena HTML-återgivningen lägger till protokoll, värd och kontextsökväg till sökvägar som är:

* av typen: `src`, `href`eller `action`

* eller avsluta med: `-src`eller `-href`

Exempel:

`.../brooklyn-coat/master.plain.html`

>[!NOTE]
>
>Länkar refererar alltid till publiceringsinstansen. De är avsedda att användas av tredje part, så länken anropas alltid från publiceringsinstansen, inte författaren.

![xf-authoring-17](assets/xf-authoring-17.png)

## Exportera Experience Fragments {#exporting-experience-fragments}

Som standard levereras Experience Fragments i HTML-format. Detta kan användas av både AEM- och tredjepartskanaler.

HTML används för export till Adobe Target. Mer information finns i [Målintegrering med Experience Fragments](/help/sites-administering/experience-fragments-target.md) .

