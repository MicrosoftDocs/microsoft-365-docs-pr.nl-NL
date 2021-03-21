---
title: Inzichten in e-mailstroom in het e-mailstroomdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Beheerders kunnen meer informatie krijgen over de inzichten en rapporten die beschikbaar zijn in het e-mailstroomdashboard in het Beveiligings- & Compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce252535d472cc4941a1353aa2be94759daebf4a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926854"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>E-mailstroominzichten in het Beveiligings- en compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Beheerders kunnen het e-mailstroomdashboard in het beveiligings- & compliancecentrum gebruiken om trends, inzichten te ontdekken en acties uit te voeren om problemen met de e-mailstroom in hun organisatie op te lossen.

![Het e-mailstroomdashboard in het beveiligings- & compliancecentrum](../../media/mail-flow-dashboard-v2.png)

De beschikbare inzichten zijn:

- [Inzicht in automatisch doorgestuurde berichten](mfi-auto-forwarded-messages-report.md)

- [Mogelijke e-maillusinzicht](mfi-mail-loop-insight.md)<sup>oplossen 1</sup>

- [Inzicht in regels voor trage e-mailstroom oplossen](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [E-mailstroomkaart](mfi-mail-flow-map-report.md)

- [Nieuwe domeinen die e-mailinzicht worden doorgestuurd](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Nieuwe gebruikers die e-mailinzicht doorsturen](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Rapport over niet-geaccepteerd domein](mfi-non-accepted-domain-report.md)

- [Rapport over niet-uitgevoerde bezorging](mfi-non-delivery-report.md)

- [Inzicht in uitgaande en binnenkomende e-mailstroom](mfi-outbound-and-inbound-mail-flow.md)

- [Inzicht in wachtrijen](mfi-queue-alerts-and-queues.md)

- [Inzicht in en rapport over SMTP-verificatieclients](mfi-smtp-auth-clients-report.md)

- [Inzicht in e-mailstroomstatus van hoofddomein](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Dit inzicht wordt alleen weergegeven in het gebied Aanbevolen voor **u** van het e-mailstroomdashboard nadat het probleem is gedetecteerd. Anders ziet u het niet.

<sup>2</sup> Dit inzicht wordt niet weergegeven in het e-mailstroomdashboard, maar is zichtbaar op de pagina [Doorsturen](view-mail-flow-reports.md#forwarding-report) nadat het probleem is gedetecteerd. Anders ziet u het niet.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Machtigingen vereist voor het weergeven van het e-mailstroomdashboard

Het e-mailstroomdashboard is beschikbaar voor leden van de volgende rollengroepen:

- **Organisatiebeheer** in het Beveiligings- & Compliancecentrum (globale beheerders).

- **[Exchange-beheerder](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure Active Directory.

- **MailFlow-beheerder** in het beveiligings- & compliancecentrum. Als het account niet ook lid is van de rollengroepen Organisatiebeheer of Exchange-beheerder, moet u rekening houden met de volgende problemen:
  - De gebruiker moet zich rechtstreeks aanmelden bij het Beveiligings- & compliancecentrum bij <https://protection.office.com> .
  - De gebruiker heeft alleen de machtiging Alleen-lezen voor het e-mailstroomdashboard.
  - De gebruiker heeft geen toegang tot het Microsoft 365-beheercentrum.

Zie Machtigingen in het Beveiligings- & [Compliancecentrum](permissions-in-the-security-and-compliance-center.md) en Gebruikers toegang geven tot het beveiligings- & compliancecentrum voor meer [informatie over machtigingen.](grant-access-to-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>Waar vindt u het e-mailstroomdashboard

Open het beveiligingscentrum & , <https://protection.office.com> vouw **E-mailstroom** uit en selecteer **Dashboard.**

Als u rechtstreeks naar het e-mailstroomdashboard wilt gaan, opent u <https://protection.office.com/mailflow/dashboard> .