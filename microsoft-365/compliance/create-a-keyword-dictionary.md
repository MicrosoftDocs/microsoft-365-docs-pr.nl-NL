---
title: Een woordenlijst met trefwoorden maken
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informatie over de basisstappen voor het maken van een trefwoordenlijst in het Office 365-beveiligings- en compliancecentrum.
ms.openlocfilehash: 1e1aa45c3bf4d31e4c969b0bc0949109fa716467
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841160"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="a003c-103">Een woordenlijst met trefwoorden maken</span><span class="sxs-lookup"><span data-stu-id="a003c-103">Create a keyword dictionary</span></span>

<span data-ttu-id="a003c-104">Preventie van gegevensverlies (DLP) kan uw vertrouwelijke items identificeren, controleren en beveiligen.</span><span class="sxs-lookup"><span data-stu-id="a003c-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="a003c-105">Soms moet er worden gezocht naar trefwoorden om gevoelige items te identificeren, met name bij het identificeren van algemene inhoud (zoals communicatie in verband met gezondheidszorg) of ongepaste taal of expliciete taal.</span><span class="sxs-lookup"><span data-stu-id="a003c-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="a003c-106">Hoewel u trefwoordlijsten in typen vertrouwelijke informatie kunt maken, zijn trefwoordlijsten beperkt in grootte en moet XML worden gewijzigd om ze te maken of te bewerken.</span><span class="sxs-lookup"><span data-stu-id="a003c-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="a003c-107">Trefwoordenlijsten bieden een eenvoudiger beheer van trefwoorden en op een veel grotere schaal. Ze ondersteunen maximaal 1 MB aan termen (na compressie) in de woordenlijst en ondersteunen elke taal.</span><span class="sxs-lookup"><span data-stu-id="a003c-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="a003c-108">De tenantlimiet is ook 1 MB na compressie.</span><span class="sxs-lookup"><span data-stu-id="a003c-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="a003c-109">De limiet van 1 MB voor de compressie na de compressie betekent dat alle woordenlijsten voor een tenant bijna 1 miljoen tekens kunnen hebben.</span><span class="sxs-lookup"><span data-stu-id="a003c-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="a003c-110">Limieten trefwoordenlijst</span><span class="sxs-lookup"><span data-stu-id="a003c-110">Keyword dictionary limits</span></span>

