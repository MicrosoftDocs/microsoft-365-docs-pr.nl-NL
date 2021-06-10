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
description: Lees hoe u de laadtijd voor onlinepagina'SharePoint kunt verminderen door JavaScript te gebruiken om het laden van afbeeldingen en niet-essentiële JavaScript uit te stellen.
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919162"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="4d73c-103">Vertraging bij het laden van afbeeldingen en JavaScript in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d73c-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="4d73c-104">In dit artikel wordt beschreven hoe u de laadtijd voor SharePoint Online-pagina's kunt verminderen door JavaScript te gebruiken om het laden van afbeeldingen uit te stellen en ook door te wachten op het laden van niet-essentiële JavaScript tot nadat de pagina is geladen.</span><span class="sxs-lookup"><span data-stu-id="4d73c-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="4d73c-105">Afbeeldingen kunnen een negatieve invloed hebben op de laadsnelheid van pagina's SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d73c-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="4d73c-106">Standaard worden in de meeste moderne internetbrowsers afbeeldingen vooraf opgehaald bij het laden van een HTML-pagina.</span><span class="sxs-lookup"><span data-stu-id="4d73c-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="4d73c-107">Hierdoor kan de pagina onnodig traag worden geladen als de afbeeldingen niet zichtbaar zijn op het scherm totdat de gebruiker omlaag schuift.</span><span class="sxs-lookup"><span data-stu-id="4d73c-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="4d73c-108">De afbeeldingen kunnen blokkeren dat de browser het zichtbare deel van de pagina laadt.</span><span class="sxs-lookup"><span data-stu-id="4d73c-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="4d73c-109">Als u dit probleem wilt oplossen, kunt u JavaScript gebruiken om het laden van de afbeeldingen eerst over te slaan.</span><span class="sxs-lookup"><span data-stu-id="4d73c-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="4d73c-110">Bovendien kan het laden van niet-essentiële JavaScript ook de downloadtijden op uw SharePoint pagina's vertragen.</span><span class="sxs-lookup"><span data-stu-id="4d73c-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="4d73c-111">In dit onderwerp worden enkele methoden beschreven die u kunt gebruiken om de laadtijden van pagina's te verbeteren met JavaScript in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d73c-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="4d73c-112">Laadtijden van pagina's verbeteren door het laden van afbeeldingen in SharePoint onlinepagina's uit te stellen met JavaScript</span><span class="sxs-lookup"><span data-stu-id="4d73c-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="4d73c-113">U kunt JavaScript gebruiken om te voorkomen dat afbeeldingen vooraf worden opgehaald door een webbrowser.</span><span class="sxs-lookup"><span data-stu-id="4d73c-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="4d73c-114">Dit versnelt de algehele weergave van documenten.</span><span class="sxs-lookup"><span data-stu-id="4d73c-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="4d73c-115">Hiervoor verwijdert u de waarde van het src-kenmerk uit de tag en vervangt u het door het pad naar een bestand in een gegevenskenmerk, \<img\> zoals: gegevens-src.</span><span class="sxs-lookup"><span data-stu-id="4d73c-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="4d73c-116">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="4d73c-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="4d73c-117">Met deze methode worden de afbeeldingen niet direct gedownload in de browser.</span><span class="sxs-lookup"><span data-stu-id="4d73c-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="4d73c-118">Als de afbeelding al in de viewport staat, wordt in JavaScript de browser opgevraagd om de URL op te halen uit het gegevenskenmerk en deze in te voegen als de waarde voor het src-kenmerk.</span><span class="sxs-lookup"><span data-stu-id="4d73c-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="4d73c-119">De afbeelding wordt alleen geladen wanneer de gebruiker schuift en deze in beeld komt.</span><span class="sxs-lookup"><span data-stu-id="4d73c-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="4d73c-120">Als u dit allemaal wilt doen, moet u JavaScript gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4d73c-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="4d73c-121">Definieer in een tekstbestand de functie **isElementInViewport()** om te controleren of een element zich in het gedeelte van de browser dat zichtbaar is voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="4d73c-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
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

<span data-ttu-id="4d73c-122">Gebruik **vervolgensElementInViewport()** in de **functie loadItemsInView().**</span><span class="sxs-lookup"><span data-stu-id="4d73c-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="4d73c-123">Met de functie **loadItemsInView()** worden alle afbeeldingen geladen die een waarde hebben voor het gegevens-src-kenmerk als ze zich in het gedeelte van de browser hebben dat zichtbaar is voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="4d73c-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="4d73c-124">Voeg de volgende functie toe aan het tekstbestand:</span><span class="sxs-lookup"><span data-stu-id="4d73c-124">Add the following function to the text file:</span></span>
  
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

