---
title: Microsoft Defender voor endpoint-partnerkansen en -scenario's
ms.reviewer: ''
description: Meer informatie over hoe u bestaande beveiligingsaanbiedingen kunt uitbreiden boven op het open framework en een uitgebreide set API's om extensies en integraties te maken met Microsoft Defender voor Eindpunt
keywords: API, partner, extend, open framework, api's, extensies, integraties, detectie, beheer, antwoord, kwetsbaarheden, intelligentie
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: be2f33514a568f290a3fc5cf0adc62db72243a6f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861105"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a><span data-ttu-id="9ab37-104">Microsoft Defender voor endpoint-partnerkansen en -scenario's</span><span class="sxs-lookup"><span data-stu-id="9ab37-104">Microsoft Defender for Endpoint partner opportunities and scenarios</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9ab37-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9ab37-105">**Applies to:**</span></span>
- [<span data-ttu-id="9ab37-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="9ab37-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9ab37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ab37-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="9ab37-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="9ab37-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9ab37-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="9ab37-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="9ab37-110">Partners kunnen eenvoudig hun bestaande beveiligingsaanbiedingen uitbreiden op de top van het open framework en een uitgebreide en volledige set API's om extensies en integraties te bouwen met Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="9ab37-110">Partners can easily extend their existing security offerings on top of the open framework and a rich and complete set of APIs to build extensions and integrations with Defender for Endpoint.</span></span> 

<span data-ttu-id="9ab37-111">De API's hebben een bereik van functionele gebieden, waaronder detectie, beheer, antwoord, beveiligingsproblemen en een breed scala aan gebruiksgevallen voor informatie.</span><span class="sxs-lookup"><span data-stu-id="9ab37-111">The APIs span functional areas including detection, management, response, vulnerabilities, and intelligence-wide range of use cases.</span></span> <span data-ttu-id="9ab37-112">Op basis van de gebruikscase en de behoefte kunnen partners gegevens streamen of query's uitvoeren vanuit Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="9ab37-112">Based on the use case and need, partners can either stream or query data from Defender for Endpoint.</span></span> 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a><span data-ttu-id="9ab37-113">Scenario 1: Externe waarschuwingscorrelatie en Automatisch onderzoek en herstel</span><span class="sxs-lookup"><span data-stu-id="9ab37-113">Scenario 1: External alert correlation and Automated investigation and remediation</span></span>
<span data-ttu-id="9ab37-114">Defender voor Eindpunt biedt unieke geautomatiseerde onderzoeks- en herstelmogelijkheden om incidentrespons op schaal te krijgen.</span><span class="sxs-lookup"><span data-stu-id="9ab37-114">Defender for Endpoint offers unique automated investigation and remediation capabilities to drive incident response at scale.</span></span> 

<span data-ttu-id="9ab37-115">Het integreren van de geautomatiseerde onderzoeks- en antwoordmogelijkheden met andere oplossingen, zoals netwerkbeveiligingsproducten of andere eindpuntbeveiligingsproducten, helpt waarschuwingen te adresseren.</span><span class="sxs-lookup"><span data-stu-id="9ab37-115">Integrating the automated investigation and response capability with other solutions such as network security products or other endpoint security products will help to address alerts.</span></span> <span data-ttu-id="9ab37-116">De integratie minimaliseert ook de complexiteit rond netwerk- en apparaatsignaalcorrelatie, wat het onderzoek en de herstelacties voor bedreigingen op apparaten effectief stroomlijnen.</span><span class="sxs-lookup"><span data-stu-id="9ab37-116">The integration also minimizes the complexities surrounding network and device signal correlation, effectively streamlining the investigation and threat remediation actions on devices.</span></span>

<span data-ttu-id="9ab37-117">Defender voor Eindpunt voegt ondersteuning voor dit scenario toe in de volgende formulieren:</span><span class="sxs-lookup"><span data-stu-id="9ab37-117">Defender for Endpoint adds support for this scenario in the following forms:</span></span>

- <span data-ttu-id="9ab37-118">Externe waarschuwingen kunnen worden doorverded naar Defender voor Eindpunt en naast elkaar worden weergegeven met aanvullende waarschuwingen op apparaatbasis van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="9ab37-118">External alerts can be pushed into Defender for Endpoint and presented side by side with additional device-based alerts from Defender for Endpoint.</span></span> <span data-ttu-id="9ab37-119">Deze weergave biedt de volledige context van de waarschuwing, met het echte proces en het volledige verhaal van de aanval.</span><span class="sxs-lookup"><span data-stu-id="9ab37-119">This view provides the full context of the alert - with the real process and the full story of attack.</span></span>

- <span data-ttu-id="9ab37-120">Wanneer een waarschuwing is gegenereerd, wordt het signaal gedeeld over alle beveiligde eindpunten van Defender voor Eindpunt in de onderneming.</span><span class="sxs-lookup"><span data-stu-id="9ab37-120">Once an alert is generated, the signal is shared across all Defender for Endpoint protected endpoints in the enterprise.</span></span> <span data-ttu-id="9ab37-121">Defender voor Eindpunt neemt direct automatisch of door operatoren ondersteund antwoord om de waarschuwing te adresseren.</span><span class="sxs-lookup"><span data-stu-id="9ab37-121">Defender for Endpoint takes immediate automated or operator-assisted response to address the alert.</span></span>

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a><span data-ttu-id="9ab37-122">Scenario 2: Integratie van beveiligingsorkestratie en automatiseringsreactie (SOAR)</span><span class="sxs-lookup"><span data-stu-id="9ab37-122">Scenario 2: Security orchestration and automation response (SOAR) integration</span></span>
<span data-ttu-id="9ab37-123">Met deze oplossingen kunt u playbooks maken en het uitgebreide gegevensmodel en de acties integreren die door Defender for Endpoint-API's worden gebruikt voor georkestreerde antwoorden, zoals query's voor apparaatgegevens, apparaatisolatie activeren, blokkeren/toestaan, waarschuwingen en andere oplossingen oplossen.</span><span class="sxs-lookup"><span data-stu-id="9ab37-123">Orchestration solutions can help build playbooks and integrate the rich data model and actions that Defender for Endpoint APIs expose to orchestrate responses, such as query for device data, trigger device isolation, block/allow, resolve alert and others.</span></span>

## <a name="scenario-3-indicators-matching"></a><span data-ttu-id="9ab37-124">Scenario 3: Indicatoren koppelen</span><span class="sxs-lookup"><span data-stu-id="9ab37-124">Scenario 3: Indicators matching</span></span> 
<span data-ttu-id="9ab37-125">Indicator voor compromissen (IOC's) is een essentiële functie in elke oplossing voor eindpuntbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="9ab37-125">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="9ab37-126">Deze mogelijkheid is beschikbaar in Defender voor Eindpunt en biedt de mogelijkheid om een lijst met indicatoren in te stellen voor preventie, detectie en uitsluiting van entiteiten.</span><span class="sxs-lookup"><span data-stu-id="9ab37-126">This capability is available in Defender for Endpoint and gives the ability to set a list of indicators for prevention, detection, and exclusion of entities.</span></span> <span data-ttu-id="9ab37-127">U kunt de actie definiëren die moet worden ondernomen en de duur voor het toepassen van de actie.</span><span class="sxs-lookup"><span data-stu-id="9ab37-127">One can define the action to be taken as well as the duration for when to apply the action.</span></span>

<span data-ttu-id="9ab37-128">De bovenstaande scenario's dienen als voorbeelden van de extensibility van het platform.</span><span class="sxs-lookup"><span data-stu-id="9ab37-128">The above scenarios serve as examples of the extensibility of the platform.</span></span> <span data-ttu-id="9ab37-129">U bent niet beperkt tot de voorbeelden en we raden u zeker aan gebruik te maken van het open kader om andere scenario's te ontdekken en te verkennen.</span><span class="sxs-lookup"><span data-stu-id="9ab37-129">You are not limited to the examples and we certainly encourage you to leverage the open framework to discover and explore other scenarios.</span></span>

<span data-ttu-id="9ab37-130">Volg de stappen in [Microsoft Defender for Endpoint-partner](get-started-partner-integration.md) worden om uw oplossing te integreren in Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="9ab37-130">Follow the steps in [Become a Microsoft Defender for Endpoint partner](get-started-partner-integration.md) to integrate your solution in Defender for Endpoint.</span></span>

## <a name="related-topic"></a><span data-ttu-id="9ab37-131">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="9ab37-131">Related topic</span></span>
- [<span data-ttu-id="9ab37-132">Overzicht van beheer en API's</span><span class="sxs-lookup"><span data-stu-id="9ab37-132">Overview of management and APIs</span></span>](management-apis.md)
