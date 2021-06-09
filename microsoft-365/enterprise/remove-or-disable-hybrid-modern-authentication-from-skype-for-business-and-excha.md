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
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Hybride moderne verificatie verwijderen of uitschakelen uit Skype voor Bedrijven en Exchange

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u HMA (Hybrid Modern Authentication) alleen hebt ingeschakeld om te vinden dat deze niet geschikt is voor uw huidige omgeving, kunt u HMA uitschakelen. In dit artikel wordt uitgelegd hoe u dit kunt doen.
  
## <a name="who-is-this-article-for"></a>Wie is dit artikel voor?

Als u Moderne verificatie hebt ingeschakeld in Skype voor Bedrijven Online of On-premises, en/of Exchange Online of On-premises en hebt gevonden dat u HMA moet uitschakelen, zijn deze stappen voor u.

> [!IMPORTANT]
> Zie het[artikel 'Skype voor Bedrijven topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)supported with Modern Authentication' als u in Skype voor Bedrijven Online of On-premises bent, een mixed-topology HMA hebt en moet kijken naar ondersteunde excuses voordat u begint.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Hybride moderne verificatie uitschakelen (Exchange)

1. **Exchange On-premises:** Open de Exchange Management Shell en voer de volgende opdrachten uit: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online:** Verbinding maken [om Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) externe PowerShell te gebruiken. Voer de volgende opdracht uit om de  *vlag OAuth2ClientProfileEnabled*  om te zetten in 'onwaar':

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Hybride moderne verificatie uitschakelen (Skype voor Bedrijven)

1. **Skype voor Bedrijven On-premises:** Voer de volgende opdrachten uit in Skype voor Bedrijven Management Shell:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype voor Bedrijven Online:** [Verbinding maken online Skype voor Bedrijven met](manage-skype-for-business-online-with-microsoft-365-powershell.md) Remote PowerShell. Voer de volgende opdracht uit om Moderne verificatie uit te schakelen:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Terugkoppeling naar het overzicht moderne verificatie](hybrid-modern-auth-overview.md) . 
