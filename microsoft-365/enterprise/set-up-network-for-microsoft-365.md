---
title: Uw netwerk instellen voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Vind koppelingen naar artikelen met informatie om u te helpen uw netwerk in te stellen voor Microsoft 365, waaronder een overzicht van netwerkconnectiviteit en een lijst met eindpunten.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689006"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="1d179-103">Uw netwerk instellen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1d179-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="1d179-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1d179-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1d179-105">Een belangrijk onderdeel van uw Microsoft 365 onboarding is ervoor te zorgen dat uw netwerk en internetverbinding zijn ingesteld voor geoptimaliseerde toegang.</span><span class="sxs-lookup"><span data-stu-id="1d179-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="1d179-106">Het configureren van uw on-premises netwerk om toegang te krijgen tot een saas-cloud (Software-as-a-Service) die wereldwijd wordt gedistribueerd, verschilt van een traditioneel netwerk dat is geoptimaliseerd voor verkeer naar on-premises datacenters en een centrale internetverbinding.</span><span class="sxs-lookup"><span data-stu-id="1d179-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="1d179-107">Gebruik deze artikelen om de belangrijkste verschillen te begrijpen en om uw edge-apparaten, clientcomputers en on-premises netwerk te wijzigen om de beste prestaties te krijgen voor uw on-premises gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1d179-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="1d179-108">Hoe Microsoft 365 netwerken werkt</span><span class="sxs-lookup"><span data-stu-id="1d179-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="1d179-109">Zie deze artikelen voor een overzicht van connectiviteit voor Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="1d179-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="1d179-110">Overzicht van netwerkverbindingen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1d179-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="1d179-111">Beginselen voor Microsoft 365-netwerkverbindingen</span><span class="sxs-lookup"><span data-stu-id="1d179-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="1d179-112">Microsoft 365-netwerkverbindingen evalueren</span><span class="sxs-lookup"><span data-stu-id="1d179-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="1d179-113">Zie Netwerkplanning en prestatieafstemming voor meer [Microsoft 365.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="1d179-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="1d179-114">Ondersteuning Microsoft 365 netwerken als leverancier van netwerkapparatuur</span><span class="sxs-lookup"><span data-stu-id="1d179-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="1d179-115">Als u een leverancier van netwerkapparatuur bent, kunt u deelnemen aan [de Office 365 Networking Partner Program.](microsoft-365-networking-partner-program.md)</span><span class="sxs-lookup"><span data-stu-id="1d179-115">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="1d179-116">Schrijf u in voor het programma om Office 365 netwerkconnectiviteitsprincipes in te bouwen in uw producten en oplossingen.</span><span class="sxs-lookup"><span data-stu-id="1d179-116">Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="1d179-117">Office 365-eindpunten</span><span class="sxs-lookup"><span data-stu-id="1d179-117">Office 365 endpoints</span></span>