<span data-ttu-id="4d73c-125">Tot slot: **oproep loadItemsInView()** vanuit **window.onscroll()** zoals weergegeven in het volgende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="4d73c-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="4d73c-126">Dit zorgt ervoor dat afbeeldingen in de viewport worden geladen zoals de gebruiker ze nodig heeft, maar niet eerder.</span><span class="sxs-lookup"><span data-stu-id="4d73c-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="4d73c-127">Voeg het volgende toe aan het tekstbestand:</span><span class="sxs-lookup"><span data-stu-id="4d73c-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="4d73c-128">Voor SharePoint Online moet u de volgende functie toevoegen aan de schuifgebeurtenis op de \<div\> #s4-workspace-tag.</span><span class="sxs-lookup"><span data-stu-id="4d73c-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="4d73c-129">Dit komt omdat de venstergebeurtenissen worden overgenomen om ervoor te zorgen dat het lint boven aan de pagina blijft staan.</span><span class="sxs-lookup"><span data-stu-id="4d73c-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="4d73c-130">Sla het tekstbestand op als een JavaScript-bestand met de extensie .js, bijvoorbeeld delayLoadImages.js.</span><span class="sxs-lookup"><span data-stu-id="4d73c-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="4d73c-131">Wanneer u klaar bent met het schrijven delayLoadImages.js, kunt u de inhoud van het bestand toevoegen aan een basispagina in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d73c-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="4d73c-132">U doet dit door een scriptkoppeling toe te voegen aan de koptekst op de basispagina.</span><span class="sxs-lookup"><span data-stu-id="4d73c-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="4d73c-133">Zodra het op een basispagina staat, wordt JavaScript toegepast op alle pagina's in uw SharePoint Online-site die die basispagina-indeling gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4d73c-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="4d73c-134">Als u dit alleen op één pagina van uw site wilt gebruiken, gebruikt u het webonderdeel scripteditor om JavaScript in tesluiten in de pagina.</span><span class="sxs-lookup"><span data-stu-id="4d73c-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="4d73c-135">Zie deze onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="4d73c-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="4d73c-136">How to: Een basispagina toepassen op een site in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="4d73c-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [<span data-ttu-id="4d73c-137">How to: Create a page layout in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="4d73c-137">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="4d73c-138">Voorbeeld: Het JavaScript-bestand verwijzen delayLoadImages.js een basispagina in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d73c-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="4d73c-139">Om dit te laten werken, moet u ook verwijzen naar jQuery op de basispagina.</span><span class="sxs-lookup"><span data-stu-id="4d73c-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="4d73c-140">In het volgende voorbeeld ziet u in de eerste paginabelasting dat er slechts één afbeelding is geladen, maar er zijn er meerdere op de pagina.</span><span class="sxs-lookup"><span data-stu-id="4d73c-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![Schermafbeelding met één afbeelding die op de pagina is geladen](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="4d73c-142">In de volgende schermafbeelding ziet u de rest van de afbeeldingen die zijn gedownload nadat ze in de weergave zijn gescrold.</span><span class="sxs-lookup"><span data-stu-id="4d73c-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![Schermafbeelding met verschillende afbeeldingen die op de pagina zijn geladen](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="4d73c-144">Het uitstellen van het laden van afbeeldingen met Behulp van JavaScript kan een effectieve techniek zijn om de prestaties te verbeteren. Als de techniek echter wordt toegepast op een openbare website, kunnen zoekmachines de afbeeldingen niet op dezelfde manier crawlen als een regelmatig gevormde afbeelding.</span><span class="sxs-lookup"><span data-stu-id="4d73c-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="4d73c-145">Dit kan van invloed zijn op de classificaties in zoekmachines, omdat metagegevens op de afbeelding zelf er pas staan als de pagina wordt geladen.</span><span class="sxs-lookup"><span data-stu-id="4d73c-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="4d73c-146">Zoekmachinecrawlers lezen alleen de HTML en zien de afbeeldingen daarom niet als inhoud op de pagina.</span><span class="sxs-lookup"><span data-stu-id="4d73c-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="4d73c-147">Afbeeldingen zijn een van de factoren die worden gebruikt om pagina's in zoekresultaten te rangschikken.</span><span class="sxs-lookup"><span data-stu-id="4d73c-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="4d73c-148">U kunt hier onder andere omheen werken door inleidende tekst voor uw afbeeldingen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4d73c-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="4d73c-149">GitHub codevoorbeeld: JavaScript injecteren om de prestaties te verbeteren</span><span class="sxs-lookup"><span data-stu-id="4d73c-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="4d73c-150">Mis het artikel en het codevoorbeeld over [JavaScript-injectie](https://go.microsoft.com/fwlink/p/?LinkId=524759) niet op GitHub.</span><span class="sxs-lookup"><span data-stu-id="4d73c-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d73c-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4d73c-151">See also</span></span>

[<span data-ttu-id="4d73c-152">Ondersteunde browsers in Office 2013 en Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="4d73c-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="4d73c-153">How to: Een basispagina toepassen op een site in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="4d73c-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[<span data-ttu-id="4d73c-154">How to: Create a page layout in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="4d73c-154">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)