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
ms.openlocfilehash: 99aa86b1b58b15c63803e1b71d071cbde5c38492
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689274"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="26b69-103">PowerShell gebruiken om rapporten te maken voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26b69-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="26b69-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="26b69-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="26b69-105">Er zijn veel verschillende rapporten beschikbaar in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="26b69-105">There are many different reports available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="26b69-106">Deze rapporten hebben echter slechts zoveel informatie en soms hebt u meer nodig.</span><span class="sxs-lookup"><span data-stu-id="26b69-106">However, these reports only provide so much information and sometimes you need more.</span></span> <span data-ttu-id="26b69-107">Dat is wanneer u PowerShell voor Microsoft 365 nodig hebt</span><span class="sxs-lookup"><span data-stu-id="26b69-107">That's when you need PowerShell for Microsoft 365</span></span>
  
<span data-ttu-id="26b69-108">In deze artikelen wordt uitgelegd hoe u PowerShell voor Microsoft 365 kunt gebruiken om gegevens te verkrijgen van uw Microsoft 365-Tenant:</span><span class="sxs-lookup"><span data-stu-id="26b69-108">These articles that describe how to use PowerShell for Microsoft 365 to obtain information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="26b69-109">Aan de slag met rapporten met behulp van PowerShell voor Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="26b69-109">Getting started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="26b69-110">PowerShell voor Microsoft 365 kan aanvullende informatie onthullen die u niet kunt zien met het Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="26b69-110">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Admin center</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
  - [<span data-ttu-id="26b69-111">PowerShell voor Microsoft 365 is geweldig bij het filteren van gegevens</span><span class="sxs-lookup"><span data-stu-id="26b69-111">PowerShell for Microsoft 365 is great at filtering data</span></span>](https://technet.microsoft.com/library/dn568034.aspx#filter)
    
  - [<span data-ttu-id="26b69-112">Met PowerShell voor Microsoft 365 kunt u eenvoudig gegevens afdrukken of opslaan</span><span class="sxs-lookup"><span data-stu-id="26b69-112">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>](https://technet.microsoft.com/library/dn568034.aspx#printsave)
    
- <span data-ttu-id="26b69-113">Rapporten voor gebruikersaccounts en licenties:</span><span class="sxs-lookup"><span data-stu-id="26b69-113">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="26b69-114">Licenties en services van Microsoft 365 weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="26b69-114">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="26b69-115">Gebruikers met een licentie van Microsoft 365 met PowerShell weergeven</span><span class="sxs-lookup"><span data-stu-id="26b69-115">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="26b69-116">Microsoft 365-account licentie en servicedetails weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="26b69-116">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="26b69-117">Microsoft 365-gebruikersaccounts weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="26b69-117">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="26b69-118">Rapporten voor SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="26b69-118">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="26b69-119">Aan de slag met SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="26b69-119">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="26b69-120">SharePoint Online-sitegroepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="26b69-120">Manage SharePoint Online site groups with PowerShell</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="26b69-121">Rapporten voor Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="26b69-121">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="26b69-122">Postvakgegevens van Exchange Online weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="26b69-122">Display Exchange Online mailbox information with PowerShell</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
  - [<span data-ttu-id="26b69-123">Exchange Online-rapporten met PowerShell weergeven</span><span class="sxs-lookup"><span data-stu-id="26b69-123">Display Exchange Online reports with PowerShell</span></span>](https://technet.microsoft.com/library/4873a063-9fc4-4ed9-826a-6e935fef61d4.aspx)
    
## <a name="related-topics"></a><span data-ttu-id="26b69-124">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="26b69-124">Related topics</span></span>

[<span data-ttu-id="26b69-125">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="26b69-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="26b69-126">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26b69-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="26b69-127">SharePoint Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="26b69-127">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="26b69-128">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="26b69-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
