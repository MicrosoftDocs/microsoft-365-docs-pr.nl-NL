---
title: Meerdere inhoudszoekingen maken, rapporteren en verwijderen
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
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Lees hoe u inhoudszoektaken kunt automatiseren, zoals het maken van zoekopdrachten en het uitvoeren van rapporten via PowerShell-scripts in het Beveiligings- & compliancecentrum in Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6155a0bf411cc83fd58291efe7797e7f68370708
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/24/2021
ms.locfileid: "52162731"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="d5266-103">Meerdere inhoudszoekingen maken, rapporteren en verwijderen</span><span class="sxs-lookup"><span data-stu-id="d5266-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="d5266-104">Het snel maken en rapporteren van zoekopdrachten voor detecties is vaak een belangrijke stap in eDiscovery en onderzoeken wanneer u meer wilt weten over de onderliggende gegevens en de rijkdom en kwaliteit van uw zoekopdrachten.</span><span class="sxs-lookup"><span data-stu-id="d5266-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="d5266-105">Om u te helpen dit te doen, biedt & Security & Compliance Center PowerShell een set cmdlets om tijdrovende inhoudszoektaken te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="d5266-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="d5266-106">Deze scripts bieden een snelle en eenvoudige manier om een aantal zoekopdrachten te maken en vervolgens rapporten uit te voeren van de geschatte zoekresultaten die u kunnen helpen bij het bepalen van de hoeveelheid gegevens in kwestie.</span><span class="sxs-lookup"><span data-stu-id="d5266-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="d5266-107">U kunt de scripts ook gebruiken om verschillende versies van zoekopdrachten te maken om de resultaten te vergelijken die elk resultaat oplevert.</span><span class="sxs-lookup"><span data-stu-id="d5266-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="d5266-108">Met deze scripts kunt u uw gegevens snel en efficiënt identificeren en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d5266-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span>

## <a name="before-you-create-a-content-search"></a><span data-ttu-id="d5266-109">Voordat u een inhoudszoekactie maakt</span><span class="sxs-lookup"><span data-stu-id="d5266-109">Before you create a Content Search</span></span>

- <span data-ttu-id="d5266-110">U moet lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum om de scripts uit te voeren die in dit onderwerp worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="d5266-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span>

- <span data-ttu-id="d5266-111">Zie Een lijst maken met alle OneDrive-locaties in uw organisatie als u een lijst wilt verzamelen met de URL's voor de OneDrive voor Bedrijven-sites [in](/onedrive/list-onedrive-urls)uw organisatie die u kunt toevoegen aan het CSV-bestand in stap 1.</span><span class="sxs-lookup"><span data-stu-id="d5266-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls).</span></span>

- <span data-ttu-id="d5266-112">Sla alle bestanden die u in dit onderwerp maakt op in dezelfde map.</span><span class="sxs-lookup"><span data-stu-id="d5266-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="d5266-113">Dat maakt het gemakkelijker om de scripts uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d5266-113">That will make it easier to run the scripts.</span></span>

- <span data-ttu-id="d5266-114">De scripts bevatten minimale foutafhandeling.</span><span class="sxs-lookup"><span data-stu-id="d5266-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="d5266-115">Het primaire doel is om snel meerdere inhoudszoekingen te maken, te rapporteren en te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d5266-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>

