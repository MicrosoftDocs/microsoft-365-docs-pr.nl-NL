---
title: PowerShell gebruiken om retentielabels te maken en publiceren
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
ms.date: ''
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informatie over het gebruik van PowerShell om retentielabels te maken en te publiceren vanuit de opdrachtregel, onafhankelijk van het Microsoft 365-compliancecentrum.
ms.openlocfilehash: 6dc008784d46567bfa76b5bbcf9b3fa6ee8155a1
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924961"
---
# <a name="create-and-publish-retention-labels-by-using-powershell"></a><span data-ttu-id="7dee0-103">PowerShell gebruiken om retentielabels te maken en publiceren</span><span class="sxs-lookup"><span data-stu-id="7dee0-103">Create and publish retention labels by using PowerShell</span></span>

><span data-ttu-id="7dee0-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="7dee0-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="7dee0-105">Wanneer u heeft besloten om [retentielabels](retention.md) te gebruiken om documenten en e-mailberichten in Microsoft 365 te bewaren of te verwijderen, weet u mogelijk dat u vele, mogelijk honderden, retentielabels moet aanmaken en publiceren.</span><span class="sxs-lookup"><span data-stu-id="7dee0-105">After you've decided to use [retention labels](retention.md) to help you keep or delete documents and emails in Microsoft 365, you might have realized that you have many and possibly hundreds of retention labels to create and publish.</span></span> <span data-ttu-id="7dee0-106">De aanbevolen methode om retentielabels op grote schaal aan te maken is door [bestandsplan](file-plan-manager.md) te gebruiken in het Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="7dee0-106">The recommended method to create retention labels at scale is by using [file plan](file-plan-manager.md) from the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7dee0-107">U kunt echter ook [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7dee0-107">However, you can also use [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels).</span></span>
  
