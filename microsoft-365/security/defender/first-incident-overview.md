---
title: Inleiding tot het reageren op uw eerste incident
description: De basisbeginselen van het reageren op uw eerste incident in Microsoft 365 Defender.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365, incident response, cyber-attack
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
ms.openlocfilehash: f66c9821e5db00cc3da5718f52b8aaaeff5a431e
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114627"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="2d59b-104">Inleiding tot het reageren op uw eerste incident</span><span class="sxs-lookup"><span data-stu-id="2d59b-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2d59b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2d59b-105">**Applies to:**</span></span>
- <span data-ttu-id="2d59b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d59b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2d59b-107">De strategie voor incidentrespons van een organisatie bepaalt de mogelijkheid om te gaan met steeds meer storende beveiligingsincidenten en cybercriminaliteit.</span><span class="sxs-lookup"><span data-stu-id="2d59b-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="2d59b-108">Hoewel het belangrijk is om preventieve maatregelen te nemen, kan de mogelijkheid om snel te handelen om gedetecteerde incidenten te beperken, uit te schakelen en te herstellen, schade en zakelijke verliezen minimaliseren.</span><span class="sxs-lookup"><span data-stu-id="2d59b-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="2d59b-109">In dit overzicht van incidentreacties ziet u hoe u, als onderdeel van een team voor beveiligingsbewerkingen, de meeste van de belangrijkste stappen voor het reageren op incidenten binnen Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2d59b-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="2d59b-110">Dit doet u als volgt:</span><span class="sxs-lookup"><span data-stu-id="2d59b-110">Here are the steps:</span></span>

- <span data-ttu-id="2d59b-111">Voorbereiding van uw beveiligingshouding</span><span class="sxs-lookup"><span data-stu-id="2d59b-111">Preparation of your security posture</span></span>
- <span data-ttu-id="2d59b-112">Voor elk incident:</span><span class="sxs-lookup"><span data-stu-id="2d59b-112">For each incident:</span></span>
  - <span data-ttu-id="2d59b-113">Stap 1: Triage en analyse</span><span class="sxs-lookup"><span data-stu-id="2d59b-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="2d59b-114">Stap 2: Herstel (insluiting, uitbanning en herstel)</span><span class="sxs-lookup"><span data-stu-id="2d59b-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="2d59b-115">Stap 3: beoordeling na incident</span><span class="sxs-lookup"><span data-stu-id="2d59b-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="2d59b-116">Een beveiligingsincident wordt door het National Institute of Standards and Technology (NIST) gedefinieerd als 'een gebeurtenis die de vertrouwelijkheid, integriteit of beschikbaarheid van een informatiesysteem daadwerkelijk of mogelijk in gevaar brengt; of de informatie die het systeem verwerkt, op slaat of verzendt; of dat een schending of bedreiging vormt van schending van beveiligingsbeleid, beveiligingsprocedures of acceptabel gebruiksbeleid.</span><span class="sxs-lookup"><span data-stu-id="2d59b-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="2d59b-117">Incidenten in Microsoft 365 Defender zijn de logische uitgangspunten voor analyse en incidentrespons.</span><span class="sxs-lookup"><span data-stu-id="2d59b-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="2d59b-118">Het analyseren en herstellen van incidenten bestaat meestal uit de meeste taken van een beveiligingsteam.</span><span class="sxs-lookup"><span data-stu-id="2d59b-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="2d59b-119">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="2d59b-119">Next step</span></span>

<span data-ttu-id="2d59b-120">[![Uw organisatie en tenant Microsoft 365 voorbereiden](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="2d59b-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="2d59b-121">Zorg ervoor dat uw organisatie en Microsoft 365 tenant voorbereid zijn [op incidentafhandeling.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="2d59b-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2d59b-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2d59b-122">See also</span></span>

- [<span data-ttu-id="2d59b-123">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="2d59b-123">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="2d59b-124">Incidenten analyseren</span><span class="sxs-lookup"><span data-stu-id="2d59b-124">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="2d59b-125">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="2d59b-125">Manage incidents</span></span>](manage-incidents.md)
