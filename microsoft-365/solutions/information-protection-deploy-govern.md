---
title: Bepalen van gegevens die onderworpen zijn aan privacyregel voor gegevens
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
description: Gebruik microsoft 365 bewaarlabels en -beleid om persoonlijke gegevens te beheren in uw Microsoft 365-omgeving.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928434"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Bepalen van gegevens die onderworpen zijn aan privacyregel voor gegevens

Informatiebeheerbesturingselementen kunnen worden gebruikt in uw omgeving om te helpen bij het voldoen aan de nalevingsvereisten voor gegevensbescherming, waaronder een nummer dat specifiek is voor Algemene verordening gegevensbescherming (AVG), HIPAA-HITECH (de Amerikaanse privacywet voor gezondheidszorg), de California Consumer Protection Act (CTPA) en de Brazil Data Protection Act (LGPD). 

Deze besturingselementen vallen voornamelijk onder de volgende oplossingsgebieden:

- Bewaarbeleid
- Bewaarlabels
- Records Management

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Privacyregels voor gegevens die van invloed zijn op besturingselementen voor informatiebeheer

Hier vindt u een voorbeeld van de privacyregels voor gegevens die betrekking kunnen hebben op besturingselementen voor informatiebeheer:

- AVG-artikel (13)(2)(a)
- AVG-artikel (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))
- LGPD-artikel 46

Zie het artikel Privacyrisico's voor gegevens beoordelen en gevoelige informatie identificeren voor meer [informatie over deze regelgeving.](information-protection-deploy-assess.md)

Voor informatiebeheer is de privacyregel voor gegevens meestal het volgende nodig:

- U moet een technisch schema gebruiken voor het bewaren en verwijderen van persoonlijke gegevens die zijn opgeslagen in Microsoft 365.
- Als u persoonlijke gegevens gaat opslaan, informeert u het onderwerp over hoe lang de gegevens worden opgeslagen, wat nu een standaardpraktijk is op front-endwebsystemen.
- Persoonsgegevens moeten worden beschermd tegen onbedoelde verwerking, verlies of wijziging met behulp van controleerbare methoden.
- Alle acties die worden uitgevoerd met betrekking tot persoonlijke gegevens, moeten worden gedocumenteerd en de documentatie moet voor een bepaalde periode worden bewaard.

Omdat de privacyregels voor gegevens niet erg specifiek zijn als het gaat om het bewaren en verwijderen van gegevens, moet rekening worden gehouden met andere factoren die richtlijnen voor informatiebeheer kunnen dicteren voor persoonlijke gegevens die zijn opgeslagen in uw Microsoft 365-abonnement. Hier zijn enkele voorbeelden:

- Veroudert consumentenaccounts na 5 jaar inactiviteit en vereist verwijdering of anonimisatie van accountgegevens na dat punt, waarbij het systeem de gegevens en werkstromen met betrekking tot meldingen en andere automatisering moet opslaan.
- Het configureren van regels voor het behouden van beleidsregels en procedures met betrekking tot AVG is ongeveer drie jaar nadat ze zijn overdwars, wat in overeenstemming is met het bewaarschema van de organisatie voor beleid en procedures.
- Het onderhouden van een afzonderlijk abonnement voor het communiceren met consumenten via de ondersteuningsorganisatie. Alle e-mailcommunicatie is na twee weken bewaard en verwijderd om de opbouw van privacyschulden in het systeem te beperken.

Een belangrijke vraag die u moet beantwoorden is: 

- Hoe lang moeten gegevens met persoonlijke gegevens worden bewaard om geldige zakelijke redenen om te voorkomen dat er 'voor altijd' wordt gebruikt? Dit moet worden afgewogen met de bewaarbehoeften voor bedrijfscontinuïteit.

Ongeacht de juridische en zakelijke redenen voor het bewaren van persoonlijke gegevens of het verwijderen ervan, biedt Microsoft een aantal mogelijkheden voor het implementeren van uw gegevensbeheerschema in Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Informatiebeheer beheren in Microsoft 365

Zie Informatiebeheer en [gegevensretentie,](../compliance/manage-information-governance.md) verwijdering en vernietiging beheren [in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)om te beginnen.

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Planningen voor het bewaren van gegevens ontwikkelen voor containers, e-mail en inhoud

Houd het volgende in gedachten:

- Het opstellen van een planning voor het bewaren van gegevens voor gedefinieerde informatietypen moet worden beschouwd als een vereiste voor het implementeren van een bewaar- of verwijderingsschema.

- Gezien het aantal informatietypen dat de meeste organisaties belangrijk vinden en de bijbehorende grote bewaarschema's voor records die daarbij horen, is het implementeren van een strategie voor gegevensretentie en recordbeheer planning vereist. 

- De sleutel tot het tot stand brengen van een effectieve strategie voor gegevensbeheer van dit type is de focus op de hoogste prioriteit voor zakelijke functies en informatietypen waarvoor een formeler beheer vereist is. Voorbeelden hiervan zijn juridische contracten, financiële overzichten en documentatie over naleving van regelgeving. Vermijd een afzonderlijk bewaarschema voor elk gegevenstype. Probeer algemene categorieën zo veel mogelijk te gebruiken, bijvoorbeeld met bewaarschema's van 7 jaar voor algemene zakelijke inhoud.

- Zodra de typen persoonlijke gegevens in uw omgeving beter bekend zijn, stelt u bewaar- en verwijderingsschema's in voor dit type inhoud en past u uw informatiearchitectuur aan om het beheer van dit soort informatie te vereenvoudigen. U kunt bijvoorbeeld persoonlijke gegevens isoleren in afzonderlijke sites, bibliotheken of mappen met gecontroleerde toegang.

### <a name="retention-policies-and-retention-labels"></a>Bewaarbeleid en retentielabels

Gebruik [bewaarbeleid en bewaarlabels om](../compliance/retention.md) inhoud in Microsoft 365 te behouden of te verwijderen die persoonlijke gegevens bevat of naar verwachting bevat.

### <a name="records-management"></a>Records Management

Gebruik bewaarlabels die inhoud als record declareeren om een [recordbeheeroplossing](../compliance/records-management.md) voor gegevens in Microsoft 365 te implementeren.

Voor gegevensbescherming worden verzoeken van gegevensonderwerpen (DSR's) die door de juridische afdeling zijn ontvangen, als record gedeclareerd en kunnen ze voor onbepaalde tijd worden opgeslagen of met bewijs worden verwijderd, om te voldoen aan de bewaarspecificaties voor regelgevingsactiviteit.