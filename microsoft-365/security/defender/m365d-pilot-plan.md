---
title: Uw pilot-Microsoft 365 Defender-project plannen
description: Plan uw pilot Microsoft 365 Defender-project met belanghebbenden om verwachtingen te beheren en een succesvol resultaat te garanderen.
keywords: Microsoft 365 Defender pilot, plan pilot Microsoft 365 Defender project, evaluate Microsoft 365 Defender in production, Microsoft 365 Defender pilot project, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 98f0c91a51cc2b73cc26e6fb53143a417a7a147e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932545"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Uw pilot-Microsoft 365 Defender-project plannen 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

|![Planning](../../media/phase-diagrams/1-planning.png)<br/>Planning|[![Voorbereiden](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[Voorbereiding](prepare-m365d-eval.md) | [![Een aanval simuleren](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[Een aanval simuleren](m365d-pilot-simulate.md) | [![Sluiten en samenvatten](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[Sluiten en samenvatten](m365d-pilot-close.md)|
|--|--|--|--|
|*U bent er!*| | | |

U bent momenteel bezig met de planningsfase.

Om ervoor te zorgen dat uw pilotproject een succes is, is het essentieel om in het begin grondig te plannen met uw belanghebbenden en goedkeuringen te krijgen. Elementen van planning zijn onder andere het identificeren van bereik, gebruiksgevallen, vereisten en succescriteria.

In deze handleiding wordt u begeleid bij het plannen van uw pilotproject. 

>[!IMPORTANT]
>Volg de testinstructies zo nauwkeurig mogelijk voor optimale resultaten.


## <a name="scope"></a>Bereik

Het bereik van de pilot bepaalt hoe breed de test zal zijn, op basis van uw omgeving en acceptabele testmethoden. Hier volgen enkele voorbeeldbereiken om rekening mee te houden:
- Ontwikkel- of testomgeving met eindpunten, servers, domeincontrollers.
- Productieomgeving met Microsoft 365, Azure, Active Directory-services, eindpunten en servers

>[!NOTE]
>Als u nog niet over de volledige licenties hebt, kunt u proeflicenties krijgen om [Microsoft 365 Defender te evalueren:](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) plannen, voorbereiden, instellen, configureren en uitvoeren van uw pilotproject. Uw belanghebbenden spelen een grote rol bij het vergemakkelijken van het proces van begin tot einde.

De typen besturingssystemen die moeten worden geëvalueerd, moeten ook worden gedefinieerd op basis van de organisatiestructuur. Dit kan het volgende zijn: [Mac-eindpunten,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements) [Linux-servers,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements) [Windows 10 eindpunten,](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions) [Windows Server 2016.](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)

## <a name="use-cases"></a>Gebruik cases

Use cases represent statements of how the tool being test is meant to be consumed by its intended users. Deze kunnen worden geformuleerd als gebruikersverhalen vanuit het oogpunt van een bepaalde persoon, zoals een SOC-analist. Bijvoorbeeld:
- Als soc-analist moet ik waarschuwingen en gebeurtenissen op apparaten, gebruikers en postvakken in mijn netwerk bekijken, correleren, beoordelen en beheren. [Incident management]
- Als soc-analist moet ik de functie en het proces hebben om schadelijke gebeurtenissen in mijn netwerk automatisch te onderzoeken en te beantwoorden. [Auto IR]
- Als soc-analist moet ik gegevens uit mijn omgeving doorzoeken om bekende en potentiële bedreigingen en verdachte activiteiten te vinden. [Advanced Hunting]

Houd er rekening mee dat deze gebruiksgevallen moeten worden gemaakt binnen de parameters van het gedefinieerde bereik. Als het testbereik bijvoorbeeld geen evaluatie bevat van hulpprogramma's zoals Microsoft Cloud App Security, moet u geen gevallen gebruiken die hiervan afhankelijk zijn als gegevensbron.

## <a name="requirements"></a>Vereisten

In de lijst met gebruiksgevallen kunt u beginnen met het maken van vereisten. Vereisten omvatten functies die een hulpmiddel moet hebben om aan de gebruiksgevallen te voldoen. Deze vereisten kunnen worden onderverdeeld in categorieën zoals configuratie en onderhoud, ondersteuning voor integraties en functiespecifieke vereisten, zoals de mogelijkheid om te jagen en de mogelijkheid om aangepaste waarschuwingen te maken.

## <a name="test-plan"></a>Testplan

Afhankelijk van de vereisten kunnen verschillende testmethoden geschikt zijn. Als de vereiste bijvoorbeeld is om de effectiviteit van geautomatiseerde herstel te evalueren, moet het testplan stappen bevatten om het gedrag(en) te genereren dat een geautomatiseerde herstelactie binnen Microsoft 365 Defender zou veroorzaken. Als de vereiste is om een bepaald gedrag of een bepaalde aanval te detecteren, kan de test meer stappen omvatten. Het punt is om een plan te hebben om nauwkeurig te testen op uw vereisten.

## <a name="success-criteria"></a>Succescriteria

Succescriteria is uiteindelijk de balk die is ingesteld voor het meten van wat u aan het testen bent. Of u nu Microsoft 365 Defender (of een andere technologie) test op andere hulpmiddelen of op zichzelf, er moeten enkele meetbare criteria zijn om de waarde te bepalen die het hulpprogramma biedt. Op basis van het bereik, de vereisten en het testplan bepalen de succescriteria hoe de test moet worden beoordeeld. Dit moet minder een pass of fail zijn en meer een gewogen score op basis van uw behoeften. Als u bijvoorbeeld wilt slagen, moet een hulpmiddel mogelijk boven de 80% scoren in bepaalde kritieke gebieden die u identificeert.

## <a name="scorecard"></a>Scorecard

U kunt alle elementen van uw plan samenbrengen door een scorecard te maken. Zie hieronder een voorbeeldscorecard:

| Use case | Vereisten | Configuratievereisten | Testplan | Verwachte uitkomst | Teststatus | Score | Opmerkingen |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Incidentbeheer|- Microsoft 365 Defender  </br></br>- Microsoft Defender voor identiteit </br></br>- Microsoft Defender voor Eindpunt </br></br>- Microsoft Cloud App Security (optioneel)|Bekijk de [vereisten voor voorbereiding,](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) configuratie en configuratie voor meer informatie |[Een aanval simuleren](m365d-pilot-simulate.md) <br></br>[Het incident onderzoeken](./m365d-pilot-simulate.md#investigate-an-incident) |De onderzoeker kan het bereik en de impact van het incident begrijpen en het incident beheren||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender voor identiteit </br></br>- Microsoft Defender voor Eindpunt |Bekijk de [vereisten voor voorbereiding,](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) configuratie en configuratie voor meer informatie <br>AutoIR inschakelen  |[Een aanval simuleren](m365d-pilot-simulate.md) <br></br>[Geautomatiseerd onderzoek](m365d-pilot-simulate.md#automated-investigation-and-remediation) |Waarschuwingen en incidenten worden automatisch door de Defender Microsoft 365 worden||||
|Geavanceerd opsporen|- Microsoft 365 Defender </br></br>- Microsoft Defender voor Eindpunt </br></br>-Microsoft Defender voor Office 365 |Bekijk de [vereisten voor voorbereiding,](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) configuratie en configuratie voor meer informatie|[Scenario voor geavanceerd jagen](./m365d-pilot-simulate.md#advanced-hunting-scenario) |Speurders kunnen gegevens vinden door middel van geavanceerd zoeken, draaien naar beïnvloede entiteiten en door aangepaste detecties te maken||||



## <a name="next-step"></a>Volgende stap
|![Voorbereidingsfase](../../media/mtp/prep.png) <br>[Voorbereidingsfase](prepare-m365d-eval.md) | Uw testomgeving Microsoft 365 Defender voorbereiden
|:-------|:-----|
