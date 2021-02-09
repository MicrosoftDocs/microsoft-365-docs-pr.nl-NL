---
title: Inzicht in automatisch doorgestuurde berichten
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Beheerders vinden meer informatie over het rapport met automatisch doorgestuurde berichten in het dashboard voor de e-mailstroom in het & compliancecentrum.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c95c403e0b342bf0466c45804ba3975c492b8e1b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150594"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Inzichten in automatisch doorgestuurde berichten in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Het inzicht **in automatisch** doorgestuurde berichten in het dashboard [E-mailstroom](mail-flow-insights-v2.md) in het [beveiligings- & Compliancecentrum](https://protection.office.com) geeft informatie weer over berichten die automatisch vanuit uw organisatie worden doorgestuurd naar geadresseerden in externe domeinen.

![Widget voor automatisch doorgestuurde berichten in het & compliancecentrum](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Details van automatisch doorgestuurde berichten

Wanneer u op het aantal berichten in de widget klikt, wordt een flyoutvenster weergegeven met meer informatie over de automatisch doorgestuurde berichten:

- **Automatisch doorgestuurde berichten met methoden voor doorsturen:**

  - **Regels voor de e-mailstroom**
  - **Op regels voor Postvak IN**
  - **Doorsturen via SMTP:** met deze methode wordt automatisch doorsturen aangegeven die beheerders voor een postvak kunnen configureren, zoals is beschreven in Doorsturen van e-mail configureren [voor een postvak.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)
  - Een koppeling naar het [doorsturende rapport](view-mail-flow-reports.md#forwarding-report) voor meer informatie.

- **Automatisch doorgestuurde berichten van domeinen en gebruikers:**

  - **De vijf belangrijkste domeinen die zijn doorgestuurd naar**
  - **Nieuwe domeinen (vorige week)**
  - **De vijf belangrijkste doorsturende gebruikers**
  - **Nieuwe gebruikers (vorige week)**
  - Een koppeling naar het [rapport met doorgestuurde wijzigingen](mfi-new-users-forwarding-email.md#forwarding-modifications-report) voor meer informatie.

![Flyout details voor het rapport Automatisch doorgestuurde berichten in het beveiligings- & compliancecentrum](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Inzichten

Er worden twee inzichten gegenereerd op basis van de rapportgegevens:

- [Nieuwe gebruikers die e-mail doorsturen](mfi-new-users-forwarding-email.md)
- [Nieuwe domeinen die e-mail worden doorgestuurd](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Zie ook

Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)
