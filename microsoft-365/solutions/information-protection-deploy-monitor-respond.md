---
title: Incidenten met gegevensprivacy in uw organisatie monitoren en erop reageren
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Gebruik controle- en waarschuwingsbeleid en verzoeken van gegevensbesantwoorden om incidenten met persoonsgegevens te monitoren en erop te reageren.
ms.openlocfilehash: 8fdba5799ca9ee97a013c1322e5e79f6bf38764a
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522071"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Incidenten met gegevensprivacy in uw organisatie monitoren en erop reageren

Microsoft 365-functies zijn beschikbaar om u te helpen bij het monitoren, onderzoeken en reageren op privacyincidenten in uw organisatie terwijl u gerelateerde mogelijkheden operationaliseert. Het hebben van processen, procedures en andere documentatie voor elk van deze kan ook belangrijk zijn om aan te tonen dat regelgevende instanties aan de regels voldoen.

Dit zijn onder andere: 

- Controle- en waarschuwingsbeleid
- Verzoeken van betrokkenen (inclusief zoeken naar inhoud en eDiscovery)
- Aanvullende onderzoeksinstrumenten en rapportages

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Regelgeving voor gegevensprivacy die van invloed is op het gebruik van monitoring- en responstools

Hier is een voorbeeld van regelgeving voor gegevensprivacy die betrekking kunnen hebben op controles op informatiebeheer:

- LGPD Artikel 46
- LGPD Artikel 48
- AVG-artikel (5, lid 1, onder f)
- GDPR-artikel (15), lid 1, onder e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1) (ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

Zie De [privacyrisico's van gegevens beoordelen en gevoelige informatie identificeren](information-protection-deploy-assess.md)voor meer informatie.

De regelgeving inzake gegevensprivacy vraagt over het algemeen om het volgende voor monitoring en respons:

- Auditing, signalering en rapportage voor activiteiten in verband met de opslag, het delen en verwerken van persoonsgegevens
- De mogelijkheid om te reageren op een verzoek om een betrokkene (DSR) en in sommige gevallen onderzoekende en andere administratieve maatregelen te nemen om aan dergelijke verzoeken te voldoen.

Uw organisatie kan ook controle- en reactieactiviteiten willen uitvoeren voor andere doeleinden, zoals andere nalevingsbehoeften of om zakelijke redenen. Het opzetten van uw monitoring- en responsschema voor gegevensprivacy moet worden uitgevoerd als onderdeel van de algehele planning, implementatie en beheer van de algemene monitoring en respons.

Om u te helpen aan de slag te gaan met een monitoring- en responsschema in Microsoft 365 voor regelgeving voor gegevensprivacy, bevat dit artikel nuttige mogelijkheden in Microsoft 365 om vragen te beantwoorden, zoals: 

- Wat voor dagelijkse bewakings-, onderzoeks- en rapportagetechnieken zijn beschikbaar voor de verschillende gegevenstypen en -bronnen?
- Welke mechanismen zijn nodig om verzoeken van betrokkenen (DSR's) en eventuele corrigerende acties, zoals anonimisering, redactie en verwijdering, te behandelen.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Controle- en waarschuwingsbeleid in het Beveiligings- en Compliancecentrum

Zie deze artikelen voor het instellen van controle-, geavanceerde controle- en waarschuwingsbeleid:

- [Geïntegreerde controle](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Postvakcontrole](../compliance/enable-mailbox-auditing.md)
- [Geavanceerde audit](../compliance/advanced-audit.md)
- [Waarschuwingsbeleid](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Verzoeken van betrokkenen voor de AVG en CCPA

Zie [Verzoeken van gegevens over de AVG en CCPA](../compliance/gdpr-dsr-office365.md) voor informatie over het reageren op een DSR in Microsoft 365.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Verwijderde gebruikers beheren in Microsoft Stream

Wanneer een gebruiker voor Microsoft Stream wordt verwijderd uit Azure Active Directory (Azure AD), blijft zijn of haar naam voorafgaand aan dat punt gekoppeld aan een geposte Stream-video. Zie [Verwijderde gebruikers beheren uit Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) om deze te verwijderen.

## <a name="additional-investigative-tools"></a>Aanvullende onderzoeksinstrumenten

Hier volgen twee extra tools die nuttig kunnen zijn voor het bewaken, onderzoeken en herstellen van gegevensprivacygerelateerde incidenten in uw organisatie:

- [Insider-risicobeheer in Microsoft 365](../compliance/insider-risk-management.md), een functie van het Microsoft Compliance-beheercentrum om interne risico's te minimaliseren door dat u risicovolle activiteiten in uw organisatie detecteren, onderzoeken en actie ondernemen.
- [Gegevensonderzoeken in Microsoft 365](../compliance/overview-data-investigations.md), een functie van het Microsoft Compliance-beheercentrum om te zoeken naar gevoelige, schadelijke of misplaatste gegevens in Microsoft 365, en vervolgens te onderzoeken wat er is gebeurd om de juiste maatregelen te nemen om het incident te herstellen.
