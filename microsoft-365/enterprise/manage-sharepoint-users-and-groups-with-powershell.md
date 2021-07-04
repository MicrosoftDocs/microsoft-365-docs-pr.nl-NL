---
title: Online SharePoint en groepen beheren met PowerShell
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
description: In dit artikel leert u hoe u PowerShell gebruikt voor Microsoft 365 om SharePoint onlinegebruikers, groepen en sites te beheren.
ms.openlocfilehash: 823c5fdc9af178a2e8ea8f0ca4c63fbfa4673dd8
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289053"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a><span data-ttu-id="4f75b-103">Online SharePoint en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f75b-103">Manage SharePoint Online users and groups with PowerShell</span></span>

<span data-ttu-id="4f75b-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4f75b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4f75b-105">Als u een SharePoint onlinebeheerder bent die werkt met grote lijsten met gebruikersaccounts of groepen en een eenvoudigere manier wilt om deze te beheren, kunt u PowerShell gebruiken voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f75b-105">If you are a SharePoint Online administrator who works with large lists of user accounts or groups and wants an easier way to manage them, you can use PowerShell for Microsoft 365.</span></span>

<span data-ttu-id="4f75b-106">Voordat u begint, moet u voor de procedures in dit onderwerp verbinding maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4f75b-106">Before you begin, the procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="4f75b-107">Zie Verbinding maken [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) voor instructies</span><span class="sxs-lookup"><span data-stu-id="4f75b-107">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span></span>

## <a name="get-a-list-of-sites-groups-and-users"></a><span data-ttu-id="4f75b-108">Een lijst met sites, groepen en gebruikers krijgen</span><span class="sxs-lookup"><span data-stu-id="4f75b-108">Get a list of sites, groups, and users</span></span>

<span data-ttu-id="4f75b-109">Voordat we gebruikers en groepen gaan beheren, moet u lijsten van uw sites, groepen en gebruikers krijgen.</span><span class="sxs-lookup"><span data-stu-id="4f75b-109">Before we start to manage users and groups, you need to get lists of your sites, groups, and users.</span></span> <span data-ttu-id="4f75b-110">U kunt deze informatie vervolgens gebruiken om het voorbeeld in dit artikel door te nemen.</span><span class="sxs-lookup"><span data-stu-id="4f75b-110">You can then use this information to work through the example in this article.</span></span>

<span data-ttu-id="4f75b-111">Een lijst met de sites in uw tenant krijgen met deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="4f75b-111">Get a list of the sites in your tenant with this command:</span></span>

```powershell
Get-SPOSite
```

<span data-ttu-id="4f75b-112">Met deze opdracht krijgt u een lijst met de groepen in uw tenant:</span><span class="sxs-lookup"><span data-stu-id="4f75b-112">Get a list of the groups in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

<span data-ttu-id="4f75b-113">Een lijst met de gebruikers in uw tenant met deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="4f75b-113">Get a list of the users in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a><span data-ttu-id="4f75b-114">Een gebruiker toevoegen aan de groep Beheerders van siteverzamelingen</span><span class="sxs-lookup"><span data-stu-id="4f75b-114">Add a user to the Site Collection Administrators group</span></span>

<span data-ttu-id="4f75b-115">U gebruikt de cmdlet om een gebruiker toe te voegen aan de lijst met beheerders van `Set-SPOUser` siteverzamelingen in een siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="4f75b-115">You use the `Set-SPOUser` cmdlet to add a user to the list of Site Collection Administrators on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

<span data-ttu-id="4f75b-116">Als u deze opdrachten wilt gebruiken, vervangt u alles in de aanhalingstekens, inclusief de < en > tekens, door de juiste namen.</span><span class="sxs-lookup"><span data-stu-id="4f75b-116">To use these commands, replace everything within the quotes, including the < and > characters, with the correct names.</span></span>

<span data-ttu-id="4f75b-117">Met deze reeks opdrachten wordt bijvoorbeeld Opal Castillo (gebruikersnaam opalc) toegevoegd aan de lijst met beheerders van siteverzamelingen in de ContosoTest-siteverzameling in de contoso-tenancy:</span><span class="sxs-lookup"><span data-stu-id="4f75b-117">For example, this set of commands adds Opal Castillo (user name opalc) to the list of Site Collection Administrators on the ContosoTest site collection in the Contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

