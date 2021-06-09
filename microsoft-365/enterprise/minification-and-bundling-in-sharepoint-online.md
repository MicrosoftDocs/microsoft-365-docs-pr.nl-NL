---
title: Minificatie en bundeling in SharePoint Online
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
description: Meer informatie over het gebruik van minificatie- en bundelingstechnieken met Web Essentials om HTTP-aanvragen te beperken en de tijd die nodig is om pagina's te laden in SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688987"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="d6c0d-103">Minificatie en bundeling in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d6c0d-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="d6c0d-104">In dit artikel wordt beschreven hoe u minificatie- en bundelingstechnieken gebruikt met Web Essentials om het aantal HTTP-aanvragen te verminderen en de tijd te beperken die nodig is om pagina's in SharePoint Online te laden.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="d6c0d-105">Wanneer u uw website aanpast, kunt u uiteindelijk een groot aantal extra bestanden toevoegen aan de server ter ondersteuning van de aanpassing.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="d6c0d-106">Als u extra JavaScript, CSS en afbeeldingen toevoegt, neemt het aantal HTTP-aanvragen toe aan de server, waardoor de weergave van een webpagina langer duurt.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="d6c0d-107">Als u meerdere bestanden van hetzelfde type hebt, kunt u deze bestanden bundelen, zodat u deze bestanden sneller kunt downloaden.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="d6c0d-108">Voor JavaScript- en CSS-bestanden kunt u ook een methode genaamd minification gebruiken, waarbij u de totale grootte van bestanden verkleint door whitespace en andere tekens te verwijderen die niet nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="d6c0d-109">JavaScript- en CSS-bestanden minification en bundelen met Web Essentials</span><span class="sxs-lookup"><span data-stu-id="d6c0d-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="d6c0d-110">U kunt software van derden, zoals Web Essentials, gebruiken om CSS- en JavaScript-bestanden te bundelen.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6c0d-111">Web Essentials is een project van derden, open-source, community-based.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="d6c0d-112">De software is een uitbreiding naar Visual Studio 2012 en Visual Studio 2013 en wordt niet ondersteund door Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="d6c0d-113">Als u Web Essentials wilt downloaden, gaat u naar de website op [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) .</span><span class="sxs-lookup"><span data-stu-id="d6c0d-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="d6c0d-114">Web Essentials biedt twee vormen van bundeling:</span><span class="sxs-lookup"><span data-stu-id="d6c0d-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="d6c0d-115">.bundle: voor CSS- en JavaScript-bestanden</span><span class="sxs-lookup"><span data-stu-id="d6c0d-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="d6c0d-116">.sprite: voor afbeeldingen (alleen beschikbaar in Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="d6c0d-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="d6c0d-117">U kunt Web Essentials gebruiken als u een bestaande functie hebt met enkele huisstijlelementen waarnaar wordt verwezen op een aangepaste basispagina, zoals:</span><span class="sxs-lookup"><span data-stu-id="d6c0d-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![Schermafbeelding van merkelement op aangepaste basispagina](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="d6c0d-119">**Een TE000127218- en CSS-bundel maken in Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="d6c0d-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="d6c0d-120">Selecteer Visual Studio in Solution Explorer de bestanden die u in de bundel wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="d6c0d-121">Klik met de rechtermuisknop op de geselecteerde bestanden en selecteer **vervolgens Web Essentials** \> **JavaScript-bundelbestand maken** in het contextmenu.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="d6c0d-122">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d6c0d-122">For example:</span></span> 
    
    ![Schermafbeelding met menuopties voor Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="d6c0d-124">De resultaten van het bundelen van JavaScript- en CSS-bestanden weergeven</span><span class="sxs-lookup"><span data-stu-id="d6c0d-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="d6c0d-125">Wanneer u een JavaScript- en CSS-bundel maakt, wordt in Web Essentials een XML-bestand gemaakt dat een receptbestand wordt genoemd waarin de JavaScript- en CSS-bestanden worden geïdentificeerd, evenals enkele andere configuratiegegevens:</span><span class="sxs-lookup"><span data-stu-id="d6c0d-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![Schermafbeelding van het JavaScript- en CSS-receptbestand](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="d6c0d-127">Als de minify-vlag is ingesteld op waar in het bundelingsrecept, worden de bestanden bovendien verkleind en gebundeld.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="d6c0d-128">Dit betekent dat er nieuwe, minified versies van de JavaScript-bestanden zijn gemaakt waarnaar u op de basispagina kunt verwijzen.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![Schermafbeelding van de minify-vlag die is ingesteld op waar](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="d6c0d-130">Wanneer u een pagina laadt vanaf uw website, kunt u de hulpprogramma's voor ontwikkelaars vanuit uw webbrowser, zoals Internet Explorer 11, gebruiken om het aantal aanvragen te bekijken dat naar de server is verzonden en hoe lang het laden van elk bestand duurde.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="d6c0d-131">De volgende afbeelding is het resultaat van het laden van de JavaScript- en CSS-bestanden vóór minificatie.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![Schermafbeelding van 80 items die worden gedownload](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="d6c0d-133">Na het bundelen van de CSS- en JavaScript-bestanden is het aantal aanvragen gedaald tot 74 en duurde het downloaden van elk bestand iets langer dan de oorspronkelijke bestanden afzonderlijk:</span><span class="sxs-lookup"><span data-stu-id="d6c0d-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![Schermafbeelding van 74 items die worden gedownload](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="d6c0d-135">Na bundeling wordt het JavaScript-bundelbestand aanzienlijk teruggebracht van 815 KB naar 365 KB:</span><span class="sxs-lookup"><span data-stu-id="d6c0d-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![Schermafbeelding met een kleinere downloadgrootte](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="d6c0d-137">Afbeeldingen bundelen door een afbeeldingsspite te maken</span><span class="sxs-lookup"><span data-stu-id="d6c0d-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="d6c0d-138">Net zoals u JavaScript- en CSS-bestanden bundelt, kunt u veel kleine pictogrammen en andere veelgebruikte afbeeldingen combineren tot een groter spriteblad en vervolgens CSS gebruiken om de afzonderlijke afbeeldingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="d6c0d-139">In plaats van elke afzonderlijke afbeelding te downloaden, downloadt de webbrowser van de gebruiker het spriteblad eenmaal en cachet deze vervolgens op de lokale computer.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="d6c0d-140">Dit verbetert de laadprestaties van pagina's door het aantal downloads en retouren naar de webserver te beperken.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="d6c0d-141">**Een afbeeldingsspite maken in Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="d6c0d-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="d6c0d-142">Selecteer Visual Studio in Solution Explorer de bestanden die u in de bundel wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="d6c0d-143">Klik met de rechtermuisknop op de geselecteerde bestanden en selecteer **vervolgens Web Essentials** \> **Afbeelding maken sprite** in het contextmenu.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="d6c0d-144">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d6c0d-144">For example:</span></span> 
    
    ![Schermafbeelding van het maken van een afbeeldingsspite](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="d6c0d-146">Kies een locatie om het sprite-bestand op te slaan.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="d6c0d-147">Het SPRITE-bestand is een XML-bestand waarin de instellingen en bestanden in de sprite worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="d6c0d-148">In de volgende cijfers wordt een voorbeeld van een sprite PNG-bestand en het bijbehorende .sprite XML-bestand ervan becijferd.</span><span class="sxs-lookup"><span data-stu-id="d6c0d-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![Schermafbeelding van een spritebestand](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Schermafbeelding van sprite XML-bestand](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

