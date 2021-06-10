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
# <a name="clone-a-content-search"></a><span data-ttu-id="47bdd-103">Een inhoudszoekactie kloonen</span><span class="sxs-lookup"><span data-stu-id="47bdd-103">Clone a Content Search</span></span>

<span data-ttu-id="47bdd-104">Het kan even duren voordat u een inhoudszoekactie maakt in het compliancecentrum in Office 365 of Microsoft 365 waarin veel postvakken of SharePoint en OneDrive voor Bedrijven worden doorzocht.</span><span class="sxs-lookup"><span data-stu-id="47bdd-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="47bdd-105">Als u de sites opgeeft die u wilt zoeken, kunnen er ook fouten optreden als u een URL verkeerd typt.</span><span class="sxs-lookup"><span data-stu-id="47bdd-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="47bdd-106">Als u deze problemen wilt voorkomen, kunt u het script Windows PowerShell in dit artikel gebruiken om snel een bestaande inhoudszoekactie te kloonen.</span><span class="sxs-lookup"><span data-stu-id="47bdd-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="47bdd-107">Wanneer u een zoekopdracht kloont, wordt er een nieuwe zoekopdracht (met een andere naam) gemaakt die dezelfde eigenschappen (zoals de inhoudslocaties en de zoekquery) bevat als de oorspronkelijke zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="47bdd-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="47bdd-108">Vervolgens kunt u de nieuwe zoekopdracht bewerken door de trefwoordquery of het datumbereik te wijzigen en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="47bdd-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="47bdd-109">Waarom worden inhoudszoekingen gekloond?</span><span class="sxs-lookup"><span data-stu-id="47bdd-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="47bdd-110">Als u de resultaten van verschillende zoekquery's voor trefwoorden op dezelfde inhoudslocaties wilt vergelijken.</span><span class="sxs-lookup"><span data-stu-id="47bdd-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="47bdd-111">Als u wilt besparen dat u een groot aantal inhoudslocaties opnieuw moet in- en uiten wanneer u een nieuwe zoekopdracht maakt.</span><span class="sxs-lookup"><span data-stu-id="47bdd-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="47bdd-112">Om de grootte van de zoekresultaten te verminderen.</span><span class="sxs-lookup"><span data-stu-id="47bdd-112">To decrease the size of the search results.</span></span> <span data-ttu-id="47bdd-113">Als u bijvoorbeeld een zoekopdracht hebt die te veel resultaten retourneert om te exporteren, kunt u de zoekopdracht kloonen en vervolgens een zoekvoorwaarde toevoegen op basis van een datumbereik om het aantal zoekresultaten te verminderen.</span><span class="sxs-lookup"><span data-stu-id="47bdd-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="47bdd-114">Scriptgegevens</span><span class="sxs-lookup"><span data-stu-id="47bdd-114">Script information</span></span>

