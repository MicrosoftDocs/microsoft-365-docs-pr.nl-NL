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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
recommendations: false
description: Lees hoe u kunt bepalen welke gebruikers groepen Microsoft 365 maken.
ms.openlocfilehash: 19a106d255708f4b1df8f798219ea7ea778bbef3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539177"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="fc117-103">Beheren wie Microsoft 365-groepen kunnen maken</span><span class="sxs-lookup"><span data-stu-id="fc117-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="fc117-104">Standaard kunnen alle gebruikers Microsoft 365 maken.</span><span class="sxs-lookup"><span data-stu-id="fc117-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="fc117-105">Dit is de aanbevolen methode, omdat gebruikers hiermee kunnen samenwerken zonder hulp van IT nodig te hebben.</span><span class="sxs-lookup"><span data-stu-id="fc117-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="fc117-106">Als uw bedrijf vereist dat u beperkt wie groepen kan maken, kunt u het maken van groepen beperken Microsoft 365 groep tot de leden van een bepaalde Microsoft 365 groep of beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="fc117-106">If your business requires that you restrict who can create groups, you can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span>

<span data-ttu-id="fc117-107">Als u zich zorgen maakt over gebruikers die teams of groepen maken die niet voldoen aan uw bedrijfsstandaarden, kunt u overwegen om gebruikers te verplichten een trainingscursus te volgen en ze vervolgens toe te voegen aan de groep toegestane gebruikers.</span><span class="sxs-lookup"><span data-stu-id="fc117-107">If you're concerned about users creating teams or groups that don't comply with your business standards, consider requiring users to complete a training course and then adding them to the group of allowed users.</span></span>

<span data-ttu-id="fc117-108">Wanneer u beperkt wie een groep kan maken, is dit van invloed op alle services die afhankelijk zijn van groepen voor toegang, waaronder:</span><span class="sxs-lookup"><span data-stu-id="fc117-108">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="fc117-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="fc117-109">Outlook</span></span>
- <span data-ttu-id="fc117-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fc117-110">SharePoint</span></span>
- <span data-ttu-id="fc117-111">Yammer</span><span class="sxs-lookup"><span data-stu-id="fc117-111">Yammer</span></span>
- <span data-ttu-id="fc117-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc117-112">Microsoft Teams</span></span>
- <span data-ttu-id="fc117-113">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="fc117-113">Microsoft Stream</span></span>
- <span data-ttu-id="fc117-114">Planner</span><span class="sxs-lookup"><span data-stu-id="fc117-114">Planner</span></span>
- <span data-ttu-id="fc117-115">Power BI (klassiek)</span><span class="sxs-lookup"><span data-stu-id="fc117-115">Power BI (classic)</span></span>
- <span data-ttu-id="fc117-116">Project web / Roadmap</span><span class="sxs-lookup"><span data-stu-id="fc117-116">Project for the web / Roadmap</span></span>

<span data-ttu-id="fc117-117">De stappen in dit artikel voorkomen niet dat leden van bepaalde rollen groepen kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="fc117-117">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="fc117-118">Office 365 Globale beheerders kunnen Groepen maken via het Microsoft 365 beheercentrum, Planner, Exchange en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="fc117-118">Office 365 Global admins can create Groups via the Microsoft 365 admin center, Planner, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="fc117-119">Andere rollen kunnen Groepen maken via beperkte middelen, hieronder weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fc117-119">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="fc117-120">Exchange Beheerder: Exchange beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc117-120">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="fc117-121">Ondersteuning voor partnerniveau 1: Microsoft 365 beheercentrum, Exchange beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc117-121">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="fc117-122">Ondersteuning voor partnerniveau 2: Microsoft 365 beheercentrum, Exchange beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc117-122">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="fc117-123">Adreslijst schrijvers: Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc117-123">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="fc117-124">SharePoint Beheerder: SharePoint beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc117-124">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="fc117-125">Teams Servicebeheerder: Teams beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc117-125">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="fc117-126">Gebruikerbeheerder: Microsoft 365 beheercentrum, Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc117-126">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="fc117-127">Als u lid bent van een van deze rollen, kunt u Microsoft 365 Groepen maken voor beperkte gebruikers en de gebruiker vervolgens toewijzen als eigenaar van de groep.</span><span class="sxs-lookup"><span data-stu-id="fc117-127">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="fc117-128">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="fc117-128">Licensing requirements</span></span>

