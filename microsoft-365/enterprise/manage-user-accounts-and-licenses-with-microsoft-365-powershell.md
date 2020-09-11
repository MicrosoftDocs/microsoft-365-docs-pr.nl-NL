---
title: Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell
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
description: Meer informatie over het beheren van gebruikersaccounts, licenties en groepen van Microsoft 365 met PowerShell.
ms.openlocfilehash: 0c6ca6a4165b616097405a9de178c254aa489a3c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429984"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="b50a2-103">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b50a2-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="b50a2-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b50a2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b50a2-105">Microsoft 365-beheerders moeten gebruikersaccounts, licenties en groepen beheren.</span><span class="sxs-lookup"><span data-stu-id="b50a2-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="b50a2-106">Hoewel u de meeste van deze taken kunt uitvoeren in het Microsoft 365-Beheercentrum, zijn sommige eenvoudiger in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b50a2-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="b50a2-107">Zie de volgende artikelen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b50a2-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="b50a2-108">Gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="b50a2-108">User accounts</span></span>

- [<span data-ttu-id="b50a2-109">Create user accounts</span><span class="sxs-lookup"><span data-stu-id="b50a2-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b50a2-110">Gebruikersaccounts weergeven</span><span class="sxs-lookup"><span data-stu-id="b50a2-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b50a2-111">Eigenschappen van gebruikersaccounts configureren</span><span class="sxs-lookup"><span data-stu-id="b50a2-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b50a2-112">Rollen toewijzen aan gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="b50a2-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b50a2-113">Gebruikersaccounts verwijderen en herstellen</span><span class="sxs-lookup"><span data-stu-id="b50a2-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b50a2-114">Gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="b50a2-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="b50a2-115">Licenties en services</span><span class="sxs-lookup"><span data-stu-id="b50a2-115">Licenses and services</span></span>
- [<span data-ttu-id="b50a2-116">Licenties en services weergeven</span><span class="sxs-lookup"><span data-stu-id="b50a2-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b50a2-117">Gelicentieerde en niet-gelicentieerde gebruikers weergeven</span><span class="sxs-lookup"><span data-stu-id="b50a2-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b50a2-118">Licenties aan gebruikersaccounts toewijzen</span><span class="sxs-lookup"><span data-stu-id="b50a2-118">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b50a2-119">Accountlicentie-en servicedetails weergeven</span><span class="sxs-lookup"><span data-stu-id="b50a2-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b50a2-120">Toegang tot services uitschakelen</span><span class="sxs-lookup"><span data-stu-id="b50a2-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="b50a2-121">Toegang tot Sway uitschakelen</span><span class="sxs-lookup"><span data-stu-id="b50a2-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="b50a2-122">Toegang tot services uitschakelen bij het toewijzen van gebruikerslicenties</span><span class="sxs-lookup"><span data-stu-id="b50a2-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="b50a2-123">Licenties van gebruikersaccounts intrekken</span><span class="sxs-lookup"><span data-stu-id="b50a2-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="b50a2-124">Groepen</span><span class="sxs-lookup"><span data-stu-id="b50a2-124">Groups</span></span>
- [<span data-ttu-id="b50a2-125">Groepslidmaatschap onderhouden</span><span class="sxs-lookup"><span data-stu-id="b50a2-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b50a2-126">Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="b50a2-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