<span data-ttu-id="1d179-118">Eindpunten zijn de set doel-IP-adressen, DNS-domeinnamen en URL's voor Office 365 internetverkeer.</span><span class="sxs-lookup"><span data-stu-id="1d179-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="1d179-119">Als u de prestaties wilt optimaliseren Office 365 cloudservices, hebben sommige eindpunten speciale verwerking nodig door uw clientbrowsers en de apparaten in uw edge-netwerk.</span><span class="sxs-lookup"><span data-stu-id="1d179-119">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network.</span></span> <span data-ttu-id="1d179-120">Deze apparaten omvatten firewalls, SSL-apparaten voor het breken en controleren en controleren van pakketten en preventiesystemen voor gegevensverlies.</span><span class="sxs-lookup"><span data-stu-id="1d179-120">These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="1d179-121">Zie [Beheer Office 365 eindpunten](managing-office-365-endpoints.md) voor de details.</span><span class="sxs-lookup"><span data-stu-id="1d179-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="1d179-122">Er zijn momenteel vijf verschillende Office 365 wolken.</span><span class="sxs-lookup"><span data-stu-id="1d179-122">There are currently five different Office 365 clouds.</span></span> <span data-ttu-id="1d179-123">Met deze tabel gaat u naar de lijst met eindpunten voor elk eindpunt.</span><span class="sxs-lookup"><span data-stu-id="1d179-123">This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="1d179-124">Eindpunten</span><span class="sxs-lookup"><span data-stu-id="1d179-124">Endpoints</span></span> | <span data-ttu-id="1d179-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1d179-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="1d179-126">Wereldwijde eindpunten</span><span class="sxs-lookup"><span data-stu-id="1d179-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="1d179-127">De eindpunten voor wereldwijde Office 365 abonnementen, waaronder de Verenigde Staten Government Community Cloud (GCC).</span><span class="sxs-lookup"><span data-stu-id="1d179-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="1d179-128">Eindpunten voor U.S. Government DoD</span><span class="sxs-lookup"><span data-stu-id="1d179-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="1d179-129">De eindpunten voor abonnementen van het Amerikaanse ministerie van Defensie (DoD).</span><span class="sxs-lookup"><span data-stu-id="1d179-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="1d179-130">Eindpunten voor U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="1d179-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="1d179-131">De eindpunten voor amerikaanse Government Community Cloud High (GCC High) abonnementen.</span><span class="sxs-lookup"><span data-stu-id="1d179-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="1d179-132">Office 365 beheerd door 21Vianet-eindpunten</span><span class="sxs-lookup"><span data-stu-id="1d179-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="1d179-133">De eindpunten voor Office 365 beheerd door 21Vianet, dat is ontworpen om te voldoen aan de behoeften voor Office 365 in China.</span><span class="sxs-lookup"><span data-stu-id="1d179-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="1d179-134">Office 365 eindpunten Germany-eindpunten</span><span class="sxs-lookup"><span data-stu-id="1d179-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="1d179-135">De eindpunten voor een afzonderlijke cloud in Europa voor de meest gereguleerde klanten in Duitsland, de Europese Unie (EU) en de European Free Trade Association (EFTA).</span><span class="sxs-lookup"><span data-stu-id="1d179-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="1d179-136">Als u het verkrijgen van de meest recente lijst met eindpunten voor uw Office 365 cloud wilt automatiseren, bekijkt u de Office 365 [IP-adres en URL-webservice.](microsoft-365-ip-web-service.md)</span><span class="sxs-lookup"><span data-stu-id="1d179-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="1d179-137">Zie deze artikelen voor meer eindpunten:</span><span class="sxs-lookup"><span data-stu-id="1d179-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="1d179-138">Aanvullende eindpunten die niet zijn opgenomen in de webservice</span><span class="sxs-lookup"><span data-stu-id="1d179-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="1d179-139">Netwerkaanvragen in Office 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="1d179-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="1d179-140">Aanvullende onderwerpen voor Microsoft 365 netwerken</span><span class="sxs-lookup"><span data-stu-id="1d179-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="1d179-141">Zie deze artikelen voor gespecialiseerde onderwerpen in Microsoft 365 netwerken:</span><span class="sxs-lookup"><span data-stu-id="1d179-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="1d179-142">Netwerken voor contentlevering</span><span class="sxs-lookup"><span data-stu-id="1d179-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="1d179-143">IPv6-ondersteuning in Office 365-services</span><span class="sxs-lookup"><span data-stu-id="1d179-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="1d179-144">Ondersteuning voor NAT met Office 365</span><span class="sxs-lookup"><span data-stu-id="1d179-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="1d179-145">ExpressRoute voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1d179-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="1d179-146">Zie deze artikelen voor informatie over het gebruik van ExpressRoute voor Office 365 verkeer:</span><span class="sxs-lookup"><span data-stu-id="1d179-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="1d179-147">Azure ExpressRoute voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1d179-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="1d179-148">ExpressRoute implementeren voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1d179-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="1d179-149">Netwerkplanning met ExpressRoute voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1d179-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="1d179-150">Routeren met ExpressRoute voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1d179-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
