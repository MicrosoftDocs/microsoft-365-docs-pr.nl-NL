---
title: Vertraging bij het laden van afbeeldingen en JavaScript in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: Lees hoe u de laadtijd voor SharePoint Online-pagina's kunt verminderen door JavaScript te gebruiken om het laden van afbeeldingen en niet-essentiële JavaScript uit te stellen.
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919162"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Vertraging bij het laden van afbeeldingen en JavaScript in SharePoint Online

In dit artikel wordt beschreven hoe u de laadtijd voor SharePoint Online-pagina's kunt verminderen door JavaScript te gebruiken om het laden van afbeeldingen uit te stellen en ook door te wachten op het laden van niet-essentiële JavaScript tot nadat de pagina is geladen.
  
Afbeeldingen kunnen een negatieve invloed hebben op de laadsnelheid van pagina's in SharePoint Online. Standaard worden in de meeste moderne internetbrowsers afbeeldingen vooraf opgehaald bij het laden van een HTML-pagina. Hierdoor kan de pagina onnodig traag worden geladen als de afbeeldingen niet zichtbaar zijn op het scherm totdat de gebruiker omlaag schuift. De afbeeldingen kunnen blokkeren dat de browser het zichtbare deel van de pagina laadt. Als u dit probleem wilt oplossen, kunt u JavaScript gebruiken om het laden van de afbeeldingen eerst over te slaan. Bovendien kan het laden van niet-essentiële JavaScript ook de downloadtijden op uw SharePoint-pagina's vertragen. In dit onderwerp worden enkele methoden beschreven die u kunt gebruiken om de laadtijden van pagina's te verbeteren met JavaScript in SharePoint Online.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Laadtijden van pagina's verbeteren door het laden van afbeeldingen in SharePoint Online-pagina's uit te stellen met JavaScript

U kunt JavaScript gebruiken om te voorkomen dat afbeeldingen vooraf worden opgehaald door een webbrowser. Dit versnelt de algehele weergave van documenten. Hiervoor verwijdert u de waarde van het src-kenmerk uit de tag en vervangt u het door het pad naar een bestand in een gegevenskenmerk, \<img\> zoals: gegevens-src. Bijvoorbeeld:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

Met deze methode worden de afbeeldingen niet direct gedownload in de browser. Als de afbeelding al in de viewport staat, wordt in JavaScript de browser opgevraagd om de URL op te halen uit het gegevenskenmerk en deze in te voegen als de waarde voor het src-kenmerk. De afbeelding wordt alleen geladen wanneer de gebruiker schuift en deze in beeld komt.
  
Als u dit allemaal wilt doen, moet u JavaScript gebruiken.
  
Definieer in een tekstbestand de functie **isElementInViewport()** om te controleren of een element zich in het gedeelte van de browser dat zichtbaar is voor de gebruiker.
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

Gebruik **vervolgensElementInViewport()** in de **functie loadItemsInView().** Met de functie **loadItemsInView()** worden alle afbeeldingen geladen die een waarde hebben voor het gegevens-src-kenmerk als ze zich in het gedeelte van de browser hebben dat zichtbaar is voor de gebruiker. Voeg de volgende functie toe aan het tekstbestand:
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

Tot slot: **oproep loadItemsInView()** vanuit **window.onscroll()** zoals weergegeven in het volgende voorbeeld. Dit zorgt ervoor dat afbeeldingen in de viewport worden geladen zoals de gebruiker ze nodig heeft, maar niet eerder. Voeg het volgende toe aan het tekstbestand:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

Voor SharePoint Online moet u de volgende functie toevoegen aan de schuifgebeurtenis op de \<div\> #s4-workspace-tag. Dit komt omdat de venstergebeurtenissen worden overgenomen om ervoor te zorgen dat het lint boven aan de pagina blijft staan.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Sla het tekstbestand op als een JavaScript-bestand met de extensie .js, bijvoorbeeld delayLoadImages.js.
  
Wanneer u klaar bent met het schrijven delayLoadImages.js, kunt u de inhoud van het bestand toevoegen aan een basispagina in SharePoint Online. U doet dit door een scriptkoppeling toe te voegen aan de koptekst op de basispagina. Zodra het op een basispagina staat, wordt JavaScript toegepast op alle pagina's op uw SharePoint Online-site die gebruikmaken van die basispagina-indeling. Als u dit alleen op één pagina van uw site wilt gebruiken, gebruikt u het webonderdeel scripteditor om JavaScript in tesluiten in de pagina. Zie deze onderwerpen voor meer informatie:
  
- [How to: Een basispagina toepassen op een site in SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [How to: Een pagina-indeling maken in SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Voorbeeld: Het JavaScript-delayLoadImages.js verwijzen vanaf een basispagina in SharePoint Online
  
Om dit te laten werken, moet u ook verwijzen naar jQuery op de basispagina. In het volgende voorbeeld ziet u in de eerste paginabelasting dat er slechts één afbeelding is geladen, maar er zijn er meerdere op de pagina.
  
![Schermafbeelding met één afbeelding die op de pagina is geladen](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
In de volgende schermafbeelding ziet u de rest van de afbeeldingen die zijn gedownload nadat ze in de weergave zijn gescrold.
  
![Schermafbeelding met verschillende afbeeldingen die op de pagina zijn geladen](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Het uitstellen van het laden van afbeeldingen met Behulp van JavaScript kan een effectieve techniek zijn om de prestaties te verbeteren. Als de techniek echter wordt toegepast op een openbare website, kunnen zoekmachines de afbeeldingen niet op dezelfde manier crawlen als een regelmatig gevormde afbeelding. Dit kan van invloed zijn op de classificaties in zoekmachines, omdat metagegevens op de afbeelding zelf er pas staan als de pagina wordt geladen. Zoekmachinecrawlers lezen alleen de HTML en zien de afbeeldingen daarom niet als inhoud op de pagina. Afbeeldingen zijn een van de factoren die worden gebruikt om pagina's in zoekresultaten te rangschikken. U kunt hier onder andere omheen werken door inleidende tekst voor uw afbeeldingen te gebruiken.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>Voorbeeld van GitHub-code: JavaScript injecteren om de prestaties te verbeteren

Mis het artikel en het codevoorbeeld over [JavaScript-injectie](https://go.microsoft.com/fwlink/p/?LinkId=524759) op GitHub niet.
  
## <a name="see-also"></a>Zie ook

[Ondersteunde browsers in Office 2013 en Microsoft 365 Apps voor bedrijven](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[How to: Een basispagina toepassen op een site in SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[How to: Een pagina-indeling maken in SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)