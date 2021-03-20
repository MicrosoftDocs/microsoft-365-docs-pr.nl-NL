---
title: Een QR-code gebruiken om u aan te melden bij de mobiele Outlook-apps
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Meer informatie over het gebruik van een QR-code om Outlook Mobile te verifiëren en te downloaden.
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914964"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Een QR-code gebruiken om u aan te melden bij de mobiele Outlook-apps

> [!IMPORTANT]
> Deze functie is alleen beschikbaar voor organisaties die Targeted Release hebben ingeschakeld in het Microsoft 365-beheercentrum. Zie De opties Standaard of Targeted release instellen voor meer informatie over hoe deze [werkt.](release-options-in-office-365.md) We breiden de komende weken uit naar meer organisaties via een openbare preview. Openbare preview biedt vroegtijdige toegang tot Microsoft 365-functies.

Als Microsoft 365-beheerder kunt u uw gebruikers inschakelen om zich aan te melden bij de Outlook voor Android- of iOS-app op hun mobiele apparaten zonder hun gebruikersnaam en wachtwoord in te voeren. Door een QR-code te scannen, kunnen gebruikers zich veilig verifiëren en zich aanmelden bij Outlook Mobile.

In de webversie van Outlook of andere bureaubladversies van Outlook-toepassingen kunnen gebruikers meldingen zien met de mededeling dat ze Outlook op hun mobiele apparaat kunnen gebruiken. Deze meldingen kunnen worden beheerd door de beheerder met Behulp van Exchange Powershell. Als gebruikers ervoor kiezen om zichzelf een sms-bericht te sturen om de app te downloaden op hun mobiele apparaat, wordt er een QR-code weergegeven op hun computer. Ze kunnen de QR-code scannen om zich aan te melden bij Outlook op hun telefoon of tablet. Deze QR-code is een teken van korte duur dat slechts één keer kan worden ingewisseld.

> [!NOTE]
> In sommige gevallen moeten uw gebruikers zich opnieuw verifiëren op hun computer om de QR-code te genereren.

## <a name="use-exchange-powershell"></a>Exchange PowerShell gebruiken

Deze functie is standaard ingeschakeld. Als u deze functie wilt uitschakelen, volgt u de onderstaande stappen.

1. [Verbinding maken met Exchange PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Met PowerShell kunt u de meldingen uitschakelen die uw gebruikers informeren over de mobiele Outlook-apps. Hierdoor wordt ook voorkomen dat de aanmeldingsstroom voor QR-code wordt weergegeven.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

Verwante onderwerpen

[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)