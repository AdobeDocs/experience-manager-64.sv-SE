---
title: 'Skillnaden mellan HTML5-formulär och PDF forms '
seo-title: 'Skillnaden mellan HTML5-formulär och PDF forms '
description: Funktion som stöds i HTML5-formulär och PDF forms
seo-description: Funktion som stöds i HTML5-formulär och PDF forms
uuid: b0a96da5-31d3-4f99-b100-91ad51736ffb
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 273096d0-b0e1-4519-8af6-11b3414cc172
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 2%

---


# Skillnaden mellan HTML5-formulär och PDF forms {#feature-differentiation-between-html-forms-and-pdf-forms}

Följande tabell anger vilka funktioner som stöds för HTML5-formulär och PDF forms:

<table> 
 <tbody>
  <tr>
   <th>Funktion</th> 
   <th>HTML5 Forms</th> 
   <th>PDF</th> 
  </tr>
  <tr>
   <td>Streckkoder<br /> </td> 
   <td>Inte tillgängligt på användargränssnittsnivå. </td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Signaturfält<br /> </td> 
   <td><strong>Digitala signaturer</strong> stöds inte, men ett nytt <strong>fält för Klottsignatur</strong> läggs till för papper som signaturer. Man kan klottra sin signatur i formuläret med hjälp av fältet <strong>Klottsignatur</strong> . Signaturen sparas i formuläret som en bild. Du kan spara geolokaliseringsinformation i fältet <strong>Klottsignatur</strong> .</td> 
   <td>Signaturfält är tillgängligt för <strong>digitala signaturer</strong>.</td> 
  </tr>
  <tr>
   <td>Datasammanfogning</td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Bilder</td> 
   <td>Data-URI-schemat används för att visa bilder. Alla moderna versioner av webbläsare har stöd för det här schemat, men det finns skillnader i det intervall med bildformat som varje webbläsare har stöd för.<br /> </td> 
   <td>Formaten .gif, .png, .jpeg, .bmp och .tiff stöds.</td> 
  </tr>
  <tr>
   <td>Sidnumrering<br /> </td> 
   <td><p>Ett HTML5-formulär är uppdelat i paneler och rutor för att ge det ett utseende som liknar PDF forms. Sidstorleken beräknas dynamiskt. Om allt innehåll på en sida i ett HTML5-formulär tas bort eller markeras som dolt, döljs den tomma sidan och inget tomt utrymme (blanksteg) visas mellan sidorna ovanför och under den tomma sidan.</p> <p>Om datasammanfogning eller skript lägger till innehåll på en sida utökas sidans längd så att det nya innehållet får plats. Inga nya sidor läggs till i formuläret så att det nya innehållet får plats. </p> <p><strong>Obs!</strong> När allt innehåll på en sida i ett HTML5-formulär tas bort eller markeras som dolt, förblir den tomma sidan (tomt utrymme) synlig mellan första och andra sidan, men inte mellan andra sidor.</p> </td> 
   <td>Sidnumrering i PDF-dokument beror på det sammanfogade datainnehållet eller på om användarinnehållet och antalet sidor ökar eller minskar baserat på det.</td> 
  </tr>
  <tr>
   <td>Sidhuvuden/sidfötter </td> 
   <td>Stöds. <br /> <br /> Eftersom mobilformulär i HTML5 inte stöder sidbrytningar visas sidhuvuden och sidfötter endast en gång. Du kan dock konfigurera dem i layouten så att de visas på flera ställen i förhandsgranskningen av mobilformulär.<br /> </td> 
   <td>Stöds.</td> 
  </tr>
  <tr>
   <td>Anpassade widgetar</td> 
   <td>Man kan anpassa widgetar för att förbättra användarupplevelsen på mobila enheter.<br /> </td> 
   <td>Alla widgetar är låsta och ingen anpassad widget kan kopplas.<br /> </td> 
  </tr>
  <tr>
   <td>XFA Script API</td> 
   <td>Stöder de vanligaste XFA-skriptkonstruktionerna. Mer information om vilka konstruktioner som stöds finns i <a href="/help/forms/using/scripting-support.md">Skriptstöd</a>.</td> 
   <td>Stöder alla XFA-skriptkonstruktioner.</td> 
  </tr>
  <tr>
   <td>Acrobat Script API:er </td> 
   <td>HTML5-formulär har stöd för de vanligaste API:erna. Mer information finns i <a href="/help/forms/using/scripting-support.md">Skriptstöd</a>.</td> 
   <td>Om PDF-filen öppnas i Acrobat eller Reader stöds även alla skript-API:er som finns i Acrobat.</td> 
  </tr>
  <tr>
   <td>Stöd för höger-till-vänster-språk </td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
 </tbody>
</table>

Följ de bästa sätten att aktivera en formulärmall för HTML5-återgivningar och se till att HTML5-formulär och XFA-baserade PDF-filer fungerar och ser likadana ut. En detaljerad lista över de effektivaste strategierna finns i [Bästa tillvägagångssätt för att utforma ett HTML5-formulär.](/help/forms/using/best-practices-for-html5-forms.md)

