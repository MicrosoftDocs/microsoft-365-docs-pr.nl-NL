---
title: Uitsluitingen configureren en valideren voor Microsoft Defender ATP voor Mac
description: Uitsluitingen voor MICROSOFT Defender ATP voor Mac verstrekken en valideren. Uitsluitingen kunnen worden ingesteld voor bestanden, mappen en processen.
keywords: microsoft, defender, atp, mac, exclusions, scans, antivirus
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
ms.openlocfilehash: 8efb90de58576b7c76a3b600d1e94713eb0c7b93
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057461"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="85d32-105">Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="85d32-105">Configure and validate exclusions for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="85d32-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="85d32-106">**Applies to:**</span></span>
- [<span data-ttu-id="85d32-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="85d32-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="85d32-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85d32-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="85d32-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="85d32-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="85d32-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="85d32-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="85d32-111">In dit artikel vindt u informatie over het definiëren van uitsluitingen die van toepassing zijn op scans op aanvraag, en realtime beveiliging en monitoring.</span><span class="sxs-lookup"><span data-stu-id="85d32-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

>[!IMPORTANT]
><span data-ttu-id="85d32-112">De uitsluitingen die in dit artikel worden beschreven, zijn niet van toepassing op andere mogelijkheden van Defender voor Eindpunt voor Mac, waaronder eindpuntdetectie en -antwoord (EDR).</span><span class="sxs-lookup"><span data-stu-id="85d32-112">The exclusions described in this article don't apply to other Defender for Endpoint for Mac capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="85d32-113">Bestanden die u uitsluit met de methoden die in dit artikel worden beschreven, kunnen nog steeds EDR-waarschuwingen en andere detecties activeren.</span><span class="sxs-lookup"><span data-stu-id="85d32-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="85d32-114">U kunt bepaalde bestanden, mappen, processen en proces geopende bestanden uitsluiten van Defender voor Eindpunt voor Mac-scans.</span><span class="sxs-lookup"><span data-stu-id="85d32-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Mac scans.</span></span>

<span data-ttu-id="85d32-115">Uitsluitingen kunnen handig zijn om onjuiste detecties te voorkomen van bestanden of software die uniek of aangepast zijn aan uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="85d32-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="85d32-116">Ze kunnen ook handig zijn voor het verminderen van prestatieproblemen die worden veroorzaakt door Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="85d32-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Mac.</span></span>

>[!WARNING]
><span data-ttu-id="85d32-117">Als u uitsluitingen definieert, wordt de beveiliging van Defender voor Eindpunt voor Mac lager.</span><span class="sxs-lookup"><span data-stu-id="85d32-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="85d32-118">U moet altijd de risico's evalueren die zijn gekoppeld aan het implementeren van uitsluitingen en u moet alleen bestanden uitsluiten die u zeker weet dat ze niet schadelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="85d32-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="85d32-119">Ondersteunde uitsluitingstypen</span><span class="sxs-lookup"><span data-stu-id="85d32-119">Supported exclusion types</span></span>

<span data-ttu-id="85d32-120">In de volgende tabel ziet u de uitsluitingstypen die worden ondersteund door Defender voor Eindpunt voor Mac.</span><span class="sxs-lookup"><span data-stu-id="85d32-120">The follow table shows the exclusion types supported by Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="85d32-121">Uitsluiting</span><span class="sxs-lookup"><span data-stu-id="85d32-121">Exclusion</span></span> | <span data-ttu-id="85d32-122">Definitie</span><span class="sxs-lookup"><span data-stu-id="85d32-122">Definition</span></span> | <span data-ttu-id="85d32-123">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="85d32-123">Examples</span></span>
---|---|---
<span data-ttu-id="85d32-124">Bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="85d32-124">File extension</span></span> | <span data-ttu-id="85d32-125">Alle bestanden met de extensie, overal op de computer</span><span class="sxs-lookup"><span data-stu-id="85d32-125">All files with the extension, anywhere on the machine</span></span> | `.test`
<span data-ttu-id="85d32-126">Bestand</span><span class="sxs-lookup"><span data-stu-id="85d32-126">File</span></span> | <span data-ttu-id="85d32-127">Een specifiek bestand dat is geïdentificeerd door het volledige pad</span><span class="sxs-lookup"><span data-stu-id="85d32-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="85d32-128">Map</span><span class="sxs-lookup"><span data-stu-id="85d32-128">Folder</span></span> | <span data-ttu-id="85d32-129">Alle bestanden onder de opgegeven map (recursief)</span><span class="sxs-lookup"><span data-stu-id="85d32-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="85d32-130">Proces</span><span class="sxs-lookup"><span data-stu-id="85d32-130">Process</span></span> | <span data-ttu-id="85d32-131">Een specifiek proces (opgegeven door het volledige pad of de bestandsnaam) en alle bestanden die hiermee worden geopend</span><span class="sxs-lookup"><span data-stu-id="85d32-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

<span data-ttu-id="85d32-132">Bestands-, map- en procesuitsluitingen ondersteunen de volgende jokertekens:</span><span class="sxs-lookup"><span data-stu-id="85d32-132">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="85d32-133">Jokerteken</span><span class="sxs-lookup"><span data-stu-id="85d32-133">Wildcard</span></span> | <span data-ttu-id="85d32-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="85d32-134">Description</span></span> | <span data-ttu-id="85d32-135">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="85d32-135">Example</span></span> | <span data-ttu-id="85d32-136">Overeenkomsten</span><span class="sxs-lookup"><span data-stu-id="85d32-136">Matches</span></span> | <span data-ttu-id="85d32-137">Komt niet overeen met</span><span class="sxs-lookup"><span data-stu-id="85d32-137">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="85d32-138">Komt overeen met een aantal tekens, inclusief geen tekens (houd er rekening mee dat wanneer dit jokerteken binnen een pad wordt gebruikt, dit slechts één map vervangt)</span><span class="sxs-lookup"><span data-stu-id="85d32-138">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/*/*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="85d32-139">?</span><span class="sxs-lookup"><span data-stu-id="85d32-139">?</span></span> | <span data-ttu-id="85d32-140">Komt overeen met een enkel teken</span><span class="sxs-lookup"><span data-stu-id="85d32-140">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

>[!NOTE]
><span data-ttu-id="85d32-141">Het product probeert vastkoppelingen op te lossen bij het evalueren van uitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="85d32-141">The product attempts to resolve firmlinks when evaluating exclusions.</span></span> <span data-ttu-id="85d32-142">Firmlink-resolutie werkt niet wanneer de uitsluiting jokertekens bevat of het doelbestand (op het `Data` volume) niet bestaat.</span><span class="sxs-lookup"><span data-stu-id="85d32-142">Firmlink resolution does not work when the exclusion contains wildcards or the target file (on the `Data` volume) does not exist.</span></span>

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="85d32-143">De lijst met uitsluitingen configureren</span><span class="sxs-lookup"><span data-stu-id="85d32-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="85d32-144">Vanuit de beheerconsole</span><span class="sxs-lookup"><span data-stu-id="85d32-144">From the management console</span></span>

<span data-ttu-id="85d32-145">Zie Voorkeuren instellen voor Defender voor Eindpunt voor Mac voor meer informatie over het configureren van uitsluitingen van JAMF, Intune of een andere [beheerconsole.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="85d32-145">For more information on how to configure exclusions from JAMF, Intune, or another management console, see [Set preferences for Defender for Endpoint for Mac](mac-preferences.md).</span></span>

### <a name="from-the-user-interface"></a><span data-ttu-id="85d32-146">Vanuit de gebruikersinterface</span><span class="sxs-lookup"><span data-stu-id="85d32-146">From the user interface</span></span>

<span data-ttu-id="85d32-147">Open de toepassing Defender voor eindpunt en ga naar **Instellingen beheren** Toevoegen of Uitsluiting  >  **verwijderen...**, zoals wordt weergegeven in de volgende schermafbeelding:</span><span class="sxs-lookup"><span data-stu-id="85d32-147">Open the Defender for Endpoint application and navigate to **Manage settings** > **Add or Remove Exclusion...**, as shown in the following screenshot:</span></span>

![Schermafbeelding van uitsluitingen beheren](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-37-exclusions)

<span data-ttu-id="85d32-149">Selecteer het type uitsluiting dat u wilt toevoegen en volg de aanwijzingen.</span><span class="sxs-lookup"><span data-stu-id="85d32-149">Select the type of exclusion that you wish to add and follow the prompts.</span></span>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="85d32-150">Lijsten met uitsluitingen valideren met het EICAR-testbestand</span><span class="sxs-lookup"><span data-stu-id="85d32-150">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="85d32-151">U kunt valideren dat uw uitsluitingslijsten werken met behulp `curl` van het downloaden van een testbestand.</span><span class="sxs-lookup"><span data-stu-id="85d32-151">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="85d32-152">Vervang in het volgende Bash-fragment `test.txt` door een bestand dat voldoet aan de uitsluitingsregels.</span><span class="sxs-lookup"><span data-stu-id="85d32-152">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="85d32-153">Als u bijvoorbeeld de extensie hebt uitgesloten, vervangt `.testing` u `test.txt` door `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="85d32-153">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="85d32-154">Als u een pad test, controleert u of u de opdracht binnen dat pad hebt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="85d32-154">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="85d32-155">Als Defender voor Eindpunt voor Mac malware rapporteert, werkt de regel niet.</span><span class="sxs-lookup"><span data-stu-id="85d32-155">If Defender for Endpoint for Mac reports malware, then the rule is not working.</span></span> <span data-ttu-id="85d32-156">Als er geen malwarerapport is en het gedownloade bestand bestaat, werkt de uitsluiting.</span><span class="sxs-lookup"><span data-stu-id="85d32-156">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="85d32-157">U kunt het bestand openen om te bevestigen dat de inhoud hetzelfde is als wat wordt beschreven op de website van het [EICAR-testbestand.](http://2016.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="85d32-157">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="85d32-158">Als u geen internetverbinding hebt, kunt u uw eigen EICAR-testbestand maken.</span><span class="sxs-lookup"><span data-stu-id="85d32-158">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="85d32-159">Schrijf de EICAR-tekenreeks naar een nieuw tekstbestand met de volgende opdracht Bash:</span><span class="sxs-lookup"><span data-stu-id="85d32-159">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="85d32-160">U kunt de tekenreeks ook kopiëren naar een leeg tekstbestand en proberen deze op te slaan met de bestandsnaam of in de map die u probeert uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="85d32-160">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="85d32-161">Bedreigingen toestaan</span><span class="sxs-lookup"><span data-stu-id="85d32-161">Allow threats</span></span>

<span data-ttu-id="85d32-162">Naast het uitsluiten van het scannen van bepaalde inhoud, kunt u het product ook zo configureren dat bepaalde categorieën bedreigingen niet worden gedetecteerd (geïdentificeerd met de naam van de bedreiging).</span><span class="sxs-lookup"><span data-stu-id="85d32-162">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="85d32-163">U moet voorzichtig zijn bij het gebruik van deze functionaliteit, omdat uw apparaat hierdoor niet wordt beveiligd.</span><span class="sxs-lookup"><span data-stu-id="85d32-163">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="85d32-164">Als u een bedreigingsnaam wilt toevoegen aan de toegestane lijst, voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="85d32-164">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="85d32-165">De bedreigingsnaam die is gekoppeld aan een detectie op uw apparaat, kunt u verkrijgen met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="85d32-165">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="85d32-166">Als u bijvoorbeeld (de bedreigingsnaam die is gekoppeld aan de EICAR-detectie) wilt toevoegen aan de toegestane lijst, voert u `EICAR-Test-File (not a virus)` de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="85d32-166">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
