---
title: Uw beveiligingshouding voorbereiden op het eerste incident
description: Stel de beveiligingsstatus Microsoft 365 van uw tenant in voor uw eerste incident in Microsoft 365 Defender.
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
ms.openlocfilehash: 76bead8fd855e4119db6297d2ab1a3d08d64a48c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297162"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="a86e4-104">Uw beveiligingshouding voorbereiden op het eerste incident</span><span class="sxs-lookup"><span data-stu-id="a86e4-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a86e4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a86e4-105">**Applies to:**</span></span>
- <span data-ttu-id="a86e4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a86e4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a86e4-107">Als u zich voorbereidt op incidentafhandeling, moet het netwerk van een organisatie voldoende worden beschermd tegen verschillende soorten beveiligingsincidenten.</span><span class="sxs-lookup"><span data-stu-id="a86e4-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="a86e4-108">Om het risico op beveiligingsincidenten te beperken, raadt het National Institute of Standards and Technology (NIST) verschillende beveiligingspraktijken aan, waaronder risicobeoordelingen, het verbeteren van de beveiliging van de host, het veilig configureren van netwerken en het voorkomen van malware.</span><span class="sxs-lookup"><span data-stu-id="a86e4-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="a86e4-109">Microsoft 365 Defender kan helpen bij het aanpakken van verschillende aspecten van incidentpreventie:</span><span class="sxs-lookup"><span data-stu-id="a86e4-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="a86e4-110">Een [Zero Trust-framework](https://docs.microsoft.com/security/zero-trust/) implementeren</span><span class="sxs-lookup"><span data-stu-id="a86e4-110">Implementing a [Zero Trust](https://docs.microsoft.com/security/zero-trust/) framework</span></span>
- <span data-ttu-id="a86e4-111">Uw beveiligingsstatus bepalen door een score toe te wijzen met [Microsoft Secure Score](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="a86e4-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="a86e4-112">Bedreigingen voorkomen via kwetsbaarheidsbeoordelingen in [Bedreigings- en kwetsbaarheidsbeheer](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="a86e4-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="a86e4-113">Inzicht in de meest recente beveiligingsrisico's, zodat u zich op deze bedreigingen kunt voorbereiden</span><span class="sxs-lookup"><span data-stu-id="a86e4-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="a86e4-114">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="a86e4-114">Step 1.</span></span> <span data-ttu-id="a86e4-115">Nul vertrouwen implementeren</span><span class="sxs-lookup"><span data-stu-id="a86e4-115">Implement Zero Trust</span></span>

<span data-ttu-id="a86e4-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) is een geïntegreerde beveiligingsbeschouwing en end-to-endstrategie waarin rekening wordt gehouden met de complexe aard van elke moderne omgeving, met inbegrip van het mobiele personeel en de gebruikers, apparaten, toepassingen en gegevens, waar ze zich ook bevinden.</span><span class="sxs-lookup"><span data-stu-id="a86e4-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="a86e4-117">Door één deelvenster met glas te bieden om alle eindpuntdetecties op een consistente manier te beheren, kan [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) Microsoft 365 Defender het uw beveiligingsteam gemakkelijker maken om de basisprincipes van Zero Trust te implementeren.</span><span class="sxs-lookup"><span data-stu-id="a86e4-117">By providing a single pane of glass to manage all endpoint detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="a86e4-118">Onderdelen van Microsoft 365 Defender kunnen schendingen van regels weergeven die zijn geïmplementeerd om beleid voor voorwaardelijke toegang voor Zero Trust tot stand te brengen door gegevens van Microsoft Defender voor Eindpunt (MDE) of andere mobiele beveiligingsleveranciers te integreren als informatiebron voor beleidsregels voor apparaat compliance en implementatie van beleidsregels voor voorwaardelijke toegang op apparaten.</span><span class="sxs-lookup"><span data-stu-id="a86e4-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint (MDE) or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="a86e4-119">Apparaatrisico is rechtstreeks van invloed op de bronnen die toegankelijk zijn voor de gebruiker van dat apparaat.</span><span class="sxs-lookup"><span data-stu-id="a86e4-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="a86e4-120">De weigering van toegang tot resources op basis van bepaalde criteria is het hoofdthema van Zero Trust en Microsoft 365 Defender biedt informatie die nodig is om de criteria op vertrouwensniveau te bepalen.</span><span class="sxs-lookup"><span data-stu-id="a86e4-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="a86e4-121">Zo kan Microsoft 365 Defender het softwareversieniveau van een apparaat bieden via de pagina Bedreigings- en beveiligingsprobleembeheer, terwijl beleidsregels voor voorwaardelijke toegang apparaten beperken die verouderde of kwetsbare versies hebben.</span><span class="sxs-lookup"><span data-stu-id="a86e4-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="a86e4-122">Automatisering is een essentieel onderdeel van het implementeren en onderhouden van een Zero Trust-omgeving, terwijl ook het aantal waarschuwingen wordt beperkt dat mogelijk tot incidenten kan leiden.</span><span class="sxs-lookup"><span data-stu-id="a86e4-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="a86e4-123">Onderdelen van Microsoft 365 Defender kunnen worden geautomatiseerd, zoals herstelacties [(ook](m365d-autoir.md) wel onderzoeken voor een incident in het Microsoft 365-beveiligingscentrum genoemd), meldingsacties en zelfs het maken van ondersteuningstickets, zoals in [ServiceNow.](https://microsoft.service-now.com/sp/)</span><span class="sxs-lookup"><span data-stu-id="a86e4-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="a86e4-124">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="a86e4-124">Step 2.</span></span> <span data-ttu-id="a86e4-125">De beveiligingsstatus van uw organisatie bepalen</span><span class="sxs-lookup"><span data-stu-id="a86e4-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="a86e4-126">Vervolgens kunnen organisaties de [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender gebruiken om uw huidige beveiligingsstatus te bepalen en aanbevelingen te overwegen voor het verbeteren van deze score.</span><span class="sxs-lookup"><span data-stu-id="a86e4-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="a86e4-127">Hoe hoger de score is, hoe meer beveiligingsaanbevelingen en verbeteracties door de organisatie zijn genomen.</span><span class="sxs-lookup"><span data-stu-id="a86e4-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="a86e4-128">Aanbevelingen voor veilige score kunnen worden gebruikt voor verschillende producten en organisaties in staat stellen hun scores nog hoger te maken.</span><span class="sxs-lookup"><span data-stu-id="a86e4-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Voorbeeld van Microsoft Secure Score in het Microsoft-beveiligingscentrum":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="a86e4-130">Stap 3.</span><span class="sxs-lookup"><span data-stu-id="a86e4-130">Step 3.</span></span> <span data-ttu-id="a86e4-131">De kwetsbaarheidsblootstelling van uw organisatie beoordelen</span><span class="sxs-lookup"><span data-stu-id="a86e4-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="a86e4-132">Het voorkomen van incidenten kan helpen bij het stroomlijnen van de beveiligingsactiviteiten om zich te richten op aan de hand van kritieke en belangrijke beveiligingsincidenten.</span><span class="sxs-lookup"><span data-stu-id="a86e4-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="a86e4-133">Softwareproblemen zijn vaak een preventief toegangspunt voor aanvallen die kunnen leiden tot gegevensdiefstal, gegevensverlies of verstoring van bedrijfsactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="a86e4-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="a86e4-134">Als er geen aanvallen worden uitgevoerd, moeten beveiligingsbewerkingen ernaar streven om een acceptabel niveau van blootstelling aan kwetsbaarheid [in](../defender-endpoint/tvm-exposure-score.md) hun organisatie te bereiken en te behouden.</span><span class="sxs-lookup"><span data-stu-id="a86e4-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="a86e4-135">Als u de voortgang van [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) de softwarepatching wilt controleren, gaat u naar de pagina Bedreigings- en kwetsbaarheidsbeheer in Defender voor Eindpunt, die u kunt openen vanuit Microsoft 365 Defender via het tabblad **Meer** bronnen.</span><span class="sxs-lookup"><span data-stu-id="a86e4-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Voorbeeld van de pagina Bedreiging en kwetsbaarheid in het Microsoft-beveiligingscentrum"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="a86e4-137">4. Nieuwe bedreigingen begrijpen</span><span class="sxs-lookup"><span data-stu-id="a86e4-137">4. Understand emerging threats</span></span>

<span data-ttu-id="a86e4-138">Gebruik [bedreigingsanalyse](threat-analytics.md) in het Microsoft 365 beveiligingscentrum om up-to-date te blijven met het huidige landschap van beveiligingsrisico's.</span><span class="sxs-lookup"><span data-stu-id="a86e4-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="a86e4-139">Deskundige beveiligingsonderzoekers van Microsoft maken rapporten waarin de meest recente cyberdreigingen gedetailleerd worden beschreven, zodat u kunt begrijpen hoe deze van invloed kunnen zijn op uw Microsoft 365-abonnement, apparaten en gebruikers.</span><span class="sxs-lookup"><span data-stu-id="a86e4-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="a86e4-140">Deze rapporten kunnen bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="a86e4-140">These reports can include:</span></span>

- <span data-ttu-id="a86e4-141">Actieve bedreigingsacteurs en hun campagnes</span><span class="sxs-lookup"><span data-stu-id="a86e4-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="a86e4-142">Populaire en nieuwe aanvalstechnieken</span><span class="sxs-lookup"><span data-stu-id="a86e4-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="a86e4-143">Kritieke beveiligingslekken</span><span class="sxs-lookup"><span data-stu-id="a86e4-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="a86e4-144">Veelvoorkomende aanvalsoppervlakken</span><span class="sxs-lookup"><span data-stu-id="a86e4-144">Common attack surfaces</span></span>
- <span data-ttu-id="a86e4-145">Voorkomende malware</span><span class="sxs-lookup"><span data-stu-id="a86e4-145">Prevalent malware</span></span>

<span data-ttu-id="a86e4-146">U kunt de aanbevelingen van een nieuwe bedreiging implementeren om uw beveiligingshouding te versterken en het oppervlak van de aanval te minimaliseren.</span><span class="sxs-lookup"><span data-stu-id="a86e4-146">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="a86e4-147">Maak tijd in uw planning om regelmatig de sectie [Bedreigingsanalyse](threat-analytics.md) van het Microsoft 365 te controleren.</span><span class="sxs-lookup"><span data-stu-id="a86e4-147">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="a86e4-148">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="a86e4-148">Next step</span></span>

<span data-ttu-id="a86e4-149">[![Stap 1: Informatie over het triagen en analyseren van incidenten](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="a86e4-149">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="a86e4-150">Meer informatie over het [triagen en analyseren van incidenten.](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="a86e4-150">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a86e4-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a86e4-151">See also</span></span>

- [<span data-ttu-id="a86e4-152">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="a86e4-152">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a86e4-153">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a86e4-153">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a86e4-154">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="a86e4-154">Manage incidents</span></span>](manage-incidents.md)
