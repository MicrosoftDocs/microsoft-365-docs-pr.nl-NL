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
ms.openlocfilehash: 783c7ea0aca47c805daf66592b401a98f739d071
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288077"
---
# <a name="reporting-and-message-trace-in-eop"></a>Rapportage en bericht traceren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken biedt EOP veel verschillende rapporten die u kunnen helpen de algehele status en status van uw organisatie te bepalen. Er zijn ook hulpprogramma's om u te helpen bij het oplossen van specifieke gebeurtenissen (zoals een bericht dat niet is aangekomen bij de beoogde geadresseerden) en het controleren van rapporten om u te helpen voldoen aan de nalevingsvereisten.

## <a name="usage-reports"></a>Gebruiksrapporten

**Activiteit in Microsoft 365-groepen:** informatie weergeven over het aantal Microsoft 365-groepen dat wordt gemaakt en gebruikt.

**E-mailactiviteit:** informatie weergeven over het aantal verzonden, ontvangen en gelezen berichten in de hele organisatie en door specifieke gebruikers.

**Gebruik van e-mailapps:** bekijk informatie over de e-mailapps die worden gebruikt. Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.

**Postvakgebruik:** informatie weergeven over gebruikte opslag, quotumgebruik, aantal items en laatste activiteit (verzenden of lezen) voor postvakken.

Zie de volgende bronnen voor meer informatie:

- [Microsoft 365-rapporten in het beheercentrum - Microsoft 365-groepen](../../admin/activity-reports/office-365-groups.md)

- [Microsoft 365-rapporten in het beheercentrum - E-mailactiviteit](../../admin/activity-reports/email-activity.md)

- [Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps](../../admin/activity-reports/email-apps-usage.md)

- [Microsoft 365-rapporten in het beheercentrum - Postvakgebruik](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Beveiligingsrapporten & compliancerapporten in het Microsoft 365-beheercentrum

Deze verbeterde rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, met overzichtsinformatie en de mogelijkheid om in te zoomen voor meer informatie.

**Defender voor Office 365:** informatie weergeven over veilige koppelingen en veilige bijlagen die deel uitmaken van Microsoft Defender voor Office 365.

**EOP:** informatie weergeven over malwaredetectie, vervalste e-mail, spamdetecties en e-mailstromen van en naar uw organisatie.

[Rapporten voor Defender voor Office 365 weergeven](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Aangepaste rapporten met Microsoft Graph

Via programmatisch rapporten maken die beschikbaar zijn in het beheercentrum met Behulp van Microsoft Graph. Zie Overview [of Microsoft Graph](https://docs.microsoft.com/graph/overview) and Working with Office 365 usage reports in Microsoft Graph (Overzicht van Microsoft Graph en werken met Office [365-gebruiksrapporten in Microsoft Graph) voor meer informatie.](https://docs.microsoft.com/graph/api/resources/report)

## <a name="message-trace"></a>Bericht traceren

Volgt e-mailberichten terwijl ze door EOP reizen. U kunt bepalen of een e-mailbericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service. U ziet ook welke acties er zijn uitgevoerd op het bericht voordat het de uiteindelijke status heeft bereikt.

U kunt deze informatie gebruiken om op een efficiënte manier antwoord te geven op vragen van gebruikers, problemen met de e-mailstroom op te lossen, beleidswijzigingen te valideren en de noodzaak om contact op te nemen met de technische ondersteuning voor hulp.

Zie [Bericht traceren in het beveiligings- & Compliancecentrum.](message-trace-scc.md)

## <a name="audit-logging"></a>Auditlogregistratie

Houdt specifieke wijzigingen bij die zijn aangebracht door beheerders in uw organisatie. Deze rapporten kunnen u helpen configuratieproblemen op te lossen of de oorzaak van beveiligings- of nalevingsproblemen te vinden. Zie [Controlerapporten in EOP.](auditing-reports-in-eop.md)

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Beschikbaarheid en latentie van rapportage- en bericht traceren van gegevens

In de volgende tabel wordt beschreven wanneer gegevens over EOP-rapporten en bericht traceren beschikbaar zijn en hoelang.

****

|Rapporttype|Gegevens die beschikbaar zijn voor (terugkijken periode)|Latentie|
|---|---|---|
|Overzichtsrapporten voor E-mailbeveiliging|90 dagen|De aggregatie van berichtgegevens wordt meestal binnen 24-48 uur voltooid. Enkele kleine, incrementele samengevoegde wijzigingen kunnen maximaal 5 dagen duren.|
|Detailrapporten over E-mailbeveiliging|90 dagen|Voor detailgegevens die minder dan zeven dagen oud zijn, worden gegevens binnen 24 uur weergegeven, maar zijn ze mogelijk pas na 48 uur voltooid. Enkele kleine incrementele wijzigingen kunnen maximaal 5 dagen duren. <p> Als u detailrapporten wilt weergeven voor berichten die meer dan zeven dagen oud zijn, kan het enkele uren duren voordat de resultaten zijn bekeken.|
|Gegevens voor bericht traceren|90 dagen|Wanneer u een bericht traceren voor berichten die minder dan zeven dagen oud zijn, worden de berichten binnen 5-30 minuten weergegeven.<p> Wanneer u een bericht traceren voor berichten die groter zijn dan zeven dagen oud, kan het enkele uren duren.|
|

> [!NOTE]
> De beschikbaarheid en latentie van gegevens is hetzelfde, ongeacht of dit is aangevraagd via het beheercentrum of externe PowerShell.
