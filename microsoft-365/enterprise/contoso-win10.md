---
title: Windows 10 Enterprise-implementatie voor Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Ontdek hoe Contoso Microsoft Endpoint Configuration Manager gebruikte om in-place upgrades voor Windows 10 Enterprise te implementeren.
ms.openlocfilehash: 7907bf64acce3af8b21459202cb6f5cbc1e9f990
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907684"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Windows 10 Enterprise-implementatie voor Contoso

Vóór de brede uitrol van Microsoft 365 voor ondernemingen had Contoso Windows-compatibele pc's en apparaten met een combinatie van Windows 7 (10%), Windows 8,1 (65%) en Windows 10 (25%). Contoso wilde haar pc’s upgraden, omdat Windows 10 Enterprise gebruikmaakt van geavanceerde beveiliging en IT-overhead vermindert door automatische implementatie van updates. 

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

Contoso heeft de upgradebereidheid in Windows Analytics gebruikt om de set geïnstalleerde apps en de compatibiliteit met Windows 10 Enterprise.

## <a name="deployment-process"></a>Implementatieproces

Contoso implementeerde het volgende proces, met de aanbevelingen van Microsoft voor aanbevolen procedures om de implementatie van de in-place upgrade van Windows 10 Enterprise te voltooien:

1. Peer-cache voor Configuration Manager werd ingeschakeld.
2. Aangepaste Windows-pakketten werden gemaakt op basis van images van het Servicecentrum voor volumelicenties.
3. Configuration Manager gebruikt om de Windows distributiepunten in hun netwerk te implementeren en builds te implementeren voor de drie validatie- en implementatiefaseringsgroepen.
4. Evaluatie werd uitgevoerd voor het slagen van de implementatie op pc’s en apparaten in de drie ringen voor validatie- en implementatiefasen met de Windows Analytics-oplossingen Apparaatstatus en Naleving van updates.
5. Op basis van Windows analysegegevens heeft Contoso de versie van de Windows 10 Enterprise voor implementatie in de brede implementatiegroep bepaald.
6. De implementatiereeksen van Configuration Manager zijn uitgevoerd om het geselecteerde Windows te implementeren in de brede implementatiegroep.
7. Bewaakte pc's en apparaten in de brede implementatiegroep met de oplossingen Apparaattoestand en Compliance bijwerken om problemen op te lossen.

Dit is de implementatie-architectuur van in-place upgrades en doorlopende updates van Contoso.

![Implementatie-architectuur van Windows 10 Enterprise van Contoso](../media/contoso-win10/contoso-win10-fig1.png)

Deze infrastructuur bestaat uit:

- Configuration Manager, die:
  - images ophaalt voor Windows 10 Enterprise-pakketten van het Microsoft Servicecentrum voor volumelicenties in het Microsoft-netwerk.
  - het centrale beheerpunt is voor implementatiepakketten.
- Regionale distributiepunten die zich normaliter in de regionale hub-kantoren van Contoso bevinden.
- Windows Pc's en apparaten op verschillende locaties die de implementatiepakketten ontvangen en installeren voor de in-place upgrade of doorlopende updates op basis van groepslidmaatschap.

## <a name="next-step"></a>Volgende stap

Lees hoe Contoso gebruik maakt van de Configuration Manager-infrastructuur om de huidige Microsoft 365-apps voor ondernemingen [binnen](contoso-o365pp.md) de organisatie te implementeren en te behouden. 

## <a name="see-also"></a>Zie ook

[Windows 10 Enterprise](/windows/deployment/)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)