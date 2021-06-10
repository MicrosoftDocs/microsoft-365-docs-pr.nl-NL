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
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822272"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="1d959-104">Updates Microsoft Defender Antivirus en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="1d959-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="1d959-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1d959-105">**Applies to:**</span></span>

- [<span data-ttu-id="1d959-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1d959-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="1d959-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1d959-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="1d959-108">Er zijn twee soorten updates die betrekking hebben op het up-to-date Microsoft Defender Antivirus houden:</span><span class="sxs-lookup"><span data-stu-id="1d959-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="1d959-109">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="1d959-109">Security intelligence updates</span></span>
- <span data-ttu-id="1d959-110">Productupdates</span><span class="sxs-lookup"><span data-stu-id="1d959-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d959-111">Het Microsoft Defender Antivirus up-to-date houden is essentieel om ervoor te zorgen dat uw apparaten de nieuwste technologie en functies hebben die nodig zijn om te beschermen tegen nieuwe malware en aanvalstechnieken.</span><span class="sxs-lookup"><span data-stu-id="1d959-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="1d959-112">Zorg ervoor dat u uw antivirusbeveiliging bij werkt, zelfs als Microsoft Defender Antivirus actief is in [de passieve modus.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="1d959-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="1d959-113">Als u de meest recente datum van de engine, het platform en de handtekening wilt zien, gaat u naar de beveiligingsintelligentie-updates voor Microsoft Defender Antivirus [en andere Microsoft-antimalware.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="1d959-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="1d959-114">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="1d959-114">Security intelligence updates</span></span>

<span data-ttu-id="1d959-115">Microsoft Defender Antivirus gebruikt beveiliging in de cloud (ook wel de Microsoft Advanced Protection Service of KAARTEN genoemd) en downloadt regelmatig [beveiligingsinformatie-updates](cloud-protection-microsoft-defender-antivirus.md) om bescherming te bieden.</span><span class="sxs-lookup"><span data-stu-id="1d959-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="1d959-116">Updates worden uitgebracht onder de onderstaande KB-nummers:</span><span class="sxs-lookup"><span data-stu-id="1d959-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="1d959-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="1d959-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="1d959-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="1d959-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="1d959-119">Beveiliging in de cloud is altijd actief en hiervoor is een actieve verbinding met internet vereist.</span><span class="sxs-lookup"><span data-stu-id="1d959-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="1d959-120">Beveiligingsintelligentie-updates vinden plaats op een geplande cadans (configureerbaar via beleid).</span><span class="sxs-lookup"><span data-stu-id="1d959-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="1d959-121">Zie Microsoft [Cloud-beveiliging](cloud-protection-microsoft-defender-antivirus.md)gebruiken in Microsoft Defender Antivirus voor meer Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="1d959-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="1d959-122">Zie Beveiligingsinformatie-updates voor Microsoft Defender Antivirus en andere Microsoft-antimalware voor een lijst met recente [beveiligingsinformatieupdates.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="1d959-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="1d959-123">Engine-updates worden opgenomen in beveiligingsinformatie-updates en worden maandelijks uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="1d959-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="1d959-124">Productupdates</span><span class="sxs-lookup"><span data-stu-id="1d959-124">Product updates</span></span>

<span data-ttu-id="1d959-125">Microsoft Defender Antivirus vereist [maandelijkse updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (ook wel *platformupdates* genoemd) en ontvangen belangrijke functieupdates naast Windows 10 releases.</span><span class="sxs-lookup"><span data-stu-id="1d959-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="1d959-126">U kunt de distributie van updates beheren via een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="1d959-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="1d959-127">Windows Serverupdateservice (WSUS)</span><span class="sxs-lookup"><span data-stu-id="1d959-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="1d959-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1d959-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="1d959-129">De gebruikelijke methode die u gebruikt om Microsoft te implementeren en Windows te installeren op eindpunten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="1d959-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="1d959-130">Zie De bronnen voor [beveiligingsupdates Microsoft Defender Antivirus beheren voor meer informatie.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="1d959-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="1d959-131">Maandelijkse updates worden gefaseerd uitgebracht, wat resulteert in meerdere pakketten die zichtbaar zijn in [uw Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="1d959-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="1d959-132">Maandelijkse platform- en engineversies</span><span class="sxs-lookup"><span data-stu-id="1d959-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="1d959-133">Zie Update voor Windows Defender [antimalwareplatform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)voor informatie over het bijwerken of installeren van de platformupdate.</span><span class="sxs-lookup"><span data-stu-id="1d959-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="1d959-134">Al onze updates bevatten</span><span class="sxs-lookup"><span data-stu-id="1d959-134">All our updates contain</span></span> 
- <span data-ttu-id="1d959-135">prestatieverbeteringen;</span><span class="sxs-lookup"><span data-stu-id="1d959-135">performance improvements;</span></span>
- <span data-ttu-id="1d959-136">verbeteringen in de servicebaarheid; en</span><span class="sxs-lookup"><span data-stu-id="1d959-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="1d959-137">integratieverbeteringen (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="1d959-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="1d959-138">Mei-2021 (Platform: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="1d959-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="1d959-139">&ensp;Versie van beveiligingsinformatieupdate: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="1d959-140">&ensp;Uitgebracht: **4 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="1d959-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="1d959-141">&ensp;Platform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="1d959-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="1d959-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="1d959-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="1d959-143">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="1d959-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-144">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-144">What's new</span></span>
- <span data-ttu-id="1d959-145">Verbeteringen in [gedragscontrole](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="1d959-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="1d959-146">Functie [voor het filteren van meldingen](network-protection.md) voor vaste netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="1d959-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-147">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-147">Known Issues</span></span>
<span data-ttu-id="1d959-148">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1d959-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="1d959-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="1d959-150">&ensp;Versie van beveiligingsinformatieupdate: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="1d959-151">&ensp;Uitgebracht: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="1d959-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="1d959-152">&ensp;Platform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="1d959-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="1d959-153">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="1d959-154">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="1d959-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-155">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-155">What's new</span></span>
- <span data-ttu-id="1d959-156">Aanvullende logica voor gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="1d959-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="1d959-157">Verbeterde detectie van keylogger in de kernelmodus</span><span class="sxs-lookup"><span data-stu-id="1d959-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="1d959-158">Nieuwe besturingselementen toegevoegd om het geleidelijke implementatieproces voor [Microsoft Defender-updates te beheren](updates.md)</span><span class="sxs-lookup"><span data-stu-id="1d959-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-159">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-159">Known Issues</span></span>
<span data-ttu-id="1d959-160">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1d959-161">Maart-2021 (Platform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="1d959-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="1d959-162">&ensp;Versie van beveiligingsinformatieupdate: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="1d959-163">&ensp;Uitgebracht: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="1d959-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="1d959-164">&ensp;Platform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="1d959-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="1d959-165">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="1d959-166">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="1d959-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-167">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-167">What's new</span></span>

- <span data-ttu-id="1d959-168">Verbetering van de engine Gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="1d959-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="1d959-169">Uitgebreide netwerkbeperking met brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="1d959-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="1d959-170">Extra mislukte poging tot het maken van een poging tot geknoei wanneer [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="1d959-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-171">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-171">Known Issues</span></span>
<span data-ttu-id="1d959-172">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="1d959-173">Eerdere versieupdates: Alleen ondersteuning voor technische upgrade</span><span class="sxs-lookup"><span data-stu-id="1d959-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="1d959-174">Nadat een nieuwe pakketversie is uitgebracht, wordt de ondersteuning voor de vorige twee versies beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="1d959-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="1d959-175">Versies die ouder zijn dan die in deze sectie worden weergegeven, en alleen beschikbaar zijn voor ondersteuning voor technische upgrades.</span><span class="sxs-lookup"><span data-stu-id="1d959-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="1d959-176">Februari-2021 (Platform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="1d959-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="1d959-177">&ensp;Versie van beveiligingsinformatieupdate: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="1d959-178">&ensp;Uitgebracht: **9 maart 2021**</span><span class="sxs-lookup"><span data-stu-id="1d959-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="1d959-179">&ensp;Platform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="1d959-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="1d959-180">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="1d959-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="1d959-181">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-182">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-182">What's new</span></span>

- <span data-ttu-id="1d959-183">Verbeterde serviceherstel door middel [van beveiliging tegen geknoei](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="1d959-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="1d959-184">Beveiligingsbereik voor tampers uitbreiden</span><span class="sxs-lookup"><span data-stu-id="1d959-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-185">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-185">Known Issues</span></span>
<span data-ttu-id="1d959-186">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1d959-187">Januari-2021 (Platform: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="1d959-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="1d959-188">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="1d959-189">&ensp;Uitgebracht: **2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="1d959-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="1d959-190">&ensp;Platform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="1d959-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="1d959-191">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="1d959-192">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-193">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-193">What's new</span></span>

- <span data-ttu-id="1d959-194">Verbeteringen voor detectie van Shellcode-exploits</span><span class="sxs-lookup"><span data-stu-id="1d959-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="1d959-195">Meer zichtbaarheid voor pogingen tot het stelen van referenties</span><span class="sxs-lookup"><span data-stu-id="1d959-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="1d959-196">Verbeteringen in antitamperingfuncties in Microsoft Defender Antivirus services</span><span class="sxs-lookup"><span data-stu-id="1d959-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="1d959-197">Verbeterde ondersteuning voor ARM x64-emulatie</span><span class="sxs-lookup"><span data-stu-id="1d959-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="1d959-198">Oplossing: EDR Blokkeermelding blijft in de bedreigingsgeschiedenis staan nadat realtimebeveiliging eerste detectie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="1d959-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-199">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-199">Known Issues</span></span>
<span data-ttu-id="1d959-200">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1d959-201">November-2020 (Platform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="1d959-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="1d959-202">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="1d959-203">&ensp;Uitgebracht: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="1d959-204">&ensp;Platform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="1d959-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="1d959-205">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="1d959-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="1d959-206">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-207">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-207">What's new</span></span>

- <span data-ttu-id="1d959-208">Verbeterde [ondersteuning voor SmartScreen-statusregistratie](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="1d959-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-209">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-209">Known Issues</span></span>
<span data-ttu-id="1d959-210">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1d959-211">Oktober-2020 (Platform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="1d959-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="1d959-212">&ensp;Versie van beveiligingsinformatieupdate: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="1d959-213">&ensp;Uitgebracht: **29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="1d959-214">&ensp;Platform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="1d959-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="1d959-215">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="1d959-216">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-217">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-217">What's new</span></span>

- <span data-ttu-id="1d959-218">Nieuwe beschrijvingen voor categorieën met speciale bedreigingen</span><span class="sxs-lookup"><span data-stu-id="1d959-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="1d959-219">Verbeterde emulatiemogelijkheden</span><span class="sxs-lookup"><span data-stu-id="1d959-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="1d959-220">Verbeterde mogelijkheden voor het toestaan/blokkeren van hostadressen</span><span class="sxs-lookup"><span data-stu-id="1d959-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="1d959-221">Nieuwe optie in Defender CSP om het samenvoegen van lokale gebruikersuitsluitingen te negeren</span><span class="sxs-lookup"><span data-stu-id="1d959-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-222">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-222">Known Issues</span></span>

<span data-ttu-id="1d959-223">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="1d959-224">September-2020 (Platform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="1d959-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="1d959-225">&ensp;Versie van beveiligingsinformatieupdate: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="1d959-226">&ensp;Uitgebracht: **1 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="1d959-227">&ensp;Platform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="1d959-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="1d959-228">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="1d959-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="1d959-229">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-230">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-230">What's new</span></span>

- <span data-ttu-id="1d959-231">Beheerdersmachtigingen zijn vereist om bestanden in quarantaine te herstellen</span><span class="sxs-lookup"><span data-stu-id="1d959-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="1d959-232">XML-opgemaakte gebeurtenissen worden nu ondersteund</span><span class="sxs-lookup"><span data-stu-id="1d959-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="1d959-233">CSP-ondersteuning voor het negeren van uitsluitings samenvoegen</span><span class="sxs-lookup"><span data-stu-id="1d959-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="1d959-234">Nieuwe beheerinterfaces voor:</span><span class="sxs-lookup"><span data-stu-id="1d959-234">New management interfaces for:</span></span>
   - <span data-ttu-id="1d959-235">UDP-inspectie</span><span class="sxs-lookup"><span data-stu-id="1d959-235">UDP Inspection</span></span>
   - <span data-ttu-id="1d959-236">Netwerkbeveiliging op Server 2019</span><span class="sxs-lookup"><span data-stu-id="1d959-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="1d959-237">IP-adresuitsluitingen voor netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="1d959-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="1d959-238">Verbeterde zichtbaarheid van TPM-metingen</span><span class="sxs-lookup"><span data-stu-id="1d959-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="1d959-239">Verbeterde Office VBA-module scannen</span><span class="sxs-lookup"><span data-stu-id="1d959-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-240">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-240">Known Issues</span></span>

<span data-ttu-id="1d959-241">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="1d959-242">Augustus-2020 (Platform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="1d959-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="1d959-243">&ensp;Versie van beveiligingsinformatieupdate: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="1d959-244">&ensp;Uitgebracht: **27 augustus 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="1d959-245">&ensp;Platform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="1d959-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="1d959-246">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="1d959-247">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="1d959-248">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-248">What's new</span></span>

- <span data-ttu-id="1d959-249">Meer telemetriegebeurtenissen toevoegen</span><span class="sxs-lookup"><span data-stu-id="1d959-249">Add more telemetry events</span></span>
- <span data-ttu-id="1d959-250">Verbeterde telemetrie scangebeurtenis</span><span class="sxs-lookup"><span data-stu-id="1d959-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="1d959-251">Verbeterde gedragscontrole voor geheugenscans</span><span class="sxs-lookup"><span data-stu-id="1d959-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="1d959-252">Verbeterde macrostreams scannen</span><span class="sxs-lookup"><span data-stu-id="1d959-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="1d959-253">Toegevoegd `AMRunningMode` aan Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="1d959-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="1d959-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wordt genegeerd.</span><span class="sxs-lookup"><span data-stu-id="1d959-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="1d959-255">Microsoft Defender Antivirus wordt automatisch uitgeschakeld wanneer er een ander antivirusprogramma wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="1d959-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="1d959-256">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-256">Known Issues</span></span>
<span data-ttu-id="1d959-257">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="1d959-258">Juli-2020 (Platform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="1d959-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="1d959-259">&ensp;Versie van beveiligingsinformatieupdate: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="1d959-260">&ensp;Uitgebracht: **28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="1d959-261">&ensp;Platform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="1d959-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="1d959-262">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="1d959-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="1d959-263">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-264">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-264">What's new</span></span>

- <span data-ttu-id="1d959-265">Verbeterde telemetrie voor BITS</span><span class="sxs-lookup"><span data-stu-id="1d959-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="1d959-266">Verbeterde validatie van Authenticode-code ondertekeningscertificaat</span><span class="sxs-lookup"><span data-stu-id="1d959-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-267">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-267">Known Issues</span></span>
<span data-ttu-id="1d959-268">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="1d959-269">Juni-2020 (Platform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="1d959-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="1d959-270">&ensp;Versie van beveiligingsinformatieupdate: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="1d959-271">&ensp;Uitgebracht: **22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="1d959-272">&ensp;Platform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="1d959-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="1d959-273">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="1d959-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="1d959-274">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-275">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-275">What's new</span></span>

- <span data-ttu-id="1d959-276">Mogelijkheid om de locatie [van de ondersteuningslogboeken op te geven](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="1d959-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="1d959-277">Het overslaan van een agressieve inhaalscan in de passieve modus.</span><span class="sxs-lookup"><span data-stu-id="1d959-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="1d959-278">Defender toestaan bij te werken op verbindingen met een datameter</span><span class="sxs-lookup"><span data-stu-id="1d959-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="1d959-279">Vaste prestaties afstemmen wanneer caching is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="1d959-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="1d959-280">Vaste registerquery</span><span class="sxs-lookup"><span data-stu-id="1d959-280">Fixed registry query</span></span> 
- <span data-ttu-id="1d959-281">Randomisatie van scantime in ADMX opgelost</span><span class="sxs-lookup"><span data-stu-id="1d959-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-282">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-282">Known Issues</span></span>
<span data-ttu-id="1d959-283">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="1d959-284">Mei-2020 (Platform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="1d959-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="1d959-285">&ensp;Versie van beveiligingsinformatieupdate: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="1d959-286">&ensp;Uitgebracht: **26 mei 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="1d959-287">&ensp;Platform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="1d959-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="1d959-288">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="1d959-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="1d959-289">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-290">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-290">What's new</span></span>

- <span data-ttu-id="1d959-291">Verbeterde logboekregistratie voor scangebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="1d959-291">Improved logging for scan events</span></span>
- <span data-ttu-id="1d959-292">Verbeterde crashafhandeling in de gebruikersmodus.</span><span class="sxs-lookup"><span data-stu-id="1d959-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="1d959-293">Gebeurtenistracing toegevoegd voor Tamper-beveiliging</span><span class="sxs-lookup"><span data-stu-id="1d959-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="1d959-294">AmSI-voorbeeldinzending opgelost</span><span class="sxs-lookup"><span data-stu-id="1d959-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="1d959-295">AmSI Cloud blokkeren opgelost</span><span class="sxs-lookup"><span data-stu-id="1d959-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="1d959-296">Installatielogboek voor beveiligingsupdates opgelost</span><span class="sxs-lookup"><span data-stu-id="1d959-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-297">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-297">Known Issues</span></span>
<span data-ttu-id="1d959-298">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="1d959-299">April-2020 (Platform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="1d959-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="1d959-300">&ensp;Versie van beveiligingsinformatieupdate: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="1d959-301">&ensp;Uitgebracht: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="1d959-302">&ensp;Platform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="1d959-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="1d959-303">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="1d959-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="1d959-304">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-305">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-305">What's new</span></span>
- <span data-ttu-id="1d959-306">Verbeteringen in WDfilter</span><span class="sxs-lookup"><span data-stu-id="1d959-306">WDfilter improvements</span></span>
- <span data-ttu-id="1d959-307">Meer actiebare gebeurtenisgegevens toevoegen om detectiegebeurtenissen voor surface reduction aan te vallen</span><span class="sxs-lookup"><span data-stu-id="1d959-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="1d959-308">Vaste versiegegevens in diagnostische gegevens en WMI</span><span class="sxs-lookup"><span data-stu-id="1d959-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="1d959-309">Onjuiste platformversie in gebruikersinterface na platformupdate opgelost</span><span class="sxs-lookup"><span data-stu-id="1d959-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="1d959-310">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="1d959-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="1d959-311">UEFI-scanfunctie</span><span class="sxs-lookup"><span data-stu-id="1d959-311">UEFI scan capability</span></span>
- <span data-ttu-id="1d959-312">Logboekregistratie uitbreiden voor updates</span><span class="sxs-lookup"><span data-stu-id="1d959-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="1d959-313">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-313">Known Issues</span></span>
<span data-ttu-id="1d959-314">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="1d959-315">Maart-2020 (Platform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="1d959-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="1d959-316">&ensp;Versie van beveiligingsinformatieupdate: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="1d959-317">&ensp;Uitgebracht: **24 maart 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="1d959-318">&ensp;Platform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="1d959-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="1d959-319">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="1d959-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="1d959-320">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="1d959-321">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-321">What's new</span></span>

- <span data-ttu-id="1d959-322">Optie CPU-beperking toegevoegd aan [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1d959-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="1d959-323">Diagnostische mogelijkheden verbeteren</span><span class="sxs-lookup"><span data-stu-id="1d959-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="1d959-324">time-out voor beveiligingsinformatie verminderen (5 min)</span><span class="sxs-lookup"><span data-stu-id="1d959-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="1d959-325">Interne logfunctie voor AMSI-engine uitbreiden</span><span class="sxs-lookup"><span data-stu-id="1d959-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="1d959-326">Melding voor procesblokkering verbeteren</span><span class="sxs-lookup"><span data-stu-id="1d959-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="1d959-327">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-327">Known Issues</span></span>
<span data-ttu-id="1d959-328">[**Opgelost**] Microsoft Defender Antivirus wordt bestanden overgeslagen tijdens het uitvoeren van een scan.</span><span class="sxs-lookup"><span data-stu-id="1d959-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="1d959-329">Februari-2020 (Platform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="1d959-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="1d959-330">&ensp;Versie van beveiligingsinformatieupdate: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="1d959-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="1d959-331">&ensp;Uitgebracht: **25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="1d959-332">&ensp;Platform/client: **-**</span><span class="sxs-lookup"><span data-stu-id="1d959-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="1d959-333">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="1d959-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="1d959-334">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="1d959-335">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="1d959-336">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-336">Known Issues</span></span>
<span data-ttu-id="1d959-337">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="1d959-338">Januari-2020 (Platform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="1d959-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="1d959-339">Versie van beveiligingsinformatieupdate: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="1d959-340">Uitgebracht: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="1d959-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="1d959-341">Platform/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="1d959-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="1d959-342">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="1d959-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="1d959-343">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="1d959-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="1d959-344">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-344">What's new</span></span>

- <span data-ttu-id="1d959-345">BSOD opgelost in WS2016 met Exchange</span><span class="sxs-lookup"><span data-stu-id="1d959-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="1d959-346">Ondersteuningsplatformupdates wanneer TMP wordt omgeleid naar netwerkpad</span><span class="sxs-lookup"><span data-stu-id="1d959-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="1d959-347">Platform- en engineversies worden toegevoegd aan [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="1d959-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="1d959-348">Update voor noodhandtekeningen uitbreiden [naar passieve modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="1d959-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="1d959-349">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="1d959-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="1d959-350">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-350">Known Issues</span></span>

<span data-ttu-id="1d959-351">[**Opgelost**] apparaten die gebruikmaken van [de moderne stand-bymodus,](/windows-hardware/design/device-experiences/modern-standby) kunnen last hebben van de Windows Defender filtert stuurprogramma, wat resulteert in een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="1d959-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="1d959-352">Getroffen machines worden voor de klant weergegeven als niet bijgewerkt naar het nieuwste antimalwareplatform.</span><span class="sxs-lookup"><span data-stu-id="1d959-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="1d959-353">Deze update is:</span><span class="sxs-lookup"><span data-stu-id="1d959-353">This update is:</span></span>
> - <span data-ttu-id="1d959-354">vereist door RS1-apparaten met een lagere versie van het platform ter ondersteuning van SHA2;</span><span class="sxs-lookup"><span data-stu-id="1d959-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="1d959-355">heeft een herstartvlag voor systemen met problemen met ophangen;</span><span class="sxs-lookup"><span data-stu-id="1d959-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="1d959-356">wordt opnieuw uitgebracht in april 2020 en wordt niet vervangen door nieuwere updates om toekomstige beschikbaarheid te behouden.</span><span class="sxs-lookup"><span data-stu-id="1d959-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="1d959-357">wordt gecategoriseerd als een update vanwege de herstartvereiste; en</span><span class="sxs-lookup"><span data-stu-id="1d959-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="1d959-358">wordt alleen aangeboden met [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="1d959-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="1d959-359">November-2019 (Platform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="1d959-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="1d959-360">Versie van beveiligingsinformatieupdate: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="1d959-361">Uitgebracht: **7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="1d959-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="1d959-362">Platform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="1d959-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="1d959-363">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="1d959-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="1d959-364">Ondersteuningsfase: **Geen ondersteuning**</span><span class="sxs-lookup"><span data-stu-id="1d959-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="1d959-365">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="1d959-365">What's new</span></span>

- <span data-ttu-id="1d959-366">MpCmdRun-traceringsniveau opgelost</span><span class="sxs-lookup"><span data-stu-id="1d959-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="1d959-367">Versiegegevens van WDFilter opgelost</span><span class="sxs-lookup"><span data-stu-id="1d959-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="1d959-368">Meldingen verbeteren (PUA)</span><span class="sxs-lookup"><span data-stu-id="1d959-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="1d959-369">MRT-logboeken toevoegen om bestanden te ondersteunen</span><span class="sxs-lookup"><span data-stu-id="1d959-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="1d959-370">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="1d959-370">Known Issues</span></span>
<span data-ttu-id="1d959-371">Wanneer deze update is geïnstalleerd, moet het apparaat het jump-pakket 4.18.2001.10 gebruiken om te kunnen bijwerken naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="1d959-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="1d959-372">Microsoft Defender Antivirus platformondersteuning</span><span class="sxs-lookup"><span data-stu-id="1d959-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="1d959-373">Platform- en motorupdates worden geleverd op een maandelijkse cadans.</span><span class="sxs-lookup"><span data-stu-id="1d959-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="1d959-374">Als u volledig wilt worden ondersteund, blijft u op de hoogte van de meest recente platformupdates.</span><span class="sxs-lookup"><span data-stu-id="1d959-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="1d959-375">Onze ondersteuningsstructuur is dynamisch en verandert in twee fasen, afhankelijk van de beschikbaarheid van de nieuwste platformversie:</span><span class="sxs-lookup"><span data-stu-id="1d959-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="1d959-376">**Servicefase beveiligings-** en kritieke updates: wanneer u de nieuwste platformversie gebruikt, komt u in aanmerking voor zowel beveiligings- als kritieke updates voor het anti-malwareplatform.</span><span class="sxs-lookup"><span data-stu-id="1d959-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="1d959-377">**Technische ondersteuning (alleen) fase:** nadat een nieuwe platformversie is uitgebracht, wordt de ondersteuning voor oudere versies (N-2) beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="1d959-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="1d959-378">Platformversies die ouder zijn dan N-2, worden niet meer ondersteund.\*</span><span class="sxs-lookup"><span data-stu-id="1d959-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="1d959-379">\*Technische ondersteuning blijft beschikbaar voor upgrades van de Windows 10 releaseversie (zie Platformversie inbegrepen bij Windows 10 [releases)](#platform-version-included-with-windows-10-releases)naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="1d959-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="1d959-380">Tijdens de fase van technische ondersteuning (alleen) worden commercieel redelijke ondersteuningsincidenten verstrekt via Microsoft Customer Service & Support en beheerde ondersteuningsaanbiedingen van Microsoft (zoals Premier Support).</span><span class="sxs-lookup"><span data-stu-id="1d959-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="1d959-381">Als voor een ondersteuningsincident escalatie nodig is voor de ontwikkeling voor verdere richtlijnen, een niet-beveiligingsupdate vereist is of een beveiligingsupdate vereist, wordt klanten gevraagd een upgrade uit te voeren naar de nieuwste platformversie of een tussentijdse update (\*).</span><span class="sxs-lookup"><span data-stu-id="1d959-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="1d959-382">Platformversie inbegrepen bij Windows 10 releases</span><span class="sxs-lookup"><span data-stu-id="1d959-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="1d959-383">In de onderstaande tabel vindt u Microsoft Defender Antivirus platform- en engineversies die worden verzonden met de nieuwste Windows 10 releases:</span><span class="sxs-lookup"><span data-stu-id="1d959-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="1d959-384">Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="1d959-384">Windows 10 release</span></span>  |<span data-ttu-id="1d959-385">Platformversie</span><span class="sxs-lookup"><span data-stu-id="1d959-385">Platform version</span></span>  |<span data-ttu-id="1d959-386">Engine-versie</span><span class="sxs-lookup"><span data-stu-id="1d959-386">Engine version</span></span> |<span data-ttu-id="1d959-387">Ondersteuningsfase</span><span class="sxs-lookup"><span data-stu-id="1d959-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="1d959-388">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="1d959-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="1d959-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="1d959-389">4.18.1909.6</span></span> |<span data-ttu-id="1d959-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="1d959-390">1.1.17000.2</span></span> | <span data-ttu-id="1d959-391">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="1d959-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1d959-392">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="1d959-392">1909  (19H2)</span></span> |<span data-ttu-id="1d959-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="1d959-393">4.18.1902.5</span></span> |<span data-ttu-id="1d959-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="1d959-394">1.1.16700.3</span></span> | <span data-ttu-id="1d959-395">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="1d959-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1d959-396">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="1d959-396">1903  (19H1)</span></span> |<span data-ttu-id="1d959-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="1d959-397">4.18.1902.5</span></span> |<span data-ttu-id="1d959-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="1d959-398">1.1.15600.4</span></span> | <span data-ttu-id="1d959-399">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="1d959-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1d959-400">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="1d959-400">1809  (RS5)</span></span> |<span data-ttu-id="1d959-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="1d959-401">4.18.1807.18075</span></span> |<span data-ttu-id="1d959-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="1d959-402">1.1.15000.2</span></span> | <span data-ttu-id="1d959-403">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="1d959-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1d959-404">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="1d959-404">1803  (RS4)</span></span> |<span data-ttu-id="1d959-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="1d959-405">4.13.17134.1</span></span> |<span data-ttu-id="1d959-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="1d959-406">1.1.14600.4</span></span> | <span data-ttu-id="1d959-407">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="1d959-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1d959-408">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="1d959-408">1709  (RS3)</span></span> |<span data-ttu-id="1d959-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="1d959-409">4.12.16299.15</span></span> |<span data-ttu-id="1d959-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="1d959-410">1.1.14104.0</span></span> | <span data-ttu-id="1d959-411">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="1d959-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1d959-412">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="1d959-412">1703  (RS2)</span></span> |<span data-ttu-id="1d959-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="1d959-413">4.11.15603.2</span></span> |<span data-ttu-id="1d959-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="1d959-414">1.1.13504.0</span></span> | <span data-ttu-id="1d959-415">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="1d959-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="1d959-416">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="1d959-416">1607 (RS1)</span></span> |<span data-ttu-id="1d959-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="1d959-417">4.10.14393.3683</span></span> |<span data-ttu-id="1d959-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="1d959-418">1.1.12805.0</span></span> | <span data-ttu-id="1d959-419">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="1d959-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="1d959-420">Zie het Windows het Windows 10 voor meer informatie over [de release.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="1d959-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="1d959-421">Updates voor implementatie van image Servicing and Management (DISM)</span><span class="sxs-lookup"><span data-stu-id="1d959-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="1d959-422">U wordt aangeraden uw Windows 10 (Enterprise-, Pro- en Home-edities), Windows Server 2019 en Windows Server 2016-installatieafbeeldingen van het besturingssysteem bij te werken met de nieuwste antivirus- en antimalware-updates.</span><span class="sxs-lookup"><span data-stu-id="1d959-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="1d959-423">Als u de installatieafbeeldingen van uw besturingssysteem up-to-date houdt, voorkomt u een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="1d959-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="1d959-424">Zie Microsoft Defender update voor Windows [installatieafbeeldingen](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)van het besturingssysteem voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1d959-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="1d959-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="1d959-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="1d959-426">&ensp;Pakketversie: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="1d959-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="1d959-427">&ensp;Platformversie: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="1d959-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="1d959-428">&ensp;Engine versie: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="1d959-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="1d959-429">&ensp;Handtekeningversie: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1d959-430">Fixes</span><span class="sxs-lookup"><span data-stu-id="1d959-430">Fixes</span></span>
- <span data-ttu-id="1d959-431">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1d959-432">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="1d959-432">Additional information</span></span>
- <span data-ttu-id="1d959-433">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1d959-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="1d959-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="1d959-435">&ensp;Pakketversie: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="1d959-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="1d959-436">&ensp;Platformversie: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="1d959-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="1d959-437">&ensp;Engine versie: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="1d959-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="1d959-438">&ensp;Handtekeningversie: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1d959-439">Fixes</span><span class="sxs-lookup"><span data-stu-id="1d959-439">Fixes</span></span>
- <span data-ttu-id="1d959-440">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1d959-441">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="1d959-441">Additional information</span></span>
- <span data-ttu-id="1d959-442">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1d959-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="1d959-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="1d959-444">&ensp;Pakketversie: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="1d959-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="1d959-445">&ensp;Platformversie: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="1d959-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="1d959-446">&ensp;Engine-versie: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="1d959-447">&ensp;Handtekeningversie: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1d959-448">Fixes</span><span class="sxs-lookup"><span data-stu-id="1d959-448">Fixes</span></span>
- <span data-ttu-id="1d959-449">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1d959-450">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="1d959-450">Additional information</span></span>
- <span data-ttu-id="1d959-451">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1d959-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="1d959-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="1d959-453">&ensp;Pakketversie: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="1d959-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="1d959-454">&ensp;Platformversie: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="1d959-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="1d959-455">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="1d959-456">&ensp;Handtekeningversie: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1d959-457">Fixes</span><span class="sxs-lookup"><span data-stu-id="1d959-457">Fixes</span></span>
- <span data-ttu-id="1d959-458">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1d959-459">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="1d959-459">Additional information</span></span>
- <span data-ttu-id="1d959-460">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1d959-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="1d959-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="1d959-462">&ensp;Pakketversie: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="1d959-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="1d959-463">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="1d959-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="1d959-464">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="1d959-465">&ensp;Handtekeningversie: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1d959-466">Fixes</span><span class="sxs-lookup"><span data-stu-id="1d959-466">Fixes</span></span>
- <span data-ttu-id="1d959-467">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1d959-468">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="1d959-468">Additional information</span></span>
- <span data-ttu-id="1d959-469">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1d959-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="1d959-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="1d959-471">&ensp;Pakketversie: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="1d959-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="1d959-472">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="1d959-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="1d959-473">&ensp;Motorversie: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="1d959-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="1d959-474">&ensp;Handtekeningversie: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1d959-475">Fixes</span><span class="sxs-lookup"><span data-stu-id="1d959-475">Fixes</span></span>
- <span data-ttu-id="1d959-476">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1d959-477">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="1d959-477">Additional information</span></span>
- <span data-ttu-id="1d959-478">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1d959-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="1d959-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="1d959-480">&ensp;Pakketversie: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="1d959-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="1d959-481">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="1d959-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="1d959-482">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="1d959-483">&ensp;Handtekeningversie: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1d959-484">Fixes</span><span class="sxs-lookup"><span data-stu-id="1d959-484">Fixes</span></span>
- <span data-ttu-id="1d959-485">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1d959-486">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="1d959-486">Additional information</span></span>
- <span data-ttu-id="1d959-487">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1d959-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="1d959-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="1d959-489">&ensp;Pakketversie: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="1d959-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="1d959-490">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="1d959-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="1d959-491">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="1d959-492">&ensp;Handtekeningversie: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1d959-493">Fixes</span><span class="sxs-lookup"><span data-stu-id="1d959-493">Fixes</span></span>
- <span data-ttu-id="1d959-494">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1d959-495">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="1d959-495">Additional information</span></span>
- <span data-ttu-id="1d959-496">Vernieuwde Microsoft Defender Antivirus handtekeningen</span><span class="sxs-lookup"><span data-stu-id="1d959-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1d959-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="1d959-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="1d959-498">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="1d959-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="1d959-499">&ensp;Platformversie: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="1d959-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="1d959-500">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="1d959-501">&ensp;Handtekeningversie: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1d959-502">Fixes</span><span class="sxs-lookup"><span data-stu-id="1d959-502">Fixes</span></span>
- <span data-ttu-id="1d959-503">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1d959-504">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="1d959-504">Additional information</span></span>
- <span data-ttu-id="1d959-505">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="1d959-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="1d959-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="1d959-507">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="1d959-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="1d959-508">&ensp;Platformversie: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="1d959-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="1d959-509">&ensp;Motorversie: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="1d959-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="1d959-510">&ensp;Handtekeningversie: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="1d959-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="1d959-511">Fixes</span><span class="sxs-lookup"><span data-stu-id="1d959-511">Fixes</span></span>
- <span data-ttu-id="1d959-512">Geen</span><span class="sxs-lookup"><span data-stu-id="1d959-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="1d959-513">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="1d959-513">Additional information</span></span>
- <span data-ttu-id="1d959-514">Ondersteuning toegevoegd voor Windows 10 RS1- of hoger os-installatieafbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="1d959-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="1d959-515">Aanvullende bronnen</span><span class="sxs-lookup"><span data-stu-id="1d959-515">Additional resources</span></span>

| <span data-ttu-id="1d959-516">Artikel</span><span class="sxs-lookup"><span data-stu-id="1d959-516">Article</span></span> | <span data-ttu-id="1d959-517">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1d959-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="1d959-518">Microsoft Defender-update voor Windows installatieafbeeldingen van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="1d959-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="1d959-519">Controleer antimalware-updatepakketten voor installatieafbeeldingen van uw besturingssysteem (WIM- en VHD-bestanden).</span><span class="sxs-lookup"><span data-stu-id="1d959-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="1d959-520">Ontvang Microsoft Defender Antivirus updates voor Windows 10 (Enterprise, Pro en Home editions), Windows Server 2019 en Windows Server 2016 installatieafbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="1d959-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="1d959-521">Beheren hoe beveiligingsupdates worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="1d959-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="1d959-522">Beveiligingsupdates kunnen via veel bronnen worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="1d959-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="1d959-523">Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="1d959-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="1d959-524">U kunt plannen wanneer beveiligingsupdates moeten worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="1d959-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="1d959-525">Updates beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="1d959-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="1d959-526">Als een eindpunt een update of geplande scan mist, kunt u een update forcen of scannen wanneer een gebruiker zich de volgende keer meldt.</span><span class="sxs-lookup"><span data-stu-id="1d959-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="1d959-527">Op basis van gebeurtenissen afgedwongen updates beheren</span><span class="sxs-lookup"><span data-stu-id="1d959-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="1d959-528">U kunt instellen dat beveiligingsupdates worden gedownload bij het opstarten of na bepaalde beveiligingsgebeurtenissen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="1d959-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="1d959-529">Updates beheren voor mobiele apparaten en virtuele machines (VM's)</span><span class="sxs-lookup"><span data-stu-id="1d959-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="1d959-530">U kunt instellingen opgeven, zoals of er updates moeten worden uitgevoerd op batterijvermogen, die vooral handig zijn voor mobiele apparaten en virtuele machines.</span><span class="sxs-lookup"><span data-stu-id="1d959-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
