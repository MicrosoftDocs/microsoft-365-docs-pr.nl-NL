---
title: Prestatieproblemen met SharePoint Online vaststellen
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: In dit artikel leest u hoe u met de ontwikkelhulpprogramma's van Internet Explorer veelvoorkomende problemen met uw SharePoint Online-site kunt vaststellen.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689178"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="8eecf-103">Prestatieproblemen met SharePoint Online vaststellen</span><span class="sxs-lookup"><span data-stu-id="8eecf-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="8eecf-104">In dit artikel leest u hoe u met de ontwikkelhulpprogramma's van Internet Explorer veelvoorkomende problemen met uw SharePoint Online-site kunt vaststellen.</span><span class="sxs-lookup"><span data-stu-id="8eecf-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="8eecf-105">Er zijn drie verschillende manieren waarop u kunt bepalen of een pagina van een SharePoint Online-site een prestatieprobleem heeft vanwege de aanpassingen.</span><span class="sxs-lookup"><span data-stu-id="8eecf-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="8eecf-106">De Netwerkmonitor van F12-werkbalk</span><span class="sxs-lookup"><span data-stu-id="8eecf-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="8eecf-107">Vergelijking met een niet-aangepaste basislijn</span><span class="sxs-lookup"><span data-stu-id="8eecf-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="8eecf-108">Metrische gegevens voor SharePoint Online-antwoordheaders</span><span class="sxs-lookup"><span data-stu-id="8eecf-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="8eecf-109">In dit onderwerp wordt beschreven hoe u al deze methoden kunt gebruiken om problemen met de prestaties op te lossen.</span><span class="sxs-lookup"><span data-stu-id="8eecf-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="8eecf-110">Als u een probleem hebt met de oorzaak van het probleem, kunt u naar een oplossing werken met behulp van de artikelen over het verbeteren van de prestaties van SharePoint, waarop u kunt zoeken https://aka.ms/tune .</span><span class="sxs-lookup"><span data-stu-id="8eecf-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="8eecf-111">De werkbalk van F12 gebruiken om de prestaties van SharePoint Online te analyseren</span><span class="sxs-lookup"><span data-stu-id="8eecf-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="8eecf-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="8eecf-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="8eecf-113">In dit artikel wordt beschreven hoe u Internet Explorer 11 gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8eecf-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="8eecf-114">Versies van de F12-hulpprogramma's voor ontwikkelaars in andere browsers hebben soortgelijke functies, maar deze kunnen er enigszins anders uitzien.</span><span class="sxs-lookup"><span data-stu-id="8eecf-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="8eecf-115">Zie voor meer informatie over de F12-hulpprogramma's voor ontwikkelaars:</span><span class="sxs-lookup"><span data-stu-id="8eecf-115">For information on the F12 developer tools, see:</span></span>
  
- [<span data-ttu-id="8eecf-116">Nieuw in F12-hulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="8eecf-116">What's new in F12 Tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [<span data-ttu-id="8eecf-117">Met de F12-hulpprogramma's voor ontwikkelaars</span><span class="sxs-lookup"><span data-stu-id="8eecf-117">Using the F12 developer tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522546)

<span data-ttu-id="8eecf-118">Druk op **F12** om de hulpprogramma's voor ontwikkelaars weer te geven en klik op het Wi-Fi-pictogram:</span><span class="sxs-lookup"><span data-stu-id="8eecf-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Schermafbeelding van F12-pictogram van hulpmiddelen voor ontwikkelaars](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="8eecf-120">Druk op het tabblad **netwerk** op de groene afspeelknop om de pagina te laden.</span><span class="sxs-lookup"><span data-stu-id="8eecf-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="8eecf-121">Het hulpmiddel retourneert alle bestanden die in de browser worden aangevraagd om de gewenste pagina te vinden.</span><span class="sxs-lookup"><span data-stu-id="8eecf-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="8eecf-122">In de volgende schermafbeelding wordt een lijst weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8eecf-122">The following screen shot shows one such list.</span></span>
  
