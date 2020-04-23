---
title: Windows 10 Enterprise-implementatie voor Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Ontdek hoe Contoso Microsoft Endpoint Configuration Manager gebruikte om in-place upgrades voor Windows 10 Enterprise te implementeren.
ms.openlocfilehash: c66be4ad5ee383301c4fb10cf2590f7cbbed033f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630679"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Windows 10 Enterprise-implementatie voor Contoso

Vóór de brede implementatie van Microsoft 365 Enterprise waren de pc’s van Contoso compatibel met Windows en werd er een combinatie van Windows 7 (10%), Windows 8.1 (65%) en Windows 10 (25%) uitgevoerd. Contoso wilde haar pc’s upgraden, omdat Windows 10 Enterprise gebruikmaakt van geavanceerde beveiliging en IT-overhead vermindert door automatische implementatie van updates. 

Na het evalueren van hun infrastructuur en bedrijfsbehoeften identificeerde Contoso deze belangrijke vereisten voor de implementatie:

- Zoveel mogelijk pc’s en apparaten moeten Windows 10 Enterprise uitvoeren
- De implementatie van de in-place upgrades gebruikt de bestaande Configuration Manager-infrastructuur
- De controle over welke versie van Windows 10 Enterprise moet worden geïmplementeerd en updates moeten plaatsvinden middels ringen.
- Pc’s en apparaten moeten up-to-date blijven met minimale administratieve IT-kosten en minimale overlast voor eindgebruikers

Up-to-date wordt gedefinieerd als de ondersteunde versie van Windows 10 Enterprise die voldoet aan de bedrijfsbehoeften van Contoso. Dit hoeft niet te betekenen dat alle Windows-compatibele pc’s de nieuwste versie van Windows 10 Enterprise uitvoeren.

## <a name="deployment-tools"></a>Implementatiehulpmiddelen

Voorafgaand en tijdens de in-place upgrades van Windows 10 Enterprise gebruikte Contoso de volgende oplossingen van Windows Analytics:

- Gereedheidscontroles voor upgrades  

  Hiermee worden systeem-, toepassings- en stuurprogrammagagevens verzameld voor analyses en vervolgens compatibiliteitsproblemen die een upgrade kunnen blokkeren en voorgestelde oplossingen van bij Microsoft bekende problemen geïdentificeerd.

- Naleving van updates  

  Geeft de status van uw apparaten weer inzake de Windows-updates, zodat u er zeker van kunt zijn dat ze de meest recente updates hebben.

- Apparaatstatus  

  Hiermee worden apparaten geïdentificeerd die regelmatig vastlopen en die daarom mogelijk opnieuw moeten worden opgebouwd of vervangen en stuurprogramma’s die de oorzaak zijn van het vastlopen, met suggesties van alternatieve versies van die stuurprogramma’s, waardoor apparaten minder vaak vastlopen. Hiermee worden meldingen weergegeven over onjuiste configuraties van Windows-gegevensbescherming en aanwijzingen naar de eindgebruikers verzonden.
 
Contoso heeft een bestaande Configuration Manager-infrastructuur (Current Branch). Configuration Manager is schaalbaar voor grote omgevingen en biedt uitgebreide controle over installatie, updates en instellingen. Er zijn ook ingebouwde functies waarmee het eenvoudiger en efficiënter wordt om Windows 10 Enterprise te implementeren en te beheren.

## <a name="planning-process"></a>Planningsproces

Voorafgaand aan de implementatie definieerde Contoso de volgende ringen:

- Drie ringen voor validatie- en implementatiefasen 
  - Eén voor preview-versies 
  - Eén voor nieuwe release-versies
  - Eén voor een eerdere versie 
- Eén ring voor brede implementatie van Windows 10 Enterprise op basis van gegevens van de validatieringen

Contoso gebruikte ook de Windows Analytics-oplossing Gereedheidscontrole voor upgrades om de geïnstalleerde apps en de compatibiliteit met Windows 10 Enterprise vast te stellen.

## <a name="deployment-process"></a>Implementatieproces

Contoso implementeerde het volgende proces, met de aanbevelingen van Microsoft voor aanbevolen procedures om de implementatie van de in-place upgrade van Windows 10 Enterprise te voltooien:

1. Peer-cache voor Configuration Manager werd ingeschakeld.
2. Aangepaste Windows-pakketten werden gemaakt op basis van images van het Servicecentrum voor volumelicenties.
3. Configuration Manager werd gebruikt om de Windows-pakketten te implementeren naar distributiepunten in hun netwerk en builds gedistribueerd naar de drie ringen voor validatie- en implementatiefasen.
4. Evaluatie werd uitgevoerd voor het slagen van de implementatie op pc’s en apparaten in de drie ringen voor validatie- en implementatiefasen met de Windows Analytics-oplossingen Apparaatstatus en Naleving van updates.
5. Op basis van de informatie van Windows Analytics bepaalde Contoso de versie van Windows 10 Enterprise die in de brede implementatiering moest worden geïmplementeerd.
6. De takenreeksen voor implementatie werden uitgevoerd voor het implementeren van de geselecteerde Windows-pakketten in de brede implementatiering.
7. Pc’s en apparaten werden bewaakt in de brede implementatiering met de oplossingen Apparaatstatus en Naleving van updates om problemen op te lossen.

Dit is de implementatie-architectuur van in-place upgrades en doorlopende updates van Contoso.

![Implementatie-architectuur van Windows 10 Enterprise van Contoso](../media/contoso-win10/contoso-win10-fig1.png)

Deze infrastructuur bestaat uit:

- Configuration Manager, die:
  - images ophaalt voor Windows 10 Enterprise-pakketten van het Microsoft Servicecentrum voor volumelicenties in het Microsoft-netwerk.
  - het centrale beheerpunt is voor implementatiepakketten.
- Regionale distributiepunten die zich normaliter in de regionale hub-kantoren van Contoso bevinden.
- Windows-pc’s en -apparaten op verschillende locaties die de implementatiepakketten ontvangen en installeren voor de in-place upgrade of doorlopende updates bij ringleden.

## <a name="next-step"></a>Volgende stap

[Lees](contoso-o365pp.md) hier hoe Contoso zijn infrastructuur voor Configuratiebeheer gebruikt voor het implementeren en onderhouden van Microsoft 365-apps voor ondernemingen in de hele organisatie. 

## <a name="see-also"></a>Zie ook

[Windows 10 Enterprise voor Microsoft 365 Enterprise](windows10-infrastructure.md)

[Implementatiehandleiding](deploy-microsoft-365-enterprise.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
