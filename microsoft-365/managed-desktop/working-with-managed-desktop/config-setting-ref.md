---
title: Verwijzing naar configureerbare instellingen voor Microsoft Managed Desktop
description: Categorieën instellen voor configureerbare instellingen in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c3f8aec244b1b0685b8293fda0b048d662c7cef2
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529359"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="a0ece-104">Referentie voor configureerbare instellingen - Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a0ece-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="a0ece-105">In dit onderwerp worden de instellingencategorieën weergegeven die klanten kunnen configureren met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="a0ece-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="a0ece-106">Elke instellingscategorie bevat informatie over vereisten, aanbevolen procedures en hoe u de instellingscategorie aanpassen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="a0ece-107">Bureaubladachtergrondafbeelding</span><span class="sxs-lookup"><span data-stu-id="a0ece-107">Desktop background picture</span></span>
<span data-ttu-id="a0ece-108">U de bureaubladachtergrondafbeelding aanpassen voor Microsoft Managed Desktop-apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a0ece-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="a0ece-109">U dit gebruiken om een bedrijfsmerk of marketingmateriaal toe te passen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="a0ece-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="a0ece-110">Requirements</span></span>

<span data-ttu-id="a0ece-111">Aan deze vereisten moet worden voldaan voor een achtergrondafbeelding op het bureaublad:</span><span class="sxs-lookup"><span data-stu-id="a0ece-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="a0ece-112">Afbeeldingsbestandsindeling - .jpg, jpeg of .png</span><span class="sxs-lookup"><span data-stu-id="a0ece-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="a0ece-113">Bestandslocatie - Host op een vertrouwde beveiligde http (https) locatie.</span><span class="sxs-lookup"><span data-stu-id="a0ece-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="a0ece-114">Niet toegestaan - Http- en bestandsshare-locaties (unc) worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="a0ece-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="a0ece-115">Bureaubladachtergrondafbeelding aanpassen en implementeren</span><span class="sxs-lookup"><span data-stu-id="a0ece-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="a0ece-116">**Een aangepaste bureaubladachtergrondafbeelding toevoegen**</span><span class="sxs-lookup"><span data-stu-id="a0ece-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="a0ece-117">Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a0ece-117">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a0ece-118">Selecteer **Configureerbaar**onder **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a0ece-119">Selecteer **in Configureerbare** werkruimte **de optie Bureaubladachtergrondafbeelding**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="a0ece-120">Voer de locatie in van de afbeelding die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a0ece-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="a0ece-121">Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="a0ece-122">Startpagina's van de browser</span><span class="sxs-lookup"><span data-stu-id="a0ece-122">Browser start pages</span></span>
<span data-ttu-id="a0ece-123">Startpagina's in de browser worden geopend in afzonderlijke tabbladen wanneer uw gebruikers Microsoft Edge starten.</span><span class="sxs-lookup"><span data-stu-id="a0ece-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="a0ece-124">Als u het uw gebruikers gemakkelijk wilt maken om een set sites te openen die ze vaak gebruiken, voegt u voor elke site een startpagina van de browser toe.</span><span class="sxs-lookup"><span data-stu-id="a0ece-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="a0ece-125">Vereisten</span><span class="sxs-lookup"><span data-stu-id="a0ece-125">Requirements</span></span>

