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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over hulpprogramma's voor het oplossen van rapporten die beschikbaar zijn voor Microsoft Exchange Online Protection (EOP)-beheerders.
ms.openlocfilehash: 86f4e18430324ed95f036f93746d826225ec3b2f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196397"
---
# <a name="reporting-and-message-trace-in-eop"></a>Rapporten en berichten traceren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, biedt EOP veel verschillende rapporten waarmee u de algehele status en de status van uw organisatie kunt bepalen. Er zijn ook hulpmiddelen waarmee u problemen kunt oplossen, zoals een bericht dat niet aan de bedoelde geadresseerden voldoet, en de controlerapporten voor de nalevingsvereisten.

## <a name="usage-reports"></a>Gebruiksrapporten

**Activiteiten van Microsoft 365 groepen**: informatie weergeven over het aantal microsoft 365-groepen dat is gemaakt en gebruikt.

**E-mail activiteit**: Hier vindt u informatie over het aantal verzonden, ontvangen en gelezen berichten in uw hele organisatie en van specifieke gebruikers.

**Gebruik van e-mail-apps**: informatie weergeven over de gebruikte e-mail-apps. Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.

**Postvakgebruik**: informatie weergeven over gebruikte opslagruimte, quota verbruik, aantal items, en laatste activiteit (verzenden of lezen) voor postvakken.

Raadpleeg de volgende bronnen voor meer informatie:

- [Microsoft 365-rapporten in het Beheercentrum-Microsoft 365-groepen](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [Microsoft 365-rapporten in het Beheercentrum-e-mail activiteit](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [Microsoft 365-rapporten in het Beheercentrum-gebruik van e-mail-apps](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [Microsoft 365-rapporten in het Beheercentrum-postvakgebruik](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Beveiligings & nalevings rapporten in het Microsoft 365-Beheercentrum

Deze verbeterde rapporten bieden een interactieve rapportering van EOP-beheerders, waaronder samenvattende informatie en de mogelijkheid om te inzoomen voor meer details.

**Advanced Threat Protection (ATP)**: Bekijk informatie over veilige koppelingen en veilige bijlagen die deel uitmaken van ATP.

**EOP**: informatie over detectie van malware, spoofing voor e-mail, detectie van spam, en de e-mail stroom van en naar uw organisatie.

[Rapporten weergeven voor Office 365 Advanced Threat Protection](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Aangepaste rapporten met Microsoft Graph

U maakt via programmering rapporten die beschikbaar zijn in het Beheercentrum met behulp van Microsoft Graph. Zie voor meer informatie: [overzicht van Microsoft Graph](https://docs.microsoft.com/graph/overview) en [werken met Office 365-gebruiksrapporten in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).

## <a name="message-trace"></a>Bericht traceren

Volg deze e-mailberichten wanneer ze onderweg zijn via EOP. U kunt bepalen of een e-mailbericht is ontvangen, afgewezen, uitgesteld of geleverd door de service. Ook ziet u welke acties zijn uitgevoerd op het bericht voordat het de definitieve status bereikte.

U kunt deze gegevens gebruiken om de vragen van uw gebruikers op de juiste manier op te lossen, problemen met de e-mail stroom op te lossen, beleidswijzigingen te valideren en contact op te nemen met technische ondersteuning voor hulp.

Zie [bericht traceren in de beveiligings & nalevings centrum](message-trace-scc.md).

## <a name="audit-logging"></a>Controlelogboekregistratie

Hiermee kunt u specifieke wijzigingen van beheerders bijhouden in uw organisatie. Deze rapporten kunnen u helpen bij het oplossen van problemen met de configuratie of voor het oplossen van problemen met betrekking tot beveiliging of compliance. Zie [controlerapporten in EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Beschikbaarheid en latentie van de gegevens van rapporten en berichten traceren

In de volgende tabel wordt beschreven wanneer EOP-rapporten en-traceringsgegevens beschikbaar zijn en hoe lang dit duurt.

****

|Rapporttype|Beschikbare gegevens voor (weergeven als periode)|Tijd|
|---|---|---|
|Overzichtsrapporten mail beveiliging|90 dagen|Het samenvoegen van berichtgegevens is vooral binnen 24-48 uur voltooid. Sommige kleine, incrementele, incrementele, ondergebrachte wijzigingen worden gedurende vijf dagen veroorzaakt.|
|Details van e-mail beveiligingsrapporten|90 dagen|Voor detailgegevens die minder dan zeven dagen oud zijn, moeten de gegevens binnen 24 uur worden weergegeven, maar mogelijk niet voltooien tot 48 uur. U kunt maximaal 5 dagen enkele kleine incrementele wijzigingen voordoen. <br/><br/> Als u detailrapporten wilt weergeven voor berichten die ouder zijn dan zeven dagen, kan het tot een paar uur duren voordat de resultaten zijn afgelopen.|
|Berichten traceren|90 dagen|Wanneer u een bericht tracering uitvoert voor berichten die minder dan zeven dagen oud zijn, worden de berichten weergegeven binnen 5-30 minuten.<br/><br/> Wanneer u een bericht tracering uitvoert voor berichten die ouder zijn dan zeven dagen, kunnen de resultaten enkele uren duren.|
|

> [!NOTE]
> De beschikbaarheid en latentie van de gegevens is afhankelijk van het aangevraagde verzoek via het Beheercentrum of vanuit een externe PowerShell.
