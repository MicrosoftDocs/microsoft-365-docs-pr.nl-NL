---
title: Stap 3. Een beoordeling na het incident uitvoeren van uw eerste incident
description: Een beoordeling uitvoeren van uw eerste incident in Microsoft 365 Defender.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1ceea1dbdb3f9d149f4e5a0bd892eda2bb9128aa
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114639"
---
# <a name="step-3-perform-a-post-incident-review-of-your-first-incident"></a><span data-ttu-id="e1fbb-105">Stap 3.</span><span class="sxs-lookup"><span data-stu-id="e1fbb-105">Step 3.</span></span> <span data-ttu-id="e1fbb-106">Een beoordeling na het incident uitvoeren van uw eerste incident</span><span class="sxs-lookup"><span data-stu-id="e1fbb-106">Perform a post-incident review of your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e1fbb-107">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e1fbb-107">**Applies to:**</span></span>
- <span data-ttu-id="e1fbb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1fbb-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="e1fbb-109">National Institute of Standards and Technology (NIST) raadt aan dat wanneer alle stappen zijn ondernomen om de aanval te herstellen, organisaties het incident moeten bekijken om hier van te leren en de beveiligingshouding of -processen te leren en verbeteren.</span><span class="sxs-lookup"><span data-stu-id="e1fbb-109">National Institute of Standards and Technology (NIST) recommends that once all steps have been taken to recover from the attack, organizations must review the incident to learn from it and learn and improve security posture or processes.</span></span> <span data-ttu-id="e1fbb-110">Het beoordelen van de verschillende aspecten van incidentafhandeling wordt belangrijk bij de voorbereiding op het volgende incident.</span><span class="sxs-lookup"><span data-stu-id="e1fbb-110">Assessing the different aspects of incident-handling becomes important in preparing for the next incident.</span></span>

<span data-ttu-id="e1fbb-111">Microsoft 365 Defender kan u helpen bij het uitvoeren van post-incidentactiviteiten door een organisatie waarschuwingen te geven die zijn afgestemd op [MITRE ATT&CK Framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="e1fbb-111">Microsoft 365 Defender can assist in performing post-incident activities by providing an organization with alerts that align with [MITRE ATT&CK Framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="e1fbb-112">Alle Microsoft Defender-oplossingen labelen aanvallen in overeenstemming met een ATT-&CK-tactiek of -techniek.</span><span class="sxs-lookup"><span data-stu-id="e1fbb-112">All Microsoft Defender solutions label attacks in accordance with an ATT&CK tactic or technique.</span></span> 

<span data-ttu-id="e1fbb-113">Door waarschuwingen toe tewijsen aan dit industriekader, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="e1fbb-113">By mapping alerts to this industry framework, you can:</span></span>

- <span data-ttu-id="e1fbb-114">Een analyse uitvoeren van hiaten in de beveiligingsdekking.</span><span class="sxs-lookup"><span data-stu-id="e1fbb-114">Conduct an analysis of gaps in security coverage.</span></span>
- <span data-ttu-id="e1fbb-115">Bepaal de naam van de tegenstander en de naamsvermelding van de campagne.</span><span class="sxs-lookup"><span data-stu-id="e1fbb-115">Determine adversary and campaign attribution.</span></span>
- <span data-ttu-id="e1fbb-116">Trendanalyse uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e1fbb-116">Perform trend analysis.</span></span>
- <span data-ttu-id="e1fbb-117">Identificeer vaardigheidshiaten in de bewustmaking van de aanvalsmethode.</span><span class="sxs-lookup"><span data-stu-id="e1fbb-117">Identify skill gaps in attack method awareness.</span></span>
- <span data-ttu-id="e1fbb-118">Maak een Power Automate Playbook voor snellere herstel.</span><span class="sxs-lookup"><span data-stu-id="e1fbb-118">Create a Power Automate Playbook for faster remediation.</span></span> 

<span data-ttu-id="e1fbb-119">Activiteiten na het incident controleren kunnen ook resulteren in het afstemmen van de beveiligingsconfiguratie en de processen van het beveiligingsteam, waardoor de reactiemogelijkheden van uw organisatie worden vergroot.</span><span class="sxs-lookup"><span data-stu-id="e1fbb-119">Post-incident review activity can also result in fine-tuning your security configuration and security team's processes, enhancing your organization’s response capabilities.</span></span>

## <a name="next-step"></a><span data-ttu-id="e1fbb-120">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="e1fbb-120">Next step</span></span>

<span data-ttu-id="e1fbb-121">Bekijk deze aanvullende onderzoekspaden:</span><span class="sxs-lookup"><span data-stu-id="e1fbb-121">See these additional investigation paths:</span></span>

- [<span data-ttu-id="e1fbb-122">Phishing-e-mail</span><span class="sxs-lookup"><span data-stu-id="e1fbb-122">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="e1fbb-123">Aanval op basis van identiteit</span><span class="sxs-lookup"><span data-stu-id="e1fbb-123">Identity-based attack</span></span>](first-incident-path-identity.md)


## <a name="see-also"></a><span data-ttu-id="e1fbb-124">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e1fbb-124">See also</span></span>

- [<span data-ttu-id="e1fbb-125">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="e1fbb-125">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e1fbb-126">Incidenten analyseren</span><span class="sxs-lookup"><span data-stu-id="e1fbb-126">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="e1fbb-127">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="e1fbb-127">Manage incidents</span></span>](manage-incidents.md)
