---
title: Gasttoegang beheren in Microsoft 365 groepen
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
description: Meer informatie over het toevoegen van gasten aan een Microsoft 365-groep, het weergeven van gastgebruikers en het gebruik van PowerShell voor het beheer van gasttoegang.
ms.openlocfilehash: 640a35cbb1a3eb395453b224cadcf0d0db82fab8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326517"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="1c230-103">Gasttoegang beheren in Microsoft 365 groepen</span><span class="sxs-lookup"><span data-stu-id="1c230-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="1c230-104">Gasttoegang voor Microsoft 365-groepen is standaard ingeschakeld voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1c230-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="1c230-105">Beheerders kunnen instellen dat gasttoegang voor groepen voor hun gehele organisatie of voor afzonderlijke groepen moet worden toegestaan.</span><span class="sxs-lookup"><span data-stu-id="1c230-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="1c230-106">Als u deze hebt ingeschakeld, kunnen groepsleden gastgebruikers uitnodigen voor een Microsoft 365-groep via de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="1c230-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="1c230-107">Uitnodigingen worden verzonden naar de groepseigenaar voorgoed keuring.</span><span class="sxs-lookup"><span data-stu-id="1c230-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="1c230-108">Nadat de gastgebruiker is goedgekeurd, wordt deze toegevoegd aan de adreslijst en de groep.</span><span class="sxs-lookup"><span data-stu-id="1c230-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="1c230-109">Yammer Enterprise-netwerken in de native modus van de [Europese](https://go.microsoft.com/fwlink/?linkid=2107357) organisatie ondersteunen geen netwerkgasten.</span><span class="sxs-lookup"><span data-stu-id="1c230-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="1c230-110">Microsoft 365 verbonden Yammer-groepen bieden momenteel geen ondersteuning voor gasttoegang, maar u kunt niet-verbonden externe groepen maken in uw Yammer-netwerk.</span><span class="sxs-lookup"><span data-stu-id="1c230-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="1c230-111">Zie [externe groepen in Yammer maken en beheren](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="1c230-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="1c230-112">Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario dat SharePoint of teams omvat.</span><span class="sxs-lookup"><span data-stu-id="1c230-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="1c230-113">Deze services hebben hun eigen instellingen voor het delen van gasten.</span><span class="sxs-lookup"><span data-stu-id="1c230-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="1c230-114">Voor uitgebreide instructies voor het instellen van gast delen in groepen, SharePoint en teams, raadpleegt u:</span><span class="sxs-lookup"><span data-stu-id="1c230-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="1c230-115">Samenwerken met gasten op een site</span><span class="sxs-lookup"><span data-stu-id="1c230-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="1c230-116">Met gasten samenwerken in een team</span><span class="sxs-lookup"><span data-stu-id="1c230-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="1c230-117">Gasttoegang voor groepen beheren</span><span class="sxs-lookup"><span data-stu-id="1c230-117">Manage groups guest access</span></span>

<span data-ttu-id="1c230-118">Als u gasttoegang in groepen wilt in-of uitschakelen, kunt u dit doen in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1c230-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="1c230-119">Ga in het Beheercentrum naar instellingen voor de organisatie van **alle instellingen weergeven** \> **Settings** \> **Org settings** en selecteer **Microsoft 365-groepen**op het tabblad **Services** .</span><span class="sxs-lookup"><span data-stu-id="1c230-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="1c230-120">Op de pagina **Microsoft 365 groepen** kiest u of u wilt dat mensen buiten uw organisatie de groeps resources kunnen gebruiken of Groepseigenaars mensen van buiten uw organisatie kunnen toevoegen aan groepen.</span><span class="sxs-lookup"><span data-stu-id="1c230-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="1c230-121">Gasten toevoegen aan een Microsoft 365-groep vanuit het Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="1c230-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="1c230-122">Als de gast al bestaat in uw adreslijst, kunt u ze toevoegen aan uw groepen vanuit het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1c230-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="1c230-123">Ga in het Beheercentrum naar de pagina **groepen**  >  **groepen** .</span><span class="sxs-lookup"><span data-stu-id="1c230-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="1c230-124">Klik op de groep waaraan u de gast wilt toevoegen en selecteer **AllesWeergeven en leden weergeven** op het tabblad **leden** .</span><span class="sxs-lookup"><span data-stu-id="1c230-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="1c230-125">Selecteer **leden toevoegen**en kies de naam van de gast die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="1c230-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="1c230-126">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1c230-126">Select **Save**.</span></span>

<span data-ttu-id="1c230-127">Als u een gast rechtstreeks aan de adreslijst wilt toevoegen, voegt u [de gebruikers van Azure Active Directory B2B-samenwerking toe aan de Azure-Portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="1c230-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="1c230-128">Als u de gegevens van een gast wilt bewerken, kunt u [de profielgegevens van een gebruiker toevoegen of bijwerken met behulp van Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="1c230-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c230-129">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1c230-129">See also</span></span>

[<span data-ttu-id="1c230-130">Gastgebruikers blokkeren voor een bepaalde groep</span><span class="sxs-lookup"><span data-stu-id="1c230-130">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="1c230-131">Groepslidmaatschap beheren in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="1c230-131">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="1c230-132">Azure Active Directory Access-beoordelingen</span><span class="sxs-lookup"><span data-stu-id="1c230-132">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="1c230-133">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="1c230-133">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
