---
title: Updates Microsoft Defender Antivirus en basislijnen toepassen
description: Beheer hoe Microsoft Defender Antivirus beveiligings- en productupdates ontvangt.
keywords: updates, beveiligingslijnlijnen, beveiliging, planningsupdates, force-updates, mobiele updates, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/12/2021
ms.openlocfilehash: 0179c620c8ba00c987395a800ed335644048283f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394963"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="10ba5-104">Updates Microsoft Defender Antivirus en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="10ba5-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="10ba5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="10ba5-105">**Applies to:**</span></span>

- [<span data-ttu-id="10ba5-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="10ba5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="10ba5-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="10ba5-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="10ba5-108">Het Microsoft Defender Antivirus up-to-date houden is essentieel om ervoor te zorgen dat uw apparaten de nieuwste technologie en functies hebben die nodig zijn om te beschermen tegen nieuwe malware en aanvalstechnieken.</span><span class="sxs-lookup"><span data-stu-id="10ba5-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="10ba5-109">Zorg ervoor dat u uw antivirusbeveiliging bij werkt, zelfs als Microsoft Defender Antivirus actief is in [de passieve modus.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="10ba5-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="10ba5-110">Er zijn twee soorten updates die betrekking hebben op het up-to-date Microsoft Defender Antivirus houden:</span><span class="sxs-lookup"><span data-stu-id="10ba5-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="10ba5-111">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="10ba5-111">Security intelligence updates</span></span>
- <span data-ttu-id="10ba5-112">Productupdates</span><span class="sxs-lookup"><span data-stu-id="10ba5-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="10ba5-113">Als u de meest recente engine, platform en handtekeningdatum wilt zien, gaat u naar de beveiligingsinformatieupdates voor Microsoft Defender Antivirus [en andere Microsoft-antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="10ba5-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="10ba5-114">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="10ba5-114">Security intelligence updates</span></span>

<span data-ttu-id="10ba5-115">Microsoft Defender Antivirus gebruikt beveiliging in de cloud (ook wel de Microsoft Advanced Protection Service of KAARTEN genoemd) en downloadt regelmatig [beveiligingsinformatie-updates](cloud-protection-microsoft-defender-antivirus.md) om bescherming te bieden.</span><span class="sxs-lookup"><span data-stu-id="10ba5-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="10ba5-116">Updates worden uitgebracht onder de onderstaande KB-nummers:</span><span class="sxs-lookup"><span data-stu-id="10ba5-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="10ba5-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="10ba5-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="10ba5-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="10ba5-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="10ba5-119">Beveiliging in de cloud is altijd actief en hiervoor is een actieve verbinding met internet vereist.</span><span class="sxs-lookup"><span data-stu-id="10ba5-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="10ba5-120">Beveiligingsintelligentie-updates vinden plaats op een geplande cadans (configureerbaar via beleid).</span><span class="sxs-lookup"><span data-stu-id="10ba5-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="10ba5-121">Zie Microsoft [Cloud-beveiliging](cloud-protection-microsoft-defender-antivirus.md)gebruiken in Microsoft Defender Antivirus voor meer Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="10ba5-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="10ba5-122">Zie Beveiligingsinformatie-updates voor Microsoft Defender Antivirus en andere Microsoft-antimalware voor een lijst met recente [beveiligingsinformatieupdates.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="10ba5-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="10ba5-123">Engine-updates worden opgenomen in beveiligingsinformatie-updates en worden maandelijks uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="10ba5-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="10ba5-124">Productupdates</span><span class="sxs-lookup"><span data-stu-id="10ba5-124">Product updates</span></span>

<span data-ttu-id="10ba5-125">Microsoft Defender Antivirus vereist [maandelijkse updates (KB4052623),](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) ook wel *platformupdates genoemd.*</span><span class="sxs-lookup"><span data-stu-id="10ba5-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="10ba5-126">U kunt de distributie van updates beheren via een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="10ba5-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="10ba5-127">Windows Serverupdateservice (WSUS)</span><span class="sxs-lookup"><span data-stu-id="10ba5-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="10ba5-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="10ba5-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="10ba5-129">De gebruikelijke methode die u gebruikt om Microsoft te implementeren en Windows te installeren op eindpunten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="10ba5-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="10ba5-130">Zie De bronnen voor [beveiligingsupdates Microsoft Defender Antivirus beheren voor meer informatie.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="10ba5-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="10ba5-131">Maandelijkse updates worden gefaseerd uitgebracht, wat resulteert in meerdere pakketten die zichtbaar zijn in [uw Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="10ba5-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="10ba5-132">In dit artikel worden wijzigingen vermeld die zijn opgenomen in het brede releasekanaal.</span><span class="sxs-lookup"><span data-stu-id="10ba5-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="10ba5-133">[Bekijk de nieuwste release van een breed kanaal hier](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span><span class="sxs-lookup"><span data-stu-id="10ba5-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="10ba5-134">Zie Het geleidelijke implementatieproces voor [Microsoft Defender-updates](manage-gradual-rollout.md)beheren voor meer informatie over het geleidelijke implementatieproces en voor meer informatie over de volgende release.</span><span class="sxs-lookup"><span data-stu-id="10ba5-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="10ba5-135">Zie Beveiligingsinformatie-updates voor Microsoft Defender Antivirus en andere [Microsoft-antimalware](https://www.microsoft.com/wdsi/defenderupdates)voor meer informatie over beveiligingsinformatie-updates.</span><span class="sxs-lookup"><span data-stu-id="10ba5-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="10ba5-136">Maandelijkse platform- en engineversies</span><span class="sxs-lookup"><span data-stu-id="10ba5-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="10ba5-137">Zie Update voor Windows Defender [antimalwareplatform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)voor informatie over het bijwerken of installeren van de platformupdate.</span><span class="sxs-lookup"><span data-stu-id="10ba5-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="10ba5-138">Al onze updates bevatten</span><span class="sxs-lookup"><span data-stu-id="10ba5-138">All our updates contain</span></span> 
- <span data-ttu-id="10ba5-139">prestatieverbeteringen;</span><span class="sxs-lookup"><span data-stu-id="10ba5-139">performance improvements;</span></span>
- <span data-ttu-id="10ba5-140">verbeteringen in de servicebaarheid; en</span><span class="sxs-lookup"><span data-stu-id="10ba5-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="10ba5-141">integratieverbeteringen (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="10ba5-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="10ba5-142">Juni-2021 (Platform: 4.18.2106.5 | Motor: 1.1.18300.4)</span><span class="sxs-lookup"><span data-stu-id="10ba5-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="10ba5-143">&ensp;Versie van beveiligingsinformatieupdate: **1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="10ba5-144">&ensp;Uitgebracht: **28 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="10ba5-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="10ba5-145">&ensp;Platform: **4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="10ba5-146">&ensp;Motor: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="10ba5-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="10ba5-147">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="10ba5-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-148">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-148">What's new</span></span>
- <span data-ttu-id="10ba5-149">Nieuwe besturingselementen voor het beheren van het geleidelijke implementatieproces van Microsoft Defender-updates.</span><span class="sxs-lookup"><span data-stu-id="10ba5-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="10ba5-150">Zie [Het geleidelijke implementatieproces voor Microsoft Defender-updates beheren.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="10ba5-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="10ba5-151">Verbetering van de motor voor gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="10ba5-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="10ba5-152">Verbeteringen in de implementatie van antimalwaredefinities</span><span class="sxs-lookup"><span data-stu-id="10ba5-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="10ba5-153">Uitgebreide edge-netwerkgebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="10ba5-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-154">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-154">Known Issues</span></span>
<span data-ttu-id="10ba5-155">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="10ba5-156">Mei-2021 (Platform: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="10ba5-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="10ba5-157">&ensp;Versie van beveiligingsinformatieupdate: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="10ba5-158">&ensp;Uitgebracht: **3 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="10ba5-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="10ba5-159">&ensp;Platform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="10ba5-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="10ba5-160">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="10ba5-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="10ba5-161">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="10ba5-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-162">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-162">What's new</span></span>
- <span data-ttu-id="10ba5-163">Verbeteringen in [gedragscontrole](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="10ba5-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="10ba5-164">Functie [voor het filteren van meldingen](network-protection.md) voor vaste netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="10ba5-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-165">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-165">Known Issues</span></span>
<span data-ttu-id="10ba5-166">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="10ba5-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="10ba5-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="10ba5-168">&ensp;Versie van beveiligingsinformatieupdate: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="10ba5-169">&ensp;Uitgebracht: **26 april 2021**  (Engine: 1.1.18100.6 uitgebracht op 5 mei 2021) &ensp; Platform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="10ba5-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="10ba5-170">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="10ba5-171">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="10ba5-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-172">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-172">What's new</span></span>
- <span data-ttu-id="10ba5-173">Aanvullende logica voor gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="10ba5-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="10ba5-174">Verbeterde detectie van de kernelmodussleutellogboek</span><span class="sxs-lookup"><span data-stu-id="10ba5-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="10ba5-175">Nieuwe besturingselementen toegevoegd om het geleidelijke implementatieproces voor [Microsoft Defender-updates te beheren](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="10ba5-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="10ba5-176">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-176">Known Issues</span></span>
<span data-ttu-id="10ba5-177">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="10ba5-178">Eerdere versieupdates: Alleen ondersteuning voor technische upgrade</span><span class="sxs-lookup"><span data-stu-id="10ba5-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="10ba5-179">Nadat een nieuwe pakketversie is uitgebracht, wordt de ondersteuning voor de vorige twee versies beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="10ba5-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="10ba5-180">Versies die ouder zijn dan die in deze sectie worden weergegeven, en alleen beschikbaar zijn voor ondersteuning voor technische upgrades.</span><span class="sxs-lookup"><span data-stu-id="10ba5-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="10ba5-181">Maart-2021 (Platform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="10ba5-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="10ba5-182">&ensp;Versie van beveiligingsinformatieupdate: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="10ba5-183">&ensp;Uitgebracht: **2 april 2021**</span><span class="sxs-lookup"><span data-stu-id="10ba5-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="10ba5-184">&ensp;Platform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="10ba5-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="10ba5-185">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="10ba5-186">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-187">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-187">What's new</span></span>

- <span data-ttu-id="10ba5-188">Verbetering van de engine Gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="10ba5-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="10ba5-189">Uitgebreide netwerkbeperking met brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="10ba5-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="10ba5-190">Extra mislukte poging tot het maken van een poging tot geknoei wanneer [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="10ba5-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-191">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-191">Known Issues</span></span>
<span data-ttu-id="10ba5-192">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="10ba5-193">Februari-2021 (Platform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="10ba5-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="10ba5-194">&ensp;Versie van beveiligingsinformatieupdate: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="10ba5-195">&ensp;Uitgebracht: **9 maart 2021**</span><span class="sxs-lookup"><span data-stu-id="10ba5-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="10ba5-196">&ensp;Platform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="10ba5-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="10ba5-197">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="10ba5-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="10ba5-198">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-199">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-199">What's new</span></span>

- <span data-ttu-id="10ba5-200">Verbeterde serviceherstel door middel [van beveiliging tegen geknoei](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="10ba5-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="10ba5-201">Beveiligingsbereik voor tampers uitbreiden</span><span class="sxs-lookup"><span data-stu-id="10ba5-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-202">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-202">Known Issues</span></span>
<span data-ttu-id="10ba5-203">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="10ba5-204">Januari-2021 (Platform: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="10ba5-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="10ba5-205">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="10ba5-206">&ensp;Uitgebracht: **2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="10ba5-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="10ba5-207">&ensp;Platform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="10ba5-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="10ba5-208">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="10ba5-209">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-210">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-210">What's new</span></span>

- <span data-ttu-id="10ba5-211">Verbeteringen voor detectie van Shellcode-exploits</span><span class="sxs-lookup"><span data-stu-id="10ba5-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="10ba5-212">Meer zichtbaarheid voor pogingen tot het stelen van referenties</span><span class="sxs-lookup"><span data-stu-id="10ba5-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="10ba5-213">Verbeteringen in antitamperingfuncties in Microsoft Defender Antivirus services</span><span class="sxs-lookup"><span data-stu-id="10ba5-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="10ba5-214">Verbeterde ondersteuning voor ARM x64-emulatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="10ba5-215">Oplossing: EDR Blokkeermelding blijft in de bedreigingsgeschiedenis staan nadat realtimebeveiliging eerste detectie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="10ba5-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-216">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-216">Known Issues</span></span>
<span data-ttu-id="10ba5-217">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="10ba5-218">November-2020 (Platform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="10ba5-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="10ba5-219">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="10ba5-220">&ensp;Uitgebracht: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="10ba5-221">&ensp;Platform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="10ba5-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="10ba5-222">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="10ba5-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="10ba5-223">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-224">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-224">What's new</span></span>

- <span data-ttu-id="10ba5-225">Verbeterde [ondersteuning voor SmartScreen-statusregistratie](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="10ba5-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-226">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-226">Known Issues</span></span>
<span data-ttu-id="10ba5-227">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="10ba5-228">Oktober-2020 (Platform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="10ba5-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="10ba5-229">&ensp;Versie van beveiligingsinformatieupdate: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="10ba5-230">&ensp;Uitgebracht: **29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="10ba5-231">&ensp;Platform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="10ba5-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="10ba5-232">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="10ba5-233">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-234">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-234">What's new</span></span>

- <span data-ttu-id="10ba5-235">Nieuwe beschrijvingen voor categorieën met speciale bedreigingen</span><span class="sxs-lookup"><span data-stu-id="10ba5-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="10ba5-236">Verbeterde emulatiemogelijkheden</span><span class="sxs-lookup"><span data-stu-id="10ba5-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="10ba5-237">Verbeterde mogelijkheden voor het toestaan/blokkeren van hostadressen</span><span class="sxs-lookup"><span data-stu-id="10ba5-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="10ba5-238">Nieuwe optie in Defender CSP om het samenvoegen van lokale gebruikersuitsluitingen te negeren</span><span class="sxs-lookup"><span data-stu-id="10ba5-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-239">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-239">Known Issues</span></span>

<span data-ttu-id="10ba5-240">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="10ba5-241">September-2020 (Platform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="10ba5-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="10ba5-242">&ensp;Versie van beveiligingsinformatieupdate: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="10ba5-243">&ensp;Uitgebracht: **1 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="10ba5-244">&ensp;Platform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="10ba5-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="10ba5-245">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="10ba5-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="10ba5-246">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-247">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-247">What's new</span></span>

- <span data-ttu-id="10ba5-248">Beheerdersmachtigingen zijn vereist om bestanden in quarantaine te herstellen</span><span class="sxs-lookup"><span data-stu-id="10ba5-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="10ba5-249">XML-opgemaakte gebeurtenissen worden nu ondersteund</span><span class="sxs-lookup"><span data-stu-id="10ba5-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="10ba5-250">CSP-ondersteuning voor het negeren van uitsluitings samenvoegen</span><span class="sxs-lookup"><span data-stu-id="10ba5-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="10ba5-251">Nieuwe beheerinterfaces voor:</span><span class="sxs-lookup"><span data-stu-id="10ba5-251">New management interfaces for:</span></span>
   - <span data-ttu-id="10ba5-252">UDP-inspectie</span><span class="sxs-lookup"><span data-stu-id="10ba5-252">UDP Inspection</span></span>
   - <span data-ttu-id="10ba5-253">Netwerkbeveiliging op Server 2019</span><span class="sxs-lookup"><span data-stu-id="10ba5-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="10ba5-254">IP-adresuitsluitingen voor netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="10ba5-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="10ba5-255">Verbeterde zichtbaarheid van TPM-metingen</span><span class="sxs-lookup"><span data-stu-id="10ba5-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="10ba5-256">Verbeterde Office VBA-module scannen</span><span class="sxs-lookup"><span data-stu-id="10ba5-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-257">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-257">Known Issues</span></span>

<span data-ttu-id="10ba5-258">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="10ba5-259">Augustus-2020 (Platform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="10ba5-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="10ba5-260">&ensp;Versie van beveiligingsinformatieupdate: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="10ba5-261">&ensp;Uitgebracht: **27 augustus 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="10ba5-262">&ensp;Platform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="10ba5-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="10ba5-263">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="10ba5-264">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="10ba5-265">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-265">What's new</span></span>

- <span data-ttu-id="10ba5-266">Meer telemetriegebeurtenissen toevoegen</span><span class="sxs-lookup"><span data-stu-id="10ba5-266">Add more telemetry events</span></span>
- <span data-ttu-id="10ba5-267">Verbeterde telemetrie scangebeurtenis</span><span class="sxs-lookup"><span data-stu-id="10ba5-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="10ba5-268">Verbeterde gedragscontrole voor geheugenscans</span><span class="sxs-lookup"><span data-stu-id="10ba5-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="10ba5-269">Verbeterde macrostreams scannen</span><span class="sxs-lookup"><span data-stu-id="10ba5-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="10ba5-270">Toegevoegd `AMRunningMode` aan Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="10ba5-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="10ba5-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wordt genegeerd.</span><span class="sxs-lookup"><span data-stu-id="10ba5-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="10ba5-272">Microsoft Defender Antivirus wordt automatisch uitgeschakeld wanneer er een ander antivirusprogramma wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="10ba5-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="10ba5-273">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-273">Known Issues</span></span>
<span data-ttu-id="10ba5-274">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="10ba5-275">Juli-2020 (Platform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="10ba5-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="10ba5-276">&ensp;Versie van beveiligingsinformatieupdate: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="10ba5-277">&ensp;Uitgebracht: **28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="10ba5-278">&ensp;Platform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="10ba5-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="10ba5-279">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="10ba5-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="10ba5-280">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-281">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-281">What's new</span></span>

- <span data-ttu-id="10ba5-282">Verbeterde telemetrie voor BITS</span><span class="sxs-lookup"><span data-stu-id="10ba5-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="10ba5-283">Verbeterde validatie van Authenticode-code ondertekeningscertificaat</span><span class="sxs-lookup"><span data-stu-id="10ba5-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-284">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-284">Known Issues</span></span>
<span data-ttu-id="10ba5-285">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="10ba5-286">Juni-2020 (Platform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="10ba5-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="10ba5-287">&ensp;Versie van beveiligingsinformatieupdate: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="10ba5-288">&ensp;Uitgebracht: **22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="10ba5-289">&ensp;Platform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="10ba5-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="10ba5-290">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="10ba5-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="10ba5-291">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-292">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-292">What's new</span></span>

- <span data-ttu-id="10ba5-293">Mogelijkheid om de locatie [van de ondersteuningslogboeken op te geven](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="10ba5-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="10ba5-294">Het overslaan van een agressieve inhaalscan in de passieve modus.</span><span class="sxs-lookup"><span data-stu-id="10ba5-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="10ba5-295">Defender toestaan bij te werken op verbindingen met een datameter</span><span class="sxs-lookup"><span data-stu-id="10ba5-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="10ba5-296">Vaste prestaties afstemmen wanneer caching is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="10ba5-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="10ba5-297">Vaste registerquery</span><span class="sxs-lookup"><span data-stu-id="10ba5-297">Fixed registry query</span></span> 
- <span data-ttu-id="10ba5-298">Randomisatie van scantime in ADMX opgelost</span><span class="sxs-lookup"><span data-stu-id="10ba5-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-299">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-299">Known Issues</span></span>
<span data-ttu-id="10ba5-300">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="10ba5-301">Mei-2020 (Platform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="10ba5-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="10ba5-302">&ensp;Versie van beveiligingsinformatieupdate: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="10ba5-303">&ensp;Uitgebracht: **26 mei 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="10ba5-304">&ensp;Platform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="10ba5-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="10ba5-305">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="10ba5-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="10ba5-306">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-307">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-307">What's new</span></span>

- <span data-ttu-id="10ba5-308">Verbeterde logboekregistratie voor scangebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="10ba5-308">Improved logging for scan events</span></span>
- <span data-ttu-id="10ba5-309">Verbeterde crashafhandeling in de gebruikersmodus.</span><span class="sxs-lookup"><span data-stu-id="10ba5-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="10ba5-310">Gebeurtenistracing toegevoegd voor Tamper-beveiliging</span><span class="sxs-lookup"><span data-stu-id="10ba5-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="10ba5-311">AmSI-voorbeeldinzending opgelost</span><span class="sxs-lookup"><span data-stu-id="10ba5-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="10ba5-312">AmSI Cloud blokkeren opgelost</span><span class="sxs-lookup"><span data-stu-id="10ba5-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="10ba5-313">Installatielogboek voor beveiligingsupdates opgelost</span><span class="sxs-lookup"><span data-stu-id="10ba5-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-314">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-314">Known Issues</span></span>
<span data-ttu-id="10ba5-315">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="10ba5-316">April-2020 (Platform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="10ba5-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="10ba5-317">&ensp;Versie van beveiligingsinformatieupdate: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="10ba5-318">&ensp;Uitgebracht: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="10ba5-319">&ensp;Platform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="10ba5-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="10ba5-320">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="10ba5-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="10ba5-321">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-322">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-322">What's new</span></span>
- <span data-ttu-id="10ba5-323">Verbeteringen in WDfilter</span><span class="sxs-lookup"><span data-stu-id="10ba5-323">WDfilter improvements</span></span>
- <span data-ttu-id="10ba5-324">Meer actiebare gebeurtenisgegevens toevoegen om detectiegebeurtenissen voor surface reduction aan te vallen</span><span class="sxs-lookup"><span data-stu-id="10ba5-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="10ba5-325">Vaste versiegegevens in diagnostische gegevens en WMI</span><span class="sxs-lookup"><span data-stu-id="10ba5-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="10ba5-326">Onjuiste platformversie in gebruikersinterface na platformupdate opgelost</span><span class="sxs-lookup"><span data-stu-id="10ba5-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="10ba5-327">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="10ba5-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="10ba5-328">UEFI-scanfunctie</span><span class="sxs-lookup"><span data-stu-id="10ba5-328">UEFI scan capability</span></span>
- <span data-ttu-id="10ba5-329">Logboekregistratie uitbreiden voor updates</span><span class="sxs-lookup"><span data-stu-id="10ba5-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="10ba5-330">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-330">Known Issues</span></span>
<span data-ttu-id="10ba5-331">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="10ba5-332">Maart-2020 (Platform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="10ba5-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="10ba5-333">&ensp;Versie van beveiligingsinformatieupdate: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="10ba5-334">&ensp;Uitgebracht: **24 maart 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="10ba5-335">&ensp;Platform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="10ba5-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="10ba5-336">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="10ba5-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="10ba5-337">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="10ba5-338">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-338">What's new</span></span>

- <span data-ttu-id="10ba5-339">Optie CPU-beperking toegevoegd aan [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="10ba5-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="10ba5-340">Diagnostische mogelijkheden verbeteren</span><span class="sxs-lookup"><span data-stu-id="10ba5-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="10ba5-341">time-out voor beveiligingsinformatie verminderen (5 min)</span><span class="sxs-lookup"><span data-stu-id="10ba5-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="10ba5-342">Interne logfunctie voor AMSI-engine uitbreiden</span><span class="sxs-lookup"><span data-stu-id="10ba5-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="10ba5-343">Melding voor procesblokkering verbeteren</span><span class="sxs-lookup"><span data-stu-id="10ba5-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="10ba5-344">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-344">Known Issues</span></span>
<span data-ttu-id="10ba5-345">[**Opgelost**] Microsoft Defender Antivirus wordt bestanden overgeslagen tijdens het uitvoeren van een scan.</span><span class="sxs-lookup"><span data-stu-id="10ba5-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="10ba5-346">Februari-2020 (Platform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="10ba5-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="10ba5-347">&ensp;Versie van beveiligingsinformatieupdate: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="10ba5-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="10ba5-348">&ensp;Uitgebracht: **25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="10ba5-349">&ensp;Platform/client: **-**</span><span class="sxs-lookup"><span data-stu-id="10ba5-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="10ba5-350">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="10ba5-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="10ba5-351">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="10ba5-352">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="10ba5-353">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-353">Known Issues</span></span>
<span data-ttu-id="10ba5-354">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="10ba5-355">Januari-2020 (Platform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="10ba5-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="10ba5-356">Versie van beveiligingsinformatieupdate: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="10ba5-357">Uitgebracht: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="10ba5-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="10ba5-358">Platform/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="10ba5-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="10ba5-359">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="10ba5-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="10ba5-360">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="10ba5-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="10ba5-361">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-361">What's new</span></span>

- <span data-ttu-id="10ba5-362">BSOD opgelost in WS2016 met Exchange</span><span class="sxs-lookup"><span data-stu-id="10ba5-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="10ba5-363">Ondersteuningsplatformupdates wanneer TMP wordt omgeleid naar netwerkpad</span><span class="sxs-lookup"><span data-stu-id="10ba5-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="10ba5-364">Platform- en engineversies worden toegevoegd aan [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="10ba5-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="10ba5-365">Update voor noodhandtekeningen uitbreiden [naar passieve modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="10ba5-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="10ba5-366">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="10ba5-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="10ba5-367">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-367">Known Issues</span></span>

<span data-ttu-id="10ba5-368">[**Opgelost**] apparaten die gebruikmaken van [de moderne stand-bymodus,](/windows-hardware/design/device-experiences/modern-standby) kunnen last hebben van de Windows Defender filtert stuurprogramma, wat resulteert in een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="10ba5-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="10ba5-369">Getroffen machines worden voor de klant weergegeven als niet bijgewerkt naar het nieuwste antimalwareplatform.</span><span class="sxs-lookup"><span data-stu-id="10ba5-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="10ba5-370">Deze update is:</span><span class="sxs-lookup"><span data-stu-id="10ba5-370">This update is:</span></span>
> - <span data-ttu-id="10ba5-371">vereist door RS1-apparaten met een lagere versie van het platform ter ondersteuning van SHA2;</span><span class="sxs-lookup"><span data-stu-id="10ba5-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="10ba5-372">heeft een herstartvlag voor systemen met problemen met ophangen;</span><span class="sxs-lookup"><span data-stu-id="10ba5-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="10ba5-373">wordt opnieuw uitgebracht in april 2020 en wordt niet vervangen door nieuwere updates om toekomstige beschikbaarheid te behouden.</span><span class="sxs-lookup"><span data-stu-id="10ba5-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="10ba5-374">wordt gecategoriseerd als een update vanwege de herstartvereiste; en</span><span class="sxs-lookup"><span data-stu-id="10ba5-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="10ba5-375">wordt alleen aangeboden met [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="10ba5-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="10ba5-376">November-2019 (Platform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="10ba5-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="10ba5-377">Versie van beveiligingsinformatieupdate: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="10ba5-378">Uitgebracht: **7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="10ba5-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="10ba5-379">Platform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="10ba5-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="10ba5-380">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="10ba5-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="10ba5-381">Ondersteuningsfase: **Geen ondersteuning**</span><span class="sxs-lookup"><span data-stu-id="10ba5-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="10ba5-382">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="10ba5-382">What's new</span></span>

- <span data-ttu-id="10ba5-383">MpCmdRun-traceringsniveau opgelost</span><span class="sxs-lookup"><span data-stu-id="10ba5-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="10ba5-384">Versiegegevens van WDFilter opgelost</span><span class="sxs-lookup"><span data-stu-id="10ba5-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="10ba5-385">Meldingen verbeteren (PUA)</span><span class="sxs-lookup"><span data-stu-id="10ba5-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="10ba5-386">MRT-logboeken toevoegen om bestanden te ondersteunen</span><span class="sxs-lookup"><span data-stu-id="10ba5-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="10ba5-387">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="10ba5-387">Known Issues</span></span>
<span data-ttu-id="10ba5-388">Wanneer deze update is geïnstalleerd, moet het apparaat het jump-pakket 4.18.2001.10 gebruiken om te kunnen bijwerken naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="10ba5-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="10ba5-389">Microsoft Defender Antivirus platformondersteuning</span><span class="sxs-lookup"><span data-stu-id="10ba5-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="10ba5-390">Platform- en motorupdates worden geleverd op een maandelijkse cadans.</span><span class="sxs-lookup"><span data-stu-id="10ba5-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="10ba5-391">Als u volledig wilt worden ondersteund, blijft u op de hoogte van de meest recente platformupdates.</span><span class="sxs-lookup"><span data-stu-id="10ba5-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="10ba5-392">Onze ondersteuningsstructuur is dynamisch en verandert in twee fasen, afhankelijk van de beschikbaarheid van de nieuwste platformversie:</span><span class="sxs-lookup"><span data-stu-id="10ba5-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="10ba5-393">**Servicefase beveiligings-** en kritieke updates: wanneer u de nieuwste platformversie gebruikt, komt u in aanmerking voor zowel beveiligings- als kritieke updates voor het anti-malwareplatform.</span><span class="sxs-lookup"><span data-stu-id="10ba5-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="10ba5-394">**Technische ondersteuning (alleen) fase:** nadat een nieuwe platformversie is uitgebracht, wordt de ondersteuning voor oudere versies (N-2) beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="10ba5-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="10ba5-395">Platformversies die ouder zijn dan N-2, worden niet meer ondersteund.\*</span><span class="sxs-lookup"><span data-stu-id="10ba5-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="10ba5-396">\*Technische ondersteuning blijft beschikbaar voor upgrades van de Windows 10 releaseversie (zie Platformversie inbegrepen bij Windows 10 [releases)](#platform-version-included-with-windows-10-releases)naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="10ba5-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="10ba5-397">Tijdens de fase van technische ondersteuning (alleen) worden commercieel redelijke ondersteuningsincidenten verstrekt via Microsoft Customer Service & Support en beheerde ondersteuningsaanbiedingen van Microsoft (zoals Premier Support).</span><span class="sxs-lookup"><span data-stu-id="10ba5-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="10ba5-398">Als voor een ondersteuningsincident escalatie nodig is voor de ontwikkeling voor verdere richtlijnen, een niet-beveiligingsupdate vereist is of een beveiligingsupdate vereist, wordt klanten gevraagd een upgrade uit te voeren naar de nieuwste platformversie of een tussentijdse update (\*).</span><span class="sxs-lookup"><span data-stu-id="10ba5-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="10ba5-399">Platformversie inbegrepen bij Windows 10 releases</span><span class="sxs-lookup"><span data-stu-id="10ba5-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="10ba5-400">In de onderstaande tabel vindt u Microsoft Defender Antivirus platform- en engineversies die worden verzonden met de nieuwste Windows 10 releases:</span><span class="sxs-lookup"><span data-stu-id="10ba5-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="10ba5-401">Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="10ba5-401">Windows 10 release</span></span>  |<span data-ttu-id="10ba5-402">Platformversie</span><span class="sxs-lookup"><span data-stu-id="10ba5-402">Platform version</span></span>  |<span data-ttu-id="10ba5-403">Engine-versie</span><span class="sxs-lookup"><span data-stu-id="10ba5-403">Engine version</span></span> |<span data-ttu-id="10ba5-404">Ondersteuningsfase</span><span class="sxs-lookup"><span data-stu-id="10ba5-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="10ba5-405">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="10ba5-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="10ba5-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="10ba5-406">4.18.1909.6</span></span> |<span data-ttu-id="10ba5-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="10ba5-407">1.1.17000.2</span></span> | <span data-ttu-id="10ba5-408">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="10ba5-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="10ba5-409">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="10ba5-409">1909  (19H2)</span></span> |<span data-ttu-id="10ba5-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="10ba5-410">4.18.1902.5</span></span> |<span data-ttu-id="10ba5-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="10ba5-411">1.1.16700.3</span></span> | <span data-ttu-id="10ba5-412">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="10ba5-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="10ba5-413">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="10ba5-413">1903  (19H1)</span></span> |<span data-ttu-id="10ba5-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="10ba5-414">4.18.1902.5</span></span> |<span data-ttu-id="10ba5-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="10ba5-415">1.1.15600.4</span></span> | <span data-ttu-id="10ba5-416">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="10ba5-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="10ba5-417">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="10ba5-417">1809  (RS5)</span></span> |<span data-ttu-id="10ba5-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="10ba5-418">4.18.1807.18075</span></span> |<span data-ttu-id="10ba5-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="10ba5-419">1.1.15000.2</span></span> | <span data-ttu-id="10ba5-420">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="10ba5-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="10ba5-421">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="10ba5-421">1803  (RS4)</span></span> |<span data-ttu-id="10ba5-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="10ba5-422">4.13.17134.1</span></span> |<span data-ttu-id="10ba5-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="10ba5-423">1.1.14600.4</span></span> | <span data-ttu-id="10ba5-424">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="10ba5-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="10ba5-425">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="10ba5-425">1709  (RS3)</span></span> |<span data-ttu-id="10ba5-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="10ba5-426">4.12.16299.15</span></span> |<span data-ttu-id="10ba5-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="10ba5-427">1.1.14104.0</span></span> | <span data-ttu-id="10ba5-428">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="10ba5-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="10ba5-429">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="10ba5-429">1703  (RS2)</span></span> |<span data-ttu-id="10ba5-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="10ba5-430">4.11.15603.2</span></span> |<span data-ttu-id="10ba5-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="10ba5-431">1.1.13504.0</span></span> | <span data-ttu-id="10ba5-432">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="10ba5-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="10ba5-433">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="10ba5-433">1607 (RS1)</span></span> |<span data-ttu-id="10ba5-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="10ba5-434">4.10.14393.3683</span></span> |<span data-ttu-id="10ba5-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="10ba5-435">1.1.12805.0</span></span> | <span data-ttu-id="10ba5-436">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="10ba5-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="10ba5-437">Zie het Windows het Windows 10 voor meer informatie over [de release.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="10ba5-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="10ba5-438">Updates voor implementatie van image Servicing and Management (DISM)</span><span class="sxs-lookup"><span data-stu-id="10ba5-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="10ba5-439">U wordt aangeraden uw Windows 10 (Enterprise-, Pro- en Home-edities), Windows Server 2019 en Windows Server 2016-installatieafbeeldingen van het besturingssysteem bij te werken met de nieuwste antivirus- en antimalware-updates.</span><span class="sxs-lookup"><span data-stu-id="10ba5-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="10ba5-440">Als u de installatieafbeeldingen van uw besturingssysteem up-to-date houdt, voorkomt u een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="10ba5-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="10ba5-441">Zie Microsoft Defender update voor Windows [installatieafbeeldingen](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)van het besturingssysteem voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="10ba5-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="10ba5-442">1.1.2107.02</span><span class="sxs-lookup"><span data-stu-id="10ba5-442">1.1.2107.02</span></span></summary>

<span data-ttu-id="10ba5-443">&ensp;Pakketversie: **1.1.2107.02**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-443">&ensp;Package version: **1.1.2107.02**  </span></span>  
<span data-ttu-id="10ba5-444">&ensp;Platformversie: **4.18.2105.5** </span><span class="sxs-lookup"><span data-stu-id="10ba5-444">&ensp;Platform version: **4.18.2105.5** </span></span>  
<span data-ttu-id="10ba5-445">&ensp;Engine-versie: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="10ba5-445">&ensp;Engine version: **1.1.18300.4**</span></span>  
<span data-ttu-id="10ba5-446">&ensp;Handtekeningversie: **1.343.658.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-446">&ensp;Signature version: **1.343.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-447">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-447">Fixes</span></span>
- <span data-ttu-id="10ba5-448">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-449">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-449">Additional information</span></span>
- <span data-ttu-id="10ba5-450">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="10ba5-451">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="10ba5-451">1.1.2106.01</span></span></summary>

<span data-ttu-id="10ba5-452">&ensp;Pakketversie: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-452">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="10ba5-453">&ensp;Platformversie: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="10ba5-453">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="10ba5-454">&ensp;Engine versie: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="10ba5-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="10ba5-455">&ensp;Handtekeningversie: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-455">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-456">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-456">Fixes</span></span>
- <span data-ttu-id="10ba5-457">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-458">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-458">Additional information</span></span>
- <span data-ttu-id="10ba5-459">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="10ba5-460">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="10ba5-460">1.1.2105.01</span></span></summary>

<span data-ttu-id="10ba5-461">&ensp;Pakketversie: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-461">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="10ba5-462">&ensp;Platformversie: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="10ba5-462">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="10ba5-463">&ensp;Engine versie: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="10ba5-463">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="10ba5-464">&ensp;Handtekeningversie: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-464">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-465">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-465">Fixes</span></span>
- <span data-ttu-id="10ba5-466">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-467">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-467">Additional information</span></span>
- <span data-ttu-id="10ba5-468">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="10ba5-469">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="10ba5-469">1.1.2104.01</span></span></summary>

<span data-ttu-id="10ba5-470">&ensp;Pakketversie: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-470">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="10ba5-471">&ensp;Platformversie: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="10ba5-471">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="10ba5-472">&ensp;Engine-versie: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-472">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="10ba5-473">&ensp;Handtekeningversie: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-473">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-474">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-474">Fixes</span></span>
- <span data-ttu-id="10ba5-475">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-476">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-476">Additional information</span></span>
- <span data-ttu-id="10ba5-477">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="10ba5-478">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="10ba5-478">1.1.2103.01</span></span></summary>

<span data-ttu-id="10ba5-479">&ensp;Pakketversie: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-479">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="10ba5-480">&ensp;Platformversie: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="10ba5-480">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="10ba5-481">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="10ba5-482">&ensp;Handtekeningversie: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-482">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-483">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-483">Fixes</span></span>
- <span data-ttu-id="10ba5-484">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-485">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-485">Additional information</span></span>
- <span data-ttu-id="10ba5-486">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="10ba5-487">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="10ba5-487">1.1.2102.03</span></span></summary>

<span data-ttu-id="10ba5-488">&ensp;Pakketversie: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-488">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="10ba5-489">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="10ba5-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="10ba5-490">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-490">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="10ba5-491">&ensp;Handtekeningversie: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-491">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-492">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-492">Fixes</span></span>
- <span data-ttu-id="10ba5-493">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-494">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-494">Additional information</span></span>
- <span data-ttu-id="10ba5-495">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="10ba5-496">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="10ba5-496">1.1.2101.02</span></span></summary>

<span data-ttu-id="10ba5-497">&ensp;Pakketversie: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-497">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="10ba5-498">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="10ba5-498">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="10ba5-499">&ensp;Motorversie: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="10ba5-499">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="10ba5-500">&ensp;Handtekeningversie: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-500">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-501">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-501">Fixes</span></span>
- <span data-ttu-id="10ba5-502">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-503">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-503">Additional information</span></span>
- <span data-ttu-id="10ba5-504">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="10ba5-505">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="10ba5-505">1.1.2012.01</span></span></summary>

<span data-ttu-id="10ba5-506">&ensp;Pakketversie: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-506">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="10ba5-507">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="10ba5-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="10ba5-508">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="10ba5-509">&ensp;Handtekeningversie: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-509">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-510">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-510">Fixes</span></span>
- <span data-ttu-id="10ba5-511">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-512">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-512">Additional information</span></span>
- <span data-ttu-id="10ba5-513">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-513">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="10ba5-514">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="10ba5-514">1.1.2011.02</span></span></summary>

<span data-ttu-id="10ba5-515">&ensp;Pakketversie: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-515">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="10ba5-516">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="10ba5-516">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="10ba5-517">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="10ba5-518">&ensp;Handtekeningversie: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-518">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-519">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-519">Fixes</span></span>
- <span data-ttu-id="10ba5-520">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-521">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-521">Additional information</span></span>
- <span data-ttu-id="10ba5-522">Vernieuwde Microsoft Defender Antivirus handtekeningen</span><span class="sxs-lookup"><span data-stu-id="10ba5-522">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="10ba5-523">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="10ba5-523">1.1.2011.01</span></span></summary>

<span data-ttu-id="10ba5-524">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="10ba5-525">&ensp;Platformversie: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="10ba5-525">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="10ba5-526">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-526">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="10ba5-527">&ensp;Handtekeningversie: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-527">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-528">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-528">Fixes</span></span>
- <span data-ttu-id="10ba5-529">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-530">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-530">Additional information</span></span>
- <span data-ttu-id="10ba5-531">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-531">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="10ba5-532">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="10ba5-532">1.1.2009.10</span></span></summary>

<span data-ttu-id="10ba5-533">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="10ba5-533">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="10ba5-534">&ensp;Platformversie: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="10ba5-534">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="10ba5-535">&ensp;Motorversie: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="10ba5-535">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="10ba5-536">&ensp;Handtekeningversie: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="10ba5-536">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="10ba5-537">Fixes</span><span class="sxs-lookup"><span data-stu-id="10ba5-537">Fixes</span></span>
- <span data-ttu-id="10ba5-538">Geen</span><span class="sxs-lookup"><span data-stu-id="10ba5-538">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="10ba5-539">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="10ba5-539">Additional information</span></span>
- <span data-ttu-id="10ba5-540">Ondersteuning toegevoegd voor Windows 10 RS1- of hoger os-installatieafbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="10ba5-540">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="10ba5-541">Aanvullende bronnen</span><span class="sxs-lookup"><span data-stu-id="10ba5-541">Additional resources</span></span>

| <span data-ttu-id="10ba5-542">Artikel</span><span class="sxs-lookup"><span data-stu-id="10ba5-542">Article</span></span> | <span data-ttu-id="10ba5-543">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="10ba5-543">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="10ba5-544">Microsoft Defender-update voor Windows installatieafbeeldingen van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="10ba5-544">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="10ba5-545">Controleer antimalware-updatepakketten voor installatieafbeeldingen van uw besturingssysteem (WIM- en VHD-bestanden).</span><span class="sxs-lookup"><span data-stu-id="10ba5-545">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="10ba5-546">Ontvang Microsoft Defender Antivirus updates voor Windows 10 (Enterprise, Pro en Home editions), Windows Server 2019 en Windows Server 2016 installatieafbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="10ba5-546">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="10ba5-547">Beheren hoe beveiligingsupdates worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="10ba5-547">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="10ba5-548">Beveiligingsupdates kunnen via veel bronnen worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="10ba5-548">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="10ba5-549">Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="10ba5-549">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="10ba5-550">U kunt plannen wanneer beveiligingsupdates moeten worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="10ba5-550">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="10ba5-551">Updates beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="10ba5-551">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="10ba5-552">Als een eindpunt een update of geplande scan mist, kunt u een update forcen of scannen wanneer een gebruiker zich de volgende keer meldt.</span><span class="sxs-lookup"><span data-stu-id="10ba5-552">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="10ba5-553">Op basis van gebeurtenissen afgedwongen updates beheren</span><span class="sxs-lookup"><span data-stu-id="10ba5-553">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="10ba5-554">U kunt instellen dat beveiligingsupdates worden gedownload bij het opstarten of na bepaalde beveiligingsgebeurtenissen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="10ba5-554">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="10ba5-555">Updates beheren voor mobiele apparaten en virtuele machines (VM's)</span><span class="sxs-lookup"><span data-stu-id="10ba5-555">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="10ba5-556">U kunt instellingen opgeven, zoals of er updates moeten worden uitgevoerd op batterijvermogen, die vooral handig zijn voor mobiele apparaten en virtuele machines.</span><span class="sxs-lookup"><span data-stu-id="10ba5-556">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
