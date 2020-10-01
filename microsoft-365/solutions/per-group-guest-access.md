---
title: Gastgebruikers blokkeren voor een bepaalde groep
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Gastgebruikers blokkeren voor een bepaalde groep
ms.openlocfilehash: 2e9c9cae13932a33b8c486148f93901904e80006
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328015"
---
# <a name="block-guest-users-from-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="5f8ad-103">Gastgebruikers blokkeren vanuit een specifieke Microsoft 365-groep of een Microsoft teams-team</span><span class="sxs-lookup"><span data-stu-id="5f8ad-103">Block guest users from a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="5f8ad-104">Als u gasttoegang wilt verlenen tot de meeste groepen en teams, maar wel een deel van de toegang tot gasttoegang wilt blokkeren, kunt u gasttoegang voor afzonderlijke groepen en teams blokkeren.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="5f8ad-105">(Het blokkeren van toegang tot een team is ongedaan gemaakt door gasttoegang tot de bijbehorende groep te blokkeren).</span><span class="sxs-lookup"><span data-stu-id="5f8ad-105">(Blocking guest access to a team is done by blocking guest access to the associated group.)</span></span>

<span data-ttu-id="5f8ad-106">Als u de palletlabels in uw organisatie gebruikt, raden we u aan ze te gebruiken voor het beheren van gasttoegang per groep.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="5f8ad-107">Voor informatie over hoe u dit doet, [kunt u de vertrouwelijkheids labels gebruiken om inhoud te beschermen in Microsoft teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="5f8ad-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="5f8ad-108">Dit is de aanbevolen aanpak.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-108">This is the recommended approach.</span></span>

<span data-ttu-id="5f8ad-109">U kunt gasttoegang voor afzonderlijke groepen ook blokkeren met behulp van Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-109">You can also block guest access to individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="5f8ad-110">U moet de preview-versie van [Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) gebruiken om de instelling voor gasttoegang op het groepeerniveau te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="5f8ad-110">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="5f8ad-111">Als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd, raadpleegt u [de module van Azure AD installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en volgt u de instructies voor het installeren van de openbare preview-versie.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-111">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="5f8ad-112">Als u de algemene beschikbaarheid van 2,0 van de versie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door `Uninstall-Module AzureAD` in uw PowerShell-sessie te worden uitgevoerd, en de preview-versie vervolgens te installeren `Install-Module AzureADPreview` .</span><span class="sxs-lookup"><span data-stu-id="5f8ad-112">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="5f8ad-113">Als u de preview-versie al hebt geïnstalleerd, controleert u `Install-Module AzureADPreview` of deze de nieuwste versie van deze module is.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-113">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="5f8ad-114">U moet over globale beheerdersrechten beschikken om deze opdrachten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-114">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="5f8ad-115">Voer het volgende script uit en wijzig */<GroupName/>* de naam van de groep waarin u gasttoegang wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-115">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="5f8ad-116">Als u uw instellingen wilt controleren, voert u deze opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5f8ad-116">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="5f8ad-117">De verificatie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="5f8ad-117">The verification looks like this:</span></span>
    
![Schermafbeelding van het PowerShell-venster waarin wordt aangegeven dat toegang tot gast groepen is ingesteld op ONWAAR.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="5f8ad-119">Gasttoegang op basis van hun domein toestaan of blokkeren</span><span class="sxs-lookup"><span data-stu-id="5f8ad-119">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="5f8ad-120">U kunt gastgebruikers die een specifiek domein gebruiken toestaan of blokkeren.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-120">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="5f8ad-121">Als uw bedrijf (Contoso) bijvoorbeeld een partnership heeft met een ander bedrijf (fabrikam), kunt u fabrikam toevoegen aan uw lijst toestaan, zodat uw gebruikers deze gasten kunnen toevoegen aan hun groepen.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-121">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="5f8ad-122">Zie [uitnodigingen voor B2B-gebruikers in specifieke organisaties toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-122">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="5f8ad-123">Gasten toevoegen aan de algemene adreslijst</span><span class="sxs-lookup"><span data-stu-id="5f8ad-123">Add guests to the global address list</span></span>

<span data-ttu-id="5f8ad-124">Gasten worden standaard niet weergegeven in de algemene adreslijst van Exchange.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-124">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="5f8ad-125">Volg de onderstaande stappen om een gast zichtbaar te maken in de algemene adreslijst.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-125">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="5f8ad-126">Ga als volgt te werk om de ObjectID van de gastgebruiker op te voeren:</span><span class="sxs-lookup"><span data-stu-id="5f8ad-126">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="5f8ad-127">Voer vervolgens de volgende opdracht uit om de juiste waarden te gebruiken voor ObjectID, OpgegevenNaam, achternaam, weergavenaam en TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="5f8ad-127">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="5f8ad-128">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="5f8ad-128">Related articles</span></span>

[<span data-ttu-id="5f8ad-129">Groepslidmaatschap beheren in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="5f8ad-129">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="5f8ad-130">Azure Active Directory Access-beoordelingen</span><span class="sxs-lookup"><span data-stu-id="5f8ad-130">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="5f8ad-131">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="5f8ad-131">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)