---
title: 'Stap 2: lokale internetverbindingen configureren voor elk kantoor'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Begrijp en configureer uw DNS-resolutie voor betere prestaties.
ms.openlocfilehash: 8b4302c06e75c59a1b99eb60399c9df897ad17ea
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810197"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="e0a88-103">Stap 2: lokale internetverbindingen configureren voor elk kantoor</span><span class="sxs-lookup"><span data-stu-id="e0a88-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="e0a88-104">*Deze stap is vereist en is van toepassing op zowel de E3- als de E5-versie van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e0a88-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1-Netwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="e0a88-106">In stap 2 zorgt u ervoor dat elk van uw kantoren lokale internetverbindingen heeft en lokale DNS-servers gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e0a88-106">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers.</span></span> <span data-ttu-id="e0a88-107">Beide elementen zijn vereist om de latentie van verbindingen te verminderen en ervoor te zorgen dat lokale client-computers verbindingen maken met het dichtstbijzijnde toegangspunt tot cloudservices van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a88-107">Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="e0a88-108">In traditionele netwerken voor grote organisaties gaat internetverkeer via de netwerk-backbone naar een centrale internetverbinding.</span><span class="sxs-lookup"><span data-stu-id="e0a88-108">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection.</span></span> <span data-ttu-id="e0a88-109">Dit werkt niet goed voor het optimaliseren van de prestaties voor een wereldwijd gedistribueerde Software-as-a-Service (SaaS)-infrastructuur, waaronder de Office 365- en Intune-producten in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0a88-109">This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Intune products in Microsoft 365.</span></span>

<span data-ttu-id="e0a88-110">Het Microsoft Global Network omvat een *Distributed Service Front Door*-infrastructuur, een zeer beschikbare en schaalbare netwerkrand met geografisch verspreide locaties.</span><span class="sxs-lookup"><span data-stu-id="e0a88-110">The Microsoft Global Network includes a *Distributed Service Front Door* infrastructure, a highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="e0a88-111">Het verbreekt verbindingen van eindgebruikers op een voordeurserver en routeert het verkeer van eindgebruikers op efficiënte wijze binnen het Microsoft Global Network.</span><span class="sxs-lookup"><span data-stu-id="e0a88-111">It terminates end user connections at a front door server and efficiently routes end user traffic within the Microsoft Global Network.</span></span>

![Het Microsoft Global Network](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

<span data-ttu-id="e0a88-113">Voor de beste prestaties moeten klanten op locatie toegang hebben tot een voordeurlocatie die zich geografisch het dichtst bij hen bevindt, in plaats van het verkeer via een netwerkbackbone te sturen naar de voordeur die het dichtst bij de centrale internetverbinding van de organisatie ligt.</span><span class="sxs-lookup"><span data-stu-id="e0a88-113">For the best performance, on-premises clients should access a front door location that is geographically closest to them, rather than sending the traffic over a network backbone and to the front door that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="e0a88-114">Hier ziet u een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e0a88-114">Here’s an example.</span></span>

![Voorbeeld van het gebruik van het Microsoft Global Network](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

<span data-ttu-id="e0a88-116">Wanneer een gebruiker in het filiaal in Parijs toegang wil krijgen tot een SharePoint Online-site:</span><span class="sxs-lookup"><span data-stu-id="e0a88-116">When a user in the Paris branch office wants to access a SharePoint Online site:</span></span>

1. <span data-ttu-id="e0a88-117">Er wordt een DNS-query verstuurd om een naam om te zetten, zoals contoso.sharepoint.com.</span><span class="sxs-lookup"><span data-stu-id="e0a88-117">It sends a DNS query to resolve a name, such as contoso.sharepoint.com.</span></span> 
2. <span data-ttu-id="e0a88-118">De DNS-server van de internetprovider stuurt die query door naar een Microsoft DNS-server.</span><span class="sxs-lookup"><span data-stu-id="e0a88-118">The DNS server provided by the ISP forwards that query to a Microsoft DNS server.</span></span>
3. <span data-ttu-id="e0a88-119">De DNS-servers van Microsoft stemmen het bron-IP-adres van de doorgestuurde DNS-query af op de regio van de wereld waaraan dat adres is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="e0a88-119">Microsoft’s DNS servers match the source IP address of the forwarded DNS query to the region of the world assigned that address.</span></span> <span data-ttu-id="e0a88-120">De Microsoft DNS-server reageert met het IP-adres van de dichtstbijzijnde Microsoft Network-voordeur in Europa.</span><span class="sxs-lookup"><span data-stu-id="e0a88-120">The Microsoft DNS server responds with the IP address of the nearest Microsoft Network front door in Europe.</span></span>
4. <span data-ttu-id="e0a88-121">De DNS-server van de internetprovider stuurt dit IP-adres naar de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e0a88-121">The ISP DNS server sends that IP address to the user.</span></span>
5. <span data-ttu-id="e0a88-122">De gebruiker brengt via de voordeur van Europa een verbinding tot stand met de SharePoint-server.</span><span class="sxs-lookup"><span data-stu-id="e0a88-122">The user initiates a connection to the SharePoint server through the Europe front door.</span></span>

<span data-ttu-id="e0a88-123">De DNS-servers van Microsoft gebruiken de DNS-query's die overeenkomen met de oorspronkelijke verbindingsaanvragen van de client om een clientaanvraag naar de geografisch dichtstbijzijnde voordeur te sturen.</span><span class="sxs-lookup"><span data-stu-id="e0a88-123">To direct a client request to the geographically nearest front door, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request.</span></span> <span data-ttu-id="e0a88-124">Voor de laagste netwerklatentie is het volgende van belang:</span><span class="sxs-lookup"><span data-stu-id="e0a88-124">Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="e0a88-125">Alle kantoren van uw organisatie moeten lokale internetverbindingen hebben voor netwerkverkeer in de categorie [optimaliseren](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="e0a88-125">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="e0a88-126">Elke lokale internetverbinding moet een regionale, lokale DNS-server gebruiken voor uitgaand internetverkeer vanaf die locatie.</span><span class="sxs-lookup"><span data-stu-id="e0a88-126">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="e0a88-127">Zie [uitgaande netwerkverbindingen lokaal instellen](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e0a88-127">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="e0a88-128">Als tussentijds controlepunt kunt u de [afsluitcriteria](networking-exit-criteria.md#crit-networking-step2) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="e0a88-128">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e0a88-129">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="e0a88-129">Next step</span></span>

|||
|:-------|:-----|
|![Stap 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="e0a88-131">Netwerk-hairpins vermijden</span><span class="sxs-lookup"><span data-stu-id="e0a88-131">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
