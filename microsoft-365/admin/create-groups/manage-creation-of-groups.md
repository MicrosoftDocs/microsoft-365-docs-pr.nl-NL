---
title: Beheren wie Office 365-groepen kunnen maken
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
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
ms.openlocfilehash: 9016b96821dd9d40a0fb65574ce96d7badd0c2bd
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212079"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="955dd-103">Beheren wie Office 365-groepen kunnen maken</span><span class="sxs-lookup"><span data-stu-id="955dd-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="955dd-104">Gebruikers kunnen eenvoudig zelf Office 365-groepen maken, dus u wordt niet langer overspoeld met aanvragen ze namens anderen te maken.</span><span class="sxs-lookup"><span data-stu-id="955dd-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="955dd-105">Afhankelijk van uw bedrijf wilt u wellicht zelf bepalen wie er groepen kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="955dd-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="955dd-106">In dit artikel wordt uitgelegd hoe u de mogelijkheid om groepen te maken in alle Office 365-services die groepen gebruiken, uitschakelen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="955dd-106">This article explains how to disable the ability to create groups in all Office 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="955dd-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="955dd-107">Outlook</span></span>
    
- <span data-ttu-id="955dd-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="955dd-108">SharePoint</span></span>
    
- <span data-ttu-id="955dd-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="955dd-109">Yammer</span></span>
    
- <span data-ttu-id="955dd-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="955dd-110">Microsoft Teams</span></span>

- <span data-ttu-id="955dd-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="955dd-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="955dd-112">StaffHub (StaffHub)</span><span class="sxs-lookup"><span data-stu-id="955dd-112">StaffHub</span></span>
    
- <span data-ttu-id="955dd-113">Planner</span><span class="sxs-lookup"><span data-stu-id="955dd-113">Planner</span></span>
    
- <span data-ttu-id="955dd-114">PowerBI (PowerBI)</span><span class="sxs-lookup"><span data-stu-id="955dd-114">PowerBI</span></span>

- <span data-ttu-id="955dd-115">Routekaart</span><span class="sxs-lookup"><span data-stu-id="955dd-115">Roadmap</span></span>
    
<span data-ttu-id="955dd-116">U het maken van Office 365-groep beperken tot de leden van een bepaalde beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="955dd-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="955dd-117">Om dit te configureren, gebruikt u Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="955dd-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="955dd-118">Dit artikel leidt u door de nodige stappen.</span><span class="sxs-lookup"><span data-stu-id="955dd-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="955dd-119">De stappen in dit artikel verhinderen niet dat leden van bepaalde rollen groepen maken.</span><span class="sxs-lookup"><span data-stu-id="955dd-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="955dd-120">Beheerders van Office 365 Global kunnen groepen op alle mogelijke manieren maken, zoals het Microsoft 365-beheercentrum, Planner, Teams, Exchange en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="955dd-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="955dd-121">Andere rollen kunnen groepen maken via beperkte middelen, hieronder vermeld.</span><span class="sxs-lookup"><span data-stu-id="955dd-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="955dd-122">Exchange Administrator: Exchange Admin center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="955dd-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="955dd-123">Ondersteuning voor Partnerniveau 1: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="955dd-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="955dd-124">Ondersteuning voor Partnertier 2: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="955dd-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="955dd-125">Directory Writers: Azure AD</span><span class="sxs-lookup"><span data-stu-id="955dd-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="955dd-126">SharePoint-beheerder: SharePoint-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="955dd-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="955dd-127">Teams Service Administrator: Teams Admin center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="955dd-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="955dd-128">Beheerder van het beheer van gebruiker: Microsoft 365-beheercentrum, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="955dd-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="955dd-129">Als u lid bent van een van deze rollen, kunt u Office 365 Groepen maken voor gebruikers met beperkte toegang, en vervolgens de gebruiker instellen als de eigenaar van de groep.</span><span class="sxs-lookup"><span data-stu-id="955dd-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="955dd-130">Gebruikers die deze rol hebben, kunnen verbonden groepen maken in Yammer, ongeacht de PowerShell-instellingen die het maken kunnen verhinderen.</span><span class="sxs-lookup"><span data-stu-id="955dd-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="955dd-131">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="955dd-131">Licensing requirements</span></span>

