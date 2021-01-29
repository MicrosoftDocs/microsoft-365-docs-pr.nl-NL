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
description: Informatie over het gebruik van een QR-code voor verificatie en het downloaden van Outlook Mobile.
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050772"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Een QR-code gebruiken om u aan te melden bij de mobiele Outlook-apps

> [!IMPORTANT]
> Deze Microsoft 365-functie is beschikbaar in de openbare preview-versie. Openbare preview biedt vroegtijdige toegang tot Microsoft 365-functies.

Als Microsoft 365-beheerder kunt u uw gebruikers in staat stellen zich aan te melden bij de app Outlook voor Android of iOS op hun mobiele apparaten zonder dat ze hun gebruikersnaam en wachtwoord moeten invoeren. Door een QR-code te scannen kunnen gebruikers zich veilig verifiëren en zich aanmelden bij Outlook Mobile.

In de webversie van Outlook of andere Bureaublad-Outlook-toepassingen zien gebruikers mogelijk meldingen met de mededeling dat ze Outlook op hun mobiele apparaat kunnen gebruiken. Deze meldingen kunnen worden beheerd door de beheerder met behulp van Exchange Powershell. Als gebruikers zichzelf een sms-bericht sturen om de app te downloaden op hun mobiele apparaat, wordt er een QR-code weergegeven op hun computer. Ze kunnen de QR-code scannen om zich aan te melden bij Outlook op hun telefoon of tablet. Deze QR-code is een token van korte duur die maar één keer kan worden ingewisseld.

> [!NOTE]
> In sommige gevallen moeten uw gebruikers zich opnieuw verifiëren op hun computer om de QR-code te genereren.

## <a name="use-exchange-powershell"></a>Exchange PowerShell gebruiken

Deze ervaring is standaard ingeschakeld. Als u deze functie wilt uitschakelen, volgt u de onderstaande stappen.

1. [Maak verbinding met Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Met PowerShell kunt u de meldingen uitschakelen om uw gebruikers te informeren over de mobiele Outlook-apps. Hiermee wordt ook voorkomen dat de aanmeldingsstroom voor QR-code wordt weergegeven.

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

Verwante onderwerpen

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)