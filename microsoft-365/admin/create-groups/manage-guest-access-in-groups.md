---
title: Gasttoegang beheren in Microsoft 365-groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Meer informatie over het toevoegen van gasten aan een Microsoft 365-groep, het bekijken van gastgebruikers en het gebruik van PowerShell om de toegang van gasten te beheren.
ms.openlocfilehash: 0322bd269f1c5637627461d136b40f6af4fc9540
ms.sourcegitcommit: 4512f54ba80d869d4c04e8f9bd897d1878280852
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2020
ms.locfileid: "44854244"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="2a734-103">Gasttoegang beheren in Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="2a734-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="2a734-104">Standaard is gasttoegang voor Microsoft 365-groepen ingeschakeld voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2a734-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="2a734-105">Beheerders kunnen bepalen of ze gasten toegang willen geven tot groepen voor hun hele organisatie of voor afzonderlijke groepen.</span><span class="sxs-lookup"><span data-stu-id="2a734-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="2a734-106">Wanneer deze is ingeschakeld, kunnen groepsleden gastgebruikers uitnodigen voor een Microsoft 365-groep via Outlook on Web.</span><span class="sxs-lookup"><span data-stu-id="2a734-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="2a734-107">Uitnodigingen worden ter goedkeuring naar de eigenaar van de groep gestuurd.</span><span class="sxs-lookup"><span data-stu-id="2a734-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="2a734-108">Na goedkeuring wordt de gastgebruiker toegevoegd aan de map en de groep.</span><span class="sxs-lookup"><span data-stu-id="2a734-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="2a734-109">Yammer Enterprise-netwerken in native mode of de [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) ondersteunen geen netwerkgasten.</span><span class="sxs-lookup"><span data-stu-id="2a734-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="2a734-110">Microsoft 365 Connected Yammer-groepen bieden momenteel geen ondersteuning voor gasttoegang, maar u niet-verbonden, externe groepen in uw Yammer-netwerk maken.</span><span class="sxs-lookup"><span data-stu-id="2a734-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="2a734-111">Zie [Externe groepen maken en beheren in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="2a734-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="2a734-112">Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario dat SharePoint of Teams omvat.</span><span class="sxs-lookup"><span data-stu-id="2a734-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="2a734-113">Deze services hebben hun eigen instellingen voor het delen van gasten.</span><span class="sxs-lookup"><span data-stu-id="2a734-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="2a734-114">Zie voor volledige instructies voor het instellen van het delen van gasten tussen groepen, SharePoint en Teams:</span><span class="sxs-lookup"><span data-stu-id="2a734-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="2a734-115">Samenwerken met gasten op een site</span><span class="sxs-lookup"><span data-stu-id="2a734-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="2a734-116">Samenwerken met gasten in een team</span><span class="sxs-lookup"><span data-stu-id="2a734-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="2a734-117">Toegang tot groepen beheren</span><span class="sxs-lookup"><span data-stu-id="2a734-117">Manage groups guest access</span></span>

<span data-ttu-id="2a734-118">Als u gasttoegang in groepen wilt in- of uitschakelen, u dit doen in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2a734-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="2a734-119">Ga in het beheercentrum naar **Alle** instellingen instellingen die \> **Settings** \> **orginstellingen weergeven** en selecteer op het tabblad **Services** **Microsoft 365-groepen**.</span><span class="sxs-lookup"><span data-stu-id="2a734-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="2a734-120">Kies op de pagina **Microsoft 365-groepen** of u mensen buiten uw organisatie groepsbronnen wilt laten openen of dat groepseigenaren mensen buiten uw organisatie aan groepen wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="2a734-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="2a734-121">Gasten toevoegen aan een Microsoft 365-groep vanuit het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="2a734-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="2a734-122">Als de gast al in uw map bestaat, u deze toevoegen aan uw groepen vanuit het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2a734-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="2a734-123">Ga in het beheercentrum **Groups**naar de pagina  >  **Groepen groepen.**</span><span class="sxs-lookup"><span data-stu-id="2a734-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="2a734-124">Klik op de groep waaraan u de gast wilt toevoegen en selecteer **Alle leden weergeven en beheren** op het tabblad **Leden.**</span><span class="sxs-lookup"><span data-stu-id="2a734-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="2a734-125">Selecteer **Leden toevoegen**en kies de naam van de gast die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="2a734-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="2a734-126">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2a734-126">Select **Save**.</span></span>

