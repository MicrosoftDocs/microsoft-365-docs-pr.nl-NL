---
title: Indicatoren maken
ms.reviewer: ''
description: Maak indicatoren voor een bestandshash, IP-adres, URL's of domeinen die de detectie, preventie en uitsluiting van entiteiten definiëren.
keywords: manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d54ab8eaa1e17be82752c480c963d3a24af56389
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187575"
---
# <a name="create-indicators"></a><span data-ttu-id="bea5d-104">Indicatoren maken</span><span class="sxs-lookup"><span data-stu-id="bea5d-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bea5d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bea5d-105">**Applies to:**</span></span>
- [<span data-ttu-id="bea5d-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="bea5d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bea5d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bea5d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="bea5d-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="bea5d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bea5d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="bea5d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="bea5d-110">Indicator voor compromissen (IOC's) is een essentiële functie in elke oplossing voor eindpuntbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="bea5d-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="bea5d-111">Deze mogelijkheid biedt SecOps de mogelijkheid om een lijst met indicatoren in te stellen voor detectie en voor blokkeren (preventie en reactie).</span><span class="sxs-lookup"><span data-stu-id="bea5d-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="bea5d-112">Maak indicatoren die de detectie, preventie en uitsluiting van entiteiten definiëren.</span><span class="sxs-lookup"><span data-stu-id="bea5d-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="bea5d-113">U kunt de actie definiëren die moet worden ondernomen, evenals de duur voor het toepassen van de actie en het bereik van de apparaatgroep waarop deze moet worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="bea5d-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="bea5d-114">Momenteel ondersteunde bronnen zijn de clouddetectie-engine van Defender voor Eindpunt, de geautomatiseerde onderzoeks- en herstelprogramma en de endpoint prevention engine (Microsoft Defender AV).</span><span class="sxs-lookup"><span data-stu-id="bea5d-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender AV).</span></span>

<span data-ttu-id="bea5d-115">**Clouddetectie-engine**</span><span class="sxs-lookup"><span data-stu-id="bea5d-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="bea5d-116">De clouddetectie-engine van Defender voor Eindpunt scant regelmatig verzamelde gegevens en probeert de indicatoren die u hebt ingesteld, aan te passen.</span><span class="sxs-lookup"><span data-stu-id="bea5d-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="bea5d-117">Wanneer er een overeenkomst is, wordt actie ondernomen op basis van de instellingen die u hebt opgegeven voor de IoC.</span><span class="sxs-lookup"><span data-stu-id="bea5d-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="bea5d-118">**Preventieprogramma voor eindpunten**</span><span class="sxs-lookup"><span data-stu-id="bea5d-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="bea5d-119">Dezelfde lijst met indicatoren wordt geëerd door het preventiemiddel.</span><span class="sxs-lookup"><span data-stu-id="bea5d-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="bea5d-120">Dit betekent dat als Microsoft Defender AV de primaire AV is geconfigureerd, de overeenkomende indicatoren worden behandeld volgens de instellingen.</span><span class="sxs-lookup"><span data-stu-id="bea5d-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="bea5d-121">Als de actie bijvoorbeeld 'Waarschuwing en blokkering' is, voorkomt Microsoft Defender AV dat bestandsuitvoeringen worden uitgevoerd (blokkeren en herstellen) en wordt een bijbehorende waarschuwing opgeheven.</span><span class="sxs-lookup"><span data-stu-id="bea5d-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="bea5d-122">Als de actie is ingesteld op 'Toestaan', wordt het bestand niet gedetecteerd of geblokkeerd door Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="bea5d-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="bea5d-123">**Geautomatiseerde onderzoeks- en herstel-engine**</span><span class="sxs-lookup"><span data-stu-id="bea5d-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="bea5d-124">Het automatische onderzoek en de herstelmaatregelen gedragen zich hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="bea5d-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="bea5d-125">Als een indicator is ingesteld op 'Toestaan', wordt automatisch onderzoek en herstel een 'slecht' vonnis voor de indicator genegeerd.</span><span class="sxs-lookup"><span data-stu-id="bea5d-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="bea5d-126">Als deze is ingesteld op 'Blokkeren', wordt dit als 'slecht' behandeld door automatisch onderzoek en herstel.</span><span class="sxs-lookup"><span data-stu-id="bea5d-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>


<span data-ttu-id="bea5d-127">De huidige ondersteunde acties zijn:</span><span class="sxs-lookup"><span data-stu-id="bea5d-127">The current supported actions are:</span></span>
- <span data-ttu-id="bea5d-128">Toestaan</span><span class="sxs-lookup"><span data-stu-id="bea5d-128">Allow</span></span>
- <span data-ttu-id="bea5d-129">Alleen waarschuwing</span><span class="sxs-lookup"><span data-stu-id="bea5d-129">Alert only</span></span>
- <span data-ttu-id="bea5d-130">Waarschuwing en blokkering</span><span class="sxs-lookup"><span data-stu-id="bea5d-130">Alert and block</span></span>


<span data-ttu-id="bea5d-131">U kunt een indicator maken voor:</span><span class="sxs-lookup"><span data-stu-id="bea5d-131">You can create an indicator for:</span></span>
- [<span data-ttu-id="bea5d-132">Bestanden</span><span class="sxs-lookup"><span data-stu-id="bea5d-132">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="bea5d-133">IP-adressen, URL's/domeinen</span><span class="sxs-lookup"><span data-stu-id="bea5d-133">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="bea5d-134">Certificaten</span><span class="sxs-lookup"><span data-stu-id="bea5d-134">Certificates</span></span>](indicator-certificates.md)


>[!NOTE]
><span data-ttu-id="bea5d-135">Er is een limiet van 15.000 indicatoren per tenant.</span><span class="sxs-lookup"><span data-stu-id="bea5d-135">There is a limit of 15,000 indicators per tenant.</span></span>


## <a name="related-topics"></a><span data-ttu-id="bea5d-136">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="bea5d-136">Related topics</span></span>

- [<span data-ttu-id="bea5d-137">Contextuele IoC maken</span><span class="sxs-lookup"><span data-stu-id="bea5d-137">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="bea5d-138">De API met Microsoft Defender voor eindpuntindicatoren gebruiken</span><span class="sxs-lookup"><span data-stu-id="bea5d-138">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="bea5d-139">Geïntegreerde partneroplossingen gebruiken</span><span class="sxs-lookup"><span data-stu-id="bea5d-139">Use partner integrated solutions</span></span>](partner-applications.md)
