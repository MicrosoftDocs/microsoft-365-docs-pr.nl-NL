---
title: Een inhoudszoekactie kloonen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Gebruik het PowerShell-script in dit artikel om snel een bestaande inhoudszoekactie te kloonen in het compliancecentrum in Office 365 of Microsoft 365.
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161913"
---
# <a name="clone-a-content-search"></a>Een inhoudszoekactie kloonen

Het kan even duren voordat u een inhoudszoekactie maakt in het compliancecentrum in Office 365 of Microsoft 365 waarin veel postvakken of SharePoint en OneDrive voor Bedrijven worden doorzocht. Als u de sites opgeeft die u wilt zoeken, kunnen er ook fouten optreden als u een URL verkeerd typt. Als u deze problemen wilt voorkomen, kunt u het script Windows PowerShell in dit artikel gebruiken om snel een bestaande inhoudszoekactie te kloonen. Wanneer u een zoekopdracht kloont, wordt er een nieuwe zoekopdracht (met een andere naam) gemaakt die dezelfde eigenschappen (zoals de inhoudslocaties en de zoekquery) bevat als de oorspronkelijke zoekopdracht. Vervolgens kunt u de nieuwe zoekopdracht bewerken door de trefwoordquery of het datumbereik te wijzigen en uit te voeren.
  
Waarom worden inhoudszoekingen gekloond?
  
- Als u de resultaten van verschillende zoekquery's voor trefwoorden op dezelfde inhoudslocaties wilt vergelijken.
    
- Als u wilt besparen dat u een groot aantal inhoudslocaties opnieuw moet in- en uiten wanneer u een nieuwe zoekopdracht maakt.
    
- Om de grootte van de zoekresultaten te verminderen. Als u bijvoorbeeld een zoekopdracht hebt die te veel resultaten retourneert om te exporteren, kunt u de zoekopdracht kloonen en vervolgens een zoekvoorwaarde toevoegen op basis van een datumbereik om het aantal zoekresultaten te verminderen.
  
## <a name="script-information"></a>Scriptgegevens

- U moet lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum om het script uit te voeren dat in dit onderwerp wordt beschreven.
    
- Het script bevat minimale foutafhandeling. Het primaire doel van het script is om snel een inhoudszoekactie te kloonen.
    
- Met het script wordt een nieuwe inhoudszoekactie gemaakt, maar deze wordt niet gestart.
    
- In dit script wordt rekening gehouden met de vraag of het zoeken naar inhoud dat u kloont, is gekoppeld aan een eDiscovery-zaak. Als de zoekopdracht is gekoppeld aan een zaak, wordt de nieuwe zoekopdracht ook gekoppeld aan hetzelfde geval. Als de bestaande zoekopdracht niet aan een zaak is gekoppeld,  wordt de nieuwe zoekopdracht weergegeven op de pagina Inhoud zoeken in het compliancecentrum. 
    
- Het voorbeeldscript in dit onderwerp wordt niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft. Het voorbeeldscript wordt geleverd als IS zonder enige garantie. Microsoft wijst alle impliciete garanties verder af, inclusief, zonder beperking, impliciete garanties van verkoopbaarheid of geschiktheid voor een bepaald doel. Het volledige risico dat voortvloeit uit het gebruik of de prestaties van het voorbeeldscript en de documentatie blijft bij u. In geen geval zijn Microsoft, de auteurs of anderen die betrokken zijn bij het maken, produceren of leveren van de scripts aansprakelijk voor enige schade (met inbegrip van, zonder beperking, schade voor verlies van bedrijfswinsten, bedrijfsonderbreking, verlies van bedrijfsgegevens of ander geldverlies) als gevolg van het gebruik van of het onvermogen om de voorbeeldscripts of documentatie te gebruiken, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Stap 1: Het script uitvoeren om een zoekopdracht te kloonen

Met het script in deze stap wordt een nieuwe inhoudszoekactie gemaakt door een bestaand script te klonen. Wanneer u dit script uit te voeren, wordt u gevraagd om de volgende informatie:
  
- **Uw gebruikersreferenties:** het script gebruikt uw referenties om verbinding te maken met het beveiligings- & compliancecentrum voor uw organisatie met Windows PowerShell. Zoals eerder vermeld, moet u lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum om het script uit te voeren. 
    
- **De naam van de bestaande zoekopdracht:** dit is de inhoudszoekactie die u wilt klonen. 
    
- **De naam** van de nieuwe zoekopdracht die wordt gemaakt: als u deze waarde leeg laat, wordt in het script een naam gemaakt voor de nieuwe zoekopdracht die is gebaseerd op de naam van de zoekopdracht die u kloont. 
    
Een zoekopdracht kloonen:
  
1. Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; `CloneSearch.ps1`bijvoorbeeld.
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. Open Windows PowerShell en ga naar de map waar u het script hebt opgeslagen.
    
3. Voer het script uit; bijvoorbeeld:
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. Wanneer u om uw referenties wordt gevraagd, voert u uw e-mailadres en wachtwoord in en klikt u op **OK.**
    
5. Voer volgende informatie in wanneer u daarom wordt gevraagd door het script. Typ elk stukje informatie en druk op **Enter.**
    
    - De naam van de bestaande zoekopdracht.
    
    - De naam van de nieuwe zoekopdracht.
    
    Met het script wordt het nieuwe zoeken naar inhoud gemaakt, maar wordt het niet gestart. Dit geeft u de mogelijkheid om de zoekopdracht in de volgende stap te bewerken en uit te voeren. U kunt de eigenschappen van de nieuwe zoekactie bekijken door de **cmdlet Get-ComplianceSearch** uit te werken of door naar de pagina Inhoud zoeken of **eDiscovery** in het compliancecentrum te gaan, afhankelijk van of de nieuwe zoekopdracht is gekoppeld aan een zaak.  
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Stap 2: De gekloonde zoekopdracht bewerken en uitvoeren in het compliancecentrum

Nadat u het script hebt uitgevoerd om een bestaande inhoudszoekactie te kloonen, gaat u naar het compliancecentrum om de nieuwe zoekopdracht te bewerken en uit te voeren. Zoals eerder vermeld, kunt u een zoekopdracht bewerken door de trefwoordzoekquery te wijzigen en zoekvoorwaarden toe te voegen of te verwijderen. Zie voor meer informatie:
  
- [Zoeken naar inhoud in Office 365](content-search.md)
    
- [Trefwoordquery's en zoekvoorwaarden voor Zoeken naar inhoud](keyword-queries-and-search-conditions.md)
    
- [eDiscovery-zaken](./get-started-core-ediscovery.md)