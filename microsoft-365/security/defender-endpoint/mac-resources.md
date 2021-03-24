---
title: Resources voor Microsoft Defender ATP voor Mac
description: Bronnen voor Microsoft Defender ATP voor Mac, waaronder hoe u deze verwijdert, hoe u diagnostische logboeken, CLI-opdrachten en bekende problemen met het product verzamelt.
keywords: microsoft, defender, atp, mac, installatie, implementeren, verwijderen, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 336f85b41884a441d0967c7f242b69c4d0e4941f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058318"
---
# <a name="resources-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="df6e9-104">Bronnen voor Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="df6e9-104">Resources for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="df6e9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="df6e9-105">**Applies to:**</span></span>
- [<span data-ttu-id="df6e9-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="df6e9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="df6e9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df6e9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="df6e9-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="df6e9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="df6e9-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="df6e9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="df6e9-110">Diagnostische gegevens verzamelen</span><span class="sxs-lookup"><span data-stu-id="df6e9-110">Collecting diagnostic information</span></span>

<span data-ttu-id="df6e9-111">Als u een probleem kunt reproduceren, kunt u het logboekregistratieniveau verhogen, het systeem enige tijd uitvoeren en het logboekregistratieniveau herstellen naar het standaardniveau.</span><span class="sxs-lookup"><span data-stu-id="df6e9-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="df6e9-112">Het logboekregistratieniveau verhogen:</span><span class="sxs-lookup"><span data-stu-id="df6e9-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="df6e9-113">Het probleem reproduceren</span><span class="sxs-lookup"><span data-stu-id="df6e9-113">Reproduce the problem</span></span>

3. <span data-ttu-id="df6e9-114">Voer `sudo mdatp diagnostic create` een back-up van de Logboeken van Microsoft Defender voor Eindpunt uit.</span><span class="sxs-lookup"><span data-stu-id="df6e9-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="df6e9-115">De bestanden worden opgeslagen in een ZIP-archief.</span><span class="sxs-lookup"><span data-stu-id="df6e9-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="df6e9-116">Met deze opdracht wordt ook het bestandspad naar de back-up afgedrukt nadat de bewerking is geslaagd.</span><span class="sxs-lookup"><span data-stu-id="df6e9-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="df6e9-117">Diagnostische logboeken worden standaard opgeslagen in `/Library/Application Support/Microsoft/Defender/wdavdiag/` .</span><span class="sxs-lookup"><span data-stu-id="df6e9-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="df6e9-118">Als u de adreslijst wilt wijzigen waarin diagnostische logboeken worden opgeslagen, gaat u naar de onderstaande `--path [directory]` opdracht en vervangt u deze door de `[directory]` gewenste adreslijst.</span><span class="sxs-lookup"><span data-stu-id="df6e9-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="df6e9-119">Logboekregistratieniveau herstellen:</span><span class="sxs-lookup"><span data-stu-id="df6e9-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="df6e9-120">Installatieproblemen met logboekregistratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-120">Logging installation issues</span></span>

<span data-ttu-id="df6e9-121">Als er een fout optreedt tijdens de installatie, meldt het installatieprogramma alleen een algemene fout.</span><span class="sxs-lookup"><span data-stu-id="df6e9-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="df6e9-122">Het gedetailleerde logboek wordt opgeslagen in `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="df6e9-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="df6e9-123">Als u problemen ervaart tijdens de installatie, stuurt u ons dit bestand zodat we de oorzaak kunnen helpen opsporen.</span><span class="sxs-lookup"><span data-stu-id="df6e9-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="df6e9-124">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="df6e9-124">Uninstalling</span></span>

<span data-ttu-id="df6e9-125">Er zijn verschillende manieren om Microsoft Defender voor Eindpunt voor Mac te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="df6e9-125">There are several ways to uninstall Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="df6e9-126">Hoewel centraal beheerd verwijderen beschikbaar is op JAMF, is deze nog niet beschikbaar voor Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="df6e9-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="df6e9-127">Interactief verwijderen</span><span class="sxs-lookup"><span data-stu-id="df6e9-127">Interactive uninstallation</span></span>

- <span data-ttu-id="df6e9-128">Open **Finder > Applications**.</span><span class="sxs-lookup"><span data-stu-id="df6e9-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="df6e9-129">Klik met de rechtermuisknop **op Microsoft Defender ATP > Naar prullenbak gaan.**</span><span class="sxs-lookup"><span data-stu-id="df6e9-129">Right click on **Microsoft Defender ATP > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="df6e9-130">Vanuit de opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="df6e9-130">From the command line</span></span>

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="df6e9-131">Configureren vanaf de opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="df6e9-131">Configuring from the command line</span></span>

<span data-ttu-id="df6e9-132">Belangrijke taken, zoals het beheren van productinstellingen en het activeren van scans op aanvraag, kunnen worden uitgevoerd vanaf de opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="df6e9-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="df6e9-133">Groep</span><span class="sxs-lookup"><span data-stu-id="df6e9-133">Group</span></span>        |<span data-ttu-id="df6e9-134">Scenario</span><span class="sxs-lookup"><span data-stu-id="df6e9-134">Scenario</span></span>                                   |<span data-ttu-id="df6e9-135">Opdracht</span><span class="sxs-lookup"><span data-stu-id="df6e9-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="df6e9-136">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-136">Configuration</span></span>|<span data-ttu-id="df6e9-137">Realtimebeveiliging in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="df6e9-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="df6e9-138">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-138">Configuration</span></span>|<span data-ttu-id="df6e9-139">Cloudbeveiliging in-/uitschakelen</span><span class="sxs-lookup"><span data-stu-id="df6e9-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="df6e9-140">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-140">Configuration</span></span>|<span data-ttu-id="df6e9-141">Productdiagnose in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="df6e9-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="df6e9-142">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-142">Configuration</span></span>|<span data-ttu-id="df6e9-143">Automatische voorbeeldinzending in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="df6e9-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="df6e9-144">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-144">Configuration</span></span>|<span data-ttu-id="df6e9-145">Een bedreigingsnaam toevoegen aan de toegestane lijst</span><span class="sxs-lookup"><span data-stu-id="df6e9-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="df6e9-146">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-146">Configuration</span></span>|<span data-ttu-id="df6e9-147">Een bedreigingsnaam verwijderen uit de toegestane lijst</span><span class="sxs-lookup"><span data-stu-id="df6e9-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="df6e9-148">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-148">Configuration</span></span>|<span data-ttu-id="df6e9-149">Alle toegestane bedreigingsnamen op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="df6e9-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="df6e9-150">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-150">Configuration</span></span>|<span data-ttu-id="df6e9-151">PUA-beveiliging in- en uit-</span><span class="sxs-lookup"><span data-stu-id="df6e9-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="df6e9-152">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-152">Configuration</span></span>|<span data-ttu-id="df6e9-153">PUA-beveiliging uitschakelen</span><span class="sxs-lookup"><span data-stu-id="df6e9-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="df6e9-154">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-154">Configuration</span></span>|<span data-ttu-id="df6e9-155">Auditmodus inschakelen voor PUA-beveiliging</span><span class="sxs-lookup"><span data-stu-id="df6e9-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="df6e9-156">Configuratie</span><span class="sxs-lookup"><span data-stu-id="df6e9-156">Configuration</span></span>|<span data-ttu-id="df6e9-157">PassiveMode in-/uitschakelen</span><span class="sxs-lookup"><span data-stu-id="df6e9-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="df6e9-158">Diagnostische gegevens</span><span class="sxs-lookup"><span data-stu-id="df6e9-158">Diagnostics</span></span>  |<span data-ttu-id="df6e9-159">Het logboekniveau wijzigen</span><span class="sxs-lookup"><span data-stu-id="df6e9-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="df6e9-160">Diagnostische gegevens</span><span class="sxs-lookup"><span data-stu-id="df6e9-160">Diagnostics</span></span>  |<span data-ttu-id="df6e9-161">Diagnostische logboeken genereren</span><span class="sxs-lookup"><span data-stu-id="df6e9-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="df6e9-162">Gezondheid</span><span class="sxs-lookup"><span data-stu-id="df6e9-162">Health</span></span>       |<span data-ttu-id="df6e9-163">De status van het product controleren</span><span class="sxs-lookup"><span data-stu-id="df6e9-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="df6e9-164">Gezondheid</span><span class="sxs-lookup"><span data-stu-id="df6e9-164">Health</span></span>       |<span data-ttu-id="df6e9-165">Controleren op een spefic-productkenmerk</span><span class="sxs-lookup"><span data-stu-id="df6e9-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="df6e9-166">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="df6e9-166">Protection</span></span>   |<span data-ttu-id="df6e9-167">Een pad scannen</span><span class="sxs-lookup"><span data-stu-id="df6e9-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="df6e9-168">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="df6e9-168">Protection</span></span>   |<span data-ttu-id="df6e9-169">Een snelle scan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="df6e9-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="df6e9-170">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="df6e9-170">Protection</span></span>   |<span data-ttu-id="df6e9-171">Een volledige scan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="df6e9-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="df6e9-172">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="df6e9-172">Protection</span></span>   |<span data-ttu-id="df6e9-173">Een lopende scan op aanvraag annuleren</span><span class="sxs-lookup"><span data-stu-id="df6e9-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="df6e9-174">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="df6e9-174">Protection</span></span>   |<span data-ttu-id="df6e9-175">Een beveiligingsintelligentie-update aanvragen</span><span class="sxs-lookup"><span data-stu-id="df6e9-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="df6e9-176">EDR</span><span class="sxs-lookup"><span data-stu-id="df6e9-176">EDR</span></span>          |<span data-ttu-id="df6e9-177">Groepslabel toevoegen aan apparaat.</span><span class="sxs-lookup"><span data-stu-id="df6e9-177">Add group tag to device.</span></span> <span data-ttu-id="df6e9-178">EDR-tags worden gebruikt voor het beheren van apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="df6e9-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="df6e9-179">Ga voor meer informatie naar https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="df6e9-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="df6e9-180">EDR</span><span class="sxs-lookup"><span data-stu-id="df6e9-180">EDR</span></span>          |<span data-ttu-id="df6e9-181">Groepslabel van apparaat verwijderen</span><span class="sxs-lookup"><span data-stu-id="df6e9-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="df6e9-182">EDR</span><span class="sxs-lookup"><span data-stu-id="df6e9-182">EDR</span></span>          |<span data-ttu-id="df6e9-183">Groeps-id toevoegen</span><span class="sxs-lookup"><span data-stu-id="df6e9-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="df6e9-184">Automatisch aanvullen inschakelen</span><span class="sxs-lookup"><span data-stu-id="df6e9-184">How to enable autocompletion</span></span>

<span data-ttu-id="df6e9-185">Als u automatisch aanvullen in bash wilt inschakelen, voer u de volgende opdracht uit en start u de Terminal-sessie opnieuw:</span><span class="sxs-lookup"><span data-stu-id="df6e9-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="df6e9-186">Automatisch aanvullen inschakelen in zsh:</span><span class="sxs-lookup"><span data-stu-id="df6e9-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="df6e9-187">Controleer of automatisch aanvullen is ingeschakeld op uw apparaat:</span><span class="sxs-lookup"><span data-stu-id="df6e9-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="df6e9-188">Als de vorige opdracht geen uitvoer produceert, kunt u automatisch aanvullen inschakelen met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="df6e9-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="df6e9-189">Voer de volgende opdrachten uit om automatisch aanvullen voor Microsoft Defender voor Eindpunt voor Mac in te stellen en start de Terminal-sessie opnieuw:</span><span class="sxs-lookup"><span data-stu-id="df6e9-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint for Mac and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="df6e9-190">Client Microsoft Defender voor endpoint quarantine directory</span><span class="sxs-lookup"><span data-stu-id="df6e9-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="df6e9-191">`/Library/Application Support/Microsoft/Defender/quarantine/` bevat de bestanden die in quarantaine zijn geplaatst door `mdatp` .</span><span class="sxs-lookup"><span data-stu-id="df6e9-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="df6e9-192">De bestanden zijn genoemd naar de bedreigingstrackingId.</span><span class="sxs-lookup"><span data-stu-id="df6e9-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="df6e9-193">De huidige trackingIds wordt weergegeven met `mdatp threat list` .</span><span class="sxs-lookup"><span data-stu-id="df6e9-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="df6e9-194">Microsoft Defender voor endpoint-portalgegevens</span><span class="sxs-lookup"><span data-stu-id="df6e9-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="df6e9-195">[De EDR-mogelijkheden](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)voor macOS zijn nu aangekomen op de Microsoft Defender voor Eindpunt-blog en bieden gedetailleerde richtlijnen voor wat u kunt verwachten in het Microsoft Defender for Endpoint Security Center.</span><span class="sxs-lookup"><span data-stu-id="df6e9-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
