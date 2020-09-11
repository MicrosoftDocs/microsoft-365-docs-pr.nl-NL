---
title: Microsoft 365 beheren met Windows PowerShell voor DAP partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Hoe u met Windows PowerShell Microsoft 365-partners voor klanten van Syndicating en Cloud Solution Providers kunt beheren met Windows PowerShell.
ms.openlocfilehash: a7b2fbb5423e3b923e17aa2d9c488e7dd085be35
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429876"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="254d8-103">Microsoft 365 beheren met Windows PowerShell voor de partners voor gedelegeerde toegang</span><span class="sxs-lookup"><span data-stu-id="254d8-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="254d8-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="254d8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="254d8-105">De partners van de gedelegeerde toegang (machtigingen) zijn syndicaties en partners van een Cloud solution provider.</span><span class="sxs-lookup"><span data-stu-id="254d8-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="254d8-106">Veel zijn netwerk-of telecommunicatie providers.</span><span class="sxs-lookup"><span data-stu-id="254d8-106">Many are network or telecom providers.</span></span> <span data-ttu-id="254d8-107">Ze bundelt Microsoft 365-abonnementen in hun serviceaanbiedingen.</span><span class="sxs-lookup"><span data-stu-id="254d8-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="254d8-108">Wanneer ze een Microsoft 365-abonnement verkopen, krijgen ze automatisch beheermachtigingen toegewezen aan de tenancies van de klant, zodat ze deze kunnen beheren en rapporteren op deze tenancies.</span><span class="sxs-lookup"><span data-stu-id="254d8-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="254d8-109">Deze taken zijn moeilijk te doen in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="254d8-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="254d8-110">Het is veel gemakkelijker om PowerShell voor Microsoft 365 te gebruiken voor beheertaken zoals:</span><span class="sxs-lookup"><span data-stu-id="254d8-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="254d8-111">Alle klanten **TenantIds** en hun domein weergeven</span><span class="sxs-lookup"><span data-stu-id="254d8-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="254d8-112">Identificeer alle gebruikers in een klant pacht en de toegewezen licenties</span><span class="sxs-lookup"><span data-stu-id="254d8-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="254d8-113">Sommige beheertaken kunnen alleen worden uitgevoerd in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="254d8-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="254d8-114">In de volgende artikelen wordt uitgelegd hoe u met behulp van een PowerShell-partners van syndicaties en CSP'S de klant-tenancies kunt beheren:</span><span class="sxs-lookup"><span data-stu-id="254d8-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="254d8-115">Microsoft 365-tenants beheren met Windows PowerShell voor Microsoft gemachtigde toegangsmachtigingen (DAP)-partners</span><span class="sxs-lookup"><span data-stu-id="254d8-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="254d8-116">Een domein toevoegen aan een client, pacht met Windows PowerShell voor gedelegeerde toegangsrechten (DAP)-partners</span><span class="sxs-lookup"><span data-stu-id="254d8-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="254d8-117">Verbinding maken met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="254d8-117">Connect to Exchange Online PowerShell</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="254d8-118">Gegevens van de Tenant met informatie van klanten ophalen met Windows PowerShell voor partners met een gedelegeerde toegangsrechten (DAP)</span><span class="sxs-lookup"><span data-stu-id="254d8-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   