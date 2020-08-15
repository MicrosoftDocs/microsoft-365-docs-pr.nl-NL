---
title: Het netwerk instellen voor Microsoft 365
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
description: Hier vindt u koppelingen naar artikelen met informatie over het instellen van uw netwerk voor Microsoft 365, waaronder een overzicht van netwerkverbindingen en een lijst met eindpunten.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689006"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="8b940-103">Het netwerk instellen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b940-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="8b940-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8b940-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8b940-105">Een belangrijk onderdeel van uw Microsoft 365-onboarding is om ervoor te zorgen dat uw netwerk-en Internet verbindingen zijn ingesteld voor geoptimaliseerde toegang.</span><span class="sxs-lookup"><span data-stu-id="8b940-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="8b940-106">Uw on-premises netwerk configureren voor toegang tot een globale Distributed software-as-a-Service (SaaS) Cloud wijkt af van een traditioneel netwerk dat is geoptimaliseerd voor verkeer naar on-premises datacenters en een centrale Internet verbinding.</span><span class="sxs-lookup"><span data-stu-id="8b940-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="8b940-107">U kunt deze artikelen gebruiken om inzicht te krijgen in de belangrijkste verschillen en om uw edge-apparaten, clients en on-premises netwerk te wijzigen om de beste prestaties te verkrijgen voor uw on-premises gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8b940-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="8b940-108">De werking van Microsoft 365-netwerken</span><span class="sxs-lookup"><span data-stu-id="8b940-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="8b940-109">Zie de volgende artikelen voor een overzicht van connectiviteit voor Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="8b940-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="8b940-110">Overzicht van Microsoft 365-netwerkconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="8b940-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="8b940-111">Principes voor Microsoft 365-netwerkverbindingen</span><span class="sxs-lookup"><span data-stu-id="8b940-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="8b940-112">Microsoft 365-netwerkconnectiviteit beoordelen</span><span class="sxs-lookup"><span data-stu-id="8b940-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="8b940-113">Zie [netwerk planning en prestaties optimaliseren voor Microsoft 365](network-planning-and-performance.md)voor advies over het verbeteren van de prestaties.</span><span class="sxs-lookup"><span data-stu-id="8b940-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="8b940-114">Microsoft 365-netwerken ondersteunen als leverancier van netwerkapparatuur</span><span class="sxs-lookup"><span data-stu-id="8b940-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="8b940-115">Als u een leverancier van netwerkapparatuur bent, neemt u deel aan het [Office 365-programma](microsoft-365-networking-partner-program.md)voor de netwerk partner.</span><span class="sxs-lookup"><span data-stu-id="8b940-115">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="8b940-116">Meld u aan bij het programma voor het maken van de principes van Office 365-netwerkverbindingen in uw producten en oplossingen.</span><span class="sxs-lookup"><span data-stu-id="8b940-116">Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="8b940-117">Office 365-eindpunten</span><span class="sxs-lookup"><span data-stu-id="8b940-117">Office 365 endpoints</span></span>

