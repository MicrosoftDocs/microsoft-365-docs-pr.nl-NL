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
ms.openlocfilehash: 94bacc2a2fe91fdc35aad753cc2e7db80a374e29
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162680"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="98e7d-103">Een woordenlijst met trefwoorden maken</span><span class="sxs-lookup"><span data-stu-id="98e7d-103">Create a keyword dictionary</span></span>

<span data-ttu-id="98e7d-104">Preventie van gegevensverlies (DLP) kan uw vertrouwelijke items identificeren, controleren en beveiligen.</span><span class="sxs-lookup"><span data-stu-id="98e7d-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="98e7d-105">Soms moet er worden gezocht naar trefwoorden om gevoelige items te identificeren, met name bij het identificeren van algemene inhoud (zoals communicatie in verband met gezondheidszorg) of ongepaste taal of expliciete taal.</span><span class="sxs-lookup"><span data-stu-id="98e7d-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="98e7d-106">Hoewel u trefwoordlijsten in typen vertrouwelijke informatie kunt maken, zijn trefwoordlijsten beperkt in grootte en moet XML worden gewijzigd om ze te maken of te bewerken.</span><span class="sxs-lookup"><span data-stu-id="98e7d-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="98e7d-107">Trefwoordenlijsten bieden een eenvoudiger beheer van trefwoorden en op een veel grotere schaal. Ze ondersteunen maximaal 1 MB aan termen (na compressie) in de woordenlijst en ondersteunen elke taal.</span><span class="sxs-lookup"><span data-stu-id="98e7d-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="98e7d-108">De tenantlimiet is ook 1 MB na compressie.</span><span class="sxs-lookup"><span data-stu-id="98e7d-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="98e7d-109">De limiet van 1 MB voor de compressie na de compressie betekent dat alle woordenlijsten voor een tenant bijna 1 miljoen tekens kunnen hebben.</span><span class="sxs-lookup"><span data-stu-id="98e7d-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="98e7d-110">Limieten trefwoordenlijst</span><span class="sxs-lookup"><span data-stu-id="98e7d-110">Keyword dictionary limits</span></span>

