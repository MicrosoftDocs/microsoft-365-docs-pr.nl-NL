---
title: Microsoft Defender ATP-functies configureren en beheren
ms.reviewer: ''
description: Microsoft Defender ATP-functies zoals aanvals vermindering, volgende generatie beveiliging en beveiligingsfuncties configureren en beheren
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
ms.openlocfilehash: 64c6e5f7eefad50aa59301de3fd46cae60d6876f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429429"
---
# <a name="configure-and-manage-microsoft-defender-atp-capabilities"></a><span data-ttu-id="33c86-104">Microsoft Defender ATP-functies configureren en beheren</span><span class="sxs-lookup"><span data-stu-id="33c86-104">Configure and manage Microsoft Defender ATP capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="33c86-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="33c86-105">**Applies to:**</span></span>

- [<span data-ttu-id="33c86-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="33c86-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="33c86-107">U kunt alle functies van Microsoft Defender ATP configureren en beheren om de beste beveiligings bescherming voor uw organisatie te krijgen.</span><span class="sxs-lookup"><span data-stu-id="33c86-107">Configure and manage all the Microsoft Defender ATP capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="33c86-108">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="33c86-108">In this section</span></span> 
<span data-ttu-id="33c86-109">Rond</span><span class="sxs-lookup"><span data-stu-id="33c86-109">Topic</span></span> | <span data-ttu-id="33c86-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="33c86-110">Description</span></span> 
:---|:---
[<span data-ttu-id="33c86-111">Mogelijkheden voor oppervlakte vermindering van aanval configureren</span><span class="sxs-lookup"><span data-stu-id="33c86-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="33c86-112">Als u zeker weet dat de configuratie-instellingen op de juiste manier zijn ingesteld en deel te maken met de beperkings technieken, worden de volgende mogelijkheden weergegeven voor aanvallen en exploitatie.</span><span class="sxs-lookup"><span data-stu-id="33c86-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitations.</span></span> 
[<span data-ttu-id="33c86-113">Volgende generatie beveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="33c86-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="33c86-114">Configureer de volgende generatie beveiliging om alle soorten opkomende bedreigingen te vangen.</span><span class="sxs-lookup"><span data-stu-id="33c86-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="33c86-115">De mogelijkheden van Microsoft Threat experts configureren</span><span class="sxs-lookup"><span data-stu-id="33c86-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="33c86-116">Configureer en beheer hoe u Cyber Security bedreigings informatie van Microsoft Threat experts wilt verzamelen.</span><span class="sxs-lookup"><span data-stu-id="33c86-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="33c86-117">Integratie van Microsoft Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="33c86-117">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="33c86-118">Andere oplossingen configureren die worden geïntegreerd met Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="33c86-118">Configure other solutions that integrate with Microsoft Defender ATP.</span></span>
[<span data-ttu-id="33c86-119">Ondersteuning voor het beheer en de API</span><span class="sxs-lookup"><span data-stu-id="33c86-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="33c86-120">U ontvangt waarschuwingen aan uw SIEM of gebruik Api's om aangepaste waarschuwingen te maken.</span><span class="sxs-lookup"><span data-stu-id="33c86-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="33c86-121">Power BI-rapporten maken en maken.</span><span class="sxs-lookup"><span data-stu-id="33c86-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="33c86-122">Instellingen voor Microsoft Defender-Beveiligingscentrum configureren</span><span class="sxs-lookup"><span data-stu-id="33c86-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="33c86-123">Verwante instellingen voor de portal configureren, zoals algemene instellingen, geavanceerde functies, de voorbeeld ervaring en andere functies inschakelen.</span><span class="sxs-lookup"><span data-stu-id="33c86-123">Configure portal related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