![Schermafbeelding van de lijst met bestanden geretourneerd met een pagina-aanvraag.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="8eecf-124">U kunt ook de downloadtijden van de bestanden aan de rechterkant zien, zoals in deze schermafbeelding wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8eecf-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Diagram met de tijd die nodig is voor het laden van de gevraagde pagina's van SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="8eecf-126">Zo krijgt u een visuele weergave van hoe lang het bestand moet worden geladen.</span><span class="sxs-lookup"><span data-stu-id="8eecf-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="8eecf-127">Als de pagina klaar is om te worden weergegeven in de browser, wordt de groene lijn aangegeven.</span><span class="sxs-lookup"><span data-stu-id="8eecf-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="8eecf-128">U kunt nu een snel overzicht van de verschillende bestanden weergeven die tot gevolg kunnen hebben dat er trage pagina wordt geladen op uw site.</span><span class="sxs-lookup"><span data-stu-id="8eecf-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="8eecf-129">Een niet-aangepaste basislijn instellen voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8eecf-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="8eecf-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="8eecf-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="8eecf-131">De beste manier om de prestaties van uw site te bepalen, is door een volledig ouder-siteverzameling in SharePoint Online in te stellen.</span><span class="sxs-lookup"><span data-stu-id="8eecf-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="8eecf-132">Op deze manier kunt u alle verschillende aspecten van uw site vergelijken en wat u ook verkrijgt zonder dat u op de pagina aan te passen.</span><span class="sxs-lookup"><span data-stu-id="8eecf-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="8eecf-133">De startpagina van OneDrive voor bedrijven is een goed voorbeeld van een afzonderlijke siteverzameling die waarschijnlijk geen aanpassingen bevat.</span><span class="sxs-lookup"><span data-stu-id="8eecf-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="8eecf-134">Info over informatie in de SharePoint-antwoord weergeven</span><span class="sxs-lookup"><span data-stu-id="8eecf-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="8eecf-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="8eecf-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="8eecf-136">In SharePoint Online kunt u via de antwoordheader voor elk bestand toegang krijgen tot de informatie die naar de browser wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="8eecf-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="8eecf-137">De meest nuttige waarde voor het vaststellen van prestatieproblemen is **SPRequestDuration**, waarmee de hoeveelheid tijd wordt weergegeven die de aanvraag heeft uitgevoerd op de server.</span><span class="sxs-lookup"><span data-stu-id="8eecf-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="8eecf-138">Dit kan u helpen om te bepalen of de aanvraag erg zwaar is en veel bronnen.</span><span class="sxs-lookup"><span data-stu-id="8eecf-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="8eecf-139">Dit is het beste inzicht in de manier waarop de server de pagina uitvoert.</span><span class="sxs-lookup"><span data-stu-id="8eecf-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="8eecf-140">Informatie over de koptekst van een SharePoint-antwoord weergeven</span><span class="sxs-lookup"><span data-stu-id="8eecf-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="8eecf-141">Zorg ervoor dat de F12-hulpprogramma's is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="8eecf-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="8eecf-142">Zie [Nieuw in de F12-hulpprogramma's](https://go.microsoft.com/fwlink/p/?LinkId=522545)voor meer informatie over het downloaden en installeren van deze hulpmiddelen.</span><span class="sxs-lookup"><span data-stu-id="8eecf-142">For more information on downloading and installing these tools, see [What's new in F12 tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).</span></span>

2. <span data-ttu-id="8eecf-143">Druk in de F12-hulpprogramma's op het tabblad **netwerk** op de groene afspeelknop om de pagina te laden.</span><span class="sxs-lookup"><span data-stu-id="8eecf-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="8eecf-144">Klik op een van de geretourneerde aspx-bestanden en klik vervolgens op **Details**.</span><span class="sxs-lookup"><span data-stu-id="8eecf-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Toont details van de antwoordheader](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="8eecf-146">Klik op **antwoordheaders**.</span><span class="sxs-lookup"><span data-stu-id="8eecf-146">Click **Response headers**.</span></span>

    ![Diagram met de URL van de antwoordheader](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="8eecf-148">Wat veroorzaakten prestatieproblemen in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="8eecf-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="8eecf-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="8eecf-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="8eecf-150">In het artikel [Navigatieopties voor SharePoint Online](navigation-options-for-sharepoint-online.md) wordt een voorbeeld van het gebruik van de SPRequestDuration-waarde weergegeven om te bepalen dat de pagina veel tijd in beslag nemen op de server.</span><span class="sxs-lookup"><span data-stu-id="8eecf-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="8eecf-151">Door een waarde voor een basislijn site te maken (zonder aanpassing), kunt u bepalen of een bepaald bestand veel tijd in beslag neemt.</span><span class="sxs-lookup"><span data-stu-id="8eecf-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="8eecf-152">Het voorbeeld dat in [Navigatieopties voor SharePoint Online](navigation-options-for-sharepoint-online.md) wordt gebruikt, is het belangrijkste aspx-bestand.</span><span class="sxs-lookup"><span data-stu-id="8eecf-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="8eecf-153">Dit bestand bevat de meeste ASP.NET-code die wordt uitgevoerd voor het laden van pagina's.</span><span class="sxs-lookup"><span data-stu-id="8eecf-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="8eecf-154">Afhankelijk van de sitesjabloon die u gebruikt, is het mogelijk dat u het volgende start. aspx, Home. aspx, default. aspx of een andere naam krijgt als u de startpagina aanpast.</span><span class="sxs-lookup"><span data-stu-id="8eecf-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="8eecf-155">Als dit getal aanzienlijk groter is dan de site van de basislijn, is het een goede aanwijzing dat er op de pagina een ingewikkelde uitzondering is op de pagina die prestatieproblemen veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="8eecf-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="8eecf-156">Als u hebt vastgesteld dat een probleem specifiek is voor uw site, kunt u het beste de beste oorzaken van de prestaties van een site verwijderen door de mogelijke oorzaken te elimineren, zoals aanpassingen van pagina's, en ze vervolgens één voor één op de site weer toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="8eecf-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="8eecf-157">Wanneer u de aanpassingen van de pagina hebt verwijderd, kunt u deze op een bepaalde manier opnieuw toevoegen.</span><span class="sxs-lookup"><span data-stu-id="8eecf-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="8eecf-158">Als u bijvoorbeeld een zeer ingewikkelde navigatie hebt, probeer dan de navigatie te wijzigen, zodat subsites niet worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8eecf-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="8eecf-159">Of als u een grote hoeveelheid inhouds samenvoeging hebt, verwijdert u deze van uw pagina en kunt u zien of het nu beter is.</span><span class="sxs-lookup"><span data-stu-id="8eecf-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="8eecf-160">Als u alle mogelijke oorzaken uitschakelt en ze in één keer toevoegt, kunt u gemakkelijk vaststellen welke functies het grootste probleem zijn en vervolgens naar een oplossing werken.</span><span class="sxs-lookup"><span data-stu-id="8eecf-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>
