---
title: Beheren wie Microsoft 365-groepen kunnen maken
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Meer informatie over hoe u kunt bepalen welke gebruikers Microsoft 365-groepen kunnen maken.
ms.openlocfilehash: d6e6c6d9caff2ac7c13d03dad97b73906a509f46
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307857"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="f61c9-103">Beheren wie Microsoft 365-groepen kunnen maken</span><span class="sxs-lookup"><span data-stu-id="f61c9-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="f61c9-104">Standaard kunnen alle gebruikers Microsoft 365-groepen maken.</span><span class="sxs-lookup"><span data-stu-id="f61c9-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="f61c9-105">Dit is de aanbevolen manier, omdat gebruikers kunnen samenwerken zonder dat ze daarvoor hulp hoeven te bieden.</span><span class="sxs-lookup"><span data-stu-id="f61c9-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="f61c9-106">Als u wilt dat u kunt instellen wie groepen kan maken, kunt u dat doen door de procedures in dit artikel te volgen.</span><span class="sxs-lookup"><span data-stu-id="f61c9-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="f61c9-107">Wanneer u beperkt wie een groep kan maken, heeft dit invloed op alle services die afhankelijk zijn van groepen voor toegang, waaronder:</span><span class="sxs-lookup"><span data-stu-id="f61c9-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="f61c9-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="f61c9-108">Outlook</span></span>
    
- <span data-ttu-id="f61c9-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="f61c9-109">SharePoint</span></span>
    
- <span data-ttu-id="f61c9-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="f61c9-110">Yammer</span></span>
    
- <span data-ttu-id="f61c9-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f61c9-111">Microsoft Teams</span></span>

- <span data-ttu-id="f61c9-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="f61c9-112">Microsoft Stream</span></span>

- <span data-ttu-id="f61c9-113">Planner</span><span class="sxs-lookup"><span data-stu-id="f61c9-113">Planner</span></span>
    
- <span data-ttu-id="f61c9-114">PowerBI (klassiek)</span><span class="sxs-lookup"><span data-stu-id="f61c9-114">PowerBI (classic)</span></span>
    
- <span data-ttu-id="f61c9-115">Project voor het web/routekaart</span><span class="sxs-lookup"><span data-stu-id="f61c9-115">Project for the web / Roadmap</span></span>
    
<span data-ttu-id="f61c9-116">U kunt het maken van een Microsoft 365-groep beperken tot de leden van een bepaalde beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="f61c9-116">You can restrict Microsoft 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="f61c9-117">U kunt deze configureren met behulp van Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f61c9-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="f61c9-118">In dit artikel wordt u stapsgewijs begeleid bij het uitvoeren van de benodigde stappen.</span><span class="sxs-lookup"><span data-stu-id="f61c9-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="f61c9-119">Met de stappen in dit artikel kunnen leden van bepaalde rollen geen groepen maken.</span><span class="sxs-lookup"><span data-stu-id="f61c9-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="f61c9-120">Globale beheerders van Office 365 kunnen groepen maken op grond van een willekeurige manier, zoals het Beheercentrum van Microsoft 365, planner, teams, Exchange en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f61c9-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="f61c9-121">Andere rollen kunnen groepen maken op grond van beperkte middelen die hieronder worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f61c9-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="f61c9-122">Exchange-beheerder: Exchange-Beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="f61c9-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="f61c9-123">Ondersteuning voor partner niveau 1: Microsoft 365-Beheercentrum, Exchange-Beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="f61c9-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="f61c9-124">Ondersteuning voor partner niveau 2: Microsoft 365-Beheercentrum, Exchange-Beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="f61c9-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="f61c9-125">Directory schrijvers: Azure AD</span><span class="sxs-lookup"><span data-stu-id="f61c9-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="f61c9-126">SharePoint-beheerder: SharePoint-Beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="f61c9-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="f61c9-127">Service beheerder voor teams: Beheercentrum voor teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="f61c9-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="f61c9-128">Gebruikersbeheer beheerder: Microsoft 365-Beheercentrum, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="f61c9-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="f61c9-129">Als u lid bent van een van deze rollen, kunt u Microsoft 365 groepen maken voor gebruikers met beperkte toegang, en vervolgens de gebruiker toewijzen als de eigenaar van de groep.</span><span class="sxs-lookup"><span data-stu-id="f61c9-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="f61c9-130">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="f61c9-130">Licensing requirements</span></span>