<span data-ttu-id="4f75b-118">U kunt deze opdrachten kopiëren en plakken in Kladblok, de variabele waarden voor $tenant, $site en $user wijzigen in werkelijke waarden uit uw omgeving en deze vervolgens plakken in het SharePoint Online Management Shell-venster om deze uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="4f75b-118">You can copy and paste these commands into Notepad, change the variable values for $tenant, $site, and $user to actual values from your environment, and then paste this into your SharePoint Online Management Shell window to run them.</span></span>

## <a name="add-a-user-to-other-site-collection-groups"></a><span data-ttu-id="4f75b-119">Een gebruiker toevoegen aan andere siteverzamelingsgroepen</span><span class="sxs-lookup"><span data-stu-id="4f75b-119">Add a user to other site collection groups</span></span>

<span data-ttu-id="4f75b-120">In deze taak gebruiken we de cmdlet om een gebruiker toe te voegen aan een groep SharePoint `Add-SPOUser` een siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="4f75b-120">In this task, we'll use the `Add-SPOUser` cmdlet to add a user to a SharePoint group on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

<span data-ttu-id="4f75b-121">Laten we bijvoorbeeld Glen Rife (gebruikersnaam glenr) toevoegen aan de groep Auditors in de contosoTest-siteverzameling in de contoso tenancy:</span><span class="sxs-lookup"><span data-stu-id="4f75b-121">For example, let's add Glen Rife (user name glenr) to the Auditors group on the ContosoTest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a><span data-ttu-id="4f75b-122">Een siteverzamelingsgroep maken</span><span class="sxs-lookup"><span data-stu-id="4f75b-122">Create a site collection group</span></span>

<span data-ttu-id="4f75b-123">U gebruikt de cmdlet om een nieuwe groep SharePoint en deze toe te voegen `New-SPOSiteGroup` aan een siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="4f75b-123">You use the `New-SPOSiteGroup` cmdlet to create a new SharePoint group and add it to a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

<span data-ttu-id="4f75b-124">Groepseigenschappen, zoals machtigingsniveaus, kunnen later worden bijgewerkt met de `Set-SPOSiteGroup` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4f75b-124">Group properties, such as permission levels, can be updated later by using the `Set-SPOSiteGroup` cmdlet.</span></span>

<span data-ttu-id="4f75b-125">Laten we bijvoorbeeld de groep Auditors met alleen-weergavemachtigingen toevoegen aan de contosotestsiteverzameling in de contoso-tenancy:</span><span class="sxs-lookup"><span data-stu-id="4f75b-125">For example, let's add the Auditors group with View Only permissions to the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a><span data-ttu-id="4f75b-126">Gebruikers uit een groep verwijderen</span><span class="sxs-lookup"><span data-stu-id="4f75b-126">Remove users from a group</span></span>

<span data-ttu-id="4f75b-127">Soms moet u een gebruiker van een site of zelfs van alle sites verwijderen.</span><span class="sxs-lookup"><span data-stu-id="4f75b-127">Sometimes you have to remove a user from a site or even all sites.</span></span> <span data-ttu-id="4f75b-128">Misschien gaat de werknemer van de ene afdeling naar de andere of verlaat hij het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="4f75b-128">Perhaps the employee moves from one division to another or leaves the company.</span></span> <span data-ttu-id="4f75b-129">U kunt dit eenvoudig doen voor één werknemer in de gebruikersinterface, maar dit is niet eenvoudig wanneer u een volledige afdeling van de ene site naar de andere moet verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="4f75b-129">You can do this for one employee easily in the UI, but this is not easily done when you have to move a complete division from one site to another.</span></span>

