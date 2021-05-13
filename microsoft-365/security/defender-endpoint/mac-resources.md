---
title: Bronnen voor Microsoft Defender voor Eindpunt op Mac
description: Bronnen voor Microsoft Defender voor Eindpunt op Mac, waaronder hoe u het verwijdert, hoe u diagnostische logboeken, CLI-opdrachten en bekende problemen met het product verzamelt.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 29e9eefdf85c80b6d3c44eba01d0df57be0193a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346388"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="50e1f-104">Resources voor Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="50e1f-104">Resources for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="50e1f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="50e1f-105">**Applies to:**</span></span>

- [<span data-ttu-id="50e1f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="50e1f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="50e1f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50e1f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="50e1f-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="50e1f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="50e1f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="50e1f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="50e1f-110">Diagnostische gegevens verzamelen</span><span class="sxs-lookup"><span data-stu-id="50e1f-110">Collecting diagnostic information</span></span>

<span data-ttu-id="50e1f-111">Als u een probleem kunt reproduceren, kunt u het logboekregistratieniveau verhogen, het systeem enige tijd uitvoeren en het logboekregistratieniveau herstellen naar het standaardniveau.</span><span class="sxs-lookup"><span data-stu-id="50e1f-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="50e1f-112">Het logboekregistratieniveau verhogen:</span><span class="sxs-lookup"><span data-stu-id="50e1f-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="50e1f-113">Het probleem reproduceren</span><span class="sxs-lookup"><span data-stu-id="50e1f-113">Reproduce the problem</span></span>

3. <span data-ttu-id="50e1f-114">Voer `sudo mdatp diagnostic create` een back-up van de Logboeken van Microsoft Defender voor Eindpunt uit.</span><span class="sxs-lookup"><span data-stu-id="50e1f-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="50e1f-115">De bestanden worden opgeslagen in een .zip archief.</span><span class="sxs-lookup"><span data-stu-id="50e1f-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="50e1f-116">Met deze opdracht wordt ook het bestandspad naar de back-up afgedrukt nadat de bewerking is geslaagd.</span><span class="sxs-lookup"><span data-stu-id="50e1f-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="50e1f-117">Diagnostische logboeken worden standaard opgeslagen in `/Library/Application Support/Microsoft/Defender/wdavdiag/` .</span><span class="sxs-lookup"><span data-stu-id="50e1f-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="50e1f-118">Als u de adreslijst wilt wijzigen waarin diagnostische logboeken worden opgeslagen, gaat u naar de onderstaande `--path [directory]` opdracht en vervangt u deze door de `[directory]` gewenste adreslijst.</span><span class="sxs-lookup"><span data-stu-id="50e1f-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="50e1f-119">Logboekregistratieniveau herstellen:</span><span class="sxs-lookup"><span data-stu-id="50e1f-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="50e1f-120">Installatieproblemen met logboekregistratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-120">Logging installation issues</span></span>

<span data-ttu-id="50e1f-121">Als er een fout optreedt tijdens de installatie, meldt het installatieprogramma alleen een algemene fout.</span><span class="sxs-lookup"><span data-stu-id="50e1f-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="50e1f-122">Het gedetailleerde logboek wordt opgeslagen in `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="50e1f-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="50e1f-123">Als u problemen ervaart tijdens de installatie, stuurt u ons dit bestand zodat we de oorzaak kunnen helpen opsporen.</span><span class="sxs-lookup"><span data-stu-id="50e1f-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="50e1f-124">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="50e1f-124">Uninstalling</span></span>

<span data-ttu-id="50e1f-125">Er zijn verschillende manieren om Microsoft Defender voor Eindpunt op macOS te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="50e1f-125">There are several ways to uninstall Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="50e1f-126">Hoewel centraal beheerd verwijderen beschikbaar is op JAMF, is deze nog niet beschikbaar voor Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="50e1f-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="50e1f-127">Interactief verwijderen</span><span class="sxs-lookup"><span data-stu-id="50e1f-127">Interactive uninstallation</span></span>

- <span data-ttu-id="50e1f-128">Open **Finder > Applications**.</span><span class="sxs-lookup"><span data-stu-id="50e1f-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="50e1f-129">Klik met de rechtermuisknop **op Microsoft Defender voor Eindpunt > Naar prullenbak gaan.**</span><span class="sxs-lookup"><span data-stu-id="50e1f-129">Right click on **Microsoft Defender for Endpoint > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="50e1f-130">Vanuit de opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="50e1f-130">From the command line</span></span>

- ```sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="50e1f-131">Configureren vanaf de opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="50e1f-131">Configuring from the command line</span></span>

<span data-ttu-id="50e1f-132">Belangrijke taken, zoals het beheren van productinstellingen en het activeren van scans op aanvraag, kunnen worden uitgevoerd vanaf de opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="50e1f-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="50e1f-133">Groep</span><span class="sxs-lookup"><span data-stu-id="50e1f-133">Group</span></span>        |<span data-ttu-id="50e1f-134">Scenario</span><span class="sxs-lookup"><span data-stu-id="50e1f-134">Scenario</span></span>                                   |<span data-ttu-id="50e1f-135">Opdracht</span><span class="sxs-lookup"><span data-stu-id="50e1f-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="50e1f-136">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-136">Configuration</span></span>|<span data-ttu-id="50e1f-137">Realtimebeveiliging in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="50e1f-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="50e1f-138">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-138">Configuration</span></span>|<span data-ttu-id="50e1f-139">Cloudbeveiliging in-/uitschakelen</span><span class="sxs-lookup"><span data-stu-id="50e1f-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="50e1f-140">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-140">Configuration</span></span>|<span data-ttu-id="50e1f-141">Productdiagnose in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="50e1f-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="50e1f-142">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-142">Configuration</span></span>|<span data-ttu-id="50e1f-143">Automatische voorbeeldinzending in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="50e1f-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="50e1f-144">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-144">Configuration</span></span>|<span data-ttu-id="50e1f-145">Een bedreigingsnaam toevoegen aan de toegestane lijst</span><span class="sxs-lookup"><span data-stu-id="50e1f-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="50e1f-146">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-146">Configuration</span></span>|<span data-ttu-id="50e1f-147">Een bedreigingsnaam verwijderen uit de toegestane lijst</span><span class="sxs-lookup"><span data-stu-id="50e1f-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="50e1f-148">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-148">Configuration</span></span>|<span data-ttu-id="50e1f-149">Alle toegestane bedreigingsnamen op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="50e1f-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="50e1f-150">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-150">Configuration</span></span>|<span data-ttu-id="50e1f-151">PUA-beveiliging in- en uit-</span><span class="sxs-lookup"><span data-stu-id="50e1f-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="50e1f-152">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-152">Configuration</span></span>|<span data-ttu-id="50e1f-153">PUA-beveiliging uitschakelen</span><span class="sxs-lookup"><span data-stu-id="50e1f-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="50e1f-154">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-154">Configuration</span></span>|<span data-ttu-id="50e1f-155">Auditmodus inschakelen voor PUA-beveiliging</span><span class="sxs-lookup"><span data-stu-id="50e1f-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="50e1f-156">Configuratie</span><span class="sxs-lookup"><span data-stu-id="50e1f-156">Configuration</span></span>|<span data-ttu-id="50e1f-157">PassiveMode in-/uitschakelen</span><span class="sxs-lookup"><span data-stu-id="50e1f-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="50e1f-158">Diagnostische gegevens</span><span class="sxs-lookup"><span data-stu-id="50e1f-158">Diagnostics</span></span>  |<span data-ttu-id="50e1f-159">Het logboekniveau wijzigen</span><span class="sxs-lookup"><span data-stu-id="50e1f-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="50e1f-160">Diagnostische gegevens</span><span class="sxs-lookup"><span data-stu-id="50e1f-160">Diagnostics</span></span>  |<span data-ttu-id="50e1f-161">Diagnostische logboeken genereren</span><span class="sxs-lookup"><span data-stu-id="50e1f-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="50e1f-162">Gezondheid</span><span class="sxs-lookup"><span data-stu-id="50e1f-162">Health</span></span>       |<span data-ttu-id="50e1f-163">De status van het product controleren</span><span class="sxs-lookup"><span data-stu-id="50e1f-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="50e1f-164">Gezondheid</span><span class="sxs-lookup"><span data-stu-id="50e1f-164">Health</span></span>       |<span data-ttu-id="50e1f-165">Controleren op een spefic-productkenmerk</span><span class="sxs-lookup"><span data-stu-id="50e1f-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="50e1f-166">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="50e1f-166">Protection</span></span>   |<span data-ttu-id="50e1f-167">Een pad scannen</span><span class="sxs-lookup"><span data-stu-id="50e1f-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="50e1f-168">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="50e1f-168">Protection</span></span>   |<span data-ttu-id="50e1f-169">Een snelle scan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="50e1f-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="50e1f-170">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="50e1f-170">Protection</span></span>   |<span data-ttu-id="50e1f-171">Een volledige scan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="50e1f-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="50e1f-172">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="50e1f-172">Protection</span></span>   |<span data-ttu-id="50e1f-173">Een lopende scan op aanvraag annuleren</span><span class="sxs-lookup"><span data-stu-id="50e1f-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="50e1f-174">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="50e1f-174">Protection</span></span>   |<span data-ttu-id="50e1f-175">Een beveiligingsintelligentie-update aanvragen</span><span class="sxs-lookup"><span data-stu-id="50e1f-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="50e1f-176">EDR</span><span class="sxs-lookup"><span data-stu-id="50e1f-176">EDR</span></span>          |<span data-ttu-id="50e1f-177">Groepslabel toevoegen aan apparaat.</span><span class="sxs-lookup"><span data-stu-id="50e1f-177">Add group tag to device.</span></span> <span data-ttu-id="50e1f-178">EDR tags worden gebruikt voor het beheren van apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="50e1f-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="50e1f-179">Ga voor meer informatie naar https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="50e1f-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="50e1f-180">EDR</span><span class="sxs-lookup"><span data-stu-id="50e1f-180">EDR</span></span>          |<span data-ttu-id="50e1f-181">Groepslabel van apparaat verwijderen</span><span class="sxs-lookup"><span data-stu-id="50e1f-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="50e1f-182">EDR</span><span class="sxs-lookup"><span data-stu-id="50e1f-182">EDR</span></span>          |<span data-ttu-id="50e1f-183">Groeps-id toevoegen</span><span class="sxs-lookup"><span data-stu-id="50e1f-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="50e1f-184">Automatisch aanvullen inschakelen</span><span class="sxs-lookup"><span data-stu-id="50e1f-184">How to enable autocompletion</span></span>

<span data-ttu-id="50e1f-185">Als u automatisch aanvullen in bash wilt inschakelen, voer u de volgende opdracht uit en start u de Terminal-sessie opnieuw:</span><span class="sxs-lookup"><span data-stu-id="50e1f-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="50e1f-186">Automatisch aanvullen inschakelen in zsh:</span><span class="sxs-lookup"><span data-stu-id="50e1f-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="50e1f-187">Controleer of automatisch aanvullen is ingeschakeld op uw apparaat:</span><span class="sxs-lookup"><span data-stu-id="50e1f-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="50e1f-188">Als de vorige opdracht geen uitvoer produceert, kunt u automatisch aanvullen inschakelen met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="50e1f-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="50e1f-189">Voer de volgende opdrachten uit om automatisch aanvullen voor Microsoft Defender voor Eindpunt in macOS in te stellen en start de Terminal-sessie opnieuw:</span><span class="sxs-lookup"><span data-stu-id="50e1f-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint on macOS and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="50e1f-190">Client Microsoft Defender voor endpoint quarantine directory</span><span class="sxs-lookup"><span data-stu-id="50e1f-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="50e1f-191">`/Library/Application Support/Microsoft/Defender/quarantine/` bevat de bestanden die in quarantaine zijn geplaatst door `mdatp` .</span><span class="sxs-lookup"><span data-stu-id="50e1f-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="50e1f-192">De bestanden zijn genoemd naar de bedreigingstrackingId.</span><span class="sxs-lookup"><span data-stu-id="50e1f-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="50e1f-193">De huidige trackingIds wordt weergegeven met `mdatp threat list` .</span><span class="sxs-lookup"><span data-stu-id="50e1f-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="50e1f-194">Microsoft Defender voor endpoint-portalgegevens</span><span class="sxs-lookup"><span data-stu-id="50e1f-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="50e1f-195">EDR mogelijkheden voor [macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)zijn nu aangekomen , op de Microsoft Defender voor Eindpunt-blog, biedt gedetailleerde richtlijnen over wat u kunt verwachten in het Microsoft Defender for Endpoint Security Center.</span><span class="sxs-lookup"><span data-stu-id="50e1f-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
