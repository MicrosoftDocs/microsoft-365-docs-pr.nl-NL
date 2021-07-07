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
ms.openlocfilehash: 8d313650f298f2ab26989bec9df1260918f7dd5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300102"
---
# <a name="create-a-keyword-dictionary"></a>Een woordenlijst met trefwoorden maken

Preventie van gegevensverlies (DLP) kan uw vertrouwelijke items identificeren, controleren en beveiligen. Soms moet er worden gezocht naar trefwoorden om gevoelige items te identificeren, met name bij het identificeren van algemene inhoud (zoals communicatie in verband met gezondheidszorg) of ongepaste taal of expliciete taal. Hoewel u trefwoordlijsten in typen vertrouwelijke informatie kunt maken, zijn trefwoordlijsten beperkt in grootte en moet XML worden gewijzigd om ze te maken of te bewerken. Trefwoordenlijsten bieden een eenvoudiger beheer van trefwoorden en op een veel grotere schaal. Ze ondersteunen maximaal 1 MB aan termen (na compressie) in de woordenlijst en ondersteunen elke taal. De tenantlimiet is ook 1 MB na compressie. De limiet van 1 MB voor de compressie na de compressie betekent dat alle woordenlijsten voor een tenant bijna 1 miljoen tekens kunnen hebben.

## <a name="keyword-dictionary-limits"></a>Limieten trefwoordenlijst

Er geldt een limiet van 50 vertrouwelijke informatietypen op basis van trefwoordlijsten die per tenant kunnen worden aangemaakt. Als u wilt weten hoeveel woordenlijsten u in uw tenant hebt, maakt u verbinding via de procedures in [Verbinding maken het Beveiligings- en compliancecentrum in PowerShell](/powershell/exchange/connect-to-scc-powershell) om verbinding te maken met uw tenant en dit PowerShell-script uit te voeren.

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Basisstappen voor het maken van een trefwoordenlijst

De trefwoorden voor uw woordenlijst kunnen afkomstig zijn uit verschillende bronnen, meestal uit een bestand (zoals een .csv- of .txt-lijst) dat in de service of door een PowerShell-cmdlet is geïmporteerd, uit een lijst die u rechtstreeks in de PowerShell-cmdlet of uit een bestaande woordenlijst invoert. Wanneer u een trefwoordenlijst maakt, volgt u dezelfde stappen:
  
