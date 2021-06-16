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
ms.date: 06/14/2021
ms.openlocfilehash: 1c7ff52398e048aa34fd9c5ab3d8edd1004ea5ec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929441"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="e4f7c-104">Updates Microsoft Defender Antivirus en basislijnen toepassen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="e4f7c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-105">**Applies to:**</span></span>

- [<span data-ttu-id="e4f7c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e4f7c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="e4f7c-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="e4f7c-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="e4f7c-108">Het Microsoft Defender Antivirus up-to-date houden is essentieel om ervoor te zorgen dat uw apparaten de nieuwste technologie en functies hebben die nodig zijn om te beschermen tegen nieuwe malware en aanvalstechnieken.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="e4f7c-109">Zorg ervoor dat u uw antivirusbeveiliging bij werkt, zelfs als Microsoft Defender Antivirus actief is in [de passieve modus.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="e4f7c-110">Er zijn twee soorten updates die betrekking hebben op het up-to-date Microsoft Defender Antivirus houden:</span><span class="sxs-lookup"><span data-stu-id="e4f7c-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="e4f7c-111">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="e4f7c-111">Security intelligence updates</span></span>
- <span data-ttu-id="e4f7c-112">Productupdates</span><span class="sxs-lookup"><span data-stu-id="e4f7c-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="e4f7c-113">Als u de meest recente engine, platform en handtekeningdatum wilt zien, gaat u naar de beveiligingsinformatieupdates voor Microsoft Defender Antivirus [en andere Microsoft-antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="e4f7c-114">Beveiligingsintelligentie-updates</span><span class="sxs-lookup"><span data-stu-id="e4f7c-114">Security intelligence updates</span></span>

<span data-ttu-id="e4f7c-115">Microsoft Defender Antivirus gebruikt beveiliging in de cloud (ook wel de Microsoft Advanced Protection Service of KAARTEN genoemd) en downloadt regelmatig [beveiligingsinformatie-updates](cloud-protection-microsoft-defender-antivirus.md) om bescherming te bieden.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="e4f7c-116">Updates worden uitgebracht onder de onderstaande KB-nummers:</span><span class="sxs-lookup"><span data-stu-id="e4f7c-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="e4f7c-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="e4f7c-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="e4f7c-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="e4f7c-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="e4f7c-119">Beveiliging in de cloud is altijd actief en hiervoor is een actieve verbinding met internet vereist.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="e4f7c-120">Beveiligingsintelligentie-updates vinden plaats op een geplande cadans (configureerbaar via beleid).</span><span class="sxs-lookup"><span data-stu-id="e4f7c-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="e4f7c-121">Zie Microsoft [Cloud-beveiliging](cloud-protection-microsoft-defender-antivirus.md)gebruiken in Microsoft Defender Antivirus voor meer Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="e4f7c-122">Zie Beveiligingsinformatie-updates voor Microsoft Defender Antivirus en andere Microsoft-antimalware voor een lijst met recente [beveiligingsinformatieupdates.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="e4f7c-123">Engine-updates worden opgenomen in beveiligingsinformatie-updates en worden maandelijks uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="e4f7c-124">Productupdates</span><span class="sxs-lookup"><span data-stu-id="e4f7c-124">Product updates</span></span>

<span data-ttu-id="e4f7c-125">Microsoft Defender Antivirus vereist [maandelijkse updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (ook wel *platformupdates* genoemd) en ontvangen belangrijke functieupdates naast Windows 10 releases.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="e4f7c-126">U kunt de distributie van updates beheren via een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="e4f7c-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="e4f7c-127">Windows Serverupdateservice (WSUS)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="e4f7c-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e4f7c-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="e4f7c-129">De gebruikelijke methode die u gebruikt om Microsoft te implementeren en Windows te installeren op eindpunten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="e4f7c-130">Zie De bronnen voor [beveiligingsupdates Microsoft Defender Antivirus beheren voor meer informatie.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="e4f7c-131">Maandelijkse updates worden gefaseerd uitgebracht, wat resulteert in meerdere pakketten die zichtbaar zijn in [uw Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="e4f7c-132">Maandelijkse platform- en engineversies</span><span class="sxs-lookup"><span data-stu-id="e4f7c-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="e4f7c-133">Zie Update voor Windows Defender [antimalwareplatform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)voor informatie over het bijwerken of installeren van de platformupdate.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="e4f7c-134">Al onze updates bevatten</span><span class="sxs-lookup"><span data-stu-id="e4f7c-134">All our updates contain</span></span> 
- <span data-ttu-id="e4f7c-135">prestatieverbeteringen;</span><span class="sxs-lookup"><span data-stu-id="e4f7c-135">performance improvements;</span></span>
- <span data-ttu-id="e4f7c-136">verbeteringen in de servicebaarheid; en</span><span class="sxs-lookup"><span data-stu-id="e4f7c-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="e4f7c-137">integratieverbeteringen (Cloud, [Microsoft 365 Defender).](/microsoft-365/security/defender/microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/><br/>
<details>
<summary> <span data-ttu-id="e4f7c-138">Mei-2021 (Platform: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="e4f7c-139">&ensp;Versie van beveiligingsinformatieupdate: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="e4f7c-140">&ensp;Uitgebracht: **3 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-140">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="e4f7c-141">&ensp;Platform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="e4f7c-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="e4f7c-143">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-144">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-144">What's new</span></span>
- <span data-ttu-id="e4f7c-145">Verbeteringen in [gedragscontrole](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="e4f7c-146">Functie [voor het filteren van meldingen](network-protection.md) voor vaste netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="e4f7c-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-147">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-147">Known Issues</span></span>
<span data-ttu-id="e4f7c-148">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4f7c-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="e4f7c-150">&ensp;Versie van beveiligingsinformatieupdate: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="e4f7c-151">&ensp;Uitgebracht: **26 april 2021**  (Engine: 1.1.18100.6 uitgebracht op 5 mei 2021) &ensp; Platform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-151">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="e4f7c-152">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="e4f7c-153">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-154">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-154">What's new</span></span>
- <span data-ttu-id="e4f7c-155">Aanvullende logica voor gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="e4f7c-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="e4f7c-156">Verbeterde detectie van keylogger in de kernelmodus</span><span class="sxs-lookup"><span data-stu-id="e4f7c-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-157">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-157">Known Issues</span></span>
<span data-ttu-id="e4f7c-158">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4f7c-159">Maart-2021 (Platform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="e4f7c-160">&ensp;Versie van beveiligingsinformatieupdate: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="e4f7c-161">&ensp;Uitgebracht: **2 april 2021**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-161">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="e4f7c-162">&ensp;Platform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="e4f7c-163">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="e4f7c-164">&ensp;Ondersteuningsfase: **Beveiligings- en kritieke updates**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-165">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-165">What's new</span></span>

- <span data-ttu-id="e4f7c-166">Verbetering van de engine Gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="e4f7c-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="e4f7c-167">Uitgebreide netwerkbeperking met brute-force-attack</span><span class="sxs-lookup"><span data-stu-id="e4f7c-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="e4f7c-168">Extra mislukte poging tot het maken van een poging tot geknoei wanneer [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e4f7c-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-169">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-169">Known Issues</span></span>
<span data-ttu-id="e4f7c-170">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="e4f7c-171">Eerdere versieupdates: Alleen ondersteuning voor technische upgrade</span><span class="sxs-lookup"><span data-stu-id="e4f7c-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="e4f7c-172">Nadat een nieuwe pakketversie is uitgebracht, wordt de ondersteuning voor de vorige twee versies beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="e4f7c-173">Versies die ouder zijn dan die in deze sectie worden weergegeven, en alleen beschikbaar zijn voor ondersteuning voor technische upgrades.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="e4f7c-174">Februari-2021 (Platform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="e4f7c-175">&ensp;Versie van beveiligingsinformatieupdate: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="e4f7c-176">&ensp;Uitgebracht: **9 maart 2021**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="e4f7c-177">&ensp;Platform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="e4f7c-178">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="e4f7c-179">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-180">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-180">What's new</span></span>

- <span data-ttu-id="e4f7c-181">Verbeterde serviceherstel door middel [van beveiliging tegen geknoei](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="e4f7c-182">Beveiligingsbereik voor tampers uitbreiden</span><span class="sxs-lookup"><span data-stu-id="e4f7c-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-183">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-183">Known Issues</span></span>
<span data-ttu-id="e4f7c-184">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4f7c-185">Januari-2021 (Platform: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="e4f7c-186">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="e4f7c-187">&ensp;Uitgebracht: **2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="e4f7c-188">&ensp;Platform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="e4f7c-189">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="e4f7c-190">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-191">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-191">What's new</span></span>

- <span data-ttu-id="e4f7c-192">Verbeteringen voor detectie van Shellcode-exploits</span><span class="sxs-lookup"><span data-stu-id="e4f7c-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="e4f7c-193">Meer zichtbaarheid voor pogingen tot het stelen van referenties</span><span class="sxs-lookup"><span data-stu-id="e4f7c-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="e4f7c-194">Verbeteringen in antitamperingfuncties in Microsoft Defender Antivirus services</span><span class="sxs-lookup"><span data-stu-id="e4f7c-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="e4f7c-195">Verbeterde ondersteuning voor ARM x64-emulatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="e4f7c-196">Oplossing: EDR Blokkeermelding blijft in de bedreigingsgeschiedenis staan nadat realtimebeveiliging eerste detectie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="e4f7c-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-197">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-197">Known Issues</span></span>
<span data-ttu-id="e4f7c-198">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4f7c-199">November-2020 (Platform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="e4f7c-200">&ensp;Versie van beveiligingsinformatieupdate: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="e4f7c-201">&ensp;Uitgebracht: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="e4f7c-202">&ensp;Platform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="e4f7c-203">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="e4f7c-204">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-205">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-205">What's new</span></span>

- <span data-ttu-id="e4f7c-206">Verbeterde [ondersteuning voor SmartScreen-statusregistratie](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-207">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-207">Known Issues</span></span>
<span data-ttu-id="e4f7c-208">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4f7c-209">Oktober-2020 (Platform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="e4f7c-210">&ensp;Versie van beveiligingsinformatieupdate: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="e4f7c-211">&ensp;Uitgebracht: **29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="e4f7c-212">&ensp;Platform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="e4f7c-213">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4f7c-214">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-215">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-215">What's new</span></span>

- <span data-ttu-id="e4f7c-216">Nieuwe beschrijvingen voor categorieën met speciale bedreigingen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="e4f7c-217">Verbeterde emulatiemogelijkheden</span><span class="sxs-lookup"><span data-stu-id="e4f7c-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="e4f7c-218">Verbeterde mogelijkheden voor het toestaan/blokkeren van hostadressen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="e4f7c-219">Nieuwe optie in Defender CSP om het samenvoegen van lokale gebruikersuitsluitingen te negeren</span><span class="sxs-lookup"><span data-stu-id="e4f7c-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-220">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-220">Known Issues</span></span>

<span data-ttu-id="e4f7c-221">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4f7c-222">September-2020 (Platform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="e4f7c-223">&ensp;Versie van beveiligingsinformatieupdate: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="e4f7c-224">&ensp;Uitgebracht: **1 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="e4f7c-225">&ensp;Platform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="e4f7c-226">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="e4f7c-227">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-228">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-228">What's new</span></span>

- <span data-ttu-id="e4f7c-229">Beheerdersmachtigingen zijn vereist om bestanden in quarantaine te herstellen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="e4f7c-230">XML-opgemaakte gebeurtenissen worden nu ondersteund</span><span class="sxs-lookup"><span data-stu-id="e4f7c-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="e4f7c-231">CSP-ondersteuning voor het negeren van uitsluitings samenvoegen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="e4f7c-232">Nieuwe beheerinterfaces voor:</span><span class="sxs-lookup"><span data-stu-id="e4f7c-232">New management interfaces for:</span></span>
   - <span data-ttu-id="e4f7c-233">UDP-inspectie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-233">UDP Inspection</span></span>
   - <span data-ttu-id="e4f7c-234">Netwerkbeveiliging op Server 2019</span><span class="sxs-lookup"><span data-stu-id="e4f7c-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="e4f7c-235">IP-adresuitsluitingen voor netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="e4f7c-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="e4f7c-236">Verbeterde zichtbaarheid van TPM-metingen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="e4f7c-237">Verbeterde Office VBA-module scannen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-238">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-238">Known Issues</span></span>

<span data-ttu-id="e4f7c-239">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="e4f7c-240">Augustus-2020 (Platform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="e4f7c-241">&ensp;Versie van beveiligingsinformatieupdate: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="e4f7c-242">&ensp;Uitgebracht: **27 augustus 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="e4f7c-243">&ensp;Platform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="e4f7c-244">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="e4f7c-245">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="e4f7c-246">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-246">What's new</span></span>

- <span data-ttu-id="e4f7c-247">Meer telemetriegebeurtenissen toevoegen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-247">Add more telemetry events</span></span>
- <span data-ttu-id="e4f7c-248">Verbeterde telemetrie scangebeurtenis</span><span class="sxs-lookup"><span data-stu-id="e4f7c-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="e4f7c-249">Verbeterde gedragscontrole voor geheugenscans</span><span class="sxs-lookup"><span data-stu-id="e4f7c-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="e4f7c-250">Verbeterde macrostreams scannen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="e4f7c-251">Toegevoegd `AMRunningMode` aan Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="e4f7c-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="e4f7c-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) wordt genegeerd.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="e4f7c-253">Microsoft Defender Antivirus wordt automatisch uitgeschakeld wanneer er een ander antivirusprogramma wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="e4f7c-254">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-254">Known Issues</span></span>
<span data-ttu-id="e4f7c-255">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4f7c-256">Juli-2020 (Platform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="e4f7c-257">&ensp;Versie van beveiligingsinformatieupdate: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="e4f7c-258">&ensp;Uitgebracht: **28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="e4f7c-259">&ensp;Platform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="e4f7c-260">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="e4f7c-261">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-262">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-262">What's new</span></span>

- <span data-ttu-id="e4f7c-263">Verbeterde telemetrie voor BITS</span><span class="sxs-lookup"><span data-stu-id="e4f7c-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="e4f7c-264">Verbeterde validatie van Authenticode-code ondertekeningscertificaat</span><span class="sxs-lookup"><span data-stu-id="e4f7c-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-265">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-265">Known Issues</span></span>
<span data-ttu-id="e4f7c-266">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4f7c-267">Juni-2020 (Platform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="e4f7c-268">&ensp;Versie van beveiligingsinformatieupdate: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="e4f7c-269">&ensp;Uitgebracht: **22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="e4f7c-270">&ensp;Platform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="e4f7c-271">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="e4f7c-272">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-273">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-273">What's new</span></span>

- <span data-ttu-id="e4f7c-274">Mogelijkheid om de locatie [van de ondersteuningslogboeken op te geven](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="e4f7c-275">Het overslaan van een agressieve inhaalscan in de passieve modus.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="e4f7c-276">Defender toestaan bij te werken op verbindingen met een datameter</span><span class="sxs-lookup"><span data-stu-id="e4f7c-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="e4f7c-277">Vaste prestaties afstemmen wanneer caching is uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="e4f7c-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="e4f7c-278">Vaste registerquery</span><span class="sxs-lookup"><span data-stu-id="e4f7c-278">Fixed registry query</span></span> 
- <span data-ttu-id="e4f7c-279">Randomisatie van scantime in ADMX opgelost</span><span class="sxs-lookup"><span data-stu-id="e4f7c-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-280">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-280">Known Issues</span></span>
<span data-ttu-id="e4f7c-281">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4f7c-282">Mei-2020 (Platform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="e4f7c-283">&ensp;Versie van beveiligingsinformatieupdate: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="e4f7c-284">&ensp;Uitgebracht: **26 mei 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="e4f7c-285">&ensp;Platform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="e4f7c-286">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="e4f7c-287">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-288">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-288">What's new</span></span>

- <span data-ttu-id="e4f7c-289">Verbeterde logboekregistratie voor scangebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-289">Improved logging for scan events</span></span>
- <span data-ttu-id="e4f7c-290">Verbeterde crashafhandeling in de gebruikersmodus.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="e4f7c-291">Gebeurtenistracing toegevoegd voor Tamper-beveiliging</span><span class="sxs-lookup"><span data-stu-id="e4f7c-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="e4f7c-292">AmSI-voorbeeldinzending opgelost</span><span class="sxs-lookup"><span data-stu-id="e4f7c-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="e4f7c-293">AmSI Cloud blokkeren opgelost</span><span class="sxs-lookup"><span data-stu-id="e4f7c-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="e4f7c-294">Installatielogboek voor beveiligingsupdates opgelost</span><span class="sxs-lookup"><span data-stu-id="e4f7c-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-295">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-295">Known Issues</span></span>
<span data-ttu-id="e4f7c-296">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4f7c-297">April-2020 (Platform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="e4f7c-298">&ensp;Versie van beveiligingsinformatieupdate: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="e4f7c-299">&ensp;Uitgebracht: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="e4f7c-300">&ensp;Platform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="e4f7c-301">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="e4f7c-302">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-303">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-303">What's new</span></span>
- <span data-ttu-id="e4f7c-304">Verbeteringen in WDfilter</span><span class="sxs-lookup"><span data-stu-id="e4f7c-304">WDfilter improvements</span></span>
- <span data-ttu-id="e4f7c-305">Meer actiebare gebeurtenisgegevens toevoegen om detectiegebeurtenissen voor surface reduction aan te vallen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="e4f7c-306">Vaste versiegegevens in diagnostische gegevens en WMI</span><span class="sxs-lookup"><span data-stu-id="e4f7c-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="e4f7c-307">Onjuiste platformversie in gebruikersinterface na platformupdate opgelost</span><span class="sxs-lookup"><span data-stu-id="e4f7c-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="e4f7c-308">Dynamic URL intel for Fileless threat protection</span><span class="sxs-lookup"><span data-stu-id="e4f7c-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="e4f7c-309">UEFI-scanfunctie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-309">UEFI scan capability</span></span>
- <span data-ttu-id="e4f7c-310">Logboekregistratie uitbreiden voor updates</span><span class="sxs-lookup"><span data-stu-id="e4f7c-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4f7c-311">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-311">Known Issues</span></span>
<span data-ttu-id="e4f7c-312">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4f7c-313">Maart-2020 (Platform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="e4f7c-314">&ensp;Versie van beveiligingsinformatieupdate: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="e4f7c-315">&ensp;Uitgebracht: **24 maart 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="e4f7c-316">&ensp;Platform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="e4f7c-317">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="e4f7c-318">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4f7c-319">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-319">What's new</span></span>

- <span data-ttu-id="e4f7c-320">Optie CPU-beperking toegevoegd aan [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="e4f7c-321">Diagnostische mogelijkheden verbeteren</span><span class="sxs-lookup"><span data-stu-id="e4f7c-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="e4f7c-322">time-out voor beveiligingsinformatie verminderen (5 min)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="e4f7c-323">Interne logfunctie voor AMSI-engine uitbreiden</span><span class="sxs-lookup"><span data-stu-id="e4f7c-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="e4f7c-324">Melding voor procesblokkering verbeteren</span><span class="sxs-lookup"><span data-stu-id="e4f7c-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e4f7c-325">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-325">Known Issues</span></span>
<span data-ttu-id="e4f7c-326">[**Opgelost**] Microsoft Defender Antivirus wordt bestanden overgeslagen tijdens het uitvoeren van een scan.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="e4f7c-327">Februari-2020 (Platform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="e4f7c-328">&ensp;Versie van beveiligingsinformatieupdate: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="e4f7c-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="e4f7c-329">&ensp;Uitgebracht: **25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="e4f7c-330">&ensp;Platform/client: **-**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="e4f7c-331">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="e4f7c-332">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="e4f7c-333">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="e4f7c-334">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-334">Known Issues</span></span>
<span data-ttu-id="e4f7c-335">Geen bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4f7c-336">Januari-2020 (Platform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="e4f7c-337">Versie van beveiligingsinformatieupdate: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="e4f7c-338">Uitgebracht: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="e4f7c-339">Platform/client: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="e4f7c-340">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="e4f7c-341">&ensp;Ondersteuningsfase: **Ondersteuning voor technische upgrade (alleen)**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="e4f7c-342">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-342">What's new</span></span>

- <span data-ttu-id="e4f7c-343">BSOD opgelost in WS2016 met Exchange</span><span class="sxs-lookup"><span data-stu-id="e4f7c-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="e4f7c-344">Ondersteuningsplatformupdates wanneer TMP wordt omgeleid naar netwerkpad</span><span class="sxs-lookup"><span data-stu-id="e4f7c-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="e4f7c-345">Platform- en engineversies worden toegevoegd aan [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="e4f7c-346">Update voor noodhandtekeningen uitbreiden [naar passieve modus](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="e4f7c-347">Fix 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="e4f7c-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e4f7c-348">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-348">Known Issues</span></span>

<span data-ttu-id="e4f7c-349">[**Opgelost**] apparaten die gebruikmaken van [de moderne stand-bymodus,](/windows-hardware/design/device-experiences/modern-standby) kunnen last hebben van de Windows Defender filtert stuurprogramma, wat resulteert in een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="e4f7c-350">Getroffen machines worden voor de klant weergegeven als niet bijgewerkt naar het nieuwste antimalwareplatform.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="e4f7c-351">Deze update is:</span><span class="sxs-lookup"><span data-stu-id="e4f7c-351">This update is:</span></span>
> - <span data-ttu-id="e4f7c-352">vereist door RS1-apparaten met een lagere versie van het platform ter ondersteuning van SHA2;</span><span class="sxs-lookup"><span data-stu-id="e4f7c-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="e4f7c-353">heeft een herstartvlag voor systemen met problemen met ophangen;</span><span class="sxs-lookup"><span data-stu-id="e4f7c-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="e4f7c-354">wordt opnieuw uitgebracht in april 2020 en wordt niet vervangen door nieuwere updates om toekomstige beschikbaarheid te behouden.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="e4f7c-355">wordt gecategoriseerd als een update vanwege de herstartvereiste; en</span><span class="sxs-lookup"><span data-stu-id="e4f7c-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="e4f7c-356">wordt alleen aangeboden met [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4f7c-357">November-2019 (Platform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="e4f7c-358">Versie van beveiligingsinformatieupdate: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="e4f7c-359">Uitgebracht: **7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="e4f7c-360">Platform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="e4f7c-361">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="e4f7c-362">Ondersteuningsfase: **Geen ondersteuning**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="e4f7c-363">Wat is er nieuw</span><span class="sxs-lookup"><span data-stu-id="e4f7c-363">What's new</span></span>

- <span data-ttu-id="e4f7c-364">MpCmdRun-traceringsniveau opgelost</span><span class="sxs-lookup"><span data-stu-id="e4f7c-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="e4f7c-365">Versiegegevens van WDFilter opgelost</span><span class="sxs-lookup"><span data-stu-id="e4f7c-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="e4f7c-366">Meldingen verbeteren (PUA)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="e4f7c-367">MRT-logboeken toevoegen om bestanden te ondersteunen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e4f7c-368">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-368">Known Issues</span></span>
<span data-ttu-id="e4f7c-369">Wanneer deze update is geïnstalleerd, moet het apparaat het jump-pakket 4.18.2001.10 gebruiken om te kunnen bijwerken naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-369">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="e4f7c-370">Microsoft Defender Antivirus platformondersteuning</span><span class="sxs-lookup"><span data-stu-id="e4f7c-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="e4f7c-371">Platform- en motorupdates worden geleverd op een maandelijkse cadans.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="e4f7c-372">Als u volledig wilt worden ondersteund, blijft u op de hoogte van de meest recente platformupdates.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="e4f7c-373">Onze ondersteuningsstructuur is dynamisch en verandert in twee fasen, afhankelijk van de beschikbaarheid van de nieuwste platformversie:</span><span class="sxs-lookup"><span data-stu-id="e4f7c-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="e4f7c-374">**Servicefase beveiligings-** en kritieke updates: wanneer u de nieuwste platformversie gebruikt, komt u in aanmerking voor zowel beveiligings- als kritieke updates voor het anti-malwareplatform.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="e4f7c-375">**Technische ondersteuning (alleen) fase:** nadat een nieuwe platformversie is uitgebracht, wordt de ondersteuning voor oudere versies (N-2) beperkt tot alleen technische ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="e4f7c-376">Platformversies die ouder zijn dan N-2, worden niet meer ondersteund.\*</span><span class="sxs-lookup"><span data-stu-id="e4f7c-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="e4f7c-377">\*Technische ondersteuning blijft beschikbaar voor upgrades van de Windows 10 releaseversie (zie Platformversie inbegrepen bij Windows 10 [releases)](#platform-version-included-with-windows-10-releases)naar de nieuwste platformversie.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="e4f7c-378">Tijdens de fase van technische ondersteuning (alleen) worden commercieel redelijke ondersteuningsincidenten verstrekt via Microsoft Customer Service & Support en beheerde ondersteuningsaanbiedingen van Microsoft (zoals Premier Support).</span><span class="sxs-lookup"><span data-stu-id="e4f7c-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="e4f7c-379">Als voor een ondersteuningsincident escalatie nodig is voor de ontwikkeling voor verdere richtlijnen, een niet-beveiligingsupdate vereist is of een beveiligingsupdate vereist, wordt klanten gevraagd een upgrade uit te voeren naar de nieuwste platformversie of een tussentijdse update (\*).</span><span class="sxs-lookup"><span data-stu-id="e4f7c-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="e4f7c-380">Platformversie inbegrepen bij Windows 10 releases</span><span class="sxs-lookup"><span data-stu-id="e4f7c-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="e4f7c-381">In de onderstaande tabel vindt u Microsoft Defender Antivirus platform- en engineversies die worden verzonden met de nieuwste Windows 10 releases:</span><span class="sxs-lookup"><span data-stu-id="e4f7c-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="e4f7c-382">Windows 10 release</span><span class="sxs-lookup"><span data-stu-id="e4f7c-382">Windows 10 release</span></span>  |<span data-ttu-id="e4f7c-383">Platformversie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-383">Platform version</span></span>  |<span data-ttu-id="e4f7c-384">Engine-versie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-384">Engine version</span></span> |<span data-ttu-id="e4f7c-385">Ondersteuningsfase</span><span class="sxs-lookup"><span data-stu-id="e4f7c-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e4f7c-386">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="e4f7c-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="e4f7c-387">4.18.1909.6</span></span> |<span data-ttu-id="e4f7c-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="e4f7c-388">1.1.17000.2</span></span> | <span data-ttu-id="e4f7c-389">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4f7c-390">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-390">1909  (19H2)</span></span> |<span data-ttu-id="e4f7c-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="e4f7c-391">4.18.1902.5</span></span> |<span data-ttu-id="e4f7c-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="e4f7c-392">1.1.16700.3</span></span> | <span data-ttu-id="e4f7c-393">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4f7c-394">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-394">1903  (19H1)</span></span> |<span data-ttu-id="e4f7c-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="e4f7c-395">4.18.1902.5</span></span> |<span data-ttu-id="e4f7c-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="e4f7c-396">1.1.15600.4</span></span> | <span data-ttu-id="e4f7c-397">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4f7c-398">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-398">1809  (RS5)</span></span> |<span data-ttu-id="e4f7c-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="e4f7c-399">4.18.1807.18075</span></span> |<span data-ttu-id="e4f7c-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="e4f7c-400">1.1.15000.2</span></span> | <span data-ttu-id="e4f7c-401">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4f7c-402">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-402">1803  (RS4)</span></span> |<span data-ttu-id="e4f7c-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="e4f7c-403">4.13.17134.1</span></span> |<span data-ttu-id="e4f7c-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="e4f7c-404">1.1.14600.4</span></span> | <span data-ttu-id="e4f7c-405">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4f7c-406">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-406">1709  (RS3)</span></span> |<span data-ttu-id="e4f7c-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="e4f7c-407">4.12.16299.15</span></span> |<span data-ttu-id="e4f7c-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="e4f7c-408">1.1.14104.0</span></span> | <span data-ttu-id="e4f7c-409">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4f7c-410">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-410">1703  (RS2)</span></span> |<span data-ttu-id="e4f7c-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="e4f7c-411">4.11.15603.2</span></span> |<span data-ttu-id="e4f7c-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="e4f7c-412">1.1.13504.0</span></span> | <span data-ttu-id="e4f7c-413">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4f7c-414">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-414">1607 (RS1)</span></span> |<span data-ttu-id="e4f7c-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="e4f7c-415">4.10.14393.3683</span></span> |<span data-ttu-id="e4f7c-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="e4f7c-416">1.1.12805.0</span></span> | <span data-ttu-id="e4f7c-417">Ondersteuning voor technische upgrade (alleen)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="e4f7c-418">Zie het Windows het Windows 10 voor meer informatie over [de release.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="e4f7c-419">Updates voor implementatie van image Servicing and Management (DISM)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="e4f7c-420">U wordt aangeraden uw Windows 10 (Enterprise-, Pro- en Home-edities), Windows Server 2019 en Windows Server 2016-installatieafbeeldingen van het besturingssysteem bij te werken met de nieuwste antivirus- en antimalware-updates.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="e4f7c-421">Als u de installatieafbeeldingen van uw besturingssysteem up-to-date houdt, voorkomt u een gat in beveiliging.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="e4f7c-422">Zie Microsoft Defender update voor Windows [installatieafbeeldingen](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)van het besturingssysteem voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="e4f7c-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="e4f7c-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="e4f7c-424">&ensp;Pakketversie: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="e4f7c-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="e4f7c-425">&ensp;Platformversie: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="e4f7c-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="e4f7c-426">&ensp;Engine versie: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="e4f7c-427">&ensp;Handtekeningversie: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4f7c-428">Fixes</span><span class="sxs-lookup"><span data-stu-id="e4f7c-428">Fixes</span></span>
- <span data-ttu-id="e4f7c-429">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4f7c-430">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-430">Additional information</span></span>
- <span data-ttu-id="e4f7c-431">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4f7c-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="e4f7c-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="e4f7c-433">&ensp;Pakketversie: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="e4f7c-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="e4f7c-434">&ensp;Platformversie: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="e4f7c-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="e4f7c-435">&ensp;Engine versie: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="e4f7c-436">&ensp;Handtekeningversie: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4f7c-437">Fixes</span><span class="sxs-lookup"><span data-stu-id="e4f7c-437">Fixes</span></span>
- <span data-ttu-id="e4f7c-438">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4f7c-439">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-439">Additional information</span></span>
- <span data-ttu-id="e4f7c-440">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4f7c-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="e4f7c-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="e4f7c-442">&ensp;Pakketversie: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="e4f7c-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="e4f7c-443">&ensp;Platformversie: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="e4f7c-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="e4f7c-444">&ensp;Engine-versie: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="e4f7c-445">&ensp;Handtekeningversie: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4f7c-446">Fixes</span><span class="sxs-lookup"><span data-stu-id="e4f7c-446">Fixes</span></span>
- <span data-ttu-id="e4f7c-447">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4f7c-448">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-448">Additional information</span></span>
- <span data-ttu-id="e4f7c-449">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4f7c-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="e4f7c-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="e4f7c-451">&ensp;Pakketversie: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="e4f7c-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="e4f7c-452">&ensp;Platformversie: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="e4f7c-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="e4f7c-453">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="e4f7c-454">&ensp;Handtekeningversie: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4f7c-455">Fixes</span><span class="sxs-lookup"><span data-stu-id="e4f7c-455">Fixes</span></span>
- <span data-ttu-id="e4f7c-456">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4f7c-457">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-457">Additional information</span></span>
- <span data-ttu-id="e4f7c-458">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4f7c-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="e4f7c-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="e4f7c-460">&ensp;Pakketversie: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="e4f7c-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="e4f7c-461">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="e4f7c-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="e4f7c-462">&ensp;Motorversie: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="e4f7c-463">&ensp;Handtekeningversie: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4f7c-464">Fixes</span><span class="sxs-lookup"><span data-stu-id="e4f7c-464">Fixes</span></span>
- <span data-ttu-id="e4f7c-465">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4f7c-466">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-466">Additional information</span></span>
- <span data-ttu-id="e4f7c-467">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4f7c-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="e4f7c-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="e4f7c-469">&ensp;Pakketversie: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="e4f7c-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="e4f7c-470">&ensp;Platformversie: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="e4f7c-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="e4f7c-471">&ensp;Motorversie: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="e4f7c-472">&ensp;Handtekeningversie: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4f7c-473">Fixes</span><span class="sxs-lookup"><span data-stu-id="e4f7c-473">Fixes</span></span>
- <span data-ttu-id="e4f7c-474">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4f7c-475">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-475">Additional information</span></span>
- <span data-ttu-id="e4f7c-476">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4f7c-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="e4f7c-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="e4f7c-478">&ensp;Pakketversie: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="e4f7c-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="e4f7c-479">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="e4f7c-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="e4f7c-480">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4f7c-481">&ensp;Handtekeningversie: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4f7c-482">Fixes</span><span class="sxs-lookup"><span data-stu-id="e4f7c-482">Fixes</span></span>
- <span data-ttu-id="e4f7c-483">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4f7c-484">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-484">Additional information</span></span>
- <span data-ttu-id="e4f7c-485">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4f7c-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="e4f7c-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="e4f7c-487">&ensp;Pakketversie: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="e4f7c-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="e4f7c-488">&ensp;Platformversie: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="e4f7c-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="e4f7c-489">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4f7c-490">&ensp;Handtekeningversie: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4f7c-491">Fixes</span><span class="sxs-lookup"><span data-stu-id="e4f7c-491">Fixes</span></span>
- <span data-ttu-id="e4f7c-492">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4f7c-493">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-493">Additional information</span></span>
- <span data-ttu-id="e4f7c-494">Vernieuwde Microsoft Defender Antivirus handtekeningen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4f7c-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="e4f7c-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="e4f7c-496">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="e4f7c-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="e4f7c-497">&ensp;Platformversie: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="e4f7c-498">&ensp;Engine versie: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4f7c-499">&ensp;Handtekeningversie: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4f7c-500">Fixes</span><span class="sxs-lookup"><span data-stu-id="e4f7c-500">Fixes</span></span>
- <span data-ttu-id="e4f7c-501">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4f7c-502">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-502">Additional information</span></span>
- <span data-ttu-id="e4f7c-503">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4f7c-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="e4f7c-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="e4f7c-505">&ensp;Pakketversie: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="e4f7c-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="e4f7c-506">&ensp;Platformversie: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="e4f7c-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="e4f7c-507">&ensp;Motorversie: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="e4f7c-508">&ensp;Handtekeningversie: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="e4f7c-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4f7c-509">Fixes</span><span class="sxs-lookup"><span data-stu-id="e4f7c-509">Fixes</span></span>
- <span data-ttu-id="e4f7c-510">Geen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4f7c-511">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="e4f7c-511">Additional information</span></span>
- <span data-ttu-id="e4f7c-512">Ondersteuning toegevoegd voor Windows 10 RS1- of hoger os-installatieafbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="e4f7c-513">Aanvullende bronnen</span><span class="sxs-lookup"><span data-stu-id="e4f7c-513">Additional resources</span></span>

| <span data-ttu-id="e4f7c-514">Artikel</span><span class="sxs-lookup"><span data-stu-id="e4f7c-514">Article</span></span> | <span data-ttu-id="e4f7c-515">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="e4f7c-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="e4f7c-516">Microsoft Defender-update voor Windows installatieafbeeldingen van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="e4f7c-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="e4f7c-517">Controleer antimalware-updatepakketten voor installatieafbeeldingen van uw besturingssysteem (WIM- en VHD-bestanden).</span><span class="sxs-lookup"><span data-stu-id="e4f7c-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="e4f7c-518">Ontvang Microsoft Defender Antivirus updates voor Windows 10 (Enterprise, Pro en Home editions), Windows Server 2019 en Windows Server 2016 installatieafbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="e4f7c-519">Beheren hoe beveiligingsupdates worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="e4f7c-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="e4f7c-520">Beveiligingsupdates kunnen via veel bronnen worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="e4f7c-521">Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast</span><span class="sxs-lookup"><span data-stu-id="e4f7c-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="e4f7c-522">U kunt plannen wanneer beveiligingsupdates moeten worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="e4f7c-523">Updates beheren voor eindpunten die verouderd zijn</span><span class="sxs-lookup"><span data-stu-id="e4f7c-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="e4f7c-524">Als een eindpunt een update of geplande scan mist, kunt u een update forcen of scannen wanneer een gebruiker zich de volgende keer meldt.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="e4f7c-525">Op basis van gebeurtenissen afgedwongen updates beheren</span><span class="sxs-lookup"><span data-stu-id="e4f7c-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="e4f7c-526">U kunt instellen dat beveiligingsupdates worden gedownload bij het opstarten of na bepaalde beveiligingsgebeurtenissen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="e4f7c-527">Updates beheren voor mobiele apparaten en virtuele machines (VM's)</span><span class="sxs-lookup"><span data-stu-id="e4f7c-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="e4f7c-528">U kunt instellingen opgeven, zoals of er updates moeten worden uitgevoerd op batterijvermogen, die vooral handig zijn voor mobiele apparaten en virtuele machines.</span><span class="sxs-lookup"><span data-stu-id="e4f7c-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
