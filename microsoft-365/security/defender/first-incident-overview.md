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
ms.openlocfilehash: 5ea847e822e094049dd8f0b941f22f3bb4f7eff4
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297174"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="b4460-104">Inleiding tot het reageren op uw eerste incident</span><span class="sxs-lookup"><span data-stu-id="b4460-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b4460-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b4460-105">**Applies to:**</span></span>
- <span data-ttu-id="b4460-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4460-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b4460-107">De strategie voor incidentrespons van een organisatie bepaalt de mogelijkheid om te gaan met steeds meer storende beveiligingsincidenten en cybercriminaliteit.</span><span class="sxs-lookup"><span data-stu-id="b4460-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="b4460-108">Hoewel het belangrijk is om preventieve maatregelen te nemen, kan de mogelijkheid om snel te handelen om gedetecteerde incidenten te beperken, uit te schakelen en te herstellen, schade en zakelijke verliezen minimaliseren.</span><span class="sxs-lookup"><span data-stu-id="b4460-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="b4460-109">In dit overzicht van incidentreacties ziet u hoe u, als onderdeel van een team voor beveiligingsbewerkingen, de meeste van de belangrijkste stappen voor het reageren op incidenten binnen Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b4460-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="b4460-110">Dit doet u als volgt:</span><span class="sxs-lookup"><span data-stu-id="b4460-110">Here are the steps:</span></span>

- <span data-ttu-id="b4460-111">Voorbereiding van uw beveiligingshouding</span><span class="sxs-lookup"><span data-stu-id="b4460-111">Preparation of your security posture</span></span>
- <span data-ttu-id="b4460-112">Voor elk incident:</span><span class="sxs-lookup"><span data-stu-id="b4460-112">For each incident:</span></span>
  - <span data-ttu-id="b4460-113">Stap 1: Triage en analyse</span><span class="sxs-lookup"><span data-stu-id="b4460-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="b4460-114">Stap 2: Herstel (insluiting, uitbanning en herstel)</span><span class="sxs-lookup"><span data-stu-id="b4460-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="b4460-115">Stap 3: beoordeling na incident</span><span class="sxs-lookup"><span data-stu-id="b4460-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="b4460-116">Een beveiligingsincident wordt door het National Institute of Standards and Technology (NIST) gedefinieerd als 'een gebeurtenis die de vertrouwelijkheid, integriteit of beschikbaarheid van een informatiesysteem daadwerkelijk of mogelijk in gevaar brengt; of de informatie die het systeem verwerkt, op slaat of verzendt; of dat een schending of bedreiging vormt van schending van beveiligingsbeleid, beveiligingsprocedures of acceptabel gebruiksbeleid.</span><span class="sxs-lookup"><span data-stu-id="b4460-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="b4460-117">Incidenten in Microsoft 365 Defender zijn de logische uitgangspunten voor analyse en incidentrespons.</span><span class="sxs-lookup"><span data-stu-id="b4460-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="b4460-118">Het analyseren en herstellen van incidenten bestaat meestal uit de meeste taken van een beveiligingsteam.</span><span class="sxs-lookup"><span data-stu-id="b4460-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="b4460-119">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="b4460-119">Next step</span></span>

<span data-ttu-id="b4460-120">[![Uw organisatie en tenant Microsoft 365 voorbereiden](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="b4460-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="b4460-121">Zorg ervoor dat uw organisatie en Microsoft 365 tenant voorbereid zijn [op incidentafhandeling.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="b4460-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b4460-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b4460-122">See also</span></span>

<span data-ttu-id="b4460-123">Incident response guidance for Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="b4460-123">Incident response guidance for Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="b4460-124">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="b4460-124">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b4460-125">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="b4460-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="b4460-126">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="b4460-126">Manage incidents</span></span>](manage-incidents.md)

<span data-ttu-id="b4460-127">Aanvullende voorbeelden van eerste incidentreacties:</span><span class="sxs-lookup"><span data-stu-id="b4460-127">Additional examples of first incident responses:</span></span>

- [<span data-ttu-id="b4460-128">Phishing-e-mail</span><span class="sxs-lookup"><span data-stu-id="b4460-128">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="b4460-129">Identity-base attack</span><span class="sxs-lookup"><span data-stu-id="b4460-129">Identity-base attack</span></span>](first-incident-path-identity.md)

[<span data-ttu-id="b4460-130">Gedetailleerde incidentrespons playbooks</span><span class="sxs-lookup"><span data-stu-id="b4460-130">Detailed incident response playbooks</span></span>](https://docs.microsoft.com/security/compass/incident-response-playbooks)


