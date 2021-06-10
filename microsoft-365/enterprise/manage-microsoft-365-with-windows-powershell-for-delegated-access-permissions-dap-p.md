---
title: Beheer Microsoft 365 met Windows PowerShell voor DAP-partners
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
description: Hoe Syndication en Cloud Solution Provider (CSP)-partners Windows PowerShell kunnen gebruiken om Microsoft 365 klantenten tenants te beheren.
ms.openlocfilehash: 352a9a01414b94a1593de6a734151b687524fe7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909524"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="ca37a-103">Het beheren van Microsoft 365 met Windows PowerShell voor partners met gedelegeerde toegangsmachtigingen</span><span class="sxs-lookup"><span data-stu-id="ca37a-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="ca37a-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ca37a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ca37a-105">DAP-partners (Gedelegeerde Access Permission) zijn Syndication- en Cloud Solution Providers (CSP)-partners.</span><span class="sxs-lookup"><span data-stu-id="ca37a-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="ca37a-106">Veel zijn netwerk- of telecomproviders.</span><span class="sxs-lookup"><span data-stu-id="ca37a-106">Many are network or telecom providers.</span></span> <span data-ttu-id="ca37a-107">Ze bundelen Microsoft 365 abonnementen in hun serviceaanbiedingen.</span><span class="sxs-lookup"><span data-stu-id="ca37a-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="ca37a-108">Wanneer ze een Microsoft 365-abonnement verkopen, worden ze automatisch machtigingen voor beheer namens (AOBO) verleend aan de tenancies van de klant, zodat ze deze tenancies kunnen beheren en rapporteren.</span><span class="sxs-lookup"><span data-stu-id="ca37a-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="ca37a-109">Deze taken zijn moeilijk te doen in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="ca37a-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ca37a-110">Het is veel gemakkelijker om PowerShell te gebruiken Microsoft 365 beheertaken uit te voeren, zoals:</span><span class="sxs-lookup"><span data-stu-id="ca37a-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="ca37a-111">Alle **tenant-ids** en hun domeinen van de klant op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="ca37a-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="ca37a-112">Alle gebruikers in een klantentenancy en hun toegewezen licenties identificeren</span><span class="sxs-lookup"><span data-stu-id="ca37a-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="ca37a-113">Sommige beheertaken kunnen alleen worden uitgevoerd in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca37a-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="ca37a-114">In de volgende artikelen ziet u hoe Syndication- en CSP-partners PowerShell gebruiken om hun klantentenancies te beheren:</span><span class="sxs-lookup"><span data-stu-id="ca37a-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="ca37a-115">Beheer Microsoft 365 tenants met Windows PowerShell voor DAP-partners (Gedelegeerde Toegangsmachtigingen)</span><span class="sxs-lookup"><span data-stu-id="ca37a-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="ca37a-116">Een domein toevoegen aan een client tenancy met Windows PowerShell voor DAP-partners (Gedelegeerde toegangsmachtiging)</span><span class="sxs-lookup"><span data-stu-id="ca37a-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="ca37a-117">Verbinding maken powershell Exchange Online gebruiken</span><span class="sxs-lookup"><span data-stu-id="ca37a-117">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [<span data-ttu-id="ca37a-118">Rapportagegegevens van klantten tenants ophalen met Windows PowerShell voor DAP-partners (Gedelegeerde toegangsmachtigingen)</span><span class="sxs-lookup"><span data-stu-id="ca37a-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
