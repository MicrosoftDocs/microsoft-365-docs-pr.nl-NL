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
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242352"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Een QR-code gebruiken om u aan te melden bij de mobiele Outlook-apps

> [!IMPORTANT]
> Deze functie is alleen beschikbaar voor organisaties die Targeted Release hebben ingeschakeld in het Microsoft 365-beheercentrum. Zie De Standard Release- of Targeted Release-opties instellen voor meer informatie over hoe dit [werkt.](release-options-in-office-365.md) De komende weken zullen we via een openbare preview naar meer organisaties worden uitgebreid. Openbare preview biedt vroegtijdige toegang tot Microsoft 365-functies.

Als Microsoft 365-beheerder kunt u uw gebruikers in staat stellen zich aan te melden bij de App Outlook voor Android of iOS op hun mobiele apparaten zonder dat ze hun gebruikersnaam en wachtwoord moeten invoeren. Door een QR-code te scannen kunnen gebruikers zich veilig verifiëren en zich aanmelden bij Outlook Mobile.

In de webversie van Outlook of andere Outlook-bureaubladtoepassingen zien gebruikers mogelijk meldingen met de mededeling dat ze Outlook op hun mobiele apparaat kunnen gebruiken. Deze meldingen kunnen worden beheerd door de beheerder met behulp van Exchange Powershell. Als gebruikers zichzelf een sms-bericht sturen om de app te downloaden op hun mobiele apparaat, wordt er een QR-code weergegeven op hun computer. Ze kunnen de QR-code scannen om zich aan te melden bij Outlook op hun telefoon of tablet. Deze QR-code is een token van korte duur die maar één keer kan worden ingewisseld.

> [!NOTE]
> In sommige gevallen moeten uw gebruikers zich opnieuw verifiëren op hun computer om de QR-code te genereren.

## <a name="use-exchange-powershell"></a>Exchange PowerShell gebruiken

Deze functie is standaard ingeschakeld. Als u deze functie wilt uitschakelen, volgt u de onderstaande stappen.

1. [Maak verbinding met Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Met PowerShell kunt u de meldingen uitschakelen om uw gebruikers te informeren over de mobiele Outlook-apps. Hiermee wordt ook voorkomen dat de aanmeldingsstroom voor QR-code wordt weergegeven.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

Verwante onderwerpen

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
