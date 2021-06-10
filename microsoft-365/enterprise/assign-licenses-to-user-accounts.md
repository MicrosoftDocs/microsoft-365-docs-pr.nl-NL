---
title: Licenties Microsoft 365 gebruikersaccounts toewijzen
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
description: Hier wordt beschreven hoe u Microsoft 365 licenties toewijst aan gebruikersaccounts, afzonderlijk of op basis van groepslidmaatschap.
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051530"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="45ab1-103">Licenties Microsoft 365 gebruikersaccounts toewijzen</span><span class="sxs-lookup"><span data-stu-id="45ab1-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="45ab1-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="45ab1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="45ab1-105">Voor het cloud-only-identiteitsmodel kunt u Microsoft 365 licenties toewijzen aan gebruikersaccounts terwijl deze worden gemaakt, afhankelijk van hoe u deze maakt.</span><span class="sxs-lookup"><span data-stu-id="45ab1-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="45ab1-106">Voor het hybride identiteitsmodel worden gebruikersaccounts van Active Directory Domain Services (AD DS) niet automatisch een locatie of een Microsoft 365 toegewezen.</span><span class="sxs-lookup"><span data-stu-id="45ab1-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="45ab1-107">**U moet elk gebruikersaccount configureren met een gebruikerslocatie vóór of samen met het toewijzen van een licentie.**</span><span class="sxs-lookup"><span data-stu-id="45ab1-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="45ab1-108">In beide gevallen moet u een licentie toewijzen aan gebruikersaccounts, zodat uw gebruikers toegang hebben tot Microsoft 365 services, zoals e-mail en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="45ab1-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="45ab1-109">U kunt licenties aan gebruikersaccounts afzonderlijk of automatisch toewijzen via groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="45ab1-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="45ab1-110">Als u Microsoft 365 licenties wilt toewijzen aan afzonderlijke gebruikersaccounts, kunt u het volgende gebruiken:</span><span class="sxs-lookup"><span data-stu-id="45ab1-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="45ab1-111">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="45ab1-111">The Microsoft 365 admin center</span></span>](../admin/manage/assign-licenses-to-users.md)
- [<span data-ttu-id="45ab1-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="45ab1-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="45ab1-113">Het Azure AD-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="45ab1-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="45ab1-114">Licenties op groepsbasis</span><span class="sxs-lookup"><span data-stu-id="45ab1-114">Group-based licensing</span></span>

<span data-ttu-id="45ab1-115">U kunt beveiligingsgroepen configureren in Azure AD om automatisch licenties van een set abonnementen toe te wijzen aan alle leden van de groep.</span><span class="sxs-lookup"><span data-stu-id="45ab1-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="45ab1-116">Dit wordt *licenties op groepsbasis* genoemd.</span><span class="sxs-lookup"><span data-stu-id="45ab1-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="45ab1-117">Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit de groep, worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van het gebruikersaccount. </span><span class="sxs-lookup"><span data-stu-id="45ab1-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="45ab1-118">Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden.</span><span class="sxs-lookup"><span data-stu-id="45ab1-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="45ab1-119">Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="45ab1-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="45ab1-120">Voor groepen die Azure B2B-accounts (business-to-business) bevatten, dient u licenties op groepsbasis niet te configureren.</span><span class="sxs-lookup"><span data-stu-id="45ab1-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="45ab1-121">Zie groepslicenties in Azure AD voor [meer informatie.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="45ab1-121">For more informaion, see [group-based licensing in Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="45ab1-122">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="45ab1-122">Next steps</span></span>

<span data-ttu-id="45ab1-123">Met de juiste set gebruikersaccounts die zijn toegewezen aan licenties, kunt u nu het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="45ab1-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="45ab1-124">Beveiliging implementeren</span><span class="sxs-lookup"><span data-stu-id="45ab1-124">Implement security</span></span>](../security/defender-365-security/security-roadmap.md)
- [<span data-ttu-id="45ab1-125">Clientsoftware implementeren, zoals Microsoft 365-apps</span><span class="sxs-lookup"><span data-stu-id="45ab1-125">Deploy client software, such as Microsoft 365 Apps</span></span>](/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="45ab1-126">Apparaatbeheer instellen</span><span class="sxs-lookup"><span data-stu-id="45ab1-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="45ab1-127">Services en toepassingen configureren</span><span class="sxs-lookup"><span data-stu-id="45ab1-127">Configure services and applications</span></span>](configure-services-and-applications.md)