---
title: IP-adres en URL-webservice van Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Informatie over het gebruik van het IP-adres en de URL-webservice van Office 365 om u te helpen bij het beter identificeren en onderscheiden van het netwerkverkeer van Office 365.
ms.openlocfilehash: 1948491e1d3db724e7b7b6a5275234acab4be08a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918952"
---
# <a name="office-365-ip-address-and-url-web-service"></a><span data-ttu-id="ebf75-103">IP-adres en URL-webservice van Office 365</span><span class="sxs-lookup"><span data-stu-id="ebf75-103">Office 365 IP Address and URL web service</span></span>

<span data-ttu-id="ebf75-104">Het IP-adres en de URL-webservice Office 365 helpen u bij het beter identificeren en onderscheiden van het Office 365-netwerkverkeer. Hierdoor is het eenvoudiger om op de hoogte te blijven van wijzigingen en deze te evalueren en te configureren.</span><span class="sxs-lookup"><span data-stu-id="ebf75-104">The Office 365 IP Address and URL web service helps you better identify and differentiate Office 365 network traffic, making it easier for you to evaluate, configure, and stay up to date with changes.</span></span> <span data-ttu-id="ebf75-105">Met deze REST-webservice worden eerdere downloadbare XML-bestanden die op 2 oktober 2018 werden geïmplementeerd vervangen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-105">This REST-based web service replaces the previous XML downloadable files, which were phased out on October 2, 2018.</span></span>

<span data-ttu-id="ebf75-106">Als klant of leverancier van netwerkperimeterapparaten kunt u de vermeldingen van de Office 365-IP-adressen en -FQDN's gebruiken als bouwstenen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-106">As a customer or a network perimeter device vendor, you can build against the web service for Office 365 IP address and FQDN entries.</span></span> <span data-ttu-id="ebf75-107">U kunt de gegevens rechtstreeks in een webbrowser openen met behulp van de volgende URL's:</span><span class="sxs-lookup"><span data-stu-id="ebf75-107">You can access the data directly in a web browser using these URLs:</span></span>

- <span data-ttu-id="ebf75-108">Gebruik [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) voor de nieuwste versie van de URL's en IP-adresbereiken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ebf75-108">For the latest version of the Office 365 URLs and IP address ranges, use [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="ebf75-109">Gebruik [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) voor de gegevens op de pagina over de URL's en IP-adresbereiken voor Office 365 voor firewalls en proxyservers.</span><span class="sxs-lookup"><span data-stu-id="ebf75-109">For the data on the Office 365 URLs and IP address ranges page for firewalls and proxy servers, use [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="ebf75-110">Gebruik [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) om alle meest recente wijzigingen sinds juli 2018, toen de webservice voor het eerst beschikbaar was, op te halen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-110">To get all the latest changes since July 2018 when the web service was first available, use [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>

<span data-ttu-id="ebf75-111">Als klant kunt u deze webservice gebruiken voor:</span><span class="sxs-lookup"><span data-stu-id="ebf75-111">As a customer, you can use this web service to:</span></span>

- <span data-ttu-id="ebf75-112">Het bijwerken van PowerShell-scripts voor het verkrijgen van Office 365-eindpuntgegevens en het wijzigen van de opmaak van uw netwerkapparatuur.</span><span class="sxs-lookup"><span data-stu-id="ebf75-112">Update your PowerShell scripts to obtain Office 365 endpoint data and modify any formatting for your networking devices.</span></span>
- <span data-ttu-id="ebf75-113">Gebruik deze informatie voor het bijwerken van PAC-bestanden die voor clientcomputers zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-113">Use this information to update PAC files deployed to client computers.</span></span>

<span data-ttu-id="ebf75-114">Als leverancier van netwerkperimeterapparaten kunt u deze webservice gebruiken voor:</span><span class="sxs-lookup"><span data-stu-id="ebf75-114">As a network perimeter device vendor, you can use this web service to:</span></span>

- <span data-ttu-id="ebf75-115">Het maken en testen van apparaatsoftware om de lijst voor geautomatiseerde configuratie te downloaden.</span><span class="sxs-lookup"><span data-stu-id="ebf75-115">Create and test device software to download the list for automated configuration.</span></span>
- <span data-ttu-id="ebf75-116">Het controleren van de huidige versie.</span><span class="sxs-lookup"><span data-stu-id="ebf75-116">Check for the current version.</span></span>
- <span data-ttu-id="ebf75-117">Het ophalen van de huidige wijzigingen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-117">Get the current changes.</span></span>

> [!NOTE]
> <span data-ttu-id="ebf75-118">Als u Azure ExpressRoute gebruikt om verbinding te maken met Office 365, raadpleegt u [Azure ExpressRoute voor Office 365](azure-expressroute.md) om vertrouwd te raken met de Office 365-services die worden ondersteund via Azure ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="ebf75-118">If you are using Azure ExpressRoute to connect to Office 365, please review [Azure ExpressRoute for Office 365](azure-expressroute.md) to familiarize yourself with the Office 365 services supported over Azure ExpressRoute.</span></span> <span data-ttu-id="ebf75-119">Raadpleeg ook het artikel [IP-adresbereiken en URL‘s van Office 365](urls-and-ip-address-ranges.md) om te lezen voor welke netwerkverzoeken van Office 365-toepassingen verbinding met internet nodig is.</span><span class="sxs-lookup"><span data-stu-id="ebf75-119">Also review the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md) to understand which network requests for Office 365 applications require Internet connectivity.</span></span> <span data-ttu-id="ebf75-120">Hiermee kunt u het beveiligingsapparaat voor een perimeternetwerk beter configureren.</span><span class="sxs-lookup"><span data-stu-id="ebf75-120">This will help to better configure your perimeter security devices.</span></span>

<span data-ttu-id="ebf75-121">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="ebf75-121">For more information, see:</span></span>

