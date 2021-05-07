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
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="8c5c5-103">Inhoud zoeken gebruiken om in het postvak en OneDrive voor Bedrijven zoeken naar een lijst met gebruikers</span><span class="sxs-lookup"><span data-stu-id="8c5c5-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="8c5c5-104">Het Beveiligings- & compliancecentrum biedt een aantal Windows PowerShell cmdlets om tijdrovende eDiscovery-gerelateerde taken te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="8c5c5-105">Het maken van een inhoudszoekactie in het beveiligings- & compliancecentrum voor het zoeken naar een groot aantal bewaarlocaties voor inhoud kost tijd en voorbereiding.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="8c5c5-106">Voordat u een zoekopdracht maakt, moet u de URL voor elke OneDrive voor Bedrijven site verzamelen en vervolgens elk postvak en OneDrive voor Bedrijven aan de zoekopdracht toevoegen.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="8c5c5-107">In toekomstige versies is dit gemakkelijker te doen in het beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="8c5c5-108">Tot die tijd kunt u het script in dit artikel gebruiken om dit proces te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="8c5c5-109">In dit script wordt u gevraagd om de naam van het MySite-domein van uw organisatie (bijvoorbeeld **contoso** in de URL), een lijst met e-mailadressen van gebruikers, de naam van de nieuwe inhoudszoekactie en de zoekquery die u wilt `https://contoso-my.sharepoint.com` gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL `https://contoso-my.sharepoint.com`), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="8c5c5-110">Het script krijgt de OneDrive voor Bedrijven-URL voor elke gebruiker in de lijst en vervolgens wordt er een inhoudszoekactie gemaakt en gestart die voor elke gebruiker in de lijst naar het postvak en de OneDrive voor Bedrijven-site zoekt, met behulp van de zoekquery die u opvraagt.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span>
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="8c5c5-111">Machtigingen en scriptgegevens</span><span class="sxs-lookup"><span data-stu-id="8c5c5-111">Permissions and script information</span></span>

- <span data-ttu-id="8c5c5-112">U moet lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum en een globale beheerder van SharePoint Online om het script uit te voeren in stap 3.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>

- <span data-ttu-id="8c5c5-113">Zorg ervoor dat u de lijst met gebruikers die u maakt in stap 2 en het script in stap 3 in dezelfde map opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="8c5c5-114">Dit maakt het eenvoudiger om het script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-114">That will make it easier to run the script.</span></span>

- <span data-ttu-id="8c5c5-115">Het script bevat minimale foutafhandeling.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-115">The script includes minimal error handling.</span></span> <span data-ttu-id="8c5c5-116">Het primaire doel is om snel en eenvoudig te zoeken in het postvak OneDrive voor Bedrijven site van elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-116">Its primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>

