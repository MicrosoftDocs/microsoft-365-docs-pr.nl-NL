---
title: 'Fase 1: Afsluitcriteria netwerkinfrastructuur'
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
description: Zorg ervoor dat uw configuratie voldoet aan de Microsoft 365 Enterprise-criteria voor de netwerkinfrastructuur.
ms.openlocfilehash: 1ace68fd19c62e4dc389604c1b0c02ddc18b52dc
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42809132"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="1b8ed-103">Fase 1: Afsluitcriteria netwerkinfrastructuur</span><span class="sxs-lookup"><span data-stu-id="1b8ed-103">Phase 1: Networking infrastructure exit criteria</span></span>

![Fase 1-Netwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="1b8ed-105">Zorg ervoor dat de netwerkinfrastructuur aan de volgende vereiste criteria voldoet en dat u de optionele criteria hebt overwogen.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-105">Make sure your networking infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="1b8ed-106">Vereist: uw netwerk is gereed voor Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1b8ed-106">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="1b8ed-107">Uw kantoren hebben een adequate internet-bandbreedte voor Microsoft 365-verkeer, waaronder Office 365-, Microsoft Intune- en Windows 10 Enterprise-installatie en -updates.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-107">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates.</span></span>
- <span data-ttu-id="1b8ed-108">Uw algehele netwerk is gekoppeld aan een [Office 365-referentiearchitectuur](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span><span class="sxs-lookup"><span data-stu-id="1b8ed-108">Your overall network maps to an [Office 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="1b8ed-109">De wijzigingen in uw netwerk zijn getest en getest en voldoen aan de vereisten voor uw netwerklatentie.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-109">Your network changes have been piloted and tested and meet with your traffic latency requirements.</span></span>

<span data-ttu-id="1b8ed-110">[Stap 1](networking-provide-bandwidth-cloud-services.md) kan u indien nodig helpen bij dit vereiste.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="1b8ed-111">Vereist: uw lokale kantoren hebben lokale internetverbindingen en naamomzetting</span><span class="sxs-lookup"><span data-stu-id="1b8ed-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="1b8ed-112">U hebt elk lokale kantoor uitgerust met een internetverbinding met een lokale internetprovider, wiens DNS-servers een lokaal openbaar IP-adres gebruiken waarmee de locatie op internet wordt aangeduid.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-112">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet.</span></span> <span data-ttu-id="1b8ed-113">Dit garandeert de best mogelijke prestaties voor gebruikers die toegang hebben tot de cloudservices van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-113">This ensures the best possible performance for users who access Microsoft 365 cloud services.</span></span>

<span data-ttu-id="1b8ed-114">Als u geen lokale internetprovider gebruikt voor elk filiaal, kan het zijn dat de prestaties hieronder leiden, aangezien het netwerkverkeer dan moet worden omgeleid langs de backbone van de organisatie of gegevensaanvragen door front-end servers moeten worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1b8ed-115">Testen</span><span class="sxs-lookup"><span data-stu-id="1b8ed-115">How to test</span></span>
<span data-ttu-id="1b8ed-116">Gebruik een hulpprogramma of website vanaf een apparaat in dat kantoor om te bepalen welk openbare IP-adres de proxyserver gebruikt.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-116">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using.</span></span> <span data-ttu-id="1b8ed-117">Gebruik bijvoorbeeld de [Wat is mijn IP-adres](https://www.whatismypublicip.com/)-webpagina.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-117">For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page.</span></span> <span data-ttu-id="1b8ed-118">Dit openbare IP-adres dat is toegewezen door uw internetprovider, zou geografisch lokaal moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-118">This public IP address assigned by your ISP should be geographically local.</span></span> <span data-ttu-id="1b8ed-119">Het mag niet afkomstig zijn van een openbaar IP-adresbereik voor een centraal kantoor of een netwerkbeveiligingsleverancier in de Cloud.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-119">It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="1b8ed-120">[Stap 2](networking-dns-resolution-same-location.md) kan u indien nodig helpen bij dit vereiste.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unnecessary-network-hairpins-are-removed"></a><span data-ttu-id="1b8ed-121">Optioneel: onnodige netwerkhairpins worden verwijderd</span><span class="sxs-lookup"><span data-stu-id="1b8ed-121">Optional: Unnecessary network hairpins are removed</span></span>

<span data-ttu-id="1b8ed-122">U hebt uw netwerkhairpins onderzocht en de effecten ervan op de prestaties van al uw kantoren bepaald.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-122">You examined your network hairpins and determined their impact on performance for all of your offices.</span></span> <span data-ttu-id="1b8ed-123">U hebt de netwerkhairpins waar mogelijk verwijderd of met uw externe netwerk- of beveiligingsprovider samengewerkt om optimale Microsoft 365-peering voor hun netwerk te implementeren.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-123">You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="1b8ed-124">[Stap 3](networking-avoid-network-hairpins.md) kan u indien nodig helpen bij deze optie.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="1b8ed-125">Optioneel: u hebt het omleiden van verkeer op uw internetbrowsers en randapparaten geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="1b8ed-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="1b8ed-126">U hebt de nieuwste PAC-bestanden geïmplementeerd in uw internetbrowsers op locatie, zodat verkeer naar DNS-domeinnamen van Microsoft 365 niet via de proxyservers wordt geleid.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="1b8ed-127">U hebt de apparaten voor uw netwerkperimeter geconfigureerd - zoals firewalls, SSL Break and Inspect en inspectieapparaten voor pakketten - om verkeer om te leiden of om het verkeer te beperken tot de categorieën Optimaliseren en toestaan van Microsoft 365-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="1b8ed-128">Testen</span><span class="sxs-lookup"><span data-stu-id="1b8ed-128">How to test</span></span>

<span data-ttu-id="1b8ed-129">Gebruik de hulpprogramma's voor logboekregistratie op uw apparaten voor uw netwerkperimeter om ervoor te zorgen dat verkeer naar Microsoft 365-bestemmingen niet wordt gecontroleerd, gedecodeerd of anderszins wordt belemmerd.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="1b8ed-130">[Stap 4](networking-configure-proxies-firewalls.md) kan u indien nodig helpen bij deze optie.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="1b8ed-131">Optioneel: uw clients en Office 365-toepassingen zijn geconfigureerd voor optimale prestaties</span><span class="sxs-lookup"><span data-stu-id="1b8ed-131">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="1b8ed-132">U hebt de TCP-instellingen (Transmission Control Protocol) geoptimaliseerd op uw clientapparaten en voor Exchange Online-, Skype voor Bedrijven Online-, SharePoint Online- en Project Online-services.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-132">You have optimized the Transmission Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="1b8ed-133">[Stap 5](networking-optimize-tcp-performance.md) kan u indien nodig helpen bij deze optie.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="1b8ed-134">Resultaten en volgende stappen</span><span class="sxs-lookup"><span data-stu-id="1b8ed-134">Results and next steps</span></span>

<span data-ttu-id="1b8ed-135">Uw intranet-gebruikers zijn nu klaar om Microsoft 365-cloudservices te gebruiken via een efficiënt netwerkpad naar en via internet.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-135">Your intranet users are now ready to consume Microsoft 365 cloud services over an efficient networking path to and across the Internet.</span></span>

|||
|:-------|:-----|
|![Fase 2-Identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="1b8ed-137">Als u de fasen voor de end-to-end-implementatie van Microsoft 365 Enterprise volgt, is [Identiteit](identity-infrastructure.md) de volgende fase.</span><span class="sxs-lookup"><span data-stu-id="1b8ed-137">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [identity](identity-infrastructure.md).</span></span> |
