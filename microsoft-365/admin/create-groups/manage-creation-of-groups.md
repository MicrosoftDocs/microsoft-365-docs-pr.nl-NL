---
title: Beheren wie groepen kan maken
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Meer informatie over hoe u bepalen welke gebruikers Microsoft 365-groepen kunnen maken.
ms.openlocfilehash: b64e7ac96c5a0e38583d00f8a61bd47c5304cf45
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761672"
---
# <a name="manage-who-can-create-groups"></a><span data-ttu-id="b2582-103">Beheren wie groepen kan maken</span><span class="sxs-lookup"><span data-stu-id="b2582-103">Manage who can create Groups</span></span>

  
<span data-ttu-id="b2582-104">Omdat het zo eenvoudig is voor gebruikers om Microsoft 365-groepen te maken, wordt u niet overspoeld met verzoeken om ze te maken namens andere mensen.</span><span class="sxs-lookup"><span data-stu-id="b2582-104">Because it's so easy for users to create Microsoft 365 groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="b2582-105">Afhankelijk van uw bedrijf wilt u wellicht zelf bepalen wie er groepen kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="b2582-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="b2582-106">In dit artikel wordt uitgelegd hoe u de mogelijkheid uitschakelen om groepen te maken in alle Microsoft 365-services die groepen gebruiken, waaronder:</span><span class="sxs-lookup"><span data-stu-id="b2582-106">This article explains how to disable the ability to create groups in all Microsoft 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="b2582-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="b2582-107">Outlook</span></span>
    
- <span data-ttu-id="b2582-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b2582-108">SharePoint</span></span>
    
- <span data-ttu-id="b2582-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="b2582-109">Yammer</span></span>
    
- <span data-ttu-id="b2582-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2582-110">Microsoft Teams</span></span>

- <span data-ttu-id="b2582-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="b2582-111">Microsoft Stream</span></span>

- <span data-ttu-id="b2582-112">Planner</span><span class="sxs-lookup"><span data-stu-id="b2582-112">Planner</span></span>
    
- <span data-ttu-id="b2582-113">PowerBI (PowerBI)</span><span class="sxs-lookup"><span data-stu-id="b2582-113">PowerBI</span></span>

- <span data-ttu-id="b2582-114">Project voor het web en roadmap</span><span class="sxs-lookup"><span data-stu-id="b2582-114">Project for the web and Roadmap</span></span>
    
<span data-ttu-id="b2582-115">U het maken van Microsoft 365-groepen beperken tot de leden van een bepaalde beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="b2582-115">You can restrict Microsoft 365 group creation to the members of a particular security group.</span></span> <span data-ttu-id="b2582-116">Als u dit wilt configureren, gebruikt u Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2582-116">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="b2582-117">Dit artikel leidt u door de benodigde stappen.</span><span class="sxs-lookup"><span data-stu-id="b2582-117">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="b2582-118">Met de stappen in dit artikel kunnen leden van bepaalde rollen er niet van worden weerhouden groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="b2582-118">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="b2582-119">Globale beheerders kunnen groepen maken op alle mogelijke manieren, zoals het Microsoft 365-beheercentrum, Planner, Teams, Exchange en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b2582-119">Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="b2582-120">Andere rollen kunnen groepen maken via beperkte middelen, hieronder vermeld.</span><span class="sxs-lookup"><span data-stu-id="b2582-120">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="b2582-121">Exchange-beheerder: Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2582-121">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="b2582-122">Ondersteuning voor Partner Tier 1: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2582-122">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="b2582-123">Partner Tier 2-ondersteuning: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2582-123">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="b2582-124">Directory Writers: Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2582-124">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="b2582-125">SharePoint-beheerder: SharePoint-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2582-125">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="b2582-126">TeamsServicebeheerder: TeamsBeheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2582-126">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="b2582-127">Beheerder gebruikersbeheer: Microsoft 365-beheercentrum, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2582-127">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="b2582-128">Als u lid bent van een van deze rollen, u Microsoft 365-groepen maken voor beperkte gebruikers en de gebruiker vervolgens toewijzen als de eigenaar van de groep.</span><span class="sxs-lookup"><span data-stu-id="b2582-128">If you're a member of one of these roles, you can create Microsoft 365 groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="b2582-129">Gebruikers met deze rol kunnen verbonden groepen maken in Yammer, ongeacht de PowerShell-instellingen die het maken ervan kunnen voorkomen.</span><span class="sxs-lookup"><span data-stu-id="b2582-129">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="b2582-130">Vergunningsvereisten</span><span class="sxs-lookup"><span data-stu-id="b2582-130">Licensing requirements</span></span>

