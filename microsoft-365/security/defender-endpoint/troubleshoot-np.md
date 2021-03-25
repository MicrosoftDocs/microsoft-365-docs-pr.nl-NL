---
title: Problemen met netwerkbeveiliging oplossen
description: Resources en voorbeeldcode om problemen met netwerkbeveiliging in Microsoft Defender voor Eindpunt op te lossen.
keywords: probleemoplossing, fout, fix, windows defender, asr, regels, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, microsoft defender for endpoint, microsoft defender advanced threat protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.date: 01/26/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 34bebddcf052a643529f1d2b8a8a869a0ffe4a91
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183815"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="8cd7f-104">Problemen met netwerkbeveiliging oplossen</span><span class="sxs-lookup"><span data-stu-id="8cd7f-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8cd7f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8cd7f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8cd7f-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="8cd7f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8cd7f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8cd7f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8cd7f-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8cd7f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8cd7f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="8cd7f-110">Wanneer u [netwerkbeveiliging gebruikt,](network-protection.md) kunnen er problemen zijn, zoals:</span><span class="sxs-lookup"><span data-stu-id="8cd7f-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="8cd7f-111">Netwerkbeveiliging blokkeert een veilige website (onwaar positief)</span><span class="sxs-lookup"><span data-stu-id="8cd7f-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="8cd7f-112">Netwerkbeveiliging blokkeert een verdachte of bekende schadelijke website (onwaar negatief)</span><span class="sxs-lookup"><span data-stu-id="8cd7f-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="8cd7f-113">Er zijn vier stappen om deze problemen op te lossen:</span><span class="sxs-lookup"><span data-stu-id="8cd7f-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="8cd7f-114">Vereisten bevestigen</span><span class="sxs-lookup"><span data-stu-id="8cd7f-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="8cd7f-115">Controlemodus gebruiken om de regel te testen</span><span class="sxs-lookup"><span data-stu-id="8cd7f-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="8cd7f-116">Uitsluitingen toevoegen voor de opgegeven regel (voor onwaar-positieven)</span><span class="sxs-lookup"><span data-stu-id="8cd7f-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="8cd7f-117">Ondersteuningslogboeken verzenden</span><span class="sxs-lookup"><span data-stu-id="8cd7f-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="8cd7f-118">Vereisten bevestigen</span><span class="sxs-lookup"><span data-stu-id="8cd7f-118">Confirm prerequisites</span></span>

