---
title: Microsoft Threat Experts
ms.reviewer: ''
description: Microsoft Threat Experts biedt een extra laag expertise aan Microsoft Defender voor Eindpunt.
keywords: managed threat hunting service, managed threat hunting, managed detection and response (MDR) service, MTE, Microsoft Threat Experts, MTE-TAN, targeted attack notification, Targeted Attack Notification
search.product: Windows 10
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
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 956fb591154df374c8010d875645e1122f3419b2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879238"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="21f4a-104">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="21f4a-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="21f4a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="21f4a-105">**Applies to:**</span></span>
- [<span data-ttu-id="21f4a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="21f4a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="21f4a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21f4a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="21f4a-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="21f4a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="21f4a-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="21f4a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="21f4a-110">Microsoft Threat Experts is een beheerde bedreigingsjachtservice die uw Beveiligingscentrums (SOC's) voorziet van monitoring en analyse op expertniveau om ervoor te zorgen dat kritieke bedreigingen in uw unieke omgevingen niet worden gemist.</span><span class="sxs-lookup"><span data-stu-id="21f4a-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="21f4a-111">Deze beheerde bedreigingsjachtservice biedt op experts gebaseerde inzichten en gegevens via deze twee mogelijkheden: gerichte aanvalsmelding en toegang tot experts op aanvraag.</span><span class="sxs-lookup"><span data-stu-id="21f4a-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="21f4a-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="21f4a-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="21f4a-113">Bespreek de geschiktheidsvereisten met uw Microsoft Technical Service-provider en -accountteam voordat u een aanvraag voor de beheerde bedreigingsjachtservice gaat indienen.</span><span class="sxs-lookup"><span data-stu-id="21f4a-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="21f4a-114">Als u een klant van Microsoft Defender voor Eindpunt bent, moet u **Microsoft Threat Experts - Targeted Attack Notifications** aanvragen om speciale inzichten en analyses te krijgen die u helpen bij het identificeren van de meest kritieke bedreigingen in uw omgeving, zodat u er snel op kunt reageren.</span><span class="sxs-lookup"><span data-stu-id="21f4a-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly.</span></span>

<span data-ttu-id="21f4a-115">Als u zich wilt Microsoft Threat Experts - Voordelen voor gerichte aanvalsmeldingen, gaat u naar Instellingen  >  **Endpoints**  >  **General**  >  **Advanced-functies**  >  **Microsoft Threat Experts - Targeted Attack Notifications** om toe te passen.</span><span class="sxs-lookup"><span data-stu-id="21f4a-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **Endpoints** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="21f4a-116">Zodra deze is geaccepteerd, krijgt u de voordelen van Meldingen voor gerichte aanvallen.</span><span class="sxs-lookup"><span data-stu-id="21f4a-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="21f4a-117">Neem contact op met uw accountteam of Microsoft-vertegenwoordiger om u te abonneren op **Microsoft Threat Experts - Experts op** aanvraag om contact op te nemen met onze bedreigingsexperts over relevante detecties en tegenstand die uw organisatie te maken heeft.</span><span class="sxs-lookup"><span data-stu-id="21f4a-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="21f4a-118">Zie [De Microsoft Threat Experts configureren voor](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="21f4a-118">See [Configure Microsoft Threat Experts capabilities](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="21f4a-119">Microsoft Threat Experts - Melding van gerichte aanval</span><span class="sxs-lookup"><span data-stu-id="21f4a-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="21f4a-120">Microsoft Threat Experts- Gerichte aanvalsmelding biedt proactief zoeken naar de belangrijkste bedreigingen voor uw netwerk, zoals inbraken door menselijke tegenpartij, hands-on-keyboard-aanvallen of geavanceerde aanvallen, zoals cyberspionage.</span><span class="sxs-lookup"><span data-stu-id="21f4a-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="21f4a-121">Deze meldingen worden als een nieuwe waarschuwing op de voormelding uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="21f4a-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="21f4a-122">De beheerde huntingservice bevat:</span><span class="sxs-lookup"><span data-stu-id="21f4a-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="21f4a-123">Bedreigingsbewaking en -analyse, waardoor de tijd en het risico voor het bedrijf worden verkleind</span><span class="sxs-lookup"><span data-stu-id="21f4a-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="21f4a-124">Door de jager getrainde kunstmatige intelligentie om bekende en onbekende aanvallen te ontdekken en prioriteit te geven</span><span class="sxs-lookup"><span data-stu-id="21f4a-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="21f4a-125">De belangrijkste risico's identificeren, soc's helpen tijd en energie te maximaliseren</span><span class="sxs-lookup"><span data-stu-id="21f4a-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="21f4a-126">Bereik van compromissen en zo veel context als snel kan worden geleverd om een snelle soc-reactie in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="21f4a-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="21f4a-127">Microsoft Threat Experts - Experts op aanvraag</span><span class="sxs-lookup"><span data-stu-id="21f4a-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="21f4a-128">Klanten kunnen onze beveiligingsexperts rechtstreeks betrekken vanuit Microsoft Defender-beveiligingscentrum voor een tijdige en nauwkeurige reactie.</span><span class="sxs-lookup"><span data-stu-id="21f4a-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="21f4a-129">Experts bieden inzichten die nodig zijn om beter inzicht te krijgen in de complexe bedreigingen die van invloed zijn op uw organisatie, van waarschuwingsvragen, mogelijk gecompromitteerde apparaten, hoofdoorzaak van een verdachte netwerkverbinding, tot aanvullende bedreigingsinformatie over lopende geavanceerde permanente bedreigingscampagnes.</span><span class="sxs-lookup"><span data-stu-id="21f4a-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="21f4a-130">Met deze mogelijkheid kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="21f4a-130">With this capability, you can:</span></span>
- <span data-ttu-id="21f4a-131">Meer informatie over waarschuwingen, waaronder de hoofdoorzaak of het bereik van het incident</span><span class="sxs-lookup"><span data-stu-id="21f4a-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="21f4a-132">Meer duidelijkheid over verdacht apparaatgedrag en de volgende stappen als u wordt geconfronteerd met een geavanceerde aanvaller</span><span class="sxs-lookup"><span data-stu-id="21f4a-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="21f4a-133">Risico's en beveiliging met betrekking tot bedreigingsacacteurs, campagnes of nieuwe technieken voor aanvallers bepalen</span><span class="sxs-lookup"><span data-stu-id="21f4a-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="21f4a-134">De optie Om **een bedreigingsdeskundige te raadplegen** is beschikbaar op verschillende plaatsen in de portal, zodat u contact kunt opnemen met experts in de context van uw onderzoek:</span><span class="sxs-lookup"><span data-stu-id="21f4a-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="21f4a-135"><i>**Help- en ondersteuningsmenu**</i></span><span class="sxs-lookup"><span data-stu-id="21f4a-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="21f4a-136">![Schermafbeelding van de menuoptie MTE-EOD](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="21f4a-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="21f4a-137"><i>**Menu Apparaatpaginaacties**</i></span><span class="sxs-lookup"><span data-stu-id="21f4a-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="21f4a-138">![Schermafbeelding van de optie actiemenu voor MTE-EOD-apparaatpagina](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="21f4a-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="21f4a-139"><i>**Menu Waarschuwingenpaginaacties**</i></span><span class="sxs-lookup"><span data-stu-id="21f4a-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="21f4a-140">![Schermafbeelding van de optie actiemenu MTE-EOD-waarschuwingspagina](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="21f4a-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="21f4a-141"><i>**Menu Bestandspaginaacties**</i></span><span class="sxs-lookup"><span data-stu-id="21f4a-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="21f4a-142">![Schermafbeelding van de optie actiemenu MTE-EOD-bestandspagina](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="21f4a-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="21f4a-143">Als u de status van uw Experts on Demand-zaken wilt bijhouden via Microsoft Services Hub, kunt u contact op nemen met uw Technical Account Manager.</span><span class="sxs-lookup"><span data-stu-id="21f4a-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="21f4a-144">Bekijk deze video voor een kort overzicht van de Microsoft Services Hub.</span><span class="sxs-lookup"><span data-stu-id="21f4a-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="21f4a-145">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="21f4a-145">Related topic</span></span>
- [<span data-ttu-id="21f4a-146">De Microsoft Threat Experts configureren</span><span class="sxs-lookup"><span data-stu-id="21f4a-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
