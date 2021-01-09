---
title: Office 365-URL's en IP-adresbereiken
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/04/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Overzicht: Office 365 vereist verbinding met internet. De volgende eindpunten moeten bereikbaar zijn voor klanten die gebruikmaken van Office 365-abonnementen, waaronder Government Community Cloud (GCC).'
hideEdit: true
ms.openlocfilehash: 88837f495caac13db5bf029354d3a27ffa21dba6
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787689"
---
# <a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="02a31-104">Office 365-URL's en IP-adresbereiken</span><span class="sxs-lookup"><span data-stu-id="02a31-104">Office 365 URLs and IP address ranges</span></span>

<span data-ttu-id="02a31-105">Office 365 vereist verbinding met internet.</span><span class="sxs-lookup"><span data-stu-id="02a31-105">Office 365 requires connectivity to the Internet.</span></span> <span data-ttu-id="02a31-106">De volgende eindpunten moeten bereikbaar zijn voor klanten die gebruikmaken van Office 365-abonnementen, waaronder Government Community Cloud (GCC).</span><span class="sxs-lookup"><span data-stu-id="02a31-106">The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).</span></span>
  
<span data-ttu-id="02a31-107">*Office 365 Worldwide (+GCC)* | [Office 365 beheerd door 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span><span class="sxs-lookup"><span data-stu-id="02a31-107">*Office 365 Worldwide (+GCC)* | [Office 365 operated by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="02a31-108">**Laatst bijgewerkt:** 01-04-2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abonnement op wijzigingenlogboek](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="02a31-108">**Last updated:** 01/04/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span> <br/> |<span data-ttu-id="02a31-109">**Downloaden:** alle vereiste en optionele bestemmingen in één lijst in [JSON-indeling](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="02a31-109">**Download:** all required and optional destinations in one [JSON formatted](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) list.</span></span>  <br/> | <span data-ttu-id="02a31-110">**Gebruik:** onze proxy-[PAC-bestanden](managing-office-365-endpoints.md#pacfiles)</span><span class="sxs-lookup"><span data-stu-id="02a31-110">**Use:** our proxy [PAC files](managing-office-365-endpoints.md#pacfiles)</span></span> <br/> |

 <span data-ttu-id="02a31-111">Begin met [Het beheren van Office 365-eindpunten](managing-office-365-endpoints.md) om onze aanbevelingen voor het beheren van netwerkverbindingen met deze gegevens te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="02a31-111">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data.</span></span> <span data-ttu-id="02a31-112">Eindpuntgegevens worden aan het begin van elke maand bijgewerkt met nieuwe IP-adressen en URL's die worden gepubliceerd 30 dagen voordat ze actief worden.</span><span class="sxs-lookup"><span data-stu-id="02a31-112">Endpoints data is updated at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active.</span></span> <span data-ttu-id="02a31-113">Dit maakt het voor klanten die nog geen geautomatiseerde updates hebben mogelijk om hun processen te voltooien voordat er een nieuwe verbinding is vereist.</span><span class="sxs-lookup"><span data-stu-id="02a31-113">This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required.</span></span> <span data-ttu-id="02a31-114">Eindpuntgegevens kunnen ook gedurende de maand worden bijgewerkt indien nodig om escalaties van ondersteuningen, beveiligingsincidenten of andere directe operationele vereisten aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="02a31-114">Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements.</span></span> <span data-ttu-id="02a31-115">De gegevens die op deze pagina worden weergegeven, zijn allemaal gegenereerd op basis van de REST-webservice.</span><span class="sxs-lookup"><span data-stu-id="02a31-115">The data shown on this page below is all generated from the REST-based web services.</span></span> <span data-ttu-id="02a31-116">Als u gebruikmaakt van een script of netwerkapparaat voor toegang tot deze gegevens, gaat u rechtstreeks naar de [Webservice](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="02a31-116">If you are using a script or a network device to access this data, you should go to the [Web service](microsoft-365-ip-web-service.md) directly.</span></span>

<span data-ttu-id="02a31-117">De onderstaande eindpuntgegevens geven een overzicht van de vereisten voor verbinding tussen de computer van een gebruiker en Office 365.</span><span class="sxs-lookup"><span data-stu-id="02a31-117">Endpoint data below lists requirements for connectivity from a user's machine to Office 365.</span></span> <span data-ttu-id="02a31-118">Het omvat geen netwerkverbindingen van Microsoft naar een klantennetwerk, ook wel hybride of inkomende netwerkverbindingen genoemd.</span><span class="sxs-lookup"><span data-stu-id="02a31-118">It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections.</span></span> <span data-ttu-id="02a31-119">Zie [Aanvullende eindpunten](additional-office365-ip-addresses-and-urls.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="02a31-119">See [Additional endpoints](additional-office365-ip-addresses-and-urls.md) for more information.</span></span>

<span data-ttu-id="02a31-120">De eindpunten worden ingedeeld in vier servicegebieden.</span><span class="sxs-lookup"><span data-stu-id="02a31-120">The endpoints are grouped into four service areas.</span></span> <span data-ttu-id="02a31-121">De eerste drie servicegebieden kunnen afzonderlijk worden geselecteerd om verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="02a31-121">The first three service areas can be independently selected for connectivity.</span></span> <span data-ttu-id="02a31-122">Het vierde servicegebied is een gangbare afhankelijkheid (met de naam Microsoft 365 Common en Office) en moet altijd een netwerkverbinding hebben.</span><span class="sxs-lookup"><span data-stu-id="02a31-122">The fourth service area is a common dependency (called Microsoft 365 Common and Office) and must always have network connectivity.</span></span>

<span data-ttu-id="02a31-123">De getoonde gegevenskolommen zijn:</span><span class="sxs-lookup"><span data-stu-id="02a31-123">Data columns shown are:</span></span>

- <span data-ttu-id="02a31-124">**ID**: Het ID-nummer van de rij, ook wel een eindpuntenset genoemd.</span><span class="sxs-lookup"><span data-stu-id="02a31-124">**ID**: The ID number of the row, also known as an endpoint set.</span></span> <span data-ttu-id="02a31-125">Deze ID is hetzelfde als die door de webservice wordt geretourneerd voor de eindpuntenset.</span><span class="sxs-lookup"><span data-stu-id="02a31-125">This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="02a31-126">**Category**: Toon of de eindpuntenset wordt gecategoriseerd als "Optimaliseren", "Toestaan" of "Standaard".</span><span class="sxs-lookup"><span data-stu-id="02a31-126">**Category**: Shows whether the endpoint set is categorized as "Optimize", "Allow", or "Default".</span></span> <span data-ttu-id="02a31-127">U vindt meer informatie over deze categorieën en richtlijnen voor het beheren ervan in [Nieuwe Office 365-eindpuntcategorieën](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="02a31-127">You can read about these categories and guidance for management of them at [New Office 365 endpoint categories](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="02a31-128">In deze kolom wordt ook aangegeven welke eindpuntensets vereist zijn voor netwerkverbinding.</span><span class="sxs-lookup"><span data-stu-id="02a31-128">This column also lists which endpoint sets are required to have network connectivity.</span></span> <span data-ttu-id="02a31-129">Voor eindpuntensets die geen netwerkverbinding hoeven te hebben, geven we in dit veld notities om aan te geven welke functionaliteit ontbreekt als de eindpuntenset wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="02a31-129">For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked.</span></span> <span data-ttu-id="02a31-130">Als u een volledig servicegebied uitsluit, vereisen de eindpuntensets die als verplicht worden genoemd geen verbinding.</span><span class="sxs-lookup"><span data-stu-id="02a31-130">If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="02a31-131">**ER**: Dit is **Ja** als de eindpuntenset wordt ondersteund via Azure ExpressRoute met Office 365-routeprefixen.</span><span class="sxs-lookup"><span data-stu-id="02a31-131">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes.</span></span> <span data-ttu-id="02a31-132">De BGP-community met de weergegeven routeprefixen komt overeen met het weergegeven servicegebied.</span><span class="sxs-lookup"><span data-stu-id="02a31-132">The BGP community that includes the route prefixes shown aligns with the service area listed.</span></span> <span data-ttu-id="02a31-133">Als ER **Nee** is, betekent het dat ExpressRoute niet wordt ondersteund voor deze eindpuntenset.</span><span class="sxs-lookup"><span data-stu-id="02a31-133">When ER is **No**, this means that ExpressRoute is not supported for this endpoint set.</span></span> <span data-ttu-id="02a31-134">U dient er echter niet vanuit te gaan dat er geen routes worden genoemd voor een eindpuntenset waarvan ER **Nee** is.</span><span class="sxs-lookup"><span data-stu-id="02a31-134">However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="02a31-135">**Adressen**: Hier worden de FQDN‘s of wildcard-domeinnamen en IP-adresbereiken voor de eindpuntenset weergegeven.</span><span class="sxs-lookup"><span data-stu-id="02a31-135">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set.</span></span> <span data-ttu-id="02a31-136">Houd er rekening mee dat een IP-adresbereik de CIDR-indeling heeft en mogelijk veel afzonderlijke IP-adressen bevat in het opgegeven netwerk.</span><span class="sxs-lookup"><span data-stu-id="02a31-136">Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>
 
- <span data-ttu-id="02a31-137">**Poorten**: Bevat de TCP- of UDP-poorten die worden gecombineerd met de adressen om het netwerkeindpunt te vormen.</span><span class="sxs-lookup"><span data-stu-id="02a31-137">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint.</span></span> <span data-ttu-id="02a31-138">Het is mogelijk dat er een aantal dubbele waarden worden weergegeven in de IP-adresbereiken waarvoor verschillende poorten worden genoemd.</span><span class="sxs-lookup"><span data-stu-id="02a31-138">You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
><span data-ttu-id="02a31-139">Zie [dit blogbericht](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) voor aanbevelingen voor IP-adressen en URL's van Yammer.</span><span class="sxs-lookup"><span data-stu-id="02a31-139">For recommendations on Yammer IP addresses and URLs, see [this blog post](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592).</span></span>
>

## <a name="related-topics"></a><span data-ttu-id="02a31-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="02a31-140">Related Topics</span></span>

[<span data-ttu-id="02a31-141">Office 365-eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="02a31-141">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="02a31-142">Algemene Microsoft Stream-eindpunten</span><span class="sxs-lookup"><span data-stu-id="02a31-142">General Microsoft Stream endpoints</span></span>](https://docs.microsoft.com/stream/network-overview#general-microsoft-stream-endpoints)
  
[<span data-ttu-id="02a31-143">Microsoft 365-connectiviteit controleren</span><span class="sxs-lookup"><span data-stu-id="02a31-143">Monitor Microsoft 365 connectivity</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/monitor-connectivity?view=o365-worldwide)

[<span data-ttu-id="02a31-144">De basis- en gemiddelde CA-bundel op het toepassingssysteem van derden</span><span class="sxs-lookup"><span data-stu-id="02a31-144">Root CA and the Intermediate CA bundle on the third-party application system</span></span>](../compliance/encryption-office-365-certificate-chains.md)
  
[<span data-ttu-id="02a31-145">Clientconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="02a31-145">Client connectivity</span></span>](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[<span data-ttu-id="02a31-146">Netwerken voor contentlevering</span><span class="sxs-lookup"><span data-stu-id="02a31-146">Content delivery networks</span></span>](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[<span data-ttu-id="02a31-147">IP-bereiken van Microsoft Azure Datacenter</span><span class="sxs-lookup"><span data-stu-id="02a31-147">Microsoft Azure Datacenter IP Ranges</span></span>](https://www.microsoft.com/download/details.aspx?id=41653)
  
[<span data-ttu-id="02a31-148">Microsoft Public IP Space</span><span class="sxs-lookup"><span data-stu-id="02a31-148">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)
