---
title: Informatie regelen die onderworpen is aan de privacywetgeving
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
description: Gebruik microsoft 365-bewaarlabels en -beleidsregels om persoonlijke gegevens in uw Microsoft 365-omgeving te beheren.
ms.openlocfilehash: a7a0d6e00d29d80dfd0cb72ba217177aa6029a2c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522299"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Informatie regelen die onderworpen is aan de privacywetgeving

Informatie governance controles kunnen worden gebruikt in uw omgeving om te helpen bij het aanpakken van de naleving van gegevens privacy behoeften, met inbegrip van een nummer dat specifiek is voor de Algemene Verordening Gegevensbescherming (GDPR), HIPAA-HITECH (de Verenigde Staten privacy wet), California Consumer Protection Act (CCPA), en de Brazil Data Protection Act (LGPD). 

Deze controles vallen voornamelijk in de volgende oplossingsgebieden:

- Bewaarbeleid
- Bewaarlabels
- Records Management

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Regelgeving voor gegevensprivacy die van invloed is op de controles op informatiebeheer

Hier is een voorbeeld van regelgeving voor gegevensprivacy die betrekking kunnen hebben op controles op informatiebeheer:

- GDPR-artikel (13,2) onder a)
- AVG-artikel (5, lid 1, onder f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)ii))
- LGPD Artikel 46

Voor meer informatie over deze regelgeving, zie de [beoordeling van de privacy van gegevens risico's en identificeren gevoelige informatie artikel](information-protection-deploy-assess.md).

Voor informatiegovernance vragen gegevensprivacyregelgeving doorgaans om het volgende:

- U moet een technische regeling hanteren voor bewaring en verwijdering van persoonsgegevens die zijn opgeslagen in Microsoft 365.
- Als u persoonlijke gegevens gaat opslaan, informeer dan het onderwerp van hoe lang de gegevens worden opgeslagen, wat nu een standaardpraktijk is op front-end websystemen.
- Persoonsgegevens moeten worden beschermd tegen onbedoelde verwerking, verlies of wijziging met behulp van verifieerbare methoden.
- Elke actie die tegen persoonsgegevens wordt uitgevoerd, moet worden gedocumenteerd en dat documentatie gedurende een bepaalde periode moet worden bewaard.

Omdat de regelgeving voor gegevensprivacy niet erg specifiek is als het gaat om het bewaren en verwijderen van gegevens, moeten andere factoren in aanmerking worden genomen die richtlijnen voor informatiebeheer kunnen dicteren voor persoonlijke gegevens die zijn opgeslagen in uw Microsoft 365-abonnement. Hier zijn een paar voorbeelden:

- Het verouderen van consumentenaccounts na 5 jaar inactiviteit en vereist verwijdering of anonimisering van accountgegevens na dat punt, waarbij orkestratie tussen het systeem moet worden opgeslagen en de gegevens en workflows die verband houden met meldingen en andere automatisering.
- Het configureren van regels voor het bijhouden van beleid en procedures met betrekking tot gdpr gedurende drie jaar nadat ze zijn vervangen, wat overeenkomt met het bewaarschema van de organisatie voor beleid en procedures.
- Het onderhouden van een apart abonnement voor communicatie met consumenten via de ondersteuningsorganisatie. Alle e-mailcommunicatie werd na twee weken bewaard en verwijderd om eventuele opbouw van privacyschulden in het systeem te verminderen.

Een belangrijke vraag om te beantwoorden is: 

- Hoe lang moet informatie met persoonsgegevens worden bewaard om geldige zakelijke redenen om te voorkomen dat het voor altijd wordt bewaard? Dit moet in evenwicht worden gebracht met de retentiebehoeften voor bedrijfscontinuïteit.

Ongeacht de juridische en zakelijke redenen om persoonlijke gegevens rond te houden of te verwijderen, biedt Microsoft een aantal mogelijkheden om uw gegevensbeheerschema in Microsoft 365 te implementeren.

## <a name="managing-information-governance-in-microsoft-365"></a>Informatiebeheer beheren in Microsoft 365

Zie [Informatiebeheer](../compliance/manage-information-governance.md) en [gegevensbewaring, verwijdering en vernietiging beheren in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)als u wilt beginnen.

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Bewaarschema's voor gegevens voor containers, e-mail en inhoud ontwikkelen

Houd het volgende in gedachten:

- Het opstellen van een gegevensbewaringsschema voor gedefinieerde informatietypen moet worden beschouwd als een voorwaarde voor de uitvoering van een bewaar- of verwijderingsschema.

- Gezien het aantal informatietypen dat de meeste organisaties belangrijk vinden en de bijbehorende grote bewaarschema's voor records die daarbij passen, vereist het implementeren van een strategie voor het bewaren van gegevens en recordsbeheer planning. 

- De sleutel tot het opzetten van een effectieve data governance strategie van dit type is om zich te concentreren op de hoogste prioriteit zakelijke functies en informatietypen die meer formeel beheer vereisen. Voorbeelden zijn juridische contracten, jaarrekeningen en documentatie over naleving van de regelgeving. Probeer te voorkomen dat u een apart bewaarschema voor elk informatietype hebt. Probeer algemene categorieën zoveel mogelijk te gebruiken, bijvoorbeeld met bewaarschema's van 7 jaar voor algemene bedrijfsinhoud.

- Zodra de typen persoonlijke gegevens in uw omgeving beter bekend zijn, stelt u bewaar- en verwijderingsschema's voor dit type inhoud vast en past u uw informatiearchitectuur aan om het beheer van dit soort informatie gemakkelijker te maken. Dit is bijvoorbeeld het isoleren van persoonlijke gegevens in afzonderlijke sites, bibliotheken of mappen met gecontroleerde toegang.

### <a name="retention-policies"></a>Bewaarbeleid

[Retentiebeleid](../compliance/retention-policies.md) maken en implementeren voor inhoud in sites die automatisch worden toegepast.

Voor gegevensprivacy voor sites die persoonsgegevens bevatten of naar verwachting bevatten, moet u bewaar- of verwijderingsregels opgeven om aan de organisatienormen te voldoen.

### <a name="retention-labels"></a>Bewaarlabels

[Retentielabels](../compliance/labels.md) maken en implementeren voor inhoud en e-mail.

Voor gegevensprivacy voor sites, bibliotheken, mappen en e-mail die persoonlijke gegevens bevatten of naar verwachting bevatten, worden regels voor automatisch bewaren of verwijderen opgegeven om aan de organisatienormen te voldoen.

### <a name="records-management"></a>Records Management

Retentielabels maken en implementeren voor recordsbeheer op basis van een bewaarschema en bestandsplan voor records.

Voor gegevensprivacy worden verzoeken van betrokkenen (DSR's) die door de juridische afdeling zijn ontvangen, als record gedeclareerd en voor onbepaalde tijd opgeslagen om te voldoen aan de specificaties voor het bewaren van activiteiten in de regelgeving.

Zie deze bronnen voor meer informatie: 

- [Records Management](../compliance/records-management.md)
- [Bestandsplanbeheer](../compliance/file-plan-manager.md)
- [Op gebeurtenissen gebaseerde retentie voor recordsbeheer](../compliance/automate-event-driven-retention.md)
- [Inhoudsverklaring](../compliance/disposition-reviews.md)
