---
title: Meldings- en berichttracering in Exchange Online Protection
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
description: Microsoft Exchange Online Protection (EOP) biedt veel verschillende rapporten waarmee u de algehele status en status van uw organisatie bepalen. Er zijn ook hulpmiddelen om u te helpen bij het oplossen van specifieke gebeurtenissen (zoals een bericht dat niet bij de beoogde ontvangers aankomt) en controlerapporten om te helpen voldoen aan de nalevingsvereisten. In de volgende tabel worden de rapporten en hulpmiddelen voor probleemoplossing beschreven die beschikbaar zijn voor EOP-beheerders.
ms.openlocfilehash: 282fd032e73ccb8217801a575f6029dbd9fadc9c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806295"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Meldings- en berichttracering in Exchange Online Protection

Microsoft Exchange Online Protection (EOP) biedt veel verschillende rapporten waarmee u de algehele status en status van uw organisatie bepalen. Er zijn ook hulpmiddelen om u te helpen bij het oplossen van specifieke gebeurtenissen (zoals een bericht dat niet bij de beoogde ontvangers aankomt) en controlerapporten om te helpen voldoen aan de nalevingsvereisten.

## <a name="usage-reports"></a>Gebruiksrapporten

**Activiteit in Office 365-groepen:** informatie weergeven over het aantal Office 365-groepen dat is gemaakt en gebruikt.

**E-mailactiviteit:** bekijk informatie over het aantal verzonden, ontvangen en gelezen berichten in uw hele organisatie en door specifieke gebruikers.

**Gebruik van e-mailapps:** bekijk informatie over de gebruikte e-mailapps. Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.

**Postvakgebruik**: Bekijk informatie over gebruikte opslag, quotumverbruik, artikeltelling en laatste activiteit (verzenden of lezen van activiteiten) voor postvakken.

Zie de volgende bronnen voor meer informatie:

- [Office 365-rapporten in het beheercentrum - Office 365-groepen](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [Office 365-rapporten in het beheercentrum - e-mailactiviteit](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [Office 365-rapporten in het beheercentrum - gebruik van e-mailapps](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [Office 365-rapporten in het beheercentrum - Postvakgebruik](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Beveiligingsrapporten & naleving in het Microsoft 365-beheercentrum

Deze verbeterde rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, waaronder beknopte informatie, en de mogelijkheid om in te zoomen voor meer details.

**Advanced Threat Protection (ATP)**: Bekijk informatie over veilige koppelingen en veilige bijlagen die deel uitmaken van ATP.

**EOP:** Bekijk informatie over malwaredetecties, vervalste e-mail, spamdetecties en e-mailstroom van en naar uw organisatie.

[Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Aangepaste rapporten met Microsoft Graph

Maak programmatisch rapporten die beschikbaar zijn in het Microsoft 365-beheercentrum met Behulp van Microsoft Graph. Bekijk de subonderwerpen [van Werken met Office 365-gebruiksrapporten in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).

## <a name="custom-reports-using-microsoft-graph"></a>Aangepaste rapporten met Microsoft Graph

Programmatisch rapporten maken. Zie [Overzicht van Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="message-trace"></a>Berichttracering

Volgt e-mailberichten terwijl ze door EOP reizen. U bepalen of een e-mailbericht is ontvangen, afgewezen, uitgesteld of door de service is bezorgd. Het laat ook zien welke acties zijn ondernomen op het bericht voordat het zijn definitieve status bereikte.

U deze informatie gebruiken om de vragen van uw gebruiker efficiënt te beantwoorden, problemen met de mailstroom op te lossen, beleidswijzigingen te valideren en de noodzaak om contact op te nemen met technische ondersteuning voor hulp te verlichten.

Zie [Een e-mailbericht traceren](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)

## <a name="audit-logging"></a>Controlelogboekregistratie

Houdt specifieke wijzigingen bij die door beheerders in uw organisatie zijn aangebracht. Met deze rapporten u configuratieproblemen oplossen of de oorzaak van beveiligings- of nalevingsgerelateerde problemen vinden. Zie [Controlerapporten in EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Beschikbaarheid en latentie van gegevens voor rapportage en berichttraceer

In de volgende tabel wordt beschreven wanneer eop-rapportage- en berichttraceringsgegevens beschikbaar zijn en voor hoe lang.

||||
|:-----|:-----|:-----|
|**Rapporttype**|**Beschikbare gegevens voor (terugblikperiode)**|**Latency**|
|Overzichtsrapporten voor e-mailbeveiliging|90 dagen|De aggregatie van berichtgegevens is meestal binnen 24-48 uur voltooid. Enkele kleine incrementele geaggregeerde wijzigingen kunnen maximaal 5 dagen voorkomen.|
|Detailrapporten voor e-mailbeveiliging|90 dagen|Voor detailgegevens die minder dan 7 dagen oud zijn, moeten gegevens binnen 24 uur worden weergegeven, maar mogelijk pas na 48 uur volledig zijn. Enkele kleine incrementele wijzigingen kunnen maximaal 5 dagen voorkomen. <br/><br/> Als u detailrapporten wilt weergeven voor berichten die meer dan 7 dagen oud zijn, kunnen de resultaten enkele uren duren.|
|Gegevens over berichttracering|90 dagen|Wanneer u een berichttracering uitvoert voor berichten die minder dan 7 dagen oud zijn, moeten de berichten binnen 5-30 minuten worden weergegeven.<br/><br/> Wanneer u een berichttracering uitvoert voor berichten die meer dan 7 dagen oud zijn, kunnen de resultaten enkele uren duren.|

> [!NOTE]
> Beschikbaarheid en latentie van gegevens is hetzelfde, ongeacht of deze worden aangevraagd via het Microsoft 365-beheercentrum of externe PowerShell.