<span data-ttu-id="4f75b-130">Maar door de SharePoint Online Management Shell- en CSV-bestanden te gebruiken, is dit snel en eenvoudig.</span><span class="sxs-lookup"><span data-stu-id="4f75b-130">However by using the SharePoint Online Management Shell and CSV files, this is fast and easy.</span></span> <span data-ttu-id="4f75b-131">In deze taak gebruikt u een Windows PowerShell om een gebruiker te verwijderen uit een beveiligingsgroep voor siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="4f75b-131">In this task, you'll use Windows PowerShell to remove a user from a site collection security group.</span></span> <span data-ttu-id="4f75b-132">Vervolgens gebruikt u een CSV-bestand en verwijdert u veel gebruikers van verschillende sites.</span><span class="sxs-lookup"><span data-stu-id="4f75b-132">Then you'll use a CSV file and remove lots of users from different sites.</span></span>

<span data-ttu-id="4f75b-133">We gebruiken de cmdlet 'Remove-SPOUser' om één Microsoft 365 gebruiker uit een siteverzamelingsgroep te verwijderen, zodat we de syntaxis van de opdracht kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="4f75b-133">We'll be using the 'Remove-SPOUser' cmdlet to remove a single Microsoft 365 user from a site collection group just so we can see the command syntax.</span></span> <span data-ttu-id="4f75b-134">De syntaxis ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="4f75b-134">Here is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="4f75b-135">Laten we bijvoorbeeld Bobby Overby verwijderen uit de groep Auditors van de siteverzameling Auditors in de contosotestsiteverzameling in de contoso-tenancy:</span><span class="sxs-lookup"><span data-stu-id="4f75b-135">For example, let's remove Bobby Overby from the site collection Auditors group in the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="4f75b-136">Stel dat we Bobby willen verwijderen uit alle groepen waarin hij zich momenteel in.</span><span class="sxs-lookup"><span data-stu-id="4f75b-136">Suppose we wanted to remove Bobby from all the groups he is currently in.</span></span> <span data-ttu-id="4f75b-137">Dit doen we als volgende:</span><span class="sxs-lookup"><span data-stu-id="4f75b-137">Here is how we would do that:</span></span>

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> <span data-ttu-id="4f75b-138">Dit is slechts een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="4f75b-138">This is just an example.</span></span> <span data-ttu-id="4f75b-139">U moet deze opdracht alleen uitvoeren als u een gebruiker echt uit elke groep moet verwijderen, bijvoorbeeld als de gebruiker het bedrijf verlaat.</span><span class="sxs-lookup"><span data-stu-id="4f75b-139">You should not run this command unless you really have to remove a user from every group, for example if the user leaves the company.</span></span>

## <a name="automate-management-of-large-lists-of-users-and-groups"></a><span data-ttu-id="4f75b-140">Beheer van grote lijsten met gebruikers en groepen automatiseren</span><span class="sxs-lookup"><span data-stu-id="4f75b-140">Automate management of large lists of users and groups</span></span>

<span data-ttu-id="4f75b-141">Als u een groot aantal accounts wilt toevoegen aan SharePoint sites en deze machtigingen wilt geven, kunt u de Microsoft 365-beheercentrum, afzonderlijke PowerShell-opdrachten of PowerShell een CSV-bestand gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4f75b-141">To add a large number of accounts to SharePoint sites and give them permissions, you can use the Microsoft 365 admin center, individual PowerShell commands, or PowerShell an a CSV file.</span></span> <span data-ttu-id="4f75b-142">Van deze opties is het CSV-bestand de snelste manier om deze taak te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="4f75b-142">Of these choices, the CSV file is the fastest way to automate this task.</span></span>

<span data-ttu-id="4f75b-143">Het basisproces bestaat uit het maken van een CSV-bestand met kopteksten (kolommen) die overeenkomen met de parameters die Windows PowerShell script nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="4f75b-143">The basic process is to create a CSV file that has headers (columns) that correspond to the parameters that the Windows PowerShell script needs.</span></span> <span data-ttu-id="4f75b-144">U kunt eenvoudig een dergelijke lijst maken in Excel en vervolgens exporteren als een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="4f75b-144">You can easily create such a list in Excel and then export it as a CSV file.</span></span> <span data-ttu-id="4f75b-145">Vervolgens gebruikt u een Windows PowerShell script om door records (rijen) in het CSV-bestand te itereren en de gebruikers toe te voegen aan groepen en groepen aan sites.</span><span class="sxs-lookup"><span data-stu-id="4f75b-145">Then, you use a Windows PowerShell script to iterate through records (rows) in the CSV file, adding the users to groups and the groups to sites.</span></span>

