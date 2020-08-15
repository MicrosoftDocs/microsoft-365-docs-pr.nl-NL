---
title: Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 26b9ff81-93b0-4251-beaf-3c9f1d7c80c8
description: In dit artikel leest u hoe u Microsoft 365-gebruikersaccounts, licenties en groepen beheert met PowerShell.
ms.openlocfilehash: a262cbb62cd457e3a22550af2f773551cf67bb43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695742"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="fceae-103">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="fceae-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="fceae-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fceae-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fceae-105">Een van de primaire taken van een Microsoft 365-beheerder beheert gebruikersaccounts, licenties en groepen.</span><span class="sxs-lookup"><span data-stu-id="fceae-105">One of the primary tasks of any Microsoft 365 administrator is managing user accounts, licenses, and groups.</span></span> <span data-ttu-id="fceae-106">Hoewel u de meeste aspecten van deze taken kunt uitvoeren in het Microsoft 365-Beheercentrum, zijn andere taken veel sneller en eenvoudiger met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fceae-106">Although you can accomplish most aspects of these tasks in the Microsoft 365 admin center, other tasks are much quicker and easier with PowerShell.</span></span> 

<span data-ttu-id="fceae-107">Zie de volgende onderwerpen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fceae-107">For more information, see these topics.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="fceae-108">Gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="fceae-108">User accounts</span></span>

- [<span data-ttu-id="fceae-109">Create user accounts</span><span class="sxs-lookup"><span data-stu-id="fceae-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="fceae-110">Gebruikersaccounts weergeven</span><span class="sxs-lookup"><span data-stu-id="fceae-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="fceae-111">Eigenschappen van gebruikersaccounts configureren</span><span class="sxs-lookup"><span data-stu-id="fceae-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="fceae-112">Rollen toewijzen aan gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="fceae-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="fceae-113">Gebruikersaccounts verwijderen en herstellen</span><span class="sxs-lookup"><span data-stu-id="fceae-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="fceae-114">Gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="fceae-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="fceae-115">Licenties en services</span><span class="sxs-lookup"><span data-stu-id="fceae-115">Licenses and services</span></span>
- [<span data-ttu-id="fceae-116">Licenties en services weergeven</span><span class="sxs-lookup"><span data-stu-id="fceae-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="fceae-117">Gebruikers met licentie en gebruikers zonder licentie weergeven</span><span class="sxs-lookup"><span data-stu-id="fceae-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="fceae-118">Licenties toewijzen aan gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="fceae-118">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="fceae-119">Account licentie en servicedetails bekijken</span><span class="sxs-lookup"><span data-stu-id="fceae-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="fceae-120">Toegang tot services uitschakelen</span><span class="sxs-lookup"><span data-stu-id="fceae-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="fceae-121">Toegang tot Sway uitschakelen</span><span class="sxs-lookup"><span data-stu-id="fceae-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="fceae-122">Toegang tot services uitschakelen tijdens het toewijzen van gebruikerslicenties</span><span class="sxs-lookup"><span data-stu-id="fceae-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="fceae-123">Licenties verwijderen uit gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="fceae-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="fceae-124">Groepen</span><span class="sxs-lookup"><span data-stu-id="fceae-124">Groups</span></span>
- [<span data-ttu-id="fceae-125">Groepslidmaatschap onderhouden</span><span class="sxs-lookup"><span data-stu-id="fceae-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="fceae-126">Microsoft 365-groepen beheren</span><span class="sxs-lookup"><span data-stu-id="fceae-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)