<span data-ttu-id="955dd-132">Om te beheren wie groepen maakt, hebben de volgende personen Azure AD Premium-licenties of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:</span><span class="sxs-lookup"><span data-stu-id="955dd-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="955dd-133">De beheerder die deze instellingen voor het maken van groepen configureert</span><span class="sxs-lookup"><span data-stu-id="955dd-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="955dd-134">De leden van de beveiligingsgroep die groepen mogen maken</span><span class="sxs-lookup"><span data-stu-id="955dd-134">The members of the security group who are allowed to create groups</span></span>

<span data-ttu-id="955dd-135">De volgende personen hebben geen Azure AD Premium- of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:</span><span class="sxs-lookup"><span data-stu-id="955dd-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="955dd-136">Mensen die lid zijn van Office 365-groepen en die niet de mogelijkheid hebben om andere groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="955dd-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="955dd-137">Stap 1: een beveiligingsgroep maken voor gebruikers die Office 365 Groepen moeten kunnen maken</span><span class="sxs-lookup"><span data-stu-id="955dd-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="955dd-138">Er kan slechts één beveiligingsgroep in uw organisatie worden gebruikt om te bepalen wie groepen kan maken.</span><span class="sxs-lookup"><span data-stu-id="955dd-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="955dd-139">U kunt wel andere beveiligingsgroepen nesten als leden van deze groep.</span><span class="sxs-lookup"><span data-stu-id="955dd-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="955dd-140">Voorbeeld: de groep met de naam Groep maken toestaan is de aangewezen beveiligingsgroep en de groepen met de naam Microsoft Planner-gebruikers en Exchange Online-gebruikers zijn lid van die groep.</span><span class="sxs-lookup"><span data-stu-id="955dd-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="955dd-141">Beheerders in de bovenstaande rollen hoeven geen lid te zijn van deze groep: ze behouden hun mogelijkheid om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="955dd-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="955dd-142">Zorg ervoor dat u een **beveiligingsgroep** gebruikt om te beperken wie groepen kan maken.</span><span class="sxs-lookup"><span data-stu-id="955dd-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="955dd-143">Als u een Office 365-groep probeert te gebruiken, kunnen leden geen groep maken vanuit SharePoint omdat deze controleert op een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="955dd-143">If you try to use an Office 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="955dd-144">Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">groepen.</a></span><span class="sxs-lookup"><span data-stu-id="955dd-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="955dd-145">Klik op **Een groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="955dd-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="955dd-146">Kies **Beveiliging** als groepstype.</span><span class="sxs-lookup"><span data-stu-id="955dd-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="955dd-147">Onthoud de naam van de groep goed.</span><span class="sxs-lookup"><span data-stu-id="955dd-147">Remember the name of the group!</span></span> <span data-ttu-id="955dd-148">Deze hebt u later nodig.</span><span class="sxs-lookup"><span data-stu-id="955dd-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="955dd-149">Voltooi het instellen van de beveiligingsgroep en voeg personen of andere beveiligingsgroepen toe die u wilt kunnen maken groepen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="955dd-149">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="955dd-150">Zie [Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-beheercentrum](../email/create-edit-or-delete-a-security-group.md)voor gedetailleerde instructies.</span><span class="sxs-lookup"><span data-stu-id="955dd-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="955dd-151">Stap 2: PowerShell-opdrachten uitvoeren</span><span class="sxs-lookup"><span data-stu-id="955dd-151">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="955dd-152">U moet de preview-versie van [Azure Active Directory PowerShell voor Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="955dd-152">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="955dd-153">Als u nog nooit een versie van de Azure AD PowerShell-module hebt geïnstalleerd, raadpleegt u [De Azure AD-module installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en de instructies volgen om de openbare preview-release te installeren.</span><span class="sxs-lookup"><span data-stu-id="955dd-153">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="955dd-154">Als u de versie met algemene beschikbaarheid van 2.0 van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te voeren `Uninstall-Module AzureAD` in uw PowerShell-sessie en vervolgens de preview-versie installeren door . `Install-Module AzureADPreview`</span><span class="sxs-lookup"><span data-stu-id="955dd-154">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="955dd-155">Als u de preview-versie `Install-Module AzureADPreview` al hebt geïnstalleerd, voert u uit om te controleren of deze de nieuwste versie van deze module is.</span><span class="sxs-lookup"><span data-stu-id="955dd-155">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="955dd-156">Kopieer het script hieronder naar een teksteditor, zoals Kladblok of de [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="955dd-156">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="955dd-157">Vervang \* \<SecurityGroupName\> \* door de naam van de beveiligingsgroep die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="955dd-157">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="955dd-158">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="955dd-158">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="955dd-159">Sla het bestand op als GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="955dd-159">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="955dd-160">Navigeer in het PowerShell-venster naar de locatie waar <FileLocation>u het bestand hebt opgeslagen (typ 'CD").</span><span class="sxs-lookup"><span data-stu-id="955dd-160">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="955dd-161">Voer het script uit door te typen:</span><span class="sxs-lookup"><span data-stu-id="955dd-161">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="955dd-162">en [meld u aan met uw beheerdersaccount](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) wanneer daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="955dd-162">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="955dd-163">De laatste regel van het script geeft de bijgewerkte instellingen weer:</span><span class="sxs-lookup"><span data-stu-id="955dd-163">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="955dd-165">Als u in de toekomst wilt wijzigen welke beveiligingsgroep wordt gebruikt, u het script opnieuw uitvoeren met de naam van de nieuwe beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="955dd-165">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="955dd-166">Als u de groepsinstellingsbeperking wilt uitschakelen en alle gebruikers opnieuw groepen wilt toestaan, stelt u $GroupName in op '' en $AllowGroupCreation op 'Waar' en voert u het script opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="955dd-166">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="955dd-167">Stap 4: Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="955dd-167">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="955dd-168">Meld u aan bij Office 365 met een gebruikersaccount van iemand die NIET in staat mag zijn om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="955dd-168">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="955dd-169">Dat wil zeggen, ze zijn geen lid van de beveiligingsgroep die u hebt gemaakt of een beheerder.</span><span class="sxs-lookup"><span data-stu-id="955dd-169">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="955dd-170">Selecteer de tegel **Planner.**</span><span class="sxs-lookup"><span data-stu-id="955dd-170">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="955dd-171">Selecteer In Planner **Nieuw plan** in de linkernavigatie om een plan te maken.</span><span class="sxs-lookup"><span data-stu-id="955dd-171">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="955dd-172">U moet een bericht ontvangen dat het maken van plannen en het maken van groepen is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="955dd-172">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="955dd-173">Probeer dezelfde procedure opnieuw met een lid van de beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="955dd-173">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="955dd-174">Als leden van de beveiligingsgroep geen groepen kunnen maken, controleert u of ze niet worden geblokkeerd via hun [OWA-postvakbeleid](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="955dd-174">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="955dd-175">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="955dd-175">Related articles</span></span>

[<span data-ttu-id="955dd-176">Getting started with Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="955dd-176">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="955dd-177">Zelfservicegroepsbeheer instellen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="955dd-177">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="955dd-178">Uitvoeringsbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="955dd-178">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="955dd-179">Azure Active Directory-cmdlets voor het configureren van groepsinstellingen</span><span class="sxs-lookup"><span data-stu-id="955dd-179">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
