---
title: Zoeken in het postvak & OneDrive voor Bedrijven een lijst met gebruikers met Inhoud zoeken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Gebruik Inhoud zoeken en het script in dit artikel om te zoeken in de postvakken en OneDrive voor Bedrijven sites voor een groep gebruikers.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51e668438c6016a0c5f2c914dc2b2e86cc56f49e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162078"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Inhoud zoeken gebruiken om in het postvak en OneDrive voor Bedrijven zoeken naar een lijst met gebruikers

Het Beveiligings- & compliancecentrum biedt een aantal Windows PowerShell cmdlets om tijdrovende eDiscovery-gerelateerde taken te automatiseren. Het maken van een inhoudszoekactie in het beveiligings- & compliancecentrum voor het zoeken naar een groot aantal bewaarlocaties voor inhoud kost tijd en voorbereiding. Voordat u een zoekopdracht maakt, moet u de URL voor elke OneDrive voor Bedrijven site verzamelen en vervolgens elk postvak en OneDrive voor Bedrijven aan de zoekopdracht toevoegen. In toekomstige versies is dit gemakkelijker te doen in het beveiligings- & Compliancecentrum. Tot die tijd kunt u het script in dit artikel gebruiken om dit proces te automatiseren. In dit script wordt u gevraagd om de naam van het MySite-domein van uw organisatie (bijvoorbeeld **contoso** in de URL), een lijst met e-mailadressen van gebruikers, de naam van de nieuwe inhoudszoekactie en de zoekquery die u wilt `https://contoso-my.sharepoint.com` gebruiken. Het script krijgt de OneDrive voor Bedrijven-URL voor elke gebruiker in de lijst en vervolgens wordt er een inhoudszoekactie gemaakt en gestart die voor elke gebruiker in de lijst naar het postvak en de OneDrive voor Bedrijven-site zoekt, met behulp van de zoekquery die u opvraagt.
  
## <a name="permissions-and-script-information"></a>Machtigingen en scriptgegevens

- U moet lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum en een globale beheerder van SharePoint Online om het script uit te voeren in stap 3.

- Zorg ervoor dat u de lijst met gebruikers die u maakt in stap 2 en het script in stap 3 in dezelfde map opgeslagen. Dit maakt het eenvoudiger om het script uit te voeren.

- Het script bevat minimale foutafhandeling. Het primaire doel is om snel en eenvoudig te zoeken in het postvak OneDrive voor Bedrijven site van elke gebruiker.

- De voorbeeldscripts in dit onderwerp worden niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft. De voorbeeldscripts worden zonder enige garantie ONGEWIJZIGD verstrekt. Microsoft wijst alle impliciete garanties met inbegrip van, maar niet beperkt tot, impliciete garanties van verkoopbaarheid en geschiktheid voor een bepaald doel af. Het risico dat ontstaat als gevolg van het gebruik of prestaties van de voorbeeldscripts ligt geheel bij u. In geen geval kan Microsoft, haar auteurs of anderen die bij het maken, produceren of leveren van de scripts zijn betrokken, aansprakelijk worden gehouden voor enige schade om welke reden dan ook (met inbegrip van maar niet beperkt tot schade door verlies van bedrijfswinsten, belemmering van de bedrijfsuitvoering, verlies van bedrijfsinformatie of andere geldelijke verliezen) voortvloeiend uit het gebruik of de onmogelijkheid van het gebruik van de voorbeeldscripts, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Stap 1: De SharePoint Online Management Shell installeren

De eerste stap is het installeren van de SharePoint Online Management Shell. U hoeft de shell niet te gebruiken in deze procedure, maar u moet deze installeren omdat deze vereisten bevat die vereist zijn voor het script dat u in stap 3 uit te voeren. Met deze vereisten kan het script communiceren met SharePoint Online om de URL's voor de OneDrive voor Bedrijven krijgen.
  
Ga naar [De SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) Windows PowerShell en voer stap 1 en stap 2 uit om de SharePoint Online Management Shell te installeren.
  
## <a name="step-2-generate-a-list-of-users"></a>Stap 2: Een lijst met gebruikers genereren