<span data-ttu-id="a003c-111">Er geldt een limiet van 50 vertrouwelijke informatietypen op basis van trefwoordlijsten die per tenant kunnen worden aangemaakt.</span><span class="sxs-lookup"><span data-stu-id="a003c-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="a003c-112">Als u wilt weten hoeveel woordenlijsten u in uw tenant hebt, maakt u verbinding via de procedures in [Verbinding maken het Beveiligings- en compliancecentrum in PowerShell](/powershell/exchange/connect-to-scc-powershell) om verbinding te maken met uw tenant en dit PowerShell-script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a003c-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="a003c-113">Basisstappen voor het maken van een trefwoordenlijst</span><span class="sxs-lookup"><span data-stu-id="a003c-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="a003c-p103">De trefwoorden voor uw woordenlijst kunnen afkomstig zijn uit verschillende bronnen, meestal uit een bestand (zoals een .csv- of .txt-lijst) dat in de service of door een PowerShell-cmdlet is geïmporteerd, uit een lijst die u rechtstreeks in de PowerShell-cmdlet of uit een bestaande woordenlijst invoert. Wanneer u een trefwoordenlijst maakt, volgt u dezelfde stappen:</span><span class="sxs-lookup"><span data-stu-id="a003c-p103">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="a003c-116">Gebruik het ,**Beveiligings- en compliancecentrum** ([https://protection.office.com](https://protection.office.com)) of maak verbinding met **Beveiligings- &amp; compliancecentrum PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a003c-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="a003c-117">**Definieer of voer uw trefwoorden in vanuit uw bedoelde bron**.</span><span class="sxs-lookup"><span data-stu-id="a003c-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="a003c-118">De wizard en de cmdlet aanvaarden beide een door komma's gescheiden lijst met trefwoorden om een aangepaste woordenlijst voor trefwoorden te creëren. Deze stap varieert dus enigszins, afhankelijk van waar uw trefwoorden vandaan komen.</span><span class="sxs-lookup"><span data-stu-id="a003c-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="a003c-119">Nadat ze zijn geladen, worden ze versleuteld en geconverteerd naar een byte-matrix voordat ze worden geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="a003c-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="a003c-120">**Uw woordenlijst maken**</span><span class="sxs-lookup"><span data-stu-id="a003c-120">**Create your dictionary**.</span></span> <span data-ttu-id="a003c-121">Kies een naam en beschrijving en maak uw woordenlijst aan.</span><span class="sxs-lookup"><span data-stu-id="a003c-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="a003c-122">Een refwoordenlijst maken met het Beveiligings- en compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="a003c-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="a003c-123">Gebruik de volgende stappen om trefwoorden te maken en te importeren voor een aangepaste woordenlijst:</span><span class="sxs-lookup"><span data-stu-id="a003c-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="a003c-124">Verbinding maken met het Beveiligings- en compliancecentrum ([https://protection.office.com](https://protection.office.com))</span><span class="sxs-lookup"><span data-stu-id="a003c-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="a003c-125">Ga naar **Classificaties > vertrouwelijke informatietypen**.</span><span class="sxs-lookup"><span data-stu-id="a003c-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="a003c-126">Selecteer **Maken** en voer een **Naam** en **Beschrijving** in voor het vertrouwelijke gegevenstype,  en selecteer vervolgens **Volgende**</span><span class="sxs-lookup"><span data-stu-id="a003c-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="a003c-127">Selecteer **Een element toevoegen** en selecteer vervolgens **Woordenlijst (grote trefwoorden)** in de vervolgkeuzelijst **Inhoud detecteren met**.</span><span class="sxs-lookup"><span data-stu-id="a003c-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="a003c-128">Selecteer **een woordenlijst toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a003c-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="a003c-129">Selecteer onder het besturingselement Zoeken **U kunt hier nieuwe woordenlijsten voor trefwoorden aanmaken**.</span><span class="sxs-lookup"><span data-stu-id="a003c-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="a003c-130">Voer een **Naam** voor de aangepaste woordenlijst in.</span><span class="sxs-lookup"><span data-stu-id="a003c-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="a003c-131">Selecteer **Importeren** en selecteer **Uit tekst** of **Uit een .csv-bestand** afhankelijk van het type trefwoordbestand.</span><span class="sxs-lookup"><span data-stu-id="a003c-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="a003c-132">Selecteer in het dialoogvenster het trefwoordbestand van uw lokale pc of netwerkbestandsshare en selecteer vervolgens **Openen**.</span><span class="sxs-lookup"><span data-stu-id="a003c-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="a003c-133">Selecteer **Opslaan** en selecteer vervolgens uw aangepaste woordenlijst in de lijst met **Trefwoordlijsten**.</span><span class="sxs-lookup"><span data-stu-id="a003c-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="a003c-134">Selecteer **Toevoegen** en vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a003c-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="a003c-135">Controleer de selecties van vertrouwelijke gegevenstype en rond deze af en selecteer **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="a003c-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="a003c-136">Een trefwoordwoordenlijst maken vanuit een bestand met PowerShell</span><span class="sxs-lookup"><span data-stu-id="a003c-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="a003c-137">Wanneer u een grote woordenlijst moet maken, is het vaak nodig om trefwoorden te gebruiken uit een bestand of een lijst die is geëxporteerd vanuit een andere bron.</span><span class="sxs-lookup"><span data-stu-id="a003c-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="a003c-138">In dit geval maakt u een trefwoordwoordenlijst met een lijst met ongepaste taal die u uit externe e-mail kunt weren.</span><span class="sxs-lookup"><span data-stu-id="a003c-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="a003c-139">U maakt als eerste [Verbinding met PowerShell van het Beveiligings-&amp; en compliancecentrum](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="a003c-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="a003c-140">Kopieer de trefwoorden naar een tekstbestand en zorg ervoor dat elk trefwoord op een aparte regel staat.</span><span class="sxs-lookup"><span data-stu-id="a003c-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="a003c-141">Sla het tekstbestand op met Unicode-codering.</span><span class="sxs-lookup"><span data-stu-id="a003c-141">Save the text file with Unicode encoding.</span></span> <span data-ttu-id="a003c-142">Selecteer in Kladblok \> **Opslaan als** \> **Codering** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="a003c-142">In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="a003c-143">Lees het bestand in een variabele door deze cmdlet uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="a003c-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="a003c-144">Maak de woordenlijst door deze cmdlet uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="a003c-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="a003c-145">Trefwoordenlijsten gebruiken in aangepaste typen vertrouwelijke informatie en DLP-beleidsregels</span><span class="sxs-lookup"><span data-stu-id="a003c-145">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="a003c-146">Trefwoordenlijsten kunnen worden gebruikt als onderdeel van de vereisten voor overeenkomende gegevens voor een aangepast type vertrouwelijke informatie, of zelf als een type gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="a003c-146">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="a003c-147">Voor beide moet een [aangepast type gevoelige informatie worden gemaakt](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a003c-147">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="a003c-148">Volg de instructies in het gekoppelde artikel om een type gevoelige informatie te maken.</span><span class="sxs-lookup"><span data-stu-id="a003c-148">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="a003c-149">Wanneer u de XML hebt, hebt u de GUID-id voor de woordenlijst nodig om deze te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a003c-149">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="a003c-150">Voer deze opdracht uit om de identiteit van uw woordenlijst op te halen en de waarde van de eigenschap **id** te kopiëren:</span><span class="sxs-lookup"><span data-stu-id="a003c-150">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="a003c-151">De uitvoer van de opdracht ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="a003c-151">The output of the command looks like this:</span></span>
  
<span data-ttu-id="a003c-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="a003c-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="a003c-p109">U plak de identiteit in uw aangepast type gevoelige informatie-XML en u upload deze. De woordenlijst wordt nu weergegeven in uw lijst met typen gevoelige informatie en u kunt deze onmiddellijk in uw beleid gebruiken, waarin u opgeeft hoeveel trefwoorden moeten overeenkomen.</span><span class="sxs-lookup"><span data-stu-id="a003c-p109">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```

> [!NOTE]
> <span data-ttu-id="a003c-155">Microsoft 365 Information Protection ondersteunt talen voor preview van dubbel-byte-tekensets voor:</span><span class="sxs-lookup"><span data-stu-id="a003c-155">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="a003c-156">Vereenvoudigd Chinees</span><span class="sxs-lookup"><span data-stu-id="a003c-156">Chinese (simplified)</span></span>
> - <span data-ttu-id="a003c-157">Traditioneel Chinees</span><span class="sxs-lookup"><span data-stu-id="a003c-157">Chinese (traditional)</span></span>
> - <span data-ttu-id="a003c-158">Koreaks</span><span class="sxs-lookup"><span data-stu-id="a003c-158">Korean</span></span>
> - <span data-ttu-id="a003c-159">Japans</span><span class="sxs-lookup"><span data-stu-id="a003c-159">Japanese</span></span>
>
><span data-ttu-id="a003c-160">Deze ondersteuning is beschikbaar voor typen gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="a003c-160">This support is available for sensitive information types.</span></span> <span data-ttu-id="a003c-161">Zie [Ondersteuning voor Information Protection voor releaseopmerkingen bij dubbel-bytetekensets (preview)](mip-dbcs-relnotes.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a003c-161">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
