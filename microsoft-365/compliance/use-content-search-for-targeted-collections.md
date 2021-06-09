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
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="8ae64-103">Inhoud zoeken gebruiken voor gerichte verzamelingen</span><span class="sxs-lookup"><span data-stu-id="8ae64-103">Use Content search for targeted collections</span></span>

<span data-ttu-id="8ae64-104">Het zoekprogramma Inhoud in het Microsoft 365 compliancecentrum biedt geen directe manier in de gebruikersinterface om specifieke mappen te zoeken in Exchange postvakken of SharePoint en OneDrive voor Bedrijven sites.</span><span class="sxs-lookup"><span data-stu-id="8ae64-104">The Content search tool in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="8ae64-105">Het is echter mogelijk om specifieke mappen (een gerichte verzameling *genoemd)* te doorzoeken door de eigenschap Map-id op te geven voor de eigenschap e-mail of pad (DocumentLink) voor sites in de syntaxis van de werkelijke zoekquery.</span><span class="sxs-lookup"><span data-stu-id="8ae64-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="8ae64-106">Het gebruik van Inhoud zoeken om een gerichte verzameling uit te voeren is handig als u zeker weet dat items die reageren op een zaak of bevoorrechte items zich bevinden in een specifiek postvak of sitemap.</span><span class="sxs-lookup"><span data-stu-id="8ae64-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="8ae64-107">U kunt het script in dit artikel gebruiken om de map-id te verkrijgen voor postvakmappen of het pad (DocumentLink) voor mappen op een SharePoint en OneDrive voor Bedrijven site.</span><span class="sxs-lookup"><span data-stu-id="8ae64-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="8ae64-108">Vervolgens kunt u de map-id of het pad in een zoekquery gebruiken om items in de map te retourneren.</span><span class="sxs-lookup"><span data-stu-id="8ae64-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="8ae64-109">Als u inhoud wilt retourneren in een map op een SharePoint of OneDrive voor Bedrijven site, gebruikt het script in dit onderwerp de beheerde eigenschap DocumentLink in plaats van de eigenschap Pad.</span><span class="sxs-lookup"><span data-stu-id="8ae64-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="8ae64-110">De eigenschap DocumentLink is krachtiger dan de eigenschap Pad, omdat hierdoor alle inhoud in een map wordt retourneren, terwijl sommige mediabestanden niet worden teruggeslagen met de eigenschap Pad.</span><span class="sxs-lookup"><span data-stu-id="8ae64-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="8ae64-111">Voordat u een gerichte verzameling uit te voeren</span><span class="sxs-lookup"><span data-stu-id="8ae64-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="8ae64-112">U moet lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum om het script uit te voeren in stap 1.</span><span class="sxs-lookup"><span data-stu-id="8ae64-112">You have to be a member of the eDiscovery Manager role group in Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="8ae64-113">Zie [eDiscovery-machtigingen toewijzen](assign-ediscovery-permissions.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8ae64-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="8ae64-114">U moet ook de rol E-mailontvangers in uw Exchange Online toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8ae64-114">You also have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="8ae64-115">Dit is vereist voor het uitvoeren van **de cmdlet Get-MailboxFolderStatistics,** die is opgenomen in het script.</span><span class="sxs-lookup"><span data-stu-id="8ae64-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="8ae64-116">Standaard wordt de rol E-mailontvangers toegewezen aan de rollengroepen Organisatiebeheer en Geadresseerdenbeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8ae64-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="8ae64-117">Zie Leden van rollengroep beheren voor meer informatie over het toewijzen van machtigingen in [Exchange Online.](/exchange/manage-role-group-members-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="8ae64-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](/exchange/manage-role-group-members-exchange-2013-help).</span></span> <span data-ttu-id="8ae64-118">U kunt ook een aangepaste rollengroep maken, de rol E-mailontvangers hieraan toewijzen en vervolgens de leden toevoegen die het script moeten uitvoeren in stap 1.</span><span class="sxs-lookup"><span data-stu-id="8ae64-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="8ae64-119">Zie Rollengroepen [beheren voor meer informatie.](/Exchange/permissions-exo/role-groups)</span><span class="sxs-lookup"><span data-stu-id="8ae64-119">For more information, see [Manage role groups](/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="8ae64-120">Het script in dit artikel ondersteunt moderne verificatie.</span><span class="sxs-lookup"><span data-stu-id="8ae64-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="8ae64-121">U kunt het script gewoon gebruiken als u een Microsoft 365 of een Microsoft 365 GCC organisatie.</span><span class="sxs-lookup"><span data-stu-id="8ae64-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="8ae64-122">Als u een organisatie Office 365 Duitsland, een Microsoft 365 GCC Hoge organisatie of een Microsoft 365 DoD-organisatie bent, moet u het script bewerken om het uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8ae64-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="8ae64-123">U moet de lijn bewerken en de `Connect-ExchangeOnline` *parameter ExchangeEnvironmentName* (en de juiste waarde voor uw organisatietype) gebruiken om verbinding te maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ae64-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="8ae64-124">U moet ook de regel bewerken en de `Connect-IPPSSession` parameters *ConnectionUri* en *AzureADAuthorizationEndpointUri* (en de juiste waarden voor uw organisatietype) gebruiken om verbinding te maken met Security & Compliance Center PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ae64-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="8ae64-125">Zie voor meer informatie de voorbeelden in Verbinding maken powershell Exchange Online [powershell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) en Verbinding maken beveiligings- & [Compliance center PowerShell.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)</span><span class="sxs-lookup"><span data-stu-id="8ae64-125">For more information, see the examples in [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="8ae64-126">Telkens wanneer u het script uit te voeren, wordt er een nieuwe externe PowerShell-sessie gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8ae64-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="8ae64-127">Dat betekent dat u alle externe PowerShell-sessies kunt gebruiken die voor u beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="8ae64-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="8ae64-128">Als u dit wilt voorkomen, kunt u de volgende opdracht uitvoeren om de actieve externe PowerShell-sessies los te koppelen.</span><span class="sxs-lookup"><span data-stu-id="8ae64-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="8ae64-129">Zie powerShell Verbinding maken [Exchange Online voor meer informatie.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8ae64-129">For more information, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="8ae64-130">Het script bevat minimale foutafhandeling.</span><span class="sxs-lookup"><span data-stu-id="8ae64-130">The script includes minimal error handling.</span></span> <span data-ttu-id="8ae64-131">Het primaire doel van het script is om snel een lijst met postvakmap-ed's of sitepaden weer te geven die kunnen worden gebruikt in de syntaxis van de zoekquery van een inhoudszoekactie om een gerichte verzameling uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8ae64-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="8ae64-132">Het voorbeeldscript in dit onderwerp wordt niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ae64-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="8ae64-133">Het voorbeeldscripts wordt zonder enige garantie ONGEWIJZIGD verstrekt.</span><span class="sxs-lookup"><span data-stu-id="8ae64-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="8ae64-134">Microsoft wijst alle impliciete garanties met inbegrip van, maar niet beperkt tot, impliciete garanties van verkoopbaarheid en geschiktheid voor een bepaald doel af.</span><span class="sxs-lookup"><span data-stu-id="8ae64-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="8ae64-135">Het risico dat ontstaat als gevolg van het gebruik of prestaties van het voorbeeldscript ligt geheel bij u.</span><span class="sxs-lookup"><span data-stu-id="8ae64-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="8ae64-136">In geen geval kan Microsoft, haar auteurs of anderen die bij het maken, produceren of leveren van de scripts zijn betrokken, aansprakelijk worden gehouden voor enige schade om welke reden dan ook (met inbegrip van maar niet beperkt tot schade door verlies van bedrijfswinsten, belemmering van de bedrijfsuitvoering, verlies van bedrijfsinformatie of andere geldelijke verliezen) voortvloeiend uit het gebruik of de onmogelijkheid van het gebruik van de voorbeeldscripts, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.</span><span class="sxs-lookup"><span data-stu-id="8ae64-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="8ae64-137">Stap 1: Voer het script uit om een lijst met mappen voor een postvak of site te krijgen</span><span class="sxs-lookup"><span data-stu-id="8ae64-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="8ae64-138">Het script dat u in deze eerste stap hebt uitgevoerd, retourneert een lijst met postvakmappen of SharePoint- en OneDrive voor Bedrijven-mappen en de bijbehorende map-id of het bijbehorende pad voor elke map.</span><span class="sxs-lookup"><span data-stu-id="8ae64-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="8ae64-139">Wanneer u dit script uit te voeren, wordt u gevraagd om de volgende informatie.</span><span class="sxs-lookup"><span data-stu-id="8ae64-139">When you run this script, it will prompt you for the following information.</span></span>