- <span data-ttu-id="47bdd-115">U moet lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum om het script uit te voeren dat in dit onderwerp wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="47bdd-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="47bdd-116">Het script bevat minimale foutafhandeling.</span><span class="sxs-lookup"><span data-stu-id="47bdd-116">The script includes minimal error handling.</span></span> <span data-ttu-id="47bdd-117">Het primaire doel van het script is om snel een inhoudszoekactie te kloonen.</span><span class="sxs-lookup"><span data-stu-id="47bdd-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="47bdd-118">Met het script wordt een nieuwe inhoudszoekactie gemaakt, maar deze wordt niet gestart.</span><span class="sxs-lookup"><span data-stu-id="47bdd-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="47bdd-119">In dit script wordt rekening gehouden met de vraag of het zoeken naar inhoud dat u kloont, is gekoppeld aan een eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="47bdd-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="47bdd-120">Als de zoekopdracht is gekoppeld aan een zaak, wordt de nieuwe zoekopdracht ook gekoppeld aan hetzelfde geval.</span><span class="sxs-lookup"><span data-stu-id="47bdd-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="47bdd-121">Als de bestaande zoekopdracht niet aan een zaak is gekoppeld,  wordt de nieuwe zoekopdracht weergegeven op de pagina Inhoud zoeken in het compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="47bdd-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="47bdd-122">Het voorbeeldscript in dit onderwerp wordt niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47bdd-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="47bdd-123">Het voorbeeldscripts wordt zonder enige garantie ONGEWIJZIGD verstrekt.</span><span class="sxs-lookup"><span data-stu-id="47bdd-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="47bdd-124">Microsoft wijst alle impliciete garanties met inbegrip van, maar niet beperkt tot, impliciete garanties van verkoopbaarheid en geschiktheid voor een bepaald doel af.</span><span class="sxs-lookup"><span data-stu-id="47bdd-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="47bdd-125">Het risico dat ontstaat als gevolg van het gebruik of prestaties van het voorbeeldscript ligt geheel bij u.</span><span class="sxs-lookup"><span data-stu-id="47bdd-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="47bdd-126">In geen geval kan Microsoft, haar auteurs of anderen die bij het maken, produceren of leveren van de scripts zijn betrokken, aansprakelijk worden gehouden voor enige schade om welke reden dan ook (met inbegrip van maar niet beperkt tot schade door verlies van bedrijfswinsten, belemmering van de bedrijfsuitvoering, verlies van bedrijfsinformatie of andere geldelijke verliezen) voortvloeiend uit het gebruik of de onmogelijkheid van het gebruik van de voorbeeldscripts, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.</span><span class="sxs-lookup"><span data-stu-id="47bdd-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="47bdd-127">Stap 1: Het script uitvoeren om een zoekopdracht te kloonen</span><span class="sxs-lookup"><span data-stu-id="47bdd-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="47bdd-128">Met het script in deze stap wordt een nieuwe inhoudszoekactie gemaakt door een bestaand script te klonen.</span><span class="sxs-lookup"><span data-stu-id="47bdd-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="47bdd-129">Wanneer u dit script uit te voeren, wordt u gevraagd om de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="47bdd-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="47bdd-130">**Uw gebruikersreferenties:** het script gebruikt uw referenties om verbinding te maken met het beveiligings- & compliancecentrum voor uw organisatie met Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47bdd-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="47bdd-131">Zoals eerder vermeld, moet u lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum om het script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="47bdd-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="47bdd-132">**De naam van de bestaande zoekopdracht:** dit is de inhoudszoekactie die u wilt klonen.</span><span class="sxs-lookup"><span data-stu-id="47bdd-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="47bdd-133">**De naam** van de nieuwe zoekopdracht die wordt gemaakt: als u deze waarde leeg laat, wordt in het script een naam gemaakt voor de nieuwe zoekopdracht die is gebaseerd op de naam van de zoekopdracht die u kloont.</span><span class="sxs-lookup"><span data-stu-id="47bdd-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="47bdd-134">Een zoekopdracht kloonen:</span><span class="sxs-lookup"><span data-stu-id="47bdd-134">To clone a search:</span></span>
  
1. <span data-ttu-id="47bdd-135">Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; `CloneSearch.ps1`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="47bdd-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="47bdd-136">Open Windows PowerShell en ga naar de map waar u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="47bdd-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="47bdd-137">Voer het script uit; bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="47bdd-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="47bdd-138">Wanneer u om uw referenties wordt gevraagd, voert u uw e-mailadres en wachtwoord in en klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="47bdd-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="47bdd-139">Voer volgende informatie in wanneer u daarom wordt gevraagd door het script.</span><span class="sxs-lookup"><span data-stu-id="47bdd-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="47bdd-140">Typ elk stukje informatie en druk op **Enter.**</span><span class="sxs-lookup"><span data-stu-id="47bdd-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="47bdd-141">De naam van de bestaande zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="47bdd-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="47bdd-142">De naam van de nieuwe zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="47bdd-142">The name of the new search.</span></span>
    
    <span data-ttu-id="47bdd-143">Met het script wordt het nieuwe zoeken naar inhoud gemaakt, maar wordt het niet gestart.</span><span class="sxs-lookup"><span data-stu-id="47bdd-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="47bdd-144">Dit geeft u de mogelijkheid om de zoekopdracht in de volgende stap te bewerken en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="47bdd-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="47bdd-145">U kunt de eigenschappen van de nieuwe zoekactie bekijken door de **cmdlet Get-ComplianceSearch** uit te werken of door naar de pagina Inhoud zoeken of **eDiscovery** in het compliancecentrum te gaan, afhankelijk van of de nieuwe zoekopdracht is gekoppeld aan een zaak. </span><span class="sxs-lookup"><span data-stu-id="47bdd-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="47bdd-146">Stap 2: De gekloonde zoekopdracht bewerken en uitvoeren in het compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="47bdd-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="47bdd-147">Nadat u het script hebt uitgevoerd om een bestaande inhoudszoekactie te kloonen, gaat u naar het compliancecentrum om de nieuwe zoekopdracht te bewerken en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="47bdd-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="47bdd-148">Zoals eerder vermeld, kunt u een zoekopdracht bewerken door de trefwoordzoekquery te wijzigen en zoekvoorwaarden toe te voegen of te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="47bdd-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="47bdd-149">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="47bdd-149">For more information, see:</span></span>
  
- [<span data-ttu-id="47bdd-150">Inhoud zoeken in Office 365 </span><span class="sxs-lookup"><span data-stu-id="47bdd-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="47bdd-151">Trefwoordquery's en zoekvoorwaarden voor Zoeken naar inhoud</span><span class="sxs-lookup"><span data-stu-id="47bdd-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="47bdd-152">eDiscovery-zaken</span><span class="sxs-lookup"><span data-stu-id="47bdd-152">eDiscovery cases</span></span>](./get-started-core-ediscovery.md)