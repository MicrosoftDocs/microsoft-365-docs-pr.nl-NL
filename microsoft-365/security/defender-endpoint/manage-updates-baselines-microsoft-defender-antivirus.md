---
title: Microsoft Defender Antivirus-updates beheren en basislijnen toepassen
description: Beheer hoe Microsoft Defender Antivirus bescherming en productupdates ontvangt.
keywords: updates, beveiligingslijnlijnen, beveiliging, planningsupdates, force-updates, mobiele updates, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b70cf96cde7d4dff8e2a4db6ce2469090dba7eb1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765609"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="5a3c4-104">Microsoft Defender Antivirus-updates beheren en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="5a3c4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-105">**Applies to:**</span></span>

- [<span data-ttu-id="5a3c4-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5a3c4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="5a3c4-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="5a3c4-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="5a3c4-108">Er zijn twee soorten updates die betrekking hebben op het up-to-date houden van Microsoft Defender Antivirus:</span><span class="sxs-lookup"><span data-stu-id="5a3c4-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="5a3c4-109">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="5a3c4-109">Security intelligence updates</span></span>
- <span data-ttu-id="5a3c4-110">Productupdates</span><span class="sxs-lookup"><span data-stu-id="5a3c4-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a3c4-111">Het up-to-date houden van Microsoft Defender Antivirus is essentieel om ervoor te zorgen dat uw apparaten de nieuwste technologie en functies hebben die nodig zijn om te beschermen tegen nieuwe malware en aanvalstechnieken.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>  
> <span data-ttu-id="5a3c4-112">Zorg ervoor dat u uw antivirusbeveiliging bij werkt, zelfs als Microsoft Defender Antivirus actief is in [de passieve modus.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="5a3c4-113">Als u de meest recente datum van de engine, het platform en de handtekening wilt zien, gaat u naar de beveiligingsinformatieupdates voor [Microsoft Defender Antivirus en andere Microsoft-antimalware.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="5a3c4-114">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="5a3c4-114">Security intelligence updates</span></span>

<span data-ttu-id="5a3c4-115">Microsoft Defender Antivirus gebruikt beveiliging in de cloud (ook wel de Microsoft Advanced Protection Service of KAARTEN genoemd) en downloadt regelmatig [beveiligingsinformatie-updates](cloud-protection-microsoft-defender-antivirus.md) om bescherming te bieden.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="5a3c4-116">Updates worden uitgebracht onder de onderstaande KB-nummers:</span><span class="sxs-lookup"><span data-stu-id="5a3c4-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="5a3c4-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="5a3c4-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="5a3c4-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="5a3c4-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="5a3c4-119">Beveiliging in de cloud is altijd actief en hiervoor is een actieve verbinding met internet vereist.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="5a3c4-120">Beveiligingsintelligentie-updates vinden plaats op een geplande cadans (configureerbaar via beleid).</span><span class="sxs-lookup"><span data-stu-id="5a3c4-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="5a3c4-121">Zie Microsoft Defender Antivirus voor meer [informatie.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="5a3c4-122">Zie Beveiligingsintelligentie-updates voor Microsoft Defender Antivirus en andere Microsoft-antimalware voor een lijst met recente [beveiligingsintelligentie-updates.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="5a3c4-123">Engine-updates worden opgenomen in beveiligingsinformatie-updates en worden maandelijks uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="5a3c4-124">Productupdates</span><span class="sxs-lookup"><span data-stu-id="5a3c4-124">Product updates</span></span>

<span data-ttu-id="5a3c4-125">Microsoft Defender Antivirus vereist [maandelijkse updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (ook wel *platformupdates* genoemd) en ontvangt naast Windows 10-versies belangrijke functie-updates.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="5a3c4-126">U kunt de distributie van updates beheren via een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="5a3c4-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="5a3c4-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="5a3c4-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5a3c4-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="5a3c4-129">De gebruikelijke methode die u gebruikt om Microsoft- en Windows-updates te implementeren voor eindpunten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="5a3c4-130">Zie De bronnen voor [Microsoft Defender Antivirusbeveiligingsupdates beheren voor meer informatie.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="5a3c4-131">Maandelijkse updates worden gefaseerd uitgebracht, wat resulteert in meerdere pakketten die zichtbaar zijn in [uw Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="5a3c4-132">Maandelijkse platform- en engineversies</span><span class="sxs-lookup"><span data-stu-id="5a3c4-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="5a3c4-133">Zie [Update voor Windows Defender antimalwareplatform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)voor informatie over het bijwerken of installeren van de platformupdate.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="5a3c4-134">Al onze updates bevatten</span><span class="sxs-lookup"><span data-stu-id="5a3c4-134">All our updates contain</span></span> 
- <span data-ttu-id="5a3c4-135">prestatieverbeteringen;</span><span class="sxs-lookup"><span data-stu-id="5a3c4-135">performance improvements;</span></span>
- <span data-ttu-id="5a3c4-136">verbeteringen in de servicebaarheid; en</span><span class="sxs-lookup"><span data-stu-id="5a3c4-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="5a3c4-137">integratieverbeteringen (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="5a3c4-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="5a3c4-138">Maart-2021 (Platform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="5a3c4-139">&ensp;Versie van beveiligingsinformatieupdate: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="5a3c4-140">&ensp;Uitgebracht: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="5a3c4-141">&ensp;Platform: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="5a3c4-142">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="5a3c4-143">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-144">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-144">What's new</span></span>

- <span data-ttu-id="5a3c4-145">Verbetering van de engine Gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="5a3c4-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="5a3c4-146">Uitgebreide netwerkbeperking met brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="5a3c4-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="5a3c4-147">Extra mislukte poging tot het maken van een poging tot geknoei wanneer [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="5a3c4-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="5a3c4-148">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-148">Known Issues</span></span>
<span data-ttu-id="5a3c4-149">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5a3c4-150">Februari-2021 (Platform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="5a3c4-151">&ensp;Versie van beveiligingsinformatieupdate: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="5a3c4-152">&ensp;Uitgebracht: **9 maart 2021**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="5a3c4-153">&ensp;Platform: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="5a3c4-154">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="5a3c4-155">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-156">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-156">What's new</span></span>

- <span data-ttu-id="5a3c4-157">Verbeterde serviceherstel door middel [van beveiliging tegen geknoei](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="5a3c4-158">Beveiligingsbereik voor tampers uitbreiden</span><span class="sxs-lookup"><span data-stu-id="5a3c4-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="5a3c4-159">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-159">Known Issues</span></span>
<span data-ttu-id="5a3c4-160">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5a3c4-161">Januari-2021 (Platform: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="5a3c4-162">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="5a3c4-163">&ensp;Uitgebracht: **2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="5a3c4-164">&ensp;Platform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="5a3c4-165">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="5a3c4-166">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-167">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-167">What's new</span></span>

- <span data-ttu-id="5a3c4-168">Verbeteringen voor detectie van Shellcode-exploits</span><span class="sxs-lookup"><span data-stu-id="5a3c4-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="5a3c4-169">Meer zichtbaarheid voor pogingen tot het stelen van referenties</span><span class="sxs-lookup"><span data-stu-id="5a3c4-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="5a3c4-170">Verbeteringen in antitampering-functies in Microsoft Defender Antivirus-services</span><span class="sxs-lookup"><span data-stu-id="5a3c4-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="5a3c4-171">Verbeterde ondersteuning voor ARM x64-emulatie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="5a3c4-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span><span class="sxs-lookup"><span data-stu-id="5a3c4-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="5a3c4-173">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-173">Known Issues</span></span>
<span data-ttu-id="5a3c4-174">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="5a3c4-175">Eerdere versieupdates: Alleen ondersteuning voor technische upgrade</span><span class="sxs-lookup"><span data-stu-id="5a3c4-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="5a3c4-176">Nadat een nieuwe pakketversie is uitgebracht, wordt de ondersteuning voor de vorige twee versies beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="5a3c4-177">Versies die ouder zijn dan die in deze sectie worden weergegeven, en alleen beschikbaar zijn voor ondersteuning voor technische upgrades.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="5a3c4-178">November-2020 (Platform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="5a3c4-179">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="5a3c4-180">&ensp;Uitgebracht: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="5a3c4-181">&ensp;Platform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="5a3c4-182">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="5a3c4-183">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-183">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-184">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-184">What's new</span></span>

- <span data-ttu-id="5a3c4-185">Verbeterde [ondersteuning voor SmartScreen-statusregistratie](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="5a3c4-186">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-186">Known Issues</span></span>
<span data-ttu-id="5a3c4-187">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5a3c4-188">Oktober-2020 (Platform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="5a3c4-189">&ensp;Versie van beveiligingsinformatieupdate: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="5a3c4-190">&ensp;Uitgebracht: **29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="5a3c4-191">&ensp;Platform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="5a3c4-192">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="5a3c4-193">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-193">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-194">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-194">What's new</span></span>

- <span data-ttu-id="5a3c4-195">Nieuwe beschrijvingen voor categorieën met speciale bedreigingen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="5a3c4-196">Verbeterde emulatiemogelijkheden</span><span class="sxs-lookup"><span data-stu-id="5a3c4-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="5a3c4-197">Verbeterde mogelijkheden voor het toestaan/blokkeren van hostadressen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="5a3c4-198">Nieuwe optie in Defender CSP om het samenvoegen van lokale gebruikersuitsluitingen te negeren</span><span class="sxs-lookup"><span data-stu-id="5a3c4-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="5a3c4-199">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-199">Known Issues</span></span>

<span data-ttu-id="5a3c4-200">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5a3c4-201">September-2020 (Platform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="5a3c4-202">&ensp;Versie van beveiligingsinformatieupdate: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="5a3c4-203">&ensp;Uitgebracht: **1 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="5a3c4-204">&ensp;Platform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="5a3c4-205">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="5a3c4-206">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-207">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-207">What's new</span></span>

- <span data-ttu-id="5a3c4-208">Beheerdersmachtigingen zijn vereist om bestanden in quarantaine te herstellen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="5a3c4-209">XML-opgemaakte gebeurtenissen worden nu ondersteund</span><span class="sxs-lookup"><span data-stu-id="5a3c4-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="5a3c4-210">CSP-ondersteuning voor het negeren van uitsluitings samenvoegen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="5a3c4-211">Nieuwe beheerinterfaces voor:</span><span class="sxs-lookup"><span data-stu-id="5a3c4-211">New management interfaces for:</span></span>
   - <span data-ttu-id="5a3c4-212">UDP-inspectie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-212">UDP Inspection</span></span>
   - <span data-ttu-id="5a3c4-213">Netwerkbeveiliging op Server 2019</span><span class="sxs-lookup"><span data-stu-id="5a3c4-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="5a3c4-214">IP-adresuitsluitingen voor netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="5a3c4-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="5a3c4-215">Verbeterde zichtbaarheid van TPM-metingen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="5a3c4-216">Verbeterde office VBA-module scannen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="5a3c4-217">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-217">Known Issues</span></span>

<span data-ttu-id="5a3c4-218">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="5a3c4-219">Augustus-2020 (Platform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="5a3c4-220">&ensp;Versie van beveiligingsinformatieupdate: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="5a3c4-221">&ensp;Uitgebracht: **27 augustus 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="5a3c4-222">&ensp;Platform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="5a3c4-223">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="5a3c4-224">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="5a3c4-225">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-225">What's new</span></span>

- <span data-ttu-id="5a3c4-226">Meer telemetriegebeurtenissen toevoegen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-226">Add more telemetry events</span></span>
- <span data-ttu-id="5a3c4-227">Verbeterde telemetrie scangebeurtenis</span><span class="sxs-lookup"><span data-stu-id="5a3c4-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="5a3c4-228">Verbeterde gedragscontrole voor geheugenscans</span><span class="sxs-lookup"><span data-stu-id="5a3c4-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="5a3c4-229">Verbeterde macrostreams scannen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="5a3c4-230">Toegevoegd `AMRunningMode` aan Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="5a3c4-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="5a3c4-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wordt genegeerd.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="5a3c4-232">Microsoft Defender Antivirus schakelt zichzelf automatisch uit wanneer er een ander antivirusprogramma wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="5a3c4-233">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-233">Known Issues</span></span>
<span data-ttu-id="5a3c4-234">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5a3c4-235">Juli-2020 (Platform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="5a3c4-236">&ensp;Versie van beveiligingsinformatieupdate: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="5a3c4-237">&ensp;Uitgebracht: **28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="5a3c4-238">&ensp;Platform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="5a3c4-239">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="5a3c4-240">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-241">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-241">What's new</span></span>

- <span data-ttu-id="5a3c4-242">Verbeterde telemetrie voor BITS</span><span class="sxs-lookup"><span data-stu-id="5a3c4-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="5a3c4-243">Verbeterde validatie van Authenticode-code ondertekeningscertificaat</span><span class="sxs-lookup"><span data-stu-id="5a3c4-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="5a3c4-244">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-244">Known Issues</span></span>
<span data-ttu-id="5a3c4-245">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5a3c4-246">Juni-2020 (Platform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="5a3c4-247">&ensp;Versie van beveiligingsinformatieupdate: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="5a3c4-248">&ensp;Uitgebracht: **22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="5a3c4-249">&ensp;Platform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="5a3c4-250">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="5a3c4-251">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-252">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-252">What's new</span></span>

- <span data-ttu-id="5a3c4-253">Mogelijkheid om de locatie [van de ondersteuningslogboeken op te geven](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="5a3c4-254">Het overslaan van een agressieve inhaalscan in de passieve modus.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="5a3c4-255">Defender toestaan bij te werken op verbindingen met een datameter</span><span class="sxs-lookup"><span data-stu-id="5a3c4-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="5a3c4-256">Vaste prestaties afstemmen wanneer caching is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="5a3c4-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="5a3c4-257">Vaste registerquery</span><span class="sxs-lookup"><span data-stu-id="5a3c4-257">Fixed registry query</span></span> 
- <span data-ttu-id="5a3c4-258">Randomisatie van scantime in ADMX opgelost</span><span class="sxs-lookup"><span data-stu-id="5a3c4-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="5a3c4-259">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-259">Known Issues</span></span>
<span data-ttu-id="5a3c4-260">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5a3c4-261">Mei-2020 (Platform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="5a3c4-262">&ensp;Versie van beveiligingsinformatieupdate: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="5a3c4-263">&ensp;Uitgebracht: **26 mei 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="5a3c4-264">&ensp;Platform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="5a3c4-265">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="5a3c4-266">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-267">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-267">What's new</span></span>

- <span data-ttu-id="5a3c4-268">Verbeterde logboekregistratie voor scangebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-268">Improved logging for scan events</span></span>
- <span data-ttu-id="5a3c4-269">Verbeterde crashafhandeling in de gebruikersmodus.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="5a3c4-270">Gebeurtenistracing toegevoegd voor Tamper-beveiliging</span><span class="sxs-lookup"><span data-stu-id="5a3c4-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="5a3c4-271">AmSI-voorbeeldinzending opgelost</span><span class="sxs-lookup"><span data-stu-id="5a3c4-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="5a3c4-272">AmSI Cloud blokkeren opgelost</span><span class="sxs-lookup"><span data-stu-id="5a3c4-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="5a3c4-273">Installatielogboek voor beveiligingsupdates opgelost</span><span class="sxs-lookup"><span data-stu-id="5a3c4-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="5a3c4-274">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-274">Known Issues</span></span>
<span data-ttu-id="5a3c4-275">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5a3c4-276">April-2020 (Platform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="5a3c4-277">&ensp;Versie van beveiligingsinformatieupdate: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="5a3c4-278">&ensp;Uitgebracht: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="5a3c4-279">&ensp;Platform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="5a3c4-280">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="5a3c4-281">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-282">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-282">What's new</span></span>
- <span data-ttu-id="5a3c4-283">Verbeteringen in WDfilter</span><span class="sxs-lookup"><span data-stu-id="5a3c4-283">WDfilter improvements</span></span>
- <span data-ttu-id="5a3c4-284">Meer actiebare gebeurtenisgegevens toevoegen om detectiegebeurtenissen voor surface reduction aan te vallen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="5a3c4-285">Vaste versiegegevens in diagnostische gegevens en WMI</span><span class="sxs-lookup"><span data-stu-id="5a3c4-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="5a3c4-286">Onjuiste platformversie in gebruikersinterface na platformupdate opgelost</span><span class="sxs-lookup"><span data-stu-id="5a3c4-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="5a3c4-287">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="5a3c4-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="5a3c4-288">UEFI-scanfunctie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-288">UEFI scan capability</span></span>
- <span data-ttu-id="5a3c4-289">Logboekregistratie uitbreiden voor updates</span><span class="sxs-lookup"><span data-stu-id="5a3c4-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="5a3c4-290">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-290">Known Issues</span></span>
<span data-ttu-id="5a3c4-291">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5a3c4-292">Maart-2020 (Platform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="5a3c4-293">&ensp;Versie van beveiligingsinformatieupdate: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="5a3c4-294">&ensp;Uitgebracht: **24 maart 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="5a3c4-295">&ensp;Platform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="5a3c4-296">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="5a3c4-297">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5a3c4-298">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-298">What's new</span></span>

- <span data-ttu-id="5a3c4-299">Optie CPU-beperking toegevoegd aan [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="5a3c4-300">Diagnostische mogelijkheden verbeteren</span><span class="sxs-lookup"><span data-stu-id="5a3c4-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="5a3c4-301">time-out voor beveiligingsinformatie verminderen (5 min)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="5a3c4-302">Interne logfunctie voor AMSI-engine uitbreiden</span><span class="sxs-lookup"><span data-stu-id="5a3c4-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="5a3c4-303">Melding voor procesblokkering verbeteren</span><span class="sxs-lookup"><span data-stu-id="5a3c4-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="5a3c4-304">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-304">Known Issues</span></span>
<span data-ttu-id="5a3c4-305">[**Opgelost**] Microsoft Defender Antivirus is het overslaan van bestanden bij het uitvoeren van een scan.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="5a3c4-306">Februari-2020 (Platform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="5a3c4-307">&ensp;Versie van beveiligingsinformatieupdate: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="5a3c4-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="5a3c4-308">&ensp;Uitgebracht: **25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="5a3c4-309">&ensp;Platform/client: **-**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="5a3c4-310">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="5a3c4-311">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="5a3c4-312">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="5a3c4-313">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-313">Known Issues</span></span>
<span data-ttu-id="5a3c4-314">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="5a3c4-315">Januari-2020 (Platform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="5a3c4-316">Versie van beveiligingsinformatieupdate: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="5a3c4-317">Uitgebracht: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="5a3c4-318">Platform/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="5a3c4-319">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="5a3c4-320">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="5a3c4-321">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-321">What's new</span></span>

- <span data-ttu-id="5a3c4-322">BSOD opgelost in WS2016 met Exchange</span><span class="sxs-lookup"><span data-stu-id="5a3c4-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="5a3c4-323">Ondersteuningsplatformupdates wanneer TMP wordt omgeleid naar netwerkpad</span><span class="sxs-lookup"><span data-stu-id="5a3c4-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="5a3c4-324">Platform- en engineversies worden toegevoegd aan [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="5a3c4-325">Update voor noodhandtekeningen uitbreiden [naar passieve modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="5a3c4-326">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="5a3c4-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="5a3c4-327">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-327">Known Issues</span></span>

<span data-ttu-id="5a3c4-328">[**Opgelost**] apparaten die gebruikmaken van [de moderne stand-bymodus,](/windows-hardware/design/device-experiences/modern-standby) kunnen last hebben van een probleem met het Windows Defender-filtertruis, wat resulteert in een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="5a3c4-329">Getroffen machines worden voor de klant weergegeven als niet bijgewerkt naar het nieuwste antimalwareplatform.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="5a3c4-330">Deze update is:</span><span class="sxs-lookup"><span data-stu-id="5a3c4-330">This update is:</span></span>
> - <span data-ttu-id="5a3c4-331">vereist door RS1-apparaten met een lagere versie van het platform ter ondersteuning van SHA2;</span><span class="sxs-lookup"><span data-stu-id="5a3c4-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="5a3c4-332">heeft een herstartvlag voor systemen met problemen met ophangen;</span><span class="sxs-lookup"><span data-stu-id="5a3c4-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="5a3c4-333">wordt opnieuw uitgebracht in april 2020 en wordt niet vervangen door nieuwere updates om toekomstige beschikbaarheid te behouden.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="5a3c4-334">wordt gecategoriseerd als een update vanwege de herstartvereiste; en</span><span class="sxs-lookup"><span data-stu-id="5a3c4-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="5a3c4-335">wordt alleen aangeboden met [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="5a3c4-336">November-2019 (Platform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="5a3c4-337">Versie van beveiligingsinformatieupdate: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="5a3c4-338">Uitgebracht: **7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="5a3c4-339">Platform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="5a3c4-340">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="5a3c4-341">Ondersteuningsfase: **Geen ondersteuning**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="5a3c4-342">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="5a3c4-342">What's new</span></span>

- <span data-ttu-id="5a3c4-343">MpCmdRun-traceringsniveau opgelost</span><span class="sxs-lookup"><span data-stu-id="5a3c4-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="5a3c4-344">Versiegegevens van WDFilter opgelost</span><span class="sxs-lookup"><span data-stu-id="5a3c4-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="5a3c4-345">Meldingen verbeteren (PUA)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="5a3c4-346">MRT-logboeken toevoegen om bestanden te ondersteunen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="5a3c4-347">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-347">Known Issues</span></span>
<span data-ttu-id="5a3c4-348">Wanneer deze update is geïnstalleerd, heeft het apparaat het jump-pakket 4.10.2001.10 nodig om te kunnen bijwerken naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="5a3c4-349">Ondersteuning voor Microsoft Defender Antivirus-platform</span><span class="sxs-lookup"><span data-stu-id="5a3c4-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="5a3c4-350">Platform- en motorupdates worden geleverd op een maandelijkse cadans.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="5a3c4-351">Als u volledig wilt worden ondersteund, blijft u op de hoogte van de meest recente platformupdates.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="5a3c4-352">Onze ondersteuningsstructuur is dynamisch en verandert in twee fasen, afhankelijk van de beschikbaarheid van de nieuwste platformversie:</span><span class="sxs-lookup"><span data-stu-id="5a3c4-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="5a3c4-353">**Servicefase beveiligings-** en kritieke updates: wanneer u de nieuwste platformversie gebruikt, komt u in aanmerking voor zowel beveiligings- als kritieke updates voor het anti-malwareplatform.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="5a3c4-354">**Technische ondersteuning (alleen) fase:** nadat een nieuwe platformversie is uitgebracht, wordt de ondersteuning voor oudere versies (N-2) beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="5a3c4-355">Platformversies die ouder zijn dan N-2, worden niet meer ondersteund.\*</span><span class="sxs-lookup"><span data-stu-id="5a3c4-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="5a3c4-356">\* Technische ondersteuning blijft beschikbaar voor upgrades van de Versie van Windows 10 (zie Platformversie inbegrepen bij [Windows 10-versies)](#platform-version-included-with-windows-10-releases)naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="5a3c4-357">Tijdens de fase van technische ondersteuning (alleen) worden commercieel redelijke ondersteuningsincidenten verstrekt via Microsoft Customer Service & Support en beheerde ondersteuningsaanbiedingen van Microsoft (zoals Premier Support).</span><span class="sxs-lookup"><span data-stu-id="5a3c4-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="5a3c4-358">Als voor een ondersteuningsincident escalatie nodig is voor de ontwikkeling voor verdere richtlijnen, een niet-beveiligingsupdate vereist is of een beveiligingsupdate vereist, wordt klanten gevraagd een upgrade uit te voeren naar de nieuwste platformversie of een tussentijdse update (\*).</span><span class="sxs-lookup"><span data-stu-id="5a3c4-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="5a3c4-359">Platformversie inbegrepen bij Windows 10-versies</span><span class="sxs-lookup"><span data-stu-id="5a3c4-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="5a3c4-360">De onderstaande tabel bevat het Microsoft Defender Antivirus-platform en de engineversies die worden geleverd met de nieuwste Windows 10-versies:</span><span class="sxs-lookup"><span data-stu-id="5a3c4-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="5a3c4-361">Windows 10-release</span><span class="sxs-lookup"><span data-stu-id="5a3c4-361">Windows 10 release</span></span>  |<span data-ttu-id="5a3c4-362">Platformversie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-362">Platform version</span></span>  |<span data-ttu-id="5a3c4-363">Engine-versie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-363">Engine version</span></span> |<span data-ttu-id="5a3c4-364">Ondersteuningsfase</span><span class="sxs-lookup"><span data-stu-id="5a3c4-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="5a3c4-365">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="5a3c4-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="5a3c4-366">4.18.1909.6</span></span> |<span data-ttu-id="5a3c4-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="5a3c4-367">1.1.17000.2</span></span> | <span data-ttu-id="5a3c4-368">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5a3c4-369">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-369">1909  (19H2)</span></span> |<span data-ttu-id="5a3c4-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="5a3c4-370">4.18.1902.5</span></span> |<span data-ttu-id="5a3c4-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="5a3c4-371">1.1.16700.3</span></span> | <span data-ttu-id="5a3c4-372">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5a3c4-373">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-373">1903  (19H1)</span></span> |<span data-ttu-id="5a3c4-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="5a3c4-374">4.18.1902.5</span></span> |<span data-ttu-id="5a3c4-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="5a3c4-375">1.1.15600.4</span></span> | <span data-ttu-id="5a3c4-376">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5a3c4-377">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-377">1809  (RS5)</span></span> |<span data-ttu-id="5a3c4-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="5a3c4-378">4.18.1807.18075</span></span> |<span data-ttu-id="5a3c4-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="5a3c4-379">1.1.15000.2</span></span> | <span data-ttu-id="5a3c4-380">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5a3c4-381">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-381">1803  (RS4)</span></span> |<span data-ttu-id="5a3c4-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="5a3c4-382">4.13.17134.1</span></span> |<span data-ttu-id="5a3c4-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="5a3c4-383">1.1.14600.4</span></span> | <span data-ttu-id="5a3c4-384">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5a3c4-385">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-385">1709  (RS3)</span></span> |<span data-ttu-id="5a3c4-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="5a3c4-386">4.12.16299.15</span></span> |<span data-ttu-id="5a3c4-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="5a3c4-387">1.1.14104.0</span></span> | <span data-ttu-id="5a3c4-388">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5a3c4-389">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-389">1703  (RS2)</span></span> |<span data-ttu-id="5a3c4-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="5a3c4-390">4.11.15603.2</span></span> |<span data-ttu-id="5a3c4-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="5a3c4-391">1.1.13504.0</span></span> | <span data-ttu-id="5a3c4-392">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5a3c4-393">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-393">1607 (RS1)</span></span> |<span data-ttu-id="5a3c4-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="5a3c4-394">4.10.14393.3683</span></span> |<span data-ttu-id="5a3c4-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="5a3c4-395">1.1.12805.0</span></span> | <span data-ttu-id="5a3c4-396">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="5a3c4-397">Zie het windows [lifecycle factsheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)voor releasegegevens van Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="5a3c4-398">Updates voor implementatie van image Servicing and Management (DISM)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="5a3c4-399">We raden u aan om uw installatieafbeeldingen van Windows 10 (Enterprise, Pro en Home), Windows Server 2019 en Windows Server 2016 OS-installatieafbeeldingen bij te werken met de nieuwste antivirus- en antimalware-updates.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="5a3c4-400">Als u de installatieafbeeldingen van uw besturingssysteem up-to-date houdt, voorkomt u een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="5a3c4-401">Zie Installatieafbeeldingen van [microsoft Defender-update voor Windows-besturingssysteem voor meer informatie.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="5a3c4-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="5a3c4-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="5a3c4-403">&ensp;Pakketversie: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="5a3c4-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="5a3c4-404">&ensp;Platformversie: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="5a3c4-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="5a3c4-405">&ensp;Engine-versie: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="5a3c4-406">&ensp;Handtekeningversie: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5a3c4-407">Fixes</span><span class="sxs-lookup"><span data-stu-id="5a3c4-407">Fixes</span></span>
- <span data-ttu-id="5a3c4-408">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5a3c4-409">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-409">Additional information</span></span>
- <span data-ttu-id="5a3c4-410">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5a3c4-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="5a3c4-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="5a3c4-412">&ensp;Pakketversie: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="5a3c4-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="5a3c4-413">&ensp;Platformversie: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="5a3c4-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="5a3c4-414">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="5a3c4-415">&ensp;Handtekeningversie: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5a3c4-416">Fixes</span><span class="sxs-lookup"><span data-stu-id="5a3c4-416">Fixes</span></span>
- <span data-ttu-id="5a3c4-417">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5a3c4-418">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-418">Additional information</span></span>
- <span data-ttu-id="5a3c4-419">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5a3c4-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="5a3c4-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="5a3c4-421">&ensp;Pakketversie: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="5a3c4-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="5a3c4-422">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="5a3c4-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="5a3c4-423">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="5a3c4-424">&ensp;Handtekeningversie: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5a3c4-425">Fixes</span><span class="sxs-lookup"><span data-stu-id="5a3c4-425">Fixes</span></span>
- <span data-ttu-id="5a3c4-426">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5a3c4-427">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-427">Additional information</span></span>
- <span data-ttu-id="5a3c4-428">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5a3c4-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="5a3c4-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="5a3c4-430">&ensp;Pakketversie: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="5a3c4-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="5a3c4-431">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="5a3c4-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="5a3c4-432">&ensp;Motorversie: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="5a3c4-433">&ensp;Handtekeningversie: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5a3c4-434">Fixes</span><span class="sxs-lookup"><span data-stu-id="5a3c4-434">Fixes</span></span>
- <span data-ttu-id="5a3c4-435">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5a3c4-436">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-436">Additional information</span></span>
- <span data-ttu-id="5a3c4-437">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5a3c4-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="5a3c4-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="5a3c4-439">&ensp;Pakketversie: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="5a3c4-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="5a3c4-440">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="5a3c4-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="5a3c4-441">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="5a3c4-442">&ensp;Handtekeningversie: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5a3c4-443">Fixes</span><span class="sxs-lookup"><span data-stu-id="5a3c4-443">Fixes</span></span>
- <span data-ttu-id="5a3c4-444">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5a3c4-445">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-445">Additional information</span></span>
- <span data-ttu-id="5a3c4-446">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5a3c4-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="5a3c4-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="5a3c4-448">&ensp;Pakketversie: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="5a3c4-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="5a3c4-449">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="5a3c4-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="5a3c4-450">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="5a3c4-451">&ensp;Handtekeningversie: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5a3c4-452">Fixes</span><span class="sxs-lookup"><span data-stu-id="5a3c4-452">Fixes</span></span>
- <span data-ttu-id="5a3c4-453">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5a3c4-454">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-454">Additional information</span></span>
- <span data-ttu-id="5a3c4-455">Vernieuwde Microsoft Defender Antivirus-handtekeningen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5a3c4-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="5a3c4-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="5a3c4-457">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="5a3c4-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="5a3c4-458">&ensp;Platformversie: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="5a3c4-459">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="5a3c4-460">&ensp;Handtekeningversie: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5a3c4-461">Fixes</span><span class="sxs-lookup"><span data-stu-id="5a3c4-461">Fixes</span></span>
- <span data-ttu-id="5a3c4-462">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5a3c4-463">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-463">Additional information</span></span>
- <span data-ttu-id="5a3c4-464">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5a3c4-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="5a3c4-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="5a3c4-466">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="5a3c4-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="5a3c4-467">&ensp;Platformversie: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="5a3c4-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="5a3c4-468">&ensp;Motorversie: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="5a3c4-469">&ensp;Handtekeningversie: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="5a3c4-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5a3c4-470">Fixes</span><span class="sxs-lookup"><span data-stu-id="5a3c4-470">Fixes</span></span>
- <span data-ttu-id="5a3c4-471">Geen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5a3c4-472">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="5a3c4-472">Additional information</span></span>
- <span data-ttu-id="5a3c4-473">Ondersteuning toegevoegd voor Windows 10 RS1 of hoger installatieafbeeldingen voor besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="5a3c4-474">Aanvullende bronnen</span><span class="sxs-lookup"><span data-stu-id="5a3c4-474">Additional resources</span></span>

| <span data-ttu-id="5a3c4-475">Artikel</span><span class="sxs-lookup"><span data-stu-id="5a3c4-475">Article</span></span> | <span data-ttu-id="5a3c4-476">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5a3c4-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="5a3c4-477">Installatieafbeeldingen van Microsoft Defender-update voor Windows-besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="5a3c4-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="5a3c4-478">Controleer antimalware-updatepakketten voor installatieafbeeldingen van uw besturingssysteem (WIM- en VHD-bestanden).</span><span class="sxs-lookup"><span data-stu-id="5a3c4-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="5a3c4-479">Microsoft Defender Antivirus-updates downloaden voor Windows 10 (enterprise-, pro- en startversies), Windows Server 2019 en Installatieafbeeldingen van Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="5a3c4-480">Beheren hoe beveiligingsupdates worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="5a3c4-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="5a3c4-481">Beveiligingsupdates kunnen via veel bronnen worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="5a3c4-482">Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="5a3c4-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="5a3c4-483">U kunt plannen wanneer beveiligingsupdates moeten worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="5a3c4-484">Updates beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="5a3c4-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="5a3c4-485">Als een eindpunt een update of geplande scan mist, kunt u een update forcen of scannen wanneer een gebruiker zich de volgende keer meldt.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="5a3c4-486">Op basis van gebeurtenissen afgedwongen updates beheren</span><span class="sxs-lookup"><span data-stu-id="5a3c4-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="5a3c4-487">U kunt instellen dat beveiligingsupdates worden gedownload bij het opstarten of na bepaalde beveiligingsgebeurtenissen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="5a3c4-488">Updates beheren voor mobiele apparaten en virtuele machines (VM's)</span><span class="sxs-lookup"><span data-stu-id="5a3c4-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="5a3c4-489">U kunt instellingen opgeven, zoals of er updates moeten worden uitgevoerd op batterijvermogen, die vooral handig zijn voor mobiele apparaten en virtuele machines.</span><span class="sxs-lookup"><span data-stu-id="5a3c4-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