- <span data-ttu-id="8ae64-140">**E-mailadres of site-URL:** Typ een e-mailadres van de bewaarder om een lijst met Exchange postvakmappen en map-eds te retourneren.</span><span class="sxs-lookup"><span data-stu-id="8ae64-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="8ae64-141">Of typ de URL voor een SharePoint site of OneDrive voor Bedrijven site om een lijst met paden voor de opgegeven site te retourneren.</span><span class="sxs-lookup"><span data-stu-id="8ae64-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="8ae64-142">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="8ae64-142">Here are some examples:</span></span>

  - <span data-ttu-id="8ae64-143">**Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com</span><span class="sxs-lookup"><span data-stu-id="8ae64-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="8ae64-144">**SharePoint**: https <span>://</span>contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="8ae64-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span>

  - <span data-ttu-id="8ae64-145">**OneDrive voor Bedrijven**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="8ae64-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span>

- <span data-ttu-id="8ae64-146">**Uw gebruikersreferenties:** het script gebruikt uw referenties om verbinding te maken met Exchange Online PowerShell of & Compliance center PowerShell met moderne verificatie.</span><span class="sxs-lookup"><span data-stu-id="8ae64-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="8ae64-147">Zoals eerder is uitgelegd, moet u de juiste machtigingen krijgen om dit script te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="8ae64-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="8ae64-148">Een lijst met postvakmappen of sitedocumentlinknamen (padnamen) weergeven:</span><span class="sxs-lookup"><span data-stu-id="8ae64-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>

