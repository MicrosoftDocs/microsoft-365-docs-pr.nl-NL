---
title: Inhoud zoeken gebruiken voor gerichte verzamelingen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: Gebruik Inhoud zoeken in het Microsoft 365 compliancecentrum om een gerichte verzameling uit te voeren, waarin wordt gezocht naar items in een specifiek postvak of sitemap.
ms.openlocfilehash: cf0364d39a78e1bbbc062d85ce750d190fbbda5a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311894"
---
# <a name="use-content-search-for-targeted-collections"></a>Inhoud zoeken gebruiken voor gerichte verzamelingen

Het zoekprogramma Inhoud in het Microsoft 365 compliancecentrum biedt geen directe manier in de gebruikersinterface om specifieke mappen te zoeken in Exchange postvakken of SharePoint en OneDrive voor Bedrijven sites. Het is echter mogelijk om specifieke mappen (een gerichte verzameling *genoemd)* te doorzoeken door de eigenschap Map-id op te geven voor de eigenschap e-mail of pad (DocumentLink) voor sites in de syntaxis van de werkelijke zoekquery. Het gebruik van Inhoud zoeken om een gerichte verzameling uit te voeren is handig als u zeker weet dat items die reageren op een zaak of bevoorrechte items zich bevinden in een specifiek postvak of sitemap. U kunt het script in dit artikel gebruiken om de map-id te verkrijgen voor postvakmappen of het pad (DocumentLink) voor mappen op een SharePoint en OneDrive voor Bedrijven site. Vervolgens kunt u de map-id of het pad in een zoekquery gebruiken om items in de map te retourneren.

> [!NOTE]
> Als u inhoud wilt retourneren in een map op een SharePoint of OneDrive voor Bedrijven site, gebruikt het script in dit onderwerp de beheerde eigenschap DocumentLink in plaats van de eigenschap Pad. De eigenschap DocumentLink is krachtiger dan de eigenschap Pad, omdat hierdoor alle inhoud in een map wordt retourneren, terwijl sommige mediabestanden niet worden teruggeslagen met de eigenschap Pad.

## <a name="before-you-run-a-targeted-collection"></a>Voordat u een gerichte verzameling uit te voeren

- U moet lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum om het script uit te voeren in stap 1. Zie [eDiscovery-machtigingen](assign-ediscovery-permissions.md)toewijzen voor meer informatie.

- U moet ook de rol E-mailontvangers in uw Exchange Online toegewezen. Dit is vereist voor het uitvoeren van **de cmdlet Get-MailboxFolderStatistics,** die is opgenomen in het script. Standaard wordt de rol E-mailontvangers toegewezen aan de rollengroepen Organisatiebeheer en Geadresseerdenbeheer in Exchange Online. Zie Leden van rollengroep beheren voor meer informatie over het toewijzen van machtigingen in [Exchange Online.](/exchange/manage-role-group-members-exchange-2013-help) U kunt ook een aangepaste rollengroep maken, de rol E-mailontvangers hieraan toewijzen en vervolgens de leden toevoegen die het script moeten uitvoeren in stap 1. Zie Rollengroepen [beheren voor meer informatie.](/Exchange/permissions-exo/role-groups)

