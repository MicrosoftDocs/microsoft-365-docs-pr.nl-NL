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
ms.date: 05/10/2021
ms.openlocfilehash: 5b599e9d5a5c3d098033af1f1df96ee9f26025ee
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52312010"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="ccc55-104">Updates Microsoft Defender Antivirus en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="ccc55-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="ccc55-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ccc55-105">**Applies to:**</span></span>

- [<span data-ttu-id="ccc55-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="ccc55-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="ccc55-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="ccc55-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="ccc55-108">Er zijn twee soorten updates die betrekking hebben op het up-to-date Microsoft Defender Antivirus houden:</span><span class="sxs-lookup"><span data-stu-id="ccc55-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="ccc55-109">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="ccc55-109">Security intelligence updates</span></span>
- <span data-ttu-id="ccc55-110">Productupdates</span><span class="sxs-lookup"><span data-stu-id="ccc55-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccc55-111">Het Microsoft Defender Antivirus up-to-date houden is essentieel om ervoor te zorgen dat uw apparaten de nieuwste technologie en functies hebben die nodig zijn om te beschermen tegen nieuwe malware en aanvalstechnieken.</span><span class="sxs-lookup"><span data-stu-id="ccc55-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="ccc55-112">Zorg ervoor dat u uw antivirusbeveiliging bij werkt, zelfs als Microsoft Defender Antivirus actief is in [de passieve modus.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ccc55-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="ccc55-113">Als u de meest recente datum van de engine, het platform en de handtekening wilt zien, gaat u naar de beveiligingsintelligentie-updates voor Microsoft Defender Antivirus [en andere Microsoft-antimalware.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ccc55-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="ccc55-114">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="ccc55-114">Security intelligence updates</span></span>

<span data-ttu-id="ccc55-115">Microsoft Defender Antivirus gebruikt beveiliging in de cloud (ook wel de Microsoft Advanced Protection Service of KAARTEN genoemd) en downloadt regelmatig [beveiligingsinformatie-updates](cloud-protection-microsoft-defender-antivirus.md) om bescherming te bieden.</span><span class="sxs-lookup"><span data-stu-id="ccc55-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="ccc55-116">Updates worden uitgebracht onder de onderstaande KB-nummers:</span><span class="sxs-lookup"><span data-stu-id="ccc55-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="ccc55-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="ccc55-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="ccc55-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="ccc55-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="ccc55-119">Beveiliging in de cloud is altijd actief en hiervoor is een actieve verbinding met internet vereist.</span><span class="sxs-lookup"><span data-stu-id="ccc55-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="ccc55-120">Beveiligingsintelligentie-updates vinden plaats op een geplande cadans (configureerbaar via beleid).</span><span class="sxs-lookup"><span data-stu-id="ccc55-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="ccc55-121">Zie Microsoft [Cloud-beveiliging](cloud-protection-microsoft-defender-antivirus.md)gebruiken in Microsoft Defender Antivirus voor meer Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="ccc55-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="ccc55-122">Zie Beveiligingsinformatie-updates voor Microsoft Defender Antivirus en andere Microsoft-antimalware voor een lijst met recente [beveiligingsinformatieupdates.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ccc55-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="ccc55-123">Engine-updates worden opgenomen in beveiligingsinformatie-updates en worden maandelijks uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="ccc55-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="ccc55-124">Productupdates</span><span class="sxs-lookup"><span data-stu-id="ccc55-124">Product updates</span></span>

<span data-ttu-id="ccc55-125">Microsoft Defender Antivirus vereist [maandelijkse updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (ook wel *platformupdates* genoemd) en ontvangen belangrijke functieupdates naast Windows 10 releases.</span><span class="sxs-lookup"><span data-stu-id="ccc55-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="ccc55-126">U kunt de distributie van updates beheren via een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="ccc55-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="ccc55-127">Windows Serverupdateservice (WSUS)</span><span class="sxs-lookup"><span data-stu-id="ccc55-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="ccc55-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ccc55-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="ccc55-129">De gebruikelijke methode die u gebruikt om Microsoft te implementeren en Windows te installeren op eindpunten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="ccc55-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="ccc55-130">Zie De bronnen voor [beveiligingsupdates Microsoft Defender Antivirus beheren voor meer informatie.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="ccc55-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="ccc55-131">Maandelijkse updates worden gefaseerd uitgebracht, wat resulteert in meerdere pakketten die zichtbaar zijn in [uw Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="ccc55-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="ccc55-132">Maandelijkse platform- en engineversies</span><span class="sxs-lookup"><span data-stu-id="ccc55-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="ccc55-133">Zie Update voor Windows Defender [antimalwareplatform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)voor informatie over het bijwerken of installeren van de platformupdate.</span><span class="sxs-lookup"><span data-stu-id="ccc55-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="ccc55-134">Al onze updates bevatten</span><span class="sxs-lookup"><span data-stu-id="ccc55-134">All our updates contain</span></span> 
- <span data-ttu-id="ccc55-135">prestatieverbeteringen;</span><span class="sxs-lookup"><span data-stu-id="ccc55-135">performance improvements;</span></span>
- <span data-ttu-id="ccc55-136">verbeteringen in de servicebaarheid; en</span><span class="sxs-lookup"><span data-stu-id="ccc55-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="ccc55-137">integratieverbeteringen (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="ccc55-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="ccc55-138">April-2021 (Platform: 4.18.2104.9 | Engine: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="ccc55-138">April-2021 (Platform: 4.18.2104.9 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="ccc55-139">&ensp;Versie van beveiligingsinformatieupdate: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="ccc55-140">&ensp;Uitgebracht: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="ccc55-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="ccc55-141">&ensp;Platform: **4.18.2104.9**</span><span class="sxs-lookup"><span data-stu-id="ccc55-141">&ensp;Platform: **4.18.2104.9**</span></span>  
<span data-ttu-id="ccc55-142">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="ccc55-143">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="ccc55-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-144">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-144">What's new</span></span>
- <span data-ttu-id="ccc55-145">Aanvullende logica voor gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="ccc55-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="ccc55-146">Verbeterde detectie van keylogger in de kernelmodus</span><span class="sxs-lookup"><span data-stu-id="ccc55-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-147">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-147">Known Issues</span></span>
<span data-ttu-id="ccc55-148">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ccc55-149">Maart-2021 (Platform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="ccc55-149">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="ccc55-150">&ensp;Versie van beveiligingsinformatieupdate: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="ccc55-151">&ensp;Uitgebracht: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="ccc55-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="ccc55-152">&ensp;Platform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="ccc55-152">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="ccc55-153">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="ccc55-154">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="ccc55-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-155">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-155">What's new</span></span>

- <span data-ttu-id="ccc55-156">Verbetering van de engine Gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="ccc55-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="ccc55-157">Uitgebreide netwerkbeperking met brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="ccc55-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="ccc55-158">Extra mislukte poging tot het maken van een poging tot geknoei wanneer [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="ccc55-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-159">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-159">Known Issues</span></span>
<span data-ttu-id="ccc55-160">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ccc55-161">Februari-2021 (Platform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="ccc55-161">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="ccc55-162">&ensp;Versie van beveiligingsinformatieupdate: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="ccc55-163">&ensp;Uitgebracht: **9 maart 2021**</span><span class="sxs-lookup"><span data-stu-id="ccc55-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="ccc55-164">&ensp;Platform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="ccc55-164">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="ccc55-165">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="ccc55-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="ccc55-166">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="ccc55-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-167">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-167">What's new</span></span>

- <span data-ttu-id="ccc55-168">Verbeterde serviceherstel door middel [van beveiliging tegen geknoei](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ccc55-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="ccc55-169">Beveiligingsbereik voor tampers uitbreiden</span><span class="sxs-lookup"><span data-stu-id="ccc55-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-170">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-170">Known Issues</span></span>
<span data-ttu-id="ccc55-171">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="ccc55-172">Eerdere versieupdates: Alleen ondersteuning voor technische upgrade</span><span class="sxs-lookup"><span data-stu-id="ccc55-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="ccc55-173">Nadat een nieuwe pakketversie is uitgebracht, wordt de ondersteuning voor de vorige twee versies beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="ccc55-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="ccc55-174">Versies die ouder zijn dan die in deze sectie worden weergegeven, en alleen beschikbaar zijn voor ondersteuning voor technische upgrades.</span><span class="sxs-lookup"><span data-stu-id="ccc55-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="ccc55-175">Januari-2021 (Platform: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="ccc55-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="ccc55-176">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ccc55-177">&ensp;Uitgebracht: **2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="ccc55-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="ccc55-178">&ensp;Platform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="ccc55-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="ccc55-179">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="ccc55-180">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-181">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-181">What's new</span></span>

- <span data-ttu-id="ccc55-182">Verbeteringen voor detectie van Shellcode-exploits</span><span class="sxs-lookup"><span data-stu-id="ccc55-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="ccc55-183">Meer zichtbaarheid voor pogingen tot het stelen van referenties</span><span class="sxs-lookup"><span data-stu-id="ccc55-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="ccc55-184">Verbeteringen in antitamperingfuncties in Microsoft Defender Antivirus services</span><span class="sxs-lookup"><span data-stu-id="ccc55-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="ccc55-185">Verbeterde ondersteuning voor ARM x64-emulatie</span><span class="sxs-lookup"><span data-stu-id="ccc55-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="ccc55-186">Oplossing: EDR Blokkeermelding blijft in de bedreigingsgeschiedenis staan nadat realtimebeveiliging eerste detectie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="ccc55-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-187">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-187">Known Issues</span></span>
<span data-ttu-id="ccc55-188">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ccc55-189">November-2020 (Platform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="ccc55-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="ccc55-190">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ccc55-191">&ensp;Uitgebracht: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="ccc55-192">&ensp;Platform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="ccc55-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="ccc55-193">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ccc55-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="ccc55-194">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-195">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-195">What's new</span></span>

- <span data-ttu-id="ccc55-196">Verbeterde [ondersteuning voor SmartScreen-statusregistratie](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="ccc55-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-197">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-197">Known Issues</span></span>
<span data-ttu-id="ccc55-198">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ccc55-199">Oktober-2020 (Platform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="ccc55-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="ccc55-200">&ensp;Versie van beveiligingsinformatieupdate: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="ccc55-201">&ensp;Uitgebracht: **29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="ccc55-202">&ensp;Platform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="ccc55-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="ccc55-203">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="ccc55-204">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-205">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-205">What's new</span></span>

- <span data-ttu-id="ccc55-206">Nieuwe beschrijvingen voor categorieën met speciale bedreigingen</span><span class="sxs-lookup"><span data-stu-id="ccc55-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="ccc55-207">Verbeterde emulatiemogelijkheden</span><span class="sxs-lookup"><span data-stu-id="ccc55-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="ccc55-208">Verbeterde mogelijkheden voor het toestaan/blokkeren van hostadressen</span><span class="sxs-lookup"><span data-stu-id="ccc55-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="ccc55-209">Nieuwe optie in Defender CSP om het samenvoegen van lokale gebruikersuitsluitingen te negeren</span><span class="sxs-lookup"><span data-stu-id="ccc55-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-210">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-210">Known Issues</span></span>

<span data-ttu-id="ccc55-211">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ccc55-212">September-2020 (Platform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="ccc55-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="ccc55-213">&ensp;Versie van beveiligingsinformatieupdate: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="ccc55-214">&ensp;Uitgebracht: **1 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="ccc55-215">&ensp;Platform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ccc55-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="ccc55-216">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="ccc55-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="ccc55-217">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-218">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-218">What's new</span></span>

- <span data-ttu-id="ccc55-219">Beheerdersmachtigingen zijn vereist om bestanden in quarantaine te herstellen</span><span class="sxs-lookup"><span data-stu-id="ccc55-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="ccc55-220">XML-opgemaakte gebeurtenissen worden nu ondersteund</span><span class="sxs-lookup"><span data-stu-id="ccc55-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="ccc55-221">CSP-ondersteuning voor het negeren van uitsluitings samenvoegen</span><span class="sxs-lookup"><span data-stu-id="ccc55-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="ccc55-222">Nieuwe beheerinterfaces voor:</span><span class="sxs-lookup"><span data-stu-id="ccc55-222">New management interfaces for:</span></span>
   - <span data-ttu-id="ccc55-223">UDP-inspectie</span><span class="sxs-lookup"><span data-stu-id="ccc55-223">UDP Inspection</span></span>
   - <span data-ttu-id="ccc55-224">Netwerkbeveiliging op Server 2019</span><span class="sxs-lookup"><span data-stu-id="ccc55-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="ccc55-225">IP-adresuitsluitingen voor netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="ccc55-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="ccc55-226">Verbeterde zichtbaarheid van TPM-metingen</span><span class="sxs-lookup"><span data-stu-id="ccc55-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="ccc55-227">Verbeterde Office VBA-module scannen</span><span class="sxs-lookup"><span data-stu-id="ccc55-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-228">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-228">Known Issues</span></span>

<span data-ttu-id="ccc55-229">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="ccc55-230">Augustus-2020 (Platform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="ccc55-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="ccc55-231">&ensp;Versie van beveiligingsinformatieupdate: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="ccc55-232">&ensp;Uitgebracht: **27 augustus 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="ccc55-233">&ensp;Platform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="ccc55-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="ccc55-234">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="ccc55-235">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="ccc55-236">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-236">What's new</span></span>

- <span data-ttu-id="ccc55-237">Meer telemetriegebeurtenissen toevoegen</span><span class="sxs-lookup"><span data-stu-id="ccc55-237">Add more telemetry events</span></span>
- <span data-ttu-id="ccc55-238">Verbeterde telemetrie scangebeurtenis</span><span class="sxs-lookup"><span data-stu-id="ccc55-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="ccc55-239">Verbeterde gedragscontrole voor geheugenscans</span><span class="sxs-lookup"><span data-stu-id="ccc55-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="ccc55-240">Verbeterde macrostreams scannen</span><span class="sxs-lookup"><span data-stu-id="ccc55-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="ccc55-241">Toegevoegd `AMRunningMode` aan Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="ccc55-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="ccc55-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wordt genegeerd.</span><span class="sxs-lookup"><span data-stu-id="ccc55-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="ccc55-243">Microsoft Defender Antivirus wordt automatisch uitgeschakeld wanneer er een ander antivirusprogramma wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="ccc55-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="ccc55-244">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-244">Known Issues</span></span>
<span data-ttu-id="ccc55-245">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ccc55-246">Juli-2020 (Platform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="ccc55-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="ccc55-247">&ensp;Versie van beveiligingsinformatieupdate: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="ccc55-248">&ensp;Uitgebracht: **28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="ccc55-249">&ensp;Platform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="ccc55-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="ccc55-250">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="ccc55-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="ccc55-251">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-252">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-252">What's new</span></span>

- <span data-ttu-id="ccc55-253">Verbeterde telemetrie voor BITS</span><span class="sxs-lookup"><span data-stu-id="ccc55-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="ccc55-254">Verbeterde validatie van Authenticode-code ondertekeningscertificaat</span><span class="sxs-lookup"><span data-stu-id="ccc55-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-255">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-255">Known Issues</span></span>
<span data-ttu-id="ccc55-256">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ccc55-257">Juni-2020 (Platform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="ccc55-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="ccc55-258">&ensp;Versie van beveiligingsinformatieupdate: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="ccc55-259">&ensp;Uitgebracht: **22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="ccc55-260">&ensp;Platform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="ccc55-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="ccc55-261">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="ccc55-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="ccc55-262">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-263">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-263">What's new</span></span>

- <span data-ttu-id="ccc55-264">Mogelijkheid om de locatie [van de ondersteuningslogboeken op te geven](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="ccc55-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="ccc55-265">Het overslaan van een agressieve inhaalscan in de passieve modus.</span><span class="sxs-lookup"><span data-stu-id="ccc55-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="ccc55-266">Defender toestaan bij te werken op verbindingen met een datameter</span><span class="sxs-lookup"><span data-stu-id="ccc55-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="ccc55-267">Vaste prestaties afstemmen wanneer caching is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="ccc55-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="ccc55-268">Vaste registerquery</span><span class="sxs-lookup"><span data-stu-id="ccc55-268">Fixed registry query</span></span> 
- <span data-ttu-id="ccc55-269">Randomisatie van scantime in ADMX opgelost</span><span class="sxs-lookup"><span data-stu-id="ccc55-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-270">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-270">Known Issues</span></span>
<span data-ttu-id="ccc55-271">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ccc55-272">Mei-2020 (Platform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="ccc55-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="ccc55-273">&ensp;Versie van beveiligingsinformatieupdate: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="ccc55-274">&ensp;Uitgebracht: **26 mei 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="ccc55-275">&ensp;Platform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="ccc55-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="ccc55-276">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="ccc55-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="ccc55-277">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-278">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-278">What's new</span></span>

- <span data-ttu-id="ccc55-279">Verbeterde logboekregistratie voor scangebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="ccc55-279">Improved logging for scan events</span></span>
- <span data-ttu-id="ccc55-280">Verbeterde crashafhandeling in de gebruikersmodus.</span><span class="sxs-lookup"><span data-stu-id="ccc55-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="ccc55-281">Gebeurtenistracing toegevoegd voor Tamper-beveiliging</span><span class="sxs-lookup"><span data-stu-id="ccc55-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="ccc55-282">AmSI-voorbeeldinzending opgelost</span><span class="sxs-lookup"><span data-stu-id="ccc55-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="ccc55-283">AmSI Cloud blokkeren opgelost</span><span class="sxs-lookup"><span data-stu-id="ccc55-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="ccc55-284">Installatielogboek voor beveiligingsupdates opgelost</span><span class="sxs-lookup"><span data-stu-id="ccc55-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-285">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-285">Known Issues</span></span>
<span data-ttu-id="ccc55-286">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ccc55-287">April-2020 (Platform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="ccc55-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="ccc55-288">&ensp;Versie van beveiligingsinformatieupdate: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="ccc55-289">&ensp;Uitgebracht: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="ccc55-290">&ensp;Platform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="ccc55-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="ccc55-291">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="ccc55-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="ccc55-292">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-293">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-293">What's new</span></span>
- <span data-ttu-id="ccc55-294">Verbeteringen in WDfilter</span><span class="sxs-lookup"><span data-stu-id="ccc55-294">WDfilter improvements</span></span>
- <span data-ttu-id="ccc55-295">Meer actiebare gebeurtenisgegevens toevoegen om detectiegebeurtenissen voor surface reduction aan te vallen</span><span class="sxs-lookup"><span data-stu-id="ccc55-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="ccc55-296">Vaste versiegegevens in diagnostische gegevens en WMI</span><span class="sxs-lookup"><span data-stu-id="ccc55-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="ccc55-297">Onjuiste platformversie in gebruikersinterface na platformupdate opgelost</span><span class="sxs-lookup"><span data-stu-id="ccc55-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="ccc55-298">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="ccc55-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="ccc55-299">UEFI-scanfunctie</span><span class="sxs-lookup"><span data-stu-id="ccc55-299">UEFI scan capability</span></span>
- <span data-ttu-id="ccc55-300">Logboekregistratie uitbreiden voor updates</span><span class="sxs-lookup"><span data-stu-id="ccc55-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="ccc55-301">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-301">Known Issues</span></span>
<span data-ttu-id="ccc55-302">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ccc55-303">Maart-2020 (Platform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="ccc55-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="ccc55-304">&ensp;Versie van beveiligingsinformatieupdate: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="ccc55-305">&ensp;Uitgebracht: **24 maart 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="ccc55-306">&ensp;Platform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="ccc55-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="ccc55-307">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="ccc55-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="ccc55-308">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ccc55-309">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-309">What's new</span></span>

- <span data-ttu-id="ccc55-310">Optie CPU-beperking toegevoegd aan [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ccc55-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="ccc55-311">Diagnostische mogelijkheden verbeteren</span><span class="sxs-lookup"><span data-stu-id="ccc55-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="ccc55-312">time-out voor beveiligingsinformatie verminderen (5 min)</span><span class="sxs-lookup"><span data-stu-id="ccc55-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="ccc55-313">Interne logfunctie voor AMSI-engine uitbreiden</span><span class="sxs-lookup"><span data-stu-id="ccc55-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="ccc55-314">Melding voor procesblokkering verbeteren</span><span class="sxs-lookup"><span data-stu-id="ccc55-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ccc55-315">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-315">Known Issues</span></span>
<span data-ttu-id="ccc55-316">[**Opgelost**] Microsoft Defender Antivirus wordt bestanden overgeslagen tijdens het uitvoeren van een scan.</span><span class="sxs-lookup"><span data-stu-id="ccc55-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="ccc55-317">Februari-2020 (Platform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="ccc55-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="ccc55-318">&ensp;Versie van beveiligingsinformatieupdate: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="ccc55-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="ccc55-319">&ensp;Uitgebracht: **25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="ccc55-320">&ensp;Platform/client: **-**</span><span class="sxs-lookup"><span data-stu-id="ccc55-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="ccc55-321">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="ccc55-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="ccc55-322">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ccc55-323">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="ccc55-324">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-324">Known Issues</span></span>
<span data-ttu-id="ccc55-325">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ccc55-326">Januari-2020 (Platform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="ccc55-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="ccc55-327">Versie van beveiligingsinformatieupdate: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="ccc55-328">Uitgebracht: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="ccc55-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="ccc55-329">Platform/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="ccc55-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="ccc55-330">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="ccc55-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="ccc55-331">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="ccc55-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ccc55-332">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-332">What's new</span></span>

- <span data-ttu-id="ccc55-333">BSOD opgelost in WS2016 met Exchange</span><span class="sxs-lookup"><span data-stu-id="ccc55-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="ccc55-334">Ondersteuningsplatformupdates wanneer TMP wordt omgeleid naar netwerkpad</span><span class="sxs-lookup"><span data-stu-id="ccc55-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="ccc55-335">Platform- en engineversies worden toegevoegd aan [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ccc55-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="ccc55-336">Update voor noodhandtekeningen uitbreiden [naar passieve modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ccc55-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="ccc55-337">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="ccc55-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ccc55-338">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-338">Known Issues</span></span>

<span data-ttu-id="ccc55-339">[**Opgelost**] apparaten die gebruikmaken van [de moderne stand-bymodus,](/windows-hardware/design/device-experiences/modern-standby) kunnen last hebben van de Windows Defender filtert stuurprogramma, wat resulteert in een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="ccc55-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="ccc55-340">Getroffen machines worden voor de klant weergegeven als niet bijgewerkt naar het nieuwste antimalwareplatform.</span><span class="sxs-lookup"><span data-stu-id="ccc55-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="ccc55-341">Deze update is:</span><span class="sxs-lookup"><span data-stu-id="ccc55-341">This update is:</span></span>
> - <span data-ttu-id="ccc55-342">vereist door RS1-apparaten met een lagere versie van het platform ter ondersteuning van SHA2;</span><span class="sxs-lookup"><span data-stu-id="ccc55-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="ccc55-343">heeft een herstartvlag voor systemen met problemen met ophangen;</span><span class="sxs-lookup"><span data-stu-id="ccc55-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="ccc55-344">wordt opnieuw uitgebracht in april 2020 en wordt niet vervangen door nieuwere updates om toekomstige beschikbaarheid te behouden.</span><span class="sxs-lookup"><span data-stu-id="ccc55-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="ccc55-345">wordt gecategoriseerd als een update vanwege de herstartvereiste; en</span><span class="sxs-lookup"><span data-stu-id="ccc55-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="ccc55-346">wordt alleen aangeboden met [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="ccc55-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ccc55-347">November-2019 (Platform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="ccc55-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="ccc55-348">Versie van beveiligingsinformatieupdate: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="ccc55-349">Uitgebracht: **7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="ccc55-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="ccc55-350">Platform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="ccc55-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="ccc55-351">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="ccc55-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="ccc55-352">Ondersteuningsfase: **Geen ondersteuning**</span><span class="sxs-lookup"><span data-stu-id="ccc55-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="ccc55-353">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="ccc55-353">What's new</span></span>

- <span data-ttu-id="ccc55-354">MpCmdRun-traceringsniveau opgelost</span><span class="sxs-lookup"><span data-stu-id="ccc55-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="ccc55-355">Versiegegevens van WDFilter opgelost</span><span class="sxs-lookup"><span data-stu-id="ccc55-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="ccc55-356">Meldingen verbeteren (PUA)</span><span class="sxs-lookup"><span data-stu-id="ccc55-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="ccc55-357">MRT-logboeken toevoegen om bestanden te ondersteunen</span><span class="sxs-lookup"><span data-stu-id="ccc55-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ccc55-358">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="ccc55-358">Known Issues</span></span>
<span data-ttu-id="ccc55-359">Wanneer deze update is geïnstalleerd, heeft het apparaat het jump-pakket 4.10.2001.10 nodig om te kunnen bijwerken naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="ccc55-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="ccc55-360">Microsoft Defender Antivirus platformondersteuning</span><span class="sxs-lookup"><span data-stu-id="ccc55-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="ccc55-361">Platform- en motorupdates worden geleverd op een maandelijkse cadans.</span><span class="sxs-lookup"><span data-stu-id="ccc55-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="ccc55-362">Als u volledig wilt worden ondersteund, blijft u op de hoogte van de meest recente platformupdates.</span><span class="sxs-lookup"><span data-stu-id="ccc55-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="ccc55-363">Onze ondersteuningsstructuur is dynamisch en verandert in twee fasen, afhankelijk van de beschikbaarheid van de nieuwste platformversie:</span><span class="sxs-lookup"><span data-stu-id="ccc55-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="ccc55-364">**Servicefase beveiligings-** en kritieke updates: wanneer u de nieuwste platformversie gebruikt, komt u in aanmerking voor zowel beveiligings- als kritieke updates voor het anti-malwareplatform.</span><span class="sxs-lookup"><span data-stu-id="ccc55-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="ccc55-365">**Technische ondersteuning (alleen) fase:** nadat een nieuwe platformversie is uitgebracht, wordt de ondersteuning voor oudere versies (N-2) beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="ccc55-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="ccc55-366">Platformversies die ouder zijn dan N-2, worden niet meer ondersteund.\*</span><span class="sxs-lookup"><span data-stu-id="ccc55-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="ccc55-367">\*Technische ondersteuning blijft beschikbaar voor upgrades van de Windows 10 releaseversie (zie Platformversie inbegrepen bij Windows 10 [releases)](#platform-version-included-with-windows-10-releases)naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="ccc55-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="ccc55-368">Tijdens de fase van technische ondersteuning (alleen) worden commercieel redelijke ondersteuningsincidenten verstrekt via Microsoft Customer Service & Support en beheerde ondersteuningsaanbiedingen van Microsoft (zoals Premier Support).</span><span class="sxs-lookup"><span data-stu-id="ccc55-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="ccc55-369">Als voor een ondersteuningsincident escalatie nodig is voor de ontwikkeling voor verdere richtlijnen, een niet-beveiligingsupdate vereist is of een beveiligingsupdate vereist, wordt klanten gevraagd een upgrade uit te voeren naar de nieuwste platformversie of een tussentijdse update (\*).</span><span class="sxs-lookup"><span data-stu-id="ccc55-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="ccc55-370">Platformversie inbegrepen bij Windows 10 releases</span><span class="sxs-lookup"><span data-stu-id="ccc55-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="ccc55-371">In de onderstaande tabel vindt u Microsoft Defender Antivirus platform- en engineversies die worden verzonden met de nieuwste Windows 10 releases:</span><span class="sxs-lookup"><span data-stu-id="ccc55-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="ccc55-372">Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="ccc55-372">Windows 10 release</span></span>  |<span data-ttu-id="ccc55-373">Platformversie</span><span class="sxs-lookup"><span data-stu-id="ccc55-373">Platform version</span></span>  |<span data-ttu-id="ccc55-374">Engine-versie</span><span class="sxs-lookup"><span data-stu-id="ccc55-374">Engine version</span></span> |<span data-ttu-id="ccc55-375">Ondersteuningsfase</span><span class="sxs-lookup"><span data-stu-id="ccc55-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="ccc55-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="ccc55-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="ccc55-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="ccc55-377">4.18.1909.6</span></span> |<span data-ttu-id="ccc55-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="ccc55-378">1.1.17000.2</span></span> | <span data-ttu-id="ccc55-379">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="ccc55-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ccc55-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="ccc55-380">1909  (19H2)</span></span> |<span data-ttu-id="ccc55-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ccc55-381">4.18.1902.5</span></span> |<span data-ttu-id="ccc55-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="ccc55-382">1.1.16700.3</span></span> | <span data-ttu-id="ccc55-383">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="ccc55-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ccc55-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="ccc55-384">1903  (19H1)</span></span> |<span data-ttu-id="ccc55-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ccc55-385">4.18.1902.5</span></span> |<span data-ttu-id="ccc55-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="ccc55-386">1.1.15600.4</span></span> | <span data-ttu-id="ccc55-387">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="ccc55-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ccc55-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="ccc55-388">1809  (RS5)</span></span> |<span data-ttu-id="ccc55-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="ccc55-389">4.18.1807.18075</span></span> |<span data-ttu-id="ccc55-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="ccc55-390">1.1.15000.2</span></span> | <span data-ttu-id="ccc55-391">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="ccc55-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ccc55-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="ccc55-392">1803  (RS4)</span></span> |<span data-ttu-id="ccc55-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="ccc55-393">4.13.17134.1</span></span> |<span data-ttu-id="ccc55-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="ccc55-394">1.1.14600.4</span></span> | <span data-ttu-id="ccc55-395">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="ccc55-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ccc55-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="ccc55-396">1709  (RS3)</span></span> |<span data-ttu-id="ccc55-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="ccc55-397">4.12.16299.15</span></span> |<span data-ttu-id="ccc55-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="ccc55-398">1.1.14104.0</span></span> | <span data-ttu-id="ccc55-399">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="ccc55-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ccc55-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="ccc55-400">1703  (RS2)</span></span> |<span data-ttu-id="ccc55-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="ccc55-401">4.11.15603.2</span></span> |<span data-ttu-id="ccc55-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="ccc55-402">1.1.13504.0</span></span> | <span data-ttu-id="ccc55-403">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="ccc55-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ccc55-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="ccc55-404">1607 (RS1)</span></span> |<span data-ttu-id="ccc55-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="ccc55-405">4.10.14393.3683</span></span> |<span data-ttu-id="ccc55-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="ccc55-406">1.1.12805.0</span></span> | <span data-ttu-id="ccc55-407">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="ccc55-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="ccc55-408">Zie het Windows het Windows 10 voor meer informatie over [de release.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="ccc55-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="ccc55-409">Updates voor implementatie van image Servicing and Management (DISM)</span><span class="sxs-lookup"><span data-stu-id="ccc55-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="ccc55-410">U wordt aangeraden uw Windows 10 (Enterprise-, Pro- en Home-edities), Windows Server 2019 en Windows Server 2016-installatieafbeeldingen van het besturingssysteem bij te werken met de nieuwste antivirus- en antimalware-updates.</span><span class="sxs-lookup"><span data-stu-id="ccc55-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="ccc55-411">Als u de installatieafbeeldingen van uw besturingssysteem up-to-date houdt, voorkomt u een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="ccc55-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="ccc55-412">Zie Microsoft Defender update voor Windows [installatieafbeeldingen](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)van het besturingssysteem voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ccc55-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="ccc55-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="ccc55-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="ccc55-414">&ensp;Pakketversie: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="ccc55-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="ccc55-415">&ensp;Platformversie: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="ccc55-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="ccc55-416">&ensp;Engine versie: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="ccc55-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="ccc55-417">&ensp;Handtekeningversie: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ccc55-418">Fixes</span><span class="sxs-lookup"><span data-stu-id="ccc55-418">Fixes</span></span>
- <span data-ttu-id="ccc55-419">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ccc55-420">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="ccc55-420">Additional information</span></span>
- <span data-ttu-id="ccc55-421">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ccc55-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="ccc55-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="ccc55-423">&ensp;Pakketversie: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="ccc55-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="ccc55-424">&ensp;Platformversie: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="ccc55-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="ccc55-425">&ensp;Engine-versie: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="ccc55-426">&ensp;Handtekeningversie: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ccc55-427">Fixes</span><span class="sxs-lookup"><span data-stu-id="ccc55-427">Fixes</span></span>
- <span data-ttu-id="ccc55-428">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ccc55-429">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="ccc55-429">Additional information</span></span>
- <span data-ttu-id="ccc55-430">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ccc55-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="ccc55-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="ccc55-432">&ensp;Pakketversie: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="ccc55-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="ccc55-433">&ensp;Platformversie: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="ccc55-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="ccc55-434">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ccc55-435">&ensp;Handtekeningversie: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ccc55-436">Fixes</span><span class="sxs-lookup"><span data-stu-id="ccc55-436">Fixes</span></span>
- <span data-ttu-id="ccc55-437">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ccc55-438">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="ccc55-438">Additional information</span></span>
- <span data-ttu-id="ccc55-439">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ccc55-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="ccc55-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="ccc55-441">&ensp;Pakketversie: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="ccc55-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="ccc55-442">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ccc55-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ccc55-443">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ccc55-444">&ensp;Handtekeningversie: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ccc55-445">Fixes</span><span class="sxs-lookup"><span data-stu-id="ccc55-445">Fixes</span></span>
- <span data-ttu-id="ccc55-446">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ccc55-447">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="ccc55-447">Additional information</span></span>
- <span data-ttu-id="ccc55-448">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ccc55-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="ccc55-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="ccc55-450">&ensp;Pakketversie: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="ccc55-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="ccc55-451">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ccc55-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ccc55-452">&ensp;Motorversie: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ccc55-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="ccc55-453">&ensp;Handtekeningversie: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ccc55-454">Fixes</span><span class="sxs-lookup"><span data-stu-id="ccc55-454">Fixes</span></span>
- <span data-ttu-id="ccc55-455">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ccc55-456">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="ccc55-456">Additional information</span></span>
- <span data-ttu-id="ccc55-457">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ccc55-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="ccc55-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="ccc55-459">&ensp;Pakketversie: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="ccc55-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="ccc55-460">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ccc55-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ccc55-461">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ccc55-462">&ensp;Handtekeningversie: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ccc55-463">Fixes</span><span class="sxs-lookup"><span data-stu-id="ccc55-463">Fixes</span></span>
- <span data-ttu-id="ccc55-464">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ccc55-465">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="ccc55-465">Additional information</span></span>
- <span data-ttu-id="ccc55-466">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ccc55-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="ccc55-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="ccc55-468">&ensp;Pakketversie: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="ccc55-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="ccc55-469">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ccc55-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ccc55-470">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ccc55-471">&ensp;Handtekeningversie: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ccc55-472">Fixes</span><span class="sxs-lookup"><span data-stu-id="ccc55-472">Fixes</span></span>
- <span data-ttu-id="ccc55-473">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ccc55-474">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="ccc55-474">Additional information</span></span>
- <span data-ttu-id="ccc55-475">Vernieuwde Microsoft Defender Antivirus handtekeningen</span><span class="sxs-lookup"><span data-stu-id="ccc55-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ccc55-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="ccc55-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="ccc55-477">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ccc55-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ccc55-478">&ensp;Platformversie: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ccc55-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="ccc55-479">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ccc55-480">&ensp;Handtekeningversie: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ccc55-481">Fixes</span><span class="sxs-lookup"><span data-stu-id="ccc55-481">Fixes</span></span>
- <span data-ttu-id="ccc55-482">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ccc55-483">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="ccc55-483">Additional information</span></span>
- <span data-ttu-id="ccc55-484">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ccc55-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="ccc55-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="ccc55-486">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ccc55-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ccc55-487">&ensp;Platformversie: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="ccc55-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="ccc55-488">&ensp;Motorversie: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ccc55-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="ccc55-489">&ensp;Handtekeningversie: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="ccc55-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ccc55-490">Fixes</span><span class="sxs-lookup"><span data-stu-id="ccc55-490">Fixes</span></span>
- <span data-ttu-id="ccc55-491">Geen</span><span class="sxs-lookup"><span data-stu-id="ccc55-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ccc55-492">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="ccc55-492">Additional information</span></span>
- <span data-ttu-id="ccc55-493">Ondersteuning toegevoegd voor Windows 10 RS1- of hoger os-installatieafbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="ccc55-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="ccc55-494">Aanvullende bronnen</span><span class="sxs-lookup"><span data-stu-id="ccc55-494">Additional resources</span></span>

| <span data-ttu-id="ccc55-495">Artikel</span><span class="sxs-lookup"><span data-stu-id="ccc55-495">Article</span></span> | <span data-ttu-id="ccc55-496">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ccc55-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="ccc55-497">Microsoft Defender-update voor Windows installatieafbeeldingen van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="ccc55-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="ccc55-498">Controleer antimalware-updatepakketten voor installatieafbeeldingen van uw besturingssysteem (WIM- en VHD-bestanden).</span><span class="sxs-lookup"><span data-stu-id="ccc55-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="ccc55-499">Ontvang Microsoft Defender Antivirus updates voor Windows 10 (Enterprise, Pro en Home editions), Windows Server 2019 en Windows Server 2016 installatieafbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="ccc55-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="ccc55-500">Beheren hoe beveiligingsupdates worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="ccc55-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ccc55-501">Beveiligingsupdates kunnen via veel bronnen worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="ccc55-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="ccc55-502">Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="ccc55-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="ccc55-503">U kunt plannen wanneer beveiligingsupdates moeten worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="ccc55-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="ccc55-504">Updates beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="ccc55-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="ccc55-505">Als een eindpunt een update of geplande scan mist, kunt u een update forcen of scannen wanneer een gebruiker zich de volgende keer meldt.</span><span class="sxs-lookup"><span data-stu-id="ccc55-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="ccc55-506">Op basis van gebeurtenissen afgedwongen updates beheren</span><span class="sxs-lookup"><span data-stu-id="ccc55-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ccc55-507">U kunt instellen dat beveiligingsupdates worden gedownload bij het opstarten of na bepaalde beveiligingsgebeurtenissen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="ccc55-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="ccc55-508">Updates beheren voor mobiele apparaten en virtuele machines (VM's)</span><span class="sxs-lookup"><span data-stu-id="ccc55-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="ccc55-509">U kunt instellingen opgeven, zoals of er updates moeten worden uitgevoerd op batterijvermogen, die vooral handig zijn voor mobiele apparaten en virtuele machines.</span><span class="sxs-lookup"><span data-stu-id="ccc55-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
