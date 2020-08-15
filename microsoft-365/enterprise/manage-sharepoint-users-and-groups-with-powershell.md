---
title: Gebruikers en groepen van SharePoint Online beheren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: In dit artikel vindt u informatie over het gebruik van PowerShell voor Microsoft 365 voor het beheren van SharePoint Online-gebruikers,-groepen en-sites.
ms.openlocfilehash: 5252ecc950e5f26d6ad60cd871910a67bf50f187
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689405"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a><span data-ttu-id="9c5af-103">Gebruikers en groepen van SharePoint Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c5af-103">Manage SharePoint Online users and groups with PowerShell</span></span>

<span data-ttu-id="9c5af-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9c5af-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9c5af-105">Als u een SharePoint Online-beheerder bent die met grote lijsten met gebruikersaccounts of groepen werkt en ze een eenvoudige manier wil beheren, kunt u PowerShell voor Microsoft 365 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9c5af-105">If you are a SharePoint Online administrator who works with large lists of user accounts or groups and wants an easier way to manage them, you can use PowerShell for Microsoft 365.</span></span> 

<span data-ttu-id="9c5af-106">Voordat u begint, moet u voor de procedures in dit onderwerp verbinding maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9c5af-106">Before you begin, the procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="9c5af-107">Zie [verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) voor instructies</span><span class="sxs-lookup"><span data-stu-id="9c5af-107">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="get-a-list-of-sites-groups-and-users"></a><span data-ttu-id="9c5af-108">Een lijst met sites, groepen en gebruikers weergeven</span><span class="sxs-lookup"><span data-stu-id="9c5af-108">Get a list of sites, groups, and users</span></span>

<span data-ttu-id="9c5af-109">Voordat we gebruikers en groepen gaan beheren, moet u lijsten met uw sites, groepen en gebruikers krijgen.</span><span class="sxs-lookup"><span data-stu-id="9c5af-109">Before we start to manage users and groups, you need to get lists of your sites, groups, and users.</span></span> <span data-ttu-id="9c5af-110">U kunt deze gegevens gebruiken om het voorbeeld in dit artikel te bewerken.</span><span class="sxs-lookup"><span data-stu-id="9c5af-110">You can then use this information to work through the example in this article.</span></span>

<span data-ttu-id="9c5af-111">U ontvangt een lijst met de sites in de Tenant met behulp van deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="9c5af-111">Get a list of the sites in your tenant with this command:</span></span>

```powershell
Get-SPOSite
```

<span data-ttu-id="9c5af-112">U ontvangt een lijst met de groepen in uw Tenant met deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="9c5af-112">Get a list of the groups in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

<span data-ttu-id="9c5af-113">U ontvangt een lijst met gebruikers in uw Tenant met deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="9c5af-113">Get a list of the users in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a><span data-ttu-id="9c5af-114">Een gebruiker toevoegen aan de groep beheerders van de site verzameling</span><span class="sxs-lookup"><span data-stu-id="9c5af-114">Add a user to the Site Collection Administrators group</span></span>

<span data-ttu-id="9c5af-115">U gebruikt de `Set-SPOUser` cmdlet om een gebruiker toe te voegen aan de lijst met beheerders van siteverzamelingen voor een siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="9c5af-115">You use the `Set-SPOUser` cmdlet to add a user to the list of Site Collection Administrators on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

<span data-ttu-id="9c5af-116">Als u deze opdrachten wilt gebruiken, vervangt u alles binnen de aanhalingstekens, waaronder de < en > tekens, met de juiste namen.</span><span class="sxs-lookup"><span data-stu-id="9c5af-116">To use these commands, replace everything within the quotes, including the < and > characters, with the correct names.</span></span>

<span data-ttu-id="9c5af-117">Deze reeks opdrachten voegt bijvoorbeeld Opal Castillo (gebruikersnaam opalc) toe aan de lijst met beheerders van de siteverzameling in de siteverzameling contoso, pacht:</span><span class="sxs-lookup"><span data-stu-id="9c5af-117">For example, this set of commands adds Opal Castillo (user name opalc) to the list of Site Collection Administrators on the ContosoTest site collection in the Contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

