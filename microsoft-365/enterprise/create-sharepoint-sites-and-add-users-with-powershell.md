---
title: SharePoint Online-sites maken en gebruikers toevoegen met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: 'Overzicht: PowerShell gebruiken om nieuwe SharePoint Online-sites te maken en vervolgens gebruikers en groepen aan deze sites toe te voegen.'
ms.openlocfilehash: 28a51cc39fe838f6c7f9c50e9d750d28e5d830c4
ms.sourcegitcommit: 24ccb910ffac4d065c512a57c5decd9dd19ef4c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594916"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="5e2f9-103">SharePoint Online-sites maken en gebruikers toevoegen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e2f9-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="5e2f9-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5e2f9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5e2f9-105">Wanneer u PowerShell voor Microsoft 365 gebruikt om SharePoint Online-sites te maken en gebruikers toe te voegen, kunt u snel en herhaaldelijk taken sneller uitvoeren dan in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5e2f9-106">Het is ook mogelijk om taken uit te voeren die niet beschikbaar zijn in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="5e2f9-107">Verbinding maken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5e2f9-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="5e2f9-108">Voor de procedures in dit onderwerp moet u verbinding maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="5e2f9-109">Zie [verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) voor instructies</span><span class="sxs-lookup"><span data-stu-id="5e2f9-109">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="5e2f9-110">Stap 1: Maak nieuwe siteverzamelingen met behulp van PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e2f9-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="5e2f9-111">Maak meerdere sites met behulp van PowerShell en een CSV-bestand dat u maakt met behulp van de voorbeeldcode en het Kladblok.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="5e2f9-112">Voor deze procedure vervangt u de informatie over de tijdelijke aanduiding tussen vierkante haken met uw eigen site-en Tenant informatie.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="5e2f9-113">Met deze procedure kunt u één bestand maken en één PowerShell-opdracht uitvoeren waarbij dat bestand wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="5e2f9-114">Dit zorgt ervoor dat de acties zowel herhalen als verplaatsbaar zijn en veel, indien niet allen, van invloed zijn op het typen van lange opdrachten in de SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="5e2f9-115">Deze procedure bestaat uit twee gedeelten.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-115">There are two parts to this procedure.</span></span> <span data-ttu-id="5e2f9-116">Eerst maakt u een CSV-bestand en gaat u naar het CSV-bestand met behulp van PowerShell, waarin de inhoud wordt gebruikt om de sites te maken.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="5e2f9-117">De PowerShell-cmdlet importeert het CSV-bestand en sluist in een lus binnen de accolades die de eerste regel van het bestand als kolomkoppen leest.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="5e2f9-118">De PowerShell-cmdlet belegt vervolgens de resterende records, maakt een nieuwe siteverzameling voor elke record en wijst eigenschappen van de siteverzameling toe op basis van de kolomkoppen.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="5e2f9-119">Een CSV-bestand maken</span><span class="sxs-lookup"><span data-stu-id="5e2f9-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="5e2f9-120">De parameter resource quotum werkt alleen op klassieke sites.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="5e2f9-121">Als u deze parameter op een moderne site gebruikt, ontvangt u mogelijk een waarschuwingsbericht dat is afgeschaft.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span> 