1. Gebruik het ,**Beveiligings- en compliancecentrum** ([https://protection.office.com](https://protection.office.com)) of maak verbinding met **Beveiligings- &amp; compliancecentrum PowerShell**.
    
2. **Definieer of voer uw trefwoorden in vanuit uw bedoelde bron**. De wizard en de cmdlet aanvaarden beide een door komma's gescheiden lijst met trefwoorden om een aangepaste woordenlijst voor trefwoorden te creëren. Deze stap varieert dus enigszins, afhankelijk van waar uw trefwoorden vandaan komen. Nadat ze zijn geladen, worden ze versleuteld en geconverteerd naar een byte-matrix voordat ze worden geïmporteerd.
    
3. **Uw woordenlijst maken** Kies een naam en beschrijving en maak uw woordenlijst aan.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Een refwoordenlijst maken met het Beveiligings- en compliancecentrum

Gebruik de volgende stappen om trefwoorden te maken en te importeren voor een aangepaste woordenlijst:

1. Verbinding maken met het Beveiligings- en compliancecentrum ([https://protection.office.com](https://protection.office.com))

2. Ga naar **Classificaties > vertrouwelijke informatietypen**.

3. Selecteer **Maken** en voer een **Naam** en **Beschrijving** in voor het vertrouwelijke gegevenstype,  en selecteer vervolgens **Volgende**

4. Selecteer **Een element toevoegen** en selecteer vervolgens **Woordenlijst (grote trefwoorden)** in de vervolgkeuzelijst **Inhoud detecteren met**.

5. Selecteer **een woordenlijst toevoegen**.

6. Selecteer onder het besturingselement Zoeken **U kunt hier nieuwe woordenlijsten voor trefwoorden aanmaken**.

7. Voer een **Naam** voor de aangepaste woordenlijst in.

8. Selecteer **Importeren** en selecteer **Uit tekst** of **Uit een .csv-bestand** afhankelijk van het type trefwoordbestand.

9. Selecteer in het dialoogvenster het trefwoordbestand van uw lokale pc of netwerkbestandsshare en selecteer vervolgens **Openen**.

10. Selecteer **Opslaan** en selecteer vervolgens uw aangepaste woordenlijst in de lijst met **Trefwoordlijsten**.

11. Selecteer **Toevoegen** en vervolgens **Volgende**.

12. Controleer de selecties van vertrouwelijke gegevenstype en rond deze af en selecteer **Voltooien**.
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>Een trefwoordwoordenlijst maken vanuit een bestand met PowerShell

Wanneer u een grote woordenlijst moet maken, is het vaak nodig om trefwoorden te gebruiken uit een bestand of een lijst die is geëxporteerd vanuit een andere bron. In dit geval maakt u een trefwoordwoordenlijst met een lijst met ongepaste taal die u uit externe e-mail kunt weren. U maakt als eerste [Verbinding met PowerShell van het Beveiligings-&amp; en compliancecentrum](/powershell/exchange/connect-to-scc-powershell).
  
1. Kopieer de trefwoorden naar een tekstbestand en zorg ervoor dat elk trefwoord op een aparte regel staat.
    
2. Sla het tekstbestand op met Unicode-codering. Selecteer in Kladblok \> **Opslaan als** \> **Codering** \> **Unicode**.
    
3. Lees het bestand in een variabele door deze cmdlet uit te voeren:
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. Maak de woordenlijst door deze cmdlet uit te voeren:
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Trefwoordenlijsten gebruiken in aangepaste typen vertrouwelijke informatie en DLP-beleidsregels

Trefwoordenlijsten kunnen worden gebruikt als onderdeel van de vereisten voor overeenkomende gegevens voor een aangepast type vertrouwelijke informatie, of zelf als een type gevoelige informatie. Voor beide moet een [aangepast type gevoelige informatie worden gemaakt](create-a-custom-sensitive-information-type-in-scc-powershell.md). Volg de instructies in het gekoppelde artikel om een type gevoelige informatie te maken. Wanneer u de XML hebt, hebt u de GUID-id voor de woordenlijst nodig om deze te gebruiken.
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

Voer deze opdracht uit om de identiteit van uw woordenlijst op te halen en de waarde van de eigenschap **id** te kopiëren: 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

De uitvoer van de opdracht ziet er zo uit:
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


U plak de identiteit in uw aangepast type gevoelige informatie-XML en u upload deze. De woordenlijst wordt nu weergegeven in uw lijst met typen gevoelige informatie en u kunt deze onmiddellijk in uw beleid gebruiken, waarin u opgeeft hoeveel trefwoorden moeten overeenkomen.
  
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
> Microsoft 365 Information Protection ondersteunt dubbelbyte tekensettalen voor:
> - Vereenvoudigd Chinees
> - Traditioneel Chinees
> - Koreaks
> - Japans
>
>Deze ondersteuning is beschikbaar voor typen gevoelige informatie. Zie [Ondersteuning voor Information Protection voor releaseopmerkingen bij dubbel-bytetekensets (preview)](mip-dbcs-relnotes.md) voor meer informatie.

> [!TIP]
> Om patronen te detecteren die Chinese/Japanse karakters en enkelbyte karakters bevatten of om patronen te detecteren die Chinees/Japans en Engels bevatten, definieert u twee varianten van het trefwoord of de regex. 
>
> Om bijvoorbeeld een trefwoord als "机密的document" te detecteren, gebruikt u twee varianten van het trefwoord; een met een spatie tussen de Japanse en Engelse tekst en een andere zonder een spatie tussen de Japanse en Engelse tekst. De trefwoorden die in de SIT moeten worden toegevoegd, moeten dus "机密的 document" en "机密的document" zijn. Evenzo moeten twee varianten worden gebruikt om een zin "東京オリンピック2020" te detecteren; "東京オリンピック 2020" en "東京オリンピック2020".
>
> Tijdens het maken van een regex met behulp van een dubbel byteafbreekstreepje of een dubbele byteperiode, moet u ervoor zorgen dat beide tekens, zoals één, een afbreekstreepje of een punt in een regex. Hier volgt een voorbeeld van een regex ter referentie:
>
>    - (?<!\d)([４][０-９]{3}[\-?\－\t]*[０-９]{4}
>
> We raden u aan een tekenreeksovereenkomst te gebruiken in plaats van een woordovereenkomst in een zoekwoordenlijst.
