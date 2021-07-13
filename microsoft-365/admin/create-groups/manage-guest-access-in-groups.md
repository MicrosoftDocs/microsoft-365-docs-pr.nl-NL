---
title: Gasttoegang beheren in Microsoft 365 groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Lees hoe u gasten kunt toevoegen aan een Microsoft 365 groep, gastgebruikers kunt bekijken en PowerShell kunt gebruiken om gasttoegang te bepalen.
ms.openlocfilehash: 41a42a0b4fc76b71892f758519db56f4c1adc897
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394061"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="99049-103">Gasttoegang beheren in Microsoft 365 groepen</span><span class="sxs-lookup"><span data-stu-id="99049-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="99049-104">Standaard is gasttoegang voor Microsoft 365 groepen ingeschakeld voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="99049-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="99049-105">Beheerders kunnen bepalen of gasttoegang tot groepen moet worden toegestaan voor hun hele organisatie of voor afzonderlijke groepen.</span><span class="sxs-lookup"><span data-stu-id="99049-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="99049-106">Wanneer deze is ingeschakeld, kunnen groepsleden gastgebruikers uitnodigen voor een Microsoft 365 groep via Outlook web.</span><span class="sxs-lookup"><span data-stu-id="99049-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="99049-107">Uitnodigingen worden ter goedkeuring naar de groepseigenaar verzonden.</span><span class="sxs-lookup"><span data-stu-id="99049-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="99049-108">Wanneer deze is goedgekeurd, wordt de gastgebruiker toegevoegd aan de adreslijst en de groep.</span><span class="sxs-lookup"><span data-stu-id="99049-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="99049-109">Yammer Enterprise netwerken die zich in de autochtone modus of de [EU-geo](/yammer/manage-security-and-compliance/manage-data-compliance) hebben, bieden geen ondersteuning voor netwerkgasten.</span><span class="sxs-lookup"><span data-stu-id="99049-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="99049-110">Microsoft 365 Verbonden Yammer groepen bieden momenteel geen ondersteuning voor gasttoegang, maar u kunt niet-verbonden, externe groepen maken in uw Yammer netwerk.</span><span class="sxs-lookup"><span data-stu-id="99049-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="99049-111">Zie [Externe groepen maken en beheren in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="99049-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="99049-112">Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario met SharePoint of Teams.</span><span class="sxs-lookup"><span data-stu-id="99049-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="99049-113">Deze services hebben hun eigen instellingen voor het delen van gasten.</span><span class="sxs-lookup"><span data-stu-id="99049-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="99049-114">Zie voor volledige instructies voor het instellen van het delen van gasten in groepen, SharePoint en Teams:</span><span class="sxs-lookup"><span data-stu-id="99049-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="99049-115">Samenwerken met gasten op een site</span><span class="sxs-lookup"><span data-stu-id="99049-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="99049-116">Samenwerken met gasten in een team</span><span class="sxs-lookup"><span data-stu-id="99049-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="99049-117">Gasttoegang voor groepen beheren</span><span class="sxs-lookup"><span data-stu-id="99049-117">Manage groups guest access</span></span>

<span data-ttu-id="99049-118">Als u gasttoegang in groepen wilt in- of uitschakelen, kunt u dit doen in de Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="99049-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="99049-119">Ga in het beheercentrum naar **Alle** organisatie-instellingen Instellingen en selecteer op het tabblad \>  \>  **Services** **Microsoft 365 groepen.**</span><span class="sxs-lookup"><span data-stu-id="99049-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="99049-120">Kies op **Microsoft 365** pagina Groepen of u personen buiten uw organisatie toegang wilt geven tot groepsbronnen of dat groepseigenaren personen buiten uw organisatie aan groepen willen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="99049-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="99049-121">Gasten toevoegen aan een Microsoft 365 vanuit het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="99049-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="99049-122">Als de gast al aanwezig is in uw adreslijst, kunt u deze toevoegen aan uw groepen vanaf de Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="99049-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="99049-123">(Groepen met dynamisch lidmaatschap moeten worden [beheerd in](/azure/active-directory/enterprise-users/groups-create-rule)Azure Active Directory .)</span><span class="sxs-lookup"><span data-stu-id="99049-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="99049-124">Ga in het beheercentrum naar de pagina  >  **Groepen groepen.**</span><span class="sxs-lookup"><span data-stu-id="99049-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="99049-125">Klik op de groep aan wie u de gast wilt toevoegen en selecteer Alle leden weergeven en **beheren** op **het tabblad** Leden.</span><span class="sxs-lookup"><span data-stu-id="99049-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="99049-126">Selecteer **Leden toevoegen** en kies de naam van de gast die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="99049-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="99049-127">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="99049-127">Select **Save**.</span></span>

<span data-ttu-id="99049-128">Als u een gast rechtstreeks aan de adreslijst wilt toevoegen, kunt u Azure Active Directory [B2B-samenwerkingsgebruikers toevoegen in de Azure-portal.](/azure/active-directory/b2b/add-users-administrator)</span><span class="sxs-lookup"><span data-stu-id="99049-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="99049-129">Als u de gegevens van een gast wilt bewerken, kunt u de profielgegevens van een gebruiker toevoegen of bijwerken met behulp [van Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="99049-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="99049-130">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="99049-130">Related content</span></span>

<span data-ttu-id="99049-131">[Gastgebruikers blokkeren uit een specifieke groep](../../solutions/per-group-guest-access.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="99049-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>\
<span data-ttu-id="99049-132">[Groepslidmaatschap beheren in Microsoft 365-beheercentrum](add-or-remove-members-from-groups.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="99049-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>\
<span data-ttu-id="99049-133">[Azure Active Directory toegang tot reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artikel)</span><span class="sxs-lookup"><span data-stu-id="99049-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>\
<span data-ttu-id="99049-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artikel)</span><span class="sxs-lookup"><span data-stu-id="99049-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>