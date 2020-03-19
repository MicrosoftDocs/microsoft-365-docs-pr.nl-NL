---
title: Beheren wie Office 365-groepen kunnen maken
f1.keywords:
- NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Meer informatie over hoe u bepalen welke gebruikers Office 365-groepen kunnen maken.
ms.openlocfilehash: a6016f6406b211aae216702910a696be50e1b82c
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807381"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="c4db3-103">Beheren wie Office 365-groepen kunnen maken</span><span class="sxs-lookup"><span data-stu-id="c4db3-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="c4db3-104">Gebruikers kunnen eenvoudig zelf Office 365-groepen maken, dus u wordt niet langer overspoeld met aanvragen ze namens anderen te maken.</span><span class="sxs-lookup"><span data-stu-id="c4db3-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="c4db3-105">Afhankelijk van uw bedrijf wilt u wellicht zelf bepalen wie er groepen kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="c4db3-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="c4db3-106">In dit artikel wordt uitgelegd hoe u de mogelijkheid om groepen te maken kunt uitschakelen **in alle Office 365-services met groepen**:</span><span class="sxs-lookup"><span data-stu-id="c4db3-106">This article explains how to disable the ability to create groups **in all Office 365 services that use groups**:</span></span> 
  
- <span data-ttu-id="c4db3-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4db3-107">Outlook</span></span>
    
- <span data-ttu-id="c4db3-108">Sharepoint</span><span class="sxs-lookup"><span data-stu-id="c4db3-108">SharePoint</span></span>
    
- <span data-ttu-id="c4db3-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="c4db3-109">Yammer</span></span>
    
- <span data-ttu-id="c4db3-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4db3-110">Microsoft Teams</span></span>

- <span data-ttu-id="c4db3-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="c4db3-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="c4db3-112">StaffHub StaffHub</span><span class="sxs-lookup"><span data-stu-id="c4db3-112">StaffHub</span></span>
    
- <span data-ttu-id="c4db3-113">Planner</span><span class="sxs-lookup"><span data-stu-id="c4db3-113">Planner</span></span>
    
- <span data-ttu-id="c4db3-114">PowerBI (PowerBI)</span><span class="sxs-lookup"><span data-stu-id="c4db3-114">PowerBI</span></span>

- <span data-ttu-id="c4db3-115">Routekaart</span><span class="sxs-lookup"><span data-stu-id="c4db3-115">Roadmap</span></span>
    
<span data-ttu-id="c4db3-116">U het maken van Office 365-groepen beperken tot de leden van een bepaalde beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="c4db3-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="c4db3-117">Als u dit wilt configureren, gebruikt u Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4db3-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="c4db3-118">Dit artikel leidt u door de benodigde stappen.</span><span class="sxs-lookup"><span data-stu-id="c4db3-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="c4db3-119">De stappen in dit artikel verhinderen niet dat leden van bepaalde rollen groepen kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="c4db3-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="c4db3-120">Office 365 Global-beheerders kunnen groepen maken op alle mogelijke manieren, zoals het Microsoft 365-beheercentrum, Planner, Teams, Exchange en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c4db3-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="c4db3-121">Andere rollen kunnen groepen maken via beperkte middelen, hieronder vermeld.</span><span class="sxs-lookup"><span data-stu-id="c4db3-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="c4db3-122">Exchange-beheerder: Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c4db3-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="c4db3-123">Ondersteuning voor partnerniveau 1: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c4db3-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="c4db3-124">Ondersteuning voor partnerniveau 2: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c4db3-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="c4db3-125">Directory-schrijvers: Azure AD</span><span class="sxs-lookup"><span data-stu-id="c4db3-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="c4db3-126">SharePoint-beheerder: SharePoint-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c4db3-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="c4db3-127">Teams Service Administrator: Teams Admin center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c4db3-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="c4db3-128">Beheerder van gebruikersbeheer: Microsoft 365-beheercentrum, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c4db3-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="c4db3-129">Als u lid bent van een van deze rollen, kunt u Office 365 Groepen maken voor gebruikers met beperkte toegang, en vervolgens de gebruiker instellen als de eigenaar van de groep.</span><span class="sxs-lookup"><span data-stu-id="c4db3-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="c4db3-130">Gebruikers met deze rol kunnen verbonden groepen maken in Yammer, ongeacht de PowerShell-instellingen die het maken van het maken kunnen voorkomen.</span><span class="sxs-lookup"><span data-stu-id="c4db3-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="c4db3-131">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="c4db3-131">Licensing requirements</span></span>

<span data-ttu-id="c4db3-132">Als u wilt beheren wie groepen maakt, hebben de volgende personen Azure AD Premium-licenties of Azure AD Basic EDU-licenties nodig:</span><span class="sxs-lookup"><span data-stu-id="c4db3-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="c4db3-133">De beheerder die deze instellingen voor het maken van groepen configureert</span><span class="sxs-lookup"><span data-stu-id="c4db3-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="c4db3-134">De leden van de beveiligingsgroep die groepen mogen maken</span><span class="sxs-lookup"><span data-stu-id="c4db3-134">The members of the security group who are allowed to create Groups</span></span>