<span data-ttu-id="4f75b-146">Laten we bijvoorbeeld een CSV-bestand maken om een groep siteverzamelingen, groepen en machtigingen te definiëren.</span><span class="sxs-lookup"><span data-stu-id="4f75b-146">For example, let's create a CSV file to define a group of site collections, groups, and permissions.</span></span> <span data-ttu-id="4f75b-147">Vervolgens maken we een CSV-bestand om de groepen te vullen met gebruikers.</span><span class="sxs-lookup"><span data-stu-id="4f75b-147">Next, we will create a CSV file to populate the groups with users.</span></span> <span data-ttu-id="4f75b-148">Ten slotte maken en uitvoeren we een eenvoudig Windows PowerShell script dat de groepen maakt en vult.</span><span class="sxs-lookup"><span data-stu-id="4f75b-148">Finally, we will create and run a simple Windows PowerShell script that creates and populates the groups.</span></span>

<span data-ttu-id="4f75b-149">Het eerste CSV-bestand voegt een of meer groepen toe aan een of meer siteverzamelingen en heeft deze structuur:</span><span class="sxs-lookup"><span data-stu-id="4f75b-149">The first CSV file will add one or more groups to one or more site collections and will have this structure:</span></span>

<span data-ttu-id="4f75b-150">Koptekst:</span><span class="sxs-lookup"><span data-stu-id="4f75b-150">Header:</span></span>

```powershell
Site,Group,PermissionLevels
```

<span data-ttu-id="4f75b-151">Item:</span><span class="sxs-lookup"><span data-stu-id="4f75b-151">Item:</span></span>

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

<span data-ttu-id="4f75b-152">Hier is een voorbeeldbestand:</span><span class="sxs-lookup"><span data-stu-id="4f75b-152">Here is an example file:</span></span>

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

<span data-ttu-id="4f75b-153">Het tweede CSV-bestand voegt een of meer gebruikers toe aan een of meer groepen en heeft deze structuur:</span><span class="sxs-lookup"><span data-stu-id="4f75b-153">The second CSV file will add one or more users to one or more groups and will have this structure:</span></span>

<span data-ttu-id="4f75b-154">Koptekst:</span><span class="sxs-lookup"><span data-stu-id="4f75b-154">Header:</span></span>

```powershell
Group,LoginName,Site
```

<span data-ttu-id="4f75b-155">Item:</span><span class="sxs-lookup"><span data-stu-id="4f75b-155">Item:</span></span>

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

<span data-ttu-id="4f75b-156">Hier is een voorbeeldbestand:</span><span class="sxs-lookup"><span data-stu-id="4f75b-156">Here is an example file:</span></span>

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

<span data-ttu-id="4f75b-157">Voor de volgende stap moet u de twee CSV-bestanden hebben opgeslagen op uw station.</span><span class="sxs-lookup"><span data-stu-id="4f75b-157">For the next step, you must have the two CSV files saved to your drive.</span></span> <span data-ttu-id="4f75b-158">Hier volgen voorbeeldopdrachten die zowel CSV-bestanden gebruiken als machtigingen en groepslidmaatschap toevoegen:</span><span class="sxs-lookup"><span data-stu-id="4f75b-158">Here are example commands that use both CSV files and to add permissions and group membership:</span></span>

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

<span data-ttu-id="4f75b-159">Het script importeert de inhoud van het CSV-bestand en gebruikt de waarden in de kolommen om de parameters van de opdrachten **New-SPOSiteGroup** en **Add-SPOUser** in te vullen.</span><span class="sxs-lookup"><span data-stu-id="4f75b-159">The script imports the CSV file contents and uses the values in the columns to populate the parameters of the **New-SPOSiteGroup** and **Add-SPOUser** commands.</span></span> <span data-ttu-id="4f75b-160">In ons voorbeeld slaan we deze op in de map O365Admin op station C, maar u kunt deze opslaan waar u maar wilt.</span><span class="sxs-lookup"><span data-stu-id="4f75b-160">In our example, we are saving this to theO365Admin folder on drive C, but you can save it wherever you want.</span></span>

