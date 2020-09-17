---
title: Bepalen welke informatie onderworpen is aan de regelgeving voor data privacy
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
description: U kunt de Microsoft 365-Bewaar labels en-beleidsregels gebruiken voor het beheren van persoonlijke gegevens in uw Microsoft 365-omgeving.
ms.openlocfilehash: 766995b9c758d4ae8cbf7140fb259d208cfb7771
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949250"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Bepalen welke informatie onderworpen is aan de regelgeving voor data privacy

De beheerfuncties voor informatiebeheer kunnen in uw omgeving worden gebruikt om gegevens aan te vullen ter informatie, waaronder een nummer dat specifiek bedoeld is voor de algemene verordening gegevensbescherming (AVG), HIPAA-HITECH (de Amerikaanse gezondheids verzorging van de gezondheids verzorging), Californië voor consumentenbescherming (CCPA) en de wet Data Protection Act (LGPD). 

De volgende besturingselementen zijn in eerste instantie ingedeeld in de volgende oplossings gebieden:

- Bewaarbeleid
- Bewaarlabels
- Records Management

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Voorschriften voor de privacy van gegevensbeheer

Hieronder ziet u een voorbeeld van een lijst met voorschriften voor de privacy van gegevens die in verband met informatiebeheer kunnen worden beheerd:

- AVG artikel (13) (2) (a)
- AVG artikel (5) (1) (f)
- HIPAA-HITECH (45 CFR 164.312 (c) (2))
- HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))
- HIPAA-HITECH (45 CFR 164.316 (b) (1) (II))
- LGPD artikel 46

Zie voor meer informatie over deze voorschriften het [artikel privacyinstellingen voor gegevens en identificeren van gevoelige informatie](information-protection-deploy-assess.md).

Voor informatiebeheer: voor informatiebeheer worden meestal de volgende gegevens verzameld:

- U dient een technisch stelsel te gebruiken voor bewaren en verwijderen van persoonlijke gegevens die zijn opgeslagen in Microsoft 365.
- Als u persoonlijke gegevens wilt opslaan, kunt u het onderwerp van de hoeveelheid werk dat de gegevens bevat, op de front-endwebservers toepassen.
- Persoonlijke gegevens moeten tegen onbedoelde verwerking, verlies of wijziging via verifieerbare methoden beschermd worden.
- Elke actie die wordt uitgevoerd met persoonlijke gegevens moet worden gedocumenteerd en de documentatie moet worden bewaard gedurende een bepaalde periode.

Aangezien de regelgeving voor gegevensbescherming niet zeer specifiek is voor het bewaren en verwijderen van gegevens, moeten andere factoren in rekening worden gebracht waarbij informatie over de beleidsregels voor informatiebeheer voor persoonlijke gegevens die zijn opgeslagen in uw abonnement op Microsoft 365, kunnen worden gedicteerd. Hier volgen enkele voorbeelden:

- Verouderde consumenten accounts na 5 jaar inactiviteit en vereist het verwijderen of anonimiseren van rekeninggegevens na dit punt, waarbij de gegevens en werkstromen die zijn gekoppeld aan meldingen en andere automatisering, worden opgeslagen.
- Het instellen van regels voor het behoud van beleid en procedures met betrekking tot AVG rond drie jaar nadat deze zijn vervangen, wat is uitgelijnd met het bewaarschema van de organisatie voor beleidsregels en procedures.
- Het onderhouden van een apart abonnement voor het communiceren met consumenten via zijn ondersteunings organisatie. Alle e-mailberichten werden na twee weken bewaard en verwijderd om de privacy van buildup in het systeem te verminderen.

U kunt op de volgende belangrijke vragen beantwoorden: 

- Hoelang is informatie die persoonlijke gegevens bevat, moet worden bewaard voor geldige zakelijke redenen om te voorkomen dat u de functie permanent houdt. Dit moet evenwichtig zijn met de Bewaar behoeften voor bedrijfscontinuïteit.

Ongeacht de juridische en zakelijke redenen voor het behoud van persoonlijke gegevens rond of te verwijderen, biedt Microsoft een aantal mogelijkheden om uw gegevensbeheer schema te implementeren in Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Information governance beheren in Microsoft 365

Zie [Gegevensbeheer](../compliance/manage-information-governance.md) en [gegevens behoud, verwijdering en vernietiging beheren in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)als u wilt beginnen.

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Schema voor het bewaren van gegevens voor containers, e-mail en inhoud ontwikkelen

Houd het volgende in gedachten:

- Het maken van een bewaarschema voor gegevens voor gedefinieerde gegevenstypen moet als vereiste gelden voor het implementeren van een bewaarschema of een verwijderings schema.

- Op basis van het aantal gegevenstypen dat de meeste organisaties belangrijk achten en de bijbehorende bewaarschema's voor uitgebreide records die samen met hen doen, moet u de plannings-en beheer strategie voor gegevens en recordbeheer implementeren. 

- De sleutel voor het opzetten van een effectieve strategie voor gegevensbeheer van dit type is de nadruk op de zakelijke functies met de hoogste prioriteit, en gegevenstypen die een formeler beheer vereisen. Voorbeelden hiervan zijn juridische contracten, financiële overzichten en documentatie over regelgevings naleving. U kunt voorkomen dat er een apart Bewaarschema voor elk afzonderlijk gegevenstype wordt weergeven. U kunt zo veel mogelijk algemene categorieën gebruiken, bijvoorbeeld met bewaarschema's van 7 jaar voor algemene bedrijfs inhoud.

- Wanneer de typen persoonlijke gegevens in uw omgeving beter bekend zijn, kunt u schema's voor het bewaren en verwijderen van bestanden vastleggen, en de informatiearchitectuur aanpassen om het beheer van deze gegevens te vereenvoudigen. U kunt bijvoorbeeld persoonlijke gegevens op afzonderlijke sites, bibliotheken of mappen isoleren met Controlled Access.

### <a name="retention-policies-and-retention-labels"></a>Bewaarbeleid en labels voor bewaarbeleid

Gebruik [bewaarbeleid en labels voor bewaarbeleid](../compliance/retention.md) om inhoud te behouden of te verwijderen in microsoft 365 met of naar verwachting om persoonlijke gegevens te bevatten.

### <a name="records-management"></a>Records Management

Labels voor bewaarbeleid gebruiken waarmee inhoud een record wordt gedeclareerd om een [oplossing voor recordbeheer](../compliance/records-management.md) voor gegevens te implementeren in microsoft 365.

Voor de privacy van gegevens (DSRs) die door de juridische afdeling worden ontvangen, wordt een record gedeclareerd en kan hij voor het behoud van het behoud van de regelgeving voorbehoud van de regelgeving van de juridische afdeling een record indienen.