1. <span data-ttu-id="5e2f9-122">Open Kladblok en plak de volgende tekst blokkering erin:</span><span class="sxs-lookup"><span data-stu-id="5e2f9-122">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="5e2f9-123">Waarbij *Tenant* de naam van de Tenant is en *eigenaar* de gebruikersnaam is van de gebruiker in de Tenant waaraan u de rol van primaire beheerder van de siteverzameling wilt verlenen.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="5e2f9-124">(Druk op CTRL + H wanneer u Kladblok gebruikt om de bulk sneller te vervangen.)</span><span class="sxs-lookup"><span data-stu-id="5e2f9-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="5e2f9-125">Sla het bestand op uw bureaublad op als **SiteCollections.csv**.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-125">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="5e2f9-126">Voordat u dit of een ander. CSV-of Windows PowerShell-scriptbestand gebruikt, is het een goede gewoonte om ervoor te zorgen dat er geen overbodige of niet-afdrukbare tekens zijn.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="5e2f9-127">Open het bestand in Word en klik op het lint op het pictogram alinea om niet-afdrukbare tekens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="5e2f9-128">Er moeten geen overbodige niet-afdrukbare tekens zijn.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="5e2f9-129">Dit kan bijvoorbeeld geen alineamarkeringen buiten de laatste aan het einde van het bestand bevatten.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="5e2f9-130">De Windows PowerShell-opdracht uitvoeren</span><span class="sxs-lookup"><span data-stu-id="5e2f9-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="5e2f9-131">Typ of kopieer en plak de volgende opdracht bij de Windows PowerShell-prompt en druk op ENTER:</span><span class="sxs-lookup"><span data-stu-id="5e2f9-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="5e2f9-132">Waarbij *Mijn alias* gelijk is aan uw alias voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-132">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="5e2f9-133">Wacht totdat de Windows PowerShell-prompt opnieuw wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-133">Wait for the Windows PowerShell prompt to reappear.</span></span> <span data-ttu-id="5e2f9-134">Het kan een paar minuten duren.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-134">It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="5e2f9-135">Typ of kopieer en plak de volgende cmdlet achter de Windows PowerShell-prompt en druk op ENTER:</span><span class="sxs-lookup"><span data-stu-id="5e2f9-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="5e2f9-136">Let op de nieuwe siteverzamelingen in de lijst.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-136">Note the new site collections in the list.</span></span> <span data-ttu-id="5e2f9-137">Als u het CSV-voorbeeldbestand gebruikt, ziet u de volgende siteverzamelingen: **TeamSite01**, **Blog01**, **Project01**en **Community01**</span><span class="sxs-lookup"><span data-stu-id="5e2f9-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="5e2f9-138">Dat is alles.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-138">That’s it.</span></span> <span data-ttu-id="5e2f9-139">U hebt meerdere siteverzamelingen gemaakt met het. CSV-bestand dat u hebt gemaakt en één Windows PowerShell-opdracht.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="5e2f9-140">U bent nu klaar om gebruikers te maken en toe te wijzen aan deze sites.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="5e2f9-141">Stap 2: gebruikers en groepen toevoegen</span><span class="sxs-lookup"><span data-stu-id="5e2f9-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="5e2f9-142">U gaat nu gebruikers maken en deze toevoegen aan een siteverzamelingsgroep.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-142">Now you’re going to create users and add them to a site collection group.</span></span> <span data-ttu-id="5e2f9-143">Vervolgens gebruikt u een CSV-bestand om nieuwe groepen en gebruikers bulksgewijs te uploaden.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-143">You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="5e2f9-144">De volgende procedures gaan verder met de voorbeeld sites TeamSite01, Blog01, Project01 en Community01.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="5e2f9-145">CSV-en ps1-bestanden maken</span><span class="sxs-lookup"><span data-stu-id="5e2f9-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="5e2f9-146">Open Kladblok en plak de volgende tekst blokkering erin:</span><span class="sxs-lookup"><span data-stu-id="5e2f9-146">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/><span data-ttu-id="5e2f9-147">Dit *is de* naam van de Tenant en de naam van de Tenant.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-147">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="5e2f9-148">Sla het bestand op uw bureaublad op als **GroupsAndPermissions.csv**.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="5e2f9-149">Open een nieuw exemplaar van Kladblok en plak het volgende tekstblok in het Kladblok:</span><span class="sxs-lookup"><span data-stu-id="5e2f9-149">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/><span data-ttu-id="5e2f9-150">Dit *is de* naam van de Tenant en de *gebruikersnaam is gelijk aan* de gebruikersnaam van een bestaande gebruiker.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="5e2f9-151">Sla het bestand op uw bureaublad op als **Users.csv**.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-151">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="5e2f9-152">Open een nieuw exemplaar van Kladblok en plak het volgende tekstblok in het Kladblok:</span><span class="sxs-lookup"><span data-stu-id="5e2f9-152">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="5e2f9-153">Waarbij mijn alias gelijk is aan de gebruikersnaam van de gebruiker die op dat moment is aangemeld.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="5e2f9-154">Sla het bestand op uw bureaublad op als **UsersAndGroups.ps1**.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="5e2f9-155">Dit is een eenvoudig Windows PowerShell-script.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="5e2f9-156">U bent nu klaar om het UsersAndGroup.ps1 script uit te voeren om gebruikers en groepen toe te voegen aan meerdere siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="5e2f9-157">UsersAndGroups.ps1 script uitvoeren</span><span class="sxs-lookup"><span data-stu-id="5e2f9-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="5e2f9-158">Ga terug naar de SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-158">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="5e2f9-159">Typ of kopieer en plak de volgende regel in de Windows PowerShell-prompt en druk op ENTER:</span><span class="sxs-lookup"><span data-stu-id="5e2f9-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="5e2f9-160">Druk op **Y**wanneer u om een bevestiging wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-160">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="5e2f9-161">Typ of kopieer en plak de volgende tekst bij de Windows PowerShell-prompt en druk op ENTER:</span><span class="sxs-lookup"><span data-stu-id="5e2f9-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="5e2f9-162">Waarbij *Mijn alias* gelijk is aan uw gebruikersnaam.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-162">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="5e2f9-163">Wacht totdat de prompt wordt weergegeven voordat u verdergaat.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-163">Wait for the prompt to return before moving on.</span></span> <span data-ttu-id="5e2f9-164">U ziet eerst welke groepen worden weergegeven wanneer ze worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-164">You will first see the groups appear as they are created.</span></span> <span data-ttu-id="5e2f9-165">Vervolgens wordt de groepslijst herhaald wanneer gebruikers worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="5e2f9-165">Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e2f9-166">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5e2f9-166">See also</span></span>

[<span data-ttu-id="5e2f9-167">Verbinding maken met SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e2f9-167">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="5e2f9-168">SharePoint Online-sitegroepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e2f9-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="5e2f9-169">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e2f9-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5e2f9-170">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5e2f9-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
