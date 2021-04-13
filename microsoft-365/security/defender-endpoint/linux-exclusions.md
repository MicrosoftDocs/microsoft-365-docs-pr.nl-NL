---
title: Uitsluitingen configureren en valideren voor Microsoft Defender ATP voor Linux
description: Uitsluitingen voor Microsoft Defender ATP voor Linux verstrekken en valideren. Uitsluitingen kunnen worden ingesteld voor bestanden, mappen en processen.
keywords: microsoft, defender, atp, linux, exclusions, scans, antivirus
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
ms.openlocfilehash: fbc8fe7ef6f9af86debdeb0826865c88e86b2c6a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688187"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="aef17-105">Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="aef17-105">Configure and validate exclusions for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aef17-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="aef17-106">**Applies to:**</span></span>
- [<span data-ttu-id="aef17-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="aef17-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aef17-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aef17-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aef17-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="aef17-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aef17-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="aef17-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="aef17-111">In dit artikel vindt u informatie over het definiëren van uitsluitingen die van toepassing zijn op scans op aanvraag, en realtime beveiliging en monitoring.</span><span class="sxs-lookup"><span data-stu-id="aef17-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aef17-112">De uitsluitingen die in dit artikel worden beschreven, zijn niet van toepassing op andere Mogelijkheden van Defender voor Endpoint voor Linux, waaronder eindpuntdetectie en -antwoord (EDR).</span><span class="sxs-lookup"><span data-stu-id="aef17-112">The exclusions described in this article don't apply to other Defender for Endpoint for Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="aef17-113">Bestanden die u uitsluit met de methoden die in dit artikel worden beschreven, kunnen nog steeds EDR-waarschuwingen en andere detecties activeren.</span><span class="sxs-lookup"><span data-stu-id="aef17-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="aef17-114">U kunt bepaalde bestanden, mappen, processen en proces geopende bestanden uitsluiten van Defender voor Eindpunt voor Linux-scans.</span><span class="sxs-lookup"><span data-stu-id="aef17-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Linux scans.</span></span>

<span data-ttu-id="aef17-115">Uitsluitingen kunnen handig zijn om onjuiste detecties te voorkomen van bestanden of software die uniek of aangepast zijn aan uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aef17-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="aef17-116">Ze kunnen ook handig zijn voor het verminderen van prestatieproblemen die worden veroorzaakt door Defender voor Eindpunt voor Linux.</span><span class="sxs-lookup"><span data-stu-id="aef17-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="aef17-117">Als u uitsluitingen definieert, wordt de bescherming van Defender voor Eindpunt voor Linux verlaagd.</span><span class="sxs-lookup"><span data-stu-id="aef17-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Linux.</span></span> <span data-ttu-id="aef17-118">U moet altijd de risico's evalueren die zijn gekoppeld aan het implementeren van uitsluitingen en u moet alleen bestanden uitsluiten die u zeker weet dat ze niet schadelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="aef17-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="aef17-119">Ondersteunde uitsluitingstypen</span><span class="sxs-lookup"><span data-stu-id="aef17-119">Supported exclusion types</span></span>

<span data-ttu-id="aef17-120">In de volgende tabel ziet u de uitsluitingstypen die worden ondersteund door Defender voor Eindpunt voor Linux.</span><span class="sxs-lookup"><span data-stu-id="aef17-120">The follow table shows the exclusion types supported by Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="aef17-121">Uitsluiting</span><span class="sxs-lookup"><span data-stu-id="aef17-121">Exclusion</span></span> | <span data-ttu-id="aef17-122">Definitie</span><span class="sxs-lookup"><span data-stu-id="aef17-122">Definition</span></span> | <span data-ttu-id="aef17-123">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="aef17-123">Examples</span></span>
---|---|---
<span data-ttu-id="aef17-124">Bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="aef17-124">File extension</span></span> | <span data-ttu-id="aef17-125">Alle bestanden met de extensie, overal op het apparaat</span><span class="sxs-lookup"><span data-stu-id="aef17-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="aef17-126">Bestand</span><span class="sxs-lookup"><span data-stu-id="aef17-126">File</span></span> | <span data-ttu-id="aef17-127">Een specifiek bestand dat is geïdentificeerd door het volledige pad</span><span class="sxs-lookup"><span data-stu-id="aef17-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="aef17-128">Map</span><span class="sxs-lookup"><span data-stu-id="aef17-128">Folder</span></span> | <span data-ttu-id="aef17-129">Alle bestanden onder de opgegeven map (recursief)</span><span class="sxs-lookup"><span data-stu-id="aef17-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="aef17-130">Proces</span><span class="sxs-lookup"><span data-stu-id="aef17-130">Process</span></span> | <span data-ttu-id="aef17-131">Een specifiek proces (opgegeven door het volledige pad of de bestandsnaam) en alle bestanden die hiermee worden geopend</span><span class="sxs-lookup"><span data-stu-id="aef17-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="aef17-132">De bovenstaande paden moeten harde koppelingen zijn, geen symbolische koppelingen, om te kunnen worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="aef17-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="aef17-133">U kunt controleren of een pad een symbolische koppeling is door te `file <path-name>` lopen.</span><span class="sxs-lookup"><span data-stu-id="aef17-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="aef17-134">Bestands-, map- en procesuitsluitingen ondersteunen de volgende jokertekens:</span><span class="sxs-lookup"><span data-stu-id="aef17-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="aef17-135">Jokerteken</span><span class="sxs-lookup"><span data-stu-id="aef17-135">Wildcard</span></span> | <span data-ttu-id="aef17-136">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="aef17-136">Description</span></span> | <span data-ttu-id="aef17-137">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="aef17-137">Example</span></span> | <span data-ttu-id="aef17-138">Overeenkomsten</span><span class="sxs-lookup"><span data-stu-id="aef17-138">Matches</span></span> | <span data-ttu-id="aef17-139">Komt niet overeen met</span><span class="sxs-lookup"><span data-stu-id="aef17-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="aef17-140">Komt overeen met een aantal tekens, inclusief geen tekens (houd er rekening mee dat wanneer dit jokerteken binnen een pad wordt gebruikt, dit slechts één map vervangt)</span><span class="sxs-lookup"><span data-stu-id="aef17-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="aef17-141">?</span><span class="sxs-lookup"><span data-stu-id="aef17-141">?</span></span> | <span data-ttu-id="aef17-142">Komt overeen met een enkel teken</span><span class="sxs-lookup"><span data-stu-id="aef17-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="aef17-143">De lijst met uitsluitingen configureren</span><span class="sxs-lookup"><span data-stu-id="aef17-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="aef17-144">Vanuit de beheerconsole</span><span class="sxs-lookup"><span data-stu-id="aef17-144">From the management console</span></span>

<span data-ttu-id="aef17-145">Zie Voorkeuren instellen voor Defender voor Eindpunt voor Linux voor meer informatie over het configureren van uitsluitingen van Puppet, Ansible of een andere [beheerconsole.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="aef17-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="aef17-146">Vanuit de opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="aef17-146">From the command line</span></span>

<span data-ttu-id="aef17-147">Voer de volgende opdracht uit om de beschikbare schakelopties voor het beheren van uitsluitingen te bekijken:</span><span class="sxs-lookup"><span data-stu-id="aef17-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="aef17-148">Wanneer u uitsluitingen configureert met jokertekens, sluit u de parameter tussen dubbele aanhalingstekens om gglobbing te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="aef17-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="aef17-149">Voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="aef17-149">Examples:</span></span>

- <span data-ttu-id="aef17-150">Een uitsluiting voor een bestandsextensie toevoegen:</span><span class="sxs-lookup"><span data-stu-id="aef17-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="aef17-151">Een uitsluiting voor een bestand toevoegen:</span><span class="sxs-lookup"><span data-stu-id="aef17-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="aef17-152">Een uitsluiting voor een map toevoegen:</span><span class="sxs-lookup"><span data-stu-id="aef17-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="aef17-153">Een uitsluiting voor een map met een jokerteken toevoegen:</span><span class="sxs-lookup"><span data-stu-id="aef17-153">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="aef17-154">Hiermee worden paden slechts één niveau lager *dan /var/* uitgesloten, maar geen mappen die dieper zijn geneste; bijvoorbeeld */var/this-subfolder/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="aef17-154">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="aef17-155">Hiermee worden alle paden uitgesloten waarvan de bovenliggende paden */var/ zijn;* bijvoorbeeld */var/this-subfolder/and-this-subfolder-as-well*.</span><span class="sxs-lookup"><span data-stu-id="aef17-155">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="aef17-156">Een uitsluiting voor een proces toevoegen:</span><span class="sxs-lookup"><span data-stu-id="aef17-156">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="aef17-157">Lijsten met uitsluitingen valideren met het EICAR-testbestand</span><span class="sxs-lookup"><span data-stu-id="aef17-157">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="aef17-158">U kunt valideren dat uw uitsluitingslijsten werken met behulp `curl` van het downloaden van een testbestand.</span><span class="sxs-lookup"><span data-stu-id="aef17-158">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="aef17-159">Vervang in het volgende Bash-fragment `test.txt` door een bestand dat voldoet aan de uitsluitingsregels.</span><span class="sxs-lookup"><span data-stu-id="aef17-159">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="aef17-160">Als u bijvoorbeeld de extensie hebt uitgesloten, vervangt `.testing` u `test.txt` door `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="aef17-160">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="aef17-161">Als u een pad test, controleert u of u de opdracht binnen dat pad hebt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="aef17-161">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="aef17-162">Als Defender voor Eindpunt voor Linux malware rapporteert, werkt de regel niet.</span><span class="sxs-lookup"><span data-stu-id="aef17-162">If Defender for Endpoint for Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="aef17-163">Als er geen malwarerapport is en het gedownloade bestand bestaat, werkt de uitsluiting.</span><span class="sxs-lookup"><span data-stu-id="aef17-163">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="aef17-164">U kunt het bestand openen om te bevestigen dat de inhoud hetzelfde is als wat wordt beschreven op de website van het [EICAR-testbestand.](http://2016.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="aef17-164">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="aef17-165">Als u geen internetverbinding hebt, kunt u uw eigen EICAR-testbestand maken.</span><span class="sxs-lookup"><span data-stu-id="aef17-165">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="aef17-166">Schrijf de EICAR-tekenreeks naar een nieuw tekstbestand met de volgende opdracht Bash:</span><span class="sxs-lookup"><span data-stu-id="aef17-166">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="aef17-167">U kunt de tekenreeks ook kopiëren naar een leeg tekstbestand en proberen deze op te slaan met de bestandsnaam of in de map die u probeert uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="aef17-167">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="aef17-168">Bedreigingen toestaan</span><span class="sxs-lookup"><span data-stu-id="aef17-168">Allow threats</span></span>

<span data-ttu-id="aef17-169">Naast het uitsluiten van het scannen van bepaalde inhoud, kunt u het product ook zo configureren dat bepaalde categorieën bedreigingen niet worden gedetecteerd (geïdentificeerd met de naam van de bedreiging).</span><span class="sxs-lookup"><span data-stu-id="aef17-169">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="aef17-170">U moet voorzichtig zijn bij het gebruik van deze functionaliteit, omdat uw apparaat hierdoor niet wordt beveiligd.</span><span class="sxs-lookup"><span data-stu-id="aef17-170">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="aef17-171">Als u een bedreigingsnaam wilt toevoegen aan de toegestane lijst, voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="aef17-171">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="aef17-172">De bedreigingsnaam die is gekoppeld aan een detectie op uw apparaat, kunt u verkrijgen met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="aef17-172">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="aef17-173">Als u bijvoorbeeld (de bedreigingsnaam die is gekoppeld aan de EICAR-detectie) wilt toevoegen aan de toegestane lijst, voert u `EICAR-Test-File (not a virus)` de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="aef17-173">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