<span data-ttu-id="9c5af-118">U kunt deze opdrachten in Kladblok kopiëren en plakken, de variabele waarden voor $tenant, $site en $user van werkelijke waarden uit de omgeving wijzigen en deze vervolgens in het SharePoint Online management shell-venster plakken om ze uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="9c5af-118">You can copy and paste these commands into Notepad, change the variable values for $tenant, $site, and $user to actual values from your environment, and then paste this into your SharePoint Online Management Shell window to run them.</span></span>

## <a name="add-a-user-to-other-site-collection-groups"></a><span data-ttu-id="9c5af-119">Een gebruiker toevoegen aan andere site verzamelings groepen</span><span class="sxs-lookup"><span data-stu-id="9c5af-119">Add a user to other site collection groups</span></span>

<span data-ttu-id="9c5af-120">In deze taak gebruiken we de `Add-SPOUser` cmdlet om een gebruiker toe te voegen aan een SharePoint-groep in een siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="9c5af-120">In this task, we'll use the `Add-SPOUser` cmdlet to add a user to a SharePoint group on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

<span data-ttu-id="9c5af-121">Laten we bijvoorbeeld Glen Rife (gebruikersnaam glenr) toevoegen aan de groep auditers in de siteverzameling voor ContosoTest in contoso, pacht:</span><span class="sxs-lookup"><span data-stu-id="9c5af-121">For example, let's add Glen Rife (user name glenr) to the Auditors group on the ContosoTest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a><span data-ttu-id="9c5af-122">Een siteverzamelingsgroep maken</span><span class="sxs-lookup"><span data-stu-id="9c5af-122">Create a site collection group</span></span>

<span data-ttu-id="9c5af-123">Met de `New-SPOSiteGroup` cmdlet maakt u een nieuwe SharePoint-groep en voegt u deze toe aan een siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="9c5af-123">You use the `New-SPOSiteGroup` cmdlet to create a new SharePoint group and add it to a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
<span data-ttu-id="9c5af-124">De eigenschappen van de groep, zoals de machtigingsniveaus, kunt u later bijwerken met behulp van de `Set-SPOSiteGroup` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c5af-124">Group properties, such as permission levels, can be updated later by using the `Set-SPOSiteGroup` cmdlet.</span></span>

<span data-ttu-id="9c5af-125">Laten we bijvoorbeeld de groep auditors toevoegen met de machtiging alleen weergeven voor de contosotest-siteverzameling in contoso, pacht:</span><span class="sxs-lookup"><span data-stu-id="9c5af-125">For example, let's add the Auditors group with View Only permissions to the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a><span data-ttu-id="9c5af-126">Gebruikers uit een groep verwijderen</span><span class="sxs-lookup"><span data-stu-id="9c5af-126">Remove users from a group</span></span>

<span data-ttu-id="9c5af-127">Soms moet u een gebruiker van een site of zelfs alle sites verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9c5af-127">Sometimes you have to remove a user from a site or even all sites.</span></span> <span data-ttu-id="9c5af-128">Het kan zijn dat de werknemer van de ene naar de andere afdeling gaat of het bedrijf verlaat.</span><span class="sxs-lookup"><span data-stu-id="9c5af-128">Perhaps the employee moves from one division to another or leaves the company.</span></span> <span data-ttu-id="9c5af-129">U kunt deze functie in de GEBRUIKERSINTERFACE eenvoudig doen voor een werknemer, maar dit is niet eenvoudig wanneer u een volledige afdeling van een site naar een andere site wilt verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="9c5af-129">You can do this for one employee easily in the UI, but this is not easily done when you have to move a complete division from one site to another.</span></span>

<span data-ttu-id="9c5af-130">Met de SharePoint Online Management Shell-en CSV-bestanden is dit echter snel en gemakkelijk.</span><span class="sxs-lookup"><span data-stu-id="9c5af-130">However by using the SharePoint Online Management Shell and CSV files, this is fast and easy.</span></span> <span data-ttu-id="9c5af-131">In deze taak gaat u Windows PowerShell gebruiken om een gebruiker te verwijderen uit een beveiligingsgroep van een siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="9c5af-131">In this task, you'll use Windows PowerShell to remove a user from a site collection security group.</span></span> <span data-ttu-id="9c5af-132">Vervolgens maakt u een CSV-bestand en verwijdert u veel gebruikers van verschillende sites.</span><span class="sxs-lookup"><span data-stu-id="9c5af-132">Then you'll use a CSV file and remove lots of users from different sites.</span></span> 