<span data-ttu-id="b2582-131">Als u wilt beheren wie groepen maakt, hebben de volgende personen Azure AD Premium-licenties of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:</span><span class="sxs-lookup"><span data-stu-id="b2582-131">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="b2582-132">De beheerder die deze instellingen voor groepsvermaken configureert</span><span class="sxs-lookup"><span data-stu-id="b2582-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="b2582-133">De leden van de beveiligingsgroep die groepen mogen maken</span><span class="sxs-lookup"><span data-stu-id="b2582-133">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="b2582-134">Zie [Licenties toewijzen of verwijderen in de Azure Active Directory-portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) voor meer informatie over het toewijzen van Azure-licenties.</span><span class="sxs-lookup"><span data-stu-id="b2582-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="b2582-135">De volgende personen hebben geen Azure AD Premium- of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:</span><span class="sxs-lookup"><span data-stu-id="b2582-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="b2582-136">Mensen die lid zijn van Microsoft 365-groepen en die niet de mogelijkheid hebben om andere groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="b2582-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="b2582-137">Stap 1: Een beveiligingsgroep maken voor gebruikers die Microsoft 365-groepen moeten maken</span><span class="sxs-lookup"><span data-stu-id="b2582-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="b2582-138">Er kan slechts één beveiligingsgroep in uw organisatie worden gebruikt om te bepalen wie groepen kan maken.</span><span class="sxs-lookup"><span data-stu-id="b2582-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="b2582-139">U kunt wel andere beveiligingsgroepen nesten als leden van deze groep.</span><span class="sxs-lookup"><span data-stu-id="b2582-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="b2582-140">Voorbeeld: de groep met de naam Groep maken toestaan is de aangewezen beveiligingsgroep en de groepen met de naam Microsoft Planner-gebruikers en Exchange Online-gebruikers zijn lid van die groep.</span><span class="sxs-lookup"><span data-stu-id="b2582-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="b2582-141">Beheerders in de bovenstaande rollen hoeven geen lid te zijn van deze groep: ze behouden hun mogelijkheid om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="b2582-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2582-142">Zorg ervoor dat u een **beveiligingsgroep** gebruikt om te beperken wie groepen kan maken.</span><span class="sxs-lookup"><span data-stu-id="b2582-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="b2582-143">Als u een Microsoft 365-groep probeert te gebruiken, kunnen leden geen groep maken vanuit SharePoint omdat deze controleert op een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="b2582-143">If you try to use a Microsoft 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="b2582-144">Ga in het beheercentrum **Groups** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepen groepen.</a></span><span class="sxs-lookup"><span data-stu-id="b2582-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="b2582-145">Klik op **Een groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="b2582-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="b2582-146">Kies **Beveiliging** als groepstype.</span><span class="sxs-lookup"><span data-stu-id="b2582-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="b2582-147">Onthoud de naam van de groep goed.</span><span class="sxs-lookup"><span data-stu-id="b2582-147">Remember the name of the group!</span></span> <span data-ttu-id="b2582-148">Deze hebt u later nodig.</span><span class="sxs-lookup"><span data-stu-id="b2582-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="b2582-149">Voltooi het instellen van de beveiligingsgroep en voeg mensen of andere beveiligingsgroepen toe die u groepen in uw organisatie wilt kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="b2582-149">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="b2582-150">Zie [Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-beheercentrum](../email/create-edit-or-delete-a-security-group.md)voor gedetailleerde instructies.</span><span class="sxs-lookup"><span data-stu-id="b2582-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="b2582-151">Stap 2: PowerShell-opdrachten uitvoeren</span><span class="sxs-lookup"><span data-stu-id="b2582-151">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="b2582-152">U moet de voorbeeldversie van [Azure Active Directory PowerShell for Graph (AzureAD) (modulenaam](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="b2582-152">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="b2582-153">Als u nog geen versie van de Azure AD PowerShell-module eerder hebt geïnstalleerd, raadpleegt u [De Azure AD-module installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en de instructies volgen om de versie van de openbare preview te installeren.</span><span class="sxs-lookup"><span data-stu-id="b2582-153">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="b2582-154">Als u de 2.0 algemene beschikbaarheidsversie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te voeren `Uninstall-Module AzureAD` in uw PowerShell-sessie en vervolgens de preview-versie installeren door `Install-Module AzureADPreview` .</span><span class="sxs-lookup"><span data-stu-id="b2582-154">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="b2582-155">Als u de preview-versie al hebt geïnstalleerd, moet u `Install-Module AzureADPreview` ervoor zorgen dat dit de nieuwste versie van deze module is.</span><span class="sxs-lookup"><span data-stu-id="b2582-155">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="b2582-156">Kopieer het script hieronder naar een teksteditor, zoals Kladblok of de [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="b2582-156">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="b2582-157">Vervang *\<SecurityGroupName\>* de naam van de beveiligingsgroep die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b2582-157">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="b2582-158">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b2582-158">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="b2582-159">Sla het bestand op als GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="b2582-159">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="b2582-160">Navigeer in het PowerShell-venster naar de locatie waar u het bestand hebt opgeslagen (typ <FileLocation> 'CD').</span><span class="sxs-lookup"><span data-stu-id="b2582-160">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="b2582-161">Voer het script uit door te typen:</span><span class="sxs-lookup"><span data-stu-id="b2582-161">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="b2582-162">en [meld u aan met uw beheerdersaccount](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) wanneer daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="b2582-162">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="b2582-163">De laatste regel van het script geeft de bijgewerkte instellingen weer:</span><span class="sxs-lookup"><span data-stu-id="b2582-163">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="b2582-165">Als u in de toekomst wilt wijzigen welke beveiligingsgroep wordt gebruikt, u het script opnieuw uitvoeren met de naam van de nieuwe beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="b2582-165">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="b2582-166">Als u de beperking voor het maken van groepen wilt uitschakelen en alle gebruikers opnieuw toestaan groepen te maken, stelt u $GroupName in op '' en $AllowGroupCreation op 'True' en het script opnieuw uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="b2582-166">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="b2582-167">Stap 3: controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="b2582-167">Step 3: Verify that it works</span></span>

<span data-ttu-id="b2582-168">Wijzigingen kunnen dertig minuten of langer duren om van kracht te worden.</span><span class="sxs-lookup"><span data-stu-id="b2582-168">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="b2582-169">U de nieuwe instellingen als volgt controleren:</span><span class="sxs-lookup"><span data-stu-id="b2582-169">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="b2582-170">Meld u aan met een gebruikersaccount van iemand die NIET de mogelijkheid zou moeten hebben om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="b2582-170">Sign in with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="b2582-171">Dat wil zeggen dat ze geen lid zijn van de beveiligingsgroep die u hebt gemaakt of een beheerder.</span><span class="sxs-lookup"><span data-stu-id="b2582-171">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="b2582-172">Selecteer de tegel **Planner.**</span><span class="sxs-lookup"><span data-stu-id="b2582-172">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="b2582-173">Selecteer in Planner **Nieuw plan** in de linkernavigatie om een plan te maken.</span><span class="sxs-lookup"><span data-stu-id="b2582-173">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="b2582-174">U moet een bericht ontvangen dat het plannen en groepscreatie is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b2582-174">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="b2582-175">Probeer dezelfde procedure opnieuw met een lid van de beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="b2582-175">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="b2582-176">Als leden van de beveiligingsgroep geen groepen kunnen maken, controleert u of ze niet worden geblokkeerd via hun [OWA-postvakbeleid](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="b2582-176">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="b2582-177">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="b2582-177">Related articles</span></span>

[<span data-ttu-id="b2582-178">Getting started with Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2582-178">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="b2582-179">Selfservicegroepsbeheer instellen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b2582-179">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="b2582-180">Beleid voor uitvoering instellen</span><span class="sxs-lookup"><span data-stu-id="b2582-180">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="b2582-181">Azure Active Directory-cmdlets voor het configureren van groepsinstellingen</span><span class="sxs-lookup"><span data-stu-id="b2582-181">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
