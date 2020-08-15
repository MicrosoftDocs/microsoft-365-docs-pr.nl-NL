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
description: 'Overzicht: RSS-en Cloud Solution Provider-partners kunnen Windows PowerShell gebruiken voor het beheren van tenants van Microsoft 365 Customer.'
ms.openlocfilehash: d4109c09a14fb5644d34daf24383053536440871
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689410"
---
# <a name="manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="66edd-103">Microsoft 365 met Windows PowerShell beheren voor partners met een gedelegeerde toegangsrechten (DAP)</span><span class="sxs-lookup"><span data-stu-id="66edd-103">Manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="66edd-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="66edd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="66edd-105">De partners van de gedelegeerde toegang (machtigingen) zijn syndicaties en partners van een Cloud solution provider.</span><span class="sxs-lookup"><span data-stu-id="66edd-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="66edd-106">Vaak zijn ze netwerk-of telecommunicatie providers van andere bedrijven.</span><span class="sxs-lookup"><span data-stu-id="66edd-106">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="66edd-107">Ze bundelt Microsoft 365-abonnementen in hun serviceaanbiedingen voor hun klanten.</span><span class="sxs-lookup"><span data-stu-id="66edd-107">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="66edd-108">Wanneer iemand een Microsoft 365-abonnement verkoopt, worden er automatisch beheermachtigingen verleend namens (AOBO) aan de klant tenancies zodat ze de klant tenancies kunnen beheren en rapporteren.</span><span class="sxs-lookup"><span data-stu-id="66edd-108">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span> <span data-ttu-id="66edd-109">U kunt dit moeilijkst en tijdrovend maken in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="66edd-109">At best, this is difficult and time consuming to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="66edd-110">Het is veel eenvoudiger om beheertaken uit te voeren, zoals het weergeven van alle klanten **TenantIds** en hun domein, of het identificeren van alle gebruikers in een klant pacht en welke licenties ze met behulp van PowerShell voor microsoft 365 zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="66edd-110">It is much easier to do administrative tasks like listing all the customer **TenantIds** and their domains or identifying all users in a customer tenancy and what licenses they are assigned by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="66edd-111">In sommige gevallen is het mogelijk deze beheertaken alleen uit te voeren in PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="66edd-111">In some cases, it is possible to do these administrative tasks only in PowerShell for Microsoft 365.</span></span> <span data-ttu-id="66edd-112">Hier volgen een aantal voorbeelden van scenario's die van toepassing zijn op het tenancies van een scenario met syndicaties en cryptografie partners:</span><span class="sxs-lookup"><span data-stu-id="66edd-112">Here are samples of scenarios that Syndication and CSP partners most frequently use to administer their customer tenancies:</span></span>
  
## 

- [<span data-ttu-id="66edd-113">Microsoft 365-tenants beheren met Windows PowerShell voor Microsoft gemachtigde toegangsmachtigingen (DAP)-partners</span><span class="sxs-lookup"><span data-stu-id="66edd-113">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="66edd-114">Een domein toevoegen aan een client, pacht met Windows PowerShell voor gedelegeerde toegangsrechten (DAP)-partners</span><span class="sxs-lookup"><span data-stu-id="66edd-114">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="66edd-115">Verbinding maken met Exchange Online-tenants met Remote Windows PowerShell voor gedelegeerde toegangsmachtigingen (DAP)</span><span class="sxs-lookup"><span data-stu-id="66edd-115">Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="66edd-116">Gegevens van de Tenant met informatie van klanten ophalen met Windows PowerShell voor partners met een gedelegeerde toegangsrechten (DAP)</span><span class="sxs-lookup"><span data-stu-id="66edd-116">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
    

    

