---
title: Voorkomen dat gasten worden toegevoegd aan een specifieke groep
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
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Informatie over het voorkomen dat gasten worden toegevoegd aan een specifieke groep
ms.openlocfilehash: 1db2055f3e546c05905dbf4c854333387112f06e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538925"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="0eb34-103">Voorkomen dat gasten worden toegevoegd aan een specifieke Microsoft 365 of Microsoft Teams team</span><span class="sxs-lookup"><span data-stu-id="0eb34-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="0eb34-104">Als u gasttoegang wilt toestaan tot de meeste groepen en teams, maar u een aantal plaatsen wilt hebben waar u gasttoegang wilt voorkomen, kunt u gasttoegang voor afzonderlijke groepen en teams blokkeren.</span><span class="sxs-lookup"><span data-stu-id="0eb34-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="0eb34-105">(Het blokkeren van gasttoegang tot een team wordt uitgevoerd door gasttoegang tot de gekoppelde groep te blokkeren.) Hiermee voorkomt u dat nieuwe gasten worden toegevoegd, maar worden gasten die al lid zijn van de groep of het team, niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0eb34-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="0eb34-106">Als u gevoeligheidslabels in uw organisatie gebruikt, raden we u aan deze te gebruiken om gasttoegang per groep te bepalen.</span><span class="sxs-lookup"><span data-stu-id="0eb34-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="0eb34-107">Voor informatie over hoe u dit doet, gebruikt u gevoeligheidslabels om inhoud [in Microsoft Teams, Microsoft 365 groepen](../compliance/sensitivity-labels-teams-groups-sites.md)en SharePoint beschermen.</span><span class="sxs-lookup"><span data-stu-id="0eb34-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span> <span data-ttu-id="0eb34-108">Dit is de aanbevolen methode.</span><span class="sxs-lookup"><span data-stu-id="0eb34-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="0eb34-109">Groepsinstellingen wijzigen met Microsoft PowerShell</span><span class="sxs-lookup"><span data-stu-id="0eb34-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="0eb34-110">U kunt ook de toevoeging van nieuwe gasten aan afzonderlijke groepen voorkomen met Behulp van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0eb34-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="0eb34-111">(Vergeet niet dat de gekoppelde site van het team SharePoint heeft afzonderlijke besturingselementen voor het [delen van gasten](/sharepoint/change-external-sharing-site).)</span><span class="sxs-lookup"><span data-stu-id="0eb34-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="0eb34-112">U moet de preview-versie van [Azure Active Directory PowerShell voor Graph](/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="0eb34-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="0eb34-113">Zie De [Azure AD-module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) installeren als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd en volg de instructies voor het installeren van de openbare preview-release.</span><span class="sxs-lookup"><span data-stu-id="0eb34-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="0eb34-114">Als u de 2.0 algemene beschikbaarheidsversie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te laten lopen in uw PowerShell-sessie en vervolgens de preview-versie te installeren door het uitvoeren `Uninstall-Module AzureAD` `Install-Module AzureADPreview` van .</span><span class="sxs-lookup"><span data-stu-id="0eb34-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="0eb34-115">Als u de preview-versie al hebt geïnstalleerd, moet u ervoor zorgen dat deze de `Install-Module AzureADPreview` nieuwste versie van deze module is.</span><span class="sxs-lookup"><span data-stu-id="0eb34-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="0eb34-116">U moet globale beheerdersrechten hebben om deze opdrachten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0eb34-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="0eb34-117">Voer het volgende script uit en ga naar de naam van de groep waarin */<GroupName/>* u gasttoegang wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="0eb34-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="0eb34-118">Voer deze opdracht uit om uw instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="0eb34-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="0eb34-119">De verificatie ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="0eb34-119">The verification looks like this:</span></span>
    
![Schermafbeelding van het PowerShell-venster waarin wordt weergegeven dat de toegang tot gastgroep is ingesteld op onwaar.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="0eb34-121">Gasttoegang toestaan of blokkeren op basis van hun domein</span><span class="sxs-lookup"><span data-stu-id="0eb34-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="0eb34-122">U kunt gasten die een specifiek domein gebruiken, toestaan of blokkeren.</span><span class="sxs-lookup"><span data-stu-id="0eb34-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="0eb34-123">Als uw bedrijf (Contoso) bijvoorbeeld een partnerschap heeft met een ander bedrijf (Fabrikam), kunt u Fabrikam toevoegen aan uw lijst Toestaan, zodat uw gebruikers deze gasten aan hun groepen kunnen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0eb34-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="0eb34-124">Zie Uitnodigingen toestaan of blokkeren voor [B2B-gebruikers van specifieke organisaties voor meer informatie.](/azure/active-directory/b2b/allow-deny-list)</span><span class="sxs-lookup"><span data-stu-id="0eb34-124">For more information, see [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="0eb34-125">Gasten toevoegen aan de algemene adreslijst</span><span class="sxs-lookup"><span data-stu-id="0eb34-125">Add guests to the global address list</span></span>

<span data-ttu-id="0eb34-126">Gasten zijn standaard niet zichtbaar in de Exchange algemene adreslijst.</span><span class="sxs-lookup"><span data-stu-id="0eb34-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="0eb34-127">Gebruik de onderstaande stappen om een gast zichtbaar te maken in de algemene adreslijst.</span><span class="sxs-lookup"><span data-stu-id="0eb34-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="0eb34-128">Zoek de object-id van de gast door het volgende uit te lopen:</span><span class="sxs-lookup"><span data-stu-id="0eb34-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="0eb34-129">Voer vervolgens het volgende uit met de juiste waarden voor ObjectID, GivenName, Achternaam, Weergavenaam en Telefoonnummer.</span><span class="sxs-lookup"><span data-stu-id="0eb34-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="0eb34-130">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0eb34-130">Related topics</span></span>

[<span data-ttu-id="0eb34-131">Planning van samenwerkingsbeheer stap voor stap</span><span class="sxs-lookup"><span data-stu-id="0eb34-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="0eb34-132">Uw samenwerkingsbeheerplan maken</span><span class="sxs-lookup"><span data-stu-id="0eb34-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="0eb34-133">Groepslidmaatschap beheren in het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="0eb34-133">Manage Group membership in the Microsoft 365 admin center</span></span>](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="0eb34-134">Azure Active Directory toegangsbeoordelingen</span><span class="sxs-lookup"><span data-stu-id="0eb34-134">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="0eb34-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="0eb34-135">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)