- <span data-ttu-id="d5266-116">De voorbeeldscripts in dit onderwerp worden niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5266-116">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="d5266-117">De voorbeeldscripts worden geleverd als IS zonder enige garantie.</span><span class="sxs-lookup"><span data-stu-id="d5266-117">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="d5266-118">Microsoft wijst alle impliciete garanties verder af, inclusief, zonder beperking, impliciete garanties van verkoopbaarheid of geschiktheid voor een bepaald doel.</span><span class="sxs-lookup"><span data-stu-id="d5266-118">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="d5266-119">Het volledige risico dat voortvloeit uit het gebruik of de prestaties van de voorbeeldscripts en documentatie blijft bij u.</span><span class="sxs-lookup"><span data-stu-id="d5266-119">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="d5266-120">In geen geval zijn Microsoft, de auteurs of anderen die betrokken zijn bij het maken, produceren of leveren van de scripts aansprakelijk voor enige schade (met inbegrip van, zonder beperking, schade voor verlies van bedrijfswinsten, bedrijfsonderbreking, verlies van bedrijfsgegevens of ander geldverlies) als gevolg van het gebruik van of het onvermogen om de voorbeeldscripts of documentatie te gebruiken, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.</span><span class="sxs-lookup"><span data-stu-id="d5266-120">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="d5266-121">Stap 1: Een CSV-bestand maken met informatie over de zoekopdrachten die u wilt uitvoeren</span><span class="sxs-lookup"><span data-stu-id="d5266-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="d5266-122">Het door komma's gescheiden waardebestand (CSV) dat u in deze stap maakt, bevat een rij voor elke gebruiker die wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="d5266-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="d5266-123">U kunt zoeken in het Exchange Online postvak van de gebruiker (inclusief het archiefpostvak, als dit is ingeschakeld) en de OneDrive voor Bedrijven site.</span><span class="sxs-lookup"><span data-stu-id="d5266-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="d5266-124">U kunt ook zoeken in alleen het postvak of de OneDrive voor Bedrijven site.</span><span class="sxs-lookup"><span data-stu-id="d5266-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="d5266-125">U kunt ook zoeken op elke site in uw SharePoint Online-organisatie.</span><span class="sxs-lookup"><span data-stu-id="d5266-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="d5266-126">Met het script dat u in stap 3 hebt uitgevoerd, wordt een afzonderlijke zoekopdracht gemaakt voor elke rij in het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="d5266-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span>

1. <span data-ttu-id="d5266-127">Kopieer en plak de volgende tekst in een .txt met Kladblok.</span><span class="sxs-lookup"><span data-stu-id="d5266-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="d5266-128">Sla dit bestand op in een map op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="d5266-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="d5266-129">De andere scripts worden ook in deze map opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="d5266-129">You'll save the other scripts to this folder as well.</span></span>

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   <span data-ttu-id="d5266-130">De eerste rij of veldnamenrij van het bestand bevat de parameters die worden gebruikt door de cmdlet **New-ComplianceSearch** (in het script in stap 3) om een nieuwe inhoudszoekactie te maken.</span><span class="sxs-lookup"><span data-stu-id="d5266-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="d5266-131">Elke parameternaam wordt gescheiden door een komma.</span><span class="sxs-lookup"><span data-stu-id="d5266-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="d5266-132">Zorg ervoor dat er geen spaties in de veldnamenrij staan.</span><span class="sxs-lookup"><span data-stu-id="d5266-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="d5266-133">Elke rij onder de veldnamenrij vertegenwoordigt de parameterwaarden voor elke zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="d5266-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="d5266-134">Zorg ervoor dat u de tijdelijke aanduidingsgegevens in het CSV-bestand vervangt door uw werkelijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="d5266-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span>

2. <span data-ttu-id="d5266-135">Open het .txt in Excel en gebruik de gegevens in de volgende tabel om het bestand te bewerken met informatie voor elke zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="d5266-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span>

   ****

   |<span data-ttu-id="d5266-136">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5266-136">Parameter</span></span>|<span data-ttu-id="d5266-137">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d5266-137">Description</span></span>|
   |---|---|
   |`ExchangeLocation`|<span data-ttu-id="d5266-138">Het SMTP-adres van het postvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d5266-138">The SMTP address of the user's mailbox.</span></span>|
   |`SharePointLocation`|<span data-ttu-id="d5266-139">De URL voor de OneDrive voor Bedrijven site van de gebruiker of de URL voor een site in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d5266-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="d5266-140">Voor de URL voor OneDrive voor Bedrijven sites gebruikt u deze indeling: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` .</span><span class="sxs-lookup"><span data-stu-id="d5266-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="d5266-141">Bijvoorbeeld. `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="d5266-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>|
   |`ContentMatchQuery`|<span data-ttu-id="d5266-142">De zoekquery voor de zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="d5266-142">The search query for the search.</span></span> <span data-ttu-id="d5266-143">Zie Trefwoordenquery's en zoekvoorwaarden voor Inhoud zoeken voor meer informatie over het maken van [een zoekquery.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="d5266-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>|
   |`StartDate`|<span data-ttu-id="d5266-144">Voor e-mail is de datum op of na het ontvangen van een bericht door een geadresseerde of verzonden door de afzender.</span><span class="sxs-lookup"><span data-stu-id="d5266-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="d5266-145">Voor documenten op SharePoint of OneDrive voor Bedrijven sites, is de datum op of nadat een document voor het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d5266-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>|
   |`EndDate`|<span data-ttu-id="d5266-146">Voor e-mail is de datum op of vóór een bericht verzonden door een verzonden door de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d5266-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="d5266-147">Voor documenten op SharePoint of OneDrive voor Bedrijven sites, is de datum op of vóór een document voor het laatst gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d5266-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>|
   |

