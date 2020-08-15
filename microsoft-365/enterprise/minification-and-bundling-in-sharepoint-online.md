---
title: Minification en bundeling in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
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
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Meer informatie over het gebruik van minification en bundel technieken met Web Essentials voor minder HTTP-aanvragen en de manier waarop u pagina's laadt in SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688987"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="6a95b-103">Minification en bundeling in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6a95b-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="6a95b-104">In dit artikel wordt uitgelegd hoe u minification en bundel technieken met Web Essentials gebruikt om het aantal HTTP-aanvragen te verminderen en de tijd te besparen voor het laden van pagina's in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6a95b-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="6a95b-105">Wanneer u uw website aanpast, kunt u het toevoegen van een groot aantal extra bestanden op de server beëindigen om de aanpassing te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="6a95b-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="6a95b-106">Door extra JavaScript, CSS en afbeeldingen toe te voegen, wordt het aantal HTTP-aanvragen voor de server verhoogd waarmee de tijd die het duurt voor het weergeven van een webpagina groter wordt.</span><span class="sxs-lookup"><span data-stu-id="6a95b-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="6a95b-107">Als u meerdere bestanden van hetzelfde type hebt, kunt u deze bestanden bundelen om sneller het downloaden van deze bestanden uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="6a95b-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="6a95b-108">Voor JavaScript-en CSS-bestanden kunt u ook gebruikmaken van een methode met de naam minification, waarbij u de totale grootte van bestanden beperkt door witruimte en andere tekens die niet nodig zijn te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="6a95b-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="6a95b-109">Minification en bundeling van JavaScript en CSS-bestanden met Web Essentials</span><span class="sxs-lookup"><span data-stu-id="6a95b-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="6a95b-110">U kunt software van derden gebruiken, zoals web Essentials, om CSS-en JavaScript-bestanden te bundelen.</span><span class="sxs-lookup"><span data-stu-id="6a95b-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6a95b-111">Web Essentials is een derde, openende bron-, op Community gebaseerd project.</span><span class="sxs-lookup"><span data-stu-id="6a95b-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="6a95b-112">De software is een uitbreiding op Visual Studio 2012 en Visual Studio 2013 en wordt niet ondersteund door Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a95b-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="6a95b-113">Bezoek de website op de website van uw voor het downloaden van web Essentials [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) .</span><span class="sxs-lookup"><span data-stu-id="6a95b-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="6a95b-114">Web Essentials biedt twee soorten bundeling:</span><span class="sxs-lookup"><span data-stu-id="6a95b-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="6a95b-115">. bundel: voor CSS-en JavaScript-bestanden</span><span class="sxs-lookup"><span data-stu-id="6a95b-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="6a95b-116">. Sprite: voor afbeeldingen (alleen beschikbaar in Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="6a95b-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="6a95b-117">U kunt web Essentials gebruiken als u een bestaande functie hebt voor bepaalde huisstijl elementen waarnaar wordt verwezen in een aangepaste basispagina, zoals:</span><span class="sxs-lookup"><span data-stu-id="6a95b-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![Schermafbeelding van het merk element in de aangepaste basispagina](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="6a95b-119">**Een TE000127218 en CSS-bundel maken in Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="6a95b-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="6a95b-120">Selecteer in Visual Studio in Solution Explorer de bestanden die u wilt opnemen in de bundel.</span><span class="sxs-lookup"><span data-stu-id="6a95b-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="6a95b-121">Klik met de rechtermuisknop op de geselecteerde bestanden en selecteer vervolgens **Web Essentials** - \> **bundelbestand maken** in het contextmenu.</span><span class="sxs-lookup"><span data-stu-id="6a95b-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="6a95b-122">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6a95b-122">For example:</span></span> 
    
    ![Schermafbeelding van de menu opties voor het werken met Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="6a95b-124">De resultaten van het bundelen van JavaScript-en CSS-bestanden bekijken</span><span class="sxs-lookup"><span data-stu-id="6a95b-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="6a95b-125">Wanneer u een JavaScript-en CSS-bundel maakt, wordt met Web Essentials een XML-bestand gemaakt, een recept bestand met de naam van de JavaScript-en CSS-bestanden en andere configuratiegegevens:</span><span class="sxs-lookup"><span data-stu-id="6a95b-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![Schermafbeelding van recept-bestand voor JavaScript en CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="6a95b-127">Als de vlag Minify is ingesteld op waar in het bundelen van het recept, worden de bestanden kleiner en gegroepeerd.</span><span class="sxs-lookup"><span data-stu-id="6a95b-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="6a95b-128">Dit betekent dat er nieuwe, minified-versies van de JavaScript-bestanden zijn gemaakt waarnaar u op de basispagina kunt verwijzen.</span><span class="sxs-lookup"><span data-stu-id="6a95b-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![Schermafbeelding van de vlag Minify ingesteld op waar](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="6a95b-130">Wanneer u een pagina van uw website laadt, kunt u de hulpmiddelen voor ontwikkelaars in uw webbrowser gebruiken, zoals Internet Explorer 11, om het aantal aanvragen te zien dat naar de server is verzonden en hoelang elk bestand moet worden geladen.</span><span class="sxs-lookup"><span data-stu-id="6a95b-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="6a95b-131">De volgende afbeelding is het resultaat van het laden van de JavaScript-en CSS-bestanden voor minification.</span><span class="sxs-lookup"><span data-stu-id="6a95b-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![Schermafbeelding met het downloaden van 80-items](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="6a95b-133">Na het bundelen van de CSS-en JavaScript-bestanden, is het aantal aanvragen gedaald tot 74 en duurde het slechts iets langer om elk bestand te downloaden dan de oorspronkelijke bestanden:</span><span class="sxs-lookup"><span data-stu-id="6a95b-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![Schermafbeelding met het downloaden van 74-items](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="6a95b-135">Na het bundelen is het JavaScript-bundelbestand aanzienlijk verkleind van 815KB in 365KB:</span><span class="sxs-lookup"><span data-stu-id="6a95b-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![Schermafbeelding met gereduceerde downloadgrootte](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="6a95b-137">Afbeeldingen bundelen door een afbeeldings sprite te maken</span><span class="sxs-lookup"><span data-stu-id="6a95b-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="6a95b-138">Net als in de manier waarop u JavaScript-en CSS-bestanden bundelt, kunt u een groot aantal kleine pictogrammen en andere gemeenschappelijke afbeeldingen combineren in een groter etiketvel en de afzonderlijke afbeeldingen met CSS weergeven.</span><span class="sxs-lookup"><span data-stu-id="6a95b-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="6a95b-139">In plaats van elke afzonderlijke afbeelding te downloaden, downloadt de webbrowser van de gebruiker de sprite-blad eenmaal en slaat u het vervolgens op in de lokale computer.</span><span class="sxs-lookup"><span data-stu-id="6a95b-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="6a95b-140">Hierdoor wordt de prestaties van de pagina geladen en worden de pagina's gepaard met het aantal downloads.</span><span class="sxs-lookup"><span data-stu-id="6a95b-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="6a95b-141">**Een afbeeldings sprite maken in Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="6a95b-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="6a95b-142">Selecteer in Visual Studio in Solution Explorer de bestanden die u wilt opnemen in de bundel.</span><span class="sxs-lookup"><span data-stu-id="6a95b-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="6a95b-143">Klik met de rechtermuisknop op de geselecteerde bestanden en selecteer vervolgens **Web Essentials** , \> **Maak afbeelding sprite** in het contextmenu.</span><span class="sxs-lookup"><span data-stu-id="6a95b-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="6a95b-144">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6a95b-144">For example:</span></span> 
    
    ![Schermafbeelding waarin wordt getoond hoe u een afbeeldings sprite maakt](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="6a95b-146">Kies een locatie om het bestand sprite op te slaan.</span><span class="sxs-lookup"><span data-stu-id="6a95b-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="6a95b-147">Het bestand. Sprite is een XML-bestand waarin de instellingen en bestanden van de sprite worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="6a95b-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="6a95b-148">In de volgende afbeelding ziet u een voorbeeld van een sprite PNG-bestand en het bijbehorende XML-bestand. sprite.</span><span class="sxs-lookup"><span data-stu-id="6a95b-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![Schermafbeelding van een sprite-bestand](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Schermafbeelding van Sprite-XML-bestand](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

