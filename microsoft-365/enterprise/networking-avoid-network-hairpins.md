---
title: 'Stap 3: Netwerkhairpins vermijden'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Inzicht krijgen in netwerkhairpins en deze verwijderen voor betere prestaties.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583423"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="6b2fc-103">Stap 3: Netwerkhairpins vermijden</span><span class="sxs-lookup"><span data-stu-id="6b2fc-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="6b2fc-104">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="6b2fc-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1-netwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="6b2fc-106">Een [netwerkhairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) treedt op wanneer het verkeer dat voor een bestemming is bedoeld, eerst wordt doorgestuurd naar een andere tussenliggende locatie, zoals een on-premises beveiligingsstack, een cloud access broker of een cloud-webgateway.</span><span class="sxs-lookup"><span data-stu-id="6b2fc-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="6b2fc-107">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="6b2fc-107">Here is an example.</span></span>

![Voorbeeld van een netwerkhairpin](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="6b2fc-109">Een netwerkhairpin kan ook worden veroorzaakt door een slechte routering op internet vanwege netwerkserviceproviders.</span><span class="sxs-lookup"><span data-stu-id="6b2fc-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="6b2fc-110">Een hairpin voegt latentie toe en kan mogelijk verkeer omleiden naar een geografisch afgelegen locatie.</span><span class="sxs-lookup"><span data-stu-id="6b2fc-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="6b2fc-111">Als u de prestaties van het verkeer naar de cloudservices van Microsoft 365 wilt optimaliseren, controleert u of de internetprovider die de lokale Internet verbinding biedt een directe relatie heeft met het wereldwijde Microsoft-netwerk.</span><span class="sxs-lookup"><span data-stu-id="6b2fc-111">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location.</span></span> <span data-ttu-id="6b2fc-112">Deze verbindingen hebben geen hairpins.</span><span class="sxs-lookup"><span data-stu-id="6b2fc-112">These connections do not have hairpins.</span></span>

<span data-ttu-id="6b2fc-113">Als u in de cloud-based netwerk- of beveiligingsservices gebruikt voor uw Microsoft 365-verkeer, moet u ervoor zorgen dat het hairpinning-effect wordt geëvalueerd en u inzicht hebt op de invloed op prestaties.</span><span class="sxs-lookup"><span data-stu-id="6b2fc-113">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood.</span></span> <span data-ttu-id="6b2fc-114">Bekijk het volgende:</span><span class="sxs-lookup"><span data-stu-id="6b2fc-114">Examine the following:</span></span>

- <span data-ttu-id="6b2fc-115">Het aantal en de locaties van uw serviceproviders waarmee het verkeer wordt doorgestuurd ten opzichte van de filialen en de peeringpunten van het Microsoft Global Network</span><span class="sxs-lookup"><span data-stu-id="6b2fc-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="6b2fc-116">De kwaliteit van de peeringrelatie op het netwerk van de serviceprovider met uw internetprovider en Microsoft</span><span class="sxs-lookup"><span data-stu-id="6b2fc-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="6b2fc-117">Het prestatieresultaat van het backhaulen in de infrastructuur van de serviceprovider</span><span class="sxs-lookup"><span data-stu-id="6b2fc-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="6b2fc-118">Configureer zo mogelijk de edge-routers om rechtstreeks vertrouwd Microsoft 365-verkeer te verzenden, in plaats van via een cloud van een derde partij of het netwerk van een cloud-based beveiligingsleverancier voor de verwerking van uw internetverkeer.</span><span class="sxs-lookup"><span data-stu-id="6b2fc-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![Hier volgt een voorbeeld van het omzeilen van een netwerkhairpin](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="6b2fc-120">Gebruik het [Office 365 Network Onboarding-hulpprogramma](https://connectivity.office.com/) om te testen hoe dicht u bij een invoerpunt voor het globale netwerk van Microsoft bent en hoe dicht u bij een punt bent waar uw bedrijfsnetwerk de verbinding maakt met uw ISP.</span><span class="sxs-lookup"><span data-stu-id="6b2fc-120">To test how close you are to an entry point for Microsoft’s global network and how close you are to the point where your organization network connects to your ISP, use the [Office 365 Network Onboarding tool](https://connectivity.office.com/).</span></span>

<span data-ttu-id="6b2fc-121">Als tussentijds controlepunt kunt u de [afsluitcriteria](networking-exit-criteria.md#crit-networking-step3) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="6b2fc-121">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="6b2fc-122">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="6b2fc-122">Next step</span></span>

|||
|:-------|:-----|
|![Stap 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="6b2fc-124">Omleiden van verkeer configureren</span><span class="sxs-lookup"><span data-stu-id="6b2fc-124">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
