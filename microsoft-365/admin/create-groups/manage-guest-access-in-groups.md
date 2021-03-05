---
title: Gasttoegang beheren in Microsoft 365-groepen
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Informatie over het toevoegen van gasten aan een Microsoft 365-groep, het weergeven van gastgebruikers en het gebruik van PowerShell om gasttoegang te bepalen.
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453655"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="9aae9-103">Gasttoegang beheren in Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="9aae9-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="9aae9-104">Gasttoegang voor Microsoft 365-groepen is standaard ingeschakeld voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9aae9-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="9aae9-105">Beheerders kunnen bepalen of gasttoegang tot groepen moet worden toegestaan voor de hele organisatie of voor afzonderlijke groepen.</span><span class="sxs-lookup"><span data-stu-id="9aae9-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="9aae9-106">Wanneer deze is ingeschakeld, kunnen groepsleden gastgebruikers via de webversie van Outlook uitnodigen voor een Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="9aae9-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="9aae9-107">Uitnodigingen worden ter goedkeuring verzonden naar de groepseigenaar.</span><span class="sxs-lookup"><span data-stu-id="9aae9-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="9aae9-108">Nadat de gastgebruiker is goedgekeurd, wordt deze toegevoegd aan de adreslijst en de groep.</span><span class="sxs-lookup"><span data-stu-id="9aae9-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="9aae9-109">Yammer Enterprise-netwerken in de native modus of de [geo van](https://go.microsoft.com/fwlink/?linkid=2107357) de EU ondersteunen geen netwerk gasten.</span><span class="sxs-lookup"><span data-stu-id="9aae9-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="9aae9-110">Met Microsoft 365 verbonden Yammer-groepen worden momenteel geen gasttoegang ondersteund, maar u kunt niet-verbonden, externe groepen maken in uw Yammer-netwerk.</span><span class="sxs-lookup"><span data-stu-id="9aae9-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="9aae9-111">Zie [Externe groepen maken en beheren in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9aae9-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="9aae9-112">Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario met SharePoint of Teams.</span><span class="sxs-lookup"><span data-stu-id="9aae9-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="9aae9-113">Deze services hebben hun eigen instellingen voor het delen van gasten.</span><span class="sxs-lookup"><span data-stu-id="9aae9-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="9aae9-114">Voor volledige instructies voor het instellen van delen van gasten in groepen, SharePoint en Teams, gaat u naar:</span><span class="sxs-lookup"><span data-stu-id="9aae9-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="9aae9-115">Samenwerken met gasten op een site</span><span class="sxs-lookup"><span data-stu-id="9aae9-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="9aae9-116">Samenwerken met gasten in een team</span><span class="sxs-lookup"><span data-stu-id="9aae9-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="9aae9-117">Gasttoegang voor groepen beheren</span><span class="sxs-lookup"><span data-stu-id="9aae9-117">Manage groups guest access</span></span>

<span data-ttu-id="9aae9-118">Als u gasttoegang in groepen wilt in- of uitschakelen, kunt u dit doen in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="9aae9-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="9aae9-119">Ga in het beheercentrum naar **Alle instellingen** van de organisatie tonen en selecteer \>  \>  **Microsoft 365-groepen**  op het tabblad Services.</span><span class="sxs-lookup"><span data-stu-id="9aae9-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="9aae9-120">Kies op **de pagina Microsoft 365-groepen** of u personen buiten uw organisatie toegang wilt geven tot groepsbronnen of dat groepseigenaren personen van buiten uw organisatie aan groepen willen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="9aae9-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="9aae9-121">Gasten toevoegen aan een Microsoft 365-groep vanuit het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="9aae9-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="9aae9-122">Als de gast al bestaat in uw adreslijst, kunt u deze toevoegen aan uw groepen vanuit het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="9aae9-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="9aae9-123">(Groepen met dynamisch lidmaatschap moeten worden [beheerd in Azure Active Directory.)](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="9aae9-123">(Groups with dynamic membership must be [managed in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="9aae9-124">Ga in het beheercentrum naar de pagina  >  **Groepen.**</span><span class="sxs-lookup"><span data-stu-id="9aae9-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="9aae9-125">Klik op de groep aan wie u de gast wilt toevoegen en selecteer **Alle leden weergeven** en beheren op het **tabblad** Leden.</span><span class="sxs-lookup"><span data-stu-id="9aae9-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="9aae9-126">Selecteer **Leden toevoegen** en kies de naam van de gast die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="9aae9-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="9aae9-127">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9aae9-127">Select **Save**.</span></span>

<span data-ttu-id="9aae9-128">Als u een gast rechtstreeks aan de adreslijst wilt toevoegen, kunt u [B2B-samenwerkingsgebruikers](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)voor Azure Active Directory toevoegen in de Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="9aae9-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="9aae9-129">Als u de gegevens van een gast wilt bewerken, kunt u de profielgegevens van een gebruiker toevoegen of [bijwerken met Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="9aae9-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="9aae9-130">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9aae9-130">See also</span></span>

[<span data-ttu-id="9aae9-131">Gastgebruikers uit een specifieke groep blokkeren</span><span class="sxs-lookup"><span data-stu-id="9aae9-131">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="9aae9-132">Groepslidmaatschap beheren in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="9aae9-132">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="9aae9-133">Azure Active Directory-toegangsbeoordelingen</span><span class="sxs-lookup"><span data-stu-id="9aae9-133">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="9aae9-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="9aae9-134">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
