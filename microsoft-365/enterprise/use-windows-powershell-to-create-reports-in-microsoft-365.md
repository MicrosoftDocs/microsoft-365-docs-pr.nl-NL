---
title: PowerShell gebruiken om rapporten te maken voor Microsoft 365
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
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: 'Overzicht: PowerShell voor Microsoft 365 gebruiken om rapporten te maken die u niet kunt maken in het Microsoft 365-Beheercentrum.'
ms.openlocfilehash: 10000f62b1d6a747cf0373623c6038b080666e1a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753976"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="d2825-103">PowerShell gebruiken om rapporten te maken voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d2825-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="d2825-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d2825-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d2825-105">Er zijn veel verschillende rapporten beschikbaar in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d2825-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d2825-106">Maar deze rapporten leveren slechts zoveel informatie en soms hebt u meer nodig.</span><span class="sxs-lookup"><span data-stu-id="d2825-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="d2825-107">Dat is wanneer u PowerShell voor Microsoft 365 nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="d2825-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="d2825-108">In deze artikelen wordt uitgelegd hoe u PowerShell voor Microsoft 365 gebruikt voor informatie over uw Microsoft 365-Tenant:</span><span class="sxs-lookup"><span data-stu-id="d2825-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="d2825-109">Aan de slag met rapporten met behulp van PowerShell voor Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="d2825-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="d2825-110">Waarom u PowerShell voor Microsoft 365 moet gebruiken</span><span class="sxs-lookup"><span data-stu-id="d2825-110">Why you need to use PowerShell for Microsoft 365</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
    
- <span data-ttu-id="d2825-111">Rapporten voor gebruikersaccounts en licenties:</span><span class="sxs-lookup"><span data-stu-id="d2825-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="d2825-112">Licenties en services van Microsoft 365 weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2825-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="d2825-113">Gebruikers met een licentie van Microsoft 365 met PowerShell weergeven</span><span class="sxs-lookup"><span data-stu-id="d2825-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="d2825-114">Microsoft 365-account licentie en servicedetails weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2825-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="d2825-115">Microsoft 365-gebruikersaccounts weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2825-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="d2825-116">Rapporten voor SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="d2825-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="d2825-117">Aan de slag met SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="d2825-117">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="d2825-118">Get-SPOSiteGroup-haalt alle groepen op een opgegeven siteverzameling op</span><span class="sxs-lookup"><span data-stu-id="d2825-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="d2825-119">Rapporten voor Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="d2825-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="d2825-120">Exchange Online PowerShell gebruiken om postvak weer te geven</span><span class="sxs-lookup"><span data-stu-id="d2825-120">Use Exchange Online PowerShell to display mailbox</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="d2825-121">Gerelateerde artikelen</span><span class="sxs-lookup"><span data-stu-id="d2825-121">Related articlesl</span></span>

[<span data-ttu-id="d2825-122">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2825-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d2825-123">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d2825-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d2825-124">SharePoint beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2825-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d2825-125">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2825-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  