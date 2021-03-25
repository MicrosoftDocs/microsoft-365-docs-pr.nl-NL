---
title: Nieuwe functies in Microsoft Defender voor Eindpunt voor Mac
description: Meer informatie over de belangrijkste wijzigingen voor eerdere versies van Microsoft Defender voor Eindpunt voor Mac.
keywords: microsoft, defender, atp, mac, installatie, macos, whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: be906baca3a54183e22fa3b4ee424a9d8fc6957a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198691"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="a65ad-104">Nieuwe functies in Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="a65ad-104">What's new in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a65ad-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a65ad-105">**Applies to:**</span></span>
- [<span data-ttu-id="a65ad-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="a65ad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a65ad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a65ad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a65ad-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a65ad-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a65ad-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a65ad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="a65ad-110">Voor macOS 11 (Big Sur) vereist Microsoft Defender voor Eindpunt extra configuratieprofielen.</span><span class="sxs-lookup"><span data-stu-id="a65ad-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="a65ad-111">Als u een bestaande klant bent die upgradet van eerdere versies van macOS, moet u de extra configuratieprofielen implementeren die op [deze pagina worden vermeld.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a65ad-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a65ad-112">Ondersteuning voor macOS 10.13 (High Sierra) wordt stopgezet op 15 februari 2021.</span><span class="sxs-lookup"><span data-stu-id="a65ad-112">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="a65ad-113">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="a65ad-113">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="a65ad-114">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-114">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="a65ad-115">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="a65ad-115">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="a65ad-116">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-116">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="a65ad-117">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="a65ad-117">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="a65ad-118">De syntaxis van het oude opdrachtregelprogramma is afgeschaft met deze release.</span><span class="sxs-lookup"><span data-stu-id="a65ad-118">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="a65ad-119">Zie Resources voor informatie over de nieuwe [syntaxis.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="a65ad-119">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="a65ad-120">Er is een nieuwe opdrachtregelknop toegevoegd om de netwerkextensie uit te schakelen: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="a65ad-120">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="a65ad-121">Deze opdracht kan handig zijn om problemen met netwerken op te lossen die kunnen worden gerelateerd aan Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="a65ad-121">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="a65ad-122">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-122">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="a65ad-123">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="a65ad-123">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="a65ad-124">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="a65ad-124">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="a65ad-125">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="a65ad-125">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="a65ad-126">Verbeterde de betrouwbaarheid van de agent bij het uitvoeren van macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="a65ad-126">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="a65ad-127">Een nieuwe opdrachtregelschakelaar () toegevoegd om AV-uitsluitingen `--ignore-exclusions` te negeren tijdens aangepaste scans ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="a65ad-127">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="a65ad-128">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-128">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="a65ad-129">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="a65ad-129">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="a65ad-130">Verwijderde voorwaarden wanneer Microsoft Defender voor Eindpunt een macOS 11 -bug (Big Sur) activeert die zich manifesteert in een kernel-paniek</span><span class="sxs-lookup"><span data-stu-id="a65ad-130">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="a65ad-131">Een geheugenlek in de systeemextensie Endpoint Security opgelost bij het uitvoeren op mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="a65ad-131">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="a65ad-132">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="a65ad-132">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="a65ad-133">101.10.72</span><span class="sxs-lookup"><span data-stu-id="a65ad-133">101.10.72</span></span>

- <span data-ttu-id="a65ad-134">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="a65ad-134">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="a65ad-135">101.09.61</span><span class="sxs-lookup"><span data-stu-id="a65ad-135">101.09.61</span></span>

- <span data-ttu-id="a65ad-136">Een nieuwe beheerde voorkeur voor het [uitschakelen van de optie voor het verzenden van feedback toegevoegd](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="a65ad-136">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="a65ad-137">Het pictogram Statusmenu geeft nu een gezonde status weer wanneer de productinstellingen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="a65ad-137">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="a65ad-138">Voorheen werd in het statusmenupictogram een waarschuwings- of foutstatus weergegeven, ook al zijn de productinstellingen beheerd door de beheerder</span><span class="sxs-lookup"><span data-stu-id="a65ad-138">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="a65ad-139">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-139">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="a65ad-140">101.09.50</span><span class="sxs-lookup"><span data-stu-id="a65ad-140">101.09.50</span></span>

- <span data-ttu-id="a65ad-141">Deze productversie is gevalideerd op macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="a65ad-141">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="a65ad-142">De nieuwe syntaxis voor het `mdatp` opdrachtregelhulpmiddel is nu de standaard syntaxis.</span><span class="sxs-lookup"><span data-stu-id="a65ad-142">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="a65ad-143">Zie Resources voor Microsoft Defender voor Eindpunt voor Mac voor meer informatie over de nieuwe [syntaxis](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="a65ad-143">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="a65ad-144">De syntaxis van het oude opdrachtregelprogramma wordt op 1 januari **2021** uit het product verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a65ad-144">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="a65ad-145">Uitgebreid met een nieuwe parameter ( ) waarmee de diagnostische `mdatp diagnostic create` `--path [directory]` logboeken kunnen worden opgeslagen in een andere adreslijst</span><span class="sxs-lookup"><span data-stu-id="a65ad-145">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="a65ad-146">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-146">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="a65ad-147">101.09.49</span><span class="sxs-lookup"><span data-stu-id="a65ad-147">101.09.49</span></span>

- <span data-ttu-id="a65ad-148">Verbeteringen in de gebruikersinterface om onderscheid te maken tussen uitsluitingen die worden beheerd door de IT-beheerder en uitsluitingen die door de lokale gebruiker zijn gedefinieerd</span><span class="sxs-lookup"><span data-stu-id="a65ad-148">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="a65ad-149">Verbeterde CPU-gebruik tijdens scans op aanvraag</span><span class="sxs-lookup"><span data-stu-id="a65ad-149">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="a65ad-150">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-150">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="a65ad-151">101.07.23</span><span class="sxs-lookup"><span data-stu-id="a65ad-151">101.07.23</span></span>

- <span data-ttu-id="a65ad-152">Nieuwe velden toegevoegd aan de uitvoer van voor het controleren van de status van de `mdatp --health` passieve modus en de EDR-groeps-id</span><span class="sxs-lookup"><span data-stu-id="a65ad-152">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="a65ad-153">`mdatp --health` wordt vervangen door `mdatp health` in een toekomstige productupdate.</span><span class="sxs-lookup"><span data-stu-id="a65ad-153">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="a65ad-154">Een fout opgelost waarbij automatische voorbeeldinzending niet is gemarkeerd als beheerd in de gebruikersinterface</span><span class="sxs-lookup"><span data-stu-id="a65ad-154">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="a65ad-155">Er zijn nieuwe instellingen toegevoegd voor het beheren van het bewaren van items in de antivirusscangeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="a65ad-155">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="a65ad-156">U kunt nu het aantal dagen opgeven om items in de [scangeschiedenis](mac-preferences.md#antivirus-scan-history-retention-in-days) te behouden en het maximum aantal items in de [scangeschiedenis opgeven](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="a65ad-156">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="a65ad-157">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="a65ad-157">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="a65ad-158">101.06.63</span><span class="sxs-lookup"><span data-stu-id="a65ad-158">101.06.63</span></span>

- <span data-ttu-id="a65ad-159">Er is een prestatieregressie aangepakt die in versie is `101.05.17` geïntroduceerd.</span><span class="sxs-lookup"><span data-stu-id="a65ad-159">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="a65ad-160">De regressie is geïntroduceerd met de fix om de kernel-paniek te elimineren die sommige klanten hebben waargenomen bij het openen van SMB-aandelen.</span><span class="sxs-lookup"><span data-stu-id="a65ad-160">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="a65ad-161">We hebben deze codewijziging teruggedraaid en onderzoeken alternatieve manieren om de kernelpaniek te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="a65ad-161">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="a65ad-162">101.05.17</span><span class="sxs-lookup"><span data-stu-id="a65ad-162">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a65ad-163">We werken aan een nieuwe en verbeterde syntaxis voor het `mdatp` opdrachtregelhulpmiddel.</span><span class="sxs-lookup"><span data-stu-id="a65ad-163">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="a65ad-164">De nieuwe syntaxis is momenteel de standaardinstelling in de Insider Fast- en Insider Slow-updatekanalen.</span><span class="sxs-lookup"><span data-stu-id="a65ad-164">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="a65ad-165">We raden u aan om uzelf te famliliariseren met deze nieuwe syntaxis.</span><span class="sxs-lookup"><span data-stu-id="a65ad-165">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="a65ad-166">We blijven de oude syntaxis ondersteunen in parallel met de nieuwe syntaxis en zorgen voor meer communicatie rond het afbouwplan voor de oude syntaxis in de komende maanden.</span><span class="sxs-lookup"><span data-stu-id="a65ad-166">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="a65ad-167">Adresseerde een kernel-paniek die zich soms voordeed bij het openen van SMB-bestandsaandelen</span><span class="sxs-lookup"><span data-stu-id="a65ad-167">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="a65ad-168">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-168">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="a65ad-169">101.05.16</span><span class="sxs-lookup"><span data-stu-id="a65ad-169">101.05.16</span></span>

- <span data-ttu-id="a65ad-170">Verbeteringen in de logica voor snelle scannen om het aantal gescande bestanden aanzienlijk te verminderen</span><span class="sxs-lookup"><span data-stu-id="a65ad-170">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="a65ad-171">Ondersteuning [voor automatisch aanvullen toegevoegd](mac-resources.md#how-to-enable-autocompletion) voor het opdrachtregelhulpmiddel</span><span class="sxs-lookup"><span data-stu-id="a65ad-171">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="a65ad-172">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="a65ad-172">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="a65ad-173">101.03.12</span><span class="sxs-lookup"><span data-stu-id="a65ad-173">101.03.12</span></span>

- <span data-ttu-id="a65ad-174">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-174">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="a65ad-175">101.01.54</span><span class="sxs-lookup"><span data-stu-id="a65ad-175">101.01.54</span></span>

- <span data-ttu-id="a65ad-176">Verbeteringen rond compatibiliteit met Time Machine</span><span class="sxs-lookup"><span data-stu-id="a65ad-176">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="a65ad-177">Toegankelijkheidsverbeteringen</span><span class="sxs-lookup"><span data-stu-id="a65ad-177">Accessibility improvements</span></span>
- <span data-ttu-id="a65ad-178">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-178">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="a65ad-179">101.00.31</span><span class="sxs-lookup"><span data-stu-id="a65ad-179">101.00.31</span></span>

- <span data-ttu-id="a65ad-180">Verbeterde [onboarding-ervaring voor Intune-gebruikers](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="a65ad-180">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="a65ad-181">[Antivirusuitsluitingen ondersteunen nu jokertekens](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="a65ad-181">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="a65ad-182">De mogelijkheid toegevoegd om antivirusscans te activeren vanuit het contextmenu van macOS.</span><span class="sxs-lookup"><span data-stu-id="a65ad-182">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="a65ad-183">U kunt nu met de rechtermuisknop op een bestand of map in Finder klikken en **Scannen met Microsoft Defender voor eindpunt selecteren**</span><span class="sxs-lookup"><span data-stu-id="a65ad-183">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="a65ad-184">In-place product downgrades worden nu expliciet afgekeurd door het installatieprogramma.</span><span class="sxs-lookup"><span data-stu-id="a65ad-184">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="a65ad-185">Als u wilt downgraden, moet u eerst de bestaande versie verwijderen en uw apparaat opnieuw configureren</span><span class="sxs-lookup"><span data-stu-id="a65ad-185">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="a65ad-186">Andere prestatieverbeteringen & bug fixes</span><span class="sxs-lookup"><span data-stu-id="a65ad-186">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="a65ad-187">100.90.27</span><span class="sxs-lookup"><span data-stu-id="a65ad-187">100.90.27</span></span>

- <span data-ttu-id="a65ad-188">U kunt nu [een updatekanaal voor](mac-updates.md#set-the-channel-name) Microsoft Defender voor Eindpunt voor Mac instellen dat verschilt van het updatekanaal voor het hele systeem</span><span class="sxs-lookup"><span data-stu-id="a65ad-188">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint for Mac that is different from the system-wide update channel</span></span>
- <span data-ttu-id="a65ad-189">Pictogram Nieuw product</span><span class="sxs-lookup"><span data-stu-id="a65ad-189">New product icon</span></span>
- <span data-ttu-id="a65ad-190">Andere verbeteringen in de gebruikerservaring</span><span class="sxs-lookup"><span data-stu-id="a65ad-190">Other user experience improvements</span></span>
- <span data-ttu-id="a65ad-191">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="a65ad-191">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="a65ad-192">100.86.92</span><span class="sxs-lookup"><span data-stu-id="a65ad-192">100.86.92</span></span>

- <span data-ttu-id="a65ad-193">Verbeteringen rond compatibiliteit met Time Machine</span><span class="sxs-lookup"><span data-stu-id="a65ad-193">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="a65ad-194">Een probleem opgelost waarbij het product soms niet alle bestanden onder tijdens het verwijderen `/Library/Application Support/Microsoft/Defender` opsschoonde</span><span class="sxs-lookup"><span data-stu-id="a65ad-194">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="a65ad-195">Minder CPU-gebruik van het product wanneer Microsoft-producten worden bijgewerkt via Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="a65ad-195">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="a65ad-196">Andere prestatieverbeteringen & bug fixes</span><span class="sxs-lookup"><span data-stu-id="a65ad-196">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="a65ad-197">100.86.91</span><span class="sxs-lookup"><span data-stu-id="a65ad-197">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="a65ad-198">Als u de meest volledige beveiliging wilt garanderen voor uw macOS-apparaten en in overeenstemming met apple die de levering van macOS-beveiligingsupdates stopt voor besturingssysteemversies ouder dan [huidige – 2], worden MDATP voor Mac-implementatie en updates niet meer ondersteund op macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="a65ad-198">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="a65ad-199">MDATP voor Mac-updates en -verbeteringen worden geleverd aan apparaten met versies Catalina [10.15], Mojave [10.14] en High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="a65ad-199">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="a65ad-200">Als MDATP voor Mac al is geïmplementeerd op uw Sierra [10.12]-apparaten, kunt u een upgrade uitvoeren naar de nieuwste macOS-versie om het risico op verlies van beveiliging te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="a65ad-200">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="a65ad-201">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-201">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="a65ad-202">100.83.73</span><span class="sxs-lookup"><span data-stu-id="a65ad-202">100.83.73</span></span>

- <span data-ttu-id="a65ad-203">Meer besturingselementen voor IT-beheerders toegevoegd rond het beheer van [uitsluitingen,](mac-preferences.md#exclusion-merge-policy) [het beheer](mac-preferences.md#threat-type-settings-merge-policy)van instellingen voor bedreigingstype en [niet-toegestaan bedreigingsacties](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="a65ad-203">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="a65ad-204">Wanneer Volledige schijftoegang niet is ingeschakeld op het apparaat, wordt er nu een waarschuwing weergegeven in het statusmenu</span><span class="sxs-lookup"><span data-stu-id="a65ad-204">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="a65ad-205">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-205">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="a65ad-206">100.82.60</span><span class="sxs-lookup"><span data-stu-id="a65ad-206">100.82.60</span></span>

- <span data-ttu-id="a65ad-207">Er is een probleem opgelost waarbij het product niet na een definitieupdate kan beginnen.</span><span class="sxs-lookup"><span data-stu-id="a65ad-207">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="a65ad-208">100.80.42</span><span class="sxs-lookup"><span data-stu-id="a65ad-208">100.80.42</span></span>

- <span data-ttu-id="a65ad-209">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="a65ad-209">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="a65ad-210">100.79.42</span><span class="sxs-lookup"><span data-stu-id="a65ad-210">100.79.42</span></span>

- <span data-ttu-id="a65ad-211">Er is een probleem opgelost waarbij Microsoft Defender voor Eindpunt voor Mac soms tijdmachine verstoort</span><span class="sxs-lookup"><span data-stu-id="a65ad-211">Fixed an issue where Microsoft Defender for Endpoint for Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="a65ad-212">Een nieuwe schakelknop toegevoegd aan het hulpprogramma voor de opdrachtregel voor het testen van de connectiviteit met de backend-service</span><span class="sxs-lookup"><span data-stu-id="a65ad-212">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="a65ad-213">Extra mogelijkheid om de volledige bedreigingsgeschiedenis in de gebruikersinterface weer te geven (kan worden bekeken vanuit de **weergave Beveiligingsgeschiedenis)**</span><span class="sxs-lookup"><span data-stu-id="a65ad-213">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="a65ad-214">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-214">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="a65ad-215">100.72.15</span><span class="sxs-lookup"><span data-stu-id="a65ad-215">100.72.15</span></span>

- <span data-ttu-id="a65ad-216">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="a65ad-216">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="a65ad-217">100.70.99</span><span class="sxs-lookup"><span data-stu-id="a65ad-217">100.70.99</span></span>

- <span data-ttu-id="a65ad-218">Er is een probleem opgelost dat van invloed is op de mogelijkheid van sommige gebruikers om een upgrade uit te voeren naar macOS Catalina wanneer realtimebeveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a65ad-218">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="a65ad-219">Dit sporadische probleem is veroorzaakt door Microsoft Defender voor het vergrendelen van bestanden in het Catalina-upgradepakket tijdens het scannen op bedreigingen, wat leidde tot fouten in de upgradevolgorde.</span><span class="sxs-lookup"><span data-stu-id="a65ad-219">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="a65ad-220">100.68.99</span><span class="sxs-lookup"><span data-stu-id="a65ad-220">100.68.99</span></span>

- <span data-ttu-id="a65ad-221">De mogelijkheid toegevoegd om de antivirusfunctionaliteit te configureren voor gebruik in [de passieve modus](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="a65ad-221">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="a65ad-222">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-222">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="a65ad-223">100.65.28</span><span class="sxs-lookup"><span data-stu-id="a65ad-223">100.65.28</span></span>

- <span data-ttu-id="a65ad-224">Ondersteuning voor macOS Catalina toegevoegd</span><span class="sxs-lookup"><span data-stu-id="a65ad-224">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="a65ad-225">macOS 10.15 (Catalina) bevat nieuwe beveiligings- en privacyverbeteringen.</span><span class="sxs-lookup"><span data-stu-id="a65ad-225">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="a65ad-226">Vanaf deze versie hebben toepassingen standaard geen toegang tot bepaalde locaties op schijf (zoals Documenten, Downloads, Bureaublad, enzovoort) zonder expliciete toestemming.</span><span class="sxs-lookup"><span data-stu-id="a65ad-226">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="a65ad-227">Bij afwezigheid van deze toestemming kan Microsoft Defender voor Eindpunt uw apparaat niet volledig beveiligen.</span><span class="sxs-lookup"><span data-stu-id="a65ad-227">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="a65ad-228">Het mechanisme voor het verlenen van deze toestemming is afhankelijk van de manier waarop u Microsoft Defender voor Eindpunt hebt geïmplementeerd:</span><span class="sxs-lookup"><span data-stu-id="a65ad-228">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="a65ad-229">Zie de bijgewerkte instructies in het onderwerp Handmatige implementatie voor [handmatige](mac-install-manually.md#how-to-allow-full-disk-access) implementatie.</span><span class="sxs-lookup"><span data-stu-id="a65ad-229">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="a65ad-230">Zie de bijgewerkte instructies in de op [JAMF gebaseerde](mac-install-with-jamf.md) implementatie- en [Microsoft Intune-implementatieonderwerpen](mac-install-with-intune.md#create-system-configuration-profiles) voor beheerde implementaties.</span><span class="sxs-lookup"><span data-stu-id="a65ad-230">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="a65ad-231">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="a65ad-231">Performance improvements & bug fixes</span></span>