<span data-ttu-id="f61c9-131">Voor het beheren van groepen moeten de volgende personen Azure AD Premium-licenties of Azure AD Basic Education-licenties aan hen toewijzen:</span><span class="sxs-lookup"><span data-stu-id="f61c9-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="f61c9-132">De beheerder die de instellingen voor het maken van een groep configureert</span><span class="sxs-lookup"><span data-stu-id="f61c9-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="f61c9-133">De leden van de beveiligingsgroep die groepen mogen maken</span><span class="sxs-lookup"><span data-stu-id="f61c9-133">The members of the security group who are allowed to create groups</span></span>
 
> [!NOTE]
> <span data-ttu-id="f61c9-134">Zie [licenties toewijzen of verwijderen in de Azure Active Directory-Portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) voor meer informatie over het toewijzen van Azure-licenties.</span><span class="sxs-lookup"><span data-stu-id="f61c9-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="f61c9-135">De volgende personen hebben geen Azure AD Premium-of Azure AD-basisonderwijs-licenties toegewezen:</span><span class="sxs-lookup"><span data-stu-id="f61c9-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="f61c9-136">Personen die lid zijn van Microsoft 365-groepen en geen andere groepen kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="f61c9-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="f61c9-137">Stap 1: een beveiligingsgroep maken voor gebruikers die Microsoft 365-groepen willen maken</span><span class="sxs-lookup"><span data-stu-id="f61c9-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="f61c9-138">U kunt slechts één beveiligingsgroep in uw organisatie gebruiken om te bepalen wie groepen kan maken.</span><span class="sxs-lookup"><span data-stu-id="f61c9-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="f61c9-139">U kunt wel andere beveiligingsgroepen nesten als leden van deze groep.</span><span class="sxs-lookup"><span data-stu-id="f61c9-139">But, you can nest other security groups as members of this group.</span></span>

<span data-ttu-id="f61c9-140">Beheerders in de hierboven vermelde rollen hoeven geen lid te zijn van deze groep: ze behouden de mogelijkheid om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="f61c9-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f61c9-141">Zorg ervoor dat u een **beveiligingsgroep** gebruikt om te beperken wie groepen kan maken.</span><span class="sxs-lookup"><span data-stu-id="f61c9-141">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="f61c9-142">Het gebruik van een Microsoft 365-groep wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="f61c9-142">Using a Microsoft 365 group is not supported.</span></span> 
    
