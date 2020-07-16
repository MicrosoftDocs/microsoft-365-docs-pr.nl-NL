---
title: Toegang tot de beheerportal
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146265"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="fbc7d-103">Toegang tot de beheerportal</span><span class="sxs-lookup"><span data-stu-id="fbc7d-103">Access the admin portal</span></span>

<span data-ttu-id="fbc7d-104">Uw gateway naar de Microsoft Managed Desktop-service is de Microsoft [Azure-portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="fbc7d-104">Your gateway to the Microsoft Managed Desktop service is the Microsoft [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="fbc7d-105">Zie de [Azure-portaldocumentatie](https://docs.microsoft.com/azure/azure-portal/)voor meer informatie over het gebruik en aanpassen van uw Azure-portalervaring in het algemeen.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-105">For more about using and customizing your Azure portal experience generally, see the [Azure portal documentation](https://docs.microsoft.com/azure/azure-portal/).</span></span> 

<span data-ttu-id="fbc7d-106">Uw beheeraccount heeft specifieke machtigingen nodig om toegang te krijgen tot de Microsoft Managed Desktop Admin-portal.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-106">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="fbc7d-107">U de toegang van beheerders tot deze functies binnen uw organisatie beheren met behulp van Role-based Access Control (RBAC).</span><span class="sxs-lookup"><span data-stu-id="fbc7d-107">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="fbc7d-108">Zie [Machtigingen administratorrol in Azure Active Directory voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)meer informatie over Azure Active Directory-rollen.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-108">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="fbc7d-109">Wijs uw beheerdersaccounts een van de volgende rollen toe om toegang te garanderen:</span><span class="sxs-lookup"><span data-stu-id="fbc7d-109">Assign your admin user accounts any of the following roles to ensure access:</span></span>

|<span data-ttu-id="fbc7d-110">Azure AD-rol</span><span class="sxs-lookup"><span data-stu-id="fbc7d-110">Azure AD role</span></span>  |<span data-ttu-id="fbc7d-111">Machtigingen voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="fbc7d-111">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="fbc7d-112">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="fbc7d-112">Global Administrator</span></span>     | <span data-ttu-id="fbc7d-113">Beheerders met deze rol hebben **lees- en schrijfmachtigingen** voor alle functies in de Microsoft Managed Desktop Admin-portal.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-113">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="fbc7d-114">Global Reader</span><span class="sxs-lookup"><span data-stu-id="fbc7d-114">Global Reader</span></span>     | <span data-ttu-id="fbc7d-115">Beheerders met deze rol hebben **alleen-lezen machtigingen** voor alle functies in de Microsoft Managed Desktop Admin-portal.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-115">Admins with this role will have **read-only permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="fbc7d-116">Intune-servicebeheerder</span><span class="sxs-lookup"><span data-stu-id="fbc7d-116">Intune Service Administrator</span></span>     |  <span data-ttu-id="fbc7d-117">Beheerders met deze rol hebben **lees- en schrijfmachtigingen** voor alle functies in de Microsoft Managed Desktop Admin-portal.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-117">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="fbc7d-118">Beheerder van serviceondersteuning</span><span class="sxs-lookup"><span data-stu-id="fbc7d-118">Service Support Administrator</span></span>     | <span data-ttu-id="fbc7d-119">Beheerders met deze rol hebben **lees- en schrijfmachtigingen** voor alle functies in de Microsoft Managed Desktop Admin-portal.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-119">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="fbc7d-120">Alleen de rol Global Administrator heeft de benodigde machtigingen om uw organisatie in te *schrijven* in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-120">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="fbc7d-121">Houd er rekening mee dat Azure Active Directory-rollen gebruikersaccounts bevoegdheden geven voor verschillende Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-121">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="fbc7d-122">Nadat u de inschrijving bij Microsoft Managed Desktop hebt voltooid, moet u altijd de rol gebruiken met de *minste* bevoegdheden die nodig zijn om uw andere taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-122">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="fbc7d-123">Rollen toewijzen aan beheerders</span><span class="sxs-lookup"><span data-stu-id="fbc7d-123">Assigning roles to administrators</span></span>

<span data-ttu-id="fbc7d-124">Zie [Machtigingen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)voor beheerdersrol in Azure Active Directory als u hulp nodig hebt bij het toewijzen van Azure Active Directory-rollen.</span><span class="sxs-lookup"><span data-stu-id="fbc7d-124">If you need help assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>
