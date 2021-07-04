---
title: Onlinesites SharePoint en gebruikers toevoegen met PowerShell
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
description: 'Overzicht: Gebruik PowerShell om nieuwe SharePoint onlinesites te maken en vervolgens gebruikers en groepen aan deze sites toe te voegen.'
ms.openlocfilehash: 0c363df3edd40d810a0d8ca63090c0fec4c1c155
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288657"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="f464c-103">Onlinesites SharePoint en gebruikers toevoegen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f464c-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="f464c-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f464c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f464c-105">Wanneer u PowerShell voor Microsoft 365 gebruikt om SharePoint Online-sites te maken en gebruikers toe te voegen, kunt u snel en herhaaldelijk taken veel sneller uitvoeren dan in de Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="f464c-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f464c-106">U kunt ook taken uitvoeren die niet kunnen worden uitgevoerd in de Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="f464c-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="f464c-107">Verbinding maken online SharePoint online</span><span class="sxs-lookup"><span data-stu-id="f464c-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="f464c-108">Voor de procedures in dit onderwerp moet u verbinding maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f464c-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="f464c-109">Zie Verbinding maken [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) voor instructies</span><span class="sxs-lookup"><span data-stu-id="f464c-109">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="f464c-110">Stap 1: Nieuwe siteverzamelingen maken met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f464c-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="f464c-111">Maak meerdere sites met PowerShell en een .csv bestand dat u maakt met behulp van de opgegeven voorbeeldcode en Kladblok.</span><span class="sxs-lookup"><span data-stu-id="f464c-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="f464c-112">Voor deze procedure vervangt u de tijdelijke aanduidingen tussen haakjes door uw eigen site- en tenantspecifieke informatie.</span><span class="sxs-lookup"><span data-stu-id="f464c-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="f464c-113">Met dit proces kunt u één bestand maken en één PowerShell-opdracht uitvoeren waarin dat bestand wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f464c-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="f464c-114">Hierdoor kunnen de acties die worden ondernomen, zowel herhaalbaar als overdraagbaar zijn en worden veel, zo niet alle, fouten weggewerkt die kunnen ontstaan door lange opdrachten te typen in de SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f464c-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="f464c-115">Deze procedure bestaat uit twee onderdelen.</span><span class="sxs-lookup"><span data-stu-id="f464c-115">There are two parts to this procedure.</span></span> <span data-ttu-id="f464c-116">Eerst maakt u een .csv bestand en vervolgens verwijst u naar dat .csv-bestand met PowerShell, waarmee de inhoud ervan wordt gebruikt om de sites te maken.</span><span class="sxs-lookup"><span data-stu-id="f464c-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="f464c-117">De PowerShell-cmdlet importeert het .csv-bestand en voert deze naar een lus in de gekrulde haken die de eerste regel van het bestand als kolomkoppen leest.</span><span class="sxs-lookup"><span data-stu-id="f464c-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="f464c-118">De PowerShell-cmdlet itereert vervolgens door de resterende records, maakt een nieuwe siteverzameling voor elke record en wijst eigenschappen van de siteverzameling toe op basis van de kolomkoppen.</span><span class="sxs-lookup"><span data-stu-id="f464c-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="f464c-119">Een .csv maken</span><span class="sxs-lookup"><span data-stu-id="f464c-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="f464c-120">De resourcequotaparameter werkt alleen op klassieke sites.</span><span class="sxs-lookup"><span data-stu-id="f464c-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="f464c-121">Als u deze parameter op een moderne site gebruikt, ontvangt u mogelijk een waarschuwing dat deze is afgeschaft.</span><span class="sxs-lookup"><span data-stu-id="f464c-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span>

1. <span data-ttu-id="f464c-122">Open Kladblok en plak het volgende tekstblok er in:</span><span class="sxs-lookup"><span data-stu-id="f464c-122">Open Notepad, and paste the following text block into it:</span></span>

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   <span data-ttu-id="f464c-123">Waarbij *tenant* de naam van uw tenant *is* en de eigenaar de gebruikersnaam is van de gebruiker op uw tenant aan wie u de rol van primaire beheerder van de siteverzameling wilt verlenen.</span><span class="sxs-lookup"><span data-stu-id="f464c-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span>

   <span data-ttu-id="f464c-124">(U kunt op Ctrl+H drukken wanneer u de Kladblok gebruikt om sneller bulksgewijs te vervangen.)</span><span class="sxs-lookup"><span data-stu-id="f464c-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span>

