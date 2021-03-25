---
title: Rapportage en berichttracering
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u informatie over rapporten en hulpprogramma's voor probleemoplossing die beschikbaar zijn voor EOP-beheerders (Microsoft Exchange Online Protection).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5e5493925a17725bfb9d6698b3f94050960ccc7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204328"
---
# <a name="reporting-and-message-trace-in-eop"></a>Rapportage en bericht traceren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, biedt EOP veel verschillende rapporten die u kunnen helpen bij het bepalen van de algehele status en status van uw organisatie. Er zijn ook hulpprogramma's waarmee u specifieke gebeurtenissen kunt oplossen (zoals een bericht dat niet bij de beoogde geadresseerden binnenkomt) en controlerapporten om te voldoen aan de nalevingsvereisten.

## <a name="usage-reports"></a>Gebruiksrapporten

**Activiteit in Microsoft 365-groepen:** Informatie weergeven over het aantal Microsoft 365-groepen dat wordt gemaakt en gebruikt.

**E-mailactiviteit:** Informatie weergeven over het aantal verzonden, ontvangen en gelezen berichten in uw hele organisatie en door specifieke gebruikers.

**Gebruik van e-mailapp:** Informatie weergeven over de e-mailapps die worden gebruikt. Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.

**Postvakgebruik:** Informatie weergeven over gebruikte opslagruimte, quotumverbruik, aantal items en laatste activiteit (verzend- of leesactiviteit) voor postvakken.

Zie de volgende bronnen voor meer informatie:

- [Microsoft 365-rapporten in het beheercentrum - Microsoft 365-groepen](../../admin/activity-reports/office-365-groups.md)

- [Microsoft 365-rapporten in het beheercentrum - E-mailactiviteit](../../admin/activity-reports/email-activity.md)

- [Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps](../../admin/activity-reports/email-apps-usage.md)

- [Microsoft 365-rapporten in het beheercentrum - Postvakgebruik](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Beveiligings- & compliancerapporten in het Microsoft 365-beheercentrum

Deze uitgebreide rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, met overzichtsgegevens en de mogelijkheid om in te zoomen voor meer informatie.

**Defender voor Office 365:** Informatie weergeven over veilige koppelingen en veilige bijlagen die deel uitmaken van Microsoft Defender voor Office 365.

**EOP:** Informatie weergeven over malwaredetecties, vervalste e-mail, spamdetecties en e-mailstroom van en naar uw organisatie.

[Rapporten weergeven voor Defender voor Office 365](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a>Aangepaste rapporten met Microsoft Graph

Maak programmatisch rapporten die beschikbaar zijn in het beheercentrum met Microsoft Graph. Zie Overzicht van [Microsoft Graph](/graph/overview) en Werken met Office [365-gebruiksrapporten in Microsoft Graph voor meer informatie.](/graph/api/resources/report)

## <a name="message-trace"></a>Bericht traceren

Volgt e-mailberichten terwijl ze via EOP reizen. U kunt bepalen of een e-mailbericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service. Ook wordt weergegeven welke acties zijn uitgevoerd op het bericht voordat het de uiteindelijke status heeft bereikt.

U kunt deze informatie gebruiken om de vragen van uw gebruiker efficiënt te beantwoorden, problemen met de e-mailstroom op te lossen, beleidswijzigingen te valideren en om contact op te nemen met de technische ondersteuning voor hulp.

Zie [Bericht traceren in het Beveiligings- & compliancecentrum](message-trace-scc.md).

## <a name="audit-logging"></a>Auditregistratie

Houdt specifieke wijzigingen bij die door beheerders in uw organisatie zijn aangebracht. Met deze rapporten kunt u configuratieproblemen oplossen of de oorzaak van beveiligings- of complianceproblemen vinden. Zie [Controlerapporten in EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Beschikbaarheid en latentie van gegevens rapporteren en berichten traceren

In de volgende tabel wordt beschreven wanneer EOP-rapportage- en bericht trace-gegevens beschikbaar zijn en hoelang.

****

|Rapporttype|Beschikbare gegevens voor (terugkijken)|Latentie|
|---|---|---|
|Overzichtsrapporten voor e-mailbeveiliging|90 dagen|De aggregatie van berichtgegevens is meestal binnen 24-48 uur voltooid. Sommige secundaire, geaggregeerde wijzigingen kunnen maximaal 5 dagen duren.|
|E-mailbeveiligingsdetailrapporten|90 dagen|Voor detailgegevens die minder dan 7 dagen oud zijn, moeten gegevens binnen 24 uur worden weergegeven, maar mogelijk pas na 48 uur zijn voltooid. Sommige kleine incrementele wijzigingen kunnen tot 5 dagen duren. <p> Als u detailrapporten wilt weergeven voor berichten die groter zijn dan 7 dagen oud, kunnen de resultaten enkele uren duren.|
|Gegevens over bericht traceren|90 dagen|Wanneer u een bericht traceert voor berichten die minder dan 7 dagen oud zijn, moeten de berichten binnen 5-30 minuten worden weergegeven.<p> Wanneer u een bericht traceert voor berichten die groter zijn dan 7 dagen oud, kunnen de resultaten enkele uren duren.|
|

> [!NOTE]
> De beschikbaarheid en latentie van gegevens is hetzelfde, ongeacht of deze zijn aangevraagd via het beheercentrum of externe PowerShell.