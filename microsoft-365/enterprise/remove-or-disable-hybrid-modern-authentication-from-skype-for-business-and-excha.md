---
title: Hybride, moderne verificatie van Skype voor bedrijven en Exchange verwijderen of uitschakelen
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: In dit artikel wordt uitgelegd hoe u hybride moderne verificatie uit Skype voor bedrijven en Exchange verwijdert of uitschakelt.
ms.openlocfilehash: da0887936f5def69ad80c8f04381bcb3a85c2349
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689020"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="5762e-103">Hybride, moderne verificatie van Skype voor bedrijven en Exchange verwijderen of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="5762e-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="5762e-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5762e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5762e-105">Als u de hybride versie van modern Authentication (HMA) alleen wilt vinden voor de huidige omgeving, kunt u HMA uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="5762e-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="5762e-106">In dit artikel wordt uitgelegd hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="5762e-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="5762e-107">Wie is dit artikel voor?</span><span class="sxs-lookup"><span data-stu-id="5762e-107">Who is this article for?</span></span>

<span data-ttu-id="5762e-108">Als u moderne verificatie hebt ingeschakeld in Skype voor bedrijven online of on-premises, en/of Exchange Online of on-premises en u het HMA moet uitschakelen, zijn deze stappen bedoeld voor u.</span><span class="sxs-lookup"><span data-stu-id="5762e-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5762e-109">Zie het artikel '[Skype voor bedrijven-topologieën ondersteund met moderne verificatie](https://technet.microsoft.com/library/mt803262.aspx)' als u Skype voor bedrijven online of on-premises gebruikt, een gemengde HMA-topologie hebt en de ondersteunde topologieën moet bekijken voordat u begint.</span><span class="sxs-lookup"><span data-stu-id="5762e-109">See the '[Skype for Business topologies supported with Modern Authentication](https://technet.microsoft.com/library/mt803262.aspx)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="5762e-110">Hybrid modern Authentication (Exchange) uitschakelen</span><span class="sxs-lookup"><span data-stu-id="5762e-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="5762e-111">**On-premises Exchange**: Open de Exchange-beheer shell en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="5762e-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="5762e-112">**Exchange Online**: [Maak verbinding met Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) via externe PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5762e-112">**Exchange Online**: [Connect to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="5762e-113">Voer de volgende opdracht uit om de  *OAuth2ClientProfileEnabled*  -vlag om te zetten in ' onwaar '.</span><span class="sxs-lookup"><span data-stu-id="5762e-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="5762e-114">Hybride moderne verificatie uitschakelen (skype voor bedrijven)</span><span class="sxs-lookup"><span data-stu-id="5762e-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="5762e-115">**Skype voor bedrijven on-premises**: Voer de volgende opdrachten uit in de Skype voor bedrijven-beheer shell:</span><span class="sxs-lookup"><span data-stu-id="5762e-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="5762e-116">**Skype voor bedrijven online**: [Maak verbinding met Skype voor bedrijven online](manage-skype-for-business-online-with-microsoft-365-powershell.md) met externe PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5762e-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="5762e-117">Voer de volgende opdracht uit om moderne verificatie uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="5762e-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="5762e-118">[Koppeling terug naar het moderne verificatie overzicht](hybrid-modern-auth-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="5762e-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
  

