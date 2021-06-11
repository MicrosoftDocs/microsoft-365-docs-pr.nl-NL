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
description: 'Overzicht: Gebruik PowerShell voor Microsoft 365 om rapporten te maken die u niet kunt maken in het Microsoft 365 beheercentrum.'
ms.openlocfilehash: 9e3b90dcdd32f80125175ad2e15a852db51e17f8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572739"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="07748-103">PowerShell gebruiken om rapporten te maken voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="07748-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="07748-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="07748-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="07748-105">Er zijn veel verschillende rapporten beschikbaar in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="07748-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="07748-106">Maar deze rapporten bevatten maar zo veel informatie en soms hebt u meer nodig.</span><span class="sxs-lookup"><span data-stu-id="07748-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="07748-107">Op dat moment hebt u PowerShell nodig voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07748-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="07748-108">In deze artikelen wordt beschreven hoe u PowerShell gebruikt voor Microsoft 365 informatie van uw Microsoft 365 tenant:</span><span class="sxs-lookup"><span data-stu-id="07748-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="07748-109">Aan de slag met rapportage met PowerShell voor Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="07748-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="07748-110">Waarom u PowerShell moet gebruiken voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="07748-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="07748-111">Rapporten voor gebruikersaccounts en -licenties:</span><span class="sxs-lookup"><span data-stu-id="07748-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="07748-112">Bekijk Microsoft 365 licenties en services met PowerShell</span><span class="sxs-lookup"><span data-stu-id="07748-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="07748-113">Bekijk Microsoft 365 gebruikers met een licentie en zonder licentie met PowerShell</span><span class="sxs-lookup"><span data-stu-id="07748-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="07748-114">De Microsoft 365 en servicegegevens van uw account weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="07748-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="07748-115">Gebruikersaccounts Microsoft 365 weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="07748-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="07748-116">Rapporten voor SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="07748-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="07748-117">Aan de slag met SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="07748-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="07748-118">Get-SPOSiteGroup : hiermee worden alle groepen op een opgegeven siteverzameling geplaatst</span><span class="sxs-lookup"><span data-stu-id="07748-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="07748-119">Rapporten voor Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="07748-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="07748-120">PowerShell Exchange Online gebruiken om postvak weer te geven</span><span class="sxs-lookup"><span data-stu-id="07748-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articles"></a><span data-ttu-id="07748-121">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="07748-121">Related articles</span></span>

[<span data-ttu-id="07748-122">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="07748-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="07748-123">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="07748-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="07748-124">Uw SharePoint beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="07748-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="07748-125">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="07748-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
