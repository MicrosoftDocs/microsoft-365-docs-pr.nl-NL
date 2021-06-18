---
title: Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt op Linux
description: Uitsluitingen opgeven en valideren voor Microsoft Defender voor Eindpunt op Linux. Uitsluitingen kunnen worden ingesteld voor bestanden, mappen en processen.
keywords: microsoft, defender, Microsoft Defender voor Eindpunt, linux, uitsluitingen, scans, antivirus
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
ms.openlocfilehash: bd506caa041af2585778fb3ecd7a40562463b17e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346412"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c05dd-105">Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="c05dd-105">Configure and validate exclusions for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c05dd-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c05dd-106">**Applies to:**</span></span>

- [<span data-ttu-id="c05dd-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c05dd-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c05dd-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c05dd-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c05dd-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c05dd-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c05dd-110">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="c05dd-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="c05dd-111">Dit artikel bevat informatie over het definiëren van uitsluitingen die van toepassing zijn op scans op aanvraag en realtime beveiliging en bewaking.</span><span class="sxs-lookup"><span data-stu-id="c05dd-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c05dd-112">De uitsluitingen die in dit artikel worden beschreven, zijn niet van toepassing op andere mogelijkheden van Defender voor Eindpunt op Linux, waaronder eindpuntdetectie en -respons (EDR).</span><span class="sxs-lookup"><span data-stu-id="c05dd-112">The exclusions described in this article don't apply to other Defender for Endpoint on Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="c05dd-113">Bestanden die u uitsluit met behulp van de methoden die in dit artikel worden beschreven, kunnen nog steeds EDR-waarschuwingen en andere detecties activeren.</span><span class="sxs-lookup"><span data-stu-id="c05dd-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="c05dd-114">U kunt bepaalde bestanden, mappen, processen en door processen geopende bestanden uitsluiten van Defender voor Eindpunt op Linux-scans.</span><span class="sxs-lookup"><span data-stu-id="c05dd-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint on Linux scans.</span></span>

<span data-ttu-id="c05dd-115">Uitsluitingen kunnen handig zijn om onjuiste detecties te voorkomen voor bestanden of software die uniek zijn of zijn aangepast aan uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c05dd-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="c05dd-116">Ze kunnen ook nuttig zijn voor het beperken van prestatieproblemen die worden veroorzaakt door Defender voor Eindpunt op Linux.</span><span class="sxs-lookup"><span data-stu-id="c05dd-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint on Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="c05dd-117">Als u uitsluitingen definieert, wordt de beveiliging verlaagd die wordt geboden door Defender voor Eindpunt op Linux.</span><span class="sxs-lookup"><span data-stu-id="c05dd-117">Defining exclusions lowers the protection offered by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="c05dd-118">U moet altijd de risico's evalueren die zijn gekoppeld aan het implementeren van uitsluitingen en u moet alleen bestanden uitsluiten waarvan u zeker weet dat ze niet schadelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="c05dd-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="c05dd-119">Ondersteunde uitsluitingstypen</span><span class="sxs-lookup"><span data-stu-id="c05dd-119">Supported exclusion types</span></span>

<span data-ttu-id="c05dd-120">In de volgende tabel ziet u de uitsluitingstypen die worden ondersteund door Defender voor Eindpunt op Linux.</span><span class="sxs-lookup"><span data-stu-id="c05dd-120">The follow table shows the exclusion types supported by Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="c05dd-121">Uitsluiting</span><span class="sxs-lookup"><span data-stu-id="c05dd-121">Exclusion</span></span> | <span data-ttu-id="c05dd-122">Definitie</span><span class="sxs-lookup"><span data-stu-id="c05dd-122">Definition</span></span> | <span data-ttu-id="c05dd-123">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="c05dd-123">Examples</span></span>
---|---|---
<span data-ttu-id="c05dd-124">Bestandsextensie</span><span class="sxs-lookup"><span data-stu-id="c05dd-124">File extension</span></span> | <span data-ttu-id="c05dd-125">Alle bestanden met de extensie, waar dan ook op het apparaat</span><span class="sxs-lookup"><span data-stu-id="c05dd-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="c05dd-126">Bestand</span><span class="sxs-lookup"><span data-stu-id="c05dd-126">File</span></span> | <span data-ttu-id="c05dd-127">Een specifiek bestand dat wordt geïdentificeerd door het volledige pad</span><span class="sxs-lookup"><span data-stu-id="c05dd-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="c05dd-128">Map</span><span class="sxs-lookup"><span data-stu-id="c05dd-128">Folder</span></span> | <span data-ttu-id="c05dd-129">Alle bestanden in de opgegeven map (recursief)</span><span class="sxs-lookup"><span data-stu-id="c05dd-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="c05dd-130">Proces</span><span class="sxs-lookup"><span data-stu-id="c05dd-130">Process</span></span> | <span data-ttu-id="c05dd-131">Een specifiek proces (opgegeven door het volledige pad of de bestandsnaam) en alle bestanden die door het proces zijn geopend</span><span class="sxs-lookup"><span data-stu-id="c05dd-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="c05dd-132">De bovenstaande paden moeten harde koppelingen zijn, geen symbolische koppelingen, om met succes te kunnen worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="c05dd-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="c05dd-133">U kunt controleren of een pad een symbolische koppeling is door `file <path-name>` uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="c05dd-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="c05dd-134">Uitsluitingen van bestanden, mappen en processen ondersteunen de volgende jokertekens:</span><span class="sxs-lookup"><span data-stu-id="c05dd-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="c05dd-135">Jokerteken</span><span class="sxs-lookup"><span data-stu-id="c05dd-135">Wildcard</span></span> | <span data-ttu-id="c05dd-136">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c05dd-136">Description</span></span> | <span data-ttu-id="c05dd-137">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="c05dd-137">Example</span></span> | <span data-ttu-id="c05dd-138">Overeenkomsten</span><span class="sxs-lookup"><span data-stu-id="c05dd-138">Matches</span></span> | <span data-ttu-id="c05dd-139">Komt niet overeen</span><span class="sxs-lookup"><span data-stu-id="c05dd-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="c05dd-140">Komt overeen met een willekeurig aantal tekens, inclusief geen (houd er rekening mee dat wanneer dit jokerteken binnen een pad wordt gebruikt, slechts één map wordt vervangen)</span><span class="sxs-lookup"><span data-stu-id="c05dd-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="c05dd-141">?</span><span class="sxs-lookup"><span data-stu-id="c05dd-141">?</span></span> | <span data-ttu-id="c05dd-142">Komt overeen met een enkel teken</span><span class="sxs-lookup"><span data-stu-id="c05dd-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="c05dd-143">De lijst met uitsluitingen configureren</span><span class="sxs-lookup"><span data-stu-id="c05dd-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="c05dd-144">Vanuit de beheerconsole</span><span class="sxs-lookup"><span data-stu-id="c05dd-144">From the management console</span></span>

<span data-ttu-id="c05dd-145">Zie [Voorkeuren instellen voor Defender voor Eindpunt op Linux](linux-preferences.md)voor meer informatie over het configureren van uitsluitingen van Puppet, Ansible of een andere beheerconsole.</span><span class="sxs-lookup"><span data-stu-id="c05dd-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="c05dd-146">Vanaf de opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="c05dd-146">From the command line</span></span>

<span data-ttu-id="c05dd-147">Voer de volgende opdracht uit om de beschikbare opties voor het beheren van uitsluitingen weer te geven:</span><span class="sxs-lookup"><span data-stu-id="c05dd-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="c05dd-148">Bij het configureren van uitsluitingen met jokertekens plaatst u de parameter tussen dubbele aanhalingstekens om globbing te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="c05dd-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="c05dd-149">Voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="c05dd-149">Examples:</span></span>

- <span data-ttu-id="c05dd-150">Een uitsluiting toevoegen voor een bestandsextensie:</span><span class="sxs-lookup"><span data-stu-id="c05dd-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="c05dd-151">Een uitsluiting toevoegen voor een bestand:</span><span class="sxs-lookup"><span data-stu-id="c05dd-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="c05dd-152">Een uitsluiting toevoegen voor een map:</span><span class="sxs-lookup"><span data-stu-id="c05dd-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="c05dd-153">Voeg een uitsluiting toe voor een map met een jokerteken:</span><span class="sxs-lookup"><span data-stu-id="c05dd-153">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="c05dd-154">Hiermee worden paden slechts één niveau onder */var/* uitgesloten, maar geen mappen die dieper zijn genest; bijvoorbeeld */var/this-submap/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="c05dd-154">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="c05dd-155">Hiermee worden alle paden uitgesloten waarvan het bovenliggende element */var/*; is. bijvoorbeeld */var/this-submap/and-this-subfolder-as-well*.</span><span class="sxs-lookup"><span data-stu-id="c05dd-155">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="c05dd-156">Een uitsluiting toevoegen voor een proces:</span><span class="sxs-lookup"><span data-stu-id="c05dd-156">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="c05dd-157">Uitsluitingslijsten valideren met het EICAR-testbestand</span><span class="sxs-lookup"><span data-stu-id="c05dd-157">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="c05dd-158">U kunt controleren of uw uitsluitingslijsten werken met behulp van `curl` en een testbestand te downloaden.</span><span class="sxs-lookup"><span data-stu-id="c05dd-158">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="c05dd-159">Vervang vervolgens het Bash-fragment `test.txt` door een bestand dat voldoet aan uw uitsluitingsregels.</span><span class="sxs-lookup"><span data-stu-id="c05dd-159">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="c05dd-160">Als u bijvoorbeeld de `.testing`-extensie hebt uitgesloten, vervangt u `test.txt` door `test.testing`.</span><span class="sxs-lookup"><span data-stu-id="c05dd-160">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="c05dd-161">Als u een pad test, moet u ervoor zorgen dat u de opdracht binnen dat pad uitvoert.</span><span class="sxs-lookup"><span data-stu-id="c05dd-161">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="c05dd-162">Als Defender voor Eindpunt op Linux malware rapporteert, werkt de regel niet.</span><span class="sxs-lookup"><span data-stu-id="c05dd-162">If Defender for Endpoint on Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="c05dd-163">Als er geen malware wordt gerapporteerd en het gedownloade bestand bestaat, werkt de uitsluiting.</span><span class="sxs-lookup"><span data-stu-id="c05dd-163">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="c05dd-164">U kunt het bestand openen om te bevestigen dat de inhoud hetzelfde is als wat wordt beschreven op de [EICAR-testbestandswebsite](http://2016.eicar.org/86-0-Intended-use.html).</span><span class="sxs-lookup"><span data-stu-id="c05dd-164">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="c05dd-165">Als u geen internettoegang hebt, kunt u uw eigen EICAR-testbestand maken.</span><span class="sxs-lookup"><span data-stu-id="c05dd-165">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="c05dd-166">Schrijf de EICAR-tekenreeks naar een nieuw tekstbestand met de volgende Bash-opdracht:</span><span class="sxs-lookup"><span data-stu-id="c05dd-166">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="c05dd-167">U kunt de tekenreeks ook kopiëren naar een leeg tekstbestand en proberen deze op te slaan met de bestandsnaam of in de map die u probeert uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="c05dd-167">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="c05dd-168">Bedreigingen toestaan</span><span class="sxs-lookup"><span data-stu-id="c05dd-168">Allow threats</span></span>

<span data-ttu-id="c05dd-169">Naast het uitsluiten dat bepaalde inhoud wordt gescand, kunt u het product ook zo configureren dat bepaalde klassen bedreigingen niet worden gedetecteerd (geïdentificeerd door de bedreigingsnaam).</span><span class="sxs-lookup"><span data-stu-id="c05dd-169">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="c05dd-170">Wees voorzichtig bij het gebruik van deze functionaliteit, omdat uw apparaat hierdoor onbeveiligd kan raken.</span><span class="sxs-lookup"><span data-stu-id="c05dd-170">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="c05dd-171">Voer de volgende opdracht uit om een bedreigingsnaam toe te voegen aan de lijst met toegestane bedreigingen:</span><span class="sxs-lookup"><span data-stu-id="c05dd-171">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="c05dd-172">De bedreigingsnaam die is gekoppeld aan een detectie op uw apparaat, kan worden verkregen met behulp van de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="c05dd-172">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="c05dd-173">Als u bijvoorbeeld `EICAR-Test-File (not a virus)` (de bedreigingsnaam die is gekoppeld aan de EICAR-detectie) wilt toevoegen aan de lijst met toegestane bedreigingen, voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="c05dd-173">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
