---
title: Nieuwe functies in Microsoft Defender voor Eindpunt op Mac
description: Meer informatie over de belangrijkste wijzigingen voor eerdere versies van Microsoft Defender voor Eindpunt op Mac.
keywords: microsoft, Defender, Microsoft Defender voor Eindpunt, Mac, installatie, macos, whatsnew
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
ms.openlocfilehash: a6415ec7d39bceeb4b68de164bbdcf6ef34755ff
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984770"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="9fda3-104">Nieuwe functies in Microsoft Defender voor Eindpunt op Mac</span><span class="sxs-lookup"><span data-stu-id="9fda3-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9fda3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9fda3-105">**Applies to:**</span></span>
- [<span data-ttu-id="9fda3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="9fda3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9fda3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9fda3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9fda3-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="9fda3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9fda3-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="9fda3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="9fda3-110">Voor macOS 11 (Big Sur) vereist Microsoft Defender voor Eindpunt extra configuratieprofielen.</span><span class="sxs-lookup"><span data-stu-id="9fda3-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="9fda3-111">Als u een bestaande klant bent die upgradet van eerdere versies van macOS, moet u de extra configuratieprofielen implementeren die op [deze pagina worden vermeld.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9fda3-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1013269-20121042132690"></a><span data-ttu-id="9fda3-112">101.32.69 (20.121042.13269.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-112">101.32.69 (20.121042.13269.0)</span></span>

- <span data-ttu-id="9fda3-113">Er is een probleem opgelost waarbij gelijktijdige toegang tot de sleutelhanger van Microsoft Defender voor Eindpunt en andere toepassingen kan leiden tot sleutelhangerbe beschadiging.</span><span class="sxs-lookup"><span data-stu-id="9fda3-113">Addressed an issue where concurrent access to the keychain from Microsoft Defender for Endpoint and other applications can lead to keychain corruption.</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="9fda3-114">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-114">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="9fda3-115">Vanaf deze versie worden bedreigingen die zijn gedetecteerd tijdens on-demand antivirusscans die worden geactiveerd via de opdrachtregelclient, automatisch verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9fda3-115">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="9fda3-116">Bedreigingen die zijn gedetecteerd tijdens scans die via de gebruikersinterface worden geactiveerd, vereisen nog steeds handmatige actie.</span><span class="sxs-lookup"><span data-stu-id="9fda3-116">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="9fda3-117">`mdatp diagnostic real-time-protection-statistics` ondersteunt nu twee extra schakelopties:</span><span class="sxs-lookup"><span data-stu-id="9fda3-117">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="9fda3-118">`--sort`: sorteert de uitvoer aflopend op het totale aantal gescande bestanden</span><span class="sxs-lookup"><span data-stu-id="9fda3-118">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="9fda3-119">`--top N`: geeft de hoogste N-resultaten weer (werkt alleen als `--sort` deze ook is opgegeven)</span><span class="sxs-lookup"><span data-stu-id="9fda3-119">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="9fda3-120">Prestatieverbeteringen (met name voor wanneer ERWD wordt gebruikt) & oplossingen</span><span class="sxs-lookup"><span data-stu-id="9fda3-120">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="9fda3-121">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-121">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="9fda3-122">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span><span class="sxs-lookup"><span data-stu-id="9fda3-122">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="9fda3-123">Met deze oplossing wordt de functionaliteit & Vulnerability Management (TVM) hersteld.</span><span class="sxs-lookup"><span data-stu-id="9fda3-123">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="9fda3-124">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-124">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="9fda3-125">Microsoft Defender voor Eindpunt op macOS is nu beschikbaar in preview voor klanten van de Amerikaanse overheid.</span><span class="sxs-lookup"><span data-stu-id="9fda3-125">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="9fda3-126">Zie Microsoft [Defender for Endpoint voor klanten](gov.md)van de Amerikaanse overheid voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9fda3-126">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="9fda3-127">Prestatieverbeteringen (met name voor de situatie waarin de XCode Simulator-app wordt gebruikt) & problemen.</span><span class="sxs-lookup"><span data-stu-id="9fda3-127">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="9fda3-128">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-128">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="9fda3-129">Er is een nieuwe optie toegevoegd aan het opdrachtregelprogramma om informatie over de laatste scan op aanvraag weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9fda3-129">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="9fda3-130">Als u informatie wilt weergeven over de laatste scan op aanvraag, voer dan `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="9fda3-130">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="9fda3-131">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-131">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="9fda3-132">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-132">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="9fda3-133">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-133">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="9fda3-134">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-134">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="9fda3-135">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-135">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="9fda3-136">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-136">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="9fda3-137">De syntaxis van het oude opdrachtregelprogramma is afgeschaft met deze release.</span><span class="sxs-lookup"><span data-stu-id="9fda3-137">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="9fda3-138">Zie Resources voor informatie over de nieuwe [syntaxis.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="9fda3-138">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="9fda3-139">Er is een nieuwe opdrachtregelknop toegevoegd om de netwerkextensie uit te schakelen: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="9fda3-139">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="9fda3-140">Deze opdracht kan handig zijn om problemen met netwerken op te lossen die kunnen worden gerelateerd aan Microsoft Defender voor Eindpunt op Mac</span><span class="sxs-lookup"><span data-stu-id="9fda3-140">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="9fda3-141">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-141">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="9fda3-142">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-142">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="9fda3-143">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="9fda3-143">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="9fda3-144">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-144">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="9fda3-145">Verbeterde de betrouwbaarheid van de agent bij het uitvoeren van macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="9fda3-145">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="9fda3-146">Een nieuwe opdrachtregelschakelaar () toegevoegd om AV-uitsluitingen `--ignore-exclusions` te negeren tijdens aangepaste scans ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="9fda3-146">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="9fda3-147">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-147">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="9fda3-148">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="9fda3-148">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="9fda3-149">Verwijderde voorwaarden wanneer Microsoft Defender voor Eindpunt een macOS 11 -bug (Big Sur) activeert die zich manifesteert in een kernel-paniek</span><span class="sxs-lookup"><span data-stu-id="9fda3-149">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="9fda3-150">Een geheugenlek in de systeemextensie Endpoint Security opgelost bij het uitvoeren op mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="9fda3-150">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="9fda3-151">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="9fda3-151">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="9fda3-152">101.10.72</span><span class="sxs-lookup"><span data-stu-id="9fda3-152">101.10.72</span></span>

- <span data-ttu-id="9fda3-153">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="9fda3-153">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="9fda3-154">101.09.61</span><span class="sxs-lookup"><span data-stu-id="9fda3-154">101.09.61</span></span>

- <span data-ttu-id="9fda3-155">Een nieuwe beheerde voorkeur voor het [uitschakelen van de optie voor het verzenden van feedback toegevoegd](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="9fda3-155">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="9fda3-156">Het pictogram Statusmenu geeft nu een gezonde status weer wanneer de productinstellingen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="9fda3-156">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="9fda3-157">Voorheen werd in het statusmenupictogram een waarschuwings- of foutstatus weergegeven, ook al zijn de productinstellingen beheerd door de beheerder</span><span class="sxs-lookup"><span data-stu-id="9fda3-157">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="9fda3-158">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-158">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="9fda3-159">101.09.50</span><span class="sxs-lookup"><span data-stu-id="9fda3-159">101.09.50</span></span>

- <span data-ttu-id="9fda3-160">Deze productversie is gevalideerd op macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="9fda3-160">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="9fda3-161">De nieuwe syntaxis voor het `mdatp` opdrachtregelhulpmiddel is nu de standaard syntaxis.</span><span class="sxs-lookup"><span data-stu-id="9fda3-161">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="9fda3-162">Zie Resources [for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line) (Bronnen voor Microsoft Defender voor eindpunt op macOS) voor meer informatie over de nieuwe syntaxis.</span><span class="sxs-lookup"><span data-stu-id="9fda3-162">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="9fda3-163">De syntaxis van het oude opdrachtregelprogramma wordt op 1 januari **2021** uit het product verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9fda3-163">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="9fda3-164">Uitgebreid met een nieuwe parameter ( ) waarmee de diagnostische `mdatp diagnostic create` `--path [directory]` logboeken kunnen worden opgeslagen in een andere adreslijst</span><span class="sxs-lookup"><span data-stu-id="9fda3-164">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="9fda3-165">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-165">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="9fda3-166">101.09.49</span><span class="sxs-lookup"><span data-stu-id="9fda3-166">101.09.49</span></span>

- <span data-ttu-id="9fda3-167">Verbeteringen in de gebruikersinterface om onderscheid te maken tussen uitsluitingen die worden beheerd door de IT-beheerder en uitsluitingen die door de lokale gebruiker zijn gedefinieerd</span><span class="sxs-lookup"><span data-stu-id="9fda3-167">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="9fda3-168">Verbeterde CPU-gebruik tijdens scans op aanvraag</span><span class="sxs-lookup"><span data-stu-id="9fda3-168">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="9fda3-169">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-169">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="9fda3-170">101.07.23</span><span class="sxs-lookup"><span data-stu-id="9fda3-170">101.07.23</span></span>

- <span data-ttu-id="9fda3-171">Nieuwe velden toegevoegd aan de uitvoer van voor het controleren van de status van de passieve modus en `mdatp --health` de EDR groep-id</span><span class="sxs-lookup"><span data-stu-id="9fda3-171">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="9fda3-172">`mdatp --health` wordt vervangen door `mdatp health` in een toekomstige productupdate.</span><span class="sxs-lookup"><span data-stu-id="9fda3-172">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="9fda3-173">Een fout opgelost waarbij automatische voorbeeldinzending niet is gemarkeerd als beheerd in de gebruikersinterface</span><span class="sxs-lookup"><span data-stu-id="9fda3-173">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="9fda3-174">Er zijn nieuwe instellingen toegevoegd voor het beheren van het bewaren van items in de antivirusscangeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="9fda3-174">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="9fda3-175">U kunt nu het aantal dagen opgeven om items in de [scangeschiedenis](mac-preferences.md#antivirus-scan-history-retention-in-days) te behouden en het maximum aantal items in de [scangeschiedenis opgeven](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="9fda3-175">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="9fda3-176">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="9fda3-176">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="9fda3-177">101.06.63</span><span class="sxs-lookup"><span data-stu-id="9fda3-177">101.06.63</span></span>

- <span data-ttu-id="9fda3-178">Er is een prestatieregressie aangepakt die in versie is `101.05.17` geïntroduceerd.</span><span class="sxs-lookup"><span data-stu-id="9fda3-178">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="9fda3-179">De regressie is geïntroduceerd met de fix om de kernel-paniek te elimineren die sommige klanten hebben waargenomen bij het openen van SMB-aandelen.</span><span class="sxs-lookup"><span data-stu-id="9fda3-179">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="9fda3-180">We hebben deze codewijziging teruggedraaid en onderzoeken alternatieve manieren om de kernelpaniek te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="9fda3-180">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="9fda3-181">101.05.17</span><span class="sxs-lookup"><span data-stu-id="9fda3-181">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9fda3-182">We werken aan een nieuwe en verbeterde syntaxis voor het `mdatp` opdrachtregelhulpmiddel.</span><span class="sxs-lookup"><span data-stu-id="9fda3-182">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="9fda3-183">De nieuwe syntaxis is momenteel de standaardinstelling in de Insider Fast- en Insider Slow-updatekanalen.</span><span class="sxs-lookup"><span data-stu-id="9fda3-183">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="9fda3-184">We raden u aan om uzelf te famliliariseren met deze nieuwe syntaxis.</span><span class="sxs-lookup"><span data-stu-id="9fda3-184">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="9fda3-185">We blijven de oude syntaxis ondersteunen in parallel met de nieuwe syntaxis en zorgen voor meer communicatie rond het afbouwplan voor de oude syntaxis in de komende maanden.</span><span class="sxs-lookup"><span data-stu-id="9fda3-185">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="9fda3-186">Adresseerde een kernel-paniek die zich soms voordeed bij het openen van SMB-bestandsaandelen</span><span class="sxs-lookup"><span data-stu-id="9fda3-186">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="9fda3-187">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-187">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="9fda3-188">101.05.16</span><span class="sxs-lookup"><span data-stu-id="9fda3-188">101.05.16</span></span>

- <span data-ttu-id="9fda3-189">Verbeteringen in de logica voor snelle scannen om het aantal gescande bestanden aanzienlijk te verminderen</span><span class="sxs-lookup"><span data-stu-id="9fda3-189">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="9fda3-190">Ondersteuning [voor automatisch aanvullen toegevoegd](mac-resources.md#how-to-enable-autocompletion) voor het opdrachtregelhulpmiddel</span><span class="sxs-lookup"><span data-stu-id="9fda3-190">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="9fda3-191">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="9fda3-191">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="9fda3-192">101.03.12</span><span class="sxs-lookup"><span data-stu-id="9fda3-192">101.03.12</span></span>

- <span data-ttu-id="9fda3-193">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-193">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="9fda3-194">101.01.54</span><span class="sxs-lookup"><span data-stu-id="9fda3-194">101.01.54</span></span>

- <span data-ttu-id="9fda3-195">Verbeteringen rond compatibiliteit met Time Machine</span><span class="sxs-lookup"><span data-stu-id="9fda3-195">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="9fda3-196">Toegankelijkheidsverbeteringen</span><span class="sxs-lookup"><span data-stu-id="9fda3-196">Accessibility improvements</span></span>
- <span data-ttu-id="9fda3-197">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-197">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="9fda3-198">101.00.31</span><span class="sxs-lookup"><span data-stu-id="9fda3-198">101.00.31</span></span>

- <span data-ttu-id="9fda3-199">Verbeterde [onboarding-ervaring voor Intune-gebruikers](/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="9fda3-199">Improved [product onboarding experience for Intune users](/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="9fda3-200">[Antivirusuitsluitingen ondersteunen nu jokertekens](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="9fda3-200">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="9fda3-201">De mogelijkheid toegevoegd om antivirusscans te activeren vanuit het contextmenu van macOS.</span><span class="sxs-lookup"><span data-stu-id="9fda3-201">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="9fda3-202">U kunt nu met de rechtermuisknop op een bestand of map in Finder klikken en **Scannen met Microsoft Defender voor eindpunt selecteren**</span><span class="sxs-lookup"><span data-stu-id="9fda3-202">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="9fda3-203">In-place product downgrades worden nu expliciet afgekeurd door het installatieprogramma.</span><span class="sxs-lookup"><span data-stu-id="9fda3-203">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="9fda3-204">Als u wilt downgraden, moet u eerst de bestaande versie verwijderen en uw apparaat opnieuw configureren</span><span class="sxs-lookup"><span data-stu-id="9fda3-204">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="9fda3-205">Andere prestatieverbeteringen & bug fixes</span><span class="sxs-lookup"><span data-stu-id="9fda3-205">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="9fda3-206">100.90.27</span><span class="sxs-lookup"><span data-stu-id="9fda3-206">100.90.27</span></span>

- <span data-ttu-id="9fda3-207">U kunt nu [een updatekanaal voor](mac-updates.md#set-the-channel-name) Microsoft Defender voor Eindpunt instellen voor macOS dat verschilt van het systeembrede updatekanaal</span><span class="sxs-lookup"><span data-stu-id="9fda3-207">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="9fda3-208">Pictogram Nieuw product</span><span class="sxs-lookup"><span data-stu-id="9fda3-208">New product icon</span></span>
- <span data-ttu-id="9fda3-209">Andere verbeteringen in de gebruikerservaring</span><span class="sxs-lookup"><span data-stu-id="9fda3-209">Other user experience improvements</span></span>
- <span data-ttu-id="9fda3-210">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="9fda3-210">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="9fda3-211">100.86.92</span><span class="sxs-lookup"><span data-stu-id="9fda3-211">100.86.92</span></span>

- <span data-ttu-id="9fda3-212">Verbeteringen rond compatibiliteit met Time Machine</span><span class="sxs-lookup"><span data-stu-id="9fda3-212">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="9fda3-213">Een probleem opgelost waarbij het product soms niet alle bestanden onder tijdens het verwijderen `/Library/Application Support/Microsoft/Defender` opsschoonde</span><span class="sxs-lookup"><span data-stu-id="9fda3-213">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="9fda3-214">Minder CPU-gebruik van het product wanneer Microsoft-producten worden bijgewerkt via Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="9fda3-214">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="9fda3-215">Andere prestatieverbeteringen & bug fixes</span><span class="sxs-lookup"><span data-stu-id="9fda3-215">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="9fda3-216">100.86.91</span><span class="sxs-lookup"><span data-stu-id="9fda3-216">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="9fda3-217">Als u de meest volledige beveiliging wilt garanderen voor uw macOS-apparaten en in overeenstemming met apple die de levering van macOS-beveiligingsupdates stopt voor besturingssysteemversies ouder dan [huidige – 2], worden MDATP voor Mac-implementatie en updates niet meer ondersteund op macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="9fda3-217">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="9fda3-218">MDATP voor Mac-updates en -verbeteringen worden geleverd aan apparaten met versies Catalina [10.15], Mojave [10.14] en High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="9fda3-218">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="9fda3-219">Als MDATP voor Mac al is geïmplementeerd op uw Sierra [10.12]-apparaten, kunt u een upgrade uitvoeren naar de nieuwste macOS-versie om het risico op verlies van beveiliging te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="9fda3-219">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="9fda3-220">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-220">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="9fda3-221">100.83.73</span><span class="sxs-lookup"><span data-stu-id="9fda3-221">100.83.73</span></span>

- <span data-ttu-id="9fda3-222">Meer besturingselementen voor IT-beheerders toegevoegd rond het beheer van [uitsluitingen,](mac-preferences.md#exclusion-merge-policy) [het beheer](mac-preferences.md#threat-type-settings-merge-policy)van instellingen voor bedreigingstype en [niet-toegestaan bedreigingsacties](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="9fda3-222">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="9fda3-223">Wanneer Volledige schijftoegang niet is ingeschakeld op het apparaat, wordt er nu een waarschuwing weergegeven in het statusmenu</span><span class="sxs-lookup"><span data-stu-id="9fda3-223">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="9fda3-224">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-224">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="9fda3-225">100.82.60</span><span class="sxs-lookup"><span data-stu-id="9fda3-225">100.82.60</span></span>

- <span data-ttu-id="9fda3-226">Er is een probleem opgelost waarbij het product niet na een definitieupdate kan beginnen.</span><span class="sxs-lookup"><span data-stu-id="9fda3-226">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="9fda3-227">100.80.42</span><span class="sxs-lookup"><span data-stu-id="9fda3-227">100.80.42</span></span>

- <span data-ttu-id="9fda3-228">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="9fda3-228">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="9fda3-229">100.79.42</span><span class="sxs-lookup"><span data-stu-id="9fda3-229">100.79.42</span></span>

- <span data-ttu-id="9fda3-230">Er is een probleem opgelost waarbij Microsoft Defender voor Eindpunt op Mac soms tijdmachine verstoort</span><span class="sxs-lookup"><span data-stu-id="9fda3-230">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="9fda3-231">Een nieuwe schakelknop toegevoegd aan het hulpprogramma voor de opdrachtregel voor het testen van de connectiviteit met de backend-service</span><span class="sxs-lookup"><span data-stu-id="9fda3-231">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="9fda3-232">Extra mogelijkheid om de volledige bedreigingsgeschiedenis in de gebruikersinterface weer te geven (kan worden bekeken vanuit de **weergave Beveiligingsgeschiedenis)**</span><span class="sxs-lookup"><span data-stu-id="9fda3-232">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="9fda3-233">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-233">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="9fda3-234">100.72.15</span><span class="sxs-lookup"><span data-stu-id="9fda3-234">100.72.15</span></span>

- <span data-ttu-id="9fda3-235">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="9fda3-235">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="9fda3-236">100.70.99</span><span class="sxs-lookup"><span data-stu-id="9fda3-236">100.70.99</span></span>

- <span data-ttu-id="9fda3-237">Er is een probleem opgelost dat van invloed is op de mogelijkheid van sommige gebruikers om een upgrade uit te voeren naar macOS Catalina wanneer realtimebeveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9fda3-237">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="9fda3-238">Dit sporadische probleem is veroorzaakt door Microsoft Defender voor het vergrendelen van bestanden in het Catalina-upgradepakket tijdens het scannen op bedreigingen, wat leidde tot fouten in de upgradevolgorde.</span><span class="sxs-lookup"><span data-stu-id="9fda3-238">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="9fda3-239">100.68.99</span><span class="sxs-lookup"><span data-stu-id="9fda3-239">100.68.99</span></span>

- <span data-ttu-id="9fda3-240">De mogelijkheid toegevoegd om de antivirusfunctionaliteit te configureren voor gebruik in [de passieve modus](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="9fda3-240">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="9fda3-241">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-241">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="9fda3-242">100.65.28</span><span class="sxs-lookup"><span data-stu-id="9fda3-242">100.65.28</span></span>

- <span data-ttu-id="9fda3-243">Ondersteuning voor macOS Catalina toegevoegd</span><span class="sxs-lookup"><span data-stu-id="9fda3-243">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="9fda3-244">macOS 10.15 (Catalina) bevat nieuwe beveiligings- en privacyverbeteringen.</span><span class="sxs-lookup"><span data-stu-id="9fda3-244">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="9fda3-245">Vanaf deze versie hebben toepassingen standaard geen toegang tot bepaalde locaties op schijf (zoals Documenten, Downloads, Bureaublad, enzovoort) zonder expliciete toestemming.</span><span class="sxs-lookup"><span data-stu-id="9fda3-245">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="9fda3-246">Bij afwezigheid van deze toestemming kan Microsoft Defender voor Eindpunt uw apparaat niet volledig beveiligen.</span><span class="sxs-lookup"><span data-stu-id="9fda3-246">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="9fda3-247">Het mechanisme voor het verlenen van deze toestemming is afhankelijk van de manier waarop u Microsoft Defender voor Eindpunt hebt geïmplementeerd:</span><span class="sxs-lookup"><span data-stu-id="9fda3-247">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="9fda3-248">Zie de bijgewerkte instructies in het onderwerp Handmatige implementatie voor [handmatige](mac-install-manually.md#how-to-allow-full-disk-access) implementatie.</span><span class="sxs-lookup"><span data-stu-id="9fda3-248">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="9fda3-249">Zie de bijgewerkte instructies in de op [JAMF gebaseerde](mac-install-with-jamf.md) implementatie- en Microsoft Intune [implementatieonderwerpen](mac-install-with-intune.md#create-system-configuration-profiles) voor beheerde implementaties.</span><span class="sxs-lookup"><span data-stu-id="9fda3-249">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="9fda3-250">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="9fda3-250">Performance improvements & bug fixes</span></span>