<span data-ttu-id="c4db3-135">De volgende personen hebben azure AD Premium- of Azure AD Basic EDU-licenties niet nodig:</span><span class="sxs-lookup"><span data-stu-id="c4db3-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="c4db3-136">Mensen die lid zijn van Office 365-groepen en die niet de mogelijkheid hebben om andere groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="c4db3-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="c4db3-137">Stap 1: een beveiligingsgroep maken voor gebruikers die Office 365 Groepen moeten kunnen maken</span><span class="sxs-lookup"><span data-stu-id="c4db3-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="c4db3-138">Er kan slechts één beveiligingsgroep in uw organisatie worden gebruikt om te bepalen wie groepen kan maken.</span><span class="sxs-lookup"><span data-stu-id="c4db3-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="c4db3-139">U kunt wel andere beveiligingsgroepen nesten als leden van deze groep.</span><span class="sxs-lookup"><span data-stu-id="c4db3-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="c4db3-140">Voorbeeld: de groep met de naam Groep maken toestaan is de aangewezen beveiligingsgroep en de groepen met de naam Microsoft Planner-gebruikers en Exchange Online-gebruikers zijn lid van die groep.</span><span class="sxs-lookup"><span data-stu-id="c4db3-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="c4db3-141">Beheerders in de hierboven genoemde rollen hoeven geen lid te zijn van deze groep: ze behouden hun vermogen om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="c4db3-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4db3-142">Zorg ervoor dat u een **beveiligingsgroep** gebruikt om te beperken wie groepen kan maken.</span><span class="sxs-lookup"><span data-stu-id="c4db3-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="c4db3-143">Als u hiervoor een Office 365-groep gebruikt, kunnen leden geen groep maken vanuit SharePoint, omdat er op een beveiligingsgroep wordt gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="c4db3-143">If you try to use an Office 365 Group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="c4db3-144">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepengroepen.</a> **Groups**</span><span class="sxs-lookup"><span data-stu-id="c4db3-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="c4db3-145">Klik op **Een groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c4db3-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="c4db3-146">Kies **Beveiliging** als groepstype.</span><span class="sxs-lookup"><span data-stu-id="c4db3-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="c4db3-147">Onthoud de naam van de groep goed.</span><span class="sxs-lookup"><span data-stu-id="c4db3-147">Remember the name of the group!</span></span> <span data-ttu-id="c4db3-148">Deze hebt u later nodig.</span><span class="sxs-lookup"><span data-stu-id="c4db3-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="c4db3-149">Werk de beveiligingsgroep in en voeg mensen of andere beveiligingsgroepen toe die u groepen in uw organisatie wilt kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="c4db3-149">Finish setting up the security group, adding people or other security groups who you want to be able to create Groups in your org.</span></span>
    
<span data-ttu-id="c4db3-150">Zie [Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-beheercentrum](../email/create-edit-or-delete-a-security-group.md)voor gedetailleerde instructies.</span><span class="sxs-lookup"><span data-stu-id="c4db3-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
  
## <a name="step-2-install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="c4db3-151">Stap 2: De preview-versie van de Azure Active Directory PowerShell voor Grafiek installeren</span><span class="sxs-lookup"><span data-stu-id="c4db3-151">Step 2: Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