1. <span data-ttu-id="8ae64-149">Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; `GetFolderSearchParameters.ps1`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8ae64-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

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

2. <span data-ttu-id="8ae64-150">Open op uw lokale computer Windows PowerShell en ga naar de map waar u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="8ae64-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="8ae64-151">Voer het script uit; bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8ae64-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="8ae64-152">Voer de informatie in waar u om wordt gevraagd in het script.</span><span class="sxs-lookup"><span data-stu-id="8ae64-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="8ae64-153">In het script wordt een lijst weergegeven met postvakmappen of sitemappen voor de opgegeven gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8ae64-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="8ae64-154">Laat dit venster open zodat u een map-id of documentlinknaam kunt kopiëren en deze kunt plakken in een zoekquery in stap 2.</span><span class="sxs-lookup"><span data-stu-id="8ae64-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="8ae64-155">In plaats van een lijst met mappen weer te geven op het computerscherm, kunt u de uitvoer van het script opnieuw naar een tekstbestand leiden.</span><span class="sxs-lookup"><span data-stu-id="8ae64-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="8ae64-156">Dit bestand wordt opgeslagen in de map waar het script zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="8ae64-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="8ae64-157">Als u bijvoorbeeld de uitvoer van het script wilt omleiden naar een tekstbestand, kunt u de volgende opdracht uitvoeren in stap 3: Vervolgens kunt u een map-id of documentlink uit het bestand kopiëren om te gebruiken in een  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` zoekquery.</span><span class="sxs-lookup"><span data-stu-id="8ae64-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>

### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="8ae64-158">Scriptuitvoer voor postvakmappen</span><span class="sxs-lookup"><span data-stu-id="8ae64-158">Script output for mailbox folders</span></span>

