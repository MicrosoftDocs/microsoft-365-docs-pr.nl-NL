---
title: Microsoft Defender controleren voor de architectuurvereisten voor eindpunten en belangrijke concepten
description: Het technische diagram voor Microsoft Defender voor Eindpunt in Microsoft 365 Defender helpt u identiteit te begrijpen in Microsoft 365 voordat u uw proeflaboratorium of testomgeving maakt.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457818"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a><span data-ttu-id="b38ce-103">Microsoft Defender controleren voor de architectuurvereisten voor eindpunten en belangrijke concepten</span><span class="sxs-lookup"><span data-stu-id="b38ce-103">Review Microsoft Defender for Endpoint architecture requirements and key concepts</span></span>

<span data-ttu-id="b38ce-104">**Is van toepassing op:** Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b38ce-104">**Applies to:** Microsoft 365 Defender</span></span>

<span data-ttu-id="b38ce-105">In dit artikel wordt u begeleid bij het instellen van de evaluatie voor Microsoft Defender voor endpoint-omgeving.</span><span class="sxs-lookup"><span data-stu-id="b38ce-105">This article will guide you in the process of setting up the evaluation for Microsoft Defender for Endpoint environment.</span></span>

<span data-ttu-id="b38ce-106">Zie het [overzichtsartikel](eval-defender-endpoint-overview.md)voor meer informatie over dit proces.</span><span class="sxs-lookup"><span data-stu-id="b38ce-106">For more information about this process, see the [overview article](eval-defender-endpoint-overview.md).</span></span>

<span data-ttu-id="b38ce-107">Voordat u Microsoft Defender voor Eindpunt inschakelen, moet u de architectuur begrijpen en aan de vereisten voldoen.</span><span class="sxs-lookup"><span data-stu-id="b38ce-107">Before enabling Microsoft Defender for Endpoint, be sure you understand the architecture and can meet the requirements.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="b38ce-108">De architectuur begrijpen</span><span class="sxs-lookup"><span data-stu-id="b38ce-108">Understand the architecture</span></span>

<span data-ttu-id="b38ce-109">Het volgende diagram illustreert Microsoft Defender voor eindpuntarchitectuur en -integraties.</span><span class="sxs-lookup"><span data-stu-id="b38ce-109">The following diagram illustrates Microsoft Defender for Endpoint architecture and integrations.</span></span> 

![Stappen voor het toevoegen van Microsoft Defender Office aan de evaluatieomgeving van Defender](../../media/defender/m365-defender-endpoint-architecture.png)

<span data-ttu-id="b38ce-111">In de volgende tabel wordt de afbeelding beschreven.</span><span class="sxs-lookup"><span data-stu-id="b38ce-111">The following table describes the illustration.</span></span>

<span data-ttu-id="b38ce-112">Uitroepen</span><span class="sxs-lookup"><span data-stu-id="b38ce-112">Call-out</span></span> | <span data-ttu-id="b38ce-113">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b38ce-113">Description</span></span>
:---|:---|
<span data-ttu-id="b38ce-114">1</span><span class="sxs-lookup"><span data-stu-id="b38ce-114">1</span></span> | <span data-ttu-id="b38ce-115">Apparaten zijn aan boord via een van de ondersteunde beheerhulpmiddelen.</span><span class="sxs-lookup"><span data-stu-id="b38ce-115">Devices are on-boarded through one of the supported management tools.</span></span> 
<span data-ttu-id="b38ce-116">2</span><span class="sxs-lookup"><span data-stu-id="b38ce-116">2</span></span> | <span data-ttu-id="b38ce-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span><span class="sxs-lookup"><span data-stu-id="b38ce-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span></span>
<span data-ttu-id="b38ce-118">3</span><span class="sxs-lookup"><span data-stu-id="b38ce-118">3</span></span> | <span data-ttu-id="b38ce-119">Beheerde apparaten worden samengevoegd en/of geregistreerd in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b38ce-119">Managed devices are joined and/or enrolled in Azure Active Directory.</span></span>
<span data-ttu-id="b38ce-120">4</span><span class="sxs-lookup"><span data-stu-id="b38ce-120">4</span></span> | <span data-ttu-id="b38ce-121">Domain-joined Windows 10 apparaten worden gesynchroniseerd met Azure Active Directory met Azure Active Directory Verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="b38ce-121">Domain-joined Windows 10 devices are synchronized to Azure Active Directory using Azure Active Directory Connect.</span></span>
<span data-ttu-id="b38ce-122">5</span><span class="sxs-lookup"><span data-stu-id="b38ce-122">5</span></span> | <span data-ttu-id="b38ce-123">Waarschuwingen, onderzoeken en antwoorden van Microsoft Defender voor eindpunten worden beheerd in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b38ce-123">Microsoft Defender for Endpoint alerts, investigations, and responses are managed in Microsoft 365 Defender.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="b38ce-124">Belangrijke concepten begrijpen</span><span class="sxs-lookup"><span data-stu-id="b38ce-124">Understand key concepts</span></span>

