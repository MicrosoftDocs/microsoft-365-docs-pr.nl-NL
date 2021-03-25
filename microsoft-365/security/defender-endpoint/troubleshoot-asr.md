---
title: Problemen met regels voor het verminderen van de surface-aanval oplossen
description: Resources en voorbeeldcode voor het oplossen van problemen met regels voor het verminderen van de surface attack in Microsoft Defender voor Eindpunt.
keywords: probleemoplossing, fout, fix, windows defender, asr, regels, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, microsoft defender for endpoint, microsoft defender advanced threat protection
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: d483c098f221e2d4d2e61a10393154b8f5d1498d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198739"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a><span data-ttu-id="295ef-104">Problemen met regels voor het verminderen van aanvallen oplossen</span><span class="sxs-lookup"><span data-stu-id="295ef-104">Troubleshoot attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="295ef-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="295ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="295ef-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="295ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="295ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="295ef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="295ef-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="295ef-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="295ef-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="295ef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="295ef-110">Wanneer u de [surface reduction-regels voor](attack-surface-reduction.md) aanvallen gebruikt, kunnen er problemen zijn, zoals:</span><span class="sxs-lookup"><span data-stu-id="295ef-110">When you use [attack surface reduction rules](attack-surface-reduction.md) you may run into issues, such as:</span></span>

- <span data-ttu-id="295ef-111">Een regel blokkeert een bestand, proces of voert een andere actie uit die niet mag worden uitgevoerd (onwaar positief)</span><span class="sxs-lookup"><span data-stu-id="295ef-111">A rule blocks a file, process, or performs some other action that it shouldn't (false positive)</span></span>

- <span data-ttu-id="295ef-112">Een regel werkt niet zoals beschreven, of blokkeert geen bestand of proces dat moet worden gebruikt (onwaar negatief)</span><span class="sxs-lookup"><span data-stu-id="295ef-112">A rule doesn't work as described, or doesn't block a file or process that it should (false negative)</span></span>

<span data-ttu-id="295ef-113">Er zijn vier stappen om deze problemen op te lossen:</span><span class="sxs-lookup"><span data-stu-id="295ef-113">There are four steps to troubleshooting these problems:</span></span>