<span data-ttu-id="4f75b-161">Laten we nu een aantal personen voor verschillende groepen op verschillende sites verwijderen met hetzelfde CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="4f75b-161">Now, let's remove a bunch of people for several groups in different sites using the same CSV file.</span></span> <span data-ttu-id="4f75b-162">Hier is een voorbeeldopdracht:</span><span class="sxs-lookup"><span data-stu-id="4f75b-162">Here is an example command:</span></span>

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a><span data-ttu-id="4f75b-163">Gebruikersrapporten genereren</span><span class="sxs-lookup"><span data-stu-id="4f75b-163">Generate user reports</span></span>

<span data-ttu-id="4f75b-164">Mogelijk wilt u een eenvoudig rapport voor een paar sites krijgen en de gebruikers weergeven voor deze sites, hun machtigingsniveau en andere eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="4f75b-164">You might want to get a simple report for a few sites and display the users for those sites, their permission level, and other properties.</span></span> <span data-ttu-id="4f75b-165">De syntaxis ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="4f75b-165">This is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="4f75b-166">Hiermee worden de gegevens voor deze drie sites verzameld en naar een tekstbestand op uw lokale station geschreven.</span><span class="sxs-lookup"><span data-stu-id="4f75b-166">This will grab the data for these three sites and write them to a text file on your local drive.</span></span> <span data-ttu-id="4f75b-167">De parameter –Toevoegen voegt nieuwe inhoud toe aan een bestaand bestand.</span><span class="sxs-lookup"><span data-stu-id="4f75b-167">Note that the parameter –Append will add new content to an existing file.</span></span>

<span data-ttu-id="4f75b-168">Laten we bijvoorbeeld een rapport uitvoeren op de sites ContosoTest, TeamSite01 en Project01 voor de Contoso1-tenant:</span><span class="sxs-lookup"><span data-stu-id="4f75b-168">For example, let's run a report on the ContosoTest, TeamSite01, and Project01 sites for the Contoso1 tenant:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="4f75b-169">Houd er rekening mee dat we alleen de variabele **$site** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="4f75b-169">Note that we had to change only the **$site** variable.</span></span> <span data-ttu-id="4f75b-170">De **$tenant** variabele behoudt de waarde door alle drie de runs van de opdracht.</span><span class="sxs-lookup"><span data-stu-id="4f75b-170">The **$tenant** variable keeps its value through all three runs of the command.</span></span>

<span data-ttu-id="4f75b-171">Maar wat als u dit voor elke site wilt doen?</span><span class="sxs-lookup"><span data-stu-id="4f75b-171">However, what if you wanted to do this for every site?</span></span> <span data-ttu-id="4f75b-172">U kunt dit doen zonder dat u al deze websites hoeft te typen met behulp van deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="4f75b-172">You can do this without having to type all those websites by using this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="4f75b-173">Dit rapport is vrij eenvoudig en u kunt meer code toevoegen om specifiekere rapporten of rapporten te maken met meer gedetailleerde informatie.</span><span class="sxs-lookup"><span data-stu-id="4f75b-173">This report is fairly simple, and you can add more code to create more specific reports or reports that include more detailed information.</span></span> <span data-ttu-id="4f75b-174">Maar dit moet u een idee geven van hoe u de SharePoint Online Management Shell kunt gebruiken om gebruikers te beheren in de SharePoint Online-omgeving.</span><span class="sxs-lookup"><span data-stu-id="4f75b-174">But this should give you an idea of how to use the SharePoint Online Management Shell to manage users in the SharePoint Online environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f75b-175">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4f75b-175">See also</span></span>

[<span data-ttu-id="4f75b-176">Verbinding maken om SharePoint Online PowerShell te gebruiken</span><span class="sxs-lookup"><span data-stu-id="4f75b-176">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[<span data-ttu-id="4f75b-177">SharePoint Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f75b-177">Manage SharePoint Online with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="4f75b-178">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f75b-178">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="4f75b-179">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4f75b-179">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