<span data-ttu-id="8ae64-159">Als u postvakmap-ID's krijgt, wordt het script verbonden met Exchange Online PowerShell, wordt de cmdlet **Get-MailboxFolderStatisics** uitgevoerd en wordt vervolgens de lijst met de mappen uit het opgegeven postvak weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8ae64-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="8ae64-160">Voor elke map in het postvak worden in het script de naam van de map weergegeven in de kolom **MapPath** en de map-id in de kolom **FolderQuery.**</span><span class="sxs-lookup"><span data-stu-id="8ae64-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="8ae64-161">Bovendien voegt het script het voorvoegsel **mapId** (de naam van de eigenschap postvak) toe aan de map-id.</span><span class="sxs-lookup"><span data-stu-id="8ae64-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="8ae64-162">Omdat de **eigenschap mapid** een doorzoekbare eigenschap is, gebruikt u in een zoekquery in stap 2 om  `folderid:<folderid>` in die map te zoeken.</span><span class="sxs-lookup"><span data-stu-id="8ae64-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="8ae64-163">In het script worden maximaal 100 postvakmappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8ae64-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ae64-164">Het script in dit artikel bevat coderingslogica die de id-waarden van de map Met 64 tekens converteert die door **Get-MailboxFolderStatistics** worden geretourneerd naar dezelfde indeling met 48 tekens die wordt geïndexeerd voor zoeken.</span><span class="sxs-lookup"><span data-stu-id="8ae64-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="8ae64-165">Als u alleen de **cmdlet Get-MailboxFolderStatistics** in PowerShell uitvoert om een map-id te verkrijgen (in plaats van het script in dit artikel uit te voeren), mislukt een zoekquery waarin die map-id-waarde wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8ae64-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="8ae64-166">U moet het script uitvoeren om de correct opgemaakte map-id's te krijgen die kunnen worden gebruikt in een inhoudszoekactie.</span><span class="sxs-lookup"><span data-stu-id="8ae64-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>

<span data-ttu-id="8ae64-167">Hier is een voorbeeld van de uitvoer die wordt geretourneerd door het script voor postvakmappen.</span><span class="sxs-lookup"><span data-stu-id="8ae64-167">Here's an example of the output returned by the script for mailbox folders.</span></span>