<span data-ttu-id="a0ece-126">U moet de volledig gekwalificeerde domeinnaam (FQDN) opgeven voor intranet- of internetsites voor startpagina's van uw browser.</span><span class="sxs-lookup"><span data-stu-id="a0ece-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="a0ece-127">Als interne sites zijn geconfigureerd, laat gebruikers weten dat toegang tot deze sites alleen is toegestaan wanneer ze zijn verbonden met het interne netwerk wanneer ze op kantoor zijn of wanneer ze zijn verbonden met een VPN-verbinding.</span><span class="sxs-lookup"><span data-stu-id="a0ece-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="a0ece-128">Startpagina's voor browser aanpassen en implementeren</span><span class="sxs-lookup"><span data-stu-id="a0ece-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="a0ece-129">**Een startpagina voor een browser toevoegen**</span><span class="sxs-lookup"><span data-stu-id="a0ece-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="a0ece-130">Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a0ece-130">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a0ece-131">Selecteer **Configureerbaar**onder **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a0ece-132">Selecteer **startpagina's voor browser in** **Configureerbare** werkruimte.</span><span class="sxs-lookup"><span data-stu-id="a0ece-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="a0ece-133">Selecteer **Startpagina toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="a0ece-134">Voer **op De startpagina van**de browser toevoegen de URL in voor de site die u wilt gebruiken en selecteer **Startpagina toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="a0ece-135">Herhaal stap 1-5 voor extra startpagina's voor de browser.</span><span class="sxs-lookup"><span data-stu-id="a0ece-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="a0ece-136">Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="a0ece-137">Locatie van de sitelijst in de ondernemingsmodus</span><span class="sxs-lookup"><span data-stu-id="a0ece-137">Enterprise mode site list location</span></span>

<span data-ttu-id="a0ece-138">Als u specifieke websites en apps hebt waarvan u weet dat ze compatibiliteitsproblemen hebben met Microsoft Edge, u de sitelijst voor de Ondernemingsmodus gebruiken, zodat de websites automatisch worden geopend met Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="a0ece-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="a0ece-139">Als u ook weet dat uw intranetsites niet correct gaan werken met Microsoft Edge, u alle intranetsites automatisch openen met Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="a0ece-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="a0ece-140">Als u de Enterprise-modus gebruikt, u Microsoft Edge blijven gebruiken als uw standaardbrowser, terwijl u er ook voor zorgen dat uw apps blijven werken op Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="a0ece-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="a0ece-141">Zie [Sitelijsten ondernemingsmodus en site in ondernemingsmodus](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)voor meer informatie over sitelijsten in de ondernemingsmodus .</span><span class="sxs-lookup"><span data-stu-id="a0ece-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="a0ece-142">U een https:// locatie opgeven of de locatie voor een intern aandeel waar u uw sitelijst in ondernemingsmodus hebt gehost.</span><span class="sxs-lookup"><span data-stu-id="a0ece-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="a0ece-143">Vereisten</span><span class="sxs-lookup"><span data-stu-id="a0ece-143">Requirements</span></span>

<span data-ttu-id="a0ece-144">Aan deze vereisten moet worden voldaan voor het lijstbestand van de site in de ondernemingsmodus:</span><span class="sxs-lookup"><span data-stu-id="a0ece-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="a0ece-145">Bestandsindeling - XML-bestand dat voldoet aan [bestandsvereisten](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="a0ece-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="a0ece-146">Bestandslocatie - Hostbestand op een interne https-locatie.</span><span class="sxs-lookup"><span data-stu-id="a0ece-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="a0ece-147">Niet toegestaan - Hosten op een intern bestandsaandeel, zoals *//sharename*, is niet toegestaan</span><span class="sxs-lookup"><span data-stu-id="a0ece-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="a0ece-148">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="a0ece-148">Best practices</span></span>

