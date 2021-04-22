---
title: Problemen met netwerkbeveiliging oplossen
description: Resources en voorbeeldcode om problemen met netwerkbeveiliging in Microsoft Defender voor Eindpunt op te lossen.
keywords: probleemoplossing, fout, fix, windows defender bijvoorbeeld, asr, regels, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f77ce94fda63a9e7e8a9484a67a22eeec136d619
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935879"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="01ae4-104">Problemen met netwerkbeveiliging oplossen</span><span class="sxs-lookup"><span data-stu-id="01ae4-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="01ae4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="01ae4-105">**Applies to:**</span></span>
- [<span data-ttu-id="01ae4-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="01ae4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="01ae4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01ae4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="01ae4-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="01ae4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="01ae4-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="01ae4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="01ae4-110">Wanneer u [netwerkbeveiliging gebruikt,](network-protection.md) kunnen er problemen zijn, zoals:</span><span class="sxs-lookup"><span data-stu-id="01ae4-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="01ae4-111">Netwerkbeveiliging blokkeert een veilige website (onwaar positief)</span><span class="sxs-lookup"><span data-stu-id="01ae4-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="01ae4-112">Netwerkbeveiliging blokkeert een verdachte of bekende schadelijke website (onwaar negatief)</span><span class="sxs-lookup"><span data-stu-id="01ae4-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="01ae4-113">Er zijn vier stappen om deze problemen op te lossen:</span><span class="sxs-lookup"><span data-stu-id="01ae4-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="01ae4-114">Vereisten bevestigen</span><span class="sxs-lookup"><span data-stu-id="01ae4-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="01ae4-115">Controlemodus gebruiken om de regel te testen</span><span class="sxs-lookup"><span data-stu-id="01ae4-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="01ae4-116">Uitsluitingen toevoegen voor de opgegeven regel (voor onwaar-positieven)</span><span class="sxs-lookup"><span data-stu-id="01ae4-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="01ae4-117">Ondersteuningslogboeken verzenden</span><span class="sxs-lookup"><span data-stu-id="01ae4-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="01ae4-118">Vereisten bevestigen</span><span class="sxs-lookup"><span data-stu-id="01ae4-118">Confirm prerequisites</span></span>

<span data-ttu-id="01ae4-119">Netwerkbeveiliging werkt alleen op apparaten met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="01ae4-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="01ae4-120">Eindpunten worden uitgevoerd met Windows 10 Pro- of Enterprise-versie, versie 1709 of hoger.</span><span class="sxs-lookup"><span data-stu-id="01ae4-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="01ae4-121">Eindpunten gebruiken Microsoft Defender Antivirus als de enige antivirusbeveiligings-app.</span><span class="sxs-lookup"><span data-stu-id="01ae4-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="01ae4-122">[Bekijk wat er gebeurt wanneer u een niet-Microsoft-antivirusoplossing gebruikt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="01ae4-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="01ae4-123">[Realtime beveiliging](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="01ae4-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="01ae4-124">[Beveiliging in de cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="01ae4-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="01ae4-125">De controlemodus is niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="01ae4-125">Audit mode is not enabled.</span></span> <span data-ttu-id="01ae4-126">Gebruik [Groepsbeleid om](enable-network-protection.md#group-policy) de regel in te stellen **op Uitgeschakeld** (waarde: **0**).</span><span class="sxs-lookup"><span data-stu-id="01ae4-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="01ae4-127">Controlemodus gebruiken</span><span class="sxs-lookup"><span data-stu-id="01ae4-127">Use audit mode</span></span>

<span data-ttu-id="01ae4-128">U kunt netwerkbeveiliging inschakelen in de auditmodus en vervolgens naar een website gaan die we hebben gemaakt om de functie te demo's.</span><span class="sxs-lookup"><span data-stu-id="01ae4-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="01ae4-129">Alle websiteverbindingen worden toegestaan door netwerkbeveiliging, maar een gebeurtenis wordt geregistreerd om een verbinding aan te geven die zou zijn geblokkeerd als netwerkbeveiliging was ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="01ae4-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="01ae4-130">Netwerkbeveiliging instellen op **auditmodus.**</span><span class="sxs-lookup"><span data-stu-id="01ae4-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="01ae4-131">Voer de verbindingsactiviteit uit die een probleem veroorzaakt (bijvoorbeeld proberen de site te bezoeken of verbinding te maken met het IP-adres dat u wel of niet wilt blokkeren).</span><span class="sxs-lookup"><span data-stu-id="01ae4-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="01ae4-132">[Bekijk de logboeken voor netwerkbeveiliging om](network-protection.md#review-network-protection-events-in-windows-event-viewer) te zien of de verbinding door de functie is geblokkeerd als deze is ingesteld op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="01ae4-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="01ae4-133">Als netwerkbeveiliging een verbinding die u verwacht niet blokkeert, blokkeert, kunt u de functie inschakelen.</span><span class="sxs-lookup"><span data-stu-id="01ae4-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="01ae4-134">Een onwaar positief of onwaar negatief rapporteren</span><span class="sxs-lookup"><span data-stu-id="01ae4-134">Report a false positive or false negative</span></span>

<span data-ttu-id="01ae4-135">Als u de functie hebt getest met de demosite en met de auditmodus en netwerkbeveiliging werkt aan vooraf geconfigureerde scenario's, maar niet werkt zoals verwacht voor een specifieke verbinding, gebruikt u het webinzendingsformulier van [Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) om een onwaar negatief of onwaar positief voor netwerkbeveiliging te melden.</span><span class="sxs-lookup"><span data-stu-id="01ae4-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="01ae4-136">Met een E5-abonnement kunt u ook een koppeling naar [een bijbehorende waarschuwing geven.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="01ae4-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="01ae4-137">Zie [Fout-positieve/negatieven adresseert in Microsoft Defender voor Eindpunt.](defender-endpoint-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="01ae4-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="01ae4-138">Website uitsluiten van netwerkbeveiligingsbereik</span><span class="sxs-lookup"><span data-stu-id="01ae4-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="01ae4-139">Als u de geblokkeerde website wilt toestaan (onwaar positief), voegt u de URL toe aan de [lijst met vertrouwde sites.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)</span><span class="sxs-lookup"><span data-stu-id="01ae4-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="01ae4-140">Webbronnen uit deze lijst omzeilen de netwerkbeveiligingscontrole.</span><span class="sxs-lookup"><span data-stu-id="01ae4-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="01ae4-141">Diagnostische gegevens verzamelen voor bestandsinzendingen</span><span class="sxs-lookup"><span data-stu-id="01ae4-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="01ae4-142">Wanneer u een probleem met netwerkbeveiliging rapporteert, wordt u gevraagd diagnostische gegevens te verzamelen en te verzenden die kunnen worden gebruikt door microsoft-ondersteunings- en technische teams om problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="01ae4-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="01ae4-143">Open een opdrachtprompt met verhoogde opdracht en wijzig in de Windows Defender-adreslijst:</span><span class="sxs-lookup"><span data-stu-id="01ae4-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="01ae4-144">Voer deze opdracht uit om de diagnostische logboeken te genereren:</span><span class="sxs-lookup"><span data-stu-id="01ae4-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="01ae4-145">Voeg het bestand toe aan het inzendingsformulier.</span><span class="sxs-lookup"><span data-stu-id="01ae4-145">Attach the file to the submission form.</span></span> <span data-ttu-id="01ae4-146">Diagnostische logboeken worden standaard opgeslagen op `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="01ae4-146">By default, diagnostic logs are saved at `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a><span data-ttu-id="01ae4-147">Verbindingsproblemen met netwerkbeveiliging oplossen (voor E5-klanten)</span><span class="sxs-lookup"><span data-stu-id="01ae4-147">Resolve connectivity issues with network protection (for E5 customers)</span></span>

<span data-ttu-id="01ae4-148">Vanwege de omgeving waarin netwerkbeveiliging wordt uitgevoerd, kan Microsoft de proxy-instellingen van het besturingssysteem niet zien.</span><span class="sxs-lookup"><span data-stu-id="01ae4-148">Due to the environment where network protection runs, Microsoft is unable to see your operating system proxy settings.</span></span> <span data-ttu-id="01ae4-149">In sommige gevallen kunnen netwerkbeveiligings clients de cloudservice niet bereiken.</span><span class="sxs-lookup"><span data-stu-id="01ae4-149">In some cases, network protection clients are unable to reach the cloud service.</span></span> <span data-ttu-id="01ae4-150">Als u verbindingsproblemen met netwerkbeveiliging wilt oplossen, configureert u een van de volgende registersleutels, zodat netwerkbeveiliging op de hoogte wordt van de proxyconfiguratie:</span><span class="sxs-lookup"><span data-stu-id="01ae4-150">To resolve connectivity issues with network protection, configure one of the following registry keys so that network protection becomes aware of the proxy configuration:</span></span>

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

<span data-ttu-id="01ae4-151">---OR---</span><span class="sxs-lookup"><span data-stu-id="01ae4-151">---OR---</span></span>


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

<span data-ttu-id="01ae4-152">U kunt de registersleutel configureren met PowerShell, Microsoft Endpoint Manager of Groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="01ae4-152">You can configure the registry key by using PowerShell, Microsoft Endpoint Manager, or Group Policy.</span></span> <span data-ttu-id="01ae4-153">Hier zijn enkele bronnen die u kunt helpen:</span><span class="sxs-lookup"><span data-stu-id="01ae4-153">Here are some resources to help:</span></span>
- [<span data-ttu-id="01ae4-154">Werken met registersleutels</span><span class="sxs-lookup"><span data-stu-id="01ae4-154">Working with Registry Keys</span></span>](/powershell/scripting/samples/working-with-registry-keys)
- [<span data-ttu-id="01ae4-155">Aangepaste clientinstellingen configureren voor Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="01ae4-155">Configure custom client settings for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [<span data-ttu-id="01ae4-156">Groepsbeleidsinstellingen gebruiken om endpointbeveiliging te beheren</span><span class="sxs-lookup"><span data-stu-id="01ae4-156">Use Group Policy settings to manage Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a><span data-ttu-id="01ae4-157">Zie ook</span><span class="sxs-lookup"><span data-stu-id="01ae4-157">See also</span></span>

- [<span data-ttu-id="01ae4-158">Netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="01ae4-158">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="01ae4-159">Netwerkbeveiliging evalueren</span><span class="sxs-lookup"><span data-stu-id="01ae4-159">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="01ae4-160">Netwerkbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="01ae4-160">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="01ae4-161">False positives/negatives in Defender for Endpoint adresseert</span><span class="sxs-lookup"><span data-stu-id="01ae4-161">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
