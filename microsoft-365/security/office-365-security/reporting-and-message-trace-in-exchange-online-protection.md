---
title: Rapportage en berichttracering
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
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over rapporten en hulpprogramma's voor het oplossen van problemen die beschikbaar zijn voor EOP-beheerders (Microsoft Exchange Online Protection).
ms.openlocfilehash: b33d343d9b7f02e32619031d3ecf72ad12f891fd
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588166"
---
# <a name="reporting-and-message-trace-in-eop"></a>Rapportage en berichttracering in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken biedt EOP veel verschillende rapporten die u kunnen helpen de algehele status en status van uw organisatie te bepalen. Er zijn ook hulpmiddelen om u te helpen specifieke gebeurtenissen op te lossen (zoals een bericht dat niet aan de beoogde ontvangers wordt verzonden) en controlerapporten om te helpen bij nalevingsvereisten.

## <a name="usage-reports"></a>Gebruiksrapporten

**Activiteit van Microsoft 365-groepen**: Bekijk informatie over het aantal Microsoft 365-groepen dat is gemaakt en gebruikt.

**E-mailactiviteit**: Bekijk informatie over het aantal verzonden, ontvangen en gelezen berichten in uw hele organisatie en door specifieke gebruikers.

**Gebruik van e-mailapps**: Bekijk informatie over de e-mail-apps die worden gebruikt. Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.

**Postvakgebruik**: Bekijk informatie over gebruikte opslag, quotumverbruik, aantal items en laatste activiteit (verzenden of lezen activiteit) voor postvakken.

Zie de volgende bronnen voor meer informatie:

- [Microsoft 365-rapporten in het beheercentrum - Microsoft 365-groepen](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [Microsoft 365-rapporten in het beheercentrum - E-mailactiviteit](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [Microsoft 365-rapporten in het beheercentrum - Gebruik postvak](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Nalevingsrapporten voor beveiligings & in het Microsoft 365-beheercentrum

Deze verbeterde rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, die beknopte informatie bevat, en de mogelijkheid om in te zoomen voor meer details.

**Advanced Threat Protection (ATP)**: Bekijk informatie over veilige koppelingen en veilige bijlagen die deel uitmaken van ATP.

**EOP:** Bekijk informatie over malwaredetecties, vervalste e-mail, spamdetecties en e-mailstroom van en naar uw organisatie.

[Rapporten voor geavanceerde bedreigingsbeveiliging van Office 365 weergeven](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Aangepaste rapporten met Microsoft Graph

Maak programmatisch rapporten die beschikbaar zijn in het beheercentrum met Microsoft Graph. Zie [Overzicht van Microsoft Graph](https://docs.microsoft.com/graph/overview) en Werken met Office [365-gebruiksrapporten in Microsoft Graph voor](https://docs.microsoft.com/graph/api/resources/report)meer informatie.

## <a name="message-trace"></a>Berichttracering

Volgt e-mailberichten terwijl ze via EOP reizen. U bepalen of een e-mailbericht is ontvangen, geweigerd, uitgesteld of geleverd door de service. Het toont ook welke acties werden ondernomen op het bericht voordat het zijn definitieve status bereikt.

U deze informatie gebruiken om de vragen van uw gebruiker efficiënt te beantwoorden, problemen met de e-mailstroom op te lossen, beleidswijzigingen te valideren en de noodzaak om contact op te nemen met technische ondersteuning voor hulp te verlichten.

Zie [Berichttracering in het Security & Compliance Center](message-trace-scc.md).

## <a name="audit-logging"></a>Controlelogboekregistratie

Houdt specifieke wijzigingen bij die door beheerders in uw organisatie zijn aangebracht. Met deze rapporten u problemen met configuratieproblemen oplossen of de oorzaak van beveiligings- of nalevingsproblemen vinden. Zie [Auditing rapporten in EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Beschikbaarheid en latentie van gegevens over het traceren van berichten

In de volgende tabel wordt beschreven wanneer eop-rapportage- en berichttraceringsgegevens beschikbaar zijn en hoe lang.

||||
|:-----|:-----|:-----|
|**Rapporttype**|**Gegevens beschikbaar voor (terugkijkperiode)**|**Latency**|
|Overzichtsrapporten voor e-mailbeveiliging|90 dagen|De aggregatie van berichtgegevens is meestal binnen 24-48 uur voltooid. Sommige kleine incrementele geaggregeerde wijzigingen kunnen optreden voor maximaal 5 dagen.|
|Gedetailleerde rapporten over e-mailbeveiliging|90 dagen|Voor detailgegevens die minder dan 7 dagen oud zijn, moeten gegevens binnen 24 uur worden weergegeven, maar mogelijk pas na 48 uur zijn voltooid. Sommige kleine incrementele wijzigingen kunnen optreden voor maximaal 5 dagen. <br/><br/> Als u gedetailleerde rapporten wilt weergeven voor berichten die groter zijn dan 7 dagen oud, kunnen de resultaten enkele uren duren.|
|Gegevens over berichttracering|90 dagen|Wanneer u een berichttracering uitvoert voor berichten die minder dan 7 dagen oud zijn, moeten de berichten binnen 5-30 minuten worden weergegeven.<br/><br/> Wanneer u een berichttracering uitvoert voor berichten die groter zijn dan 7 dagen oud, kunnen de resultaten enkele uren duren.|
|

> [!NOTE]
> Beschikbaarheid en latentie van gegevens zijn hetzelfde, ongeacht of dit wordt aangevraagd via het beheercentrum of de externe PowerShell.
