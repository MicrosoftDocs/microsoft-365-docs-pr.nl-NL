---
title: Automatisch doorsturen van e-mail stoppen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het stoppen van e-mailberichten voor automatisch doorsturen.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701734"
---
# <a name="stop-email-auto-forward"></a>Automatisch doorsturen van e-mail stoppen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Als een hacker toegang krijgt tot het postvak van een gebruiker, kunnen ze de e-mail van de gebruiker automatisch doorsturen naar een extern adres en de informatie over het eigendom stelen. U kunt dit beëindigen door een e-mail stroom regel te maken.

## <a name="try-it"></a>Probeer het zelf!

1. Selecteer in het Microsoft 365-Beheercentrum de optie **Exchange**, **e-mail stroom** en klik op het tabblad **regels** op het plusteken en kies **een nieuwe regel maken**.
1. Selecteer **meer opties**. Geef een naam op voor de nieuwe regel.
1. Open vervolgens de vervolgkeuzelijst voor het **toepassen van deze regel**, en selecteer vervolgens **extern intern**.
1. Selecteer **binnen de organisatie** en klik vervolgens op **OK**.
1. Kies **voorwaarde toevoegen**, open de vervolgkeuzelijst, selecteer **de berichteigenschappen** en **Voeg vervolgens het berichttype toe**.
1. Open de vervolgkeuzelijst **berichttype selecteren** , kies **automatisch doorsturen** en klik vervolgens op **OK**.
1. Open de vervolgkeuzelijst **Ga als volgt** te werk, selecteer **het bericht blokkeren**, vervolgens **het bericht afwijzen en een uitleg toevoegen**.
1. Voer de berichttekst voor de uitleg in en selecteer **OK**.
1. Schuif naar de onderkant en selecteer **Opslaan**.

    Uw regel is gemaakt en hackers kunnen geen berichten meer automatisch doorsturen.