<span data-ttu-id="a0ece-149">Deze best practices worden aangeboden om klanten te helpen beslissingen te nemen om hun IT-infrastructuur te moderniseren:</span><span class="sxs-lookup"><span data-stu-id="a0ece-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="a0ece-150">**Kies een beperkt aantal sites** : Microsoft Managed Desktop gebruikt Microsoft Edge als de favoriete browser om de algehele beveiliging voor uw organisatie en bruikbaarheid voor uw gebruikers te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="a0ece-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="a0ece-151">De meeste sites in deze lijst zijn voor oudere web-apps die een oudere versie van een browser nodig hebben die niet zoveel beveiligingsfuncties bevat.</span><span class="sxs-lookup"><span data-stu-id="a0ece-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="a0ece-152">**Overweeg een alternatief** : overweeg een andere site of web-app waarvoor geen oudere browser nodig is.</span><span class="sxs-lookup"><span data-stu-id="a0ece-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="a0ece-153">Of overweeg de site bij te werken zodat deze nieuwere browsers kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a0ece-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="a0ece-154">Nieuwere browsers maken gebruik van de nieuwste technologie en helpen de beveiliging te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="a0ece-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="a0ece-155">Locatie van de lijst met de ondernemingssitemodus aanpassen en implementeren</span><span class="sxs-lookup"><span data-stu-id="a0ece-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="a0ece-156">**Locatie van een lijst met bedrijfssitemodus toevoegen**</span><span class="sxs-lookup"><span data-stu-id="a0ece-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="a0ece-157">Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a0ece-157">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="a0ece-158">Selecteer **Configureerbaar**onder **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="a0ece-159">Selecteer **in Configureerbare** werkruimte de locatie van de sitelijst in **de ondernemingsmodus**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="a0ece-160">Voer de https-locatie voor uw sitelijst in.</span><span class="sxs-lookup"><span data-stu-id="a0ece-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="a0ece-161">Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="a0ece-162">Vertrouwde sites</span><span class="sxs-lookup"><span data-stu-id="a0ece-162">Trusted sites</span></span>

<span data-ttu-id="a0ece-163">Vertrouwde sites stellen u in staat om beveiligingszones aan te passen, of waar een site kan worden gebruikt, voor verschillende sites.</span><span class="sxs-lookup"><span data-stu-id="a0ece-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="a0ece-164">Veiligheidszones zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="a0ece-164">Security zones include:</span></span> 
- <span data-ttu-id="a0ece-165">Zone 1 – Lokale intranetzone</span><span class="sxs-lookup"><span data-stu-id="a0ece-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="a0ece-166">Zone 2 – Zone Trusted sites</span><span class="sxs-lookup"><span data-stu-id="a0ece-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="a0ece-167">Zone 3 – Internetzone</span><span class="sxs-lookup"><span data-stu-id="a0ece-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="a0ece-168">Zone 4 – Zone Restricted Sites</span><span class="sxs-lookup"><span data-stu-id="a0ece-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="a0ece-169">Vereisten</span><span class="sxs-lookup"><span data-stu-id="a0ece-169">Requirements</span></span>