![Voorbeeld van de lijst met postvakmappen en map-ID's die door het script worden geretourneerd](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

<span data-ttu-id="8ae64-169">In het voorbeeld in stap 2 ziet u de query die wordt gebruikt om te zoeken in de submap Purges in de map Herstelbare items van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8ae64-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>

### <a name="script-output-for-site-folders"></a><span data-ttu-id="8ae64-170">Scriptuitvoer voor sitemappen</span><span class="sxs-lookup"><span data-stu-id="8ae64-170">Script output for site folders</span></span>

<span data-ttu-id="8ae64-171">Als u het pad van de **eigenschap documentlink** krijgt van SharePoint- of OneDrive voor Bedrijven-sites, wordt het script verbonden met Security & Compliance PowerShell, wordt er een nieuwe inhoudszoekactie gemaakt die op de site naar mappen zoekt en wordt vervolgens een lijst weergegeven met de mappen op de opgegeven site.</span><span class="sxs-lookup"><span data-stu-id="8ae64-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="8ae64-172">In het script wordt de naam van elke map weergegeven en wordt het voorvoegsel **van documentlink** toegevoegd aan de MAP-URL.</span><span class="sxs-lookup"><span data-stu-id="8ae64-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="8ae64-173">Omdat de **eigenschap documentlink** een doorzoekbare eigenschap is, gebruikt u eigenschap:waardepaar in een zoekquery in stap 2 om in `documentlink:<path>` die map te zoeken.</span><span class="sxs-lookup"><span data-stu-id="8ae64-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="8ae64-174">In het script worden maximaal 200 sitemappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8ae64-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="8ae64-175">Als er meer dan 200 sitemappen zijn, worden de nieuwste mappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8ae64-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>

<span data-ttu-id="8ae64-176">Hier is een voorbeeld van de uitvoer die wordt geretourneerd door het script voor sitemappen.</span><span class="sxs-lookup"><span data-stu-id="8ae64-176">Here's an example of the output returned by the script for site folders.</span></span>

![Voorbeeld van de lijst met documentlinknamen voor sitemappen die door het script worden geretourneerd](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="8ae64-178">Stap 2: Een map-id of documentlink gebruiken om een gerichte verzameling uit te voeren</span><span class="sxs-lookup"><span data-stu-id="8ae64-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="8ae64-179">Nadat u het script hebt uitgevoerd om een lijst met map-1D's of documentkoppelingen voor een specifieke gebruiker te verzamelen, gaat u naar het compliancecentrum van Microsoft 365 en maakt u een nieuwe inhoudszoekactie om in een specifieke map te zoeken.</span><span class="sxs-lookup"><span data-stu-id="8ae64-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="8ae64-180">U gebruikt het paar of eigenschap:waarde in de zoekquery die u configureert in het vak Trefwoord Inhoud zoeken (of als de waarde voor de  `folderid:<folderid>` parameter  `documentlink:<path>`  *ContentMatchQuery*  als u de **cmdlet New-ComplianceSearch** gebruikt).</span><span class="sxs-lookup"><span data-stu-id="8ae64-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="8ae64-181">U kunt de  `folderid`  `documentlink` of-eigenschap combineren met andere zoekparameters of zoekvoorwaarden.</span><span class="sxs-lookup"><span data-stu-id="8ae64-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="8ae64-182">Als u alleen de eigenschap of eigenschap in de query op neemt, worden alle items in de opgegeven map  `folderid`  `documentlink` als retourneert.</span><span class="sxs-lookup"><span data-stu-id="8ae64-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>

1. <span data-ttu-id="8ae64-183">Ga naar en meld u aan met het account en de referenties die u hebt gebruikt om het script uit te <https://compliance.microsoft.com> voeren in stap 1.</span><span class="sxs-lookup"><span data-stu-id="8ae64-183">Go to <https://compliance.microsoft.com> and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="8ae64-184">Klik in het linkerdeelvenster van het compliancecentrum op **Alle** inhoud  >  **zoeken weergeven** en klik vervolgens op Nieuwe **zoekopdracht.**</span><span class="sxs-lookup"><span data-stu-id="8ae64-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="8ae64-185">Plak in **het vak** Trefwoorden de of de waarde die is geretourneerd door het script in `folderid:<folderid>` stap  `documentlink:<path>` 1.</span><span class="sxs-lookup"><span data-stu-id="8ae64-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="8ae64-186">In de query in de volgende schermafbeelding wordt bijvoorbeeld gezocht naar een item in de submap Purges in de map Herstelbare items van de gebruiker (de waarde van de eigenschap voor de submap Purges wordt weergegeven in de `folderid` schermafbeelding in stap 1):</span><span class="sxs-lookup"><span data-stu-id="8ae64-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![De mapid of documentlink plakken in het trefwoordvak van de zoekquery](../media/FolderIDSearchQuery.png)

4. <span data-ttu-id="8ae64-188">Selecteer **onder** Locaties de optie **Specifieke locaties** en klik vervolgens op **Wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="8ae64-188">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="8ae64-189">Ga op een van de volgende stappen te werk, op basis van of u een postvakmap of een sitemap zoekt:</span><span class="sxs-lookup"><span data-stu-id="8ae64-189">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="8ae64-190">Klik naast **Exchange** e-mail op **Gebruikers,** groepen of teams kiezen en voeg vervolgens hetzelfde postvak toe dat u hebt opgegeven tijdens het uitvoeren van het script in stap 1.</span><span class="sxs-lookup"><span data-stu-id="8ae64-190">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="8ae64-191">Of</span><span class="sxs-lookup"><span data-stu-id="8ae64-191">Or</span></span>

    - <span data-ttu-id="8ae64-192">Klik naast **SharePoint sites** op Sites **kiezen** en voeg vervolgens dezelfde site-URL toe die u hebt opgegeven toen u het script in stap 1 uitliep.</span><span class="sxs-lookup"><span data-stu-id="8ae64-192">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="8ae64-193">Nadat u de inhoudslocatie hebt op opslaan om te zoeken, klikt u  op **Opslaan & uitvoeren,** typt u een naam voor het zoeken naar inhoud en klikt u vervolgens op Opslaan om de doelverzamelingszoekactie te starten.</span><span class="sxs-lookup"><span data-stu-id="8ae64-193">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span>

### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="8ae64-194">Voorbeelden van zoekquery's voor gerichte verzamelingen</span><span class="sxs-lookup"><span data-stu-id="8ae64-194">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="8ae64-195">Hier zijn enkele voorbeelden van het gebruik van de eigenschappen en eigenschappen  `folderid`  `documentlink` in een zoekquery om een gerichte verzameling uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8ae64-195">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="8ae64-196">Tijdelijke aanduidingen worden gebruikt voor  `folderid:<folderid>` en om ruimte te  `documentlink:<path>` besparen.</span><span class="sxs-lookup"><span data-stu-id="8ae64-196">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span>

- <span data-ttu-id="8ae64-197">In dit voorbeeld wordt gezocht in drie verschillende postvakmappen.</span><span class="sxs-lookup"><span data-stu-id="8ae64-197">This example searches three different mailbox folders.</span></span> <span data-ttu-id="8ae64-198">U kunt vergelijkbare query-syntaxis gebruiken om te zoeken in de verborgen mappen in de map Herstelbare items van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8ae64-198">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="8ae64-199">In dit voorbeeld wordt in een postvakmap gezocht naar items die een exacte woordgroep bevatten.</span><span class="sxs-lookup"><span data-stu-id="8ae64-199">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="8ae64-200">In dit voorbeeld wordt in een sitemap (en eventuele submappen) gezocht naar documenten met de letters 'NDA' in de titel.</span><span class="sxs-lookup"><span data-stu-id="8ae64-200">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="8ae64-201">In dit voorbeeld wordt in een sitemap (en een submap) gezocht naar documenten die binnen een datumbereik zijn gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8ae64-201">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="8ae64-202">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="8ae64-202">More information</span></span>

<span data-ttu-id="8ae64-203">Houd rekening met de volgende dingen wanneer u het script in dit artikel gebruikt om gerichte verzamelingen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8ae64-203">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>

- <span data-ttu-id="8ae64-204">Het script verwijdert geen mappen uit de resultaten.</span><span class="sxs-lookup"><span data-stu-id="8ae64-204">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="8ae64-205">Sommige mappen die in de resultaten worden vermeld, kunnen dus niet kunnen worden doorzocht (of nul items retourneren) omdat ze door het systeem gegenereerde inhoud bevatten of omdat ze alleen submappen bevatten en geen postvakitems.</span><span class="sxs-lookup"><span data-stu-id="8ae64-205">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="8ae64-206">Dit script retourneert alleen mapgegevens voor het primaire postvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8ae64-206">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="8ae64-207">Het retourneert geen informatie over mappen in het archiefpostvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8ae64-207">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="8ae64-208">Als u informatie over mappen in het archiefpostvak van de gebruiker wilt retourneren, kunt u het script bewerken.</span><span class="sxs-lookup"><span data-stu-id="8ae64-208">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="8ae64-209">U kunt dit doen door de regel te wijzigen in en vervolgens het bewerkte script op te slaan `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8ae64-209">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="8ae64-210">Deze wijziging retourneert de map-eds voor mappen en submappen in het archiefpostvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8ae64-210">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="8ae64-211">Als u het hele archiefpostvak wilt doorzoeken, kunt u alle map-id-eigenschappen:waardeparen verbinden met een `OR` operator in een zoekquery.</span><span class="sxs-lookup"><span data-stu-id="8ae64-211">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="8ae64-212">Bij het zoeken in postvakmappen wordt alleen gezocht naar de opgegeven map (die door de eigenschap wordt geïdentificeerd). Submappen worden niet `folderid` doorzocht.</span><span class="sxs-lookup"><span data-stu-id="8ae64-212">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="8ae64-213">Als u wilt zoeken in submappen, moet u de map-id gebruiken voor de submap die u wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="8ae64-213">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="8ae64-214">Wanneer u sitemappen zoekt, worden de map (geïdentificeerd door de eigenschap) en `documentlink` alle submappen doorzocht.</span><span class="sxs-lookup"><span data-stu-id="8ae64-214">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span>

- <span data-ttu-id="8ae64-215">Wanneer u de resultaten exporteert van een zoekopdracht waarin u alleen de eigenschap in de zoekquery hebt opgegeven, kunt u de eerste `folderid` exportoptie kiezen: 'Alle items, met uitzondering van items met een niet-herkende notatie, worden versleuteld of zijn om andere redenen niet geïndexeerd.'</span><span class="sxs-lookup"><span data-stu-id="8ae64-215">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="8ae64-216">Alle items in de map worden altijd geëxporteerd, ongeacht de indexeringsstatus, omdat de map-id altijd wordt geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="8ae64-216">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
