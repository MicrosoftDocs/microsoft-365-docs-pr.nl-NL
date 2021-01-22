---
title: Uw testresultaten van het Microsoft 365 Defender-project samenvatten
description: Sluit uw pilot met Microsoft 365 Defender af door uw scorecard te voltooien, de resultaten van uw rapport te analyseren en te bepalen hoe u verder wilt gaan.
keywords: Microsoft Threat Protection-pilot, bepaal wat er moet gebeuren na de pilot van het Microsoft Threat Protection-project, wat er moet gebeuren na de evaluatie van Microsoft Threat Protection in productie, overstappen van Microsoft Threat Protection-pilot naar implementatie, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c8608568301f11a20c940a5ff9f1c205ce6e48f1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930160"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="81f99-104">Uw Microsoft 365 Defender-testfase sluiten en samenvatten</span><span class="sxs-lookup"><span data-stu-id="81f99-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="81f99-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="81f99-105">**Applies to:**</span></span>
- <span data-ttu-id="81f99-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81f99-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="81f99-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="81f99-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="81f99-108">Planning</span><span class="sxs-lookup"><span data-stu-id="81f99-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="81f99-109">[![Voorbereiden](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="81f99-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="81f99-110">Voorbereiding</span><span class="sxs-lookup"><span data-stu-id="81f99-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="81f99-111">[![Een aanval simuleren](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="81f99-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="81f99-112">Een aanval simuleren</span><span class="sxs-lookup"><span data-stu-id="81f99-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Sluiten en samenvatten](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="81f99-114">Sluiten en samenvatten</span><span class="sxs-lookup"><span data-stu-id="81f99-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="81f99-115">*U bent hier!*</span><span class="sxs-lookup"><span data-stu-id="81f99-115">*You are here!*</span></span>|


<span data-ttu-id="81f99-116">U bent nu bezig met het afsluiten en samenvatten van de fase.</span><span class="sxs-lookup"><span data-stu-id="81f99-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="81f99-117">U hebt zojuist een geavanceerde, alleen geheugen-aanval-aanval uitgevoerd die code op afstand op een domeincontroller heeft uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="81f99-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="81f99-118">U hebt gezien hoe Microsoft Defender for Endpoint en Microsoft Defender for Identity waarschuwingen detecteren en maken voor schadelijke activiteiten.</span><span class="sxs-lookup"><span data-stu-id="81f99-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="81f99-119">U hebt ook gezien hoe waarschuwingen van verschillende bronnen samen met andere contextuele informatie worden bezorgd bij één incident in de portal van het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="81f99-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="81f99-120">Als deze integratie wordt ervaren, kunnen SOC-analisten onderzoek doen en de benodigde actie ondernemen.</span><span class="sxs-lookup"><span data-stu-id="81f99-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="81f99-121">U hebt ook een geavanceerde zoekquery gemaakt die inkomende e-mailberichten identificeert waar de gebruiker de bijlage heeft geopend of opgeslagen en detectie heeft gemaakt op basis van die query.</span><span class="sxs-lookup"><span data-stu-id="81f99-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="81f99-122">U hebt het einde van het proces bereikt nadat alle tests zijn afgelopen.</span><span class="sxs-lookup"><span data-stu-id="81f99-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="81f99-123">De uiteindelijke uitvoer moet zijn:</span><span class="sxs-lookup"><span data-stu-id="81f99-123">The final output should be:</span></span>

- <span data-ttu-id="81f99-124">Een voltooide scorecard</span><span class="sxs-lookup"><span data-stu-id="81f99-124">A completed scorecard</span></span>
- <span data-ttu-id="81f99-125">Een gedetailleerd rapport van de resultaten van de pilot</span><span class="sxs-lookup"><span data-stu-id="81f99-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="81f99-126">Een beslissing over hoe u verder wilt gaan</span><span class="sxs-lookup"><span data-stu-id="81f99-126">A decision on how to move forward</span></span>

<span data-ttu-id="81f99-127">Presenteert de rapporten van uw uiteindelijke uitvoer aan interne belanghebbenden (die u hebt geïdentificeerd tijdens de [voorbereidingsfase)](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) en contactpersonen van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81f99-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="81f99-128">Een dergelijke inspanning zorgt ervoor dat elke feedback kan worden gebruikt om producten en documentatie te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="81f99-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="81f99-129">We hopen dat u plezier hebt gemaakt van deze gesimuleerde omgeving.</span><span class="sxs-lookup"><span data-stu-id="81f99-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="81f99-130">Implementer wat u op grotere schaal hebt geleerd in uw organisatie om de geïntegreerde beveiligingsoplossing zo goed mogelijk te kunnen implementeren.</span><span class="sxs-lookup"><span data-stu-id="81f99-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="81f99-131">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="81f99-131">Next step</span></span>
<span data-ttu-id="81f99-132">Meer informatie over de pilaren van Microsoft 365 Defender via de volgende interactieve handleidingen:</span><span class="sxs-lookup"><span data-stu-id="81f99-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="81f99-133">Uw organisatie beschermen met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="81f99-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="81f99-134">Verdachte activiteiten en potentiële aanvallen detecteren met Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="81f99-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="81f99-135">Beveiligingsrisico's detecteren en waarschuwingen beheren met Microsoft Cloud-app-beveiliging</span><span class="sxs-lookup"><span data-stu-id="81f99-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="81f99-136">Bedreigingen onderzoeken en herstellen met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="81f99-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