<span data-ttu-id="9c5af-133">We gebruiken de cmdlet Remove-echtgenoot om één Microsoft 365-gebruiker uit de groep siteverzameling te verwijderen, zodat we de opdrachtsyntaxis kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="9c5af-133">We'll be using the 'Remove-SPOUser' cmdlet to remove a single Microsoft 365 user from a site collection group just so we can see the command syntax.</span></span> <span data-ttu-id="9c5af-134">U ziet de syntaxis als volgt:</span><span class="sxs-lookup"><span data-stu-id="9c5af-134">Here is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
<span data-ttu-id="9c5af-135">Laten we de Overby van de siteverzameling in de contosotest-siteverzameling verwijderen uit de siteverzameling van de siteverzameling in de contoso pacht:</span><span class="sxs-lookup"><span data-stu-id="9c5af-135">For example, let's remove Bobby Overby from the site collection Auditors group in the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="9c5af-136">Stel dat we Berend willen verwijderen van alle groepen die hij momenteel aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="9c5af-136">Suppose we wanted to remove Bobby from all the groups he is currently in.</span></span> <span data-ttu-id="9c5af-137">Dit doet u als volgt:</span><span class="sxs-lookup"><span data-stu-id="9c5af-137">Here is how we would do that:</span></span>

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> <span data-ttu-id="9c5af-138">Dit is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="9c5af-138">This is just an example.</span></span> <span data-ttu-id="9c5af-139">U dient deze opdracht niet uit te voeren, tenzij u echt een gebruiker uit elke groep moet verwijderen, bijvoorbeeld als de gebruiker het bedrijf verlaat.</span><span class="sxs-lookup"><span data-stu-id="9c5af-139">You should not run this command unless you really have to remove a user from every group, for example if the user leaves the company.</span></span>

## <a name="automate-management-of-large-lists-of-users-and-groups"></a><span data-ttu-id="9c5af-140">Beheer van grote lijsten van gebruikers en groepen automatiseren</span><span class="sxs-lookup"><span data-stu-id="9c5af-140">Automate management of large lists of users and groups</span></span>

<span data-ttu-id="9c5af-141">Als u een groot aantal accounts wilt toevoegen aan SharePoint-sites en ze machtigingen wilt geven, kunt u het Microsoft 365-Beheercentrum, afzonderlijke PowerShell-opdrachten of PowerShell gebruiken als een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="9c5af-141">To add a large number of accounts to SharePoint sites and give them permissions, you can use the Microsoft 365 admin center, individual PowerShell commands, or PowerShell an a CSV file.</span></span> <span data-ttu-id="9c5af-142">Met deze opties is het CSV-bestand de snelste manier om deze taak te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="9c5af-142">Of these choices, the CSV file is the fastest way to automate this task.</span></span>

<span data-ttu-id="9c5af-143">Het basisproces is het maken van een CSV-bestand met kopteksten (kolommen) die overeenkomen met de parameters die door het Windows PowerShell-script worden vereist.</span><span class="sxs-lookup"><span data-stu-id="9c5af-143">The basic process is to create a CSV file that has headers (columns) that correspond to the parameters that the Windows PowerShell script needs.</span></span> <span data-ttu-id="9c5af-144">U kunt eenvoudig een lijst maken in Excel en deze vervolgens als een CSV-bestand exporteren.</span><span class="sxs-lookup"><span data-stu-id="9c5af-144">You can easily create such a list in Excel and then export it as a CSV file.</span></span> <span data-ttu-id="9c5af-145">Vervolgens gebruikt u een Windows PowerShell-script om records (rijen) uit het CSV-bestand te doorzoeken en de gebruikers toe te voegen aan groepen en de groepen aan sites.</span><span class="sxs-lookup"><span data-stu-id="9c5af-145">Then, you use a Windows PowerShell script to iterate through records (rows) in the CSV file, adding the users to groups and the groups to sites.</span></span> 