- [<span data-ttu-id="ebf75-122">Announcement blog post in the Office 365 Tech Community Forum</span><span class="sxs-lookup"><span data-stu-id="ebf75-122">Announcement blog post in the Office 365 Tech Community Forum</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [<span data-ttu-id="ebf75-123">Office 365 Tech Community Forum for questions about use of the web services</span><span class="sxs-lookup"><span data-stu-id="ebf75-123">Office 365 Tech Community Forum for questions about use of the web services</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a><span data-ttu-id="ebf75-124">Veelgebruikte parameters</span><span class="sxs-lookup"><span data-stu-id="ebf75-124">Common parameters</span></span>

<span data-ttu-id="ebf75-125">De volgende parameters worden veel gebruikt in alle webservicemethoden:</span><span class="sxs-lookup"><span data-stu-id="ebf75-125">These parameters are common across all the web service methods:</span></span>

- <span data-ttu-id="ebf75-126">**format=<JSON | CSV>** — De standaardindeling van de geretourneerde gegevens is JSON.</span><span class="sxs-lookup"><span data-stu-id="ebf75-126">**format=<JSON | CSV>** — By default, the returned data format is JSON.</span></span> <span data-ttu-id="ebf75-127">Gebruik deze optionele parameter als u de gegevens in een indeling met door komma's gescheiden waarden wilt hebben.</span><span class="sxs-lookup"><span data-stu-id="ebf75-127">Use this optional parameter to return the data in comma-separated values (CSV) format.</span></span>
- <span data-ttu-id="ebf75-128">**ClientRequestId=\<guid>** — Een verplichte GUID die u genereert voor clientkoppeling.</span><span class="sxs-lookup"><span data-stu-id="ebf75-128">**ClientRequestId=\<guid>** — A required GUID that you generate for client association.</span></span> <span data-ttu-id="ebf75-129">Genereer een unieke GUID voor elke computer waarmee de webservice wordt aangeroepen (de scripts op deze pagina genereren een GUID voor u).</span><span class="sxs-lookup"><span data-stu-id="ebf75-129">Generate a unique GUID for each machine that calls the web service (the scripts included on this page generate a GUID for you).</span></span> <span data-ttu-id="ebf75-130">Gebruik niet de GUID's uit het volgende voorbeeld. Deze kunnen in de toekomst door de webservice worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-130">Do not use the GUIDs shown in the following examples because they might be blocked by the web service in the future.</span></span> <span data-ttu-id="ebf75-131">De indeling van de GUID is _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, waarin de x voor een hexadecimaal getal staat.</span><span class="sxs-lookup"><span data-stu-id="ebf75-131">GUID format is _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, where x represents a hexadecimal number.</span></span>

  <span data-ttu-id="ebf75-132">Als u een GUID wilt genereren, kunt u gebruikmaken van de opdracht [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) PowerShell of een online service zoals [Online GUID Generator](https://www.guidgenerator.com/).</span><span class="sxs-lookup"><span data-stu-id="ebf75-132">To generate a GUID, you can use the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) PowerShell command, or use an online service such as [Online GUID Generator](https://www.guidgenerator.com/).</span></span>

## <a name="version-web-method"></a><span data-ttu-id="ebf75-133">Versiewebmethode</span><span class="sxs-lookup"><span data-stu-id="ebf75-133">Version web method</span></span>

<span data-ttu-id="ebf75-134">Microsoft werkt het IP-adres en de FQDN-vermeldingen van Office 365 aan het begin van elke maand bij.</span><span class="sxs-lookup"><span data-stu-id="ebf75-134">Microsoft updates the Office 365 IP address and FQDN entries at the end of each month.</span></span> <span data-ttu-id="ebf75-135">Er worden soms out-of-band updates gepubliceerd vanwege ondersteuningsincidenten, beveiligingsupdates of andere operationele vereisten.</span><span class="sxs-lookup"><span data-stu-id="ebf75-135">Out-of-band updates are sometimes published due to support incidents, security updates or other operational requirements.</span></span>

<span data-ttu-id="ebf75-136">Aan de gegevens voor elk gepubliceerd exemplaar wordt een versienummer toegewezen en met de versiewebmethode kunt u controleren op de meest recente versie van elk service-exemplaar van Office 365.</span><span class="sxs-lookup"><span data-stu-id="ebf75-136">The data for each published instance is assigned a version number, and the version web method enables you to check for the latest version of each Office 365 service instance.</span></span> <span data-ttu-id="ebf75-137">U wordt aangeraden de versie niet meer dan één keer per uur te controleren.</span><span class="sxs-lookup"><span data-stu-id="ebf75-137">We recommend that you check the version not more than once an hour.</span></span>

<span data-ttu-id="ebf75-138">Parameters voor de versiewebmethode zijn:</span><span class="sxs-lookup"><span data-stu-id="ebf75-138">Parameters for the version web method are:</span></span>

- <span data-ttu-id="ebf75-139">**AllVersions=<true | false>** — Standaard is de geretourneerde versie de laatste.</span><span class="sxs-lookup"><span data-stu-id="ebf75-139">**AllVersions=<true | false>** — By default, the version returned is the latest.</span></span> <span data-ttu-id="ebf75-140">Neem deze optionele parameter op om alle gepubliceerde versies aan te vragen sinds de webservice voor het eerst werd uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="ebf75-140">Include this optional parameter to request all published versions since the web service was first released.</span></span>
- <span data-ttu-id="ebf75-141">**Format=<JSON | CSV | RSS>** — Naast de JSON- en CSV-indelingen, ondersteunt de versiewebmethode ook RSS.</span><span class="sxs-lookup"><span data-stu-id="ebf75-141">**Format=<JSON | CSV | RSS>** — In addition to the JSON and CSV formats, the version web method also supports RSS.</span></span> <span data-ttu-id="ebf75-142">U kunt deze optionele parameter combineren met de parameter _AllVersions=true_ om een RSS-feed aan te vragen die kan worden gebruikt met Outlook of andere RSS-lezers.</span><span class="sxs-lookup"><span data-stu-id="ebf75-142">You can use this optional parameter along with the _AllVersions=true_ parameter to request an RSS feed that can be used with Outlook or other RSS readers.</span></span>
- <span data-ttu-id="ebf75-143">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — Deze optionele parameter specificeert het exemplaar waarvoor de versie moet worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-143">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This optional parameter specifies the instance to return the version for.</span></span> <span data-ttu-id="ebf75-144">Indien niet gebruikt, worden alle exemplaren geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-144">If omitted, all instances are returned.</span></span> <span data-ttu-id="ebf75-145">Geldige exemplaren zijn: wereldwijd, China, Duitsland, USGovDoD en USGovGCCHigh.</span><span class="sxs-lookup"><span data-stu-id="ebf75-145">Valid instances are: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.</span></span>

<span data-ttu-id="ebf75-146">De versiewebmethode is niet beperkt en geeft nooit 429 HTTP-antwoordcodes.</span><span class="sxs-lookup"><span data-stu-id="ebf75-146">The version web method is not rate limited and does not ever return 429 HTTP Response Codes.</span></span> <span data-ttu-id="ebf75-147">Het antwoord op de versiewebmethode omvat een cache-besturingselementindeling die het in de cache opslaan van de gegevens voor 1 uur aanbeveelt.</span><span class="sxs-lookup"><span data-stu-id="ebf75-147">The response to the version web method does include a cache-control header recommending caching of the data for 1 hour.</span></span> <span data-ttu-id="ebf75-148">Het resultaat van de versiewebmethode kan één record zijn of een matrix van records.</span><span class="sxs-lookup"><span data-stu-id="ebf75-148">The result from the version web method can be a single record or an array of records.</span></span> <span data-ttu-id="ebf75-149">De elementen van elke record zijn:</span><span class="sxs-lookup"><span data-stu-id="ebf75-149">The elements of each record are:</span></span>

- <span data-ttu-id="ebf75-150">exemplaar - De korte naam van het Office 365-service-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="ebf75-150">instance — The short name of the Office 365 service instance.</span></span>
- <span data-ttu-id="ebf75-151">nieuwste - De nieuwste versie voor eindpunten van het opgegeven exemplaar.</span><span class="sxs-lookup"><span data-stu-id="ebf75-151">latest — The latest version for endpoints of the specified instance.</span></span>
- <span data-ttu-id="ebf75-152">versies - Een lijst met alle voorgaande versies voor het opgegeven exemplaar.</span><span class="sxs-lookup"><span data-stu-id="ebf75-152">versions — A list of all previous versions for the specified instance.</span></span> <span data-ttu-id="ebf75-153">Dit element is alleen opgenomen als de parameter _AllVersions_ waar is.</span><span class="sxs-lookup"><span data-stu-id="ebf75-153">This element is only included if the _AllVersions_ parameter is true.</span></span>

### <a name="examples"></a><span data-ttu-id="ebf75-154">Voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="ebf75-154">Examples:</span></span>

<span data-ttu-id="ebf75-155">Voorbeeld 1 URI aanvragen: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ebf75-155">Example 1 request URI: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ebf75-156">Met deze URI wordt de nieuwste versie van elk Office 365-service-exemplaar geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-156">This URI returns the latest version of each Office 365 service instance.</span></span> <span data-ttu-id="ebf75-157">Resultaat van voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ebf75-157">Example result:</span></span>

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> <span data-ttu-id="ebf75-158">De GUID voor de parameter ClientRequestID in deze URI's is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="ebf75-158">The GUID for the ClientRequestID parameter in these URIs are only an example.</span></span> <span data-ttu-id="ebf75-159">Genereer uw eigen GUID als u de URI's voor de webservice wilt uitproberen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-159">To try the web service URIs out, generate your own GUID.</span></span> <span data-ttu-id="ebf75-160">De in deze voorbeelden getoonde GUID's kunnen in de toekomst door de webservice worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-160">The GUIDs shown in these examples may be blocked by the web service in the future.</span></span>

<span data-ttu-id="ebf75-161">Voorbeeld 2 URI aanvragen: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ebf75-161">Example 2 request URI: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ebf75-162">Met deze URI wordt de nieuwste versie van het opgegeven Office 365-service-exemplaar geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-162">This URI returns the latest version of the specified Office 365 service instance.</span></span> <span data-ttu-id="ebf75-163">Resultaat van voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ebf75-163">Example result:</span></span>

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

<span data-ttu-id="ebf75-164">Voorbeeld 3 URI aanvragen: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ebf75-164">Example 3 request URI: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ebf75-165">Met deze URI wordt de uitvoer in een CSV-indeling getoond.</span><span class="sxs-lookup"><span data-stu-id="ebf75-165">This URI shows output in CSV format.</span></span> <span data-ttu-id="ebf75-166">Resultaat van voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ebf75-166">Example result:</span></span>

```csv
instance,latest
Worldwide,2018063000
```

<span data-ttu-id="ebf75-167">Voorbeeld 4 URI aanvragen: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ebf75-167">Example 4 request URI: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ebf75-168">Met deze URI worden alle vorige versies getoond die voor het Office 365 Worldwide-service-exemplaar zijn gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-168">This URI shows all prior versions that have been published for the Office 365 worldwide service instance.</span></span> <span data-ttu-id="ebf75-169">Resultaat van voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ebf75-169">Example result:</span></span>

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

<span data-ttu-id="ebf75-170">Voorbeeld 5 URI voor RSS-feed: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span><span class="sxs-lookup"><span data-stu-id="ebf75-170">Example 5 RSS Feed URI: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span></span>

<span data-ttu-id="ebf75-171">Met deze URI wordt een RSS-feed weergegeven van de gepubliceerde versies die koppelingen bevatten naar de lijst met wijzigingen voor elke versie.</span><span class="sxs-lookup"><span data-stu-id="ebf75-171">This URI shows an RSS feed of the published versions that include links to the list of changes for each version.</span></span> <span data-ttu-id="ebf75-172">Resultaat van voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ebf75-172">Example result:</span></span>

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a><span data-ttu-id="ebf75-173">Eindpuntenwebmethode</span><span class="sxs-lookup"><span data-stu-id="ebf75-173">Endpoints web method</span></span>

<span data-ttu-id="ebf75-174">Met de eindpuntenwebmethode worden alle records voor IP-adresbereiken en URL's geretourneerd waaruit de Office 365-service is opgebouwd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-174">The endpoints web method returns all records for IP address ranges and URLs that make up the Office 365 service.</span></span> <span data-ttu-id="ebf75-175">De meest recente gegevens uit de eindpuntenwebmethode moeten altijd worden gebruikt voor de configuratie van netwerkapparaten.</span><span class="sxs-lookup"><span data-stu-id="ebf75-175">The latest data from the endpoints web method should always be used for network device configuration.</span></span> <span data-ttu-id="ebf75-176">Microsoft biedt 30 dagen voorafgaande kennisgeving voor het publiceren van nieuwe toevoegingen om u tijd te geven om toegangsbeheerlijsten en bypasslijsten van de proxyserver bij te werken.</span><span class="sxs-lookup"><span data-stu-id="ebf75-176">Microsoft provides advance notice 30 days prior to publishing new additions to give you time to update access control lists and proxy server bypass lists.</span></span> <span data-ttu-id="ebf75-177">U wordt aangeraden de eindpuntenwebmethode pas opnieuw aan te roepen wanneer de versiewebmethode aangeeft dat er een nieuwe versie van de gegevens beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="ebf75-177">We recommend that you only call the endpoints web method again when the version web method indicates that a new version of the data is available.</span></span>

<span data-ttu-id="ebf75-178">Parameters voor de eindpuntenwebmethode zijn:</span><span class="sxs-lookup"><span data-stu-id="ebf75-178">Parameters for the endpoints web method are:</span></span>

- <span data-ttu-id="ebf75-179">**ServiceAreas=<Common | Exchange | SharePoint | Skype>** — Een door komma‘s gescheiden lijst van servicegebieden.</span><span class="sxs-lookup"><span data-stu-id="ebf75-179">**ServiceAreas=<Common | Exchange | SharePoint | Skype>** — A comma-separated list of service areas.</span></span> <span data-ttu-id="ebf75-180">Geldige items zijn _Common_, _Exchange_, _SharePoint_ en _Skype_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-180">Valid items are _Common_, _Exchange_, _SharePoint_, and _Skype_.</span></span> <span data-ttu-id="ebf75-181">Omdat _Common_-servicegebieditems een vereiste zijn voor alle overige servicegebieden, is dit item altijd in de webservice opgenomen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-181">Because _Common_ service area items are a prerequisite for all other service areas, the web service always includes them.</span></span> <span data-ttu-id="ebf75-182">Als u deze parameter niet opneemt, worden alle services geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-182">If you do not include this parameter, all service areas are returned.</span></span>
- <span data-ttu-id="ebf75-183">**TenantName=<tenant_name>** — De naam van uw Office 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="ebf75-183">**TenantName=<tenant_name>** — Your Office 365 tenant name.</span></span> <span data-ttu-id="ebf75-184">De webservice gebruikt de opgegeven naam en voegt deze in delen van URL's in waarin de naam van de tenant is opgenomen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-184">The web service takes your provided name and inserts it in parts of URLs that include the tenant name.</span></span> <span data-ttu-id="ebf75-185">Als u geen tenantnaam opgeeft, bevatten deze URL's een jokerteken (\*).</span><span class="sxs-lookup"><span data-stu-id="ebf75-185">If you don't provide a tenant name, those parts of URLs have the wildcard character (\*).</span></span>
- <span data-ttu-id="ebf75-186">**NoIPv6=<true | false>** — Stel de waarde in op _true_ om NoIPv6-adressen van de uitvoer uit te sluiten als u IPv6 niet gebruikt in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="ebf75-186">**NoIPv6=<true | false>** — Set the value to _true_ to exclude IPv6 addresses from the output if you don't use IPv6 in your network.</span></span>
- <span data-ttu-id="ebf75-187">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — Deze verplichte parameter specificeert het exemplaar waarvoor de eindpunten moeten worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-187">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This required parameter specifies the instance from which to return the endpoints.</span></span> <span data-ttu-id="ebf75-188">Geldige exemplaren zijn: _Worldwide_, _China_, _Germany_, _USGovDoD_ en _USGovGCCHigh_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-188">Valid instances are: _Worldwide_, _China_, _Germany_, _USGovDoD_, and _USGovGCCHigh_.</span></span>

<span data-ttu-id="ebf75-189">Als u de eindpuntenwebmethode te vaak oproept van hetzelfde IP-adres van de client, ontvangt u mogelijk de HTTP-antwoordcode _429 (te veel aanvragen)_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-189">If you call the endpoints web method too many times from the same client IP address, you might receive HTTP response code _429 (Too Many Requests)_.</span></span> <span data-ttu-id="ebf75-190">Als u deze antwoordcode krijgt, wacht u 1 uur voordat u de aanvraag herhaalt of genereert u een nieuwe GUID voor de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="ebf75-190">If you get this response code, wait 1 hour before repeating your request, or generate a new GUID for the request.</span></span> <span data-ttu-id="ebf75-191">Over het algemeen kunt u het beste de eindpuntenwebmethode pas opnieuw aanroepen wanneer de versiewebmethode aangeeft dat er een nieuwe versie van de gegevens beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="ebf75-191">As a general best practice, only call the endpoints web method when the version web method indicates that a new version is available.</span></span>

<span data-ttu-id="ebf75-192">Het resultaat van de eindpuntenwebmethode bestaat uit een matrix met records, waarbij elke record een specifieke eindpuntenset voorstelt.</span><span class="sxs-lookup"><span data-stu-id="ebf75-192">The result from the endpoints web method is an array of records in which each record represents a specific endpoint set.</span></span> <span data-ttu-id="ebf75-193">De elementen van elke record zijn:</span><span class="sxs-lookup"><span data-stu-id="ebf75-193">The elements for each record are:</span></span>

- <span data-ttu-id="ebf75-194">id - Het onveranderlijke id-nummer van de eindpuntenset.</span><span class="sxs-lookup"><span data-stu-id="ebf75-194">id — The immutable id number of the endpoint set.</span></span>
- <span data-ttu-id="ebf75-195">serviceArea — Het servicegebied waar dit deel van uitmaakt: _Common_, _Exchange_, _SharePoint_ of _Skype_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-195">serviceArea — The service area that this is part of: _Common_, _Exchange_, _SharePoint_, or _Skype_.</span></span>
- <span data-ttu-id="ebf75-196">urls: URL's voor de eindpuntenset.</span><span class="sxs-lookup"><span data-stu-id="ebf75-196">urls — URLs for the endpoint set.</span></span> <span data-ttu-id="ebf75-197">Een JSON-matrix van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="ebf75-197">A JSON array of DNS records.</span></span> <span data-ttu-id="ebf75-198">Dit argument wordt weggelaten indien leeg.</span><span class="sxs-lookup"><span data-stu-id="ebf75-198">Omitted if blank.</span></span>
- <span data-ttu-id="ebf75-199">tcpPorts — TCP-poorten voor de eindpuntenset.</span><span class="sxs-lookup"><span data-stu-id="ebf75-199">tcpPorts — TCP ports for the endpoint set.</span></span> <span data-ttu-id="ebf75-200">Alle poortelementen worden ingedeeld als een door komma's gescheiden lijst met poorten of poortbereiken die door een streepje (-) worden gescheiden.</span><span class="sxs-lookup"><span data-stu-id="ebf75-200">All ports elements are formatted as a comma-separated list of ports or port ranges separated by a dash character (-).</span></span> <span data-ttu-id="ebf75-201">Poorten zijn van toepassing op alle IP-adressen en alle URL's in die eindpuntenset voor een bepaalde categorie.</span><span class="sxs-lookup"><span data-stu-id="ebf75-201">Ports apply to all IP addresses and all URLs in the endpoint set for a given category.</span></span> <span data-ttu-id="ebf75-202">Dit argument wordt weggelaten indien leeg.</span><span class="sxs-lookup"><span data-stu-id="ebf75-202">Omitted if blank.</span></span>
- <span data-ttu-id="ebf75-203">udpPorts - UDP-poorten voor de IP-adresbereiken in deze eindpuntenset.</span><span class="sxs-lookup"><span data-stu-id="ebf75-203">udpPorts — UDP ports for the IP address ranges in this endpoint set.</span></span> <span data-ttu-id="ebf75-204">Dit argument wordt weggelaten indien leeg.</span><span class="sxs-lookup"><span data-stu-id="ebf75-204">Omitted if blank.</span></span>
- <span data-ttu-id="ebf75-205">ips - De IP-adresbereiken die zijn gekoppeld aan deze eindpuntenset zoals gekoppeld aan de vermelde TCP- of UDP-poorten.</span><span class="sxs-lookup"><span data-stu-id="ebf75-205">ips — The IP address ranges associated with this endpoint set as associated with the listed TCP or UDP ports.</span></span> <span data-ttu-id="ebf75-206">Een JSON-matrix met IP-adresbereiken.</span><span class="sxs-lookup"><span data-stu-id="ebf75-206">A JSON array of IP address ranges.</span></span> <span data-ttu-id="ebf75-207">Dit argument wordt weggelaten indien leeg.</span><span class="sxs-lookup"><span data-stu-id="ebf75-207">Omitted if blank.</span></span>
- <span data-ttu-id="ebf75-208">category - De verbindingscategorie voor de eindpuntenset.</span><span class="sxs-lookup"><span data-stu-id="ebf75-208">category — The connectivity category for the endpoint set.</span></span> <span data-ttu-id="ebf75-209">Geldige waarden zijn _Optimaliseren_, _Toestaan_ en _Standaard_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-209">Valid values are _Optimize_, _Allow_, and _Default_.</span></span> <span data-ttu-id="ebf75-210">Als u de uitvoer van de eindpuntenwebmethode zoekt voor de categorie van een specifiek IP-adres of -URL, is het mogelijk dat uw query meerdere categorieën retourneert.</span><span class="sxs-lookup"><span data-stu-id="ebf75-210">If you search the endpoints web method output for the category of a specific IP address or URL, it is possible that your query will return multiple categories.</span></span> <span data-ttu-id="ebf75-211">Volg in dat geval de aanbeveling voor de categorie met de hoogste prioriteit.</span><span class="sxs-lookup"><span data-stu-id="ebf75-211">In such a case, follow the recommendation for the highest priority category.</span></span> <span data-ttu-id="ebf75-212">Als het eindpunt bijvoorbeeld wordt weergegeven in zowel _Optimaliseren_ als _Toestaan_, volgt u de vereisten voor _Optimaliseren_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-212">For example, if the endpoint appears in both _Optimize_ and _Allow_, you should follow the requirements for _Optimize_.</span></span> <span data-ttu-id="ebf75-213">Vereist.</span><span class="sxs-lookup"><span data-stu-id="ebf75-213">Required.</span></span>
- <span data-ttu-id="ebf75-214">expressRoute — _True_ als deze eindpuntenset via ExpressRoute wordt gerouteerd, _False_ als dit niet het geval is.</span><span class="sxs-lookup"><span data-stu-id="ebf75-214">expressRoute — _True_ if this endpoint set is routed over ExpressRoute, _False_ if not.</span></span>
- <span data-ttu-id="ebf75-215">required — _True_ als deze eindpuntenset moet zijn verbonden om ondersteuning van Office 365 mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="ebf75-215">required — _True_ if this endpoint set is required to have connectivity for Office 365 to be supported.</span></span> <span data-ttu-id="ebf75-216">_False_ als deze eindpunt serie optioneel is.</span><span class="sxs-lookup"><span data-stu-id="ebf75-216">_False_ if this endpoint set is optional.</span></span>
- <span data-ttu-id="ebf75-217">notes - Voor optionele eindpunten beschrijft deze tekst de Office 365-functionaliteit die niet beschikbaar is als IP-adressen of URL‘s in deze eindpuntenset niet kunnen worden bereikt in de netwerklaag.</span><span class="sxs-lookup"><span data-stu-id="ebf75-217">notes — For optional endpoints, this text describes Office 365 functionality that would be unavailable if IP addresses or URLs in this endpoint set cannot be accessed at the network layer.</span></span> <span data-ttu-id="ebf75-218">Dit argument wordt weggelaten indien leeg.</span><span class="sxs-lookup"><span data-stu-id="ebf75-218">Omitted if blank.</span></span>

### <a name="examples"></a><span data-ttu-id="ebf75-219">Voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="ebf75-219">Examples:</span></span>

<span data-ttu-id="ebf75-220">Voorbeeld 1 URI aanvragen: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ebf75-220">Example 1 request URI: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ebf75-221">Met deze URI worden voor alle werkbelastingen alle eindpunten verkregen voor het Office 365 Worldwide-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="ebf75-221">This URI obtains all endpoints for the Office 365 worldwide instance for all workloads.</span></span> <span data-ttu-id="ebf75-222">Voorbeeldresultaat dat een fragment van de uitvoer toont:</span><span class="sxs-lookup"><span data-stu-id="ebf75-222">Example result that shows an excerpt of the output:</span></span>

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

<span data-ttu-id="ebf75-223">Houd er rekening mee dat de volledige uitvoer van de aanvraag in dit voorbeeld andere eindpunten sets zou kunnen bevatten.</span><span class="sxs-lookup"><span data-stu-id="ebf75-223">Note that the full output of the request in this example would contain other endpoint sets.</span></span>

<span data-ttu-id="ebf75-224">Voorbeeld 2 URI aanvragen: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ebf75-224">Example 2 request URI: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ebf75-225">In dit voorbeeld worden alleen eindpunten verkregen voor het Office 365 Worldwide-exemplaar voor Exchange Online en afhankelijkheden.</span><span class="sxs-lookup"><span data-stu-id="ebf75-225">This example obtains endpoints for the Office 365 Worldwide instance for Exchange Online and dependencies only.</span></span>

<span data-ttu-id="ebf75-226">De uitvoer van voorbeeld 2 lijkt op die van voorbeeld 1, behalve dat in de resultaten geen eindpunten zijn opgenomen voor SharePoint Online of Skype voor Bedrijven Online.</span><span class="sxs-lookup"><span data-stu-id="ebf75-226">The output for example 2 is similar to example 1 except that the results would not include endpoints for SharePoint Online or Skype for Business Online.</span></span>

## <a name="changes-web-method"></a><span data-ttu-id="ebf75-227">Wijzigingenwebmethode</span><span class="sxs-lookup"><span data-stu-id="ebf75-227">Changes web method</span></span>

<span data-ttu-id="ebf75-228">Met de wijzigingenwebmethode worden de meest recente updates die zijn gepubliceerd, geretourneerd. Dit zijn gewoonlijk de wijzigingen aan IP-adresbereiken en URL's van de vorige maand.</span><span class="sxs-lookup"><span data-stu-id="ebf75-228">The changes web method returns the most recent updates that have been published, typically the previous month's changes to IP address ranges and URLs.</span></span>

<span data-ttu-id="ebf75-229">De belangrijkste wijzigingen in de gegevens van eindpunten zijn nieuwe URL's en IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-229">The most critical changes to endpoints data are new URLs and IP addresses.</span></span> <span data-ttu-id="ebf75-230">Het niet toevoegen van een IP-adres aan een toegangsbeheerlijst van een firewall of een URL naar een bypasslijst voor een proxyserver kan een storing veroorzaken voor Office 365-gebruikers van dat netwerkapparaat.</span><span class="sxs-lookup"><span data-stu-id="ebf75-230">Failure to add an IP address to a firewall access control list or a URL to a proxy server bypass list can cause an outage for Office 365 users behind that network device.</span></span> <span data-ttu-id="ebf75-231">Niettegenstaande operationele vereisten worden nieuwe eindpunten op de webservice gepubliceerd 30 dagen voor de datum waarop de eindpunten zijn ingericht voor gebruik, zodat u tijd hebt om toegangsbeheerlijsten en bypasslijsten voor proxyservers over te slaan.</span><span class="sxs-lookup"><span data-stu-id="ebf75-231">Notwithstanding operational requirements, new endpoints are published to the web service 30 days in advance of the date the endpoints are provisioned for use to give you time to update access control lists and proxy server bypass lists.</span></span>

<span data-ttu-id="ebf75-232">De vereiste parameter voor de wijzigingenwebmethode is:</span><span class="sxs-lookup"><span data-stu-id="ebf75-232">The required parameter for the changes web method is:</span></span>

- <span data-ttu-id="ebf75-233">**Version=\<YYYYMMDDNN>** — Verplichte URL-routeparameter.</span><span class="sxs-lookup"><span data-stu-id="ebf75-233">**Version=\<YYYYMMDDNN>** — Required URL route parameter.</span></span> <span data-ttu-id="ebf75-234">Deze waarde is de versie die u momenteel hebt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-234">This value is the version that you have currently implemented.</span></span> <span data-ttu-id="ebf75-235">De webservice retourneert de wijzigingen sinds die versie.</span><span class="sxs-lookup"><span data-stu-id="ebf75-235">The web service will return the changes since that version.</span></span> <span data-ttu-id="ebf75-236">De indeling is _JJJJMMDDNN_, waarbij _NN_ een natuurlijk getal is, dat is verhoogd als er meerdere versies op één dag moeten worden gepubliceerd en _00_ de eerste update voor een bepaalde dag voorstelt.</span><span class="sxs-lookup"><span data-stu-id="ebf75-236">The format is _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day, with _00_ representing the first update for a given day.</span></span> <span data-ttu-id="ebf75-237">Voor de webservice moet de _versie_ parameter precies 10 cijfers bevatten.</span><span class="sxs-lookup"><span data-stu-id="ebf75-237">The web service requires the _version_ parameter to contain exactly 10 digits.</span></span>

<span data-ttu-id="ebf75-238">De wijzigingenwebmethode is op dezelfde manier beperkt als de eindpuntenwebmethode.</span><span class="sxs-lookup"><span data-stu-id="ebf75-238">The changes web method is rate limited in the same way as the endpoints web method.</span></span> <span data-ttu-id="ebf75-239">Als u een 429 HTTP-antwoordcode krijgt, wacht u 1 uur voordat u de aanvraag herhaalt of genereert u een nieuwe GUID voor de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="ebf75-239">If you receive a 429 HTTP response code, wait 1 hour before repeating your request or generate a new GUID for the request.</span></span>

<span data-ttu-id="ebf75-240">Het resultaat van de wijzigingenwebmethode is een matrix met records, waarbij elke record een wijziging voorstelt in een bepaalde versie van de eindpunten.</span><span class="sxs-lookup"><span data-stu-id="ebf75-240">The result from the changes web method is an array of records in which each record represents a change in a specific version of the endpoints.</span></span> <span data-ttu-id="ebf75-241">De elementen van elke record zijn:</span><span class="sxs-lookup"><span data-stu-id="ebf75-241">The elements for each record are:</span></span>

- <span data-ttu-id="ebf75-242">id - De onveranderlijke id van de wijzigingenrecord.</span><span class="sxs-lookup"><span data-stu-id="ebf75-242">id — The immutable id of the change record.</span></span>
- <span data-ttu-id="ebf75-243">endpointSetId - De id van de eindpuntensetrecord die is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-243">endpointSetId — The ID of the endpoint set record that is changed.</span></span>
- <span data-ttu-id="ebf75-244">disposition - Beschrijft wat de wijziging heeft veranderd aan de eindpuntensetrecord.</span><span class="sxs-lookup"><span data-stu-id="ebf75-244">disposition — Describes what the change did to the endpoint set record.</span></span> <span data-ttu-id="ebf75-245">Waarden zijn _wijzigen_, _toevoegen_ of _verwijderen_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-245">Values are _change_, _add_, or _remove_.</span></span>
- <span data-ttu-id="ebf75-246">impact — Niet alle wijzigingen zijn even belangrijk voor elke omgeving.</span><span class="sxs-lookup"><span data-stu-id="ebf75-246">impact — Not all changes will be equally important to every environment.</span></span> <span data-ttu-id="ebf75-247">Dit element beschrijft de verwachte uitwerking op een perimeteromgeving van een bedrijfsnetwerk als gevolg van deze wijziging.</span><span class="sxs-lookup"><span data-stu-id="ebf75-247">This element describes the expected impact to an enterprise network perimeter environment as a result of this change.</span></span> <span data-ttu-id="ebf75-248">Dit element wordt alleen opgenomen in de wijzigingsrecords van versie **2018112800** en hoger.</span><span class="sxs-lookup"><span data-stu-id="ebf75-248">This element is included only in change records of version **2018112800** and later.</span></span> <span data-ttu-id="ebf75-249">De opties voor de uitwerking zijn: — AddedIp – Er is een IP-adres toegevoegd aan Office 365 en deze wordt binnenkort live op de service.</span><span class="sxs-lookup"><span data-stu-id="ebf75-249">Options for the impact are: — AddedIp – An IP address was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="ebf75-250">Dit is een wijziging die u moet uitvoeren op een firewall of een ander laag 3-netwerkperimeterapparaat.</span><span class="sxs-lookup"><span data-stu-id="ebf75-250">This represents a change you need to take on a firewall or other layer 3 network perimeter device.</span></span> <span data-ttu-id="ebf75-251">Als u dit niet toevoegt voordat we het gaan gebruiken, kan er mogelijk een storing optreden.</span><span class="sxs-lookup"><span data-stu-id="ebf75-251">If you don’t add this before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="ebf75-252">— AddedUrl - Er is een URL toegevoegd aan Office 365 en deze wordt binnenkort live voor de service.</span><span class="sxs-lookup"><span data-stu-id="ebf75-252">— AddedUrl – A URL was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="ebf75-253">Dit is een wijziging die u moet uitvoeren op een proxyserver of een netwerkperimeterapparaat dat de URL parseert.</span><span class="sxs-lookup"><span data-stu-id="ebf75-253">This represents a change you need to take on a proxy server or URL parsing network perimeter device.</span></span> <span data-ttu-id="ebf75-254">Als u deze URL niet toevoegt voordat we het gaan gebruiken, kan er mogelijk een storing optreden.</span><span class="sxs-lookup"><span data-stu-id="ebf75-254">If you don’t add this URL before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="ebf75-255">— AddedIpAndUrl - Er zijn zowel een IP-adres als een URL toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-255">— AddedIpAndUrl — Both an IP address and a URL were added.</span></span> <span data-ttu-id="ebf75-256">Dit is een wijziging die u moet uitvoeren op een apparaat met een laag 3-firewall of een proxyserver of apparaat dat URL parseert.</span><span class="sxs-lookup"><span data-stu-id="ebf75-256">This represents a change you need to take on either a firewall layer 3 device or a proxy server or URL parsing device.</span></span> <span data-ttu-id="ebf75-257">Als u dit IP/URL-paar niet toevoegt voordat we het gaan gebruiken, kan er mogelijk een storing optreden.</span><span class="sxs-lookup"><span data-stu-id="ebf75-257">If you don’t add this IP/URL pair before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="ebf75-258">— RemovedIpOrUrl – Er is minstens één IP-adres of URL verwijderd van Office 365.</span><span class="sxs-lookup"><span data-stu-id="ebf75-258">— RemovedIpOrUrl – At least one IP address or URL was removed from Office 365.</span></span> <span data-ttu-id="ebf75-259">Verwijder de netwerkeindpunten van uw perimeterapparaten, maar er is geen deadline om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-259">Remove the network endpoints from your perimeter devices, but there’s no deadline for you to do this.</span></span>
  <span data-ttu-id="ebf75-260">— ChangedIsExpressRoute - Het ExpressRoute-ondersteuningskenmerk is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-260">— ChangedIsExpressRoute – The ExpressRoute support attribute was changed.</span></span> <span data-ttu-id="ebf75-261">Als u ExpressRoute gebruikt, moet u mogelijk actie ondernemen afhankelijk van uw configuratie.</span><span class="sxs-lookup"><span data-stu-id="ebf75-261">If you use ExpressRoute, you might need to take action depending on your configuration.</span></span>
  <span data-ttu-id="ebf75-262">— MovedIpOrUrl – We hebben een IP-adres of URL van deze eindpuntenset naar een andere verplaatst.</span><span class="sxs-lookup"><span data-stu-id="ebf75-262">— MovedIpOrUrl – We moved an IP address or Url between this endpoint set and another one.</span></span> <span data-ttu-id="ebf75-263">Over het algemeen hoeft u geen actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-263">Generally no action is required.</span></span>
  <span data-ttu-id="ebf75-264">— RemovedDuplicateIpOrUrl – We hebben een gedupliceerd IP-adres of URL verwijderd, maar deze is nog steeds gepubliceerd voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="ebf75-264">— RemovedDuplicateIpOrUrl – We removed a duplicate IP address or Url but it’s still published for Office 365.</span></span> <span data-ttu-id="ebf75-265">Over het algemeen hoeft u geen actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-265">Generally no action is required.</span></span>
  <span data-ttu-id="ebf75-266">— OtherNonPriorityChanges – We hebben iets gewijzigd dat minder belangrijk is dan alle andere opties, zoals de inhoud van een notitieveld.</span><span class="sxs-lookup"><span data-stu-id="ebf75-266">— OtherNonPriorityChanges – We changed something less critical than all of the other options, such as the contents of a note field.</span></span>
- <span data-ttu-id="ebf75-267">version — De versie van de gepubliceerde eindpuntenset waarin de wijziging is aangebracht.</span><span class="sxs-lookup"><span data-stu-id="ebf75-267">version — The version of the published endpoint set in which the change was introduced.</span></span> <span data-ttu-id="ebf75-268">Versienummers hebben de indeling _JJJJMMDDNN_, waarbij _NN_ een natuurlijk getal is, dat is verhoogd als er meerdere versies op één dag moeten worden gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-268">Version numbers are of the format _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day.</span></span>
- <span data-ttu-id="ebf75-269">previous - Een substructuur met een opsomming van vorige waarden van gewijzigde elementen in de eindpuntenset.</span><span class="sxs-lookup"><span data-stu-id="ebf75-269">previous — A substructure detailing previous values of changed elements on the endpoint set.</span></span> <span data-ttu-id="ebf75-270">Deze wordt niet opgenomen voor nieuw toegevoegde eindpuntensets.</span><span class="sxs-lookup"><span data-stu-id="ebf75-270">This will not be included for newly added endpoint sets.</span></span> <span data-ttu-id="ebf75-271">Bevat _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ en _notes_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-271">Includes  _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="ebf75-272">current - Een substructuur met een opsomming van bijgewerkte waarden van gewijzigde elementen in de eindpuntenset.</span><span class="sxs-lookup"><span data-stu-id="ebf75-272">current — A substructure detailing updated values of changes elements on the endpoint set.</span></span> <span data-ttu-id="ebf75-273">Bevat _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ en _notes_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-273">Includes _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="ebf75-274">add - Een substructuur met een opsomming van items die aan eindpuntensetverzamelingen moeten worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-274">add — A substructure detailing items to be added to endpoint set collections.</span></span> <span data-ttu-id="ebf75-275">Wordt weggelaten als er geen toevoegingen zijn.</span><span class="sxs-lookup"><span data-stu-id="ebf75-275">Omitted if there are no additions.</span></span>
  <span data-ttu-id="ebf75-276">— effectiveDate — Definieert de gegevens als de toevoegingen live in de service zijn.</span><span class="sxs-lookup"><span data-stu-id="ebf75-276">— effectiveDate — Defines the data when the additions will be live in the service.</span></span>
  <span data-ttu-id="ebf75-277">— ips — Toe te voegen items aan de _ips_-matrix.</span><span class="sxs-lookup"><span data-stu-id="ebf75-277">— ips — Items to be added to the _ips_ array.</span></span>
  <span data-ttu-id="ebf75-278">— urls- Toe te voegen items aan de _URL‘s_-matrix.</span><span class="sxs-lookup"><span data-stu-id="ebf75-278">— urls- Items to be added to the _urls_ array.</span></span>
- <span data-ttu-id="ebf75-279">remove - Een substructuur met een opsomming van items die uit de eindpuntenset moeten worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-279">remove — A substructure detailing items to be removed from the endpoint set.</span></span> <span data-ttu-id="ebf75-280">Wordt weggelaten als er geen verwijderingen zijn.</span><span class="sxs-lookup"><span data-stu-id="ebf75-280">Omitted if there are no removals.</span></span>
  <span data-ttu-id="ebf75-281">— ips — Items die uit de _ips_-matrix moeten worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-281">— ips — Items to be removed from the _ips_ array.</span></span>
  <span data-ttu-id="ebf75-282">— urls- Items die uit de _URL‘s_-matrix moeten worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-282">— urls- Items to be removed from the _urls_ array.</span></span>

### <a name="examples"></a><span data-ttu-id="ebf75-283">Voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="ebf75-283">Examples:</span></span>

<span data-ttu-id="ebf75-284">Voorbeeld 1 URI aanvragen: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ebf75-284">Example 1 request URI: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ebf75-285">Hiermee worden alle voorgaande wijzigingen aan het Office 365 Worldwide-service-exemplaar aangevraagd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-285">This requests all previous changes to the Office 365 worldwide service instance.</span></span> <span data-ttu-id="ebf75-286">Resultaat van voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ebf75-286">Example result:</span></span>

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

<span data-ttu-id="ebf75-287">Voorbeeld 2 URI aanvragen: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ebf75-287">Example 2 request URI: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ebf75-288">Hiermee worden wijzigingen aangevraagd die zijn aangebracht na de opgegeven versie van het Office 365 Worldwide-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="ebf75-288">This requests changes since the specified version to the Office 365 Worldwide instance.</span></span> <span data-ttu-id="ebf75-289">In dit geval is de versie die is opgegeven de nieuwste versie.</span><span class="sxs-lookup"><span data-stu-id="ebf75-289">In this case, the version specified is the latest.</span></span> <span data-ttu-id="ebf75-290">Resultaat van voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ebf75-290">Example result:</span></span>

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a><span data-ttu-id="ebf75-291">Voorbeeld van PowerShell-script</span><span class="sxs-lookup"><span data-stu-id="ebf75-291">Example PowerShell Script</span></span>

<span data-ttu-id="ebf75-292">U kunt dit PowerShell-script uitvoeren om te zien of er acties zijn die u moet ondernemen voor bijgewerkte gegevens.</span><span class="sxs-lookup"><span data-stu-id="ebf75-292">You can run this PowerShell script to see if there are actions you need to take for updated data.</span></span> <span data-ttu-id="ebf75-293">U kunt dit script uitvoeren als een geplande taak om te controleren of er een versie-update is.</span><span class="sxs-lookup"><span data-stu-id="ebf75-293">You can run this script as a scheduled task to check for a version update.</span></span> <span data-ttu-id="ebf75-294">Om te voorkomen dat de webservice te zwaar belast wordt, dient u het script niet meer dan één keer per uur uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ebf75-294">To avoid excessive load on the web service, try not to run the script more than once an hour.</span></span>

<span data-ttu-id="ebf75-295">Het script doet het volgende:</span><span class="sxs-lookup"><span data-stu-id="ebf75-295">The script does the following:</span></span>

- <span data-ttu-id="ebf75-296">Het versienummer van de huidige eindpunten van het Office 365 Worldwide-exemplaar wordt gecontroleerd door de webservice REST API aan te roepen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-296">Checks the version number of the current Office 365 Worldwide instance endpoints by calling the web service REST API.</span></span>
- <span data-ttu-id="ebf75-297">Hiermee wordt gecontroleerd op een huidig versiebestand via _$Env:TEMP\O365_endpoints_latestversion.txt_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-297">Checks for a current version file at _$Env:TEMP\O365_endpoints_latestversion.txt_.</span></span> <span data-ttu-id="ebf75-298">Het pad van de globale variabele **$Env:TEMP** is meestal _C:\Users\\<username\>\AppData\Local\Temp_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-298">The path of the global variable **$Env:TEMP** is usually _C:\Users\\<username\>\AppData\Local\Temp_.</span></span>
- <span data-ttu-id="ebf75-299">Als dit de eerste keer is dat het script wordt uitgevoerd, geeft het script de huidige versie en alle huidige IP-adressen en URL's als resultaat, schrijft het de eindpuntenversie naar het bestand _$Env: TEMP \ O365_endpoints_latestversion. txt_ en de gegevensuitvoer van de eindpunten naar het bestand _$Env: TEMP \ O365_endpoints_data. txt_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-299">If this is the first time the script has been run, the script returns the current version and all current IP addresses and URLs, writes the endpoints version to the file _$Env:TEMP\O365_endpoints_latestversion.txt_ and the endpoints data output to the file _$Env:TEMP\O365_endpoints_data.txt_.</span></span> <span data-ttu-id="ebf75-300">U kunt het pad en/of de naam van het uitvoerbestand wijzigen door deze regels te bewerken:</span><span class="sxs-lookup"><span data-stu-id="ebf75-300">You can modify the path and/or name of the output file by editing these lines:</span></span>

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- <span data-ttu-id="ebf75-301">Wanneer de nieuwste webserviceversie identiek is aan de versie in het bestand _O365_endpoints_latestversion. txt_, wordt het script bij elke daaropvolgende uitvoering van het script afgesloten zonder enige wijzigingen door te voeren.</span><span class="sxs-lookup"><span data-stu-id="ebf75-301">On each subsequent execution of the script, if the latest web service version is identical to the version in the _O365_endpoints_latestversion.txt_ file, the script exits without making any changes.</span></span>
- <span data-ttu-id="ebf75-302">Wanneer de nieuwste versie van de webservice nieuwer is dan de versie in het bestand _O365_endpoints_latestversion.txt_, retourneert het script de eindpunten en filters voor de eindpunten in de categorie **Toestaan** en **Optimaliseren**, wordt de versie bijgewerkt in het bestand _O365_endpoints_latestversion.txt_ en worden de bijgewerkte gegevens naar het bestand _O365_endpoints_data.txt_ geschreven.</span><span class="sxs-lookup"><span data-stu-id="ebf75-302">When the latest web service version is newer than the version in the _O365_endpoints_latestversion.txt_ file, the script returns the endpoints and filters for the **Allow** and **Optimize** category endpoints, updates the version in the _O365_endpoints_latestversion.txt_ file, and writes the updated data to the _O365_endpoints_data.txt_ file.</span></span>

<span data-ttu-id="ebf75-303">Het script genereert een unieke _ClientRequestId_ voor de computer waarop deze wordt uitgevoerd en gebruikt deze ID voor meerdere gesprekken.</span><span class="sxs-lookup"><span data-stu-id="ebf75-303">The script generates a unique _ClientRequestId_ for the computer it is executed on, and reuses this ID across multiple calls.</span></span> <span data-ttu-id="ebf75-304">Deze ID wordt opgeslagen in het bestand _O365_endpoints_latestversion. txt_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-304">This ID is stored in the _O365_endpoints_latestversion.txt_ file.</span></span>

### <a name="to-run-the-powershell-script"></a><span data-ttu-id="ebf75-305">Het PowerShell-script uitvoeren</span><span class="sxs-lookup"><span data-stu-id="ebf75-305">To run the PowerShell script</span></span>

1. <span data-ttu-id="ebf75-306">Kopieer het script en sla het op uw lokale harde schijf of in een scriptlocatie op als _Get-O365WebServiceUpdates.ps1_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-306">Copy the script and save it to your local hard drive or script location as _Get-O365WebServiceUpdates.ps1_.</span></span>
1. <span data-ttu-id="ebf75-307">Voer het script uit in de gewenste scripteditor, zoals de PowerShell ISE of VS Code of met een PowerShell-console, met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="ebf75-307">Execute the script in your preferred script editor such as the PowerShell ISE or VS Code, or from a PowerShell console using the following command:</span></span>

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    <span data-ttu-id="ebf75-308">Er zijn geen parameters die moeten worden doorgegeven aan het script.</span><span class="sxs-lookup"><span data-stu-id="ebf75-308">There are no parameters to pass to the script.</span></span>

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a><span data-ttu-id="ebf75-309">Voorbeeld van Python-script</span><span class="sxs-lookup"><span data-stu-id="ebf75-309">Example Python Script</span></span>

<span data-ttu-id="ebf75-310">Hier ziet u een Python-script, getest met Python 3.6.3 onder Windows 10. U kunt het uitvoeren om te zien of er acties zijn die u moet ondernemen voor bijgewerkte gegevens.</span><span class="sxs-lookup"><span data-stu-id="ebf75-310">Here is a Python script, tested with Python 3.6.3 on Windows 10, that you can run to see if there are actions you need to take for updated data.</span></span> <span data-ttu-id="ebf75-311">Met dit script wordt het versienummer van de eindpunten van het Office 365 Worldwide-exemplaar gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="ebf75-311">This script checks the version number for the Office 365 Worldwide instance endpoints.</span></span> <span data-ttu-id="ebf75-312">Als er een wijziging is, worden de eindpunten gedownload en wordt er gefilterd op de eindpunten in de categorie _Toestaan_ en _Optimaliseren_.</span><span class="sxs-lookup"><span data-stu-id="ebf75-312">When there is a change, it downloads the endpoints and filters for the _Allow_ and _Optimize_ category endpoints.</span></span> <span data-ttu-id="ebf75-313">Er wordt ook een unieke ClientRequestId gebruikt voor meerdere aanroepen en wordt de nieuwste versie in een tijdelijk bestand opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-313">It also uses a unique ClientRequestId across multiple calls and saves the latest version found in a temporary file.</span></span> <span data-ttu-id="ebf75-314">Roep dit script eenmaal per uur aan om te controleren op een update van de versie.</span><span class="sxs-lookup"><span data-stu-id="ebf75-314">You should call this script once an hour to check for a version update.</span></span>

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a><span data-ttu-id="ebf75-315">Versiebeheer van webservice-interface</span><span class="sxs-lookup"><span data-stu-id="ebf75-315">Web Service interface versioning</span></span>

<span data-ttu-id="ebf75-316">In de toekomst zijn mogelijk updates van de parameters of resultaten van deze webservicemethoden vereist.</span><span class="sxs-lookup"><span data-stu-id="ebf75-316">Updates to the parameters or results for these web service methods may be required in the future.</span></span> <span data-ttu-id="ebf75-317">Nadat de versie voor algemene beschikbaarheid van deze webservices is gepubliceerd, zal Microsoft redelijke inspanningen betrachten om u vooraf op de hoogte te stellen van materiële updates van de webservice.</span><span class="sxs-lookup"><span data-stu-id="ebf75-317">After the general availability version of these web services is published, Microsoft will make reasonable efforts to provide advance notice of material updates to the web service.</span></span> <span data-ttu-id="ebf75-318">Indien Microsoft van mening is dat een update wijzigingen aan clients noodzakelijk maakt met behulp van de webservice, blijft de vorige versie van de webservice beschikbaar gedurende ten minste 12 maanden na de uitgifte van de nieuwe versie.</span><span class="sxs-lookup"><span data-stu-id="ebf75-318">When Microsoft believes that an update will require changes to clients using the web service, Microsoft will keep the previous version (one version back) of the web service available for at least 12 months after the release of the new version.</span></span> <span data-ttu-id="ebf75-319">Klanten die in die periode geen upgrade uitvoeren, kunnen mogelijk geen gebruik maken van de website en de bijbehorende methoden.</span><span class="sxs-lookup"><span data-stu-id="ebf75-319">Customers who do not upgrade during that time may be unable to access the web service and its methods.</span></span> <span data-ttu-id="ebf75-320">Klanten dienen zich ervoor te zorgen dat clients van de webservice foutloos blijven functioneren indien de volgende wijzigingen aan de handtekening van de webservice-interface worden aangebracht:</span><span class="sxs-lookup"><span data-stu-id="ebf75-320">Customers must ensure that clients of the web service continue working without error if the following changes are made to the web service interface signature:</span></span>

- <span data-ttu-id="ebf75-321">Het toevoegen van een nieuwe, optionele parameter aan een bestaande webmethode die niet hoeft te worden opgegeven door oudere clients en die geen invloed heeft op het resultaat dat een oudere client ontvangt.</span><span class="sxs-lookup"><span data-stu-id="ebf75-321">Adding a new optional parameter to an existing web method that doesn't have to be provided by older clients and doesn't impact the result an older client receives.</span></span>
- <span data-ttu-id="ebf75-322">Het toevoegen van een attribuut met een nieuwe naam aan een van de respons-REST-items of van aanvullende kolommen aan de respons-CSV.</span><span class="sxs-lookup"><span data-stu-id="ebf75-322">Adding a new named attribute in one of the response REST items or additional columns to the response CSV.</span></span>
- <span data-ttu-id="ebf75-323">Het toevoegen van een nieuwe webmethode met een nieuwe naam die niet door de oudere clients wordt aangeroepen.</span><span class="sxs-lookup"><span data-stu-id="ebf75-323">Adding a new web method with a new name that is not called by the older clients.</span></span>

## <a name="update-notifications"></a><span data-ttu-id="ebf75-324">Updatemeldingen</span><span class="sxs-lookup"><span data-stu-id="ebf75-324">Update notifications</span></span>

<span data-ttu-id="ebf75-325">U kunt een paar verschillende methoden gebruiken om e-mailmeldingen te ontvangen wanneer er wijzigingen in de IP-adressen en URL's worden gepubliceerd op de webservice.</span><span class="sxs-lookup"><span data-stu-id="ebf75-325">You can use a few different methods to get email notifications when changes to the IP addresses and URLs are published to the web service.</span></span>

- <span data-ttu-id="ebf75-326">Als u een Microsoft Flow-oplossing wilt gebruiken, raadpleegt u [Microsoft Flow gebruiken om een e-mail te ontvangen over wijzigingen aan Office 365-IP-adressen en URL's](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span><span class="sxs-lookup"><span data-stu-id="ebf75-326">To use a Microsoft Flow solution, see [Use Microsoft Flow to receive an email for changes to Office 365 IP Addresses and URLs](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span></span>
- <span data-ttu-id="ebf75-327">Als u een Azure Logic-app wilt implementeren met een ARM-sjabloon, raadpleegt u [Office 365 updatemelding (v 1.1)](https://aka.ms/ipurlws-updates-template).</span><span class="sxs-lookup"><span data-stu-id="ebf75-327">To deploy an Azure Logic App using an ARM template, see [Office 365 Update Notification (v1.1)](https://aka.ms/ipurlws-updates-template).</span></span>
- <span data-ttu-id="ebf75-328">Als u uw eigen meldingenscript wilt schrijven met PowerShell, raadpleegt u [Send-MailMessage](/powershell/module/microsoft.powershell.utility/send-mailmessage).</span><span class="sxs-lookup"><span data-stu-id="ebf75-328">To write your own notification script using PowerShell, see [Send-MailMessage](/powershell/module/microsoft.powershell.utility/send-mailmessage).</span></span>

## <a name="exporting-a-proxy-pac-file"></a><span data-ttu-id="ebf75-329">Een PAC-bestand voor een proxy exporteren</span><span class="sxs-lookup"><span data-stu-id="ebf75-329">Exporting a Proxy PAC file</span></span>

<span data-ttu-id="ebf75-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) is een PowerShell-script dat de meest recente netwerkeindpunten leest uit het IP-adres en de webservice-URL van Office 365 en een voorbeeld van een PAC-bestand maakt.</span><span class="sxs-lookup"><span data-stu-id="ebf75-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) is a PowerShell script that reads the latest network endpoints from the Office 365 IP Address and URL web service and creates a sample PAC file.</span></span> <span data-ttu-id="ebf75-331">Voor meer informatie over het gebruiken van Get-PacFile, raadpleegt u [Een PAC-bestand gebruiken voor directe routering van belangrijk Office 365-verkeer](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="ebf75-331">For information on using Get-PacFile, see [Use a PAC file for direct routing of vital Office 365 traffic](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ebf75-332">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ebf75-332">Related Topics</span></span>
  
[<span data-ttu-id="ebf75-333">URL's en IP-adresbereiken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ebf75-333">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="ebf75-334">Office 365-eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="ebf75-334">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)
  
[<span data-ttu-id="ebf75-335">Veelgestelde vragen over Office 365-eindpunten</span><span class="sxs-lookup"><span data-stu-id="ebf75-335">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[<span data-ttu-id="ebf75-336">Beginselen voor Office 365-netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="ebf75-336">Office 365 Network Connectivity Principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="ebf75-337">Aanpassing van Office 365-netwerk en -prestaties</span><span class="sxs-lookup"><span data-stu-id="ebf75-337">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="ebf75-338">Office 365-netwerkverbinding beoordelen</span><span class="sxs-lookup"><span data-stu-id="ebf75-338">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
[<span data-ttu-id="ebf75-339">Mediakwaliteit en prestaties van de netwerkverbinding in Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="ebf75-339">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[<span data-ttu-id="ebf75-340">Uw netwerk instellen voor Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="ebf75-340">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[<span data-ttu-id="ebf75-341">Office 365-prestatieafstemming gebruikt basislijnen en prestatiegeschiedenis</span><span class="sxs-lookup"><span data-stu-id="ebf75-341">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)
  
[<span data-ttu-id="ebf75-342">Prestatieproblemen met Office 365 oplossen: planning</span><span class="sxs-lookup"><span data-stu-id="ebf75-342">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)