<span data-ttu-id="8cd7f-119">Netwerkbeveiliging werkt alleen op apparaten met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="8cd7f-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="8cd7f-120">Eindpunten worden uitgevoerd met Windows 10 Pro- of Enterprise-versie, versie 1709 of hoger.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="8cd7f-121">Eindpunten gebruiken Microsoft Defender Antivirus als de enige antivirusbeveiligings-app.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="8cd7f-122">[Bekijk wat er gebeurt wanneer u een niet-Microsoft-antivirusoplossing gebruikt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="8cd7f-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="8cd7f-123">[Realtime beveiliging](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="8cd7f-124">[Beveiliging in de cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="8cd7f-125">De controlemodus is niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-125">Audit mode is not enabled.</span></span> <span data-ttu-id="8cd7f-126">Gebruik [Groepsbeleid om](enable-network-protection.md#group-policy) de regel in te stellen **op Uitgeschakeld** (waarde: **0**).</span><span class="sxs-lookup"><span data-stu-id="8cd7f-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="8cd7f-127">Controlemodus gebruiken</span><span class="sxs-lookup"><span data-stu-id="8cd7f-127">Use audit mode</span></span>

<span data-ttu-id="8cd7f-128">U kunt netwerkbeveiliging inschakelen in de auditmodus en vervolgens naar een website gaan die we hebben gemaakt om de functie te demo's.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="8cd7f-129">Alle websiteverbindingen worden toegestaan door netwerkbeveiliging, maar een gebeurtenis wordt geregistreerd om een verbinding aan te geven die zou zijn geblokkeerd als netwerkbeveiliging was ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="8cd7f-130">Netwerkbeveiliging instellen op **auditmodus.**</span><span class="sxs-lookup"><span data-stu-id="8cd7f-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="8cd7f-131">Voer de verbindingsactiviteit uit die een probleem veroorzaakt (bijvoorbeeld proberen de site te bezoeken of verbinding te maken met het IP-adres dat u wel of niet wilt blokkeren).</span><span class="sxs-lookup"><span data-stu-id="8cd7f-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="8cd7f-132">[Bekijk de logboeken voor netwerkbeveiliging om](network-protection.md#review-network-protection-events-in-windows-event-viewer) te zien of de verbinding door de functie is geblokkeerd als deze is ingesteld op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8cd7f-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="8cd7f-133">Als netwerkbeveiliging een verbinding die u verwacht niet blokkeert, blokkeert, kunt u de functie inschakelen.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="8cd7f-134">Een onwaar positief of onwaar negatief rapporteren</span><span class="sxs-lookup"><span data-stu-id="8cd7f-134">Report a false positive or false negative</span></span>

<span data-ttu-id="8cd7f-135">Als u de functie hebt getest met de demosite en met de auditmodus en netwerkbeveiliging werkt aan vooraf geconfigureerde scenario's, maar niet werkt zoals verwacht voor een specifieke verbinding, gebruikt u het webinzendingsformulier van [Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) om een onwaar negatief of onwaar positief voor netwerkbeveiliging te melden.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="8cd7f-136">Met een E5-abonnement kunt u ook een koppeling naar [een bijbehorende waarschuwing geven.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="8cd7f-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="8cd7f-137">Zie [Fout-positieve/negatieven adresseert in Microsoft Defender voor Eindpunt.](defender-endpoint-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="8cd7f-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="8cd7f-138">Website uitsluiten van netwerkbeveiligingsbereik</span><span class="sxs-lookup"><span data-stu-id="8cd7f-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="8cd7f-139">Als u de geblokkeerde website wilt toestaan (onwaar positief), voegt u de URL toe aan de [lijst met vertrouwde sites.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)</span><span class="sxs-lookup"><span data-stu-id="8cd7f-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="8cd7f-140">Webbronnen uit deze lijst omzeilen de netwerkbeveiligingscontrole.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="8cd7f-141">Diagnostische gegevens verzamelen voor bestandsinzendingen</span><span class="sxs-lookup"><span data-stu-id="8cd7f-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="8cd7f-142">Wanneer u een probleem met netwerkbeveiliging rapporteert, wordt u gevraagd diagnostische gegevens te verzamelen en te verzenden die kunnen worden gebruikt door microsoft-ondersteunings- en technische teams om problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="8cd7f-143">Open een opdrachtprompt met verhoogde opdracht en wijzig in de Windows Defender-adreslijst:</span><span class="sxs-lookup"><span data-stu-id="8cd7f-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="8cd7f-144">Voer deze opdracht uit om de diagnostische logboeken te genereren:</span><span class="sxs-lookup"><span data-stu-id="8cd7f-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="8cd7f-145">Standaard worden ze opgeslagen in C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-145">By default, they are saved to C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab.</span></span> <span data-ttu-id="8cd7f-146">Voeg het bestand toe aan het inzendingsformulier.</span><span class="sxs-lookup"><span data-stu-id="8cd7f-146">Attach the file to the submission form.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8cd7f-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8cd7f-147">Related topics</span></span>

- [<span data-ttu-id="8cd7f-148">Netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="8cd7f-148">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="8cd7f-149">Netwerkbeveiliging evalueren</span><span class="sxs-lookup"><span data-stu-id="8cd7f-149">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="8cd7f-150">Netwerkbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="8cd7f-150">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="8cd7f-151">False positives/negatives in Defender for Endpoint adresseert</span><span class="sxs-lookup"><span data-stu-id="8cd7f-151">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