- Het script in dit artikel ondersteunt moderne verificatie. U kunt het script gewoon gebruiken als u een Microsoft 365 of een Microsoft 365 GCC organisatie. Als u een organisatie Office 365 Duitsland, een Microsoft 365 GCC Hoge organisatie of een Microsoft 365 DoD-organisatie bent, moet u het script bewerken om het uit te voeren. U moet de lijn bewerken en de `Connect-ExchangeOnline` *parameter ExchangeEnvironmentName* (en de juiste waarde voor uw organisatietype) gebruiken om verbinding te maken met Exchange Online PowerShell.  U moet ook de regel bewerken en de `Connect-IPPSSession` parameters *ConnectionUri* en *AzureADAuthorizationEndpointUri* (en de juiste waarden voor uw organisatietype) gebruiken om verbinding te maken met Security & Compliance Center PowerShell. Zie voor meer informatie de voorbeelden in Verbinding maken powershell Exchange Online [powershell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) en Verbinding maken beveiligings- & [Compliance center PowerShell.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- Telkens wanneer u het script uit te voeren, wordt er een nieuwe externe PowerShell-sessie gemaakt. Dat betekent dat u alle externe PowerShell-sessies kunt gebruiken die voor u beschikbaar zijn. Als u dit wilt voorkomen, kunt u de volgende opdracht uitvoeren om de actieve externe PowerShell-sessies los te koppelen.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Zie powerShell Verbinding maken [Exchange Online voor meer informatie.](/powershell/exchange/connect-to-exchange-online-powershell)

- Het script bevat minimale foutafhandeling. Het primaire doel van het script is om snel een lijst met postvakmap-ed's of sitepaden weer te geven die kunnen worden gebruikt in de syntaxis van de zoekquery van een inhoudszoekactie om een gerichte verzameling uit te voeren.

- Het voorbeeldscript in dit onderwerp wordt niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft. Het voorbeeldscript wordt geleverd als IS zonder enige garantie. Microsoft wijst alle impliciete garanties verder af, inclusief, zonder beperking, impliciete garanties van verkoopbaarheid of geschiktheid voor een bepaald doel. Het volledige risico dat voortvloeit uit het gebruik of de prestaties van het voorbeeldscript en de documentatie blijft bij u. In geen geval zijn Microsoft, de auteurs of anderen die betrokken zijn bij het maken, produceren of leveren van de scripts aansprakelijk voor enige schade (met inbegrip van, zonder beperking, schade voor verlies van bedrijfswinsten, bedrijfsonderbreking, verlies van bedrijfsgegevens of ander geldverlies) als gevolg van het gebruik van of het onvermogen om de voorbeeldscripts of documentatie te gebruiken, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Stap 1: Voer het script uit om een lijst met mappen voor een postvak of site te krijgen

Het script dat u in deze eerste stap hebt uitgevoerd, retourneert een lijst met postvakmappen of SharePoint- en OneDrive voor Bedrijven-mappen en de bijbehorende map-id of het bijbehorende pad voor elke map. Wanneer u dit script uit te voeren, wordt u gevraagd om de volgende informatie.

- **E-mailadres of site-URL:** Typ een e-mailadres van de bewaarder om een lijst met Exchange postvakmappen en map-eds te retourneren. Of typ de URL voor een SharePoint site of OneDrive voor Bedrijven site om een lijst met paden voor de opgegeven site te retourneren. Dit zijn enkele voorbeelden:

  - **Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com

  - **SharePoint**: https <span>://</span>contoso.sharepoint.com/sites/marketing

  - **OneDrive voor Bedrijven**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com

- **Uw gebruikersreferenties:** het script gebruikt uw referenties om verbinding te maken met Exchange Online PowerShell of & Compliance center PowerShell met moderne verificatie. Zoals eerder is uitgelegd, moet u de juiste machtigingen krijgen om dit script te kunnen uitvoeren.

Een lijst met postvakmappen of sitedocumentlinknamen (padnamen) weergeven:

1. Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; `GetFolderSearchParameters.ps1`bijvoorbeeld.

   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
   # The script will then:                                            #
   #    * If an email address is supplied: list the folders for the target mailbox.            #
   #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
   #    * for the site.                                                                                    #
   #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
   #      appended to the folder ID or documentlink to use in a Content Search.                #
   # Notes:                                                #
   #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
   #      the current folder and all sub-folders are searched.                        #
   #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
   #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
   #      each sub-folder that you want to search.                                #
   #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
   #########################################################################################################
   # Collect the target email address or SharePoint Url
   $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
   # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
   }
   elseif ($addressOrSite.IndexOf("http") -ige 0)
   {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
   }
   else
   {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
   }
   ```

2. Open op uw lokale computer Windows PowerShell en ga naar de map waar u het script hebt opgeslagen.

3. Voer het script uit; bijvoorbeeld:

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. Voer de informatie in waar u om wordt gevraagd in het script.

    In het script wordt een lijst weergegeven met postvakmappen of sitemappen voor de opgegeven gebruiker. Laat dit venster open zodat u een map-id of documentlinknaam kunt kopiëren en deze kunt plakken in een zoekquery in stap 2.

    > [!TIP]
    > In plaats van een lijst met mappen weer te geven op het computerscherm, kunt u de uitvoer van het script opnieuw naar een tekstbestand leiden. Dit bestand wordt opgeslagen in de map waar het script zich bevindt. Als u bijvoorbeeld de uitvoer van het script wilt omleiden naar een tekstbestand, kunt u de volgende opdracht uitvoeren in stap 3: Vervolgens kunt u een map-id of documentlink uit het bestand kopiëren om te gebruiken in een  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` zoekquery.

