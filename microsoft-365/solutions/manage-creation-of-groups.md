---
title: Beheren wie Microsoft 365-groepen kan maken
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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Lees hoe u kunt bepalen welke gebruikers Microsoft 365-groepen kunnen maken.
ms.openlocfilehash: 3fa430e44c272e5ababbfb0e4befba707c72c1ba
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122382"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="c7cde-103">Beheren wie Microsoft 365-groepen kan maken</span><span class="sxs-lookup"><span data-stu-id="c7cde-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="c7cde-104">Standaard kunnen alle gebruikers Microsoft 365-groepen maken.</span><span class="sxs-lookup"><span data-stu-id="c7cde-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="c7cde-105">Dit is de aanbevolen aanpak, omdat gebruikers hierdoor kunnen gaan samenwerken zonder dat de IT-ondersteuning hiervoor nodig is.</span><span class="sxs-lookup"><span data-stu-id="c7cde-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="c7cde-106">Als uw bedrijf vereist dat u beperkt wie groepen kan maken, kunt u dit doen door de procedures in dit artikel te volgen.</span><span class="sxs-lookup"><span data-stu-id="c7cde-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="c7cde-107">Wanneer u beperkt wie een groep kan maken, is dit van invloed op alle services die afhankelijk zijn van groepen voor toegang, waaronder:</span><span class="sxs-lookup"><span data-stu-id="c7cde-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="c7cde-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="c7cde-108">Outlook</span></span>
- <span data-ttu-id="c7cde-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c7cde-109">SharePoint</span></span>
- <span data-ttu-id="c7cde-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="c7cde-110">Yammer</span></span>
- <span data-ttu-id="c7cde-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7cde-111">Microsoft Teams</span></span>
- <span data-ttu-id="c7cde-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="c7cde-112">Microsoft Stream</span></span>
- <span data-ttu-id="c7cde-113">Planner</span><span class="sxs-lookup"><span data-stu-id="c7cde-113">Planner</span></span>
- <span data-ttu-id="c7cde-114">Power BI (klassiek)</span><span class="sxs-lookup"><span data-stu-id="c7cde-114">Power BI (classic)</span></span>
- <span data-ttu-id="c7cde-115">Project voor het web / Roadmap</span><span class="sxs-lookup"><span data-stu-id="c7cde-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="c7cde-116">U kunt het maken van Microsoft 365-groepen beperken tot de leden van een bepaalde Microsoft 365-groep of beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="c7cde-116">You can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span> <span data-ttu-id="c7cde-117">U kunt dit configureren met Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7cde-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="c7cde-118">In dit artikel worden de benodigde stappen beschreven.</span><span class="sxs-lookup"><span data-stu-id="c7cde-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="c7cde-119">Met de stappen in dit artikel wordt niet voorkomen dat leden met bepaalde rollen groepen kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="c7cde-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="c7cde-120">Globale beheerders van Office 365 kunnen groepen maken op elke manier, zoals het Microsoft 365-beheercentrum, Planner, Teams, Exchange en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c7cde-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="c7cde-121">Andere rollen kunnen groepen maken via beperkte middelen, zoals hieronder wordt vermeld.</span><span class="sxs-lookup"><span data-stu-id="c7cde-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="c7cde-122">Exchange-beheerder: Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c7cde-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="c7cde-123">Ondersteuning voor partnerlaag 1: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c7cde-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="c7cde-124">Ondersteuning voor partnerlaag 2: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c7cde-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="c7cde-125">Schrijvers van adreslijst: Azure AD</span><span class="sxs-lookup"><span data-stu-id="c7cde-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="c7cde-126">SharePoint-beheerder: SharePoint-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c7cde-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="c7cde-127">Teams-servicebeheerder: Teams-beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c7cde-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="c7cde-128">Beheerder gebruikersbeheer: Microsoft 365-beheercentrum, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="c7cde-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>

<span data-ttu-id="c7cde-129">Als u lid bent van een van deze rollen, kunt u Microsoft 365-groepen maken voor beperkte gebruikers en de gebruiker vervolgens toewijzen als de eigenaar van de groep.</span><span class="sxs-lookup"><span data-stu-id="c7cde-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="c7cde-130">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="c7cde-130">Licensing requirements</span></span>

