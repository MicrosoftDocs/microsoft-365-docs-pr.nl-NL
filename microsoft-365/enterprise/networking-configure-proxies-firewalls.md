---
title: 'Stap 4: Omleiden van verkeer configureren'
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
description: Informatie over het gebruik en configureren van webbrowsers en edge-apparaten voor het omleiden van verkeer naar vertrouwde Office 365-locaties.
ms.openlocfilehash: 71f62c5e245962f3514c49477e3cdeda17cb6397
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806616"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="584d3-103">Stap 4: Omleiden van verkeer configureren</span><span class="sxs-lookup"><span data-stu-id="584d3-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="584d3-104">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="584d3-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1- Netwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="584d3-106">Aangezien algemeen internetverkeer riskant kan zijn, wordt doorgaans de beveiliging in organisatienetwerken afgedwongen door de edge-apparaten, zoals proxyservers, SSL-onderbreking en inspectie, pakketinspectie-apparaten en preventie van gegevensverlies.</span><span class="sxs-lookup"><span data-stu-id="584d3-106">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="584d3-107">Lees over enkele problemen met de netwerkinterceptie-apparaten op [Het gebruik van netwerkapparaten van derden of oplossingen voor Office 365-verkeer](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="584d3-107">Read about some of the issues with network interception devices at [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).</span></span>