2. <span data-ttu-id="f464c-125">Sla het bestand op uw bureaublad op **alsSiteCollections.csv.**</span><span class="sxs-lookup"><span data-stu-id="f464c-125">Save the file on your desktop as **SiteCollections.csv**.</span></span>

> [!TIP]
> <span data-ttu-id="f464c-126">Voordat u dit of een ander .csv of Windows PowerShell scriptbestand gebruikt, is het een goede gewoonte om ervoor te zorgen dat er geen overbodige of niet-afdrukbare tekens zijn.</span><span class="sxs-lookup"><span data-stu-id="f464c-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="f464c-127">Open het bestand in Word en klik op het lint op het alineapictogram om niet-afdrukbare tekens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="f464c-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="f464c-128">Er mogen geen overbodige niet-afdrukbare tekens zijn.</span><span class="sxs-lookup"><span data-stu-id="f464c-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="f464c-129">Er mogen bijvoorbeeld geen alineamarkeringen achter de laatste alineamarkeringen aan het einde van het bestand staan.</span><span class="sxs-lookup"><span data-stu-id="f464c-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="f464c-130">De opdracht Windows PowerShell uitvoeren</span><span class="sxs-lookup"><span data-stu-id="f464c-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="f464c-131">Typ Windows PowerShell en plak de volgende opdracht en druk op Enter:</span><span class="sxs-lookup"><span data-stu-id="f464c-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span>

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   <span data-ttu-id="f464c-132">Waarbij *MyAlias* gelijk is aan uw gebruikersalias.</span><span class="sxs-lookup"><span data-stu-id="f464c-132">Where *MyAlias* equals your user alias.</span></span>

2. <span data-ttu-id="f464c-133">Wacht totdat de Windows PowerShell wordt opnieuw verschijnt.</span><span class="sxs-lookup"><span data-stu-id="f464c-133">Wait for the Windows PowerShell prompt to reappear.</span></span> <span data-ttu-id="f464c-134">Het kan een paar minuten duren.</span><span class="sxs-lookup"><span data-stu-id="f464c-134">It might take a minute or two.</span></span>

3. <span data-ttu-id="f464c-135">Typ Windows PowerShell of kopieer en plak de volgende cmdlet en druk op Enter:</span><span class="sxs-lookup"><span data-stu-id="f464c-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span>

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. <span data-ttu-id="f464c-136">Let op de nieuwe siteverzamelingen in de lijst.</span><span class="sxs-lookup"><span data-stu-id="f464c-136">Note the new site collections in the list.</span></span> <span data-ttu-id="f464c-137">Als u ons voorbeeld CSV-bestand gebruikt, ziet u de volgende siteverzamelingen: **TeamSite01,** **Blog01,** **Project01** en **Community01**</span><span class="sxs-lookup"><span data-stu-id="f464c-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="f464c-138">Dat is alles.</span><span class="sxs-lookup"><span data-stu-id="f464c-138">That’s it.</span></span> <span data-ttu-id="f464c-139">U hebt meerdere siteverzamelingen gemaakt met het .csv bestand dat u hebt gemaakt en één opdracht Windows PowerShell maken.</span><span class="sxs-lookup"><span data-stu-id="f464c-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="f464c-140">U bent nu klaar om gebruikers aan deze sites te maken en toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="f464c-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="f464c-141">Stap 2: Gebruikers en groepen toevoegen</span><span class="sxs-lookup"><span data-stu-id="f464c-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="f464c-142">U gaat nu gebruikers maken en toevoegen aan een groep siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="f464c-142">Now you’re going to create users and add them to a site collection group.</span></span> <span data-ttu-id="f464c-143">Vervolgens gebruikt u een .csv om nieuwe groepen en gebruikers bulksgewijs te uploaden.</span><span class="sxs-lookup"><span data-stu-id="f464c-143">You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="f464c-144">In de volgende procedures worden de voorbeeldsites TeamSite01, Blog01, Project01 en Community01 gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f464c-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="f464c-145">Bestanden .csv en .ps1 maken</span><span class="sxs-lookup"><span data-stu-id="f464c-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="f464c-146">Open Kladblok en plak het volgende tekstblok er in:</span><span class="sxs-lookup"><span data-stu-id="f464c-146">Open Notepad, and paste the following text block into it:</span></span>

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

   <span data-ttu-id="f464c-147">Waarbij *tenant* gelijk is aan uw tenantnaam.</span><span class="sxs-lookup"><span data-stu-id="f464c-147">Where *tenant* equals your tenant name.</span></span>