<span data-ttu-id="8b940-118">Eindpunten zijn de set doel-IP-adressen, DNS-domeinnamen en Url's voor Office 365-verkeer op internet.</span><span class="sxs-lookup"><span data-stu-id="8b940-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="8b940-119">Voor het optimaliseren van de prestaties van de cloudservices van Office 365 moeten sommige eindpunten speciale functies hebben voor de clientbrowsers en de apparaten in het Edge-netwerk.</span><span class="sxs-lookup"><span data-stu-id="8b940-119">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network.</span></span> <span data-ttu-id="8b940-120">Deze apparaten zijn firewalls, SSL-onderbreking en inspectie-en pakket controleapparaten, en systemen voor preventie van gegevensverlies.</span><span class="sxs-lookup"><span data-stu-id="8b940-120">These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="8b940-121">Zie [Office 365-eindpunten beheren](managing-office-365-endpoints.md) voor de details.</span><span class="sxs-lookup"><span data-stu-id="8b940-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="8b940-122">Er zijn momenteel vijf verschillende Clouds van Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b940-122">There are currently five different Office 365 clouds.</span></span> <span data-ttu-id="8b940-123">In deze tabel vindt u een lijst met eindpunten voor elk item.</span><span class="sxs-lookup"><span data-stu-id="8b940-123">This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="8b940-124">Eindpunten</span><span class="sxs-lookup"><span data-stu-id="8b940-124">Endpoints</span></span> | <span data-ttu-id="8b940-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="8b940-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="8b940-126">Wereldwijde eindpunten</span><span class="sxs-lookup"><span data-stu-id="8b940-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="8b940-127">De eindpunten voor wereldwijde Office 365-abonnementen, waaronder de Verenigde Staten van de Cloud gemeenschappen van de overheid (GCC).</span><span class="sxs-lookup"><span data-stu-id="8b940-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="8b940-128">U.S. Government DoD-eindpunten</span><span class="sxs-lookup"><span data-stu-id="8b940-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="8b940-129">De eindpunten voor de Nederlandse afdeling van de defensie (DoD).</span><span class="sxs-lookup"><span data-stu-id="8b940-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="8b940-130">High-eindpunten van Amerikaanse overheid GCC</span><span class="sxs-lookup"><span data-stu-id="8b940-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="8b940-131">De eindpunten voor de Verenigde Staten Government Community High (GCC High)-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="8b940-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="8b940-132">Office 365 beheerd door 21Vianet-eindpunten</span><span class="sxs-lookup"><span data-stu-id="8b940-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="8b940-133">De eindpunten van Office 365, beheerd door 21Vianet, dat is ontworpen om te voldoen aan de behoeften van Office 365 in China.</span><span class="sxs-lookup"><span data-stu-id="8b940-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="8b940-134">Office 365 Duitsland-eindpunten</span><span class="sxs-lookup"><span data-stu-id="8b940-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="8b940-135">De eindpunten voor een aparte Cloud in Europa voor de meest gereglementeerde klanten in Duitsland, de Europese Unie (EU) en de Europese gratis Trade Association (EVA).</span><span class="sxs-lookup"><span data-stu-id="8b940-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="8b940-136">Als u de meest recente lijst met eindpunten voor uw Office 365-Cloud wilt automatiseren, raadpleegt u de [website IP Address and URL van office 365](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="8b940-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="8b940-137">Voor extra eindpunten raadpleegt u de volgende artikelen:</span><span class="sxs-lookup"><span data-stu-id="8b940-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="8b940-138">Extra eindpunten die niet zijn opgenomen in de webservice</span><span class="sxs-lookup"><span data-stu-id="8b940-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="8b940-139">Netwerkverzoeken in Office 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="8b940-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="8b940-140">Meer onderwerpen voor Microsoft 365-netwerken</span><span class="sxs-lookup"><span data-stu-id="8b940-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="8b940-141">Zie de volgende artikelen voor gespecialiseerde onderwerpen in Microsoft 365-netwerken:</span><span class="sxs-lookup"><span data-stu-id="8b940-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="8b940-142">Netwerken voor content levering</span><span class="sxs-lookup"><span data-stu-id="8b940-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="8b940-143">IPv6-ondersteuning in Office 365-Services</span><span class="sxs-lookup"><span data-stu-id="8b940-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="8b940-144">NAT-ondersteuning met Office 365</span><span class="sxs-lookup"><span data-stu-id="8b940-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="8b940-145">ExpressRoute voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b940-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="8b940-146">Zie de volgende artikelen voor informatie over het gebruik van ExpressRoute voor Office 365-verkeer:</span><span class="sxs-lookup"><span data-stu-id="8b940-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="8b940-147">Azure ExpressRoute voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8b940-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="8b940-148">ExpressRoute voor Office 365 implementeren</span><span class="sxs-lookup"><span data-stu-id="8b940-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="8b940-149">Netwerk planning met ExpressRoute voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8b940-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="8b940-150">Routeren met ExpressRoute voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8b940-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
