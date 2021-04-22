---
title: Uw testresultaten van Microsoft 365 Defender samenvatten
description: Sluit uw testproject microsoft 365 Defender af door uw scorecard te voltooien, uw rapport te analyseren en te bepalen hoe u verder wilt gaan.
keywords: Microsoft 365 Defender pilot, beslissen wat te doen na pilot Microsoft 365 Defender project, wat te doen na de evaluatie van Microsoft 365 Defender in productie, overgang van Microsoft 365 Defender pilot naar implementatie, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerde jacht
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 64cdb37b64780a651b2689e68e21c5a385df5ba9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932867"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="2dc8c-104">Uw Microsoft 365 Defender-pilot sluiten en samenvatten</span><span class="sxs-lookup"><span data-stu-id="2dc8c-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2dc8c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2dc8c-105">**Applies to:**</span></span>
- <span data-ttu-id="2dc8c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2dc8c-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="2dc8c-107">[![Planning](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="2dc8c-107">[![Planning](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span></span><br/>[<span data-ttu-id="2dc8c-108">Planning</span><span class="sxs-lookup"><span data-stu-id="2dc8c-108">Planning</span></span>](m365d-pilot-plan.md) |<span data-ttu-id="2dc8c-109">[![Voorbereiden](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="2dc8c-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="2dc8c-110">Voorbereiding</span><span class="sxs-lookup"><span data-stu-id="2dc8c-110">Preparation</span></span>](prepare-m365d-eval.md) | <span data-ttu-id="2dc8c-111">[![Een aanval simuleren](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="2dc8c-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="2dc8c-112">Een aanval simuleren</span><span class="sxs-lookup"><span data-stu-id="2dc8c-112">Simulate attack</span></span>](m365d-pilot-simulate.md) | ![Sluiten en samenvatten](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="2dc8c-114">Sluiten en samenvatten</span><span class="sxs-lookup"><span data-stu-id="2dc8c-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="2dc8c-115">*U bent er!*</span><span class="sxs-lookup"><span data-stu-id="2dc8c-115">*You are here!*</span></span>|


<span data-ttu-id="2dc8c-116">U bent momenteel bezig met het sluiten en samenvatten van de fase.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="2dc8c-117">U hebt zojuist een geavanceerde geheugen-alleen-aanvalssimulatie uitgevoerd die code op afstand heeft uitgevoerd op een domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="2dc8c-118">U hebt gezien hoe Microsoft Defender voor Eindpunt en Microsoft Defender voor identiteit waarschuwingen detecteren en maken voor verborgen schadelijke activiteiten.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="2dc8c-119">U hebt ook gezien hoe waarschuwingen uit verschillende bronnen samen met andere contextuele informatie worden bezorgd in één incident in de microsoft 365-beveiligingscentrumportal.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="2dc8c-120">Als u dergelijke integratie ondervindt, kunnen SOC-analisten de benodigde actie onderzoeken en ondernemen.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="2dc8c-121">U hebt ook een geavanceerde query gemaakt om inkomende e-mailberichten te identificeren waarin de gebruiker de bijlage heeft geopend of opgeslagen en detectie heeft gemaakt op basis van die query.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="2dc8c-122">U hebt het einde van het proces bereikt nadat alle tests zijn afgerond.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="2dc8c-123">De uiteindelijke uitvoer moet zijn:</span><span class="sxs-lookup"><span data-stu-id="2dc8c-123">The final output should be:</span></span>

- <span data-ttu-id="2dc8c-124">Een voltooide scorecard</span><span class="sxs-lookup"><span data-stu-id="2dc8c-124">A completed scorecard</span></span>
- <span data-ttu-id="2dc8c-125">Een gedetailleerd rapport van de resultaten van de pilot</span><span class="sxs-lookup"><span data-stu-id="2dc8c-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="2dc8c-126">Een beslissing over hoe u verder kunt gaan</span><span class="sxs-lookup"><span data-stu-id="2dc8c-126">A decision on how to move forward</span></span>

<span data-ttu-id="2dc8c-127">Presenteert de rapporten van uw uiteindelijke uitvoer aan interne [](./prepare-m365d-eval.md) belanghebbenden (die u hebt geïdentificeerd tijdens de voorbereidingsfase) en Microsoft-contactpersonen.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](./prepare-m365d-eval.md) phase) and Microsoft contacts.</span></span> <span data-ttu-id="2dc8c-128">Een dergelijke inspanning zorgt ervoor dat feedback kan worden gebruikt om producten en documentatie te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="2dc8c-129">We hopen dat u genoten hebt van deze simulatie.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="2dc8c-130">Begin met het implementeren van wat u op grotere schaal in uw organisatie hebt geleerd om het beste uit de geïntegreerde beveiligingsoplossing te halen.</span><span class="sxs-lookup"><span data-stu-id="2dc8c-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="2dc8c-131">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="2dc8c-131">Next step</span></span>
<span data-ttu-id="2dc8c-132">Meer informatie over de Microsoft 365 Defender-pilaren via de volgende interactieve handleidingen:</span><span class="sxs-lookup"><span data-stu-id="2dc8c-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="2dc8c-133">Uw organisatie beveiligen met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2dc8c-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="2dc8c-134">Verdachte activiteiten en mogelijke aanvallen detecteren met Microsoft Defender voor identiteit</span><span class="sxs-lookup"><span data-stu-id="2dc8c-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="2dc8c-135">Bedreigingen detecteren en waarschuwingen beheren met Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2dc8c-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="2dc8c-136">Bedreigingen onderzoeken en corrigeren met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2dc8c-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)