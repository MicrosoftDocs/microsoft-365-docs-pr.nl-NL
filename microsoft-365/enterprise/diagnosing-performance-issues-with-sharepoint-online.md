---
title: Prestatieproblemen diagnosticeren met SharePoint Online
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
description: In dit artikel wordt beschreven hoe u veelvoorkomende problemen met uw SharePoint onlinesite kunt opsporen met behulp van hulpprogramma's voor ontwikkelaars van Internet Explorer.
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927610"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="c7ac1-103">Prestatieproblemen diagnosticeren met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c7ac1-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="c7ac1-104">In dit artikel wordt beschreven hoe u veelvoorkomende problemen met uw SharePoint onlinesite kunt opsporen met behulp van hulpprogramma's voor ontwikkelaars van Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="c7ac1-105">Er zijn drie verschillende manieren waarop u kunt vaststellen dat een pagina op een SharePoint Online-site een prestatieprobleem heeft met de aanpassingen.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="c7ac1-106">De netwerkmonitor van de F12-werkbalk</span><span class="sxs-lookup"><span data-stu-id="c7ac1-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="c7ac1-107">Vergelijking met een niet-aangepaste basislijn</span><span class="sxs-lookup"><span data-stu-id="c7ac1-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="c7ac1-108">SharePoint Metrische onlinereactiekoppen</span><span class="sxs-lookup"><span data-stu-id="c7ac1-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="c7ac1-109">In dit onderwerp wordt beschreven hoe u elk van deze methoden kunt gebruiken om prestatieproblemen te diagnosticeren.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="c7ac1-110">Nadat u de oorzaak van het probleem hebt gevonden, kunt u naar een oplossing werken met behulp van de artikelen over het verbeteren van SharePoint prestaties die u kunt vinden op https://aka.ms/tune .</span><span class="sxs-lookup"><span data-stu-id="c7ac1-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="c7ac1-111">De werkbalk F12 gebruiken om de prestaties te diagnosticeren in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c7ac1-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="c7ac1-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ac1-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="c7ac1-113">In dit artikel gebruiken we Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="c7ac1-114">Versies van de hulpprogramma's voor F12-ontwikkelaars in andere browsers hebben vergelijkbare functies, hoewel ze er mogelijk iets anders uitzien.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="c7ac1-115">Zie de volgende informatie over de hulpprogramma's voor F12-ontwikkelaars:</span><span class="sxs-lookup"><span data-stu-id="c7ac1-115">For information on the F12 developer tools, see:</span></span>
  