<span data-ttu-id="7dee0-108">Gebruik de informatie, sjabloonbestanden en voorbeelden en het script in dit artikel om bulksgewijs retentielabels te maken en deze te publiceren in beleid voor retentielabels.</span><span class="sxs-lookup"><span data-stu-id="7dee0-108">Use the information, template files and examples, and script in this article to help you bulk-create retention labels and publish them in retention label policies.</span></span> <span data-ttu-id="7dee0-109">Vervolgens kunnen de retentielabels worden [ toegepast door beheerders en gebruikers](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="7dee0-109">Then, the retention labels can be [applied by administrators and users](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span></span>

<span data-ttu-id="7dee0-110">De opgegeven instructies bieden geen ondersteuning voor retentielabels die automatisch worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="7dee0-110">The supplied instructions don't support retention labels that are auto-applied.</span></span>

<span data-ttu-id="7dee0-111">Overzicht:</span><span class="sxs-lookup"><span data-stu-id="7dee0-111">Overview:</span></span> 

1. <span data-ttu-id="7dee0-112">Maak in Excel een lijst met uw retentielabels aan en een lijst met het hun beleidsregels voor retentielabels.</span><span class="sxs-lookup"><span data-stu-id="7dee0-112">In Excel, create a list of your retention labels and a list of their retention label policies.</span></span>

2. <span data-ttu-id="7dee0-113">Gebruik PowerShell om de retentielabels en het beleid voor retentielabels in die lijsten aan te maken.</span><span class="sxs-lookup"><span data-stu-id="7dee0-113">Use PowerShell to create the retention labels and retention label policies in those lists.</span></span>
  
## <a name="disclaimer"></a><span data-ttu-id="7dee0-114">Disclaimer</span><span class="sxs-lookup"><span data-stu-id="7dee0-114">Disclaimer</span></span>

<span data-ttu-id="7dee0-115">De voorbeeldscripts in dit artikel worden niet ondersteund door een standaardondersteuningsprogramma of -service van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7dee0-115">The sample scripts provided in this article aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="7dee0-116">De voorbeeldscripts worden zonder enige garantie ONGEWIJZIGD verstrekt.</span><span class="sxs-lookup"><span data-stu-id="7dee0-116">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="7dee0-117">Microsoft wijst alle impliciete garanties met inbegrip van, maar niet beperkt tot, impliciete garanties van verkoopbaarheid en geschiktheid voor een bepaald doel af.</span><span class="sxs-lookup"><span data-stu-id="7dee0-117">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="7dee0-118">Het risico dat ontstaat als gevolg van het gebruik of prestaties van de voorbeeldscripts ligt geheel bij u.</span><span class="sxs-lookup"><span data-stu-id="7dee0-118">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="7dee0-119">In geen geval kan Microsoft, haar auteurs of anderen die bij het maken, produceren of leveren van de scripts zijn betrokken, aansprakelijk worden gehouden voor enige schade om welke reden dan ook (met inbegrip van maar niet beperkt tot schade door verlies van bedrijfswinsten, belemmering van de bedrijfsuitvoering, verlies van bedrijfsinformatie of andere geldelijke verliezen) voortvloeiend uit het gebruik of de onmogelijkheid van het gebruik van de voorbeeldscripts, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.</span><span class="sxs-lookup"><span data-stu-id="7dee0-119">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-create-a-csv-file-for-the-retention-labels"></a><span data-ttu-id="7dee0-120">Stap 1: een .csv-bestand maken voor de retentielabels</span><span class="sxs-lookup"><span data-stu-id="7dee0-120">Step 1: Create a .csv file for the retention labels</span></span>

1. <span data-ttu-id="7dee0-121">Kopieer het volgende .csv-voorbeeldbestand voor een sjabloon en voorbeeldgegevens voor vier verschillende retentielabels en plak deze in Excel.</span><span class="sxs-lookup"><span data-stu-id="7dee0-121">Copy the following sample .csv file for a template and example entries for four different retention labels, and paste them into Excel.</span></span> 

2. <span data-ttu-id="7dee0-122">Converteer de tekst naar kolommen: tabblad **Gegevens** \> **Tekst naar kolommen** \> **Met scheidingstekens** \> **Komma** \> **Algemeen**</span><span class="sxs-lookup"><span data-stu-id="7dee0-122">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="7dee0-123">Vervang de voorbeelden door vermeldingen voor uw eigen retentielabels en instellingen.</span><span class="sxs-lookup"><span data-stu-id="7dee0-123">Replace the examples with entries for your own retention labels and settings.</span></span> <span data-ttu-id="7dee0-124">Zie [New-ComplianceTag](/powershell/module/exchange/new-compliancetag) voor meer informatie over de parameterwaarden.</span><span class="sxs-lookup"><span data-stu-id="7dee0-124">For more information about the parameter values, see [New-ComplianceTag](/powershell/module/exchange/new-compliancetag).</span></span>

3. <span data-ttu-id="7dee0-125">Sla het werkblad op als een .csv-bestand op een locatie die u gemakkelijk kunt vinden voor een latere stap.</span><span class="sxs-lookup"><span data-stu-id="7dee0-125">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="7dee0-126">Bijvoorbeeld: C:\>Scripts\Labels.csv</span><span class="sxs-lookup"><span data-stu-id="7dee0-126">For example: C:\>Scripts\Labels.csv</span></span>

  
<span data-ttu-id="7dee0-127">Opmerkingen:</span><span class="sxs-lookup"><span data-stu-id="7dee0-127">Notes:</span></span>

- <span data-ttu-id="7dee0-p106">Als het CSV-bestand een retentielabel bevat met dezelfde naam als een reeds bestaand label, wordt het maken van dat retentielabel door het script overgeslagen. Er worden geen duplicaat retentielabels gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7dee0-p106">If the .csv file contains a retention label with the same name as one that already exists, the script skips creating that retention label. No duplicate retention labels are created.</span></span>
    
- <span data-ttu-id="7dee0-130">Wijzig de kolomkoppen van het voorziene .csv-voorbeeldbestand niet of wijzig de naam niet, anders mislukt het script.</span><span class="sxs-lookup"><span data-stu-id="7dee0-130">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-labels"></a><span data-ttu-id="7dee0-131">Voorbeeld van een .csv-bestand voor retentielabels</span><span class="sxs-lookup"><span data-stu-id="7dee0-131">Sample .csv file for retention labels</span></span>

```
Name (Required),Comment (Optional),IsRecordLabel (Required),RetentionAction (Optional),RetentionDuration (Optional),RetentionType (Optional),ReviewerEmail (Optional)
LabelName_t_1,Record - keep and delete - 2 years,$true,KeepAndDelete,730,CreationAgeInDays,
LabelName_t_2,Keep and delete tag - 7 years,$false,KeepAndDelete,2555,ModificationAgeInDays,
LabelName_t_3,5 year delete,$false,Delete,1825,TaggedAgeInDays,
LabelName_t_4,Record label tag - financial,$true,Keep,730,CreationAgeInDays,
```

## <a name="step-2-create-a-csv-file-for-the-retention-label-policies"></a><span data-ttu-id="7dee0-132">Stap 2: een .csv-bestand maken voor het beleid voor retentielabels</span><span class="sxs-lookup"><span data-stu-id="7dee0-132">Step 2: Create a .csv file for the retention label policies</span></span>

1. <span data-ttu-id="7dee0-133">Kopieer het volgende .csv-voorbeeldbestand voor een sjabloon en voorbeeldgegevens voor drie verschillende beleidsregels voor retentielabels en plak deze in Excel.</span><span class="sxs-lookup"><span data-stu-id="7dee0-133">Copy the following sample .csv file for a template and example entries for three different retention label policies, and paste them into Excel.</span></span> 

2. <span data-ttu-id="7dee0-134">Converteer de tekst naar kolommen: tabblad **Gegevens** \> **Tekst naar kolommen** \> **Met scheidingstekens** \> **Komma** \> **Algemeen**</span><span class="sxs-lookup"><span data-stu-id="7dee0-134">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="7dee0-135">Vervang de voorbeelden door vermeldingen voor uw eigen beleid voor retentielabels en instellingen.</span><span class="sxs-lookup"><span data-stu-id="7dee0-135">Replace the examples with entries for your own retention label policies and their settings.</span></span> <span data-ttu-id="7dee0-136">Zie [Nieuw-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) voor meer informatie over de parameterwaarden voor deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7dee0-136">For more information about the parameter values for this cmdlet, see [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy).</span></span>

3. <span data-ttu-id="7dee0-137">Sla het werkblad op als een .csv-bestand op een locatie die u gemakkelijk kunt vinden voor een latere stap.</span><span class="sxs-lookup"><span data-stu-id="7dee0-137">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="7dee0-138">Bijvoorbeeld:`<path>Policies.csv`</span><span class="sxs-lookup"><span data-stu-id="7dee0-138">For example: `<path>Policies.csv`</span></span>


<span data-ttu-id="7dee0-139">Opmerkingen:</span><span class="sxs-lookup"><span data-stu-id="7dee0-139">Notes:</span></span>
  
- <span data-ttu-id="7dee0-p109">Als het CSV-bestand een retentielabelbeleid bevat met dezelfde naam als een reeds bestaand beleid, wordt het maken van dat retentielabelbeleid overgeslagen. Er worden geen duplicaat beleidsregels voor retentielabels gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7dee0-p109">If the .csv file contains a retention label policy with the same name as one that already exists, the script skips creating that retention label policy. No duplicate retention label policies are created.</span></span>
    
- <span data-ttu-id="7dee0-142">Wijzig de kolomkoppen van het voorziene .csv-voorbeeldbestand niet of wijzig de naam niet, anders mislukt het script.</span><span class="sxs-lookup"><span data-stu-id="7dee0-142">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-policies"></a><span data-ttu-id="7dee0-143">Voorbeeld van een .csv-bestand voor retentiebeleidsregels</span><span class="sxs-lookup"><span data-stu-id="7dee0-143">Sample .csv file for retention policies</span></span>

```
Policy Name (Required),PublishComplianceTag (Required),Comment (Optional),Enabled (Required),ExchangeLocation (Optional),ExchangeLocationException (Optional),ModernGroupLocation (Optional),ModernGroupLocationException (Optional),OneDriveLocation (Optional),OneDriveLocationException (Optional),PublicFolderLocation (Optional),SharePointLocation (Optional),SharePointLocationException (Optional),SkypeLocation (Optional),SkypeLocationException (Optional)
Publishing Policy Red1,"LabelName_t_1, LabelName_t_2, LabelName_t_3, LabelName_t_4",N/A,$true,All,,All,,All,,,All,,,
Publishing Policy Orange1,"LabelName_t_1, LabelName_t_2",N/A,$true,All,,,,,,,,,,
Publishing Policy Yellow1,"LabelName_t_3, LabelName_t_4",N/A,$false,All,,,,,,,,,,
```

## <a name="step-3-create-the-powershell-script"></a><span data-ttu-id="7dee0-144">Stap 3: het PowerShell-script aanmaken</span><span class="sxs-lookup"><span data-stu-id="7dee0-144">Step 3: Create the PowerShell script</span></span>

1. <span data-ttu-id="7dee0-145">Kopieer en plak het volgende PowerShell-script in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="7dee0-145">Copy and paste the following PowerShell script into Notepad.</span></span>

2. <span data-ttu-id="7dee0-146">Sla het bestand op met de bestandsextensie **.ps1** op een locatie die u gemakkelijk kunt terugvinden.</span><span class="sxs-lookup"><span data-stu-id="7dee0-146">Save the file by using a file name extension of **.ps1** in a location that's easy to find.</span></span> <span data-ttu-id="7dee0-147">Bijvoorbeeld:`<path>CreateRetentionSchedule.ps1`</span><span class="sxs-lookup"><span data-stu-id="7dee0-147">For example: `<path>CreateRetentionSchedule.ps1`</span></span>

<span data-ttu-id="7dee0-148">Opmerkingen:</span><span class="sxs-lookup"><span data-stu-id="7dee0-148">Notes:</span></span>

- <span data-ttu-id="7dee0-149">In het script wordt u gevraagd de twee bronbestanden op te geven die u in de vorige twee stappen hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="7dee0-149">The script prompts you to provide the two source files that you created in the previous two steps:</span></span>
    - <span data-ttu-id="7dee0-150">Als u het bronbestand niet opgeeft om de retentielabels te maken, gaat het script verder met het aanmaken van beleidsregels voor retentielabels.</span><span class="sxs-lookup"><span data-stu-id="7dee0-150">If you don't specify the source file to create the retention labels, the script moves on to create the retention label policies.</span></span> 
    - <span data-ttu-id="7dee0-151">Als u het bronbestand niet opgeeft om het beleid voor retentielabels te maken, gaat het script verder met het aanmaken van retentielabels.</span><span class="sxs-lookup"><span data-stu-id="7dee0-151">If you don't specify the source file to create the retention label policies, the script creates the retention labels only.</span></span>

- <span data-ttu-id="7dee0-152">Het script genereert een logboekbestand met de acties die worden ondernomen en of de actie is geslaagd of mislukt.</span><span class="sxs-lookup"><span data-stu-id="7dee0-152">The script generates a log file that records each action it took and whether the action succeeded or failed.</span></span> <span data-ttu-id="7dee0-153">Zie de laatste stap voor instructies om dit logboekbestand te vinden.</span><span class="sxs-lookup"><span data-stu-id="7dee0-153">See the final step for instructions how to locate this log file.</span></span>

### <a name="powershell-script"></a><span data-ttu-id="7dee0-154">PowerShell-script</span><span class="sxs-lookup"><span data-stu-id="7dee0-154">PowerShell script</span></span>

```Powershell
<#
. Steps: Import and publish retention labels
    ○ Load retention labels csv file 
    ○ Validate csv file input
    ○ Create retention labels
    ○ Create retention policies
    ○ Publish retention labels for the policies
    ○ Generate the log for retention labels and policies creation
    ○ Generate the csv result for the labels and policies created
. Syntax
    .\Publish-ComplianceTag.ps1 [-LabelListCSV <string>] [-PolicyListCSV <string>] 
. Detailed Description
    1) [-LabelListCSV <string>]
    -LabelListCSV ".\SampleInputFile_LabelList.csv"
    Load compliance tag for creation.
    2) [-PolicyListCSV <string>]
    -PolicyListCSV ".\SampleInputFile_PolicyList.csv"
    Load compliance tag for creation.
#>
param (
    [Parameter(Mandatory = $true)]
    [string]$LabelListCSV = "",
    [Parameter(Mandatory = $true)]
    [string]$PolicyListCSV = "",
    [Switch]$ResultCSV
)
# -------------------
# File operation
# -------------------
Function FileExist
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath,
        [Switch]$Warning
    )
    $inputFileExist = Test-Path $FilePath
    if (!$inputFileExist)
    {
        if ($Warning -eq $false) 
        { 
            WriteToLog -Type "Failed" -Message "[File: $FilePath] The file doesn't exist"
            throw 
        }
        else 
        { 
            WriteToLog -Type "Warning" -Message "[File: $FilePath] The file doesn't exist"
        }
    }
    else
    {
        WriteToLog -Type "Succeed" -Message "[File: $FilePath] The file is found"
    }
}
# -------------------
# Log operation
# -------------------
Function WriteToLog
{
    Param(
        # Message want to write to log file
        [Parameter(Mandatory = $true)]
        [String]$Message,
        # "Succeed" or "Faild"
        [String]$Type = "Message"
    )
    $date = Get-Date -Format 'HH:mm:ss'
    $logInfo = $date + " - [$Type] " + $Message
    $logInfo | Out-File -FilePath $logfilePath -Append
    if ($Type -eq "Succeed") { Write-Host $logInfo -ForegroundColor Green }
    elseif ($Type -eq "Failed") { Write-Host $logInfo -ForegroundColor Red }
    elseif ($Type -eq "Warning") { Write-Host $logInfo -ForegroundColor Yellow }
    elseif ($Type -eq "Start") { Write-Host $logInfo -ForegroundColor Cyan }
    else { Write-Verbose $logInfo }
}
Function Create-Log
{
    Param(
        # Log folder Root
        [Parameter(Mandatory = $true)]
        [String]$LogFolderRoot,
        # The function Log file for
        [Parameter(Mandatory = $true)]
        [String]$LogFunction
    )
    $logFolderPath = "$LogFolderRoot\logfiles"
    $folderExist = Test-Path "$logFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$logFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $logfilePath = "$logFolderPath\Log_{0}_{1}.txt" -f $LogFunction, $date
    Write-Verbose "Log file is written to: $logfilePath"
    $logfile = New-Item $logfilePath  -type file
    return $logfilePath
}
Function Create-ResultCSV
{
    Param(
        # Result folder Root
        [Parameter(Mandatory = $true)]
        [String]$ResultFolderRoot,
        # The function Result file for
        [Parameter(Mandatory = $true)]
        [String]$ResultFunction
    )
    $retFolderPath = "$ResultFolderRoot\logfiles"
    $folderExist = Test-Path "$retFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$retFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $retfilePath = "$retFolderPath\Result_{0}_{1}.csv" -f $ResultFunction, $date
    Write-Verbose "Result file is written to: $retfilePath"
    $retfile = New-Item $retfilePath  -type file
    return $retfilePath
}
# -------------------
# Prepare Log File
# -------------------
$scriptPath = '.\'
$logfilePath = Create-Log -LogFolderRoot $scriptPath -LogFunction "Publish_Compliance_Tag"
if ($ResultCSV)
{
    $tagRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Creation"
    $tagPubRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Publish"
}
# -------------------
# Invoke Powershell cmdlet
# -------------------
Function InvokePowerShellCmdlet
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$CmdLet
    )
    try
    {
        WriteToLog -Type "Start" -Message "Execute Cmdlet : '$CmdLet'" 
        return Invoke-Expression $CmdLet -ErrorAction SilentlyContinue
    }
    catch
    {
        WriteToLog -Type "Failed" "Failed to execute cmdlet!"
        WriteToLog -Type "Failed" $error[0]
        return $null
    }
}
# -------------------
# Create Compliance Tag
# -------------------
Function CreateComplianceTag
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to create Compliance Tag"
    FileExist $FilePath
    
    # TODO Validate CSV file for the Header
    try
    {
        # Import csv
        $labels = Import-Csv $FilePath
        # Retrieve existing compliance tags
        $tags = InvokePowerShellCmdlet "Get-ComplianceTag"
        foreach($lab in $labels)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $cmdlet = 'New-ComplianceTag'
            if ([String]::IsNullOrEmpty($lab.'Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $name = $lab.'Name (Required)'
                $cmdlet += " -Name '" + $name + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'Comment (Optional)'))
            {
                $para = $lab.'Comment (Optional)'
                $cmdlet += " -Comment '" + $para + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'IsRecordLabel (Required)'))
            {
                $para = $lab.'IsRecordLabel (Required)'
                $cmdlet += " -IsRecordLabel " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionAction (Optional)'))
            {
                $para = $lab.'RetentionAction (Optional)'
                $cmdlet += " -RetentionAction " + $para 
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionDuration (Optional)'))
            {
                $para = $lab.'RetentionDuration (Optional)'
                $cmdlet += " -RetentionDuration " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionType (Optional)'))
            {
                $para = $lab.'RetentionType (Optional)'
                $cmdlet += " -RetentionType " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'ReviewerEmail (Optional)'))
            {
                $emails = $lab.'ReviewerEmail (Optional)'.Split(",") | ForEach-Object { $_.Trim() }
                if (($emails -ne $null) -and ($emails.Count -ne 0))
                {
                    $eml = '@('
                    foreach($email in $emails)
                    {
                        $eml += "'{0}'," -f $email
                    }
                    $eml = $eml.Substring(0, $eml.Length - 1) + ')'
                    
                    $cmdlet += " -ReviewerEmail " + $eml
                }
            }
            # If the tag already exists, skip for creation
            if (($tags -eq $null) -or ($tags | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create compliance tag
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
                
                $ret = InvokePowerShellCmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The tag '$name' already exists! Skip for creation!"
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Create Retention Compliance Policy
# -------------------
Function CreateRetentionCompliancePolicy
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to Create Retention Policy"
    FileExist $FilePath
    try
    {
        # Import csv
        $list = Import-Csv -Path $FilePath
        # Retrieve existing retention compliance policy
        $policies = InvokePowerShellCmdlet "Get-RetentionCompliancePolicy"
        foreach($rp in $list)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $rpid = [String]::Empty;
            $cmdlet = 'New-RetentionCompliancePolicy'
            if ([String]::IsNullOrEmpty($rp.'Policy Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
               $name = $rp.'Policy Name (Required)'
               $cmdlet += " -Name '" + $name + "'"
            }
            if ([String]::IsNullOrEmpty($rp.'Enabled (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $enabled = $rp.'Enabled (Required)'
                $cmdlet += " -Enabled " + $enabled
            }
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocation (Optional)'))
            {
                $para = $rp.'ExchangeLocation (Optional)'
                $cmdlet += " -ExchangeLocation " + $para
            }
         
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocationException (Optional)'))
            {
                $para = $rp.'ExchangeLocationException (Optional)'
                $cmdlet += " -ExchangeLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocation (Optional)'))
            {
                $para = $rp.'ModernGroupLocation (Optional)'
                $cmdlet += " -ModernGroupLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocationException (Optional)'))
            {
                $para = $rp.'ModernGroupLocationException (Optional)'
                $cmdlet += " -ModernGroupLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocation (Optional)'))
            {
                $para = $rp.'OneDriveLocation (Optional)'
                $cmdlet += " -OneDriveLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocationException (Optional)'))
            {
                $para = $rp.'OneDriveLocationException (Optional)'
                $cmdlet += " -OneDriveLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocation (Optional)'))
            {
                $para = $rp.'SharePointLocation (Optional)'
                $cmdlet += " -SharePointLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocationException (Optional)'))
            {
                $para = $rp.'SharePointLocationException (Optional)'
                $cmdlet += " -SharePointLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'PublicFolderLocation (Optional)'))
            {
                $para = $rp.'PublicFolderLocation (Optional)'
                $cmdlet += " -PublicFolderLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocation (Optional)'))
            {
                $para = $rp.'SkypeLocation (Optional)'
                $cmdlet += " -SkypeLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocationException (Optional)'))
            {
                $para = $rp.'SkypeLocationException (Optional)'
                $cmdlet += " -SkypeLocationException " + $para
            }
            # If the policy already exists, skip for creation
            if (($policies -eq $null) -or ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create retention compliance policy
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
            
                $ret = invokepowershellcmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
                $rpid = $ret.Guid
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The policy '$name' already exists! Skip for creation!"
                $rpid = ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }).Guid
            }
                        
            # Retrieve tag name for publishing
            $ts = $rp.'PublishComplianceTag (Required)'
            $tagList = $ts.Split(",") | ForEach-Object { $_.Trim() }
            
            WriteToLog -Type "Message" -Message "Publish Tags : '$ts'" 
            
            PublishComplianceTag -PolicyGuid $rpid -TagName $tagList
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Publish Compliance Tag
# -------------------
Function PublishComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$PolicyGuid,
        [Parameter(Mandatory = $true)]
        [String[]]$TagNames
    )
    
    WriteToLog -Type "Start" "Start to Publish Compliance Tag"
    try
    {
        # Retrieve existing rule related to the given compliance policy
        $rule = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $PolicyGuid)
        $tagGuids = New-Object System.Collections.ArrayList
        
        foreach ($tn in $TagNames)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag {0}" -f $tn)
            $tagGuids.Add($t.Guid) | Out-Null
        }
        if ($rule -ne $null)
        {
            foreach ($r in $rule)
            {
                if ([String]::IsNullOrEmpty($r.PublishComplianceTag))
                {
                    continue;
                }
                else
                {
                    $tl = $r.PublishComplianceTag.Split(",")
                    if ($tagGuids.Contains([GUID]$tl[0]))
                    {
                        $tagGuids.Remove([GUID]$tl[0]);
                    }
                }
            }
        }
        
        foreach($t in $tagGuids)
        {
            # Publish compliance tag
            $cmdlet = "New-RetentionComplianceRule -Policy {0} -PublishComplianceTag {1}" -f $PolicyGuid, $t
            $ret = InvokePowerShellCmdlet $cmdlet
            
            if ($ret -eq $null)
            {
                WriteToLog -Type "Failed" $error[0]
                break;
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Export All Labels Created in The Process
# -------------------
Function ExportCreatedComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$LabelFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Compliance Tag Created"
    try
    {
        # Import input csv
        $labels = Import-Csv $LabelFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn Name,([string])
        $col2 = New-Object system.Data.DataColumn Comment,([string])
        $col3 = New-Object system.Data.DataColumn IsRecordLabel,([string])
        $col4 = New-Object system.Data.DataColumn RetentionAction,([string])
        $col5 = New-Object system.Data.DataColumn RetentionDuration,([string])
        $col6 = New-Object system.Data.DataColumn RetentionType,([string])
        $col7 = New-Object system.Data.DataColumn ReviewerEmail,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        foreach($lab in $labels)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag '{0}' " -f $lab.'Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Name'] = $t.Name
            $row['Comment'] = $t.Comment
            $row['IsRecordLabel'] = $t.IsRecordLabel
            $row['RetentionAction'] = $t.RetentionAction
            $row['RetentionDuration'] = $t.RetentionDuration
            $row['RetentionType'] = $t.RetentionType
            $row['ReviewerEmail'] = $t.ReviewerEmail
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# -------------------
# Export All Published Labels and Policies in The Process
# -------------------
Function ExportPublishedComplianceTagAndPolicy
{
    Param(
        [Parameter(Mandatory = $true)]
        [String[]]$PolicyFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Published Compliance Tag and Policy"
    try
    {
        # Import input csv
        $policies = Import-Csv $PolicyFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn 'Policy Name',([string])
        $col2 = New-Object system.Data.DataColumn PublishComplianceTag,([string])
        $col3 = New-Object system.Data.DataColumn Comment,([string])
        $col4 = New-Object system.Data.DataColumn Enabled,([string])
        $col5 = New-Object system.Data.DataColumn ExchangeLocation,([string])
        $col6 = New-Object system.Data.DataColumn ExchangeLocationException,([string])
        $col7 = New-Object system.Data.DataColumn ModernGroupLocation,([string])
        $col8 = New-Object system.Data.DataColumn ModernGroupLocationException,([string])
        $col9 = New-Object system.Data.DataColumn OneDriveLocation,([string])
        $col10 = New-Object system.Data.DataColumn OneDriveLocationException,([string])
        $col11 = New-Object system.Data.DataColumn PublicFolderLocation,([string])
        $col12 = New-Object system.Data.DataColumn SharePointLocation,([string])
        $col13 = New-Object system.Data.DataColumn SharePointLocationException,([string])
        $col14 = New-Object system.Data.DataColumn SkypeLocation,([string])
        $col15 = New-Object system.Data.DataColumn SkypeLocationException,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        $table.columns.add($col8)
        $table.columns.add($col9)
        $table.columns.add($col10)
        $table.columns.add($col11)
        $table.columns.add($col12)
        $table.columns.add($col13)
        $table.columns.add($col14)
        $table.columns.add($col15)
        foreach($policy in $policies)
        {
            $t = InvokePowerShellCmdlet ("Get-RetentionCompliancePolicy '{0}' -DistributionDetail" -f $policy.'Policy Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Policy Name'] = $t.Name
            
            $rules = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $t.Guid)
            $tagList = [String]::Empty
            foreach($rule in $rules)
            {
                if ([String]::IsNullOrEmpty($rule.PublishComplianceTag) -eq $False)
                {
                    $tName = $rule.PublishComplianceTag.Split(',')[1]
                    $tagList = [String]::Concat($tagList, $tName, ",")
                }
            }
            if (![String]::IsNullOrEmpty($tagList))
            {
                $tagList = $tagList.Substring(0, $tagList.LastIndexOf(','))
            }
            $row['PublishComplianceTag'] = $tagList
            $row['Comment'] = $t.Comment
            $row['Enabled'] = $t.Enabled
            $row['ExchangeLocation'] = $t.ExchangeLocation
            $row['ExchangeLocationException'] = $t.ExchangeLocationException
            $row['ModernGroupLocation'] = $t.ModernGroupLocation
            $row['ModernGroupLocationException'] = $t.ModernGroupLocationException
            $row['OneDriveLocation'] = $t.OneDriveLocation
            $row['OneDriveLocationException'] = $t.OneDriveLocationException
            $row['PublicFolderLocation'] = $t.PublicFolderLocation
            $row['SharePointLocation'] = $t.SharePointLocation
            $row['SharePointLocationException'] = $t.SharePointLocationException
            $row['SkypeLocation'] = $t.SkypeLocation
            $row['SkypeLocationException'] = $t.SkypeLocationException
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagPubRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# Create compliance tag
CreateComplianceTag -FilePath $LabelListCSV
# Create retention policy and publish compliance tag with the policy
CreateRetentionCompliancePolicy -FilePath $PolicyListCSV
# Export to result csv
if ($ResultCSV)
{
    ExportCreatedComplianceTag -LabelFilePath $LabelListCSV
    ExportPublishedComplianceTagAndPolicy -PolicyFilePath $PolicyListCSV 
}

```

## <a name="step-4-run-the-powershell-script"></a><span data-ttu-id="7dee0-155">Stap 4: het PowerShell-script uitvoeren</span><span class="sxs-lookup"><span data-stu-id="7dee0-155">Step 4: Run the PowerShell script</span></span>

<span data-ttu-id="7dee0-156">Maak als eerste [verbinding met PowerShell van het beveiligings- en compliancecentrum](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="7dee0-156">First, [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="7dee0-157">Voer vervolgens het script uit waardoor de retentielabels worden gemaakt en gepubliceerd:</span><span class="sxs-lookup"><span data-stu-id="7dee0-157">Then, run the script that creates and publishes the retention labels:</span></span>
  
1. <span data-ttu-id="7dee0-158">Voer in de PowerShell-sessie van het Beveiligings- en compliancecentrum het pad in, gevolgd door de tekens `.\` en de bestandsnaam van het script, en druk vervolgens op ENTER om het script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="7dee0-158">In your Security & Compliance Center PowerShell session, enter the path, followed by the characters `.\` and the file name of the script, and then press ENTER to run the script.</span></span> <span data-ttu-id="7dee0-159">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="7dee0-159">For example:</span></span>
    
    ```powershell
    <path>.\CreateRetentionSchedule.ps1
    ```

2. <span data-ttu-id="7dee0-160">In het script wordt u gevraagd om de locatie van de .csv-bestanden die u in de vorige twee stappen hebt gemaakt op te geven.</span><span class="sxs-lookup"><span data-stu-id="7dee0-160">The script prompts you for the locations of the .csv files that you created in the previous steps.</span></span> <span data-ttu-id="7dee0-161">Voer het pad in, gevolgd door de tekens `.\` en de bestandsnaam van het .csv-bestand, en druk op ENTER.</span><span class="sxs-lookup"><span data-stu-id="7dee0-161">Enter the path, followed by the characters `.\` and file name of the .csv file, and then press ENTER.</span></span> <span data-ttu-id="7dee0-162">Bijvoorbeeld bij de eerste prompt:</span><span class="sxs-lookup"><span data-stu-id="7dee0-162">For example, for the first prompt:</span></span>
    
    ```powershell
    <path>.\Labels.csv
    ```

## <a name="step-5-view-the-log-file-with-the-results"></a><span data-ttu-id="7dee0-163">Stap 5: het logboekbestand met de resultaten weergeven</span><span class="sxs-lookup"><span data-stu-id="7dee0-163">Step 5: View the log file with the results</span></span>

<span data-ttu-id="7dee0-164">Gebruik het logboekbestand dat het script heeft gemaakt om de resultaten te controleren en na te gaan of er fouten zijn die moeten worden opgelost.</span><span class="sxs-lookup"><span data-stu-id="7dee0-164">Use the log file that the script created to check the results and identify any failures that need resolving.</span></span>

<span data-ttu-id="7dee0-165">U vindt het logboekbestand op de volgende locatie, hoewel de cijfers in de voorbeeldbestandsnaam afwijken.</span><span class="sxs-lookup"><span data-stu-id="7dee0-165">You can find the log file at the following location, although the digits in the example file name vary.</span></span>
  
```
<path>.\Log_Publish_Compliance_Tag_01112018_151239.txt
```