---
title: Strategieën voor de implementatie van de basisinfrastructuur van Microsoft 365 voor Enterprise
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Ontdek enkele manieren waarop u de fasen van de basisinfrastructuur voor Microsoft 365 voor ondernemingen kunt implementeren.
ms.openlocfilehash: 765bba743485c13c65cd6377abe01f80f2df4c23
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811298"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-deployment-strategies"></a>Strategieën voor de implementatie van de basisinfrastructuur van Microsoft 365 voor Enterprise

Er zijn veel manieren waarop u de fasen van de [basisinfrastructuur](deploy-foundation-infrastructure.md) van Microsoft 365 voor ondernemingen kunt implementeren en de mogelijkheden, software en services voor uw gebruikers kunt uitrollen. De implementatie kan groot en complex zijn, afhankelijk van de grootte van uw organisatie en de bestaande infrastructuur. Om u op weg te helpen met het projectbeheer kunt u de volgende implementatiestrategieën overwegen:

- Seriële implementatie
- Parallelle implementatie met niet-overlappende implementatie van gebruikers
- Parallelle implementatie met overlappende implementatie van gebruikers
- Up-front infrastructuur en uitrol van de end-to-end configuratie

Gebruik deze strategieën voor ideeën over hoe u het totale project kunt beheren en sneller de zakelijke voordelen van Microsoft 365 voor ondernemingen kunt realiseren.

>[!Note]
>Dit artikel bevat veronderstellingen en vereenvoudigingen zodat de implementatiestrategieën op consistente wijze kunnen worden beschreven. Deze implementatiestrategieën zijn algemeen van aard en zijn niet bedoeld als specifiek tijdsbestek, noch zijn ze bedoeld voor alle organisaties en situaties.
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a>Elementen van IT-projectbeheer voor typische ondernemingen

De IT-infrastructuur omvat zowel backend-services als de implementatie van nieuwe of verbeterde mogelijkheden, of geïnstalleerde software voor eindgebruikers. IT-afdelingen implementeren meestal elementen van een IT-infrastructuur op een methodische wijze. Een van de manieren waarop een element van de IT-infrastructuur succesvol kan worden geïmplementeerd, bestaat uit:

- Een proefimplementatie 

  Dit omvat initiële infrastructuurconfiguratie en uitrol naar een proefset van gebruikers, testen en daaropvolgende aanpassingen aan de infrastructuurconfiguratie.

- Een gebruikersimplementatie

  Dit omvat de uitrol naar de rest van uw organisatie op basis van regio's, afdelingen, groepen of andere soorten systematische verspreiding van de configuratie of software.

De gebruikers in de proefimplementatie zijn niet hetzelfde als die in de gebruikersimplementatie.

In dit artikel worden de volgende afbeeldingen gebruikt om deze definities weer te geven: 