- <span data-ttu-id="8c5c5-117">De voorbeeldscripts in dit onderwerp worden niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-117">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="8c5c5-118">De voorbeeldscripts worden geleverd als IS zonder enige garantie.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-118">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="8c5c5-119">Microsoft wijst alle impliciete garanties verder af, inclusief, zonder beperking, impliciete garanties van verkoopbaarheid of geschiktheid voor een bepaald doel.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-119">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="8c5c5-120">Het volledige risico dat voortvloeit uit het gebruik of de prestaties van de voorbeeldscripts en documentatie blijft bij u.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-120">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="8c5c5-121">In geen geval zijn Microsoft, de auteurs of anderen die betrokken zijn bij het maken, produceren of leveren van de scripts aansprakelijk voor enige schade (met inbegrip van, zonder beperking, schade voor verlies van bedrijfswinsten, bedrijfsonderbreking, verlies van bedrijfsgegevens of ander geldverlies) als gevolg van het gebruik van of het onvermogen om de voorbeeldscripts of documentatie te gebruiken, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-121">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="8c5c5-122">Stap 1: De SharePoint Online Management Shell installeren</span><span class="sxs-lookup"><span data-stu-id="8c5c5-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="8c5c5-123">De eerste stap is het installeren van de SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="8c5c5-124">U hoeft de shell niet te gebruiken in deze procedure, maar u moet deze installeren omdat deze vereisten bevat die vereist zijn voor het script dat u in stap 3 uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="8c5c5-125">Met deze vereisten kan het script communiceren met SharePoint Online om de URL's voor de OneDrive voor Bedrijven krijgen.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="8c5c5-126">Ga naar [De SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) Windows PowerShell en voer stap 1 en stap 2 uit om de SharePoint Online Management Shell te installeren.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="8c5c5-127">Stap 2: Een lijst met gebruikers genereren</span><span class="sxs-lookup"><span data-stu-id="8c5c5-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="8c5c5-128">Met het script in stap 3 wordt een inhoudszoekactie gemaakt om te zoeken in de postvakken en OneDrive accounts voor een lijst met gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="8c5c5-129">U kunt alleen de e-mailadressen in een tekstbestand typen of u kunt een opdracht uitvoeren in Windows PowerShell om een lijst met e-mailadressen op te halen en deze op te slaan in een bestand (in dezelfde map waarin u het script in stap 3 op wilt slaan).</span><span class="sxs-lookup"><span data-stu-id="8c5c5-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="8c5c5-130">Hier ziet u [een Exchange Online PowerShell-opdracht](/powershell/exchange/connect-to-exchange-online-powershell) die u kunt uitvoeren om een lijst met e-mailadressen te krijgen voor alle gebruikers in uw organisatie en deze op te slaan in een tekstbestand met de naam `Users.txt` .</span><span class="sxs-lookup"><span data-stu-id="8c5c5-130">Here's an [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="8c5c5-131">Nadat u deze opdracht hebt uitgevoerd, moet u het bestand openen en de koptekst met de eigenschapsnaam  `PrimarySmtpAddress` verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="8c5c5-132">Het tekstbestand moet alleen een lijst met e-mailadressen bevatten en verder niets.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="8c5c5-133">Zorg ervoor dat er geen lege rijen zijn voor of na de lijst met e-mailadressen.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="8c5c5-134">Stap 3: Het script uitvoeren om de zoekopdracht te maken en te starten</span><span class="sxs-lookup"><span data-stu-id="8c5c5-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="8c5c5-135">Wanneer u het script in deze stap uit te voeren, wordt u gevraagd om de volgende informatie.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="8c5c5-136">Zorg ervoor dat u deze informatie klaar hebt voordat u het script gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="8c5c5-137">**Uw gebruikersreferenties:** het script gebruikt uw referenties om toegang te krijgen tot SharePoint Online om de OneDrive voor Bedrijven-URL's te krijgen en verbinding te maken met het Beveiligings- & Compliancecentrum met externe PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="8c5c5-138">**Naam van uw MySite-domein:** het domein MySite is het domein dat alle OneDrive voor Bedrijven sites in uw organisatie bevat.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="8c5c5-139">Als de URL voor uw MySite-domein bijvoorbeeld is, voert u deze in wanneer u in het script wordt gevraagd om de naam van uw **https://contoso-my.sharepoint.com**  `contoso` MySite-domein.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="8c5c5-140">**Padnaam van het tekstbestand uit stap 2:** de padnaam van het tekstbestand dat u hebt gemaakt in stap 2.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="8c5c5-141">Als het tekstbestand en het script zich in dezelfde map bevinden, voert u de naam van het tekstbestand in.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="8c5c5-142">Voer anders de volledige padnaam voor het tekstbestand in.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="8c5c5-143">**Naam van het zoeken naar inhoud:** de naam van het zoeken naar inhoud die door het script wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="8c5c5-144">**Zoekquery:** de zoekquery die wordt gebruikt voor het zoeken naar inhoud, wordt gemaakt en uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="8c5c5-145">Zie Trefwoordenquery's en zoekvoorwaarden voor Inhoud zoeken voor meer [informatie over zoekquery's.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="8c5c5-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="8c5c5-146">**Het script uitvoeren:**</span><span class="sxs-lookup"><span data-stu-id="8c5c5-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="8c5c5-147">Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; `SearchEXOOD4B.ps1`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="8c5c5-148">Sla het bestand op in dezelfde map waarin u de lijst met gebruikers hebt opgeslagen in stap 2.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
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

2. <span data-ttu-id="8c5c5-149">Open Windows PowerShell en ga naar de map waar u het script en de lijst met gebruikers hebt opgeslagen in stap 2.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="8c5c5-150">Start het script; bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8c5c5-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="8c5c5-151">Wanneer u om uw referenties wordt gevraagd, voert u uw e-mailadres en wachtwoord in en klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="8c5c5-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="8c5c5-152">Voer volgende informatie in wanneer u daarom wordt gevraagd door het script.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="8c5c5-153">Typ elk stukje informatie en druk op **Enter.**</span><span class="sxs-lookup"><span data-stu-id="8c5c5-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="8c5c5-154">De naam van uw MySite-domein.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="8c5c5-155">De padnaam van het tekstbestand dat de lijst met gebruikers bevat.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="8c5c5-156">Een naam voor het zoeken naar inhoud.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="8c5c5-157">De zoekquery (laat deze leeg om alle items in de inhoudslocaties te retourneren).</span><span class="sxs-lookup"><span data-stu-id="8c5c5-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="8c5c5-158">Het script krijgt de URL's voor elke OneDrive voor Bedrijven site en maakt en start de zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="8c5c5-159">U kunt de cmdlet **Get-ComplianceSearch** uitvoeren in Security & Compliance Center PowerShell om de zoekstatistieken  en resultaten weer te geven, of u kunt naar de pagina Zoeken naar inhoud gaan in het beveiligings- & compliancecentrum om informatie over de zoekopdracht weer te geven.</span><span class="sxs-lookup"><span data-stu-id="8c5c5-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span>