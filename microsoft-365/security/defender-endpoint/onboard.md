---
title: Microsoft Defender ATP-mogelijkheden configureren en beheren
ms.reviewer: ''
description: Microsoft Defender ATP-mogelijkheden configureren en beheren, zoals surface reduction voor aanvallen en beveiliging van de volgende generatie
keywords: configure, manage, capabilities, attack surface reduction, next-generation protection, security controls, endpoint detection and response, auto investigation and remediation, security controls, controls
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
ms.openlocfilehash: a0872de9774773c136bca6febd621daba5b2d7d3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186375"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="37ad0-104">Microsoft Defender voor endpoint-mogelijkheden configureren en beheren</span><span class="sxs-lookup"><span data-stu-id="37ad0-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37ad0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="37ad0-105">**Applies to:**</span></span>
- [<span data-ttu-id="37ad0-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="37ad0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="37ad0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37ad0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="37ad0-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="37ad0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="37ad0-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="37ad0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="37ad0-110">Configureer en beheer alle Mogelijkheden van Defender voor Eindpunt om de beste beveiliging voor uw organisatie te krijgen.</span><span class="sxs-lookup"><span data-stu-id="37ad0-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="37ad0-111">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="37ad0-111">In this section</span></span> 
<span data-ttu-id="37ad0-112">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="37ad0-112">Topic</span></span> | <span data-ttu-id="37ad0-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="37ad0-113">Description</span></span> 
:---|:---
[<span data-ttu-id="37ad0-114">Mogelijkheden voor het verlagen van de Surface-aanval configureren</span><span class="sxs-lookup"><span data-stu-id="37ad0-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="37ad0-115">Door ervoor te zorgen dat configuratie-instellingen correct zijn ingesteld en technieken voor risicobeperking worden toegepast, zijn deze mogelijkheden bestand tegen aanvallen en misbruik.</span><span class="sxs-lookup"><span data-stu-id="37ad0-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="37ad0-116">Beveiliging van de volgende generatie configureren</span><span class="sxs-lookup"><span data-stu-id="37ad0-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="37ad0-117">Configureer de beveiliging van de volgende generatie om alle soorten nieuwe bedreigingen op te vangen.</span><span class="sxs-lookup"><span data-stu-id="37ad0-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="37ad0-118">Microsoft Threat Experts-mogelijkheden configureren</span><span class="sxs-lookup"><span data-stu-id="37ad0-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="37ad0-119">Configureer en beheer hoe u cyberbeveiligingsintelligentie wilt krijgen van Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="37ad0-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="37ad0-120">Microsoft Threat Protection-integratie configureren</span><span class="sxs-lookup"><span data-stu-id="37ad0-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="37ad0-121">Configureer andere oplossingen die zijn geïntegreerd met Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="37ad0-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="37ad0-122">Ondersteuning voor beheer en API</span><span class="sxs-lookup"><span data-stu-id="37ad0-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="37ad0-123">Haal waarschuwingen naar uw SIEM of gebruik API's om aangepaste waarschuwingen te maken.</span><span class="sxs-lookup"><span data-stu-id="37ad0-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="37ad0-124">Power BI-rapporten maken en bouwen.</span><span class="sxs-lookup"><span data-stu-id="37ad0-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="37ad0-125">Instellingen van het Microsoft Defender-beveiligingscentrum configureren</span><span class="sxs-lookup"><span data-stu-id="37ad0-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="37ad0-126">Configureer portalgerelateerde instellingen, zoals algemene instellingen, geavanceerde functies, en schakel de preview-ervaring en andere functies in.</span><span class="sxs-lookup"><span data-stu-id="37ad0-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



