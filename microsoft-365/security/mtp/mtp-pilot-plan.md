---
title: Uw testfase Microsoft 365 Defender-project plannen
description: Plan uw pilot Microsoft 365 Defender-project met belanghebbenden om de verwachtingen te beheren en te zorgen voor een succesvol resultaat.
keywords: Microsoft Threat Protection-pilot, plan pilot Microsoft Threat Protection-project, evalueer Microsoft Threat Protection in productie, Microsoft Threat Protection pilotproject, cyberbeveiliging, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8037b71fc41fb7fb0bdbfc829bad2ece1de6849b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930172"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Uw testfase Microsoft 365 Defender-project plannen 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

|![Planning](../../media/phase-diagrams/1-planning.png)<br/>Planning|[![Voorbereiden](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[Voorbereiding](prepare-mtpeval.md) | [![Een aanval simuleren](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[Een aanval simuleren](mtp-pilot-simulate.md) | [![Sluiten en samenvatten](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[Sluiten en samenvatten](mtp-pilot-close.md)|
|--|--|--|--|
|*U bent hier!*| | | |

U bent nu in de planningsfase.

Om ervoor te zorgen dat uw pilot een succes wordt, is het essentieel om in het begin grondig te plannen en goedkeuring van uw belanghebbenden te krijgen. Planningelementen zijn onder andere het identificeren van een bereik, use cases, vereisten en criteria voor succes.

In deze handleiding wordt u begeleid bij het plannen van uw pilotproject. 

>[!IMPORTANT]
>Voor optimale resultaten volgt u de instructies van de testfase zo goed mogelijk.


## <a name="scope"></a>Bereik

Het bereik van de test bepaalt hoe ruim de test zal zijn, op basis van uw omgeving en acceptabele testmethoden. Hier volgen enkele voorbeeldbereiken om rekening mee te houden:
- Ontwikkel- of testomgeving met eindpunten, servers en domeincontrollers.
- Productieomgeving met Microsoft 365, Azure, Active Directory-services, eindpunten en servers

>[!NOTE]
>Als u nog niet de volledige licenties hebt, kunt u proeflicenties krijgen om [Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) te evalueren: plannen, voorbereiden, instellen, configureren en uitvoeren van uw pilotproject. Uw belanghebbenden spelen een grote rol bij het vergemakkelijken van het proces van begin tot einde.

De typen besturingssystemen die moeten worden geëvalueerd, moeten ook worden gedefinieerd op basis van het organisatorische werk. Dit kunnen de volgende zijn: [Mac-eindpunten,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements) [Linux-servers,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements) [Windows 10-eindpunten,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions) [Windows Server 2016.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)

## <a name="use-cases"></a>Use cases

Use cases zijn instructies over de manier waarop het testhulpmiddel bedoeld is om te worden gebruikt door de beoogde gebruikers. Deze kunnen worden formuleren als gebruikersverhalen vanuit het oogpunt van een bepaalde persona, zoals een SOC-analist. Bijvoorbeeld:
- Als SOC-analist moet ik waarschuwingen en gebeurtenissen op apparaten, gebruikers en postvakken in mijn netwerk bekijken, correleren, beoordelen en beheren. [Incidentbeheer]
- Als SOC-analist heb ik het hulpprogramma en het proces nodig om schadelijke gebeurtenissen in mijn netwerk automatisch te onderzoeken en te beantwoorden. [Auto-IR]
- Als SOC-analist moet ik gegevens uit mijn omgeving doorzoeken om bekende en potentiële bedreigingen en verdachte activiteiten te vinden. [Geavanceerd zoeken]

Houd er rekening mee dat deze use cases moeten worden gemaakt binnen de parameters van het gedefinieerde bereik. Als het testbereik bijvoorbeeld geen evaluatie van hulpprogramma's bevat, zoals Microsoft Cloud App-beveiliging, moeten de gevallen die hiervan afhankelijk zijn als gegevensbron niet worden gemaakt.

## <a name="requirements"></a>Vereisten

In de lijst met use cases kunt u beginnen met het maken van vereisten. Vereisten omvatten functies die een hulpmiddel moet hebben om te voldoen aan de use cases. Deze vereisten kunnen worden onderverdeeld in categorieën, zoals configuratie en onderhoud, ondersteuning voor integraties en functiespecifieke vereisten, zoals het zoeken naar mogelijkheden en de mogelijkheid om aangepaste waarschuwingen te maken.

## <a name="test-plan"></a>Testplan

Afhankelijk van de vereisten zijn verschillende testmethoden mogelijk geschikt. Als de vereiste bijvoorbeeld is om het probleem van Geautomatiseerde herstel te evalueren, moet het testplan stappen bevatten om het gedrag(s) te genereren dat een automatische herstelactie in Microsoft 365 Defender zou activeren. Als de vereiste is om een bepaald gedrag of een specifieke aanval te detecteren, zijn er mogelijk meer stappen nodig voor de test. Het is de bedoeling dat u een plan hebt om nauwkeurig te kunnen testen op uw vereisten.

## <a name="success-criteria"></a>Criteria voor succes

Criteria voor succes zijn uiteindelijk de balk die is ingesteld om te meten met wat u aan het testen bent. Ongeacht of u Microsoft 365 Defender (of een andere technologie daarvoor) test met andere hulpprogramma's of op zichzelf, er moeten enkele meetbare criteria zijn om de waarde te bepalen die het hulpprogramma biedt. Op basis van het bereik, de vereisten en het testplan wordt aan de hand van de criteria bepaald hoe de toets moet worden beoordeeld. Dit zou minder moeten zijn dan een wachtwoord of moet mislukken en meer een gewogen score op basis van uw behoeften. Als u bijvoorbeeld succesvol wilt zijn, moet een hulpprogramma mogelijk hoger zijn dan 80% op bepaalde kritieke gebieden die u identificeert.

## <a name="scorecard"></a>Scorecard

U kunt alle elementen van uw plan onder andere samenbrengen door een scorecard te maken. Zie een voorbeeldscorecard hieronder:

| Use case | Vereisten | Configuratievereisten | Testplan | Verwacht resultaat | Teststatus | Score | Opmerkingen |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Incidentbeheer|- Microsoft 365 Defender  </br></br>- Microsoft Defender voor identiteit </br></br>- Microsoft Defender voor eindpunt </br></br>- Microsoft Cloud-app-beveiliging (optioneel)|Zie de [vereisten voor](https://aka.ms/mtp-trial-lab) voorbereiding, configuratie en configuratie voor meer informatie |[Een aanval simuleren](mtp-pilot-simulate.md) <br></br>[Het incident onderzoeken](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |Mensen kunnen het bereik en de invloed van het incident begrijpen en het incident beheren||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender voor identiteit </br></br>- Microsoft Defender voor eindpunt |Zie de [vereisten voor](https://aka.ms/mtp-trial-lab) voorbereiding, configuratie en configuratie voor meer informatie <br>AutoIR inschakelen  |[Een aanval simuleren](mtp-pilot-simulate.md) <br></br>[Geautomatiseerd onderzoek](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#automated-investigation-and-remediation) |Waarschuwingen en incidenten worden automatisch verhelpen door Microsoft 365 Defender||||
|Geavanceerd opsporen|- Microsoft 365 Defender </br></br>- Microsoft Defender voor eindpunt </br></br>-Microsoft Defender voor Office 365 |Zie de [vereisten voor](https://aka.ms/mtp-trial-lab) voorbereiding, configuratie en configuratie voor meer informatie|[Scenario geavanceerd zoeken](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#advanced-hunting-scenario) |Met behulp van geavanceerd zoeken, draaien naar beïnvloede entiteiten en door aangepaste detecties te maken, kunnen ze gegevens vinden.||||



## <a name="next-step"></a>Volgende stap
|![Voorbereidingsfase](../../media/mtp/prep.png) <br>[Voorbereidingsfase](prepare-mtpeval.md) | Uw Microsoft 365 Defender-testomgeving voorbereiden
|:-------|:-----|
