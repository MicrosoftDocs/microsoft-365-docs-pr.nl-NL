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
description: Beheerders kunnen meer informatie krijgen over het rapport Automatisch doorgestuurde berichten in het e-mailstroomdashboard in het beveiligings- & Compliancecentrum.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 75cf060d9a597bb991fc8af2c4c70f9ecc592ad7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929358"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Inzicht in automatisch doorgestuurde berichten in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Het **inzicht in** automatisch doorgestuurde berichten in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [Beveiligings- & Compliancecentrum](https://protection.office.com) bevat informatie over berichten die automatisch vanuit uw organisatie worden doorgestuurd naar geadresseerden in externe domeinen.

![Widget Automatisch doorgestuurde berichten in het beveiligings- & compliancecentrum](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Details van automatisch doorgestuurde berichten

Wanneer u op het aantal berichten in de widget klikt, wordt er een flyoutvenster weergegeven met meer informatie over de automatisch doorgestuurde berichten:

- **Automatisch doorgestuurde berichten doorsturen:**

  - **Op e-mailstroomregels**
  - **Op Regels voor Postvak IN**
  - **Doorsturen via SMTP:** Deze methode geeft automatisch doorsturen aan dat beheerders kunnen configureren in een postvak, zoals beschreven in E-mail doorsturen configureren [voor een postvak.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)
  - Een koppeling naar het [rapport Doorsturen](view-mail-flow-reports.md#forwarding-report) voor meer informatie.

- **Automatisch doorgestuurde berichten door domeinen en gebruikers:**

  - **Top 5 domeinen die zijn doorgestuurd naar**
  - **Nieuwe domeinen (vorige week)**
  - **Top 5 doorsturende gebruikers**
  - **Nieuwe gebruikers (vorige week)**
  - Een koppeling naar het [rapport Wijzigingen doorsturen](mfi-new-users-forwarding-email.md#forwarding-modifications-report) voor meer informatie.

![Details flyout for the Auto-forwarded messages report in the Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Inzichten

Er worden twee inzichten gegenereerd op basis van de rapportgegevens:

- [Nieuwe gebruikers die e-mail doorsturen](mfi-new-users-forwarding-email.md)
- [Nieuwe domeinen die e-mail worden doorgestuurd](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Zie ook

Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)