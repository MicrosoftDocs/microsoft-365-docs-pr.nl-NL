---
title: Toezicht houden op het privacy van gebeurtenissen in uw organisatie en deze beantwoorden
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
- m365solution-scenario
ms.custom: ''
description: Gebruik controle-en waarschuwings beleid en verzoeken om gegevens te controleren en te reageren op persoonlijke gegevens.
ms.openlocfilehash: 296220ac8b34d9ce10c783194b78ca344e746b84
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377197"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Toezicht houden op het privacy van gebeurtenissen in uw organisatie en deze beantwoorden

Microsoft 365-functies zijn beschikbaar om u te helpen bij het controleren, onderzoeken en beantwoorden van gebeurtenissen in uw organisatie, zoals u operationalize gerelateerde mogelijkheden. Het hebben van processen, procedures en andere documentatie voor elk van deze factoren kan ook belangrijk zijn om de naleving van de regelgevende instanties te illustreren.

Dit zijn onder andere: 

- Beleid voor controle en waarschuwingen
- Aanvragen voor gegevens, waaronder inhoud zoeken en eDiscovery
- Aanvullende hulpprogramma's voor onderzoek en rapportage

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Voorschriften met betrekking tot de privacy van functies voor het gebruik van controle-en antwoord Programma's

Hieronder ziet u een voorbeeld van een lijst met voorschriften voor de privacy van gegevens die in verband met informatiebeheer kunnen worden beheerd:

- LGPD artikel 46
- LGPD artikel 48
- AVG artikel (5) (1) (f)
- AVG artikel (15) (1) (e)
- HIPAA-HITECH (45 C.F.R. 164.308 (a) (1) (II) (D))
- HIPAA-HITECH (45 C.F.R. 164.308 (a) (6) (II)
- HIPAA-HITECH (45 C.F.R. 164.312 (b))
- CCPA (1798.105 (c))

Voor meer informatie raadpleegt u de [beoordeelde Risico's en gevoelige informatie voor gegevens](information-protection-deploy-assess.md).

De informatie over de privacy van gegevens wordt in het algemeen naar het volgende gekeken voor bewaken en beantwoorden:

- Controleren, waarschuwen en rapporteren voor activiteiten met betrekking tot opslag, delen en verwerking van persoonlijke gegevens
- De mogelijkheid om te reageren op een verzoek voor een data subject (DSR) en in sommige gevallen, onderzoek van onderzoek en andere administratieve maatregelen om aan dergelijke verzoeken te voldoen.

Uw organisatie wil wellicht ook toezicht-en antwoord activiteiten uitvoeren voor andere doeleinden, zoals andere nalevings behoeften of voor zakelijke redenen. Het opzetten van uw toezicht-en antwoordschema voor de privacy van gegevens moet worden afgehandeld als onderdeel van de algemene controle-en antwoord planning, implementatie en beheer.

Om u te helpen aan de slag te gaan met een monitoring-en antwoordschema in Microsoft 365 voor data privacy Regulations, bevat dit artikel nuttige functies in Microsoft 365 voor het beantwoorden van vragen, zoals: 

- Welke soort dag-en rapportage technieken zijn er voor de verschillende gegevenstypen en bronnen beschikbaar?
- Welke mechanismen nodig zijn voor het verwerken van aanvragen voor gegevens-subjecten (DSRs) en eventuele herstelbewerkingen, zoals anonimiseren, redactie en verwijdering.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Beleidsregels voor controleren en waarschuwingen in het beveiligings-en nalevings centrum

Zie de volgende artikelen voor het instellen van controle, geavanceerde controle en waarschuwings beleid:

- [Geïntegreerde controle](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Postvakcontrole](../compliance/enable-mailbox-auditing.md)
- [Geavanceerde controle](../compliance/advanced-audit.md)
- [Waarschuwingsbeleid](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Aanvragen voor AVG en CCPA

Zie [aanvragen van AVG en CCPA](../compliance/gdpr-dsr-office365.md) voor meer informatie over het reageren op een DSR in microsoft 365.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Verwijderde gebruikers beheren in Microsoft stream

Voor Microsoft stream, wanneer een gebruiker wordt verwijderd uit Azure Active Directory (Azure AD), en het e-mailadres van de gebruiker vóór dat punt is gekoppeld aan de video, blijft het bijbehorende e-mailadres aan de video gekoppeld. Zie [Verwijderde gebruikers beheren vanuit Microsoft stream](https://docs.microsoft.com/stream/managing-deleted-users) om dit te verwijderen.

## <a name="additional-investigative-tools"></a>Aanvullende hulpmiddelen voor onderzoek

Hier volgen nog twee extra hulpmiddelen waarmee u nuttige gebeurtenissen in verband met privacy in uw organisatie kunt volgen, onderzoeken en herstellen:

- [Insider Risk Management in Microsoft 365](../compliance/insider-risk-management.md), een functie van het Microsoft compliance-Beheercentrum om intern risico te minimaliseren, zodat u risico activiteiten in uw organisatie kunt detecteren, onderzoeken en ondernemen.
- [Gegevens onderzoek in Microsoft 365](../compliance/overview-data-investigations.md), een functie van het Microsoft compliance-Beheercentrum om te zoeken naar gevoelige, kwaadaardige of verkeerd geplaatste gegevens in microsoft 365 en onderzoek wat er is gebeurd om het incident te herstellen.