![De grafische weergave van de definities van prototype- en gebruikersimplementatie](../media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

De arcering van de afbeelding voor de gebruikersimplementatie geeft het percentage binnen uw organisatie aan van 0% tot 100% bij een gestructureerde of methodische aanpak, zoals groepen, afdelingen of regio's.

## <a name="deployment-strategies"></a>Implementatiestrategieën

Overweeg met de volgende implementatiestrategieën:

- Seriële implementatie
- Parallelle implementatie met niet-overlappende implementatie van gebruikers
- Parallelle implementatie met overlappende implementatie van gebruikers
- Up-front infrastructuur en uitrol van de end-to-end configuratie

### <a name="serial-deployment"></a>Seriële implementatie

Met een seriële implementatie kunt u een fase volledig uitrollen, waardoor de fase 100% kan worden voltooid voor al uw gebruikers, voordat u naar de volgende stap gaat. Hier zijn enkele redenen waarom u op deze manier zou kunnen implementeren:

- Risicobeperking
- Resourcing-beperkingen
- Financieringscycli van de IT-afdeling
- Afhankelijkheden van IT-technologie
- Beheer van bedrijfsveranderingen en weerstand van eindgebruikers

Dit Gantt-diagram toont een vereenvoudigde seriële implementatie van fasen 2-6 van de basisinfrastructuur voor Microsoft 365 voor ondernemingen.

![De seriële implementatie van fasen 2-6 van de Foundation-infrastructuur](../media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
Om de discussie en het voorbeeld te vereenvoudigen, wordt aangenomen dat elke fase en implementatiesegment binnen elke fase evenveel tijd in beslag nemen.

>[!Note]
>Fase 1: netwerken van de basisinfrastructuur voor Microsoft 365 voor ondernemingen is een fase specifiek voor IT-afdelingen. Gebruikers profiteren van de voordelen van geoptimaliseerde connectiviteit met de cloudbronnen van Microsoft, maar hen wordt niet opgelegd dit na te streven.
>

Dit is een vereenvoudigde gebruikerservaring voor prototypen als voorbeeld:

- In december moet ik mijn smartphone voor MFA gaan gebruiken. (Identiteit)
- In maart wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop. (Windows 10 Enterprise)
- In juni wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013. (Office 365 ProPlus)
- In september worden de apparaatimplementatie en het app- en apparaatbeleid toegepast. (Mobile device management)
- In december wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten. (Informatiebescherming)

Het resultaat is een frequentie van 90 dagen tussen opeenvolgende proefimplementaties.

Hieronder ziet u een vereenvoudigde ervaring voor de eindgebruiker als voorbeeld:

- In januari moet ik mijn smartphone voor MFA gaan gebruiken. (Identiteit)
- In april wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop. (Windows 10 Enterprise)
- In juli wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013. (Office 365 ProPlus)
- In oktober worden de apparaatimplementatie en het app- en apparaatbeleid toegepast. (Mobile device management)
- In januari van het volgend jaar wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten. (Informatiebescherming)

Het resultaat is een frequentie van 90 dagen tussen opeenvolgende gebruikersimplementaties.

Het nadeel van deze implementatiestrategie is dat het lang kan duren voordat de basisinfrastructuur van Microsoft 365 voor ondernemingen volledig is geïmplementeerd.

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a>Parallelle implementatie met niet-overlappende implementatie van gebruikers (parallel 1)

Voor deze implementatiestrategie start u de proefimplementatie van de volgende fase tijdens het laatste deel van de gebruikersimplementatie van de huidige fase.
Hier is de implementatie van fase 2-6 wanneer de proefimplementatie plaatsvindt terwijl de implementatie van de gebruiker van de vorige fase wordt afgerond.

![De parallelle implementatie van fasen 2-6 met niet-overlappende gebruikersimplementatie](../media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
Het eindresultaat is dat de gebruikersimplementatie voor de huidige fase in uw hele organisatie is voltooid voordat de volgende begint. Gebruikers die niet deelnemen aan proefimplementaties hebben niet te maken met de implementatie van meerdere fasen tegelijk, maar proefimplementaties worden parallel uitgevoerd met gebruikersimplementaties.

Dit is een vereenvoudigde gebruikerservaring voor prototypen als voorbeeld:

- In december moet ik mijn smartphone voor MFA gaan gebruiken. (Identiteit)
- In februari wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop. (Windows 10 Enterprise)
- In april wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013. (Office 365 ProPlus)
- In juni worden de apparaatimplementatie en het app- en apparaatbeleid toegepast. (Mobile device management)
- In augustus wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten. (Informatiebescherming)

Het resultaat is een frequentie van 60 dagen tussen opeenvolgende proefimplementaties.

Hieronder ziet u een vereenvoudigde ervaring voor de eindgebruiker als voorbeeld:

- In januari moet ik mijn smartphone voor MFA gaan gebruiken. (Identiteit)
- In maart wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop. (Windows 10 Enterprise)
- In mei wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013. (Office 365 ProPlus)
- In juli worden de apparaatimplementatie en het app- en apparaatbeleid toegepast. (Mobile device management)
- In september wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten. (Informatiebescherming)

Het resultaat is een frequentie van 60 dagen tussen opeenvolgende gebruikersimplementaties.

Het voordeel van deze implementatiestrategie is dat het minder tijd kost om de basisinfrastructuur van Microsoft 365 voor ondernemingen volledig te implementeren, zonder dat uw IT-afdeling en gebruikers tegelijkertijd met meerdere implementaties te maken krijgen.

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a>Parallelle implementatie met overlappende implementatie van gebruikers (parallel 2)

Voor deze implementatiestrategie start u het volgende:

- Proefimplementatie van de volgende fase tijdens het laatste deel van de gebruikersimplementatie van de huidige fase.
- De gebruikersimplementatie van de volgende fase tijdens de implementatie van de huidige fase op zodanige wijze dat er geen gebruikers zijn die meerdere fasen tegelijk doorlopen. Hierbij wordt ervan uitgegaan dat u elke fase van de Foundation-infrastructuur op dezelfde manier uitvouwt, zoals regio's, afdelingen of andere groepen.

Dit is een vereenvoudigde vergelijking tussen de verschillende implementatiestrategieën.

![De parallelle implementatie van fasen 2-6 met overlappende gebruikersimplementatie](../media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

Het eindresultaat luidt als volgt:

- Proefimplementaties gaan zonder pauze van de ene fase over in de volgende.
- De gebruikersimplementatie voor een fase begint met het voltooien van de gebruikersimplementatie in de vorige fase, maar er wordt niet meer dan één fase tegelijk uitgerold.

Dit is een vereenvoudigde gebruikerservaring voor prototypen als voorbeeld:

- In december moet ik mijn smartphone voor MFA gaan gebruiken. (Identiteit)
- In januari wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop. (Windows 10 Enterprise)
- In februari wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013. (Office 365 ProPlus)
- In maart worden de apparaatimplementatie en het app- en apparaatbeleid toegepast. (Mobile device management)
- In april wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten. (Informatiebescherming)

Het resultaat is een frequentie van 30 dagen tussen opeenvolgende proefimplementaties.

Hieronder ziet u een vereenvoudigde ervaring voor de eindgebruiker als voorbeeld:

- In januari moet ik mijn smartphone voor MFA gaan gebruiken. (Identiteit)
- In februari wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop. (Windows 10 Enterprise)
- In maart wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013. (Office 365 ProPlus)
- In april worden de apparaatimplementatie en het app- en apparaatbeleid toegepast. (Mobile device management)
- In mei wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten. (Informatiebescherming)

Het resultaat is een frequentie van 30 dagen tussen opeenvolgende gebruikersimplementaties.

Het voordeel van deze implementatiestrategie is dat het nog minder tijd kost om de basisinfrastructuur van Microsoft 365 voor ondernemingen volledig te implementeren, zonder dat eindgebruikers tegelijkertijd met meerdere implementaties te maken krijgen. Gebruikers krijgen echter geen onderbreking tussen de opeenvolgende fasen.

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a>Up-front infrastructuur en uitrol van de end-to-end configuratie

Voor kleinere organisaties die de fasen 2-6 kunnen comprimeren tot één implementatiesegment, ziet de resulterende implementatie er als volgt uit:
 
![Up-front infrastructuur en uitrol van de end-to-end configuratie](../media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

De IT-afdeling configureert de infrastructuur voor fase 2-6 en rolt vervolgens uit naar de prototypegebruikers, om te controleren op end-to-end-functionaliteit. Prototypegebruikers krijgen bijvoorbeeld al deze functionaliteit tegelijkertijd:

- MFA en andere identiteitsfuncties (Identiteit)
- Windows 10 Enterprise op Windows-apparaten (Windows 10 Enterprise)
- Office 365 ProPlus voor de Office-suite (Office 365 ProPlus)
- App- en apparaatinstellingen (Mobile Device Management)
- Azure Information Protection-client geïnstalleerd en training over het toepassen van labels op documenten (informatiebeveiliging)

Zodra de proefimplementatie is voltooid, begint de implementatie van de gebruikers, waarbij elke gebruiker tegelijkertijd alle functionaliteit krijgt.

## <a name="next-step"></a>Volgende stap

Start de implementatie van Microsoft 365 voor ondernemingen met de [basisinfrastructuur](deploy-foundation-infrastructure.md).
