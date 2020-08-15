---
title: Laden van afbeeldingen en JavaScript vertragen in SharePoint Online
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
description: Meer informatie over hoe u de laadtijd voor SharePoint Online-pagina's kunt verkleinen met behulp van JavaScript om het laden van afbeeldingen en niet-basisscripts te uitstellen.
ms.openlocfilehash: ee86ae0813c11fbfd836d7d38ea124c1e3f277d0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689319"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="52bce-103">Laden van afbeeldingen en JavaScript vertragen in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="52bce-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="52bce-104">In dit artikel wordt beschreven hoe u de laadtijd voor SharePoint Online-pagina's kunt verkleinen met behulp van JavaScript om het laden van afbeeldingen te vertraagen, en het niet mogelijk is om niet-essentieel JavaScript te laden totdat de pagina wordt geladen.</span><span class="sxs-lookup"><span data-stu-id="52bce-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="52bce-105">Afbeeldingen kunnen een negatieve invloed hebben op de laad snelheid van pagina's in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="52bce-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="52bce-106">Standaardafbeeldingen van de nieuwste Internet browsers voorafgaand aan het ophalen van afbeeldingen bij het laden van een HTML-pagina.</span><span class="sxs-lookup"><span data-stu-id="52bce-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="52bce-107">Dit kan tot gevolg hebben dat de pagina langzaam wordt geladen als de afbeeldingen niet zichtbaar zijn op het scherm totdat de gebruiker omlaag schuift.</span><span class="sxs-lookup"><span data-stu-id="52bce-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="52bce-108">De afbeeldingen kunnen verhinderen dat de browser het zichtbare gedeelte van de pagina laadt.</span><span class="sxs-lookup"><span data-stu-id="52bce-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="52bce-109">U kunt dit probleem omzeilen door JavaScript te gebruiken om de afbeeldingen eerst over te slaan.</span><span class="sxs-lookup"><span data-stu-id="52bce-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="52bce-110">Daarnaast kunt u de downloads van niet-belangrijkste JavaScript ook trager downloaden op uw SharePoint-pagina's.</span><span class="sxs-lookup"><span data-stu-id="52bce-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="52bce-111">In dit onderwerp worden enkele methoden beschreven die u kunt gebruiken om de laadtijden van pagina's te verbeteren met JavaScript in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="52bce-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="52bce-112">Het laden van pagina's verbeteren door het laden van afbeeldingen op SharePoint Online-pagina's te vertragen met behulp van JavaScript</span><span class="sxs-lookup"><span data-stu-id="52bce-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="52bce-113">U kunt JavaScript gebruiken om te voorkomen dat een webbrowser afbeeldingen vooraf ophalen.</span><span class="sxs-lookup"><span data-stu-id="52bce-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="52bce-114">Hiermee wordt de algehele rendering van documenten versneld.</span><span class="sxs-lookup"><span data-stu-id="52bce-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="52bce-115">Als u dit wilt doen, verwijdert u de waarde van het SRC-kenmerk van de \<img\> tag en vervangt u deze door het pad naar een bestand in een gegevenskenmerk zoals: data-src.</span><span class="sxs-lookup"><span data-stu-id="52bce-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="52bce-116">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="52bce-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="52bce-117">Met deze methode kunt u de afbeeldingen niet meteen downloaden via de browser.</span><span class="sxs-lookup"><span data-stu-id="52bce-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="52bce-118">Als de afbeelding zich al in de viewport bevindt, krijgt de browser de URL van het gegevenskenmerk en voegt u deze in als de waarde voor het kenmerk src.</span><span class="sxs-lookup"><span data-stu-id="52bce-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="52bce-119">De afbeelding wordt alleen geladen wanneer de gebruiker in beeld schuift.</span><span class="sxs-lookup"><span data-stu-id="52bce-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="52bce-120">Om dit te doen, moet u JavaScript gebruiken.</span><span class="sxs-lookup"><span data-stu-id="52bce-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="52bce-121">Definieer in een tekstbestand de functie **functie iselementinviewport ()** om te controleren of een element zich in een deel van de browser bevindt dat zichtbaar is voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="52bce-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
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

<span data-ttu-id="52bce-122">Gebruik vervolgens **functie iselementinviewport ()** in de **loadItemsInView-functie ()** .</span><span class="sxs-lookup"><span data-stu-id="52bce-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="52bce-123">Met de functie **loadItemsInView ()** worden alle afbeeldingen met een waarde voor het data-SRC-kenmerk geladen, indien deze deel uitmaken van de browser die zichtbaar is voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="52bce-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="52bce-124">Voeg de volgende functie toe aan het tekstbestand:</span><span class="sxs-lookup"><span data-stu-id="52bce-124">Add the following function to the text file:</span></span>
  
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