1. <span data-ttu-id="f61c9-143">Ga in het Beheercentrum naar de [pagina groepen](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="f61c9-143">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="f61c9-144">Klik op **een groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f61c9-144">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="f61c9-145">Kies **beveiliging** als groepstype.</span><span class="sxs-lookup"><span data-stu-id="f61c9-145">Choose **Security** as the group type.</span></span> <span data-ttu-id="f61c9-146">Onthoud de naam van de groep goed.</span><span class="sxs-lookup"><span data-stu-id="f61c9-146">Remember the name of the group!</span></span> <span data-ttu-id="f61c9-147">Deze hebt u later nodig.</span><span class="sxs-lookup"><span data-stu-id="f61c9-147">You'll need it later.</span></span>
  
4. <span data-ttu-id="f61c9-148">Voltooi het instellen van de beveiligingsgroep en voeg personen of andere beveiligingsgroepen toe die groepen in uw organisatie moeten kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="f61c9-148">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="f61c9-149">Zie [een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)voor gedetailleerde instructies.</span><span class="sxs-lookup"><span data-stu-id="f61c9-149">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="f61c9-150">Stap 2: PowerShell-opdrachten uitvoeren</span><span class="sxs-lookup"><span data-stu-id="f61c9-150">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="f61c9-151">U moet de preview-versie van [Azure Active Directory PowerShell voor Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview**) gebruiken om de instelling voor gasttoegang op het groepeerniveau te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="f61c9-151">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="f61c9-152">Als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd, raadpleegt u [de module van Azure AD installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en volgt u de instructies voor het installeren van de openbare preview-versie.</span><span class="sxs-lookup"><span data-stu-id="f61c9-152">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="f61c9-153">Als u de algemene beschikbaarheid van 2,0 van de versie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door `Uninstall-Module AzureAD` in uw PowerShell-sessie te worden uitgevoerd, en de preview-versie vervolgens te installeren `Install-Module AzureADPreview` .</span><span class="sxs-lookup"><span data-stu-id="f61c9-153">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="f61c9-154">Als u de preview-versie al hebt geïnstalleerd, controleert u `Install-Module AzureADPreview` of deze de nieuwste versie van deze module is.</span><span class="sxs-lookup"><span data-stu-id="f61c9-154">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="f61c9-155">Kopieer het volgende script naar een teksteditor, zoals Kladblok of de [Windows PowerShell-ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="f61c9-155">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="f61c9-156">Vervang door *\<SecurityGroupName\>* de naam van de beveiligingsgroep die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f61c9-156">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="f61c9-157">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="f61c9-157">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="f61c9-158">Sla het bestand op als GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="f61c9-158">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="f61c9-159">Ga in het PowerShell-venster naar de locatie waar u het bestand hebt opgeslagen (type CD <FileLocation> ).</span><span class="sxs-lookup"><span data-stu-id="f61c9-159">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="f61c9-160">Voer het script uit door het volgende te typen:</span><span class="sxs-lookup"><span data-stu-id="f61c9-160">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="f61c9-161">en [Meld u aan met uw beheerdersaccount](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) wanneer hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="f61c9-161">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="f61c9-162">In de laatste regel van het script worden de bijgewerkte instellingen weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f61c9-162">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="f61c9-164">Als u in de toekomst de gebruikte beveiligingsgroep wilt wijzigen, kunt u het script opnieuw uitvoeren met de naam van de nieuwe beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="f61c9-164">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="f61c9-165">Als u de beperking voor het maken van een groep wilt uitschakelen en alle gebruikers de mogelijkheid wilt bieden om groepen te maken, stelt u $GroupName in op ' ' en ' $AllowGroupCreation ' en voert u het script opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="f61c9-165">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="f61c9-166">Stap 3: controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="f61c9-166">Step 3: Verify that it works</span></span>

<span data-ttu-id="f61c9-167">Het kan dertig minuten of langer duren voordat de wijzigingen zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f61c9-167">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="f61c9-168">U kunt de nieuwe instellingen als volgt controleren:</span><span class="sxs-lookup"><span data-stu-id="f61c9-168">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="f61c9-169">Meld u aan bij Microsoft 365 met een gebruikersaccount van iemand die de mogelijkheid om groepen te maken niet heeft.</span><span class="sxs-lookup"><span data-stu-id="f61c9-169">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="f61c9-170">Dat wil zeggen dat ze geen lid zijn van de beveiligingsgroep die u hebt gemaakt of van een beheerder.</span><span class="sxs-lookup"><span data-stu-id="f61c9-170">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="f61c9-171">Selecteer de tegel **planner** .</span><span class="sxs-lookup"><span data-stu-id="f61c9-171">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="f61c9-172">Selecteer **nieuw plan** in het linker navigatieniveau in Planner om een plan te maken.</span><span class="sxs-lookup"><span data-stu-id="f61c9-172">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="f61c9-173">U moet een bericht weergeven dat het maken van een abonnement en het maken van groepen is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f61c9-173">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="f61c9-174">Probeer opnieuw dezelfde procedure met een lid van de beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="f61c9-174">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="f61c9-175">Als leden van de beveiligingsgroep geen groepen kunnen maken, controleert u of ze niet worden geblokkeerd via het [OWA-postvak beleid](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="f61c9-175">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="f61c9-176">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="f61c9-176">Related articles</span></span>

[<span data-ttu-id="f61c9-177">Getting started with Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f61c9-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="f61c9-178">Selfservice voor groepsbeheer instellen in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f61c9-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="f61c9-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="f61c9-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="f61c9-180">Azure Active Directory-cmdlets voor het configureren van instellingen voor groepen</span><span class="sxs-lookup"><span data-stu-id="f61c9-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