<span data-ttu-id="a0ece-170">Geef de volledig gekwalificeerde domeinnaam (FQDN) voor intranet of internetsites voor elke vertrouwde site.</span><span class="sxs-lookup"><span data-stu-id="a0ece-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="a0ece-171">Vertrouwde sites aanpassen en implementeren</span><span class="sxs-lookup"><span data-stu-id="a0ece-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="a0ece-172">**Een vertrouwde site toevoegen**</span><span class="sxs-lookup"><span data-stu-id="a0ece-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="a0ece-173">Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a0ece-173">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a0ece-174">Selecteer **Configureerbaar**onder **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a0ece-175">Selecteer **vertrouwde sites**in **Configureerbare** werkruimte en selecteer **Vervolgens Vertrouwde site toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="a0ece-176">Voer **op Vertrouwde site toevoegen**de URL in, kies een beveiligingszone en selecteer **Vervolgens Vertrouwde site toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="a0ece-177">Herhaal stap 1-4 voor elke vertrouwde site die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="a0ece-178">Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="a0ece-179">**Een vertrouwde site verwijderen**</span><span class="sxs-lookup"><span data-stu-id="a0ece-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="a0ece-180">Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a0ece-180">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a0ece-181">Selecteer **Configureerbaar**onder **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a0ece-182">Selecteer **vertrouwde sites**in **de werkruimte Configureerbaar.**</span><span class="sxs-lookup"><span data-stu-id="a0ece-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="a0ece-183">Selecteer de site die u wilt verwijderen en selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="a0ece-184">Herhaal stap 1-4 voor elke vertrouwde site die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="a0ece-185">Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="a0ece-186">Proxy</span><span class="sxs-lookup"><span data-stu-id="a0ece-186">Proxy</span></span>
<span data-ttu-id="a0ece-187">U netwerkproxy-instellingen voor uw organisatie beheren.</span><span class="sxs-lookup"><span data-stu-id="a0ece-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="a0ece-188">Voeg uw proxyserver en poortnummer toe en voeg vervolgens uitzonderingen op uw proxysite toe.</span><span class="sxs-lookup"><span data-stu-id="a0ece-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="a0ece-189">Microsoft Managed Desktop bevat een set standaardproxy-uitzonderingen die nodig zijn om de service te laten werken.</span><span class="sxs-lookup"><span data-stu-id="a0ece-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="a0ece-190">De standaarduitsluitingslijst kan alleen worden gewijzigd door de Microsoft Managed Desktop-service.</span><span class="sxs-lookup"><span data-stu-id="a0ece-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="a0ece-191">Zie [Netwerkconfiguratie voor Microsoft Managed Desktop voor](../get-ready/network.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a0ece-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="a0ece-192">De uitzonderingen op proxysite die u toevoegt in de Microsoft Managed Desktop-portal, worden toegevoegd aan de standaardproxy-uitzonderingen die zijn opgenomen in de Microsoft Managed Desktop-service.</span><span class="sxs-lookup"><span data-stu-id="a0ece-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="a0ece-193">Het bijwerken van de standaardlijst voor proxy-uitzondering wordt altijd geprioriteerd boven implementaties van klanten.</span><span class="sxs-lookup"><span data-stu-id="a0ece-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="a0ece-194">Dit betekent dat uw gefaseerde implementatie wordt onderbroken als er een implementatie is voor de standaardlijst voor proxy-uitzondering.</span><span class="sxs-lookup"><span data-stu-id="a0ece-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="a0ece-195">Vereisten</span><span class="sxs-lookup"><span data-stu-id="a0ece-195">Requirements</span></span>

<span data-ttu-id="a0ece-196">Aan deze vereisten moet worden voldaan voor uitzonderingen op proxyserver en proxysite:</span><span class="sxs-lookup"><span data-stu-id="a0ece-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="a0ece-197">Moet een geldig serveradres en poortnummer zijn</span><span class="sxs-lookup"><span data-stu-id="a0ece-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="a0ece-198">URL's moeten een geldige http-site zijn</span><span class="sxs-lookup"><span data-stu-id="a0ece-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="a0ece-199">Proxy's aanpassen en implementeren</span><span class="sxs-lookup"><span data-stu-id="a0ece-199">Customize and deploy proxies</span></span>

<span data-ttu-id="a0ece-200">**Een afzonderlijke proxysiteuitzondering toevoegen**</span><span class="sxs-lookup"><span data-stu-id="a0ece-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="a0ece-201">Aanmelden bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a0ece-201">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a0ece-202">Selecteer **Configureerbaar**onder **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a0ece-203">Selecteer Proxy in **de werkruimte Configureerbaar.** **Proxy**</span><span class="sxs-lookup"><span data-stu-id="a0ece-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="a0ece-204">Voer het **adres-** en **poortnummer** voor uw proxyserver in en selecteer **Proxy exception toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="a0ece-205">Voer de URL van een geldige http-site in en selecteer **Proxy exception toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a0ece-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="a0ece-206">Herhaal stap 1-5 voor elke vertrouwde site die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="a0ece-207">Selecteer **Fase-implementatie** om uw wijzigingen op te slaan en deze te implementeren in de groep Testen.</span><span class="sxs-lookup"><span data-stu-id="a0ece-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a0ece-208">Overige informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="a0ece-208">Additional resources</span></span>
- [<span data-ttu-id="a0ece-209">Overzicht van configureerbare instellingen</span><span class="sxs-lookup"><span data-stu-id="a0ece-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="a0ece-210">Configureerbare instellingen implementeren</span><span class="sxs-lookup"><span data-stu-id="a0ece-210">Deploy configurable settings</span></span>](config-setting-deploy.md)
