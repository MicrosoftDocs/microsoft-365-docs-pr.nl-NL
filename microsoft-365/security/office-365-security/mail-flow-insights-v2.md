---
title: E-mail stroom inzichten in het dashboard voor e-mail stroom
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Beheerders kunnen inzicht krijgen in de inzichten en rapporten die beschikbaar zijn in het dashboard voor de e-mail stroom van de beveiligings & compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 089c6351485712d841691d5b856b1ba28dfe4fc4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198479"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>E-mailstroominzichten in het Beveiligings- en compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Beheerders kunnen het dashboard voor e-mail stroom gebruiken in het beveiligings & compliance om trends, inzichten en acties uit te voeren om problemen met de e-mail stroom binnen hun organisatie op te lossen.

![Het dashboard voor e-mail stroom in de beveiligings & compliance](../../media/mail-flow-dashboard-v2.png)

De beschikbare inzichten zijn:

- [Inzicht in automatisch doorgestuurde berichten](mfi-auto-forwarded-messages-report.md)

- [Mogelijke oplossing voor e-mail herhalen](mfi-mail-loop-insight.md)<sup>1</sup>

- [Regels voor trage e-mail stromen herstellen](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [E-mailstroomkaart](mfi-mail-flow-map-report.md)

- [Nieuwe domeinen die worden doorgestuurd e-mail Insight](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Nieuwe gebruikers doorsturen e-mail Insight](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Rapport over niet-geaccepteerd domein](mfi-non-accepted-domain-report.md)

- [Rapport over niet-uitgevoerde bezorging](mfi-non-delivery-report.md)

- [Inzicht in uitgaande en binnenkomende e-mailstroom](mfi-outbound-and-inbound-mail-flow.md)

- [Inzicht in wachtrijen](mfi-queue-alerts-and-queues.md)

- [Inzicht in en rapport over SMTP-verificatieclients](mfi-smtp-auth-clients-report.md)

- [Inzicht in e-mailstroomstatus van hoofddomein](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> dit inzicht wordt alleen weergegeven in het **Aanbevolen** gebied van het e-mail stroom dashboard wanneer het probleem is gedetecteerd. Anders ziet u het niet.

<sup>2</sup> dit inzicht wordt niet weergegeven op het dashboard voor de e-mail stroom, maar is zichtbaar op de pagina voor het [doorsturen van rapporten](view-mail-flow-reports.md#forwarding-report) nadat het probleem is gedetecteerd. Anders ziet u het niet.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Vereiste machtigingen voor het weergeven van het dashboard voor e-mail stroom

Het dashboard voor e-mail stroom is beschikbaar voor leden van de volgende Routegroepen:

- **Organisatiebeheer** in het beveiligings & nalevings centrum (globale beheerders).

- **[Exchange-beheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in azure AD.

- E-mail **stroom beheerder** in de beveiligings & nalevings centrum: als een lid van deze rollen groep geen lid is van de globale beheerder of de rollen groepen van Exchange-beheerders, moet u de volgende problemen en vereisten noteren:

  - De gebruiker moet zich rechtstreeks aanmelden bij de beveiligings & nalevings centrum <https://protection.office.com> .
  - De gebruiker heeft slechts de alleen-lezen machtiging voor het dashboard voor e-mail stroom.
  - De gebruiker heeft geen toegang tot het Microsoft 365-Beheercentrum.

Zie [machtigingen in het beveiligings & nalevings](permissions-in-the-security-and-compliance-center.md) centrum en [gebruikers toegang geven tot de beveiligings & nalevings centrum](grant-access-to-the-security-and-compliance-center.md)voor meer informatie over machtigingen in het nalevings centrum voor beveiligings &.

## <a name="where-to-find-the-mail-flow-dashboard"></a>Waar vind ik het e-mail stroom dashboard?

Open het beveiligings & nalevings centrum <https://protection.office.com> , vouw **e-mail stroom**uit en selecteer vervolgens **Dashboard**.

Als u rechtstreeks naar het e-mail flow dashboard wilt gaan, opent u het <https://protection.office.com/mailflow/dashboard> .
