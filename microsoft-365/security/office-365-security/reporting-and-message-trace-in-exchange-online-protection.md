---
title: Rapportage en berichttracering in Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) biedt veel verschillende rapporten waarmee u de algehele status en status van uw organisatie bepalen. Er zijn ook tools om specifieke gebeurtenissen op te lossen (zoals een bericht dat niet bij de beoogde ontvangers binnenkomt) en controlerapporten om te helpen bij nalevingsvereisten. In de volgende tabel worden de rapporten en hulpprogramma's voor probleemoplossing beschreven die beschikbaar zijn voor EOP-beheerders.
ms.openlocfilehash: e961c76daaad72fbd1ddede5651cb49fd66d48be
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634350"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Rapportage en berichttracering in Exchange Online Protection

Microsoft Exchange Online Protection (EOP) biedt veel verschillende rapporten waarmee u de algehele status en status van uw organisatie bepalen. Er zijn ook tools om specifieke gebeurtenissen op te lossen (zoals een bericht dat niet bij de beoogde ontvangers binnenkomt) en controlerapporten om te helpen bij nalevingsvereisten.

## <a name="usage-reports"></a>Gebruiksrapporten

**Activiteit in Microsoft 365-groepen:** bekijk informatie over het aantal Microsoft 365-groepen dat wordt gemaakt en gebruikt.

**E-mailactiviteit:** bekijk informatie over het aantal verzonden, ontvangen en gelezen berichten in uw hele organisatie en door specifieke gebruikers.

**Gebruik van e-mailapps:** bekijk informatie over de e-mailapps die worden gebruikt. Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.

**Postvakgebruik:** bekijk informatie over gebruikte opslag, quotumverbruik, aantal objecten en laatste activiteit (verzenden of lezen van activiteiten) voor postvakken.

Zie de volgende bronnen voor meer informatie:

- [Microsoft 365-rapporten in het beheercentrum - Microsoft 365-groepen](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [Microsoft 365-rapporten in het beheercentrum - E-mailactiviteit](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [Microsoft 365-rapporten in het beheercentrum - gebruik van e-mailapps](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [Microsoft 365-rapporten in het beheercentrum - Postvakgebruik](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Beveiligingsrapporten & nalevingsrapporten in het Microsoft 365-beheercentrum

Deze verbeterde rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, waaronder beknopte informatie en de mogelijkheid om in te zoomen voor meer details.

**Advanced Threat Protection (ATP)**: Bekijk informatie over veilige koppelingen en veilige bijlagen die deel uitmaken van ATP.

**EOP:** Bekijk informatie over malwaredetecties, vervalste e-mail, spamdetecties en e-mailstroom van en naar uw organisatie.

[Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Aangepaste rapporten met Microsoft Graph

Maak programmatisch rapporten die beschikbaar zijn in het Microsoft 365-beheercentrum met Behulp van Microsoft Graph. Zie de subonderwerpen van [Werken met Office 365-gebruiksrapporten in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).

## <a name="custom-reports-using-microsoft-graph"></a>Aangepaste rapporten met Microsoft Graph

Programmatisch rapporten maken. Zie [Overzicht van Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="message-trace"></a>Berichttracering

Volgt e-mailberichten terwijl ze via EOP reizen. U bepalen of een e-mailbericht is ontvangen, geweigerd, uitgesteld of geleverd door de service. Het laat ook zien welke acties werden ondernomen op het bericht voordat het zijn definitieve status bereikte.

U deze informatie gebruiken om de vragen van uw gebruiker efficiënt te beantwoorden, problemen met de e-mailstroom op te lossen, beleidswijzigingen te valideren en de noodzaak om contact op te nemen met de technische ondersteuning voor hulp te verlichten.

Zie [Een e-mailbericht traceren](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)

## <a name="audit-logging"></a>Controlelogboekregistratie

Houdt specifieke wijzigingen bij die door beheerders zijn aangebracht in uw organisatie. Met deze rapporten u configuratieproblemen oplossen of de oorzaak van beveiligings- of nalevingsproblemen vinden. Zie [Controlerapporten in EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Beschikbaarheid en latentie van rapportage- en berichttraceringsgegevens

In de volgende tabel wordt beschreven wanneer EOP-rapportage- en berichttraceringsgegevens beschikbaar zijn en voor hoe lang.

||||
|:-----|:-----|:-----|
|**Rapporttype**|**Beschikbare gegevens voor (terugblikperiode)**|**Latency**|
|Overzichtsrapporten voor e-mailbeveiliging|90 dagen|De aggregatie van berichtgegevens is meestal binnen 24-48 uur voltooid. Sommige kleine incrementele geaggregeerde wijzigingen kunnen optreden voor maximaal 5 dagen.|
|Detailrapporten voor e-mailbeveiliging|90 dagen|Voor gedetailleerde gegevens die minder dan 7 dagen oud zijn, moeten gegevens binnen 24 uur worden weergegeven, maar mogelijk niet volledig zijn tot 48 uur. Sommige kleine incrementele wijzigingen kunnen optreden voor maximaal 5 dagen. <br/><br/> Als u gedetailleerde rapporten wilt weergeven voor berichten die meer dan 7 dagen oud zijn, kunnen de resultaten enkele uren duren.|
|Gegevens over berichttracering|90 dagen|Wanneer u een berichttracering uitvoert voor berichten die minder dan 7 dagen oud zijn, moeten de berichten binnen 5-30 minuten worden weergegeven.<br/><br/> Wanneer u een berichttracering uitvoert voor berichten die meer dan 7 dagen oud zijn, kunnen de resultaten enkele uren duren.|

> [!NOTE]
> Beschikbaarheid en latentie van gegevens is hetzelfde, of het nu wordt aangevraagd via het Microsoft 365-beheercentrum of het externe PowerShell.
