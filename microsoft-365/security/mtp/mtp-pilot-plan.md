---
title: Uw proefproject voor Microsoft Threat Protection plannen
description: Plan uw pilot Microsoft Threat Protection-project met belanghebbenden voor het beheren van de verwachtingen en zorg voor een succesvolle uitslag.
keywords: Proefversie van Microsoft Threat Protection, proefabonnement Microsoft Threat Protection, Microsoft Threat Protection evalueren in productie, Microsoft Threat Protection pilotproject, Cyber beveiliging, Geavanceerd permanent risico, beveiliging van uw bedrijf, apparatuur, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerde jacht
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 601e81fc5265fe2ec5f41009b6c4fa43c0c8233d
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962607"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a>Uw proefproject voor Microsoft Threat Protection plannen 

**Van toepassing op:**
- Microsoft Threat Protection

Om ervoor te zorgen dat uw pilotproject een gunstige uitkomst is, is het van essentieel belang dat u de belanghebbenden snel goed keurt en goedkeuring van uw belanghebbenden ontvangt. De planning van elementen bevat identificatie bereik, gebruiks kwesties, vereisten en succescriteria. 

Deze handleiding helpt u bij het plannen van uw pilotproject. 

>[!IMPORTANT]
>Volg voor optimale resultaten de instructies voor het testen.


## <a name="scope"></a>Scoop

Het bereik van de leider bepaalt hoe breed de test is, op basis van uw omgeving en de acceptabele testmethoden. Hier volgen enkele voorbeelden van aandachtspunten:
- Ontwikkelings-of testomgeving, waaronder eindpunten, servers, domeincontrollers.
- Productieomgeving met Microsoft 365, azure, Active Directory Services, eindpunten en servers

>[!NOTE]
>Als u de volledige licentie nog niet hebt, kunt u een proefabonnement krijgen voor het [evalueren van Microsoft Threat Protection (Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) plannen, voorbereiden, instellen, configureren en uitvoeren van uw pilotproject). De belanghebbenden kunnen een belangrijke rol spelen, zodat de procedure van begin tot eind wordt vergemakkelijkt.

De typen besturingssystemen die moeten worden geëvalueerd, worden ook gedefinieerd op basis van de organisatie-Makeup. Dit kan de volgende bebestaan: [Mac-eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux-servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10-eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Gebruik zaken

Use-cases stellen de manier weer waarop het te testen instrument wordt gebruikt door de bedoelde gebruikers. Deze kunnen worden geformuleerd als gebruikers verhalen vanuit het oogpunt van een bepaalde persoon, zoals een SOC-analist. Bijvoorbeeld:
- Als SOC-analist moet ik waarschuwingen en gebeurtenissen op alle apparaten, gebruikers en postvakken in mijn netwerk weergeven, correleren, beoordelen, beoordelen en beheren. [Incidentenbeheer]
- Als SOC-Analyst moet ik het hulpmiddel en het proces voor het automatisch onderzoeken en beantwoorden van schadelijke gebeurtenissen in mijn netwerk hebben. [Automatische IR]
- Als SOC-analist moet ik de gegevens van mijn omgeving doorzoeken om bekende, potentiële bedreigingen en verdachte activiteiten te vinden. [Geavanceerde jacht]

Houd er rekening mee dat het gebruik van dit soort aanvragen binnen de parameters van het gedefinieerde bereik moet worden gemaakt. Als u bijvoorbeeld het test bereik omvat, is het niet mogelijk om een evaluatie te maken van hulpmiddelen zoals beveiliging van de Cloud-app van Microsoft.

## <a name="requirements"></a>Vereisten

Vanuit de lijst met begebruikte zaken, kunt u beginnen met het maken van vereisten. Voor de vereisten behoren functies een programma dient te voldoen aan de use cases. Deze vereisten kunnen worden opgesplitst in categorieën zoals configuratie en onderhoud, ondersteuning voor integraties en functie-specifieke vereisten, zoals de ondersteuning van de jacht en de mogelijkheid om aangepaste waarschuwingen te maken.

## <a name="test-plan"></a>Test plan

Afhankelijk van de vereisten, is het mogelijk dat er verschillende testmethoden geschikt zijn. Als u bijvoorbeeld de effectiviteit van geautomatiseerde herbemiddeling evalueert, moet het testplan stappen opnemen om de gedrag (en) te genereren waarmee een geautomatiseerde herstelactie binnen Microsoft Threat Protection werd geactiveerd. Als u een bepaald gedrag of een bepaalde aanval moet detecteren, dan kan de test meer stappen veroorzaken. U kunt het beste een plan op basis van de vereisten nauwkeurig testen.

## <a name="success-criteria"></a>Criteria voor succes

De criteria voor succes zijn uiteindelijk de balk die is ingesteld voor de waardering van wat u wilt testen. Of u nu Microsoft Threat Protection (of andere hulpmiddelen voor die materie) tegen andere hulpmiddelen of op een andere manier test, moet u een aantal meetbaarste criteria gebruiken om de waarde van het hulpmiddel te bepalen. Afhankelijk van de vereisten voor het bereik, de vereisten en het testen van het plan, wordt het resultaat van de test bepaald. Dit kan minder of niet meer zijn, en ook een gewogen score op basis van uw behoeften. Als u bijvoorbeeld een succesvolle aanduiding wilt hebben, moet een hulpmiddel mogelijk een Score van 80% hebben in bepaalde kritieke gebieden die u identificeert.

## <a name="scorecard"></a>Werd

U kunt ook een scorecard maken om alle elementen van uw plan bijeen te brengen. Hieronder ziet u een voorbeeld van een Scorecard:

|**Use-case**|**Vereisten**|**Configuratievereisten**|**Test plan**|**Verwacht resultaat**|**Status testen**|**Score**|**Opmerkingen**|
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Incidentenbeheer|-Microsoft Threat Protection </br></br>-Azure ATP </br></br>-Microsoft Defender ATP </br></br>-Beveiliging van Microsoft Cloud-app (optioneel)|Zie de [vereisten](https://aka.ms/mtp-trial-lab) voor voorbereiden voor voorbereiden, instellen en configureren voor meer informatie |[Aanval simuleren](mtp-pilot-simulate.md) <br></br>[Het incident onderzoeken](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#investigate-an-incident) |Onderzoekers kunnen inzicht krijgen in de reikwijdte en impact van het incident en het incident beheren||||
|AutoIR|-Microsoft Threat Protection </br></br>-Azure ATP </br></br>-Microsoft Defender ATP |Zie de [vereisten](https://aka.ms/mtp-trial-lab) voor voorbereiden voor voorbereiden, instellen en configureren voor meer informatie <br>AutoIR inschakelen  |[Aanval simuleren](mtp-pilot-simulate.md) <br></br>[Automatisch onderzoek](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |Waarschuwingen en incidenten worden automatisch doorgevoerd door Microsoft Threat Protection||||
|Geavanceerd opsporen|-Microsoft Threat Protection </br></br>-Microsoft Defender ATP </br></br>-Office 365 ATP   |Zie de [vereisten](https://aka.ms/mtp-trial-lab) voor voorbereiden voor voorbereiden, instellen en configureren voor meer informatie|[Scenario voor Geavanceerd jacht](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |Onderzoekers kunnen gegevens vinden via Geavanceerd jacht, draaien naar beïnvloede entiteiten en aangepaste detecties maken||||



## <a name="next-step"></a>Volgende stap
|![Voorbereidende fase](../../media/prepare.png) <br>[Voorbereidende fase](prepare-mtpeval.md) | Uw testomgeving voor Microsoft Threat Protection voorbereiden
|:-------|:-----|