### <a name="script-output-for-mailbox-folders"></a>Scriptuitvoer voor postvakmappen

Als u postvakmap-ID's krijgt, wordt het script verbonden met Exchange Online PowerShell, wordt de cmdlet **Get-MailboxFolderStatisics** uitgevoerd en wordt vervolgens de lijst met de mappen uit het opgegeven postvak weergegeven. Voor elke map in het postvak worden in het script de naam van de map weergegeven in de kolom **MapPath** en de map-id in de kolom **FolderQuery.** Bovendien voegt het script het voorvoegsel **mapId** (de naam van de eigenschap postvak) toe aan de map-id. Omdat de **eigenschap mapid** een doorzoekbare eigenschap is, gebruikt u in een zoekquery in stap 2 om  `folderid:<folderid>` in die map te zoeken. In het script worden maximaal 100 postvakmappen weergegeven.

> [!IMPORTANT]
> Het script in dit artikel bevat coderingslogica die de id-waarden van de map Met 64 tekens converteert die door **Get-MailboxFolderStatistics** worden geretourneerd naar dezelfde indeling met 48 tekens die wordt geïndexeerd voor zoeken. Als u alleen de **cmdlet Get-MailboxFolderStatistics** in PowerShell uitvoert om een map-id te verkrijgen (in plaats van het script in dit artikel uit te voeren), mislukt een zoekquery waarin die map-id-waarde wordt gebruikt. U moet het script uitvoeren om de correct opgemaakte map-id's te krijgen die kunnen worden gebruikt in een inhoudszoekactie.

Hier is een voorbeeld van de uitvoer die wordt geretourneerd door het script voor postvakmappen.

