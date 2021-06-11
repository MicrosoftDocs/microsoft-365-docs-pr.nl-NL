---
title: Limieten in hoofd-eDiscovery-zaak
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In dit artikel worden de limieten beschreven in het hoofd-eDiscovery-geval in Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311422"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="7a068-103">Limieten in Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7a068-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="7a068-104">In de volgende tabel worden de limieten voor kern-eDiscovery-zaken en -gegevens vermeld die zijn gekoppeld aan een kern-eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="7a068-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="7a068-105">Zie Overzicht van Core eDiscovery voor meer informatie over Core [eDiscovery.](./get-started-core-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="7a068-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="7a068-106">Beschrijving van limiet</span><span class="sxs-lookup"><span data-stu-id="7a068-106">Description of limit</span></span> | <span data-ttu-id="7a068-107">Limiet</span><span class="sxs-lookup"><span data-stu-id="7a068-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="7a068-108">Maximum aantal zaken voor een organisatie.</span><span class="sxs-lookup"><span data-stu-id="7a068-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="7a068-109">Geen limiet</span><span class="sxs-lookup"><span data-stu-id="7a068-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="7a068-110">Maximum aantal case-holds voor een organisatie.</span><span class="sxs-lookup"><span data-stu-id="7a068-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="7a068-111">10.000</span><span class="sxs-lookup"><span data-stu-id="7a068-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="7a068-112">Maximum aantal postvakken in één case hold.</span><span class="sxs-lookup"><span data-stu-id="7a068-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="7a068-113">Deze limiet omvat het gecombineerde totaal van gebruikerspostvakken en de postvakken die zijn gekoppeld aan Microsoft 365 Groepen, Microsoft Teams en Yammer Groepen.</span><span class="sxs-lookup"><span data-stu-id="7a068-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="7a068-114">1,000</span><span class="sxs-lookup"><span data-stu-id="7a068-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="7a068-115">Maximum aantal sites in één geval.</span><span class="sxs-lookup"><span data-stu-id="7a068-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="7a068-116">Deze limiet omvat het gecombineerde totaal OneDrive voor Bedrijven sites, SharePoint sites en de sites die zijn gekoppeld aan Microsoft 365 Groepen, Microsoft Teams en Yammer Groepen.</span><span class="sxs-lookup"><span data-stu-id="7a068-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="7a068-117">100</span><span class="sxs-lookup"><span data-stu-id="7a068-117">100</span></span>  <br/> |
  |<span data-ttu-id="7a068-118">Het maximum aantal zaken dat wordt weergegeven op de basis-startpagina van eDiscovery en het maximum aantal items dat wordt weergegeven op de tabbladen Houdt, Zoekopdrachten en Exporteren in een zaak.</span><span class="sxs-lookup"><span data-stu-id="7a068-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="7a068-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a068-119"><sup>1</sup></span></span> |<span data-ttu-id="7a068-120">1,000</span><span class="sxs-lookup"><span data-stu-id="7a068-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="7a068-121"><sup>1</sup> Als u een lijst wilt weergeven met meer dan 1.000 gevallen, opgeslagen, gezocht of exporteert, kunt u de bijbehorende Office 365 Security & Compliance PowerShell-cmdlets gebruiken:</span><span class="sxs-lookup"><span data-stu-id="7a068-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="7a068-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="7a068-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="7a068-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="7a068-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="7a068-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="7a068-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="7a068-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="7a068-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="7a068-126">Zie Limieten voor zoeken naar inhoud en Core eDiscovery voor meer informatie over limieten voor zoekopdrachten en exporten die zijn gekoppeld aan een core [eDiscovery-zaak.](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="7a068-126">For more information about limits related to searches and exports associated with a Core eDiscovery case, see [Limits for Content search and Core eDiscovery](limits-for-content-search.md).</span></span>