Met het script in stap 3 wordt een inhoudszoekactie gemaakt om te zoeken in de postvakken en OneDrive accounts voor een lijst met gebruikers. U kunt alleen de e-mailadressen in een tekstbestand typen of u kunt een opdracht uitvoeren in Windows PowerShell om een lijst met e-mailadressen op te halen en deze op te slaan in een bestand (in dezelfde map waarin u het script in stap 3 op wilt slaan).
  
Hier ziet u [een Exchange Online PowerShell-opdracht](/powershell/exchange/connect-to-exchange-online-powershell) die u kunt uitvoeren om een lijst met e-mailadressen te krijgen voor alle gebruikers in uw organisatie en deze op te slaan in een tekstbestand met de naam `Users.txt` . 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

Nadat u deze opdracht hebt uitgevoerd, moet u het bestand openen en de koptekst met de eigenschapsnaam  `PrimarySmtpAddress` verwijderen. Het tekstbestand moet alleen een lijst met e-mailadressen bevatten en verder niets. Zorg ervoor dat er geen lege rijen zijn voor of na de lijst met e-mailadressen.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Stap 3: Het script uitvoeren om de zoekopdracht te maken en te starten

Wanneer u het script in deze stap uit te voeren, wordt u gevraagd om de volgende informatie. Zorg ervoor dat u deze informatie klaar hebt voordat u het script gaat uitvoeren.
  
- **Uw gebruikersreferenties:** het script gebruikt uw referenties om toegang te krijgen tot SharePoint Online om de OneDrive voor Bedrijven-URL's te krijgen en verbinding te maken met het Beveiligings- & Compliancecentrum met externe PowerShell. 
    
- **Naam van uw MySite-domein:** het domein MySite is het domein dat alle OneDrive voor Bedrijven sites in uw organisatie bevat. Als de URL voor uw MySite-domein bijvoorbeeld is, voert u deze in wanneer u in het script wordt gevraagd om de naam van uw **https://contoso-my.sharepoint.com**  `contoso` MySite-domein. 
    
- **Padnaam van het tekstbestand uit stap 2:** de padnaam van het tekstbestand dat u hebt gemaakt in stap 2. Als het tekstbestand en het script zich in dezelfde map bevinden, voert u de naam van het tekstbestand in. Voer anders de volledige padnaam voor het tekstbestand in. 
    
- **Naam van het zoeken naar inhoud:** de naam van het zoeken naar inhoud die door het script wordt gemaakt. 
    
- **Zoekquery:** de zoekquery die wordt gebruikt voor het zoeken naar inhoud, wordt gemaakt en uitgevoerd. Zie Trefwoordenquery's en zoekvoorwaarden voor Inhoud zoeken voor meer [informatie over zoekquery's.](keyword-queries-and-search-conditions.md)


**Het script uitvoeren:**
    
1. Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; `SearchEXOOD4B.ps1`bijvoorbeeld. Sla het bestand op in dezelfde map waarin u de lijst met gebruikers hebt opgeslagen in stap 2.
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. Open Windows PowerShell en ga naar de map waar u het script en de lijst met gebruikers hebt opgeslagen in stap 2.
    
3. Start het script; bijvoorbeeld:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. Wanneer u om uw referenties wordt gevraagd, voert u uw e-mailadres en wachtwoord in en klikt u op **OK.** 
    
5. Voer volgende informatie in wanneer u daarom wordt gevraagd door het script. Typ elk stukje informatie en druk op **Enter.**
    
    - De naam van uw MySite-domein. 
    
    - De padnaam van het tekstbestand dat de lijst met gebruikers bevat.
    
    - Een naam voor het zoeken naar inhoud.
    
    - De zoekquery (laat deze leeg om alle items in de inhoudslocaties te retourneren).
    
    Het script krijgt de URL's voor elke OneDrive voor Bedrijven site en maakt en start de zoekopdracht. U kunt de cmdlet **Get-ComplianceSearch** uitvoeren in Security & Compliance Center PowerShell om de zoekstatistieken  en resultaten weer te geven, of u kunt naar de pagina Zoeken naar inhoud gaan in het beveiligings- & compliancecentrum om informatie over de zoekopdracht weer te geven.