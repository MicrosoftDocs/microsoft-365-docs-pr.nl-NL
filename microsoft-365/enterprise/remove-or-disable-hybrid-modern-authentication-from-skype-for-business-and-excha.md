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
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547094"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Hybride, moderne verificatie van Skype voor bedrijven en Exchange verwijderen of uitschakelen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u de hybride versie van modern Authentication (HMA) alleen wilt vinden voor de huidige omgeving, kunt u HMA uitschakelen. In dit artikel wordt uitgelegd hoe u dit kunt doen.
  
## <a name="who-is-this-article-for"></a>Wie is dit artikel voor?

Als u moderne verificatie hebt ingeschakeld in Skype voor bedrijven online of on-premises, en/of Exchange Online of on-premises en u het HMA moet uitschakelen, zijn deze stappen bedoeld voor u.

> [!IMPORTANT]
> Zie het artikel '[Skype voor bedrijven-topologieën ondersteund met moderne verificatie](https://technet.microsoft.com/library/mt803262.aspx)' als u Skype voor bedrijven online of on-premises gebruikt, een gemengde HMA-topologie hebt en de ondersteunde topologieën moet bekijken voordat u begint.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Hybrid modern Authentication (Exchange) uitschakelen

1. **On-premises Exchange**: Open de Exchange-beheer shell en voer de volgende opdrachten uit: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [Maak verbinding met Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) via externe PowerShell. Voer de volgende opdracht uit om de  *OAuth2ClientProfileEnabled*  -vlag om te zetten in ' onwaar '.

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Hybride moderne verificatie uitschakelen (skype voor bedrijven)

1. **Skype voor bedrijven on-premises**: Voer de volgende opdrachten uit in de Skype voor bedrijven-beheer shell:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype voor bedrijven online**: [Maak verbinding met Skype voor bedrijven online](manage-skype-for-business-online-with-microsoft-365-powershell.md) met externe PowerShell. Voer de volgende opdracht uit om moderne verificatie uit te schakelen:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Koppeling terug naar het moderne verificatie overzicht](hybrid-modern-auth-overview.md) . 
  

