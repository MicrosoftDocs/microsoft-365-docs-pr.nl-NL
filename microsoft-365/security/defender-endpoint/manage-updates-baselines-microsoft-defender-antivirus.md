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
ms.date: 06/04/2021
ms.openlocfilehash: a1b7891e9e397e7345eb73a94d6298a9da781d98
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795980"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="33169-104">Updates Microsoft Defender Antivirus en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="33169-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="33169-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="33169-105">**Applies to:**</span></span>

- [<span data-ttu-id="33169-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="33169-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="33169-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="33169-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="33169-108">Er zijn twee soorten updates die betrekking hebben op het up-to-date Microsoft Defender Antivirus houden:</span><span class="sxs-lookup"><span data-stu-id="33169-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="33169-109">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="33169-109">Security intelligence updates</span></span>
- <span data-ttu-id="33169-110">Productupdates</span><span class="sxs-lookup"><span data-stu-id="33169-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33169-111">Het Microsoft Defender Antivirus up-to-date houden is essentieel om ervoor te zorgen dat uw apparaten de nieuwste technologie en functies hebben die nodig zijn om te beschermen tegen nieuwe malware en aanvalstechnieken.</span><span class="sxs-lookup"><span data-stu-id="33169-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="33169-112">Zorg ervoor dat u uw antivirusbeveiliging bij werkt, zelfs als Microsoft Defender Antivirus actief is in [de passieve modus.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="33169-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="33169-113">Als u de meest recente datum van de engine, het platform en de handtekening wilt zien, gaat u naar de beveiligingsintelligentie-updates voor Microsoft Defender Antivirus [en andere Microsoft-antimalware.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="33169-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="33169-114">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="33169-114">Security intelligence updates</span></span>

<span data-ttu-id="33169-115">Microsoft Defender Antivirus gebruikt beveiliging in de cloud (ook wel de Microsoft Advanced Protection Service of KAARTEN genoemd) en downloadt regelmatig [beveiligingsinformatie-updates](cloud-protection-microsoft-defender-antivirus.md) om bescherming te bieden.</span><span class="sxs-lookup"><span data-stu-id="33169-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="33169-116">Updates worden uitgebracht onder de onderstaande KB-nummers:</span><span class="sxs-lookup"><span data-stu-id="33169-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="33169-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="33169-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="33169-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="33169-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="33169-119">Beveiliging in de cloud is altijd actief en hiervoor is een actieve verbinding met internet vereist.</span><span class="sxs-lookup"><span data-stu-id="33169-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="33169-120">Beveiligingsintelligentie-updates vinden plaats op een geplande cadans (configureerbaar via beleid).</span><span class="sxs-lookup"><span data-stu-id="33169-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="33169-121">Zie Microsoft [Cloud-beveiliging](cloud-protection-microsoft-defender-antivirus.md)gebruiken in Microsoft Defender Antivirus voor meer Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="33169-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="33169-122">Zie Beveiligingsinformatie-updates voor Microsoft Defender Antivirus en andere Microsoft-antimalware voor een lijst met recente [beveiligingsinformatieupdates.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="33169-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="33169-123">Engine-updates worden opgenomen in beveiligingsinformatie-updates en worden maandelijks uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="33169-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="33169-124">Productupdates</span><span class="sxs-lookup"><span data-stu-id="33169-124">Product updates</span></span>

<span data-ttu-id="33169-125">Microsoft Defender Antivirus vereist [maandelijkse updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (ook wel *platformupdates* genoemd) en ontvangen belangrijke functieupdates naast Windows 10 releases.</span><span class="sxs-lookup"><span data-stu-id="33169-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="33169-126">U kunt de distributie van updates beheren via een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="33169-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="33169-127">Windows Serverupdateservice (WSUS)</span><span class="sxs-lookup"><span data-stu-id="33169-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="33169-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="33169-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="33169-129">De gebruikelijke methode die u gebruikt om Microsoft te implementeren en Windows te installeren op eindpunten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="33169-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="33169-130">Zie De bronnen voor [beveiligingsupdates Microsoft Defender Antivirus beheren voor meer informatie.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="33169-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="33169-131">Maandelijkse updates worden gefaseerd uitgebracht, wat resulteert in meerdere pakketten die zichtbaar zijn in [uw Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="33169-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="33169-132">Maandelijkse platform- en engineversies</span><span class="sxs-lookup"><span data-stu-id="33169-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="33169-133">Zie Update voor Windows Defender [antimalwareplatform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)voor informatie over het bijwerken of installeren van de platformupdate.</span><span class="sxs-lookup"><span data-stu-id="33169-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="33169-134">Al onze updates bevatten</span><span class="sxs-lookup"><span data-stu-id="33169-134">All our updates contain</span></span> 
- <span data-ttu-id="33169-135">prestatieverbeteringen;</span><span class="sxs-lookup"><span data-stu-id="33169-135">performance improvements;</span></span>
- <span data-ttu-id="33169-136">verbeteringen in de servicebaarheid; en</span><span class="sxs-lookup"><span data-stu-id="33169-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="33169-137">integratieverbeteringen (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="33169-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="33169-138">Mei-2021 (Platform: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="33169-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="33169-139">&ensp;Versie van beveiligingsinformatieupdate: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="33169-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="33169-140">&ensp;Uitgebracht: **4 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="33169-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="33169-141">&ensp;Platform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="33169-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="33169-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="33169-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="33169-143">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="33169-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-144">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-144">What's new</span></span>
- <span data-ttu-id="33169-145">Verbeteringen in [gedragscontrole](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="33169-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="33169-146">Functie [voor het filteren van meldingen](network-protection.md) voor vaste netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="33169-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-147">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-147">Known Issues</span></span>
<span data-ttu-id="33169-148">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="33169-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="33169-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="33169-150">&ensp;Versie van beveiligingsinformatieupdate: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="33169-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="33169-151">&ensp;Uitgebracht: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="33169-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="33169-152">&ensp;Platform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="33169-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="33169-153">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="33169-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="33169-154">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="33169-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-155">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-155">What's new</span></span>
- <span data-ttu-id="33169-156">Aanvullende logica voor gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="33169-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="33169-157">Verbeterde detectie van keylogger in de kernelmodus</span><span class="sxs-lookup"><span data-stu-id="33169-157">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-158">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-158">Known Issues</span></span>
<span data-ttu-id="33169-159">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="33169-160">Maart-2021 (Platform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="33169-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="33169-161">&ensp;Versie van beveiligingsinformatieupdate: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="33169-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="33169-162">&ensp;Uitgebracht: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="33169-162">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="33169-163">&ensp;Platform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="33169-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="33169-164">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="33169-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="33169-165">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="33169-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-166">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-166">What's new</span></span>

- <span data-ttu-id="33169-167">Verbetering van de engine Gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="33169-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="33169-168">Uitgebreide netwerkbeperking met brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="33169-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="33169-169">Extra mislukte poging tot het maken van een poging tot geknoei wanneer [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="33169-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-170">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-170">Known Issues</span></span>
<span data-ttu-id="33169-171">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="33169-172">Eerdere versieupdates: Alleen ondersteuning voor technische upgrade</span><span class="sxs-lookup"><span data-stu-id="33169-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="33169-173">Nadat een nieuwe pakketversie is uitgebracht, wordt de ondersteuning voor de vorige twee versies beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="33169-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="33169-174">Versies die ouder zijn dan die in deze sectie worden weergegeven, en alleen beschikbaar zijn voor ondersteuning voor technische upgrades.</span><span class="sxs-lookup"><span data-stu-id="33169-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="33169-175">Februari-2021 (Platform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="33169-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="33169-176">&ensp;Versie van beveiligingsinformatieupdate: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="33169-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="33169-177">&ensp;Uitgebracht: **9 maart 2021**</span><span class="sxs-lookup"><span data-stu-id="33169-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="33169-178">&ensp;Platform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="33169-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="33169-179">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="33169-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="33169-180">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-181">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-181">What's new</span></span>

- <span data-ttu-id="33169-182">Verbeterde serviceherstel door middel [van beveiliging tegen geknoei](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="33169-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="33169-183">Beveiligingsbereik voor tampers uitbreiden</span><span class="sxs-lookup"><span data-stu-id="33169-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-184">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-184">Known Issues</span></span>
<span data-ttu-id="33169-185">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="33169-186">Januari-2021 (Platform: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="33169-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="33169-187">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="33169-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="33169-188">&ensp;Uitgebracht: **2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="33169-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="33169-189">&ensp;Platform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="33169-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="33169-190">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="33169-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="33169-191">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-192">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-192">What's new</span></span>

- <span data-ttu-id="33169-193">Verbeteringen voor detectie van Shellcode-exploits</span><span class="sxs-lookup"><span data-stu-id="33169-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="33169-194">Meer zichtbaarheid voor pogingen tot het stelen van referenties</span><span class="sxs-lookup"><span data-stu-id="33169-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="33169-195">Verbeteringen in antitamperingfuncties in Microsoft Defender Antivirus services</span><span class="sxs-lookup"><span data-stu-id="33169-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="33169-196">Verbeterde ondersteuning voor ARM x64-emulatie</span><span class="sxs-lookup"><span data-stu-id="33169-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="33169-197">Oplossing: EDR Blokkeermelding blijft in de bedreigingsgeschiedenis staan nadat realtimebeveiliging eerste detectie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="33169-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-198">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-198">Known Issues</span></span>
<span data-ttu-id="33169-199">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="33169-200">November-2020 (Platform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="33169-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="33169-201">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="33169-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="33169-202">&ensp;Uitgebracht: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="33169-203">&ensp;Platform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="33169-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="33169-204">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="33169-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="33169-205">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-206">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-206">What's new</span></span>

- <span data-ttu-id="33169-207">Verbeterde [ondersteuning voor SmartScreen-statusregistratie](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="33169-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-208">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-208">Known Issues</span></span>
<span data-ttu-id="33169-209">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="33169-210">Oktober-2020 (Platform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="33169-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="33169-211">&ensp;Versie van beveiligingsinformatieupdate: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="33169-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="33169-212">&ensp;Uitgebracht: **29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="33169-213">&ensp;Platform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="33169-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="33169-214">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="33169-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="33169-215">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-216">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-216">What's new</span></span>

- <span data-ttu-id="33169-217">Nieuwe beschrijvingen voor categorieën met speciale bedreigingen</span><span class="sxs-lookup"><span data-stu-id="33169-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="33169-218">Verbeterde emulatiemogelijkheden</span><span class="sxs-lookup"><span data-stu-id="33169-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="33169-219">Verbeterde mogelijkheden voor het toestaan/blokkeren van hostadressen</span><span class="sxs-lookup"><span data-stu-id="33169-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="33169-220">Nieuwe optie in Defender CSP om het samenvoegen van lokale gebruikersuitsluitingen te negeren</span><span class="sxs-lookup"><span data-stu-id="33169-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-221">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-221">Known Issues</span></span>

<span data-ttu-id="33169-222">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="33169-223">September-2020 (Platform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="33169-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="33169-224">&ensp;Versie van beveiligingsinformatieupdate: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="33169-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="33169-225">&ensp;Uitgebracht: **1 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="33169-226">&ensp;Platform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="33169-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="33169-227">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="33169-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="33169-228">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-229">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-229">What's new</span></span>

- <span data-ttu-id="33169-230">Beheerdersmachtigingen zijn vereist om bestanden in quarantaine te herstellen</span><span class="sxs-lookup"><span data-stu-id="33169-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="33169-231">XML-opgemaakte gebeurtenissen worden nu ondersteund</span><span class="sxs-lookup"><span data-stu-id="33169-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="33169-232">CSP-ondersteuning voor het negeren van uitsluitings samenvoegen</span><span class="sxs-lookup"><span data-stu-id="33169-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="33169-233">Nieuwe beheerinterfaces voor:</span><span class="sxs-lookup"><span data-stu-id="33169-233">New management interfaces for:</span></span>
   - <span data-ttu-id="33169-234">UDP-inspectie</span><span class="sxs-lookup"><span data-stu-id="33169-234">UDP Inspection</span></span>
   - <span data-ttu-id="33169-235">Netwerkbeveiliging op Server 2019</span><span class="sxs-lookup"><span data-stu-id="33169-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="33169-236">IP-adresuitsluitingen voor netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="33169-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="33169-237">Verbeterde zichtbaarheid van TPM-metingen</span><span class="sxs-lookup"><span data-stu-id="33169-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="33169-238">Verbeterde Office VBA-module scannen</span><span class="sxs-lookup"><span data-stu-id="33169-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-239">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-239">Known Issues</span></span>

<span data-ttu-id="33169-240">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="33169-241">Augustus-2020 (Platform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="33169-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="33169-242">&ensp;Versie van beveiligingsinformatieupdate: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="33169-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="33169-243">&ensp;Uitgebracht: **27 augustus 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="33169-244">&ensp;Platform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="33169-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="33169-245">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="33169-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="33169-246">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="33169-247">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-247">What's new</span></span>

- <span data-ttu-id="33169-248">Meer telemetriegebeurtenissen toevoegen</span><span class="sxs-lookup"><span data-stu-id="33169-248">Add more telemetry events</span></span>
- <span data-ttu-id="33169-249">Verbeterde telemetrie scangebeurtenis</span><span class="sxs-lookup"><span data-stu-id="33169-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="33169-250">Verbeterde gedragscontrole voor geheugenscans</span><span class="sxs-lookup"><span data-stu-id="33169-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="33169-251">Verbeterde macrostreams scannen</span><span class="sxs-lookup"><span data-stu-id="33169-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="33169-252">Toegevoegd `AMRunningMode` aan Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="33169-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="33169-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wordt genegeerd.</span><span class="sxs-lookup"><span data-stu-id="33169-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="33169-254">Microsoft Defender Antivirus wordt automatisch uitgeschakeld wanneer er een ander antivirusprogramma wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="33169-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="33169-255">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-255">Known Issues</span></span>
<span data-ttu-id="33169-256">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="33169-257">Juli-2020 (Platform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="33169-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="33169-258">&ensp;Versie van beveiligingsinformatieupdate: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="33169-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="33169-259">&ensp;Uitgebracht: **28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="33169-260">&ensp;Platform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="33169-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="33169-261">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="33169-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="33169-262">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-263">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-263">What's new</span></span>

- <span data-ttu-id="33169-264">Verbeterde telemetrie voor BITS</span><span class="sxs-lookup"><span data-stu-id="33169-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="33169-265">Verbeterde validatie van Authenticode-code ondertekeningscertificaat</span><span class="sxs-lookup"><span data-stu-id="33169-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-266">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-266">Known Issues</span></span>
<span data-ttu-id="33169-267">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="33169-268">Juni-2020 (Platform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="33169-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="33169-269">&ensp;Versie van beveiligingsinformatieupdate: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="33169-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="33169-270">&ensp;Uitgebracht: **22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="33169-271">&ensp;Platform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="33169-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="33169-272">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="33169-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="33169-273">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-274">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-274">What's new</span></span>

- <span data-ttu-id="33169-275">Mogelijkheid om de locatie [van de ondersteuningslogboeken op te geven](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="33169-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="33169-276">Het overslaan van een agressieve inhaalscan in de passieve modus.</span><span class="sxs-lookup"><span data-stu-id="33169-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="33169-277">Defender toestaan bij te werken op verbindingen met een datameter</span><span class="sxs-lookup"><span data-stu-id="33169-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="33169-278">Vaste prestaties afstemmen wanneer caching is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="33169-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="33169-279">Vaste registerquery</span><span class="sxs-lookup"><span data-stu-id="33169-279">Fixed registry query</span></span> 
- <span data-ttu-id="33169-280">Randomisatie van scantime in ADMX opgelost</span><span class="sxs-lookup"><span data-stu-id="33169-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-281">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-281">Known Issues</span></span>
<span data-ttu-id="33169-282">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="33169-283">Mei-2020 (Platform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="33169-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="33169-284">&ensp;Versie van beveiligingsinformatieupdate: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="33169-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="33169-285">&ensp;Uitgebracht: **26 mei 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="33169-286">&ensp;Platform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="33169-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="33169-287">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="33169-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="33169-288">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-289">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-289">What's new</span></span>

- <span data-ttu-id="33169-290">Verbeterde logboekregistratie voor scangebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="33169-290">Improved logging for scan events</span></span>
- <span data-ttu-id="33169-291">Verbeterde crashafhandeling in de gebruikersmodus.</span><span class="sxs-lookup"><span data-stu-id="33169-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="33169-292">Gebeurtenistracing toegevoegd voor Tamper-beveiliging</span><span class="sxs-lookup"><span data-stu-id="33169-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="33169-293">AmSI-voorbeeldinzending opgelost</span><span class="sxs-lookup"><span data-stu-id="33169-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="33169-294">AmSI Cloud blokkeren opgelost</span><span class="sxs-lookup"><span data-stu-id="33169-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="33169-295">Installatielogboek voor beveiligingsupdates opgelost</span><span class="sxs-lookup"><span data-stu-id="33169-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-296">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-296">Known Issues</span></span>
<span data-ttu-id="33169-297">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="33169-298">April-2020 (Platform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="33169-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="33169-299">&ensp;Versie van beveiligingsinformatieupdate: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="33169-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="33169-300">&ensp;Uitgebracht: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="33169-301">&ensp;Platform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="33169-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="33169-302">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="33169-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="33169-303">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-304">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-304">What's new</span></span>
- <span data-ttu-id="33169-305">Verbeteringen in WDfilter</span><span class="sxs-lookup"><span data-stu-id="33169-305">WDfilter improvements</span></span>
- <span data-ttu-id="33169-306">Meer actiebare gebeurtenisgegevens toevoegen om detectiegebeurtenissen voor surface reduction aan te vallen</span><span class="sxs-lookup"><span data-stu-id="33169-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="33169-307">Vaste versiegegevens in diagnostische gegevens en WMI</span><span class="sxs-lookup"><span data-stu-id="33169-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="33169-308">Onjuiste platformversie in gebruikersinterface na platformupdate opgelost</span><span class="sxs-lookup"><span data-stu-id="33169-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="33169-309">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="33169-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="33169-310">UEFI-scanfunctie</span><span class="sxs-lookup"><span data-stu-id="33169-310">UEFI scan capability</span></span>
- <span data-ttu-id="33169-311">Logboekregistratie uitbreiden voor updates</span><span class="sxs-lookup"><span data-stu-id="33169-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="33169-312">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-312">Known Issues</span></span>
<span data-ttu-id="33169-313">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="33169-314">Maart-2020 (Platform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="33169-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="33169-315">&ensp;Versie van beveiligingsinformatieupdate: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="33169-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="33169-316">&ensp;Uitgebracht: **24 maart 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="33169-317">&ensp;Platform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="33169-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="33169-318">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="33169-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="33169-319">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="33169-320">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-320">What's new</span></span>

- <span data-ttu-id="33169-321">Optie CPU-beperking toegevoegd aan [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="33169-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="33169-322">Diagnostische mogelijkheden verbeteren</span><span class="sxs-lookup"><span data-stu-id="33169-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="33169-323">time-out voor beveiligingsinformatie verminderen (5 min)</span><span class="sxs-lookup"><span data-stu-id="33169-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="33169-324">Interne logfunctie voor AMSI-engine uitbreiden</span><span class="sxs-lookup"><span data-stu-id="33169-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="33169-325">Melding voor procesblokkering verbeteren</span><span class="sxs-lookup"><span data-stu-id="33169-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="33169-326">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-326">Known Issues</span></span>
<span data-ttu-id="33169-327">[**Opgelost**] Microsoft Defender Antivirus wordt bestanden overgeslagen tijdens het uitvoeren van een scan.</span><span class="sxs-lookup"><span data-stu-id="33169-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="33169-328">Februari-2020 (Platform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="33169-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="33169-329">&ensp;Versie van beveiligingsinformatieupdate: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="33169-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="33169-330">&ensp;Uitgebracht: **25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="33169-331">&ensp;Platform/client: **-**</span><span class="sxs-lookup"><span data-stu-id="33169-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="33169-332">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="33169-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="33169-333">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="33169-334">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="33169-335">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-335">Known Issues</span></span>
<span data-ttu-id="33169-336">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="33169-337">Januari-2020 (Platform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="33169-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="33169-338">Versie van beveiligingsinformatieupdate: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="33169-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="33169-339">Uitgebracht: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="33169-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="33169-340">Platform/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="33169-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="33169-341">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="33169-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="33169-342">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="33169-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="33169-343">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-343">What's new</span></span>

- <span data-ttu-id="33169-344">BSOD opgelost in WS2016 met Exchange</span><span class="sxs-lookup"><span data-stu-id="33169-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="33169-345">Ondersteuningsplatformupdates wanneer TMP wordt omgeleid naar netwerkpad</span><span class="sxs-lookup"><span data-stu-id="33169-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="33169-346">Platform- en engineversies worden toegevoegd aan [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="33169-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="33169-347">Update voor noodhandtekeningen uitbreiden [naar passieve modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="33169-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="33169-348">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="33169-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="33169-349">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-349">Known Issues</span></span>

<span data-ttu-id="33169-350">[**Opgelost**] apparaten die gebruikmaken van [de moderne stand-bymodus,](/windows-hardware/design/device-experiences/modern-standby) kunnen last hebben van de Windows Defender filtert stuurprogramma, wat resulteert in een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="33169-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="33169-351">Getroffen machines worden voor de klant weergegeven als niet bijgewerkt naar het nieuwste antimalwareplatform.</span><span class="sxs-lookup"><span data-stu-id="33169-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="33169-352">Deze update is:</span><span class="sxs-lookup"><span data-stu-id="33169-352">This update is:</span></span>
> - <span data-ttu-id="33169-353">vereist door RS1-apparaten met een lagere versie van het platform ter ondersteuning van SHA2;</span><span class="sxs-lookup"><span data-stu-id="33169-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="33169-354">heeft een herstartvlag voor systemen met problemen met ophangen;</span><span class="sxs-lookup"><span data-stu-id="33169-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="33169-355">wordt opnieuw uitgebracht in april 2020 en wordt niet vervangen door nieuwere updates om toekomstige beschikbaarheid te behouden.</span><span class="sxs-lookup"><span data-stu-id="33169-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="33169-356">wordt gecategoriseerd als een update vanwege de herstartvereiste; en</span><span class="sxs-lookup"><span data-stu-id="33169-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="33169-357">wordt alleen aangeboden met [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="33169-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="33169-358">November-2019 (Platform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="33169-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="33169-359">Versie van beveiligingsinformatieupdate: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="33169-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="33169-360">Uitgebracht: **7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="33169-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="33169-361">Platform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="33169-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="33169-362">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="33169-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="33169-363">Ondersteuningsfase: **Geen ondersteuning**</span><span class="sxs-lookup"><span data-stu-id="33169-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="33169-364">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="33169-364">What's new</span></span>

- <span data-ttu-id="33169-365">MpCmdRun-traceringsniveau opgelost</span><span class="sxs-lookup"><span data-stu-id="33169-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="33169-366">Versiegegevens van WDFilter opgelost</span><span class="sxs-lookup"><span data-stu-id="33169-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="33169-367">Meldingen verbeteren (PUA)</span><span class="sxs-lookup"><span data-stu-id="33169-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="33169-368">MRT-logboeken toevoegen om bestanden te ondersteunen</span><span class="sxs-lookup"><span data-stu-id="33169-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="33169-369">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="33169-369">Known Issues</span></span>
<span data-ttu-id="33169-370">Wanneer deze update is geïnstalleerd, heeft het apparaat het jump-pakket 4.10.2001.10 nodig om te kunnen bijwerken naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="33169-370">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="33169-371">Microsoft Defender Antivirus platformondersteuning</span><span class="sxs-lookup"><span data-stu-id="33169-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="33169-372">Platform- en motorupdates worden geleverd op een maandelijkse cadans.</span><span class="sxs-lookup"><span data-stu-id="33169-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="33169-373">Als u volledig wilt worden ondersteund, blijft u op de hoogte van de meest recente platformupdates.</span><span class="sxs-lookup"><span data-stu-id="33169-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="33169-374">Onze ondersteuningsstructuur is dynamisch en verandert in twee fasen, afhankelijk van de beschikbaarheid van de nieuwste platformversie:</span><span class="sxs-lookup"><span data-stu-id="33169-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="33169-375">**Servicefase beveiligings-** en kritieke updates: wanneer u de nieuwste platformversie gebruikt, komt u in aanmerking voor zowel beveiligings- als kritieke updates voor het anti-malwareplatform.</span><span class="sxs-lookup"><span data-stu-id="33169-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="33169-376">**Technische ondersteuning (alleen) fase:** nadat een nieuwe platformversie is uitgebracht, wordt de ondersteuning voor oudere versies (N-2) beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="33169-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="33169-377">Platformversies die ouder zijn dan N-2, worden niet meer ondersteund.\*</span><span class="sxs-lookup"><span data-stu-id="33169-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="33169-378">\*Technische ondersteuning blijft beschikbaar voor upgrades van de Windows 10 releaseversie (zie Platformversie inbegrepen bij Windows 10 [releases)](#platform-version-included-with-windows-10-releases)naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="33169-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="33169-379">Tijdens de fase van technische ondersteuning (alleen) worden commercieel redelijke ondersteuningsincidenten verstrekt via Microsoft Customer Service & Support en beheerde ondersteuningsaanbiedingen van Microsoft (zoals Premier Support).</span><span class="sxs-lookup"><span data-stu-id="33169-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="33169-380">Als voor een ondersteuningsincident escalatie nodig is voor de ontwikkeling voor verdere richtlijnen, een niet-beveiligingsupdate vereist is of een beveiligingsupdate vereist, wordt klanten gevraagd een upgrade uit te voeren naar de nieuwste platformversie of een tussentijdse update (\*).</span><span class="sxs-lookup"><span data-stu-id="33169-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="33169-381">Platformversie inbegrepen bij Windows 10 releases</span><span class="sxs-lookup"><span data-stu-id="33169-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="33169-382">In de onderstaande tabel vindt u Microsoft Defender Antivirus platform- en engineversies die worden verzonden met de nieuwste Windows 10 releases:</span><span class="sxs-lookup"><span data-stu-id="33169-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="33169-383">Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="33169-383">Windows 10 release</span></span>  |<span data-ttu-id="33169-384">Platformversie</span><span class="sxs-lookup"><span data-stu-id="33169-384">Platform version</span></span>  |<span data-ttu-id="33169-385">Engine-versie</span><span class="sxs-lookup"><span data-stu-id="33169-385">Engine version</span></span> |<span data-ttu-id="33169-386">Ondersteuningsfase</span><span class="sxs-lookup"><span data-stu-id="33169-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="33169-387">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="33169-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="33169-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="33169-388">4.18.1909.6</span></span> |<span data-ttu-id="33169-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="33169-389">1.1.17000.2</span></span> | <span data-ttu-id="33169-390">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="33169-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="33169-391">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="33169-391">1909  (19H2)</span></span> |<span data-ttu-id="33169-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="33169-392">4.18.1902.5</span></span> |<span data-ttu-id="33169-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="33169-393">1.1.16700.3</span></span> | <span data-ttu-id="33169-394">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="33169-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="33169-395">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="33169-395">1903  (19H1)</span></span> |<span data-ttu-id="33169-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="33169-396">4.18.1902.5</span></span> |<span data-ttu-id="33169-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="33169-397">1.1.15600.4</span></span> | <span data-ttu-id="33169-398">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="33169-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="33169-399">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="33169-399">1809  (RS5)</span></span> |<span data-ttu-id="33169-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="33169-400">4.18.1807.18075</span></span> |<span data-ttu-id="33169-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="33169-401">1.1.15000.2</span></span> | <span data-ttu-id="33169-402">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="33169-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="33169-403">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="33169-403">1803  (RS4)</span></span> |<span data-ttu-id="33169-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="33169-404">4.13.17134.1</span></span> |<span data-ttu-id="33169-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="33169-405">1.1.14600.4</span></span> | <span data-ttu-id="33169-406">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="33169-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="33169-407">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="33169-407">1709  (RS3)</span></span> |<span data-ttu-id="33169-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="33169-408">4.12.16299.15</span></span> |<span data-ttu-id="33169-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="33169-409">1.1.14104.0</span></span> | <span data-ttu-id="33169-410">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="33169-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="33169-411">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="33169-411">1703  (RS2)</span></span> |<span data-ttu-id="33169-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="33169-412">4.11.15603.2</span></span> |<span data-ttu-id="33169-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="33169-413">1.1.13504.0</span></span> | <span data-ttu-id="33169-414">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="33169-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="33169-415">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="33169-415">1607 (RS1)</span></span> |<span data-ttu-id="33169-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="33169-416">4.10.14393.3683</span></span> |<span data-ttu-id="33169-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="33169-417">1.1.12805.0</span></span> | <span data-ttu-id="33169-418">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="33169-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="33169-419">Zie het Windows het Windows 10 voor meer informatie over [de release.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="33169-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="33169-420">Updates voor implementatie van image Servicing and Management (DISM)</span><span class="sxs-lookup"><span data-stu-id="33169-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="33169-421">U wordt aangeraden uw Windows 10 (Enterprise-, Pro- en Home-edities), Windows Server 2019 en Windows Server 2016-installatieafbeeldingen van het besturingssysteem bij te werken met de nieuwste antivirus- en antimalware-updates.</span><span class="sxs-lookup"><span data-stu-id="33169-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="33169-422">Als u de installatieafbeeldingen van uw besturingssysteem up-to-date houdt, voorkomt u een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="33169-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="33169-423">Zie Microsoft Defender update voor Windows [installatieafbeeldingen](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)van het besturingssysteem voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="33169-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="33169-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="33169-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="33169-425">&ensp;Pakketversie: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="33169-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="33169-426">&ensp;Platformversie: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="33169-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="33169-427">&ensp;Engine versie: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="33169-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="33169-428">&ensp;Handtekeningversie: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="33169-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="33169-429">Fixes</span><span class="sxs-lookup"><span data-stu-id="33169-429">Fixes</span></span>
- <span data-ttu-id="33169-430">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="33169-431">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="33169-431">Additional information</span></span>
- <span data-ttu-id="33169-432">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="33169-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="33169-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="33169-434">&ensp;Pakketversie: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="33169-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="33169-435">&ensp;Platformversie: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="33169-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="33169-436">&ensp;Engine versie: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="33169-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="33169-437">&ensp;Handtekeningversie: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="33169-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="33169-438">Fixes</span><span class="sxs-lookup"><span data-stu-id="33169-438">Fixes</span></span>
- <span data-ttu-id="33169-439">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="33169-440">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="33169-440">Additional information</span></span>
- <span data-ttu-id="33169-441">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="33169-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="33169-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="33169-443">&ensp;Pakketversie: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="33169-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="33169-444">&ensp;Platformversie: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="33169-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="33169-445">&ensp;Engine-versie: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="33169-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="33169-446">&ensp;Handtekeningversie: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="33169-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="33169-447">Fixes</span><span class="sxs-lookup"><span data-stu-id="33169-447">Fixes</span></span>
- <span data-ttu-id="33169-448">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="33169-449">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="33169-449">Additional information</span></span>
- <span data-ttu-id="33169-450">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="33169-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="33169-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="33169-452">&ensp;Pakketversie: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="33169-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="33169-453">&ensp;Platformversie: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="33169-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="33169-454">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="33169-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="33169-455">&ensp;Handtekeningversie: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="33169-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="33169-456">Fixes</span><span class="sxs-lookup"><span data-stu-id="33169-456">Fixes</span></span>
- <span data-ttu-id="33169-457">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="33169-458">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="33169-458">Additional information</span></span>
- <span data-ttu-id="33169-459">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="33169-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="33169-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="33169-461">&ensp;Pakketversie: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="33169-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="33169-462">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="33169-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="33169-463">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="33169-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="33169-464">&ensp;Handtekeningversie: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="33169-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="33169-465">Fixes</span><span class="sxs-lookup"><span data-stu-id="33169-465">Fixes</span></span>
- <span data-ttu-id="33169-466">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="33169-467">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="33169-467">Additional information</span></span>
- <span data-ttu-id="33169-468">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="33169-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="33169-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="33169-470">&ensp;Pakketversie: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="33169-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="33169-471">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="33169-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="33169-472">&ensp;Motorversie: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="33169-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="33169-473">&ensp;Handtekeningversie: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="33169-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="33169-474">Fixes</span><span class="sxs-lookup"><span data-stu-id="33169-474">Fixes</span></span>
- <span data-ttu-id="33169-475">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="33169-476">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="33169-476">Additional information</span></span>
- <span data-ttu-id="33169-477">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="33169-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="33169-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="33169-479">&ensp;Pakketversie: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="33169-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="33169-480">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="33169-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="33169-481">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="33169-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="33169-482">&ensp;Handtekeningversie: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="33169-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="33169-483">Fixes</span><span class="sxs-lookup"><span data-stu-id="33169-483">Fixes</span></span>
- <span data-ttu-id="33169-484">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="33169-485">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="33169-485">Additional information</span></span>
- <span data-ttu-id="33169-486">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="33169-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="33169-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="33169-488">&ensp;Pakketversie: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="33169-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="33169-489">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="33169-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="33169-490">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="33169-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="33169-491">&ensp;Handtekeningversie: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="33169-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="33169-492">Fixes</span><span class="sxs-lookup"><span data-stu-id="33169-492">Fixes</span></span>
- <span data-ttu-id="33169-493">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="33169-494">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="33169-494">Additional information</span></span>
- <span data-ttu-id="33169-495">Vernieuwde Microsoft Defender Antivirus handtekeningen</span><span class="sxs-lookup"><span data-stu-id="33169-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="33169-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="33169-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="33169-497">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="33169-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="33169-498">&ensp;Platformversie: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="33169-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="33169-499">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="33169-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="33169-500">&ensp;Handtekeningversie: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="33169-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="33169-501">Fixes</span><span class="sxs-lookup"><span data-stu-id="33169-501">Fixes</span></span>
- <span data-ttu-id="33169-502">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="33169-503">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="33169-503">Additional information</span></span>
- <span data-ttu-id="33169-504">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="33169-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="33169-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="33169-506">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="33169-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="33169-507">&ensp;Platformversie: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="33169-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="33169-508">&ensp;Motorversie: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="33169-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="33169-509">&ensp;Handtekeningversie: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="33169-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="33169-510">Fixes</span><span class="sxs-lookup"><span data-stu-id="33169-510">Fixes</span></span>
- <span data-ttu-id="33169-511">Geen</span><span class="sxs-lookup"><span data-stu-id="33169-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="33169-512">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="33169-512">Additional information</span></span>
- <span data-ttu-id="33169-513">Ondersteuning toegevoegd voor Windows 10 RS1- of hoger os-installatieafbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="33169-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="33169-514">Aanvullende bronnen</span><span class="sxs-lookup"><span data-stu-id="33169-514">Additional resources</span></span>

| <span data-ttu-id="33169-515">Artikel</span><span class="sxs-lookup"><span data-stu-id="33169-515">Article</span></span> | <span data-ttu-id="33169-516">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="33169-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="33169-517">Microsoft Defender-update voor Windows installatieafbeeldingen van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="33169-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="33169-518">Controleer antimalware-updatepakketten voor installatieafbeeldingen van uw besturingssysteem (WIM- en VHD-bestanden).</span><span class="sxs-lookup"><span data-stu-id="33169-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="33169-519">Ontvang Microsoft Defender Antivirus updates voor Windows 10 (Enterprise, Pro en Home editions), Windows Server 2019 en Windows Server 2016 installatieafbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="33169-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="33169-520">Beheren hoe beveiligingsupdates worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="33169-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="33169-521">Beveiligingsupdates kunnen via veel bronnen worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="33169-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="33169-522">Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="33169-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="33169-523">U kunt plannen wanneer beveiligingsupdates moeten worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="33169-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="33169-524">Updates beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="33169-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="33169-525">Als een eindpunt een update of geplande scan mist, kunt u een update forcen of scannen wanneer een gebruiker zich de volgende keer meldt.</span><span class="sxs-lookup"><span data-stu-id="33169-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="33169-526">Op basis van gebeurtenissen afgedwongen updates beheren</span><span class="sxs-lookup"><span data-stu-id="33169-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="33169-527">U kunt instellen dat beveiligingsupdates worden gedownload bij het opstarten of na bepaalde beveiligingsgebeurtenissen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="33169-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="33169-528">Updates beheren voor mobiele apparaten en virtuele machines (VM's)</span><span class="sxs-lookup"><span data-stu-id="33169-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="33169-529">U kunt instellingen opgeven, zoals of er updates moeten worden uitgevoerd op batterijvermogen, die vooral handig zijn voor mobiele apparaten en virtuele machines.</span><span class="sxs-lookup"><span data-stu-id="33169-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