3. <span data-ttu-id="d5266-148">Sla het Excel bestand op als een CSV-bestand in een map op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="d5266-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="d5266-149">Het script dat u in stap 3 maakt, gebruikt de informatie in dit CSV-bestand om de zoekopdrachten te maken.</span><span class="sxs-lookup"><span data-stu-id="d5266-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span>

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="d5266-150">Stap 2: Verbinding maken beveiliging & Compliance center PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5266-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="d5266-151">De volgende stap is om verbinding te maken met Security & Compliance Center PowerShell voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d5266-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="d5266-152">Zie voor stapsgewijs instructies Verbinding maken [Beveiligingscentrum & PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="d5266-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="d5266-153">Stap 3: Het script uitvoeren om de zoekopdrachten te maken en te starten</span><span class="sxs-lookup"><span data-stu-id="d5266-153">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="d5266-154">Met het script in deze stap wordt een afzonderlijke inhoudszoekfunctie gemaakt voor elke rij in het CSV-bestand dat u in stap 1 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d5266-154">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="d5266-155">Wanneer u dit script uit te voeren, wordt u gevraagd om twee waarden:</span><span class="sxs-lookup"><span data-stu-id="d5266-155">When you run this script, you'll be prompted for two values:</span></span>

- <span data-ttu-id="d5266-156">**Groeps-id zoeken:** deze naam biedt een eenvoudige manier om de zoekopdrachten te organiseren die zijn gemaakt vanuit het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="d5266-156">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="d5266-157">Elke zoekopdracht die wordt gemaakt, wordt benoemd met de zoekgroep-id en vervolgens wordt een getal toegevoegd aan de zoeknaam.</span><span class="sxs-lookup"><span data-stu-id="d5266-157">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="d5266-158">Als u bijvoorbeeld **ContosoCase** voor de groep-id zoeken in typt, worden de zoekopdrachten benoemd **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, en ga zo maar door.</span><span class="sxs-lookup"><span data-stu-id="d5266-158">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="d5266-159">Houd er rekening mee dat de naam die u typt, casegevoelig is.</span><span class="sxs-lookup"><span data-stu-id="d5266-159">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="d5266-160">Wanneer u de groeps-id zoeken gebruikt in stap 4 en stap 5, moet u hetzelfde geval gebruiken als toen u deze maakte.</span><span class="sxs-lookup"><span data-stu-id="d5266-160">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span>

- <span data-ttu-id="d5266-161">**CSV-bestand:** de naam van het CSV-bestand dat u hebt gemaakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="d5266-161">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="d5266-162">Zorg ervoor dat u de volledige bestandsnaam gebruikt, inclusief de .csv bestandsextensie.  `ContosoCase.csv`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d5266-162">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

<span data-ttu-id="d5266-163">Het script uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="d5266-163">To run the script:</span></span>

1. <span data-ttu-id="d5266-164">Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; `CreateSearches.ps1`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d5266-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="d5266-165">Sla het bestand op in dezelfde map waar u de andere bestanden hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="d5266-165">Save the file to the same folder where you saved the other files.</span></span>

   ```Powershell
   # Get the Search Group ID and the location of the CSV input file
   $searchGroup = Read-Host 'Search Group ID'
   $csvFile = Read-Host 'Source CSV file'

   # Do a quick check to make sure our group name will not collide with other searches
   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
       Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
       return
    }
    $searchCounter++
   }

   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }

     # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
     $exchangeLocation = $null
     if ( $_.ExchangeLocation)
     {
           $exchangeLocation = $_.ExchangeLocation
     }

    # Create and run the search
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query

    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
       Write-Host " ." -NoNewline
       Start-Sleep -s 3
    }
    Write-Host ""

    $searchCounter++
   }
   ```

2. <span data-ttu-id="d5266-166">Ga Windows PowerShell naar de map waar u het script in de vorige stap hebt opgeslagen en voer het script vervolgens uit. bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d5266-166">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\CreateSearches.ps1
   ```

3. <span data-ttu-id="d5266-167">Typ een **naam van** een zoekgroep bij de vraag Groeps-id zoeken en druk vervolgens op **Enter**;  `ContosoCase`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d5266-167">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="d5266-168">Onthoud dat deze naam casegevoelig is, dus u moet deze op dezelfde manier typen in de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="d5266-168">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>

4. <span data-ttu-id="d5266-169">Typ bij **de bron-CSV-bestandsprompt** de naam van het CSV-bestand, inclusief de .csv bestandsextensie;  `ContosoCase.csv`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d5266-169">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

5. <span data-ttu-id="d5266-170">Druk **op Enter** om het script te blijven uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d5266-170">Press **Enter** to continue running the script.</span></span>

   <span data-ttu-id="d5266-171">Het script geeft de voortgang weer van het maken en uitvoeren van de zoekopdrachten.</span><span class="sxs-lookup"><span data-stu-id="d5266-171">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="d5266-172">Wanneer het script is voltooid, wordt het opnieuw gevraagd.</span><span class="sxs-lookup"><span data-stu-id="d5266-172">When the script is complete, it returns to the prompt.</span></span>

   ![Voorbeelduitvoer van het uitvoeren van het script om meerdere compliancezoekingen te maken](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="d5266-174">Stap 4: Het script uitvoeren om de zoekschattingen te rapporteren</span><span class="sxs-lookup"><span data-stu-id="d5266-174">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="d5266-175">Nadat u de zoekopdrachten hebt gemaakt, is de volgende stap het uitvoeren van een script waarin een eenvoudig rapport wordt weergegeven van het aantal zoektreffers voor elke zoekopdracht die is gemaakt in stap 3.</span><span class="sxs-lookup"><span data-stu-id="d5266-175">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="d5266-176">Het rapport bevat ook de grootte van de resultaten voor elke zoekopdracht en het totale aantal treffers en de totale grootte van alle zoekopdrachten.</span><span class="sxs-lookup"><span data-stu-id="d5266-176">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="d5266-177">Wanneer u het rapportscript uit te voeren, wordt u gevraagd om de groep-id zoeken en een CSV-bestandsnaam als u het rapport wilt opslaan in een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="d5266-177">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>

1. <span data-ttu-id="d5266-178">Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; `SearchReport.ps1`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d5266-178">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="d5266-179">Sla het bestand op in dezelfde map waar u de andere bestanden hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="d5266-179">Save the file to the same folder where you saved the other files.</span></span>

   ```Powershell
   $searchGroup = Read-Host 'Search Group ID'
   $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
   $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
   $allSearchStats = @()
   foreach ($partialObj in $searches)
   {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
   }
   # Calculate the totals
   $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
   # Convert the total size to MB and round to the nearst 100th
   $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
   $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
   # Get the total successful searches and total of all searches
   $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
   $allCount = $allSearchStats.Count
   $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
   # Totals Row
   $totalSearchStats = New-Object PSObject
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
   $allSearchStats += $totalSearchStats
   # Just get the columns we're interested in showing
   $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
   # Print the results to the screen
   $allSearchStatsPrime |ft -AutoSize -Wrap
   # Save the results to a CSV file
   if ($outputFile)
   {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
   }
   ```

2. <span data-ttu-id="d5266-180">Ga Windows PowerShell naar de map waar u het script in de vorige stap hebt opgeslagen en voer het script vervolgens uit. bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d5266-180">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\SearchReport.ps1
   ```

3. <span data-ttu-id="d5266-181">Typ een **naam van** een zoekgroep bij de vraag Groeps-id zoeken en druk vervolgens op **Enter**; bijvoorbeeld  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="d5266-181">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="d5266-182">Onthoud dat deze naam casegevoelig is, dus u moet deze op dezelfde manier typen als u deed toen u het script in stap 3 uitliep.</span><span class="sxs-lookup"><span data-stu-id="d5266-182">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

4. <span data-ttu-id="d5266-183">Typ op het pad Bestand om het rapport op te slaan in een **CSV-bestand (leeg** laten om alleen het rapport weer te geven) een bestandsnaam van het volledige bestandsnaampad (inclusief de bestandsextensie .csv) als u het rapport wilt opslaan in een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="d5266-183">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="d5266-184">naam van het CSV-bestand, inclusief de .csv bestandsextensie.</span><span class="sxs-lookup"><span data-stu-id="d5266-184">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="d5266-185">U kunt bijvoorbeeld typen om deze op te slaan in de huidige adreslijst of u kunt typen om deze op te slaan  `ContosoCaseReport.csv`  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` in een andere map.</span><span class="sxs-lookup"><span data-stu-id="d5266-185">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="d5266-186">U kunt de prompt ook leeg laten om het rapport weer te geven, maar niet opslaan in een bestand.</span><span class="sxs-lookup"><span data-stu-id="d5266-186">You can also leave the prompt blank to display the report but not save it to a file.</span></span>

5. <span data-ttu-id="d5266-187">Druk **op Enter**.</span><span class="sxs-lookup"><span data-stu-id="d5266-187">Press **Enter**.</span></span>

   <span data-ttu-id="d5266-188">Het script geeft de voortgang weer van het maken en uitvoeren van de zoekopdrachten.</span><span class="sxs-lookup"><span data-stu-id="d5266-188">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="d5266-189">Wanneer het script is voltooid, wordt het rapport weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d5266-189">When the script is complete, the report is displayed.</span></span>

   ![Voer het zoekrapport uit om de schattingen voor de zoekgroep weer te geven](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> <span data-ttu-id="d5266-191">Als hetzelfde postvak of dezelfde site is opgegeven als een inhoudslocatie in meer dan één zoekopdracht in een zoekgroep, kan de schatting van de totale resultaten in het rapport (voor zowel het aantal items als de totale grootte) resultaten voor dezelfde items bevatten.</span><span class="sxs-lookup"><span data-stu-id="d5266-191">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="d5266-192">Dit komt omdat hetzelfde e-mailbericht of hetzelfde document meerdere keer wordt geteld als het overeenkomt met de query voor verschillende zoekopdrachten in de zoekgroep.</span><span class="sxs-lookup"><span data-stu-id="d5266-192">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span>

## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="d5266-193">Stap 5: Het script uitvoeren om de zoekopdrachten te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d5266-193">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="d5266-194">Omdat u mogelijk veel zoekopdrachten maakt, kunt u met dit laatste script de zoekopdrachten die u in stap 3 hebt gemaakt, eenvoudig verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d5266-194">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="d5266-195">Net als de andere scripts wordt u ook gevraagd om de id Van de zoekgroep.</span><span class="sxs-lookup"><span data-stu-id="d5266-195">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="d5266-196">Alle zoekopdrachten met de zoekgroep-id in de zoeknaam worden verwijderd wanneer u dit script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d5266-196">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span>

1. <span data-ttu-id="d5266-197">Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; `DeleteSearches.ps1`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d5266-197">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="d5266-198">Sla het bestand op in dezelfde map waar u de andere bestanden hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="d5266-198">Save the file to the same folder where you saved the other files.</span></span>

   ```Powershell
   # Delete all searches in a search group
   $searchGroup = Read-Host 'Search Group ID'
   Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
   }
   ```

2. <span data-ttu-id="d5266-199">Ga Windows PowerShell naar de map waar u het script in de vorige stap hebt opgeslagen en voer het script vervolgens uit. bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d5266-199">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. <span data-ttu-id="d5266-200">Typ in **de prompt Groeps-id** zoeken een naam van de zoekgroep voor de zoekopdrachten die u wilt verwijderen en druk vervolgens op **Enter**;  `ContosoCase`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d5266-200">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="d5266-201">Onthoud dat deze naam casegevoelig is, dus u moet deze op dezelfde manier typen als u deed toen u het script in stap 3 uitliep.</span><span class="sxs-lookup"><span data-stu-id="d5266-201">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

   <span data-ttu-id="d5266-202">In het script wordt de naam weergegeven van elke zoekopdracht die wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d5266-202">The script displays the name of each search that's deleted.</span></span>

   ![Het script uitvoeren om de zoekopdrachten in de zoekgroep te verwijderen](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
