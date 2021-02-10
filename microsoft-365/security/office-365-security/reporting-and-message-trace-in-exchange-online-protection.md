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
description: In dit artikel vindt u informatie over rapporten en hulpprogramma's voor probleemoplossing die beschikbaar zijn voor beheerders van Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86c9eb0ee050c4c1a40ef7f29ea3d01dc202be9a
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166673"
---
# <a name="reporting-and-message-trace-in-eop"></a>Rapportage en bericht traceren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken biedt EOP veel verschillende rapporten die u kunnen helpen de algehele status en status van uw organisatie te bepalen. Er zijn ook hulpprogramma's om u te helpen bij het oplossen van specifieke gebeurtenissen (zoals een bericht dat niet is aangekomen bij de beoogde geadresseerden) en het controleren van rapporten om u te helpen voldoen aan de nalevingsvereisten.

## <a name="usage-reports"></a>Gebruiksrapporten

**Activiteit in Microsoft 365-groepen:** informatie weergeven over het aantal Microsoft 365-groepen dat wordt gemaakt en gebruikt.

**E-mailactiviteit:** bekijk informatie over het aantal verzonden, ontvangen en gelezen berichten in de hele organisatie en door specifieke gebruikers.

**Gebruik van e-mailapps:** bekijk informatie over de e-mailapps die worden gebruikt. Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.

**Postvakgebruik:** informatie weergeven over gebruikte opslag, quotumgebruik, aantal items en laatste activiteit (verzenden of lezen) voor postvakken.

Zie de volgende bronnen voor meer informatie:

- [Microsoft 365-rapporten in het beheercentrum - Microsoft 365-groepen](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [Microsoft 365-rapporten in het beheercentrum - E-mailactiviteit](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [Microsoft 365-rapporten in het beheercentrum - Postvakgebruik](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Beveiligingsrapporten & compliancerapporten in het Microsoft 365-beheercentrum

Deze verbeterde rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, met overzichtsinformatie en de mogelijkheid om in te zoomen voor meer informatie.

**Defender voor Office 365:** informatie weergeven over veilige koppelingen en veilige bijlagen die deel uitmaken van Microsoft Defender voor Office 365.

**EOP:** informatie weergeven over malwaredetectie, vervalste e-mail, spamdetecties en e-mailstromen van en naar uw organisatie.

[Rapporten voor Defender voor Office 365 weergeven](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Aangepaste rapporten met Microsoft Graph

Via programmatisch rapporten maken die beschikbaar zijn in het beheercentrum met Behulp van Microsoft Graph. Zie Overview [of Microsoft Graph](https://docs.microsoft.com/graph/overview) and Working with Office 365 usage reports in Microsoft Graph (Overzicht van Microsoft Graph en werken met Office [365-gebruiksrapporten in Microsoft Graph) voor meer informatie.](https://docs.microsoft.com/graph/api/resources/report)

## <a name="message-trace"></a>Bericht traceren

Volgt e-mailberichten terwijl ze door EOP reizen. U kunt bepalen of een e-mailbericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service. U ziet ook welke acties er zijn uitgevoerd op het bericht voordat het de uiteindelijke status heeft bereikt.

U kunt deze informatie gebruiken om efficiënt antwoord te geven op vragen van gebruikers, problemen met de e-mailstroom op te lossen, beleidswijzigingen te valideren en de noodzaak om contact op te nemen met de technische ondersteuning voor hulp.

Zie [Bericht traceren in het beveiligings- & Compliancecentrum.](message-trace-scc.md)

## <a name="audit-logging"></a>Auditlogregistratie

Houdt specifieke wijzigingen bij die zijn aangebracht door beheerders in uw organisatie. Deze rapporten kunnen u helpen configuratieproblemen op te lossen of de oorzaak van beveiligings- of nalevingsproblemen te vinden. Zie [Controlerapporten in EOP.](auditing-reports-in-eop.md)

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Beschikbaarheid en latentie van rapportage- en bericht traceren van gegevens

In de volgende tabel wordt beschreven wanneer gegevens over EOP-rapporten en bericht traceren beschikbaar zijn en hoelang.

****

|Rapporttype|Gegevens beschikbaar voor (terugkijken termijn)|Latentie|
|---|---|---|
|Overzichtsrapporten voor E-mailbeveiliging|90 dagen|De aggregatie van berichtgegevens wordt meestal binnen 24-48 uur voltooid. Enkele kleine, incrementele samengevoegde wijzigingen kunnen maximaal 5 dagen duren.|
|Detailrapporten over E-mailbeveiliging|90 dagen|Voor detailgegevens die minder dan zeven dagen oud zijn, worden gegevens binnen 24 uur weergegeven, maar zijn ze mogelijk pas na 48 uur voltooid. Enkele kleine incrementele wijzigingen kunnen maximaal 5 dagen duren. <p> Als u detailrapporten wilt weergeven voor berichten die meer dan zeven dagen oud zijn, kunnen de resultaten enkele uren in duren.|
|Gegevens voor bericht traceren|90 dagen|Wanneer u een bericht traceren voor berichten die minder dan zeven dagen oud zijn, worden de berichten binnen 5-30 minuten weergegeven.<p> Wanneer u een bericht traceren voor berichten die groter zijn dan zeven dagen oud, kan het enkele uren duren.|
|

> [!NOTE]
> De beschikbaarheid en latentie van gegevens is hetzelfde, ongeacht of dit is aangevraagd via het beheercentrum of externe PowerShell.
