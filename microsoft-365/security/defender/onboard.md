---
title: Microsoft Defender voor endpoint-mogelijkheden configureren en beheren
ms.reviewer: ''
description: Microsoft Defender configureren en beheren voor endpoint-mogelijkheden, zoals surface reduction voor aanvallen en beveiliging van de volgende generatie
keywords: configure, manage, capabilities, attack surface reduction, next generation protection, security controls, endpoint detection and response, auto investigation and remediation, security controls, controls
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 95c462829b43ae41c1fe664b2313a716078baea7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058561"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="b8294-104">Microsoft Defender voor endpoint-mogelijkheden configureren en beheren</span><span class="sxs-lookup"><span data-stu-id="b8294-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b8294-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b8294-105">**Applies to:**</span></span>

- [<span data-ttu-id="b8294-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="b8294-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="b8294-107">Configureer en beheer alle mogelijkheden van Microsoft Defender voor eindpunten om de beste beveiliging voor uw organisatie te krijgen.</span><span class="sxs-lookup"><span data-stu-id="b8294-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="b8294-108">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="b8294-108">In this section</span></span> 
<span data-ttu-id="b8294-109">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="b8294-109">Topic</span></span> | <span data-ttu-id="b8294-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b8294-110">Description</span></span> 
:---|:---
[<span data-ttu-id="b8294-111">Mogelijkheden voor het verlagen van de Surface-aanval configureren</span><span class="sxs-lookup"><span data-stu-id="b8294-111">Configure attack surface reduction capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="b8294-112">Door ervoor te zorgen dat configuratie-instellingen correct zijn ingesteld en technieken voor risicobeperking worden toegepast, zijn deze mogelijkheden bestand tegen aanvallen en misbruik.</span><span class="sxs-lookup"><span data-stu-id="b8294-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="b8294-113">Beveiliging van de volgende generatie configureren</span><span class="sxs-lookup"><span data-stu-id="b8294-113">Configure next generation protection</span></span>](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="b8294-114">Configureer de volgende generatiebeveiliging om alle soorten nieuwe bedreigingen te vangen.</span><span class="sxs-lookup"><span data-stu-id="b8294-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="b8294-115">Microsoft Threat Experts-mogelijkheden configureren</span><span class="sxs-lookup"><span data-stu-id="b8294-115">Configure Microsoft Threat Experts capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="b8294-116">Configureer en beheer hoe u cyberbeveiligingsintelligentie wilt krijgen van Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="b8294-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="b8294-117">Microsoft 365 Defender-integratie configureren</span><span class="sxs-lookup"><span data-stu-id="b8294-117">Configure Microsoft 365 Defender integration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="b8294-118">Configureer andere oplossingen die zijn geïntegreerd met Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b8294-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="b8294-119">Ondersteuning voor beheer en API</span><span class="sxs-lookup"><span data-stu-id="b8294-119">Management and API support</span></span>](/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="b8294-120">Haal waarschuwingen naar uw SIEM of gebruik API's om aangepaste waarschuwingen te maken.</span><span class="sxs-lookup"><span data-stu-id="b8294-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="b8294-121">Power BI-rapporten maken en bouwen.</span><span class="sxs-lookup"><span data-stu-id="b8294-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="b8294-122">Instellingen van het Microsoft Defender-beveiligingscentrum configureren</span><span class="sxs-lookup"><span data-stu-id="b8294-122">Configure Microsoft Defender Security Center settings</span></span>](/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="b8294-123">Configureer portalgerelateerde instellingen, zoals algemene instellingen, geavanceerde functies, en schakel de preview-ervaring en andere functies in.</span><span class="sxs-lookup"><span data-stu-id="b8294-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>