<span data-ttu-id="fc117-129">Als u wilt beheren wie groepen maakt, hebben de volgende personen Azure AD Premium of Azure AD Basic EDU-licenties die aan hen zijn toegewezen:</span><span class="sxs-lookup"><span data-stu-id="fc117-129">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="fc117-130">De beheerder die deze instellingen voor het maken van groepen configureert</span><span class="sxs-lookup"><span data-stu-id="fc117-130">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="fc117-131">De leden van de groep die groepen mogen maken</span><span class="sxs-lookup"><span data-stu-id="fc117-131">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="fc117-132">Zie [Licenties toewijzen of verwijderen in](/azure/active-directory/fundamentals/license-users-groups) de Azure Active Directory portal voor meer informatie over het toewijzen van Azure-licenties.</span><span class="sxs-lookup"><span data-stu-id="fc117-132">See [Assign or remove licenses in the Azure Active Directory portal](/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="fc117-133">De volgende personen hebben geen Azure AD-Premium of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:</span><span class="sxs-lookup"><span data-stu-id="fc117-133">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="fc117-134">Personen die lid zijn van Microsoft 365 groepen en die niet de mogelijkheid hebben om andere groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="fc117-134">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="fc117-135">Stap 1: Een groep maken voor gebruikers die groepen Microsoft 365 maken</span><span class="sxs-lookup"><span data-stu-id="fc117-135">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="fc117-136">Slechts één groep in uw organisatie kan worden gebruikt om te bepalen wie groepen kan maken.</span><span class="sxs-lookup"><span data-stu-id="fc117-136">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="fc117-137">Maar u kunt andere groepen nesten als leden van deze groep.</span><span class="sxs-lookup"><span data-stu-id="fc117-137">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="fc117-138">Beheerders in de bovenstaande rollen hoeven geen lid te zijn van deze groep: ze behouden hun mogelijkheid om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="fc117-138">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="fc117-139">Ga in het beheercentrum naar de pagina [Groepen.](https://admin.microsoft.com/adminportal/home#/groups)</span><span class="sxs-lookup"><span data-stu-id="fc117-139">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="fc117-140">Klik op **Een groep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="fc117-140">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="fc117-141">Kies het groeptype dat u wilt.</span><span class="sxs-lookup"><span data-stu-id="fc117-141">Choose the group type you want.</span></span> <span data-ttu-id="fc117-142">Onthoud de naam van de groep goed.</span><span class="sxs-lookup"><span data-stu-id="fc117-142">Remember the name of the group!</span></span> <span data-ttu-id="fc117-143">Deze hebt u later nodig.</span><span class="sxs-lookup"><span data-stu-id="fc117-143">You'll need it later.</span></span>

4. <span data-ttu-id="fc117-144">Sluit het instellen van de groep af, voeg personen of andere groepen toe die u groepen in uw organisatie wilt kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="fc117-144">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="fc117-145">Zie Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365 [voor gedetailleerde instructies.](../admin/email/create-edit-or-delete-a-security-group.md)</span><span class="sxs-lookup"><span data-stu-id="fc117-145">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="fc117-146">Stap 2: PowerShell-opdrachten uitvoeren</span><span class="sxs-lookup"><span data-stu-id="fc117-146">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="fc117-147">U moet de preview-versie van [Azure Active Directory PowerShell voor Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fc117-147">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="fc117-148">Zie De [Azure AD-module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) installeren als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd en volg de instructies voor het installeren van de openbare preview-release.</span><span class="sxs-lookup"><span data-stu-id="fc117-148">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="fc117-149">Als u de 2.0 algemene beschikbaarheidsversie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te laten lopen in uw PowerShell-sessie en vervolgens de preview-versie te installeren door het uitvoeren `Uninstall-Module AzureAD` `Install-Module AzureADPreview` van .</span><span class="sxs-lookup"><span data-stu-id="fc117-149">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="fc117-150">Als u de preview-versie al hebt geïnstalleerd, moet u ervoor zorgen dat deze de `Install-Module AzureADPreview` nieuwste versie van deze module is.</span><span class="sxs-lookup"><span data-stu-id="fc117-150">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="fc117-151">Kopieer het script hieronder naar een teksteditor, zoals Kladblok of de [Windows PowerShell ISE.](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="fc117-151">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="fc117-152">Vervang *\<GroupName\>* door de naam van de groep die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="fc117-152">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="fc117-153">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="fc117-153">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="fc117-154">Sla het bestand op als GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="fc117-154">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="fc117-155">Ga in het PowerShell-venster naar de locatie waar u het bestand hebt opgeslagen (typ <FileLocation> 'CD').</span><span class="sxs-lookup"><span data-stu-id="fc117-155">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="fc117-156">Voer het script uit door te typen:</span><span class="sxs-lookup"><span data-stu-id="fc117-156">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="fc117-157">en [meld u aan met uw beheerdersaccount](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="fc117-157">and [sign in with your administrator account](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="fc117-158">Op de laatste regel van het script worden de bijgewerkte instellingen weergegeven:</span><span class="sxs-lookup"><span data-stu-id="fc117-158">The last line of the script will display the updated settings:</span></span>

![Schermafbeelding van powershell-scriptuitvoer.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="fc117-160">Als u in de toekomst wilt wijzigen welke groep wordt gebruikt, kunt u het script opnieuw uitvoeren met de naam van de nieuwe groep.</span><span class="sxs-lookup"><span data-stu-id="fc117-160">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="fc117-161">Als u de beperking voor het maken van groepen wilt uitschakelen en alle gebruikers opnieuw groepen wilt toestaan, stelt u $GroupName in op '' en $AllowGroupCreation op 'Waar' en het script opnieuw uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="fc117-161">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="fc117-162">Stap 3: controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="fc117-162">Step 3: Verify that it works</span></span>

<span data-ttu-id="fc117-163">Wijzigingen kunnen dertig minuten of meer duren.</span><span class="sxs-lookup"><span data-stu-id="fc117-163">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="fc117-164">U kunt de nieuwe instellingen als volgt controleren:</span><span class="sxs-lookup"><span data-stu-id="fc117-164">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="fc117-165">Meld u aan bij Microsoft 365 met een gebruikersaccount van iemand die niet de mogelijkheid zou moeten hebben om groepen te maken.</span><span class="sxs-lookup"><span data-stu-id="fc117-165">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="fc117-166">Dat wil zeggen dat ze geen lid zijn van de groep die u hebt gemaakt of een beheerder.</span><span class="sxs-lookup"><span data-stu-id="fc117-166">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="fc117-167">Selecteer de **tegel Planner.**</span><span class="sxs-lookup"><span data-stu-id="fc117-167">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="fc117-168">Selecteer nieuw plan in **de** linkernavigatie om een plan te maken in Planner.</span><span class="sxs-lookup"><span data-stu-id="fc117-168">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="fc117-169">U krijgt een bericht dat het plannen en maken van groepen is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="fc117-169">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="fc117-170">Probeer dezelfde procedure opnieuw met een lid van de groep.</span><span class="sxs-lookup"><span data-stu-id="fc117-170">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="fc117-171">Als leden van de groep geen groepen kunnen maken, controleert u of ze niet worden geblokkeerd via hun [OWA-postvakbeleid.](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="fc117-171">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc117-172">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="fc117-172">Related topics</span></span>

[<span data-ttu-id="fc117-173">Planning van samenwerkingsbeheer stap voor stap</span><span class="sxs-lookup"><span data-stu-id="fc117-173">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="fc117-174">Uw samenwerkingsbeheerplan maken</span><span class="sxs-lookup"><span data-stu-id="fc117-174">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="fc117-175">Getting started with Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc117-175">Getting started with Office 365 PowerShell</span></span>](../enterprise/getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="fc117-176">Selfservicegroepsbeheer instellen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fc117-176">Set up self-service group management in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="fc117-177">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="fc117-177">Set-ExecutionPolicy</span></span>](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="fc117-178">Azure Active Directory cmdlets voor het configureren van groepsinstellingen</span><span class="sxs-lookup"><span data-stu-id="fc117-178">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
