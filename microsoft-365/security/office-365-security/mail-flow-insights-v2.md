---
title: Inzichten in e-mailstroom in het dashboard E-mailstroom
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Beheerders kunnen meer informatie krijgen over de inzichten en rapporten die beschikbaar zijn in het dashboard voor de e-mailstroom in het & compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b65e235e3446fa62bca1c9f8aef73f2387b1140b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167093"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>E-mailstroominzichten in het Beveiligings- en compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Beheerders kunnen het dashboard E-mailstroom in het beveiligings- & compliancecentrum gebruiken om trends en inzichten te ontdekken en acties uit te voeren om problemen met de e-mailstroom in hun organisatie op te lossen.

![Het dashboard E-mailstroom in het & compliancecentrum](../../media/mail-flow-dashboard-v2.png)

De beschikbare inzichten zijn:

- [Inzicht in automatisch doorgestuurde berichten](mfi-auto-forwarded-messages-report.md)

- [Oplossing voor mogelijk inzicht in e-maillus](mfi-mail-loop-insight.md)<sup>1</sup>

- [Slow Mail Flow Rules Insight](mfi-slow-mail-flow-rules-insight.md)<sup>1 oplossen</sup>

- [E-mailstroomkaart](mfi-mail-flow-map-report.md)

- [Nieuwe domeinen die e-mailinzichten worden doorgestuurd](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Nieuwe gebruikers die e-mailinzichten doorsturen](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Rapport over niet-geaccepteerd domein](mfi-non-accepted-domain-report.md)

- [Rapport over niet-uitgevoerde bezorging](mfi-non-delivery-report.md)

- [Inzicht in uitgaande en binnenkomende e-mailstroom](mfi-outbound-and-inbound-mail-flow.md)

- [Inzicht in wachtrijen](mfi-queue-alerts-and-queues.md)

- [Inzicht in en rapport over SMTP-verificatieclients](mfi-smtp-auth-clients-report.md)

- [Inzicht in e-mailstroomstatus van hoofddomein](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Dit inzicht wordt  pas weergegeven in het gebied Aanbevolen voor u in het dashboard E-mailstroom nadat het probleem is gedetecteerd. Anders wordt het niet gezien.

<sup>2</sup> Dit inzicht wordt niet weergegeven op het dashboard [](view-mail-flow-reports.md#forwarding-report) van de e-mailstroom, maar is zichtbaar op de pagina Doorsturen nadat het probleem is gedetecteerd. Anders wordt het niet gezien.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Machtigingen vereist voor het weergeven van het dashboard E-mailstroom

Het dashboard E-mailstroom is beschikbaar voor leden van de volgende rollengroepen:

- **Organisatiebeheer** in het & compliancecentrum (globale beheerders).

- **[Exchange-beheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure Active Directory.

- **MailFlow-beheerder** in het & compliancecentrum. Als het account niet ook lid is van de rollengroepen Organisatiebeheer of Exchange-beheerder, moet u rekening houden met de volgende problemen:
  - De gebruiker moet zich rechtstreeks aanmelden bij het & <https://protection.office.com> compliancecentrum.
  - De gebruiker heeft alleen-lezenmachtigingen voor het dashboard E-mailstroom.
  - De gebruiker heeft geen toegang tot het Microsoft 365-beheercentrum.

Zie Machtigingen in het [&](permissions-in-the-security-and-compliance-center.md) beveiligings- en compliancecentrum en geef gebruikers toegang tot het & compliancecentrum voor meer informatie over [machtigingen.](grant-access-to-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>Waar u het dashboard voor de e-mailstroom kunt vinden

Open het beveiligingscentrum & <https://protection.office.com> compliancecentrum, vouw **de e-mailstroom uit** en selecteer **Dashboard.**

Als u rechtstreeks naar het dashboard van de e-mailstroom wilt gaan, opent u <https://protection.office.com/mailflow/dashboard> .