1. [<span data-ttu-id="295ef-114">Vereisten bevestigen</span><span class="sxs-lookup"><span data-stu-id="295ef-114">Confirm prerequisites</span></span>](#confirm-prerequisites)

2. [<span data-ttu-id="295ef-115">Controlemodus gebruiken om de regel te testen</span><span class="sxs-lookup"><span data-stu-id="295ef-115">Use audit mode to test the rule</span></span>](#use-audit-mode-to-test-the-rule)

3. <span data-ttu-id="295ef-116">[Uitsluitingen toevoegen voor de opgegeven regel](#add-exclusions-for-a-false-positive) (voor onwaar-positieven)</span><span class="sxs-lookup"><span data-stu-id="295ef-116">[Add exclusions for the specified rule](#add-exclusions-for-a-false-positive) (for false positives)</span></span>

4. [<span data-ttu-id="295ef-117">Ondersteuningslogboeken verzenden</span><span class="sxs-lookup"><span data-stu-id="295ef-117">Submit support logs</span></span>](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a><span data-ttu-id="295ef-118">Vereisten bevestigen</span><span class="sxs-lookup"><span data-stu-id="295ef-118">Confirm prerequisites</span></span>

<span data-ttu-id="295ef-119">Surface Reduction-regels voor aanvallen werken alleen op apparaten met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="295ef-119">Attack surface reduction rules will only work on devices with the following conditions:</span></span>

- <span data-ttu-id="295ef-120">Eindpunten worden uitgevoerd met Windows 10 Enterprise, versie 1709 (ook wel de Fall Creators Update genoemd).</span><span class="sxs-lookup"><span data-stu-id="295ef-120">Endpoints are running Windows 10 Enterprise, version 1709 (also known as the Fall Creators Update).</span></span>

- <span data-ttu-id="295ef-121">Eindpunten gebruiken Microsoft Defender Antivirus als de enige antivirusbeveiligings-app.</span><span class="sxs-lookup"><span data-stu-id="295ef-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="295ef-122">[Als u een andere antivirus-app gebruikt,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)kan Microsoft Defender AV zichzelf uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="295ef-122">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

- <span data-ttu-id="295ef-123">[Realtime beveiliging](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="295ef-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>

- <span data-ttu-id="295ef-124">Controlemodus is niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="295ef-124">Audit mode isn't enabled.</span></span> <span data-ttu-id="295ef-125">Gebruik Groepsbeleid om de regel in te stellen **op Uitgeschakeld** (waarde: **0**) zoals beschreven in [Surface reduction rules voor aanvallen inschakelen.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="295ef-125">Use Group Policy to set the rule to **Disabled** (value: **0**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

<span data-ttu-id="295ef-126">Als aan deze vereisten is voldaan, gaat u verder met de volgende stap om de regel in de auditmodus te testen.</span><span class="sxs-lookup"><span data-stu-id="295ef-126">If these prerequisites have all been met, proceed to the next step to test the rule in audit mode.</span></span>

## <a name="use-audit-mode-to-test-the-rule"></a><span data-ttu-id="295ef-127">Controlemodus gebruiken om de regel te testen</span><span class="sxs-lookup"><span data-stu-id="295ef-127">Use audit mode to test the rule</span></span>

<span data-ttu-id="295ef-128">U kunt naar de website van Windows Defender Test ground bij [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) gaan om te bevestigen dat regels voor het verminderen van aanvallen over het algemeen werken voor vooraf geconfigureerde scenario's en processen op een apparaat, of u kunt de auditmodus gebruiken, zodat alleen regels kunnen worden gemeld.</span><span class="sxs-lookup"><span data-stu-id="295ef-128">You can visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm attack surface reduction rules are generally working for pre-configured scenarios and processes on a device, or you can use audit mode, which enables rules for reporting only.</span></span>

<span data-ttu-id="295ef-129">Volg deze instructies in [Het demoprogramma gebruiken](evaluate-attack-surface-reduction.md) om te zien hoe regels voor het verminderen van aanvallen werken om de specifieke regel te testen waarmee u problemen ondervindt.</span><span class="sxs-lookup"><span data-stu-id="295ef-129">Follow these instructions in [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span></span>

1. <span data-ttu-id="295ef-130">Schakel de auditmodus in voor de specifieke regel die u wilt testen.</span><span class="sxs-lookup"><span data-stu-id="295ef-130">Enable audit mode for the specific rule you want to test.</span></span> <span data-ttu-id="295ef-131">Gebruik Groepsbeleid om de regel in te stellen op **de auditmodus** (waarde: **2)** zoals beschreven in Regels voor het inschakelen van de [surface reduction van aanvallen.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="295ef-131">Use Group Policy to set the rule to **Audit mode** (value: **2**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span> <span data-ttu-id="295ef-132">Met de controlemodus kan de regel het bestand of proces rapporteren, maar kan deze nog steeds worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="295ef-132">Audit mode allows the rule to report the file or process, but will still allow it to run.</span></span>

2. <span data-ttu-id="295ef-133">Voer de activiteit uit die een probleem veroorzaakt (bijvoorbeeld het bestand of proces openen of uitvoeren dat moet worden geblokkeerd, maar wordt toegestaan).</span><span class="sxs-lookup"><span data-stu-id="295ef-133">Perform the activity that is causing an issue (for example, open or execute the file or process that should be blocked but is being allowed).</span></span>

3. <span data-ttu-id="295ef-134">[Bekijk de gebeurtenislogboeken van](attack-surface-reduction.md) de attack surface reduction rule om te zien of de regel het bestand of proces zou hebben geblokkeerd als de regel was ingesteld op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="295ef-134">[Review the attack surface reduction rule event logs](attack-surface-reduction.md) to see if the rule would have blocked the file or process if the rule had been set to **Enabled**.</span></span>

<span data-ttu-id="295ef-135">Als een regel een bestand of proces dat u verwacht, niet blokkeert, controleert u eerst of de auditmodus is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="295ef-135">If a rule isn't blocking a file or process that you're expecting it should block, first check if audit mode is enabled.</span></span>

<span data-ttu-id="295ef-136">De auditmodus is mogelijk ingeschakeld voor het testen van een andere functie, of door een geautomatiseerd PowerShell-script, en is mogelijk niet uitgeschakeld nadat de tests zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="295ef-136">Audit mode may have been enabled for testing another feature, or by an automated PowerShell script, and may not have been disabled after the tests were completed.</span></span>

<span data-ttu-id="295ef-137">Als u de regel hebt getest met het demoprogramma en met de auditmodus en de regels voor de beperking van de aanvalsoppervlakken werken aan vooraf geconfigureerde scenario's, maar de regel werkt niet zoals verwacht, gaat u naar een van de volgende secties op basis van uw situatie:</span><span class="sxs-lookup"><span data-stu-id="295ef-137">If you've tested the rule with the demo tool and with audit mode, and attack surface reduction rules are working on pre-configured scenarios, but the rule isn't working as expected, proceed to either of the following sections based on your situation:</span></span>

1. <span data-ttu-id="295ef-138">Als de surface reduction-regel voor aanvallen iets blokkeert dat niet mag worden geblokkeerd (ook wel een onwaar positief genoemd), kunt u eerst een uitsluitingsregel voor de beperking van het oppervlak van de aanval [toevoegen.](#add-exclusions-for-a-false-positive)</span><span class="sxs-lookup"><span data-stu-id="295ef-138">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can [first add an attack surface reduction rule exclusion](#add-exclusions-for-a-false-positive).</span></span>

2. <span data-ttu-id="295ef-139">Als de surface reduction-regel van de aanval niet iets blokkeert dat moet worden geblokkeerd (ook wel een onwaar negatief genoemd), kunt u direct verdergaan met de laatste stap, diagnostische gegevens verzamelen en het probleem bij ons [indienen.](#collect-diagnostic-data-for-file-submissions)</span><span class="sxs-lookup"><span data-stu-id="295ef-139">If the attack surface reduction rule isn't blocking something that it should block (also known as a false negative), you can proceed immediately to the last step, [collecting diagnostic data and submitting the issue to us](#collect-diagnostic-data-for-file-submissions).</span></span>

## <a name="add-exclusions-for-a-false-positive"></a><span data-ttu-id="295ef-140">Uitsluitingen toevoegen voor een onwaar positief</span><span class="sxs-lookup"><span data-stu-id="295ef-140">Add exclusions for a false positive</span></span>

<span data-ttu-id="295ef-141">Als de surface reduction-regel van de aanval iets blokkeert dat niet mag worden geblokkeerd (ook wel een onwaar positief genoemd), kunt u uitsluitingen toevoegen om te voorkomen dat regels voor het verminderen van aanvallen de uitgesloten bestanden of mappen evalueren.</span><span class="sxs-lookup"><span data-stu-id="295ef-141">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can add exclusions to prevent attack surface reduction rules from evaluating the excluded files or folders.</span></span>

<span data-ttu-id="295ef-142">Zie Surface reduction aanpassen om een uitsluiting [toe te voegen.](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="295ef-142">To add an exclusion, see [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="295ef-143">U kunt afzonderlijke bestanden en mappen opgeven die moeten worden uitgesloten, maar u kunt geen afzonderlijke regels opgeven.</span><span class="sxs-lookup"><span data-stu-id="295ef-143">You can specify individual files and folders to be excluded, but you cannot specify individual rules.</span></span>
><span data-ttu-id="295ef-144">Dit betekent dat alle bestanden of mappen die zijn uitgesloten, worden uitgesloten van alle ASR-regels.</span><span class="sxs-lookup"><span data-stu-id="295ef-144">This means any files or folders that are excluded will be excluded from all ASR rules.</span></span>

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="295ef-145">Een onwaar positief of onwaar negatief rapporteren</span><span class="sxs-lookup"><span data-stu-id="295ef-145">Report a false positive or false negative</span></span>

<span data-ttu-id="295ef-146">Gebruik het [webinzendingsformulier](https://www.microsoft.com/wdsi/filesubmission) van Windows Defender Security Intelligence om een onwaar negatief of onwaar positief voor netwerkbeveiliging te melden.</span><span class="sxs-lookup"><span data-stu-id="295ef-146">Use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="295ef-147">Met een Windows E5-abonnement kunt u ook een koppeling naar [een bijbehorende waarschuwing geven.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="295ef-147">With a Windows E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="295ef-148">Diagnostische gegevens verzamelen voor bestandsinzendingen</span><span class="sxs-lookup"><span data-stu-id="295ef-148">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="295ef-149">Wanneer u een probleem rapporteert met regels voor het verminderen van de surface attack, wordt u gevraagd diagnostische gegevens te verzamelen en in te dienen die kunnen worden gebruikt door ondersteunings- en technische teams van Microsoft om problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="295ef-149">When you report a problem with attack surface reduction rules, you're asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="295ef-150">Open een opdrachtprompt met verhoogde opdracht en wijzig in de Windows Defender-adreslijst:</span><span class="sxs-lookup"><span data-stu-id="295ef-150">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd "c:\program files\windows defender"
   ```

2. <span data-ttu-id="295ef-151">Voer deze opdracht uit om de diagnostische logboeken te genereren:</span><span class="sxs-lookup"><span data-stu-id="295ef-151">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="295ef-152">Standaard worden ze opgeslagen in `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="295ef-152">By default, they're saved to `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> <span data-ttu-id="295ef-153">Voeg het bestand toe aan het inzendingsformulier.</span><span class="sxs-lookup"><span data-stu-id="295ef-153">Attach the file to the submission form.</span></span>

## <a name="related-articles"></a><span data-ttu-id="295ef-154">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="295ef-154">Related articles</span></span>

- [<span data-ttu-id="295ef-155">Surface Reduction-regels voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="295ef-155">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="295ef-156">Regels voor het verlagen van de surface voor aanvallen inschakelen</span><span class="sxs-lookup"><span data-stu-id="295ef-156">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)

- [<span data-ttu-id="295ef-157">Regels voor het verlagen van het oppervlak van de aanval evalueren</span><span class="sxs-lookup"><span data-stu-id="295ef-157">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