2. <span data-ttu-id="f464c-148">Sla het bestand op uw bureaublad op **alsGroupsAndPermissions.csv.**</span><span class="sxs-lookup"><span data-stu-id="f464c-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span>

3. <span data-ttu-id="f464c-149">Open een nieuw exemplaar van Kladblok en plak het volgende tekstblok er in:</span><span class="sxs-lookup"><span data-stu-id="f464c-149">Open a new instance of Notepad, and paste the following text block into it:</span></span>

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

   <span data-ttu-id="f464c-150">Waarbij *tenant* gelijk is aan uw tenantnaam en *gebruikersnaam* gelijk is aan de gebruikersnaam van een bestaande gebruiker.</span><span class="sxs-lookup"><span data-stu-id="f464c-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span>

4. <span data-ttu-id="f464c-151">Sla het bestand op uw bureaublad op **alsUsers.csv.**</span><span class="sxs-lookup"><span data-stu-id="f464c-151">Save the file to your desktop as **Users.csv**.</span></span>

5. <span data-ttu-id="f464c-152">Open een nieuw exemplaar van Kladblok en plak het volgende tekstblok er in:</span><span class="sxs-lookup"><span data-stu-id="f464c-152">Open a new instance of Notepad, and paste the following text block into it:</span></span>

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   <span data-ttu-id="f464c-153">Waarbij MyAlias gelijk is aan de gebruikersnaam van de gebruiker die momenteel is aangemeld.</span><span class="sxs-lookup"><span data-stu-id="f464c-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span>

6. <span data-ttu-id="f464c-154">Sla het bestand op uw bureaublad op **alsUsersAndGroups.ps1.**</span><span class="sxs-lookup"><span data-stu-id="f464c-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="f464c-155">Dit is een eenvoudig Windows PowerShell script.</span><span class="sxs-lookup"><span data-stu-id="f464c-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="f464c-156">U kunt nu het script UsersAndGroup.ps1 om gebruikers en groepen toe te voegen aan meerdere siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="f464c-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="f464c-157">Voer UsersAndGroups.ps1 script uit</span><span class="sxs-lookup"><span data-stu-id="f464c-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="f464c-158">Ga terug naar de SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f464c-158">Return to the SharePoint Online Management Shell.</span></span>

2. <span data-ttu-id="f464c-159">Typ of kopieer Windows PowerShell de volgende regel en druk op Enter:</span><span class="sxs-lookup"><span data-stu-id="f464c-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span>

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. <span data-ttu-id="f464c-160">Druk bij de bevestigingsprompt op **Y**.</span><span class="sxs-lookup"><span data-stu-id="f464c-160">At the confirmation prompt, press **Y**.</span></span>

4. <span data-ttu-id="f464c-161">Typ of kopieer en plak Windows PowerShell de volgende prompt en druk op Enter:</span><span class="sxs-lookup"><span data-stu-id="f464c-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span>

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   <span data-ttu-id="f464c-162">Waarbij *MyAlias* gelijk is aan uw gebruikersnaam.</span><span class="sxs-lookup"><span data-stu-id="f464c-162">Where *MyAlias* equals your user name.</span></span>

5. <span data-ttu-id="f464c-163">Wacht totdat de prompt wordt terugkomt voordat u verder gaat.</span><span class="sxs-lookup"><span data-stu-id="f464c-163">Wait for the prompt to return before moving on.</span></span> <span data-ttu-id="f464c-164">De groepen worden eerst weergegeven terwijl ze worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f464c-164">You will first see the groups appear as they are created.</span></span> <span data-ttu-id="f464c-165">Vervolgens wordt de groepslijst herhaald wanneer gebruikers worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="f464c-165">Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="f464c-166">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f464c-166">See also</span></span>

[<span data-ttu-id="f464c-167">Verbinding maken om SharePoint Online PowerShell te gebruiken</span><span class="sxs-lookup"><span data-stu-id="f464c-167">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[<span data-ttu-id="f464c-168">Online SharePoint onlinesitegroepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f464c-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="f464c-169">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f464c-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="f464c-170">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f464c-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