<span data-ttu-id="584d3-108">De DNS-domeinnamen en IP-adressen die worden gebruikt door de cloudservices van Microsoft 365, zijn echter algemeen bekend.</span><span class="sxs-lookup"><span data-stu-id="584d3-108">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known.</span></span> <span data-ttu-id="584d3-109">Bovendien worden het verkeer en de services met veel beveiligingsfuncties beschermd.</span><span class="sxs-lookup"><span data-stu-id="584d3-109">Additionally, the traffic and services themselves are protected with many security features.</span></span> <span data-ttu-id="584d3-110">Omdat deze beveiliging en bescherming al aanwezig zijn, hoeven uw edge-apparaten het niet te dupliceren.</span><span class="sxs-lookup"><span data-stu-id="584d3-110">Because this security and protection is already in place, your edge devices don’t need to duplicate it.</span></span> <span data-ttu-id="584d3-111">Tussenliggende bestemmingen en dubbele beveiligingsprocessen voor Microsoft 365-verkeer kunnen de prestaties aanzienlijk verminderen.</span><span class="sxs-lookup"><span data-stu-id="584d3-111">Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="584d3-112">De eerste stap bij het elimineren van tussenliggende bestemmingen en gedupliceerde beveiligingsprocessen is om Microsoft 365-verkeer te identificeren.</span><span class="sxs-lookup"><span data-stu-id="584d3-112">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic.</span></span> <span data-ttu-id="584d3-113">Microsoft heeft de volgende typen DNS-domeinnamen en IP-adresbereiken in de zogenaamde eindpunten gedefinieerd:</span><span class="sxs-lookup"><span data-stu-id="584d3-113">Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="584d3-114">**Optimaliseer**- Vereist voor verbinding met elke Office 365-service en vertegenwoordigt 75% van de Microsoft 365-bandbreedte, verbindingen en een gegevensvolume.</span><span class="sxs-lookup"><span data-stu-id="584d3-114">**Optimize** - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data.</span></span> <span data-ttu-id="584d3-115">Deze eindpunten vertegenwoordigen Microsoft 365-scenario's die het gevoeligst zijn voor netwerkprestaties, latentie en beschikbaarheid.</span><span class="sxs-lookup"><span data-stu-id="584d3-115">These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency, and availability.</span></span>
- <span data-ttu-id="584d3-116">**Toestaan**- Vereist voor verbindingen met specifieke services en functies van Microsoft 365, maar zijn niet zo gevoelig voor netwerkprestaties en latentie als in de categorie Optimaliseer.</span><span class="sxs-lookup"><span data-stu-id="584d3-116">**Allow** - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="584d3-117">**Standaard**- Vertegenwoordigt Microsoft 365-services en afhankelijkheden waarvoor geen optimalisering nodig is.</span><span class="sxs-lookup"><span data-stu-id="584d3-117">**Default** - Represent Microsoft 365 services and dependencies that do not require any optimization.</span></span> <span data-ttu-id="584d3-118">U kunt Standaardeindpunten voor categorieën beschouwen als normaal internetverkeer.</span><span class="sxs-lookup"><span data-stu-id="584d3-118">You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="584d3-119">U vindt de DNS-domeinnamen en IP-adresbereiken op [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="584d3-119">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="584d3-120">Microsoft beveelt het volgende aan:</span><span class="sxs-lookup"><span data-stu-id="584d3-120">Microsoft recommends that you:</span></span>

- <span data-ttu-id="584d3-121">Gebruik de Proxy Automatic Configuration (PAC)-scripts voor de internetbrowsers van uw on-premises computers om uw proxyservers te omzeilen voor de DNS-domeinnamen van de cloudservices van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="584d3-121">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services.</span></span> <span data-ttu-id="584d3-122">Zie de [Get-Pacfile PowerShell script](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic) voor het nieuwste Microsoft 365-PAC-script.</span><span class="sxs-lookup"><span data-stu-id="584d3-122">For the latest Microsoft 365 PAC script, see the [Get-Pacfile PowerShell script](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

- <span data-ttu-id="584d3-123">Analyseer uw edge-apparaten om de dubbele verwerking te bepalen en vervolgens te configureren voor het doorsturen van verkeer om eindpunten te optimaliseren en toe te staan zonder te verwerken.</span><span class="sxs-lookup"><span data-stu-id="584d3-123">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing.</span></span> <span data-ttu-id="584d3-124">Dit wordt ook wel omleiden van netwerkverkeer genoemd.</span><span class="sxs-lookup"><span data-stu-id="584d3-124">This is known as traffic bypass.</span></span> 

<span data-ttu-id="584d3-125">Hier volgen deze aanbevelingen in de netwerkinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="584d3-125">Here are these recommendations in your network infrastructure.</span></span>

![Opmerkingen voor het optimaliseren van on-premises verkeer](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

<span data-ttu-id="584d3-127">Edge-apparaten bevatten firewalls, SSL Break and Inspect, apparaten voor pakketinspectie en preventie van gegevensverlies.</span><span class="sxs-lookup"><span data-stu-id="584d3-127">Edge devices include firewalls, SSL Break and Inspect, packet inspection devices, and data loss prevention systems.</span></span> <span data-ttu-id="584d3-128">Als u de configuratie van edge-apparaten wilt configureren en bijwerken, kunt u een script of een REST-oproep gebruiken om een gestructureerde lijst met eindpunten te gebruiken uit de Office 365 Eindpoints webservice.</span><span class="sxs-lookup"><span data-stu-id="584d3-128">To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service.</span></span> <span data-ttu-id="584d3-129">Zie [URL's en IP-adressen voor Office 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="584d3-129">For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="584d3-130">U hoeft alleen de normale proxy- en netwerkbeveilingsverwerking voor verkeer naar Microsoft 365 optimaliseren en toestaan van eindpunt-categorieën.</span><span class="sxs-lookup"><span data-stu-id="584d3-130">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints.</span></span> <span data-ttu-id="584d3-131">Al het andere algemene internetverkeer wordt via een proxy verzonden en zijn onderhevig aan de bestaande netwerkbeveiligingsverwerking.</span><span class="sxs-lookup"><span data-stu-id="584d3-131">All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="584d3-132">Als tussentijds controlepunt kunt u het [afsluitcriteria](networking-exit-criteria.md#crit-networking-step4) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="584d3-132">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="584d3-133">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="584d3-133">Next step</span></span>

|||
|:-------|:-----|
|![Stap 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="584d3-135">Prestaties van client en Office 365-service optimaliseren</span><span class="sxs-lookup"><span data-stu-id="584d3-135">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



