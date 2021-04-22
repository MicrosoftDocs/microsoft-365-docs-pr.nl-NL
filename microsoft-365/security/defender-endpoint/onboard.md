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
ms.openlocfilehash: 25b70f91824db2a6d05db5d3981dd50f4f2b477a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934739"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="e7459-104">Microsoft Defender voor endpoint-mogelijkheden configureren en beheren</span><span class="sxs-lookup"><span data-stu-id="e7459-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e7459-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e7459-105">**Applies to:**</span></span>

- [<span data-ttu-id="e7459-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e7459-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e7459-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7459-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e7459-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e7459-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e7459-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e7459-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e7459-110">Meer informatie over het configureren en beheren van De functies van Defender voor eindpunten, om de beste beveiliging voor uw organisatie te krijgen.</span><span class="sxs-lookup"><span data-stu-id="e7459-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="e7459-111">Zie Onboard devices to the Microsoft Defender for Endpoint service (Onboard [devices to the Microsoft Defender for Endpoint service)](./onboard-configure.md)voor praktisch advies over het verbinden van nieuwe apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e7459-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e7459-112">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="e7459-112">In this section</span></span>

<span data-ttu-id="e7459-113">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="e7459-113">Topic</span></span> | <span data-ttu-id="e7459-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e7459-114">Description</span></span>
:---|:---
[<span data-ttu-id="e7459-115">Instellingen van het Microsoft Defender-beveiligingscentrum configureren</span><span class="sxs-lookup"><span data-stu-id="e7459-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="e7459-116">Configureer portalgerelateerde instellingen, zoals algemene instellingen, geavanceerde functies of schakel de preview-ervaring in.</span><span class="sxs-lookup"><span data-stu-id="e7459-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="e7459-117">Mogelijkheden voor het verlagen van de Surface-aanval configureren</span><span class="sxs-lookup"><span data-stu-id="e7459-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="e7459-118">Configureer de mogelijkheden voor het beperken van het oppervlak van de aanval om ervoor te zorgen dat instellingen correct worden toegepast en gebruik te maken van mitigatietechnieken.</span><span class="sxs-lookup"><span data-stu-id="e7459-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="e7459-119">Beveiliging van de volgende generatie configureren</span><span class="sxs-lookup"><span data-stu-id="e7459-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="e7459-120">Configureer de beveiliging van de volgende generatie om alle soorten nieuwe bedreigingen op te vangen.</span><span class="sxs-lookup"><span data-stu-id="e7459-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="e7459-121">Microsoft Threat Experts-mogelijkheden configureren</span><span class="sxs-lookup"><span data-stu-id="e7459-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="e7459-122">Configureer en beheer cyberbeveiligingsintelligentie van Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="e7459-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="e7459-123">Microsoft 365 Defender-integratie configureren</span><span class="sxs-lookup"><span data-stu-id="e7459-123">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="e7459-124">Configureer andere oplossingen die zijn geïntegreerd met Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="e7459-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="e7459-125">Ondersteuning voor beheer en API</span><span class="sxs-lookup"><span data-stu-id="e7459-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="e7459-126">Haal waarschuwingen naar uw SIEM (Security Information and Event Management) of gebruik API's om aangepaste waarschuwingen te maken.</span><span class="sxs-lookup"><span data-stu-id="e7459-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="e7459-127">Power BI-rapporten maken en bouwen.</span><span class="sxs-lookup"><span data-stu-id="e7459-127">Create and build Power BI reports.</span></span>
