---
title: Microsoft Defender voor Eindpunt op Linux-resources
ms.reviewer: ''
description: Beschrijft bronnen voor Microsoft Defender voor Eindpunt op Linux, waaronder hoe u deze verwijdert, hoe u diagnostische logboeken, CLI-opdrachten en bekende problemen met het product verzamelt.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, pop, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aaf9c0a8eef4e050ca034d1aee69d24c5adb909d
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930365"
---
# <a name="resources"></a><span data-ttu-id="95c73-104">Resources</span><span class="sxs-lookup"><span data-stu-id="95c73-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="95c73-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="95c73-105">**Applies to:**</span></span>

- [<span data-ttu-id="95c73-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="95c73-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="95c73-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95c73-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="95c73-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="95c73-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="95c73-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="95c73-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="95c73-110">Diagnostische gegevens verzamelen</span><span class="sxs-lookup"><span data-stu-id="95c73-110">Collect diagnostic information</span></span>

<span data-ttu-id="95c73-111">Als u een probleem kunt reproduceren, moet u eerst het logboekregistratieniveau verhogen, het systeem enige tijd uitvoeren en vervolgens het logboekregistratieniveau herstellen naar het standaardniveau.</span><span class="sxs-lookup"><span data-stu-id="95c73-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="95c73-112">Het logboekregistratieniveau verhogen:</span><span class="sxs-lookup"><span data-stu-id="95c73-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="95c73-113">Reproduceer het probleem.</span><span class="sxs-lookup"><span data-stu-id="95c73-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="95c73-114">Voer de volgende opdracht uit om een back-up te maken van de logboeken van Defender voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="95c73-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="95c73-115">De bestanden worden opgeslagen in een .zip archief.</span><span class="sxs-lookup"><span data-stu-id="95c73-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="95c73-116">Met deze opdracht wordt ook het bestandspad naar de back-up afgedrukt nadat de bewerking is geslaagd:</span><span class="sxs-lookup"><span data-stu-id="95c73-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="95c73-117">Logboekregistratieniveau herstellen:</span><span class="sxs-lookup"><span data-stu-id="95c73-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```

   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="95c73-118">Problemen met de installatie van logboeken</span><span class="sxs-lookup"><span data-stu-id="95c73-118">Log installation issues</span></span>

<span data-ttu-id="95c73-119">Als er een fout optreedt tijdens de installatie, meldt het installatieprogramma alleen een algemene fout.</span><span class="sxs-lookup"><span data-stu-id="95c73-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="95c73-120">Het gedetailleerde logboek wordt opgeslagen in `/var/log/microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="95c73-120">The detailed log will be saved to `/var/log/microsoft/mdatp/install.log`.</span></span>
<span data-ttu-id="95c73-121">Als u problemen ervaart tijdens de installatie, stuurt u ons dit bestand zodat we de oorzaak kunnen helpen opsporen.</span><span class="sxs-lookup"><span data-stu-id="95c73-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="95c73-122">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="95c73-122">Uninstall</span></span>

<span data-ttu-id="95c73-123">Er zijn verschillende manieren om Defender voor Endpoint op Linux te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="95c73-123">There are several ways to uninstall Defender for Endpoint on Linux.</span></span> <span data-ttu-id="95c73-124">Als u een configuratiehulpmiddel zoals Poppenkast gebruikt, volgt u de instructies voor het verwijderen van het pakket voor het configuratieprogramma.</span><span class="sxs-lookup"><span data-stu-id="95c73-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="95c73-125">Handmatig verwijderen</span><span class="sxs-lookup"><span data-stu-id="95c73-125">Manual uninstallation</span></span>

- <span data-ttu-id="95c73-126">`sudo yum remove mdatp` voor RHEL en varianten(CentOS en Oracle Linux).</span><span class="sxs-lookup"><span data-stu-id="95c73-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="95c73-127">`sudo zypper remove mdatp` voor SLES en varianten.</span><span class="sxs-lookup"><span data-stu-id="95c73-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="95c73-128">`sudo apt-get purge mdatp` voor Ubuntu- en Debian-systemen.</span><span class="sxs-lookup"><span data-stu-id="95c73-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="95c73-129">Configureren vanaf de opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="95c73-129">Configure from the command line</span></span>

<span data-ttu-id="95c73-130">Belangrijke taken, zoals het beheren van productinstellingen en het activeren van scans op aanvraag, kunnen worden uitgevoerd vanaf de opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="95c73-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="95c73-131">Algemene opties</span><span class="sxs-lookup"><span data-stu-id="95c73-131">Global options</span></span>

<span data-ttu-id="95c73-132">Standaard wordt met het opdrachtregelhulpmiddel het resultaat uitgevoerd in een door de mens gelezen indeling.</span><span class="sxs-lookup"><span data-stu-id="95c73-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="95c73-133">Daarnaast ondersteunt het hulpprogramma ook de uitvoer van het resultaat als JSON, wat handig is voor automatiseringsscenario's.</span><span class="sxs-lookup"><span data-stu-id="95c73-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="95c73-134">Als u de uitvoer wilt wijzigen in JSON, gaat u `--output json` naar een van de onderstaande opdrachten.</span><span class="sxs-lookup"><span data-stu-id="95c73-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="95c73-135">Ondersteunde opdrachten</span><span class="sxs-lookup"><span data-stu-id="95c73-135">Supported commands</span></span>

<span data-ttu-id="95c73-136">De volgende tabel bevat opdrachten voor enkele van de meest voorkomende scenario's.</span><span class="sxs-lookup"><span data-stu-id="95c73-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="95c73-137">Voer `mdatp help` de terminal uit om de volledige lijst met ondersteunde opdrachten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="95c73-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="95c73-138">Groep</span><span class="sxs-lookup"><span data-stu-id="95c73-138">Group</span></span>                 |<span data-ttu-id="95c73-139">Scenario</span><span class="sxs-lookup"><span data-stu-id="95c73-139">Scenario</span></span>                                                |<span data-ttu-id="95c73-140">Opdracht</span><span class="sxs-lookup"><span data-stu-id="95c73-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="95c73-141">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-141">Configuration</span></span>         |<span data-ttu-id="95c73-142">Realtimebeveiliging in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="95c73-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="95c73-143">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-143">Configuration</span></span>         |<span data-ttu-id="95c73-144">Gedragscontrole in-/uitschakelen</span><span class="sxs-lookup"><span data-stu-id="95c73-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]`
|<span data-ttu-id="95c73-145">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-145">Configuration</span></span>         |<span data-ttu-id="95c73-146">Cloudbeveiliging in-/uitschakelen</span><span class="sxs-lookup"><span data-stu-id="95c73-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="95c73-147">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-147">Configuration</span></span>         |<span data-ttu-id="95c73-148">Productdiagnose in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="95c73-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="95c73-149">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-149">Configuration</span></span>         |<span data-ttu-id="95c73-150">Automatische voorbeeldinzending in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="95c73-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="95c73-151">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-151">Configuration</span></span>         |<span data-ttu-id="95c73-152">Passieve AV-modus in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="95c73-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="95c73-153">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-153">Configuration</span></span>         |<span data-ttu-id="95c73-154">Een antivirusuitsluiting toevoegen/verwijderen voor een bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="95c73-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="95c73-155">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-155">Configuration</span></span>         |<span data-ttu-id="95c73-156">Een antivirusuitsluiting voor een bestand toevoegen/verwijderen</span><span class="sxs-lookup"><span data-stu-id="95c73-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="95c73-157">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-157">Configuration</span></span>         |<span data-ttu-id="95c73-158">Een antivirusuitsluiting voor een adreslijst toevoegen/verwijderen</span><span class="sxs-lookup"><span data-stu-id="95c73-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="95c73-159">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-159">Configuration</span></span>         |<span data-ttu-id="95c73-160">Een antivirusuitsluiting toevoegen/verwijderen voor een proces</span><span class="sxs-lookup"><span data-stu-id="95c73-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="95c73-161">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-161">Configuration</span></span>         |<span data-ttu-id="95c73-162">Alle antivirusuitsluitingen op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="95c73-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="95c73-163">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-163">Configuration</span></span>         |<span data-ttu-id="95c73-164">Een bedreigingsnaam toevoegen aan de toegestane lijst</span><span class="sxs-lookup"><span data-stu-id="95c73-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="95c73-165">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-165">Configuration</span></span>         |<span data-ttu-id="95c73-166">Een bedreigingsnaam verwijderen uit de toegestane lijst</span><span class="sxs-lookup"><span data-stu-id="95c73-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="95c73-167">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-167">Configuration</span></span>         |<span data-ttu-id="95c73-168">Alle toegestane bedreigingsnamen op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="95c73-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="95c73-169">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-169">Configuration</span></span>         |<span data-ttu-id="95c73-170">PUA-beveiliging in- en uit-</span><span class="sxs-lookup"><span data-stu-id="95c73-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="95c73-171">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-171">Configuration</span></span>         |<span data-ttu-id="95c73-172">PUA-beveiliging uitschakelen</span><span class="sxs-lookup"><span data-stu-id="95c73-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="95c73-173">Configuratie</span><span class="sxs-lookup"><span data-stu-id="95c73-173">Configuration</span></span>         |<span data-ttu-id="95c73-174">Auditmodus inschakelen voor PUA-beveiliging</span><span class="sxs-lookup"><span data-stu-id="95c73-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="95c73-175">Diagnostische gegevens</span><span class="sxs-lookup"><span data-stu-id="95c73-175">Diagnostics</span></span>           |<span data-ttu-id="95c73-176">Het logboekniveau wijzigen</span><span class="sxs-lookup"><span data-stu-id="95c73-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="95c73-177">Diagnostische gegevens</span><span class="sxs-lookup"><span data-stu-id="95c73-177">Diagnostics</span></span>           |<span data-ttu-id="95c73-178">Diagnostische logboeken genereren</span><span class="sxs-lookup"><span data-stu-id="95c73-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="95c73-179">Gezondheid</span><span class="sxs-lookup"><span data-stu-id="95c73-179">Health</span></span>                |<span data-ttu-id="95c73-180">De status van het product controleren</span><span class="sxs-lookup"><span data-stu-id="95c73-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="95c73-181">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="95c73-181">Protection</span></span>            |<span data-ttu-id="95c73-182">Een pad scannen</span><span class="sxs-lookup"><span data-stu-id="95c73-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="95c73-183">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="95c73-183">Protection</span></span>            |<span data-ttu-id="95c73-184">Een snelle scan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="95c73-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="95c73-185">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="95c73-185">Protection</span></span>            |<span data-ttu-id="95c73-186">Een volledige scan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="95c73-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="95c73-187">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="95c73-187">Protection</span></span>            |<span data-ttu-id="95c73-188">Een lopende scan op aanvraag annuleren</span><span class="sxs-lookup"><span data-stu-id="95c73-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="95c73-189">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="95c73-189">Protection</span></span>            |<span data-ttu-id="95c73-190">Een beveiligingsintelligentie-update aanvragen</span><span class="sxs-lookup"><span data-stu-id="95c73-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="95c73-191">Beveiligingsgeschiedenis</span><span class="sxs-lookup"><span data-stu-id="95c73-191">Protection history</span></span>    |<span data-ttu-id="95c73-192">De volledige beveiligingsgeschiedenis afdrukken</span><span class="sxs-lookup"><span data-stu-id="95c73-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="95c73-193">Beveiligingsgeschiedenis</span><span class="sxs-lookup"><span data-stu-id="95c73-193">Protection history</span></span>    |<span data-ttu-id="95c73-194">Bedreigingsdetails krijgen</span><span class="sxs-lookup"><span data-stu-id="95c73-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="95c73-195">Quarantainebeheer</span><span class="sxs-lookup"><span data-stu-id="95c73-195">Quarantine management</span></span> |<span data-ttu-id="95c73-196">Alle in quarantaine geplaatste bestanden op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="95c73-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="95c73-197">Quarantainebeheer</span><span class="sxs-lookup"><span data-stu-id="95c73-197">Quarantine management</span></span> |<span data-ttu-id="95c73-198">Alle bestanden uit de quarantaine verwijderen</span><span class="sxs-lookup"><span data-stu-id="95c73-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="95c73-199">Quarantainebeheer</span><span class="sxs-lookup"><span data-stu-id="95c73-199">Quarantine management</span></span> |<span data-ttu-id="95c73-200">Een bestand toevoegen dat is gedetecteerd als een bedreiging voor de quarantaine</span><span class="sxs-lookup"><span data-stu-id="95c73-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="95c73-201">Quarantainebeheer</span><span class="sxs-lookup"><span data-stu-id="95c73-201">Quarantine management</span></span> |<span data-ttu-id="95c73-202">Een bestand verwijderen dat is gedetecteerd als een bedreiging uit de quarantaine</span><span class="sxs-lookup"><span data-stu-id="95c73-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="95c73-203">Quarantainebeheer</span><span class="sxs-lookup"><span data-stu-id="95c73-203">Quarantine management</span></span> |<span data-ttu-id="95c73-204">Een bestand uit de quarantaine herstellen</span><span class="sxs-lookup"><span data-stu-id="95c73-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="95c73-205">Eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="95c73-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="95c73-206">Vroege preview instellen (ongebruikt)</span><span class="sxs-lookup"><span data-stu-id="95c73-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="95c73-207">Eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="95c73-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="95c73-208">Groeps-id instellen</span><span class="sxs-lookup"><span data-stu-id="95c73-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="95c73-209">Eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="95c73-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="95c73-210">Tag instellen/verwijderen, alleen `GROUP` ondersteund</span><span class="sxs-lookup"><span data-stu-id="95c73-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="95c73-211">Eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="95c73-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="95c73-212">lijstuitsluitingen (hoofd)</span><span class="sxs-lookup"><span data-stu-id="95c73-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="95c73-213">Microsoft Defender voor endpoint-portalgegevens</span><span class="sxs-lookup"><span data-stu-id="95c73-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="95c73-214">In de portal Defender voor eindpunt ziet u twee categorieën met informatie:</span><span class="sxs-lookup"><span data-stu-id="95c73-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="95c73-215">Antiviruswaarschuwingen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="95c73-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="95c73-216">Ernst</span><span class="sxs-lookup"><span data-stu-id="95c73-216">Severity</span></span>
  - <span data-ttu-id="95c73-217">Scantype</span><span class="sxs-lookup"><span data-stu-id="95c73-217">Scan type</span></span>
  - <span data-ttu-id="95c73-218">Apparaatgegevens (hostnaam, apparaataanduiding, tenant-id, app-versie en ostype)</span><span class="sxs-lookup"><span data-stu-id="95c73-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="95c73-219">Bestandsgegevens (naam, pad, grootte en hash)</span><span class="sxs-lookup"><span data-stu-id="95c73-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="95c73-220">Bedreigingsgegevens (naam, type en status)</span><span class="sxs-lookup"><span data-stu-id="95c73-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="95c73-221">Apparaatgegevens, waaronder:</span><span class="sxs-lookup"><span data-stu-id="95c73-221">Device information, including:</span></span>
  - <span data-ttu-id="95c73-222">Apparaataanduiding</span><span class="sxs-lookup"><span data-stu-id="95c73-222">Device identifier</span></span>
  - <span data-ttu-id="95c73-223">Tenant-id</span><span class="sxs-lookup"><span data-stu-id="95c73-223">Tenant identifier</span></span>
  - <span data-ttu-id="95c73-224">App-versie</span><span class="sxs-lookup"><span data-stu-id="95c73-224">App version</span></span>
  - <span data-ttu-id="95c73-225">Hostname</span><span class="sxs-lookup"><span data-stu-id="95c73-225">Hostname</span></span>
  - <span data-ttu-id="95c73-226">OS-type</span><span class="sxs-lookup"><span data-stu-id="95c73-226">OS type</span></span>
  - <span data-ttu-id="95c73-227">OS-versie</span><span class="sxs-lookup"><span data-stu-id="95c73-227">OS version</span></span>
  - <span data-ttu-id="95c73-228">Computermodel</span><span class="sxs-lookup"><span data-stu-id="95c73-228">Computer model</span></span>
  - <span data-ttu-id="95c73-229">Processorarchitectuur</span><span class="sxs-lookup"><span data-stu-id="95c73-229">Processor architecture</span></span>
  - <span data-ttu-id="95c73-230">Of het apparaat een virtuele machine is</span><span class="sxs-lookup"><span data-stu-id="95c73-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="95c73-231">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="95c73-231">Known issues</span></span>

- <span data-ttu-id="95c73-232">Mogelijk ziet u 'Geen sensorgegevens, beperkte communicatie' op de pagina computergegevens van de Microsoft Defender-beveiligingscentrum portal, ook al werkt het product zoals verwacht.</span><span class="sxs-lookup"><span data-stu-id="95c73-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="95c73-233">We werken aan een oplossing voor dit probleem.</span><span class="sxs-lookup"><span data-stu-id="95c73-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="95c73-234">Aangemelde gebruikers worden niet weergegeven in de Microsoft Defender-beveiligingscentrum portal.</span><span class="sxs-lookup"><span data-stu-id="95c73-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="95c73-235">Als de installatie van *libatomic1* mislukt in SUSE-distributies, moet u controleren of uw besturingssysteem is geregistreerd:</span><span class="sxs-lookup"><span data-stu-id="95c73-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
