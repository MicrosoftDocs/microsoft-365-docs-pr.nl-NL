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
# <a name="modify-a-keyword-dictionary"></a>Een woordenlijst met trefwoorden wijzigen

Mogelijk moet u trefwoorden in een van uw trefwoordenlijsten wijzigen of een van de ingebouwde woordenlijsten wijzigen. U kunt dit doen via PowerShell of via het Compliancecentrum.

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>Een woordenlijst met trefwoorden wijzigen in compliancecentrum

Woordenlijsten met trefwoorden kunnen worden gebruikt `Primary elements` als of in sit-patronen `Supporting elements` (Sensitive Information Type). U kunt een woordenlijst met trefwoorden bewerken tijdens het maken van een SIT of in een bestaande SIT. Bijvoorbeeld om een bestaande woordenlijst met trefwoorden te bewerken:

1. Open het patroon met de woordenlijst met trefwoorden die u wilt bijwerken.
2. Zoek de woordenlijst met trefwoorden die u wilt bijwerken en kies Bewerken. 
3.  Maak uw bewerkingen met één trefwoord per regel.

![Schermafbeelding van trefwoorden bewerken](../media/edit-keyword-dictionary.png)

4. Kies `Done` .

## <a name="modify-a-keyword-dictionary-using-powershell"></a>Een woordenlijst met trefwoorden wijzigen met PowerShell 

Zo wijzigen bijvoorbeeld we bepaalde termen in PowerShell, slaan we de termen lokaal op waar u ze in een editor kunt wijzigen en werken we vervolgens de vorige termen bij. 

Haal eerst het woordenlijstobject op:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

Als u `$dict` afdrukt, worden de verschillende variabelen weergegeven. De trefwoorden zelf worden opgeslagen in een object in de backend, maar `$dict.KeywordDictionary` bevat een representatie van de trefwoorden die u gebruikt om de woordenlijst te wijzigen. 

Voordat u de woordenlijst wijzigt, moet u de reeks termen weer in een matrix veranderen met de `.split(',')`-methode. Vervolgens verwijdert u de ongewenste spaties tussen trefwoorden met de `.trim()`-methode, zodat alleen de trefwoorden overblijven. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Nu verwijdert u een aantal termen uit de woordenlijst. Omdat de voorbeeldwoordenlijst slechts een paar trefwoorden bevat, kunt u de woordenlijst eenvoudig exporteren en bewerken in Kladblok, maar woordenlijsten bevatten over het algemeen een grote hoeveelheid tekst, dus u leert deze manier om deze eenvoudig te bewerken in PowerShell.
  
In de laatste stap hebt u de trefwoorden in een matrix opgeslagen. Er zijn verschillende manieren om [items uit een matrix te verwijderen](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), maar het is eenvoudig om een matrix te maken met de termen die u uit de woordenlijst wilt verwijderen. Kopieer vervolgens alleen de woordenlijsttermen die niet in de lijst met te verwijderen termen staan.
  
Voer de opdracht `$terms` uit om de huidige lijst met termen weer te geven. De uitvoer van de opdracht ziet er zo uit: 
  
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

Voer deze opdracht uit om de termen op te geven die u wilt verwijderen:
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

Voer deze opdracht uit als u de termen daadwerkelijk uit de lijst wilt verwijderen:
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Voer de opdracht `$updatedTerms` uit om de bijgewerkte lijst met termen weer te geven. De uitvoer van de opdracht ziet er zo uit (de opgegeven termen zijn verwijderd): 
  
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

Open het bestand, voeg de andere termen toe en sla op met UTF-16 (Unicode-codering). Nu uploadt u de bijgewerkte termen en wordt de woordenlijst bijgewerkt.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Nu is de woordenlijst bijgewerkt. Het `Identity`-veld heeft de naam van de woordenlijst. Als u ook de naam van de woordenlijst wilt wijzigen met de cmdlet `set-`, hoeft u enkel de parameter `-Name` met de nieuwe woordenlijstnaam toe te voegen aan het bovenstaande. 

Zie ook
- [Een woordenlijst met trefwoorden maken](create-a-keyword-dictionary.md)
- [Een aangepast type gevoelige informatie maken](create-a-custom-sensitive-information-type.md)