<span data-ttu-id="2a734-127">Als u een gast rechtstreeks aan de map wilt toevoegen, u [Azure Active Directory B2B-samenwerkingsgebruikers toevoegen in de Azure-portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="2a734-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="2a734-128">Als u een van de gegevens van een gast wilt bewerken, u [de profielgegevens](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)van een gebruiker toevoegen of bijwerken met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a734-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="2a734-129">Gastgebruikers blokkeren uit een specifieke groep</span><span class="sxs-lookup"><span data-stu-id="2a734-129">Block guest users from a specific group</span></span>

<span data-ttu-id="2a734-130">Als u gasttoegang tot de meeste groepen wilt toestaan, maar een aantal wilt hebben waar u gasttoegang wilt voorkomen, u de toegang van gasten voor afzonderlijke groepen blokkeren met Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a734-130">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="2a734-131">U moet de voorbeeldversie van [Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="2a734-131">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="2a734-132">Als u nog geen versie van de Azure AD PowerShell-module eerder hebt geïnstalleerd, raadpleegt u [De Azure AD-module installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en de instructies volgen om de versie van de openbare preview te installeren.</span><span class="sxs-lookup"><span data-stu-id="2a734-132">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="2a734-133">Als u de 2.0 algemene beschikbaarheidsversie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te voeren `Uninstall-Module AzureAD` in uw PowerShell-sessie en vervolgens de preview-versie installeren door `Install-Module AzureADPreview` .</span><span class="sxs-lookup"><span data-stu-id="2a734-133">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="2a734-134">Als u de preview-versie al hebt geïnstalleerd, moet u `Install-Module AzureADPreview` ervoor zorgen dat dit de nieuwste versie van deze module is.</span><span class="sxs-lookup"><span data-stu-id="2a734-134">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="2a734-135">U moet algemene beheerdersrechten hebben om deze opdrachten uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2a734-135">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="2a734-136">Voer het volgende script uit en wijzig */<GroupName/>* de naam van de groep waar u gasttoegang wilt blokkeren.</span><span class="sxs-lookup"><span data-stu-id="2a734-136">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="2a734-137">Voer deze opdracht uit om uw instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="2a734-137">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="2a734-138">De verificatie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="2a734-138">The verification looks like this:</span></span>
    
![Schermafbeelding van het PowerShell-venster waaruit blijkt dat de toegang tot de gastgroep is ingesteld op false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="2a734-140">Toegang van gasten toestaan of blokkeren op basis van hun domein</span><span class="sxs-lookup"><span data-stu-id="2a734-140">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="2a734-141">U gastgebruikers die een specifiek domein gebruiken toestaan of blokkeren.</span><span class="sxs-lookup"><span data-stu-id="2a734-141">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="2a734-142">Als uw bedrijf (Contoso) bijvoorbeeld een partnerschap heeft met een ander bedrijf (Fabrikam), u Fabrikam toevoegen aan uw lijst Toestaan, zodat uw gebruikers deze gasten aan hun groepen kunnen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="2a734-142">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="2a734-143">Zie [Uitnodigingen voor B2B-gebruikers van specifieke organisaties toestaan of blokkeren voor](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2a734-143">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="2a734-144">Gasten toevoegen aan de algemene adreslijst</span><span class="sxs-lookup"><span data-stu-id="2a734-144">Add guests to the global address list</span></span>

<span data-ttu-id="2a734-145">Gasten zijn standaard niet zichtbaar in de algemene adreslijst van Exchange.</span><span class="sxs-lookup"><span data-stu-id="2a734-145">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="2a734-146">Gebruik de onderstaande stappen om een gast zichtbaar te maken in de algemene adreslijst.</span><span class="sxs-lookup"><span data-stu-id="2a734-146">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="2a734-147">Zoek de ObjectID van de gastgebruiker door uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="2a734-147">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="2a734-148">Voer vervolgens het volgende uit met de juiste waarden voor ObjectID, GivenName, Achternaam, DisplayName en Telefoonnummer.</span><span class="sxs-lookup"><span data-stu-id="2a734-148">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="2a734-149">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="2a734-149">Related articles</span></span>

[<span data-ttu-id="2a734-150">Groepslidmaatschap beheren in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="2a734-150">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="2a734-151">Azure Active Directory-toegangsbeoordelingen</span><span class="sxs-lookup"><span data-stu-id="2a734-151">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="2a734-152">AzureADUser instellen</span><span class="sxs-lookup"><span data-stu-id="2a734-152">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