<span data-ttu-id="c4db3-152">Deze procedures vereisen de preview-versie van de Azure Active Directory PowerShell voor Grafiek.</span><span class="sxs-lookup"><span data-stu-id="c4db3-152">These procedures require the preview version of the Azure Active Directory PowerShell for Graph.</span></span> <span data-ttu-id="c4db3-153">De GA-versie werkt niet.</span><span class="sxs-lookup"><span data-stu-id="c4db3-153">The GA version will not work.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c4db3-154">U de preview- en GA-versies niet tegelijkertijd op dezelfde computer installeren.</span><span class="sxs-lookup"><span data-stu-id="c4db3-154">You cannot install both the preview and GA versions on the same computer at the same time.</span></span> <span data-ttu-id="c4db3-155">U de module installeren op Windows 10, Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="c4db3-155">You can install the module on Windows 10, Windows Server 2016.</span></span>

  
<span data-ttu-id="c4db3-156">Als aanbevolen procedure wordt aangeraden  *altijd*  bij te blijven: verwijder de oude AzureADPreview- of AzureAD-versie en installeer de meest recente versie.</span><span class="sxs-lookup"><span data-stu-id="c4db3-156">As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
1. <span data-ttu-id="c4db3-157">Type Windows PowerShell in de zoekbalk.</span><span class="sxs-lookup"><span data-stu-id="c4db3-157">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="c4db3-158">Klik met de rechtermuisknop op **Windows PowerShell** en selecteer **Als administrator uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="c4db3-158">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
    
    ![Open PowerShell met 'Als administrator uitvoeren.'](../../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
    
3. <span data-ttu-id="c4db3-160">Stel het beleid in op RemoteSigned met [het beleid voor uitvoering instellen](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span><span class="sxs-lookup"><span data-stu-id="c4db3-160">Set the policy to RemoteSigned by using [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span></span>
    
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
  
4. <span data-ttu-id="c4db3-161">Controleer de geïnstalleerde module:</span><span class="sxs-lookup"><span data-stu-id="c4db3-161">Check installed module:</span></span>
    
    ```
    Get-InstalledModule -Name "AzureAD*"
    ```

5. <span data-ttu-id="c4db3-162">Als u een eerdere versie van AzureADPreview of AzureAD wilt verwijderen, moet u deze opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="c4db3-162">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
    ```
    Uninstall-Module AzureADPreview
    ```

    <span data-ttu-id="c4db3-163">of</span><span class="sxs-lookup"><span data-stu-id="c4db3-163">or</span></span>
  
    ```
    Uninstall-Module AzureAD
    ```

6. <span data-ttu-id="c4db3-164">Als u de meest recente versie van AzureADPreview wilt installeren, moet u deze opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="c4db3-164">To install the latest version of AzureADPreview, run this command:</span></span>
  
    ```
    Install-Module AzureADPreview
    ```

    <span data-ttu-id="c4db3-165">Typ bij het bericht over een niet-vertrouwde opslagplaats: **Y**. Het installeren van de nieuwe module duurt ongeveer een minuut.</span><span class="sxs-lookup"><span data-stu-id="c4db3-165">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>

<span data-ttu-id="c4db3-166">Laat het PowerShell-venster open voor stap 3, hieronder.</span><span class="sxs-lookup"><span data-stu-id="c4db3-166">Leave the PowerShell window open for Step 3, below.</span></span>
  
## <a name="step-3-run-powershell-commands"></a><span data-ttu-id="c4db3-167">Stap 3: PowerShell-opdrachten uitvoeren</span><span class="sxs-lookup"><span data-stu-id="c4db3-167">Step 3: Run PowerShell commands</span></span>

<span data-ttu-id="c4db3-168">Kopieer het onderstaande script naar een teksteditor, zoals Kladblok of het [Windows PowerShell ISE.](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="c4db3-168">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="c4db3-169">\* \<Vervang SecurityGroupName\> \* door de naam van de beveiligingsgroep die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c4db3-169">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="c4db3-170">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c4db3-170">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="c4db3-171">Sla het bestand op als GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="c4db3-171">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="c4db3-172">Navigeer in het PowerShell-venster naar de locatie waar <FileLocation>u het bestand hebt opgeslagen (typ 'CD').</span><span class="sxs-lookup"><span data-stu-id="c4db3-172">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="c4db3-173">Voer het script uit door te typen:</span><span class="sxs-lookup"><span data-stu-id="c4db3-173">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="c4db3-174">en [meld u aan met uw beheerdersaccount](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) wanneer daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="c4db3-174">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="c4db3-175">De laatste regel van het script geeft de bijgewerkte instellingen weer:</span><span class="sxs-lookup"><span data-stu-id="c4db3-175">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="c4db3-177">Als u in de toekomst wilt wijzigen welke beveiligingsgroep wordt gebruikt, u het script opnieuw uitvoeren met de naam van de nieuwe beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="c4db3-177">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="c4db3-178">Als u de beperking voor het maken van groepen wilt uitschakelen en alle gebruikers opnieuw wilt toestaan groepen te maken, stelt u $GroupName in op '' en $AllowGroupCreation op 'Waar' en voert u het script opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="c4db3-178">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="c4db3-179">Stap 4: Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="c4db3-179">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="c4db3-180">Meld u aan bij Office 365 met een gebruikersaccount van iemand die NIET in staat mag zijn om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="c4db3-180">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="c4db3-181">Dat wil zeggen dat ze geen lid zijn van de beveiligingsgroep die u hebt gemaakt of een beheerder.</span><span class="sxs-lookup"><span data-stu-id="c4db3-181">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="c4db3-182">Selecteer de tegel **Planner.**</span><span class="sxs-lookup"><span data-stu-id="c4db3-182">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="c4db3-183">Selecteer in Planner **Nieuw plan** in de linkernavigatie om een plan te maken.</span><span class="sxs-lookup"><span data-stu-id="c4db3-183">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="c4db3-184">U moet een bericht ontvangen dat het plannen en het maken van groepen is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c4db3-184">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="c4db3-185">Probeer dezelfde procedure opnieuw met een lid van de beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="c4db3-185">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="c4db3-186">Als leden van de beveiligingsgroep geen groepen kunnen maken, controleert u of ze niet worden geblokkeerd via hun [OWA-postvakbeleid.](https://go.microsoft.com/fwlink/?linkid=852135)</span><span class="sxs-lookup"><span data-stu-id="c4db3-186">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="c4db3-187">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="c4db3-187">Related articles</span></span>

[<span data-ttu-id="c4db3-188">Getting started with Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4db3-188">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="c4db3-189">Selfservicegroepsbeheer instellen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4db3-189">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="c4db3-190">Beleid voor setuitvoering</span><span class="sxs-lookup"><span data-stu-id="c4db3-190">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="c4db3-191">Azure Active Directory-cmdlets voor het configureren van groepsinstellingen</span><span class="sxs-lookup"><span data-stu-id="c4db3-191">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
