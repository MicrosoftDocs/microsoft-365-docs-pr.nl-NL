---
title: Een woordenlijst met trefwoorden wijzigen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het wijzigen van een woordenlijst met trefwoorden in het Microsoft 365 compliancecentrum.
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685203"
---
# <a name="modify-a-keyword-dictionary"></a><span data-ttu-id="96edb-103">Een woordenlijst met trefwoorden wijzigen</span><span class="sxs-lookup"><span data-stu-id="96edb-103">Modify a keyword dictionary</span></span>

<span data-ttu-id="96edb-104">Mogelijk moet u trefwoorden in een van uw trefwoordenlijsten wijzigen of een van de ingebouwde woordenlijsten wijzigen.</span><span class="sxs-lookup"><span data-stu-id="96edb-104">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="96edb-105">U kunt dit doen via PowerShell of via het Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="96edb-105">You can do this through PowerShell or through the Compliance center.</span></span>

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a><span data-ttu-id="96edb-106">Een woordenlijst met trefwoorden wijzigen in compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="96edb-106">Modify a keyword dictionary in Compliance center</span></span>

<span data-ttu-id="96edb-107">Woordenlijsten met trefwoorden kunnen worden gebruikt `Primary elements` als of in sit-patronen `Supporting elements` (Sensitive Information Type).</span><span class="sxs-lookup"><span data-stu-id="96edb-107">Keyword dictionaries can be used as `Primary elements` or `Supporting elements` in sensitive information type (SIT) patterns.</span></span> <span data-ttu-id="96edb-108">U kunt een woordenlijst met trefwoorden bewerken tijdens het maken van een SIT of in een bestaande SIT.</span><span class="sxs-lookup"><span data-stu-id="96edb-108">You can edit a keyword dictionary while creating a SIT or in an existing SIT.</span></span> <span data-ttu-id="96edb-109">Bijvoorbeeld om een bestaande woordenlijst met trefwoorden te bewerken:</span><span class="sxs-lookup"><span data-stu-id="96edb-109">For example to edit an existing keyword dictionary:</span></span>

1. <span data-ttu-id="96edb-110">Open het patroon met de woordenlijst met trefwoorden die u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="96edb-110">Open the pattern that has the keyword dictionary you want to update.</span></span>
2. <span data-ttu-id="96edb-111">Zoek de woordenlijst met trefwoorden die u wilt bijwerken en kies Bewerken.</span><span class="sxs-lookup"><span data-stu-id="96edb-111">Find the keyword dictionary you want to update and choose edit.</span></span> 
3.  <span data-ttu-id="96edb-112">Maak uw bewerkingen met één trefwoord per regel.</span><span class="sxs-lookup"><span data-stu-id="96edb-112">Make your edits, using one keyword per line.</span></span>

![Schermafbeelding van trefwoorden bewerken](../media/edit-keyword-dictionary.png)

4. <span data-ttu-id="96edb-114">Kies `Done` .</span><span class="sxs-lookup"><span data-stu-id="96edb-114">Choose `Done`.</span></span>

## <a name="modify-a-keyword-dictionary-using-powershell"></a><span data-ttu-id="96edb-115">Een woordenlijst met trefwoorden wijzigen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="96edb-115">Modify a keyword dictionary using PowerShell</span></span> 

