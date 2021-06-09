---
title: Hybride moderne verificatie verwijderen of uitschakelen uit Skype voor Bedrijven en Exchange
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
description: In dit artikel wordt uitgelegd hoe u hybride moderne verificatie verwijdert of uit Skype voor Bedrijven en Exchange.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927286"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="e7bb1-103">Hybride moderne verificatie verwijderen of uitschakelen uit Skype voor Bedrijven en Exchange</span><span class="sxs-lookup"><span data-stu-id="e7bb1-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="e7bb1-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e7bb1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e7bb1-105">Als u HMA (Hybrid Modern Authentication) alleen hebt ingeschakeld om te vinden dat deze niet geschikt is voor uw huidige omgeving, kunt u HMA uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="e7bb1-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="e7bb1-106">In dit artikel wordt uitgelegd hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="e7bb1-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="e7bb1-107">Wie is dit artikel voor?</span><span class="sxs-lookup"><span data-stu-id="e7bb1-107">Who is this article for?</span></span>

<span data-ttu-id="e7bb1-108">Als u Moderne verificatie hebt ingeschakeld in Skype voor Bedrijven Online of On-premises, en/of Exchange Online of On-premises en hebt gevonden dat u HMA moet uitschakelen, zijn deze stappen voor u.</span><span class="sxs-lookup"><span data-stu-id="e7bb1-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7bb1-109">Zie het[artikel 'Skype voor Bedrijven topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)supported with Modern Authentication' als u in Skype voor Bedrijven Online of On-premises bent, een mixed-topology HMA hebt en moet kijken naar ondersteunde excuses voordat u begint.</span><span class="sxs-lookup"><span data-stu-id="e7bb1-109">See the '[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="e7bb1-110">Hybride moderne verificatie uitschakelen (Exchange)</span><span class="sxs-lookup"><span data-stu-id="e7bb1-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="e7bb1-111">**Exchange On-premises:** Open de Exchange Management Shell en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="e7bb1-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="e7bb1-112">**Exchange Online:** Verbinding maken [om Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) externe PowerShell te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e7bb1-112">**Exchange Online**: [Connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="e7bb1-113">Voer de volgende opdracht uit om de  *vlag OAuth2ClientProfileEnabled*  om te zetten in 'onwaar':</span><span class="sxs-lookup"><span data-stu-id="e7bb1-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="e7bb1-114">Hybride moderne verificatie uitschakelen (Skype voor Bedrijven)</span><span class="sxs-lookup"><span data-stu-id="e7bb1-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="e7bb1-115">**Skype voor Bedrijven On-premises:** Voer de volgende opdrachten uit in Skype voor Bedrijven Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e7bb1-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="e7bb1-116">**Skype voor Bedrijven Online:** [Verbinding maken online Skype voor Bedrijven met](manage-skype-for-business-online-with-microsoft-365-powershell.md) Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7bb1-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="e7bb1-117">Voer de volgende opdracht uit om Moderne verificatie uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="e7bb1-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="e7bb1-118">[Terugkoppeling naar het overzicht moderne verificatie](hybrid-modern-auth-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="e7bb1-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
