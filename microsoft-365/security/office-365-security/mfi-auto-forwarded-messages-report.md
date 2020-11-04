---
title: Inzicht in automatisch doorgestuurde berichten
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Beheerders kunnen informatie vinden over het rapport met automatisch doorgestuurde berichten in het dashboard voor de e-mail stroom van het beveiligings & nalevings centrum.
ms.openlocfilehash: 01a094b8531672708fc024e8ed0c5833786dbb0c
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877787"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Berichten met automatisch doorgestuurde inzichten in het beveiligings & nalevings centrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Met de **automatisch doorgestuurde berichten** in het [Dashboard voor e-mail stromen](mail-flow-insights-v2.md) in de [beveiligings & nalevings centrum](https://protection.office.com) wordt informatie weergegeven over berichten die automatisch van uw organisatie worden doorgestuurd naar geadresseerden in externe domeinen.

![Widget berichten automatisch doorsturen in het Beveiligingscentrum beveiligings &](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Details van automatisch doorgestuurde berichten

Wanneer u op het aantal berichten in het object klikt, wordt er een flyout weergegeven met meer informatie over de automatisch doorgestuurde berichten:

- **Berichten automatisch doorsturen met behulp van doorstuur methoden** :

  - **Door een e-mail stroom regel**
  - **Door regels voor Postvak in**
  - **Door het doorsturen van SMTP** : dit is automatisch doorsturen die beheerders kunnen configureren in een postvak zoals beschreven in het [doorsturen van e-mail voor een postvak configureren](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - Een koppeling naar het [doorstuur rapport](view-mail-flow-reports.md#forwarding-report) voor meer informatie.

- **Berichten automatisch doorsturen en door domeinen en gebruikers** :

  - **Vijf belangrijkste domeinen doorgestuurd naar**
  - **Nieuwe domeinen (vorige week)**
  - **Belangrijkste 5 doorstuur gebruikers**
  - **Nieuwe gebruikers (vorige week)**
  - Een koppeling naar de [lijst met wijzigingen doorsturen](mfi-new-users-forwarding-email.md#forwarding-modifications-report) voor meer informatie.

![Flyout Details van het rapport met automatisch doorgestuurde berichten in het Beveiligingscentrum beveiligings &](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Inzichten

Er worden twee inzichten gegenereerd op basis van de rapportgegevens:

- [Nieuwe gebruikers die e-mail doorsturen](mfi-new-users-forwarding-email.md)
- [Nieuwe domeinen die e-mail worden doorgestuurd](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Zie ook

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