<span data-ttu-id="52bce-125">Bel tot slot **loadItemsInView ()** vanuit **Window. onscroll ()** , zoals wordt weergegeven in het volgende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="52bce-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="52bce-126">Dit zorgt ervoor dat alle afbeeldingen in de viewport worden geladen terwijl de gebruiker ze nodig hebben, maar niet eerder.</span><span class="sxs-lookup"><span data-stu-id="52bce-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="52bce-127">Voeg het volgende toe aan het tekstbestand:</span><span class="sxs-lookup"><span data-stu-id="52bce-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="52bce-128">Voor SharePoint Online dient u de volgende functie toe te voegen aan de scroll-gebeurtenis in de tag #s4-Workspace \<div\> .</span><span class="sxs-lookup"><span data-stu-id="52bce-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="52bce-129">Dit komt doordat de venster gebeurtenissen worden overschreven om ervoor te zorgen dat het lint boven aan de pagina blijft.</span><span class="sxs-lookup"><span data-stu-id="52bce-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="52bce-130">Sla het tekstbestand op als een JavaScript-bestand met de extensie. js, bijvoorbeeld delayLoadImages.js.</span><span class="sxs-lookup"><span data-stu-id="52bce-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="52bce-131">Wanneer u klaar bent met het schrijven van delayLoadImages.js, kunt u de inhoud van het bestand toevoegen aan een basispagina in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="52bce-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="52bce-132">U doet dit door een scriptkoppeling toe te voegen aan de koptekst op de basispagina.</span><span class="sxs-lookup"><span data-stu-id="52bce-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="52bce-133">Wanneer de afbeelding op de basispagina staat, wordt deze op alle pagina's van de SharePoint Online-site toegepast die de basispagina-indeling gebruiken.</span><span class="sxs-lookup"><span data-stu-id="52bce-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="52bce-134">Als u dit alleen op één pagina van uw site wilt gebruiken, gebruikt u het webonderdeel script editor om JavaScript op de pagina in te sluiten.</span><span class="sxs-lookup"><span data-stu-id="52bce-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="52bce-135">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="52bce-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="52bce-136">Procedure: een basispagina toepassen op een site in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="52bce-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525627)

- [<span data-ttu-id="52bce-137">Procedure: een pagina-indeling maken in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="52bce-137">How to: Create a page layout in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525628)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="52bce-138">Voorbeeld: verwijzen naar het JavaScript-delayLoadImages.js bestand van een basispagina in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="52bce-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="52bce-139">Om dit te kunnen werken, moet u ook verwijzen naar jQuery op de basispagina.</span><span class="sxs-lookup"><span data-stu-id="52bce-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="52bce-140">In het volgende voorbeeld ziet u dat er op de eerste pagina wordt gelaadd, maar er is een aantal afbeeldingen geladen, maar er zijn nog meer op de pagina.</span><span class="sxs-lookup"><span data-stu-id="52bce-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![Schermafbeelding van één afbeelding die wordt weergegeven op de pagina](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="52bce-142">In de volgende schermafbeelding wordt de rest van de afbeeldingen weergegeven die worden gedownload wanneer ze in beeld schuiven.</span><span class="sxs-lookup"><span data-stu-id="52bce-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![Schermafbeelding van diverse afbeeldingen die op de pagina zijn geladen](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="52bce-144">Als u het laden van afbeeldingen met behulp van JavaScript vertraagt, kan de prestaties van de afbeelding toenemen. Als de methode op een openbare website wordt toegepast, kunnen de afbeeldingen niet worden verkend met behulp van zoekprogramma's, op dezelfde manier als de afbeeldingen een regelmatig opgestelde afbeelding verkennen.</span><span class="sxs-lookup"><span data-stu-id="52bce-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="52bce-145">Dit kan van invloed zijn op de invloed op de zoekmachines, aangezien de metagegevens van de afbeelding zelf niet echt zijn totdat de pagina wordt geladen.</span><span class="sxs-lookup"><span data-stu-id="52bce-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="52bce-146">In crawlers voor zoekmachines wordt alleen de HTML gelezen en worden de afbeeldingen daarom niet weergegeven als inhoud op de pagina.</span><span class="sxs-lookup"><span data-stu-id="52bce-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="52bce-147">Afbeeldingen vormen een van de factoren die worden gebruikt voor het rangschikken van pagina's in zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="52bce-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="52bce-148">Eén manier om dit te omzeilen is door in te LEIDENE tekst voor uw afbeeldingen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="52bce-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="52bce-149">Voorbeeld van een GitHub-code: JavaScript invoegen om de prestaties te verbeteren</span><span class="sxs-lookup"><span data-stu-id="52bce-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="52bce-150">U hoeft het artikel en het codevoorbeeld niet te missen op een [JavaScript-injectie](https://go.microsoft.com/fwlink/p/?LinkId=524759) op github.</span><span class="sxs-lookup"><span data-stu-id="52bce-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52bce-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="52bce-151">See also</span></span>

[<span data-ttu-id="52bce-152">Ondersteunde browsers in Office 2013 en Microsoft 365-apps voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="52bce-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="52bce-153">Procedure: een basispagina toepassen op een site in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="52bce-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525627)
  
[<span data-ttu-id="52bce-154">Procedure: een pagina-indeling maken in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="52bce-154">How to: Create a page layout in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525628)