- <span data-ttu-id="c7ac1-116">[Nieuwe functies in F12-hulpprogramma's](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="c7ac1-116">[What's new in F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span></span>

- <span data-ttu-id="c7ac1-117">[De hulpprogramma's voor F12-ontwikkelaars gebruiken](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="c7ac1-117">[Using the F12 developer tools](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span></span>

<span data-ttu-id="c7ac1-118">Druk op **F12** om de hulpprogramma's voor ontwikkelaars weer te geven en klik vervolgens op Wi-Fi pictogram:</span><span class="sxs-lookup"><span data-stu-id="c7ac1-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Schermafbeelding van het wifi-pictogram hulpprogramma's voor F12-ontwikkelaars](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="c7ac1-120">Druk op **het** tabblad Netwerk op de groene knop Afspelen om een pagina te laden.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="c7ac1-121">Het hulpprogramma retourneert alle bestanden die door de browser worden opgevraagd om de pagina te krijgen waar u om hebt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="c7ac1-122">In de volgende schermafbeelding ziet u een dergelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-122">The following screen shot shows one such list.</span></span>
  
![Schermafbeelding van de lijst met bestanden die zijn geretourneerd met een paginaaanvraag.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="c7ac1-124">U kunt ook de downloadtijden van de bestanden aan de rechterkant zien, zoals wordt weergegeven in deze schermafbeelding.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Diagram met de tijd die nodig is voor het laden van de aangevraagde pagina's SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="c7ac1-126">Dit geeft een visuele weergave van hoe lang het bestand heeft moeten worden geladen.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="c7ac1-127">De groene lijn geeft aan wanneer de pagina klaar is om door de browser te worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="c7ac1-128">Hierdoor hebt u snel een overzicht van de verschillende bestanden die mogelijk leiden tot trage paginabelastingen op uw site.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="c7ac1-129">Een niet-aangepaste basislijn instellen voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c7ac1-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="c7ac1-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ac1-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="c7ac1-131">De beste manier om de zwakke punten van de prestaties van uw site te bepalen, is door een volledig kant-en-klaar siteverzameling in te stellen in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="c7ac1-132">Op deze manier kunt u alle verschillende aspecten van uw site vergelijken met wat u zou krijgen zonder aanpassing op de pagina.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="c7ac1-133">De OneDrive voor Bedrijven startpagina is een goed voorbeeld van een afzonderlijke siteverzameling die waarschijnlijk geen aanpassingen bevat.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="c7ac1-134">Informatie SharePoint antwoordkop weergeven</span><span class="sxs-lookup"><span data-stu-id="c7ac1-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="c7ac1-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ac1-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="c7ac1-136">In SharePoint Online hebt u toegang tot de gegevens die worden teruggestuurd naar de browser in de antwoordkop voor elk bestand.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="c7ac1-137">De meest nuttige waarde voor het diagnosticeren van prestatieproblemen is **SPRequestDuration,** waarmee de hoeveelheid tijd wordt weergegeven die de aanvraag op de server heeft genomen om te worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="c7ac1-138">Dit kan helpen bepalen of de aanvraag erg zwaar en resourceintensief is.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="c7ac1-139">Dit is het beste inzicht dat u hebt in hoeveel werk de server doet om de pagina te bedienen.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="c7ac1-140">Informatie over SharePoint koptekst weergeven</span><span class="sxs-lookup"><span data-stu-id="c7ac1-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="c7ac1-141">Controleer of de F12-hulpprogramma's zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="c7ac1-142">Zie Nieuwe functies [in F12-hulpprogramma's](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))voor meer informatie over het downloaden en installeren van deze hulpprogramma's.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-142">For more information on downloading and installing these tools, see [What's new in F12 tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).</span></span>

2. <span data-ttu-id="c7ac1-143">Druk in de F12-hulpmiddelen op het tabblad **Netwerk** op de groene knop Afspelen om een pagina te laden.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="c7ac1-144">Klik op een van de .aspx-bestanden die door het hulpprogramma worden geretourneerd en klik vervolgens op **DETAILS.**</span><span class="sxs-lookup"><span data-stu-id="c7ac1-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Toont details van de antwoordkop](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="c7ac1-146">Klik **op Antwoordkoppen**.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-146">Click **Response headers**.</span></span>

    ![Diagram met de URL van de antwoordkoptekst](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="c7ac1-148">Wat veroorzaakt prestatieproblemen in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="c7ac1-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="c7ac1-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ac1-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="c7ac1-150">In het artikel Navigatieopties voor [SharePoint Online](navigation-options-for-sharepoint-online.md) wordt een voorbeeld weergegeven van het gebruik van de waarde SPRequestDuration om te bepalen dat de ingewikkelde structurele navigatie ervoor zorgde dat de pagina lang op de server werd verwerkt.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="c7ac1-151">Door een waarde te nemen voor een basislijnsite (zonder aanpassing), is het mogelijk om te bepalen of het laden van een bepaald bestand lang duurt.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="c7ac1-152">Het voorbeeld dat wordt gebruikt in [navigatieopties voor SharePoint Online](navigation-options-for-sharepoint-online.md) is het hoofdbestand .aspx.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="c7ac1-153">Dat bestand bevat de meeste ASP.NET code die wordt uitgevoerd voor het laden van de pagina.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="c7ac1-154">Afhankelijk van de sitesjabloon die u gebruikt, kan dit start.aspx, home.aspx, default.aspx of een andere naam zijn als u de startpagina aan te passen.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="c7ac1-155">Als dit getal aanzienlijk hoger is dan uw basislijnsite, is dit een goede indicatie dat er iets complexs aan de hand is op uw pagina dat prestatieproblemen veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="c7ac1-156">Nadat u hebt vastgesteld dat er een specifiek probleem is voor uw site, kunt u de beste manier vinden om erachter te komen wat de slechte prestaties veroorzaakt door alle mogelijke oorzaken te verwijderen, zoals paginaaanpassingen, en deze vervolgens een voor een toe te voegen aan de site.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="c7ac1-157">Nadat u voldoende aanpassingen hebt verwijderd dat de pagina goed presteert, kunt u vervolgens specifieke aanpassingen een voor een toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="c7ac1-158">Als u bijvoorbeeld een zeer complexe navigatie hebt, kunt u de navigatie wijzigen om geen subsites weer te geven. Controleer vervolgens de hulpprogramma's voor ontwikkelaars om te zien of dit een verschil maakt.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="c7ac1-159">Of als u een grote hoeveelheid inhouds roll-ups hebt, probeert u deze van uw pagina te verwijderen en te kijken of dit de zaken verbetert.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="c7ac1-160">Als u alle mogelijke oorzaken wegwerkt en deze in één voor één toevoegt, kunt u eenvoudig bepalen welke functies het grootste probleem zijn en vervolgens naar een oplossing werken.</span><span class="sxs-lookup"><span data-stu-id="c7ac1-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>