---
title: Microsoft Defender voor endpoint-mogelijkheden configureren en beheren
ms.reviewer: ''
description: Microsoft Defender configureren en beheren voor endpoint-mogelijkheden, zoals surface reduction voor aanvallen en beveiliging van de volgende generatie
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3ad23e030048506784edd8f1988fa33263a085ae
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861333"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="534f1-104">Microsoft Defender voor endpoint-mogelijkheden configureren en beheren</span><span class="sxs-lookup"><span data-stu-id="534f1-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="534f1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="534f1-105">**Applies to:**</span></span>

- [<span data-ttu-id="534f1-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="534f1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="534f1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="534f1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="534f1-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="534f1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="534f1-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="534f1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="534f1-110">Meer informatie over het configureren en beheren van De functies van Defender voor eindpunten, om de beste beveiliging voor uw organisatie te krijgen.</span><span class="sxs-lookup"><span data-stu-id="534f1-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="534f1-111">Zie Onboard devices to the Microsoft Defender for Endpoint service (Onboard [devices to the Microsoft Defender for Endpoint service)](./onboard-configure.md)voor praktisch advies over het verbinden van nieuwe apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="534f1-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="534f1-112">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="534f1-112">In this section</span></span>

<span data-ttu-id="534f1-113">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="534f1-113">Topic</span></span> | <span data-ttu-id="534f1-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="534f1-114">Description</span></span>
:---|:---
[<span data-ttu-id="534f1-115">Instellingen van het Microsoft Defender-beveiligingscentrum configureren</span><span class="sxs-lookup"><span data-stu-id="534f1-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="534f1-116">Configureer portalgerelateerde instellingen, zoals algemene instellingen, geavanceerde functies of schakel de preview-ervaring in.</span><span class="sxs-lookup"><span data-stu-id="534f1-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="534f1-117">Mogelijkheden voor het verlagen van de Surface-aanval configureren</span><span class="sxs-lookup"><span data-stu-id="534f1-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="534f1-118">Configureer de mogelijkheden voor het beperken van het oppervlak van de aanval om ervoor te zorgen dat instellingen correct worden toegepast en gebruik te maken van mitigatietechnieken.</span><span class="sxs-lookup"><span data-stu-id="534f1-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="534f1-119">Beveiliging van de volgende generatie configureren</span><span class="sxs-lookup"><span data-stu-id="534f1-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="534f1-120">Configureer de beveiliging van de volgende generatie om alle soorten nieuwe bedreigingen op te vangen.</span><span class="sxs-lookup"><span data-stu-id="534f1-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="534f1-121">Microsoft Threat Experts-mogelijkheden configureren</span><span class="sxs-lookup"><span data-stu-id="534f1-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="534f1-122">Configureer en beheer cyberbeveiligingsintelligentie van Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="534f1-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="534f1-123">Microsoft Threat Protection-integratie configureren</span><span class="sxs-lookup"><span data-stu-id="534f1-123">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="534f1-124">Configureer andere oplossingen die zijn geïntegreerd met Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="534f1-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="534f1-125">Ondersteuning voor beheer en API</span><span class="sxs-lookup"><span data-stu-id="534f1-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="534f1-126">Haal waarschuwingen naar uw SIEM (Security Information and Event Management) of gebruik API's om aangepaste waarschuwingen te maken.</span><span class="sxs-lookup"><span data-stu-id="534f1-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="534f1-127">Power BI-rapporten maken en bouwen.</span><span class="sxs-lookup"><span data-stu-id="534f1-127">Create and build Power BI reports.</span></span>