![Voorbeeld van de lijst met postvakmappen en map-ID's die door het script worden geretourneerd](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

In het voorbeeld in stap 2 ziet u de query die wordt gebruikt om te zoeken in de submap Purges in de map Herstelbare items van de gebruiker.

### <a name="script-output-for-site-folders"></a>Scriptuitvoer voor sitemappen

Als u het pad van de **eigenschap documentlink** krijgt van SharePoint- of OneDrive voor Bedrijven-sites, wordt het script verbonden met Security & Compliance PowerShell, wordt er een nieuwe inhoudszoekactie gemaakt die op de site naar mappen zoekt en wordt vervolgens een lijst weergegeven met de mappen op de opgegeven site. In het script wordt de naam van elke map weergegeven en wordt het voorvoegsel **van documentlink** toegevoegd aan de MAP-URL. Omdat de **eigenschap documentlink** een doorzoekbare eigenschap is, gebruikt u eigenschap:waardepaar in een zoekquery in stap 2 om in `documentlink:<path>` die map te zoeken. In het script worden maximaal 200 sitemappen weergegeven. Als er meer dan 200 sitemappen zijn, worden de nieuwste mappen weergegeven.

Hier is een voorbeeld van de uitvoer die wordt geretourneerd door het script voor sitemappen.

![Voorbeeld van de lijst met documentlinknamen voor sitemappen die door het script worden geretourneerd](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Stap 2: Een map-id of documentlink gebruiken om een gerichte verzameling uit te voeren

Nadat u het script hebt uitgevoerd om een lijst met map-1D's of documentkoppelingen voor een specifieke gebruiker te verzamelen, gaat u naar het compliancecentrum van Microsoft 365 en maakt u een nieuwe inhoudszoekactie om in een specifieke map te zoeken. U gebruikt het paar of eigenschap:waarde in de zoekquery die u configureert in het vak Trefwoord Inhoud zoeken (of als de waarde voor de  `folderid:<folderid>` parameter  `documentlink:<path>`  *ContentMatchQuery*  als u de **cmdlet New-ComplianceSearch** gebruikt). U kunt de  `folderid`  `documentlink` of-eigenschap combineren met andere zoekparameters of zoekvoorwaarden. Als u alleen de eigenschap of eigenschap in de query op neemt, worden alle items in de opgegeven map  `folderid`  `documentlink` als retourneert.

1. Ga naar en meld u aan met het account en de referenties die u hebt gebruikt om het script uit te <https://compliance.microsoft.com> voeren in stap 1.

2. Klik in het linkerdeelvenster van het compliancecentrum op **Alle** inhoud  >  **zoeken weergeven** en klik vervolgens op Nieuwe **zoekopdracht.**

3. Plak in **het vak** Trefwoorden de of de waarde die is geretourneerd door het script in `folderid:<folderid>` stap  `documentlink:<path>` 1.

    In de query in de volgende schermafbeelding wordt bijvoorbeeld gezocht naar een item in de submap Purges in de map Herstelbare items van de gebruiker (de waarde van de eigenschap voor de submap Purges wordt weergegeven in de `folderid` schermafbeelding in stap 1):

    ![De mapid of documentlink plakken in het trefwoordvak van de zoekquery](../media/FolderIDSearchQuery.png)

4. Selecteer **onder** Locaties de optie **Specifieke locaties** en klik vervolgens op **Wijzigen.**

5. Ga op een van de volgende stappen te werk, op basis van of u een postvakmap of een sitemap zoekt:

    - Klik naast **Exchange** e-mail op **Gebruikers,** groepen of teams kiezen en voeg vervolgens hetzelfde postvak toe dat u hebt opgegeven tijdens het uitvoeren van het script in stap 1.

      Of

    - Klik naast **SharePoint sites** op Sites **kiezen** en voeg vervolgens dezelfde site-URL toe die u hebt opgegeven toen u het script in stap 1 uitliep.

6. Nadat u de inhoudslocatie hebt op opslaan om te zoeken, klikt u  op **Opslaan & uitvoeren,** typt u een naam voor het zoeken naar inhoud en klikt u vervolgens op Opslaan om de doelverzamelingszoekactie te starten.

### <a name="examples-of-search-queries-for-targeted-collections"></a>Voorbeelden van zoekquery's voor gerichte verzamelingen

Hier zijn enkele voorbeelden van het gebruik van de eigenschappen en eigenschappen  `folderid`  `documentlink` in een zoekquery om een gerichte verzameling uit te voeren. Tijdelijke aanduidingen worden gebruikt voor  `folderid:<folderid>` en om ruimte te  `documentlink:<path>` besparen.

- In dit voorbeeld wordt gezocht in drie verschillende postvakmappen. U kunt vergelijkbare query-syntaxis gebruiken om te zoeken in de verborgen mappen in de map Herstelbare items van een gebruiker.

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- In dit voorbeeld wordt in een postvakmap gezocht naar items die een exacte woordgroep bevatten.

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- In dit voorbeeld wordt in een sitemap (en eventuele submappen) gezocht naar documenten met de letters 'NDA' in de titel.

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- In dit voorbeeld wordt in een sitemap (en een submap) gezocht naar documenten die binnen een datumbereik zijn gewijzigd.

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Meer informatie

Houd rekening met de volgende dingen wanneer u het script in dit artikel gebruikt om gerichte verzamelingen uit te voeren.

- Het script verwijdert geen mappen uit de resultaten. Sommige mappen die in de resultaten worden vermeld, kunnen dus niet kunnen worden doorzocht (of nul items retourneren) omdat ze door het systeem gegenereerde inhoud bevatten of omdat ze alleen submappen bevatten en geen postvakitems.

- Dit script retourneert alleen mapgegevens voor het primaire postvak van de gebruiker. Het retourneert geen informatie over mappen in het archiefpostvak van de gebruiker. Als u informatie over mappen in het archiefpostvak van de gebruiker wilt retourneren, kunt u het script bewerken. U kunt dit doen door de regel te wijzigen in en vervolgens het bewerkte script op te slaan `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` en uit te voeren. Deze wijziging retourneert de map-eds voor mappen en submappen in het archiefpostvak van de gebruiker. Als u het hele archiefpostvak wilt doorzoeken, kunt u alle map-id-eigenschappen:waardeparen verbinden met een `OR` operator in een zoekquery.

- Bij het zoeken in postvakmappen wordt alleen gezocht naar de opgegeven map (die door de eigenschap wordt geïdentificeerd). Submappen worden niet `folderid` doorzocht. Als u wilt zoeken in submappen, moet u de map-id gebruiken voor de submap die u wilt zoeken.

- Wanneer u sitemappen zoekt, worden de map (geïdentificeerd door de eigenschap) en `documentlink` alle submappen doorzocht.

- Wanneer u de resultaten exporteert van een zoekopdracht waarin u alleen de eigenschap in de zoekquery hebt opgegeven, kunt u de eerste `folderid` exportoptie kiezen: 'Alle items, met uitzondering van items met een niet-herkende notatie, worden versleuteld of zijn om andere redenen niet geïndexeerd.' Alle items in de map worden altijd geëxporteerd, ongeacht de indexeringsstatus, omdat de map-id altijd wordt geïndexeerd.
