---
title: De mogelijkheden van Microsoft Defender voor eindpunten configureren en beheren
ms.reviewer: ''
description: Microsoft Defender configureren en beheren voor eindpunt mogelijkheden zoals aanvals vermindering en de volgende generatie beveiliging
keywords: configureren, beheren, functies, oppervlakte van aanval, volgende generatie beveiliging, beveiligings besturing, detectie van het eindpunt en antwoord, automatisch onderzoek en herstel, beveiliging besturingselement
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: b202b30e218448794eac7588078ff3ac9cfe9ee3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844810"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="55a7c-104">De mogelijkheden van Microsoft Defender voor eindpunten configureren en beheren</span><span class="sxs-lookup"><span data-stu-id="55a7c-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="55a7c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="55a7c-105">**Applies to:**</span></span>

- [<span data-ttu-id="55a7c-106">Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="55a7c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="55a7c-107">U kunt alle functies van Microsoft Defender voor eindpunten configureren en beheren om de beste beveiligings beveiliging voor uw organisatie te krijgen.</span><span class="sxs-lookup"><span data-stu-id="55a7c-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="55a7c-108">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="55a7c-108">In this section</span></span> 
<span data-ttu-id="55a7c-109">Rond</span><span class="sxs-lookup"><span data-stu-id="55a7c-109">Topic</span></span> | <span data-ttu-id="55a7c-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="55a7c-110">Description</span></span> 
:---|:---
[<span data-ttu-id="55a7c-111">Mogelijkheden voor oppervlakte vermindering van aanval configureren</span><span class="sxs-lookup"><span data-stu-id="55a7c-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="55a7c-112">Als u zeker weet dat de configuratie-instellingen op de juiste manier zijn ingesteld en van toepassing zijn, worden deze mogelijkheden weergegeven voor aanvallen en exploitatie.</span><span class="sxs-lookup"><span data-stu-id="55a7c-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="55a7c-113">Volgende generatie beveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="55a7c-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="55a7c-114">Configureer de volgende generatie beveiliging om alle soorten opkomende bedreigingen te vangen.</span><span class="sxs-lookup"><span data-stu-id="55a7c-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="55a7c-115">De mogelijkheden van Microsoft Threat experts configureren</span><span class="sxs-lookup"><span data-stu-id="55a7c-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="55a7c-116">Configureer en beheer hoe u Cyber Security bedreigings informatie van Microsoft Threat experts wilt verzamelen.</span><span class="sxs-lookup"><span data-stu-id="55a7c-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="55a7c-117">Integratie van Microsoft 365 Defender configureren</span><span class="sxs-lookup"><span data-stu-id="55a7c-117">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="55a7c-118">Andere oplossingen configureren die worden geïntegreerd met Microsoft Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="55a7c-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="55a7c-119">Ondersteuning voor het beheer en de API</span><span class="sxs-lookup"><span data-stu-id="55a7c-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="55a7c-120">U ontvangt waarschuwingen aan uw SIEM of gebruik Api's om aangepaste waarschuwingen te maken.</span><span class="sxs-lookup"><span data-stu-id="55a7c-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="55a7c-121">Power BI-rapporten maken en maken.</span><span class="sxs-lookup"><span data-stu-id="55a7c-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="55a7c-122">Instellingen voor Microsoft Defender-Beveiligingscentrum configureren</span><span class="sxs-lookup"><span data-stu-id="55a7c-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="55a7c-123">Instellingen voor de portal configureren, zoals algemene instellingen, geavanceerde functies, de voorbeeld ervaring en andere functies inschakelen.</span><span class="sxs-lookup"><span data-stu-id="55a7c-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