<span data-ttu-id="98e7d-111">Er geldt een limiet van 50 vertrouwelijke informatietypen op basis van trefwoordlijsten die per tenant kunnen worden aangemaakt.</span><span class="sxs-lookup"><span data-stu-id="98e7d-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="98e7d-112">Als u wilt weten hoeveel woordenlijsten u in uw tenant hebt, maakt u verbinding via de procedures in [Verbinding maken het Beveiligings- en compliancecentrum in PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) om verbinding te maken met uw tenant en dit PowerShell-script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="98e7d-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="98e7d-113">Basisstappen voor het maken van een trefwoordenlijst</span><span class="sxs-lookup"><span data-stu-id="98e7d-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="98e7d-114">De trefwoorden voor uw woordenlijst kunnen afkomstig zijn uit verschillende bronnen, meestal uit een bestand (zoals een .csv- of .txt-lijst) dat in de service of door een PowerShell-cmdlet is geïmporteerd, uit een lijst die u rechtstreeks in de PowerShell-cmdlet of uit een bestaande woordenlijst invoert.</span><span class="sxs-lookup"><span data-stu-id="98e7d-114">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary.</span></span> <span data-ttu-id="98e7d-115">Wanneer u een trefwoordenlijst maakt, volgt u dezelfde basisstappen:</span><span class="sxs-lookup"><span data-stu-id="98e7d-115">When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="98e7d-116">Gebruik het ,**Beveiligings- en compliancecentrum** ([https://protection.office.com](https://protection.office.com)) of maak verbinding met **Beveiligings- &amp; compliancecentrum PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="98e7d-117">**Definieer of voer uw trefwoorden in vanuit uw bedoelde bron**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="98e7d-118">De wizard en de cmdlet aanvaarden beide een door komma's gescheiden lijst met trefwoorden om een aangepaste woordenlijst voor trefwoorden te creëren. Deze stap varieert dus enigszins, afhankelijk van waar uw trefwoorden vandaan komen.</span><span class="sxs-lookup"><span data-stu-id="98e7d-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="98e7d-119">Nadat ze zijn geladen, worden ze versleuteld en geconverteerd naar een byte-matrix voordat ze worden geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="98e7d-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="98e7d-120">**Uw woordenlijst maken**</span><span class="sxs-lookup"><span data-stu-id="98e7d-120">**Create your dictionary**.</span></span> <span data-ttu-id="98e7d-121">Kies een naam en beschrijving en maak uw woordenlijst aan.</span><span class="sxs-lookup"><span data-stu-id="98e7d-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="98e7d-122">Een refwoordenlijst maken met het Beveiligings- en compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="98e7d-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="98e7d-123">Gebruik de volgende stappen om trefwoorden te maken en te importeren voor een aangepaste woordenlijst:</span><span class="sxs-lookup"><span data-stu-id="98e7d-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="98e7d-124">Verbinding maken met het Beveiligings- en compliancecentrum ([https://protection.office.com](https://protection.office.com))</span><span class="sxs-lookup"><span data-stu-id="98e7d-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="98e7d-125">Ga naar **Classificaties > vertrouwelijke informatietypen**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="98e7d-126">Selecteer **Maken** en voer een **Naam** en **Beschrijving** in voor het vertrouwelijke gegevenstype,  en selecteer vervolgens **Volgende**</span><span class="sxs-lookup"><span data-stu-id="98e7d-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="98e7d-127">Selecteer **Een element toevoegen** en selecteer vervolgens **Woordenlijst (grote trefwoorden)** in de vervolgkeuzelijst **Inhoud detecteren met**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="98e7d-128">Selecteer **een woordenlijst toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="98e7d-129">Selecteer onder het besturingselement Zoeken **U kunt hier nieuwe woordenlijsten voor trefwoorden aanmaken**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="98e7d-130">Voer een **Naam** voor de aangepaste woordenlijst in.</span><span class="sxs-lookup"><span data-stu-id="98e7d-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="98e7d-131">Selecteer **Importeren** en selecteer **Uit tekst** of **Uit een .csv-bestand** afhankelijk van het type trefwoordbestand.</span><span class="sxs-lookup"><span data-stu-id="98e7d-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="98e7d-132">Selecteer in het dialoogvenster het trefwoordbestand van uw lokale pc of netwerkbestandsshare en selecteer vervolgens **Openen**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="98e7d-133">Selecteer **Opslaan** en selecteer vervolgens uw aangepaste woordenlijst in de lijst met **Trefwoordlijsten**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="98e7d-134">Selecteer **Toevoegen** en vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="98e7d-135">Controleer de selecties van vertrouwelijke gegevenstype en rond deze af en selecteer **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="98e7d-136">Een trefwoordwoordenlijst maken vanuit een bestand met PowerShell</span><span class="sxs-lookup"><span data-stu-id="98e7d-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="98e7d-137">Wanneer u een grote woordenlijst moet maken, is het vaak nodig om trefwoorden te gebruiken uit een bestand of een lijst die is geëxporteerd vanuit een andere bron.</span><span class="sxs-lookup"><span data-stu-id="98e7d-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="98e7d-138">In dit geval maakt u een trefwoordwoordenlijst met een lijst met ongepaste taal die u uit externe e-mail kunt weren.</span><span class="sxs-lookup"><span data-stu-id="98e7d-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="98e7d-139">U maakt als eerste [Verbinding met PowerShell van het Beveiligings-&amp; en compliancecentrum](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="98e7d-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="98e7d-140">Kopieer de trefwoorden naar een tekstbestand en zorg ervoor dat elk trefwoord op een aparte regel staat.</span><span class="sxs-lookup"><span data-stu-id="98e7d-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="98e7d-141">Sla het tekstbestand op met Unicode-codering.</span><span class="sxs-lookup"><span data-stu-id="98e7d-141">Save the text file with Unicode encoding.</span></span> <span data-ttu-id="98e7d-142">Selecteer in Kladblok \> **Opslaan als** \> **Codering** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="98e7d-142">In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="98e7d-143">Lees het bestand in een variabele door deze cmdlet uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="98e7d-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="98e7d-144">Maak de woordenlijst door deze cmdlet uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="98e7d-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="98e7d-145">Een bestaande trefwoordenlijst wijzigen</span><span class="sxs-lookup"><span data-stu-id="98e7d-145">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="98e7d-146">Mogelijk moet u trefwoorden in een van uw trefwoordenlijsten wijzigen of een van de ingebouwde woordenlijsten wijzigen.</span><span class="sxs-lookup"><span data-stu-id="98e7d-146">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="98e7d-147">Op dit moment kunt u alleen een aangepaste woordenlijst met trefwoorden bijwerken via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98e7d-147">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="98e7d-148">Zo wijzigen bijvoorbeeld we bepaalde termen in PowerShell, slaan we de termen lokaal op waar u ze in een editor kunt wijzigen en werken we vervolgens de vorige termen bij.</span><span class="sxs-lookup"><span data-stu-id="98e7d-148">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="98e7d-149">Haal eerst het woordenlijstobject op:</span><span class="sxs-lookup"><span data-stu-id="98e7d-149">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="98e7d-150">Als u `$dict` afdrukt, worden de verschillende variabelen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="98e7d-150">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="98e7d-151">De trefwoorden zelf worden opgeslagen in een object in de backend, maar `$dict.KeywordDictionary` bevat een representatie van de trefwoorden die u gebruikt om de woordenlijst te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="98e7d-151">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="98e7d-152">Voordat u de woordenlijst wijzigt, moet u de reeks termen weer in een matrix veranderen met de `.split(',')`-methode.</span><span class="sxs-lookup"><span data-stu-id="98e7d-152">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="98e7d-153">Vervolgens verwijdert u de ongewenste spaties tussen trefwoorden met de `.trim()`-methode, zodat alleen de trefwoorden overblijven.</span><span class="sxs-lookup"><span data-stu-id="98e7d-153">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="98e7d-154">Nu verwijdert u een aantal termen uit de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="98e7d-154">Now you'll remove some terms from the dictionary.</span></span> <span data-ttu-id="98e7d-155">Omdat de voorbeeldwoordenlijst slechts een paar trefwoorden bevat, kunt u de woordenlijst eenvoudig exporteren en bewerken in Kladblok, maar woordenlijsten bevatten over het algemeen een grote hoeveelheid tekst, dus u leert deze manier om deze eenvoudig te bewerken in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98e7d-155">Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="98e7d-156">In de laatste stap hebt u de trefwoorden in een matrix opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="98e7d-156">In the last step, you saved the keywords to an array.</span></span> <span data-ttu-id="98e7d-157">Er zijn verschillende manieren om [items uit een matrix te verwijderen](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), maar het is eenvoudig om een matrix te maken met de termen die u uit de woordenlijst wilt verwijderen. Kopieer vervolgens alleen de woordenlijsttermen die niet in de lijst met te verwijderen termen staan.</span><span class="sxs-lookup"><span data-stu-id="98e7d-157">There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="98e7d-158">Voer de opdracht `$terms` uit om de huidige lijst met termen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="98e7d-158">Run the command  `$terms` to show the current list of terms.</span></span> <span data-ttu-id="98e7d-159">De uitvoer van de opdracht ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="98e7d-159">The output of the command looks like this:</span></span> 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

<span data-ttu-id="98e7d-160">Voer deze opdracht uit om de termen op te geven die u wilt verwijderen:</span><span class="sxs-lookup"><span data-stu-id="98e7d-160">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="98e7d-161">Voer deze opdracht uit als u de termen daadwerkelijk uit de lijst wilt verwijderen:</span><span class="sxs-lookup"><span data-stu-id="98e7d-161">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="98e7d-162">Voer de opdracht `$updatedTerms` uit om de bijgewerkte lijst met termen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="98e7d-162">Run the command  `$updatedTerms` to show the updated list of terms.</span></span> <span data-ttu-id="98e7d-163">De uitvoer van de opdracht ziet er zo uit (de opgegeven termen zijn verwijderd):</span><span class="sxs-lookup"><span data-stu-id="98e7d-163">The output of the command looks like this (the specified terms have been removed):</span></span> 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="98e7d-164">Open het bestand, voeg de andere termen toe en sla op met UTF-16 (Unicode-codering).</span><span class="sxs-lookup"><span data-stu-id="98e7d-164">Now open the file, add your other terms, and save with Unicode encoding (UTF-16).</span></span> <span data-ttu-id="98e7d-165">Nu uploadt u de bijgewerkte termen en wordt de woordenlijst bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="98e7d-165">Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="98e7d-166">Nu is de woordenlijst bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="98e7d-166">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="98e7d-167">Het `Identity`-veld heeft de naam van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="98e7d-167">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="98e7d-168">Als u ook de naam van de woordenlijst wilt wijzigen met de cmdlet `set-`, hoeft u enkel de parameter `-Name` met de nieuwe woordenlijstnaam toe te voegen aan het bovenstaande.</span><span class="sxs-lookup"><span data-stu-id="98e7d-168">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="98e7d-169">Trefwoordenlijsten gebruiken in aangepaste typen vertrouwelijke informatie en DLP-beleidsregels</span><span class="sxs-lookup"><span data-stu-id="98e7d-169">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="98e7d-170">Trefwoordenlijsten kunnen worden gebruikt als onderdeel van de vereisten voor overeenkomende gegevens voor een aangepast type vertrouwelijke informatie, of zelf als een type gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="98e7d-170">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="98e7d-171">Voor beide moet een [aangepast type gevoelige informatie worden gemaakt](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="98e7d-171">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="98e7d-172">Volg de instructies in het gekoppelde artikel om een type gevoelige informatie te maken.</span><span class="sxs-lookup"><span data-stu-id="98e7d-172">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="98e7d-173">Wanneer u de XML hebt, hebt u de GUID-id voor de woordenlijst nodig om deze te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="98e7d-173">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="98e7d-174">Voer deze opdracht uit om de identiteit van uw woordenlijst op te halen en de waarde van de eigenschap **id** te kopiëren:</span><span class="sxs-lookup"><span data-stu-id="98e7d-174">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="98e7d-175">De uitvoer van de opdracht ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="98e7d-175">The output of the command looks like this:</span></span>
  
<span data-ttu-id="98e7d-176">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="98e7d-176">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="98e7d-177">Plak de identiteit in de XML van het aangepaste gegevenstype en upload deze.</span><span class="sxs-lookup"><span data-stu-id="98e7d-177">Paste the identity into your custom sensitive information type's XML and upload it.</span></span> <span data-ttu-id="98e7d-178">De woordenlijst wordt nu weergegeven in uw lijst met typen vertrouwelijke informatie en u kunt deze onmiddellijk in uw beleid gebruiken, waarin u opgeeft hoeveel trefwoorden moeten worden overeenkomen.</span><span class="sxs-lookup"><span data-stu-id="98e7d-178">Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
> <span data-ttu-id="98e7d-179">Microsoft 365 Information Protection ondersteunt talen voor preview van dubbel-byte-tekensets voor:</span><span class="sxs-lookup"><span data-stu-id="98e7d-179">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="98e7d-180">Vereenvoudigd Chinees</span><span class="sxs-lookup"><span data-stu-id="98e7d-180">Chinese (simplified)</span></span>
> - <span data-ttu-id="98e7d-181">Traditioneel Chinees</span><span class="sxs-lookup"><span data-stu-id="98e7d-181">Chinese (traditional)</span></span>
> - <span data-ttu-id="98e7d-182">Korean</span><span class="sxs-lookup"><span data-stu-id="98e7d-182">Korean</span></span>
> - <span data-ttu-id="98e7d-183">Japanese</span><span class="sxs-lookup"><span data-stu-id="98e7d-183">Japanese</span></span>
>
><span data-ttu-id="98e7d-184">Deze ondersteuning is beschikbaar voor typen gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="98e7d-184">This support is available for sensitive information types.</span></span> <span data-ttu-id="98e7d-185">Zie [Ondersteuning voor Information Protection voor releaseopmerkingen bij dubbel-bytetekensets (preview)](mip-dbcs-relnotes.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="98e7d-185">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