<span data-ttu-id="9c5af-146">Als u bijvoorbeeld een CSV-bestand wilt maken, kunt u een groep siteverzamelingen, groepen en machtigingen definiëren.</span><span class="sxs-lookup"><span data-stu-id="9c5af-146">For example, let's create a CSV file to define a group of site collections, groups, and permissions.</span></span> <span data-ttu-id="9c5af-147">Vervolgens maakt u een CSV-bestand om de groepen met gebruikers te vullen.</span><span class="sxs-lookup"><span data-stu-id="9c5af-147">Next, we will create a CSV file to populate the groups with users.</span></span> <span data-ttu-id="9c5af-148">Tot slot maakt u een simpel Windows PowerShell-script waarmee de groepen worden gemaakt en gevuld.</span><span class="sxs-lookup"><span data-stu-id="9c5af-148">Finally, we will create and run a simple Windows PowerShell script that creates and populates the groups.</span></span>

<span data-ttu-id="9c5af-149">Het eerste CSV-bestand voegt een of meer groepen toe aan een of meer siteverzamelingen, en heeft de volgende structuur:</span><span class="sxs-lookup"><span data-stu-id="9c5af-149">The first CSV file will add one or more groups to one or more site collections and will have this structure:</span></span>

<span data-ttu-id="9c5af-150">Factuurkop</span><span class="sxs-lookup"><span data-stu-id="9c5af-150">Header:</span></span>

```powershell
Site,Group,PermissionLevels
```

<span data-ttu-id="9c5af-151">Item</span><span class="sxs-lookup"><span data-stu-id="9c5af-151">Item:</span></span>

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

<span data-ttu-id="9c5af-152">Hier ziet u een voorbeeld van een bestand:</span><span class="sxs-lookup"><span data-stu-id="9c5af-152">Here is an example file:</span></span>

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

<span data-ttu-id="9c5af-153">Het tweede CSV-bestand voegt een of meer gebruikers toe aan een of meer groepen, en heeft de volgende structuur:</span><span class="sxs-lookup"><span data-stu-id="9c5af-153">The second CSV file will add one or more users to one or more groups and will have this structure:</span></span>

<span data-ttu-id="9c5af-154">Factuurkop</span><span class="sxs-lookup"><span data-stu-id="9c5af-154">Header:</span></span>

```powershell
Group,LoginName,Site
```

<span data-ttu-id="9c5af-155">Item</span><span class="sxs-lookup"><span data-stu-id="9c5af-155">Item:</span></span>

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

<span data-ttu-id="9c5af-156">Hier ziet u een voorbeeld van een bestand:</span><span class="sxs-lookup"><span data-stu-id="9c5af-156">Here is an example file:</span></span>

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

<span data-ttu-id="9c5af-157">Voor de volgende stap moet u de twee CSV-bestanden opslaan op uw station.</span><span class="sxs-lookup"><span data-stu-id="9c5af-157">For the next step, you must have the two CSV files saved to your drive.</span></span> <span data-ttu-id="9c5af-158">Hier ziet u voorbeelden van opdrachten die gebruikmaken van CSV-bestanden en het toevoegen van machtigingen en groepslidmaatschap:</span><span class="sxs-lookup"><span data-stu-id="9c5af-158">Here are example commands that use both CSV files and to add permissions and group membership:</span></span>

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

<span data-ttu-id="9c5af-159">Met het script wordt de inhoud van het CSV-bestand geïmporteerd en worden de waarden in de kolommen gebruikt voor het vullen van de parameters van de opdrachten **New-SPOSiteGroup** en **add-echtgenote** .</span><span class="sxs-lookup"><span data-stu-id="9c5af-159">The script imports the CSV file contents and uses the values in the columns to populate the parameters of the **New-SPOSiteGroup** and **Add-SPOUser** commands.</span></span> <span data-ttu-id="9c5af-160">In ons voorbeeld wordt deze map opgeslagen in de map theO365Admin op station C, maar u kunt de locatie waar u maar wilt.</span><span class="sxs-lookup"><span data-stu-id="9c5af-160">In our example, we are saving this to theO365Admin folder on drive C, but you can save it wherever you want.</span></span>