<span data-ttu-id="c7cde-131">Om te beheren wie groepen maakt, moeten de volgende personen Azure AD Premium-licenties of Azure AD Basic EDU-licenties aan hen toegewezen hebben:</span><span class="sxs-lookup"><span data-stu-id="c7cde-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="c7cde-132">De beheerder die deze instellingen voor het maken van groepen configureert</span><span class="sxs-lookup"><span data-stu-id="c7cde-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="c7cde-133">De leden van de groep die groepen mogen maken</span><span class="sxs-lookup"><span data-stu-id="c7cde-133">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="c7cde-134">Zie [Licenties toewijzen of verwijderen in de Azure Active Directory-portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) voor meer informatie over het toewijzen van Azure-licenties.</span><span class="sxs-lookup"><span data-stu-id="c7cde-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="c7cde-135">De volgende personen hebben geen Azure AD Premium- of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:</span><span class="sxs-lookup"><span data-stu-id="c7cde-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="c7cde-136">Personen die lid zijn van Microsoft 365-groepen en die niet in staat zijn om andere groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="c7cde-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="c7cde-137">Stap 1: Een groep maken voor gebruikers die Microsoft 365-groepen moeten maken</span><span class="sxs-lookup"><span data-stu-id="c7cde-137">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="c7cde-138">Slechts één groep in uw organisatie kan worden gebruikt om te bepalen wie groepen kan maken.</span><span class="sxs-lookup"><span data-stu-id="c7cde-138">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="c7cde-139">Maar u kunt andere groepen nesten als leden van deze groep.</span><span class="sxs-lookup"><span data-stu-id="c7cde-139">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="c7cde-140">Beheerders in de bovenstaande rollen hoeven geen lid te zijn van deze groep: ze behouden hun mogelijkheid om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="c7cde-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="c7cde-141">Ga in het beheercentrum naar de [pagina Groepen.](https://admin.microsoft.com/adminportal/home#/groups)</span><span class="sxs-lookup"><span data-stu-id="c7cde-141">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="c7cde-142">Klik op **Groep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="c7cde-142">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="c7cde-143">Kies het 3D-groepstype.</span><span class="sxs-lookup"><span data-stu-id="c7cde-143">Choose the group type you want.</span></span> <span data-ttu-id="c7cde-144">Onthoud de naam van de groep goed.</span><span class="sxs-lookup"><span data-stu-id="c7cde-144">Remember the name of the group!</span></span> <span data-ttu-id="c7cde-145">Deze hebt u later nodig.</span><span class="sxs-lookup"><span data-stu-id="c7cde-145">You'll need it later.</span></span>

4. <span data-ttu-id="c7cde-146">Rond het instellen van de groep af en voeg personen of andere groepen toe die u in uw organisatie wilt kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="c7cde-146">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="c7cde-147">Zie Een beveiligingsgroep maken, bewerken of verwijderen in het [Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)voor gedetailleerde instructies.</span><span class="sxs-lookup"><span data-stu-id="c7cde-147">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="c7cde-148">Stap 2: PowerShell-opdrachten uitvoeren</span><span class="sxs-lookup"><span data-stu-id="c7cde-148">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="c7cde-149">U moet de preview-versie van [Azure Active Directory PowerShell for Graph (AzureAD) (modulenaam](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="c7cde-149">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="c7cde-150">Als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd, gaat u naar De [Azure AD-module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) installeren en volgt u de instructies om de openbare preview-versie te installeren.</span><span class="sxs-lookup"><span data-stu-id="c7cde-150">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="c7cde-151">Als u de 2.0 algemene beschikbaarheidsversie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te zetten in uw PowerShell-sessie en vervolgens de preview-versie te installeren. `Uninstall-Module AzureAD` `Install-Module AzureADPreview`</span><span class="sxs-lookup"><span data-stu-id="c7cde-151">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="c7cde-152">Als u de preview-versie al hebt geïnstalleerd, moet u ervoor zorgen dat dit de nieuwste versie `Install-Module AzureADPreview` van deze module is.</span><span class="sxs-lookup"><span data-stu-id="c7cde-152">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="c7cde-153">Kopieer het onderstaande script naar een teksteditor, zoals Kladblok of [de Windows PowerShell ISE.](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="c7cde-153">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="c7cde-154">Vervang *\<GroupName\>* door de naam van de groep die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c7cde-154">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="c7cde-155">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c7cde-155">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="c7cde-156">Sla het bestand op als GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="c7cde-156">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="c7cde-157">Navigeer in het PowerShell-venster naar de locatie waar u het bestand hebt opgeslagen (typ <FileLocation> 'CD').</span><span class="sxs-lookup"><span data-stu-id="c7cde-157">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="c7cde-158">Voer het script uit door te typen:</span><span class="sxs-lookup"><span data-stu-id="c7cde-158">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="c7cde-159">en [meld u aan met uw beheerdersaccount](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) wanneer hier om wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="c7cde-159">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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

<span data-ttu-id="c7cde-160">Op de laatste regel van het script worden de bijgewerkte instellingen weergegeven:</span><span class="sxs-lookup"><span data-stu-id="c7cde-160">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="c7cde-162">Als u in de toekomst wilt wijzigen welke groep wordt gebruikt, kunt u het script opnieuw uitvoeren met de naam van de nieuwe groep.</span><span class="sxs-lookup"><span data-stu-id="c7cde-162">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="c7cde-163">Als u de beperking voor het maken van groepen wilt uitschakelen en weer wilt toestaan dat alle gebruikers groepen maken, stelt u $GroupName in op '' en $AllowGroupCreation op 'Waar' en voeren u het script opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="c7cde-163">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="c7cde-164">Stap 3: controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="c7cde-164">Step 3: Verify that it works</span></span>

<span data-ttu-id="c7cde-165">Het kan dertig minuten of meer duren voordat de wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="c7cde-165">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="c7cde-166">U kunt de nieuwe instellingen als volgt controleren:</span><span class="sxs-lookup"><span data-stu-id="c7cde-166">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="c7cde-167">Meld u aan bij Microsoft 365 met een gebruikersaccount van iemand die NIET in staat mag zijn om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="c7cde-167">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="c7cde-168">Dat wil zeggen dat ze geen lid zijn van de groep die u hebt gemaakt of van een beheerder.</span><span class="sxs-lookup"><span data-stu-id="c7cde-168">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="c7cde-169">Selecteer de **Planner-tegel.**</span><span class="sxs-lookup"><span data-stu-id="c7cde-169">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="c7cde-170">Selecteer in Planner **Nieuw plan** in het linkernavigatievenster om een plan te maken.</span><span class="sxs-lookup"><span data-stu-id="c7cde-170">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="c7cde-171">Er wordt een bericht weergegeven dat plannen en het maken van groepen zijn uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c7cde-171">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="c7cde-172">Probeer dezelfde procedure opnieuw met een lid van de groep.</span><span class="sxs-lookup"><span data-stu-id="c7cde-172">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="c7cde-173">Als leden van de groep geen groepen kunnen maken, controleert u of deze niet worden geblokkeerd door hun [OWA-postvakbeleid.](https://go.microsoft.com/fwlink/?linkid=852135)</span><span class="sxs-lookup"><span data-stu-id="c7cde-173">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c7cde-174">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c7cde-174">Related topics</span></span>

[<span data-ttu-id="c7cde-175">Planning van samenwerkingsbeheer stap voor stap</span><span class="sxs-lookup"><span data-stu-id="c7cde-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="c7cde-176">Uw samenwerkingsbeheerplan maken</span><span class="sxs-lookup"><span data-stu-id="c7cde-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="c7cde-177">Getting started with Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7cde-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="c7cde-178">Selfservice voor groepsbeheer instellen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c7cde-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="c7cde-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="c7cde-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="c7cde-180">Azure Active Directory-cmdlets voor het configureren van groepsinstellingen</span><span class="sxs-lookup"><span data-stu-id="c7cde-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
