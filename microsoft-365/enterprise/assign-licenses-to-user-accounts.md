---
title: Microsoft 365-licenties toewijzen aan gebruikersaccounts
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
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
ms.openlocfilehash: 60936e52bffa58d50419f771e670848ee76271fd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688995"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="cc5de-103">Microsoft 365-licenties toewijzen aan gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="cc5de-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="cc5de-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cc5de-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cc5de-105">Voor het identiteits model Cloud only kunt u Microsoft 365-licenties toewijzen aan gebruikersaccounts wanneer ze worden gemaakt, afhankelijk van hoe u ze maakt.</span><span class="sxs-lookup"><span data-stu-id="cc5de-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="cc5de-106">Wanneer gebruikersaccounts van Active Directory Domain Services (AD DS) voor de eerste keer worden gesynchroniseerd, worden er niet automatisch een licentie voor Microsoft 365 toegewezen.</span><span class="sxs-lookup"><span data-stu-id="cc5de-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license.</span></span> <span data-ttu-id="cc5de-107">U moet eerst elk gebruikersaccount configureren op een gebruikerslocatie.</span><span class="sxs-lookup"><span data-stu-id="cc5de-107">You must first configure each user account with a user location.</span></span>

<span data-ttu-id="cc5de-108">In beide gevallen moet u een licentie toewijzen aan gebruikersaccounts, zodat uw gebruikers toegang hebben tot Microsoft 365-Services, zoals e-mail en Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="cc5de-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="cc5de-109">U kunt licenties toewijzen aan gebruikersaccounts afzonderlijk of automatisch via groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="cc5de-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="cc5de-110">U kunt Microsoft 365-licenties toewijzen aan afzonderlijke gebruikersaccounts via:</span><span class="sxs-lookup"><span data-stu-id="cc5de-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="cc5de-111">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="cc5de-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="cc5de-112">PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc5de-112">PowerShell for Microsoft 365</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="cc5de-113">Zie [Licentieverlening op groeps basis in azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)voor automatische licentietoewijzing.</span><span class="sxs-lookup"><span data-stu-id="cc5de-113">For automatic license assignment, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cc5de-114">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="cc5de-114">Next steps</span></span>

<span data-ttu-id="cc5de-115">Met de volledige set gebruikersaccounts waaraan een licentie is toegewezen, kunt u nu:</span><span class="sxs-lookup"><span data-stu-id="cc5de-115">With the full set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="cc5de-116">Beveiliging implementeren</span><span class="sxs-lookup"><span data-stu-id="cc5de-116">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="cc5de-117">Clientsoftware installeren, zoals Microsoft 365-apps</span><span class="sxs-lookup"><span data-stu-id="cc5de-117">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="cc5de-118">Mobile Device Management instellen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc5de-118">Set up Mobile Device Management in Microsoft 365</span></span>](https://support.office.com/article/set-up-mobile-device-management-mdm-in-office-365-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [<span data-ttu-id="cc5de-119">Services en toepassingen configureren</span><span class="sxs-lookup"><span data-stu-id="cc5de-119">Configure services and applications</span></span>](configure-services-and-applications.md)