<span data-ttu-id="96edb-116">Zo wijzigen bijvoorbeeld we bepaalde termen in PowerShell, slaan we de termen lokaal op waar u ze in een editor kunt wijzigen en werken we vervolgens de vorige termen bij.</span><span class="sxs-lookup"><span data-stu-id="96edb-116">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="96edb-117">Haal eerst het woordenlijstobject op:</span><span class="sxs-lookup"><span data-stu-id="96edb-117">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="96edb-118">Als u `$dict` afdrukt, worden de verschillende variabelen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="96edb-118">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="96edb-119">De trefwoorden zelf worden opgeslagen in een object in de backend, maar `$dict.KeywordDictionary` bevat een representatie van de trefwoorden die u gebruikt om de woordenlijst te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="96edb-119">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="96edb-120">Voordat u de woordenlijst wijzigt, moet u de reeks termen weer in een matrix veranderen met de `.split(',')`-methode.</span><span class="sxs-lookup"><span data-stu-id="96edb-120">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="96edb-121">Vervolgens verwijdert u de ongewenste spaties tussen trefwoorden met de `.trim()`-methode, zodat alleen de trefwoorden overblijven.</span><span class="sxs-lookup"><span data-stu-id="96edb-121">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="96edb-122">Nu verwijdert u een aantal termen uit de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="96edb-122">Now you'll remove some terms from the dictionary.</span></span> <span data-ttu-id="96edb-123">Omdat de voorbeeldwoordenlijst slechts een paar trefwoorden bevat, kunt u de woordenlijst eenvoudig exporteren en bewerken in Kladblok, maar woordenlijsten bevatten over het algemeen een grote hoeveelheid tekst, dus u leert deze manier om deze eenvoudig te bewerken in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96edb-123">Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="96edb-124">In de laatste stap hebt u de trefwoorden in een matrix opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="96edb-124">In the last step, you saved the keywords to an array.</span></span> <span data-ttu-id="96edb-125">Er zijn verschillende manieren om [items uit een matrix te verwijderen](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), maar het is eenvoudig om een matrix te maken met de termen die u uit de woordenlijst wilt verwijderen. Kopieer vervolgens alleen de woordenlijsttermen die niet in de lijst met te verwijderen termen staan.</span><span class="sxs-lookup"><span data-stu-id="96edb-125">There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="96edb-126">Voer de opdracht `$terms` uit om de huidige lijst met termen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="96edb-126">Run the command  `$terms` to show the current list of terms.</span></span> <span data-ttu-id="96edb-127">De uitvoer van de opdracht ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="96edb-127">The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="96edb-128">Voer deze opdracht uit om de termen op te geven die u wilt verwijderen:</span><span class="sxs-lookup"><span data-stu-id="96edb-128">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="96edb-129">Voer deze opdracht uit als u de termen daadwerkelijk uit de lijst wilt verwijderen:</span><span class="sxs-lookup"><span data-stu-id="96edb-129">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="96edb-130">Voer de opdracht `$updatedTerms` uit om de bijgewerkte lijst met termen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="96edb-130">Run the command  `$updatedTerms` to show the updated list of terms.</span></span> <span data-ttu-id="96edb-131">De uitvoer van de opdracht ziet er zo uit (de opgegeven termen zijn verwijderd):</span><span class="sxs-lookup"><span data-stu-id="96edb-131">The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="96edb-132">Open het bestand, voeg de andere termen toe en sla op met UTF-16 (Unicode-codering).</span><span class="sxs-lookup"><span data-stu-id="96edb-132">Now open the file, add your other terms, and save with Unicode encoding (UTF-16).</span></span> <span data-ttu-id="96edb-133">Nu uploadt u de bijgewerkte termen en wordt de woordenlijst bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="96edb-133">Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="96edb-134">Nu is de woordenlijst bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="96edb-134">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="96edb-135">Het `Identity`-veld heeft de naam van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="96edb-135">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="96edb-136">Als u ook de naam van de woordenlijst wilt wijzigen met de cmdlet `set-`, hoeft u enkel de parameter `-Name` met de nieuwe woordenlijstnaam toe te voegen aan het bovenstaande.</span><span class="sxs-lookup"><span data-stu-id="96edb-136">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 

<span data-ttu-id="96edb-137">Zie ook</span><span class="sxs-lookup"><span data-stu-id="96edb-137">See Also</span></span>
- [<span data-ttu-id="96edb-138">Een woordenlijst met trefwoorden maken</span><span class="sxs-lookup"><span data-stu-id="96edb-138">Create a keyword dictionary</span></span>](create-a-keyword-dictionary.md)
- [<span data-ttu-id="96edb-139">Een aangepast type gevoelige informatie maken</span><span class="sxs-lookup"><span data-stu-id="96edb-139">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