<span data-ttu-id="b38ce-125">In de volgende tabel worden belangrijke concepten geïdentificeerd die belangrijk zijn om te begrijpen bij het evalueren, configureren en implementeren van Microsoft Defender voor Eindpunt:</span><span class="sxs-lookup"><span data-stu-id="b38ce-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Endpoint:</span></span> 

<span data-ttu-id="b38ce-126">Concept</span><span class="sxs-lookup"><span data-stu-id="b38ce-126">Concept</span></span> | <span data-ttu-id="b38ce-127">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b38ce-127">Description</span></span> | <span data-ttu-id="b38ce-128">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="b38ce-128">More information</span></span>
:---|:---|:---|
<span data-ttu-id="b38ce-129">Beheerportal</span><span class="sxs-lookup"><span data-stu-id="b38ce-129">Administration Portal</span></span> | <span data-ttu-id="b38ce-130">Microsoft 365 Defender portal om te controleren en te helpen bij het reageren op waarschuwingen van potentiële geavanceerde permanente bedreigingsactiviteit of datalekken.</span><span class="sxs-lookup"><span data-stu-id="b38ce-130">Microsoft 365 Defender portal to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> | [<span data-ttu-id="b38ce-131">Overzicht van de Portal van Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b38ce-131">Microsoft Defender for Endpoint portal overview</span></span>](/defender-endpoint/portal-overview)
<span data-ttu-id="b38ce-132">Surface Reduction aanvallen</span><span class="sxs-lookup"><span data-stu-id="b38ce-132">Attack Surface Reduction</span></span> | <span data-ttu-id="b38ce-133">Verminder uw aanvalsoppervlakken door de plaatsen waar uw organisatie kwetsbaar is voor cyberaanvallen en aanvallen te minimaliseren.</span><span class="sxs-lookup"><span data-stu-id="b38ce-133">Help reduce your attack surfaces by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> | [<span data-ttu-id="b38ce-134">Overzicht van kwetsbaarheid voor aanvallen verminderen</span><span class="sxs-lookup"><span data-stu-id="b38ce-134">Overview of attack surface reduction</span></span>](/defender-endpoint/overview-attack-surface-reduction)
<span data-ttu-id="b38ce-135">Eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="b38ce-135">Endpoint Detection and Response</span></span> | <span data-ttu-id="b38ce-136">De mogelijkheden voor eindpuntdetectie en -respons bieden geavanceerde detecties voor aanvallen die in realtime en actie kunnen worden ondernomen.</span><span class="sxs-lookup"><span data-stu-id="b38ce-136">Endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> | [<span data-ttu-id="b38ce-137">Overzicht van eindpuntdetectie en -respons mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="b38ce-137">Overview of endpoint detection and response capabilities</span></span>](/defender-endpoint/overview-endpoint-detection-response)
<span data-ttu-id="b38ce-138">Gedrag blokkeren en insluiting</span><span class="sxs-lookup"><span data-stu-id="b38ce-138">Behavioral Blocking and Containment</span></span> | <span data-ttu-id="b38ce-139">Mogelijkheden voor het blokkeren en inperken van gedrag kunnen helpen bij het identificeren en stoppen van bedreigingen, op basis van hun gedrag en procesbomen, zelfs wanneer de bedreiging is gestart met de uitvoering.</span><span class="sxs-lookup"><span data-stu-id="b38ce-139">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> | [<span data-ttu-id="b38ce-140">Gedragsblokkering en -insluiting</span><span class="sxs-lookup"><span data-stu-id="b38ce-140">Behavioral blocking and containment</span></span>](/defender-endpoint/behavioral-blocking-containment)
<span data-ttu-id="b38ce-141">Geautomatiseerd onderzoek en antwoord</span><span class="sxs-lookup"><span data-stu-id="b38ce-141">Automated Investigation and Response</span></span> | <span data-ttu-id="b38ce-142">Voor geautomatiseerd onderzoek worden verschillende inspectiealgoritmen gebruikt op basis van processen die door beveiligingsanalisten worden gebruikt en die zijn ontworpen om waarschuwingen te onderzoeken en onmiddellijk actie te ondernemen om inbreuken op te lossen.</span><span class="sxs-lookup"><span data-stu-id="b38ce-142">Automated investigation uses various inspection algorithms based on processes that are used by security analysts and designed to examine alerts and take immediate action to resolve breaches.</span></span> | [<span data-ttu-id="b38ce-143">Geautomatiseerde onderzoeken gebruiken om bedreigingen te onderzoeken en te corrigeren</span><span class="sxs-lookup"><span data-stu-id="b38ce-143">Use automated investigations to investigate and remediate threats</span></span>](/defender-endpoint/automated-investigations)
<span data-ttu-id="b38ce-144">Geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b38ce-144">Advanced Hunting</span></span> | <span data-ttu-id="b38ce-145">Geavanceerd zoeken is een op query's gebaseerd hulpprogramma voor bedreigingsjacht waarmee u tot 30 dagen onbewerkte gegevens kunt verkennen, zodat u gebeurtenissen in uw netwerk proactief kunt controleren om bedreigingsindicatoren en entiteiten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="b38ce-145">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data so that you can proactively inspect events in your network to locate threat indicators and entities.</span></span> | [<span data-ttu-id="b38ce-146">Overzicht van geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="b38ce-146">Overview of advanced hunting</span></span>](/defender-endpoint/advanced-hunting-overview)
<span data-ttu-id="b38ce-147">Dreigingsanalyse</span><span class="sxs-lookup"><span data-stu-id="b38ce-147">Threat Analytics</span></span> | <span data-ttu-id="b38ce-148">Bedreigingsanalyse is een reeks rapporten van deskundige Microsoft-beveiligingsonderzoekers over de meest relevante bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="b38ce-148">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats.</span></span> | [<span data-ttu-id="b38ce-149">Nieuwe bedreigingen traceren en hierop reageren</span><span class="sxs-lookup"><span data-stu-id="b38ce-149">Track and respond to emerging threats</span></span>](/defender-endpoint/threat-analytics)


<span data-ttu-id="b38ce-150">Zie Wat is Microsoft Defender voor eindpunt voor meer informatie over de mogelijkheden van Microsoft Defender [voor Eindpunt.](/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="b38ce-150">For more detailed information about the capabilities included with Microsoft Defender for Endpoint, see [What is Microsoft Defender for Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="b38ce-151">SIEM-integratie</span><span class="sxs-lookup"><span data-stu-id="b38ce-151">SIEM integration</span></span>

<span data-ttu-id="b38ce-152">U kunt Microsoft Defender voor Eindpunt integreren met Azure Sentinel om beveiligingsgebeurtenissen in uw organisatie uitgebreider te analyseren en playbooks te maken voor een effectieve en onmiddellijke reactie.</span><span class="sxs-lookup"><span data-stu-id="b38ce-152">You can integrate Microsoft Defender for Endpoint with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> 

<span data-ttu-id="b38ce-153">Microsoft Defender voor Eindpunt kan ook worden geïntegreerd in andere SIEM-oplossingen (Security Information and Event Management).</span><span class="sxs-lookup"><span data-stu-id="b38ce-153">Microsoft Defender for Endpoint can also be integrated into other Security Information and Event Management (SIEM) solutions.</span></span> <span data-ttu-id="b38ce-154">Zie [SiEM-integratie inschakelen in Microsoft Defender voor eindpunt voor meer informatie.](/defender-endpoint/enable-siem-integration)</span><span class="sxs-lookup"><span data-stu-id="b38ce-154">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](/defender-endpoint/enable-siem-integration).</span></span>


## <a name="next-steps"></a><span data-ttu-id="b38ce-155">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="b38ce-155">Next steps</span></span>
[<span data-ttu-id="b38ce-156">De evaluatie inschakelen</span><span class="sxs-lookup"><span data-stu-id="b38ce-156">Enable the evaluation</span></span>](eval-defender-endpoint-enable-eval.md)

<span data-ttu-id="b38ce-157">Terug naar het overzicht voor [Microsoft Defender evalueren voor eindpunt](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b38ce-157">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="b38ce-158">Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b38ce-158">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>