---
title: Microsoft 365-licenties toewijzen aan gebruikersaccounts
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Hierin wordt beschreven hoe u Microsoft 365-licenties toewijst aan gebruikersaccounts, afzonderlijk of op basis van groepslidmaatschap.
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326505"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="a1651-103">Microsoft 365-licenties toewijzen aan gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="a1651-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="a1651-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a1651-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a1651-105">Voor het identiteits model Cloud only kunt u Microsoft 365-licenties toewijzen aan gebruikersaccounts wanneer ze worden gemaakt, afhankelijk van hoe u ze maakt.</span><span class="sxs-lookup"><span data-stu-id="a1651-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="a1651-106">Wanneer gebruikersaccounts van Active Directory Domain Services (AD DS) voor de eerste keer worden gesynchroniseerd, worden er niet automatisch een locatie of een Microsoft 365-licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a1651-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="a1651-107">**U moet elk gebruikersaccount configureren met een gebruikerslocatie, voorafgaand aan of samen met het toewijzen van een licentie.**</span><span class="sxs-lookup"><span data-stu-id="a1651-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="a1651-108">In beide gevallen moet u een licentie toewijzen aan gebruikersaccounts, zodat uw gebruikers toegang hebben tot Microsoft 365-Services, zoals e-mail en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="a1651-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="a1651-109">U kunt licenties toewijzen aan gebruikersaccounts afzonderlijk of automatisch via groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="a1651-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="a1651-110">U kunt Microsoft 365-licenties toewijzen aan afzonderlijke gebruikersaccounts via:</span><span class="sxs-lookup"><span data-stu-id="a1651-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="a1651-111">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="a1651-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="a1651-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1651-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="a1651-113">Het Azure AD-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="a1651-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="a1651-114">Licenties op groepsbasis</span><span class="sxs-lookup"><span data-stu-id="a1651-114">Group-based licensing</span></span>

<span data-ttu-id="a1651-115">U kunt beveiligingsgroepen configureren in azure AD om automatisch licenties toe te wijzen aan een reeks abonnementen voor alle leden van de groep.</span><span class="sxs-lookup"><span data-stu-id="a1651-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="a1651-116">Dit wordt *licenties op groepsbasis* genoemd.</span><span class="sxs-lookup"><span data-stu-id="a1651-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="a1651-117">Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit de groep, worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van het gebruikersaccount. </span><span class="sxs-lookup"><span data-stu-id="a1651-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="a1651-118">Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden.</span><span class="sxs-lookup"><span data-stu-id="a1651-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="a1651-119">Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="a1651-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="a1651-120">Voor groepen die Azure B2B-accounts (business-to-business) bevatten, dient u licenties op groepsbasis niet te configureren.</span><span class="sxs-lookup"><span data-stu-id="a1651-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="a1651-121">Zie voor meer informatie over licenties op [groeps basis in azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="a1651-121">For more informaion, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a1651-122">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="a1651-122">Next steps</span></span>

<span data-ttu-id="a1651-123">Met de juiste set gebruikersaccounts waaraan een licentie is toegewezen, kunt u nu:</span><span class="sxs-lookup"><span data-stu-id="a1651-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="a1651-124">Beveiliging implementeren</span><span class="sxs-lookup"><span data-stu-id="a1651-124">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="a1651-125">Clientsoftware installeren, zoals Microsoft 365-apps</span><span class="sxs-lookup"><span data-stu-id="a1651-125">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="a1651-126">Apparaatbeheer instellen</span><span class="sxs-lookup"><span data-stu-id="a1651-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="a1651-127">Services en toepassingen configureren</span><span class="sxs-lookup"><span data-stu-id="a1651-127">Configure services and applications</span></span>](configure-services-and-applications.md)