<span data-ttu-id="9c5af-161">Laten we nu een aantal personen verwijderen voor verschillende groepen in verschillende sites met hetzelfde CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="9c5af-161">Now, let's remove a bunch of people for several groups in different sites using the same CSV file.</span></span> <span data-ttu-id="9c5af-162">Hier ziet u een voorbeeld van een opdracht:</span><span class="sxs-lookup"><span data-stu-id="9c5af-162">Here is an example command:</span></span>

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a><span data-ttu-id="9c5af-163">Gebruikers rapporten genereren</span><span class="sxs-lookup"><span data-stu-id="9c5af-163">Generate user reports</span></span>

<span data-ttu-id="9c5af-164">Mogelijk wilt u een eenvoudig rapport voor enkele sites weergeven en de gebruikers voor deze sites, hun machtigingsniveau en andere eigenschappen weergeven.</span><span class="sxs-lookup"><span data-stu-id="9c5af-164">You might want to get a simple report for a few sites and display the users for those sites, their permission level, and other properties.</span></span> <span data-ttu-id="9c5af-165">Hoe ziet de syntaxis er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="9c5af-165">This is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="9c5af-166">Hierdoor worden de gegevens van deze drie sites opgezocht en naar een tekstbestand op uw lokale station geschreven.</span><span class="sxs-lookup"><span data-stu-id="9c5af-166">This will grab the data for these three sites and write them to a text file on your local drive.</span></span> <span data-ttu-id="9c5af-167">Houd er rekening mee dat via de parameter toevoegen nieuwe inhoud aan een bestaand bestand wordt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="9c5af-167">Note that the parameter –Append will add new content to an existing file.</span></span>

<span data-ttu-id="9c5af-168">Laten we bijvoorbeeld een rapport uitvoeren op de sites ContosoTest, TeamSite01 en Project01 voor de Contoso1-Tenant:</span><span class="sxs-lookup"><span data-stu-id="9c5af-168">For example, let's run a report on the ContosoTest, TeamSite01, and Project01 sites for the Contoso1 tenant:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="9c5af-169">Let erop dat we alleen de **$site** variabele wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9c5af-169">Note that we had to change only the **$site** variable.</span></span> <span data-ttu-id="9c5af-170">Met de **$Tenant** variabele wordt de waarde van de hele opdracht beperkt.</span><span class="sxs-lookup"><span data-stu-id="9c5af-170">The **$tenant** variable keeps its value through all three runs of the command.</span></span>

<span data-ttu-id="9c5af-171">Maar wat als u dit wilt doen voor elke site?</span><span class="sxs-lookup"><span data-stu-id="9c5af-171">However, what if you wanted to do this for every site?</span></span> <span data-ttu-id="9c5af-172">U kunt dit doen zonder alle websites te hoeven typen met behulp van deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="9c5af-172">You can do this without having to type all those websites by using this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="9c5af-173">Dit rapport is tamelijk simpel, en u kunt meer informatie toevoegen om specifiekere rapporten of rapporten te maken die meer gedetailleerde informatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="9c5af-173">This report is fairly simple, and you can add more code to create more specific reports or reports that include more detailed information.</span></span> <span data-ttu-id="9c5af-174">Dit geeft wel een idee van hoe u de SharePoint Online Management Shell kunt gebruiken voor het beheren van gebruikers in de SharePoint Online-omgeving.</span><span class="sxs-lookup"><span data-stu-id="9c5af-174">But this should give you an idea of how to use the SharePoint Online Management Shell to manage users in the SharePoint Online environment.</span></span>
   
## <a name="see-also"></a><span data-ttu-id="9c5af-175">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9c5af-175">See also</span></span>

[<span data-ttu-id="9c5af-176">Verbinding maken met SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c5af-176">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="9c5af-177">SharePoint Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c5af-177">Manage SharePoint Online with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="9c5af-178">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c5af-178">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9c5af-179">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9c5af-179">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
