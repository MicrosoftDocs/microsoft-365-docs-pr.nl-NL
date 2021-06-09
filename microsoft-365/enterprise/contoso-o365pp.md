---
title: Implementatie van Microsoft 365-apps voor ondernemingen voor Contoso
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
description: Ontdek hoe Contoso Microsoft Endpoint Configuration Manager gebruikt om Microsoft 365-apps voor ondernemingen te implementeren.
ms.openlocfilehash: 71958b2e87882e478a852db1f906f61207837854
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907672"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Implementatie van Microsoft 365-apps voor ondernemingen voor Contoso

Contoso heeft hun pc's geüpgraded naar Windows 10 Enterprise en Microsoft 365-apps voor ondernemingen om effectievere samenwerking, betere beveiliging en een modernere bureaubladervaring mogelijk te maken. Nadat ze hun infrastructuur en zakelijke behoeften hebben beoordeeld, heeft Contoso deze belangrijke vereisten voor de implementatie geïdentificeerd:

- Alle pc's moeten Microsoft 365-apps voor ondernemingen.
- Implementatie moet indien mogelijk gebruikmaken van bestaande beheerhulpmiddelen en -infrastructuur.
- Implementatie moet ondersteuning bieden voor meerdere talen en bestaande architecturen op apparaten van gebruikers.
- Pc's moeten up-to-date en veilig blijven met minimale IT-beheerkosten en minimale gevolgen voor gebruikers.

## <a name="deployment-tools"></a>Implementatiehulpmiddelen

Op basis van hun vereisten heeft Contoso ervoor gekozen om Windows 10 Enterprise en Microsoft 365-apps voor ondernemingen te implementeren via Configuration Manager (Current Branch). Configuration Manager is schaalbaar voor grote omgevingen en biedt uitgebreide controle over installatie, updates en instellingen. Er zijn ook ingebouwde functies waarmee het eenvoudiger en efficiënter wordt om Office te implementeren en te beheren, waaronder:

- Peercache, wat kan helpen bij beperkte netwerkcapaciteit bij het implementeren naar apparaten op externe locaties.
- Het Office clientbeheer, waarmee u eenvoudig updates Office implementeren en controleren en beheerders toegang geeft tot de nieuwste implementatie- en beheerfuncties.
- Intelligente implementatie van taalpakket, inclusief het automatisch implementeren van dezelfde taal als het besturingssysteem.
- Een volledig ondersteunde en eenvoudig te gebruiken methode voor het verwijderen van bestaande versies van Office van een client tijdens de implementatie.

Naast Configuration Manager heeft Contoso de [gereedheids-Toolkit voor Office-invoegingen](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)en VBA , een gratis hulpprogramma van Microsoft, gebruikt om compatibiliteitsproblemen met hun Office-macro's en invoegvoegingen te beoordelen.

## <a name="managing-deployment-and-updates"></a>Implementatie en updates beheren

Microsoft 365-apps voor ondernemingen heeft een nieuw releasemodel: Office-als-een-service. Met het servicemodel kunt u eenvoudig op de hoogte blijven van nieuwe functies. Maar it-afdelingen moeten vaak de manier wijzigen waarop ze nieuwe releases implementeren en testen. Om compatibiliteitsproblemen te minimaliseren en ervoor te zorgen dat hun computers up-to-date blijven, heeft Contoso Windows en Office in twee fasen geïmplementeerd:

- Eerst hebben ze Microsoft 365-apps voor ondernemingen geïmplementeerd op een kleine set representatieve apparaten in de hele organisatie. Deze testgroep is gebruikt om apps, invoegprogramma's en hardware te testen met Microsoft 365-apps voor ondernemingen.
- Vier maanden later, nadat alle kritieke problemen met apps, invoegtoepassingen en hardware in de pilotgroep waren verholpen, heeft Contoso Microsoft 365-apps voor ondernemingen toegepast op de rest van de apparaten in de organisatie (de brede groep).

In plaats van updates voor Office te beheren met Configuration Manager, heeft Contoso automatische updates vanuit de cloud ingeschakeld. Cloud-updates beperken de administratieve overhead en zorgen ervoor dat apparaten up-to-date blijven.

Contoso heeft dezelfde tweefasenbenadering gevolgd voor functie-updates als voor het implementeren van Office: Apparaten in de testgroep hebben vier maanden eerder functieupdates ontvangen dan apparaten in de rest van de organisatie (de brede groep). Om dit in te schakelen voor Office, heeft Contoso twee aanbevolen [updatekanalen](/DeployOffice/overview-update-channels) gebruikt:

- Halfjaarlijks Enterprise-kanaal (voorbeeld) voor updates voor de pilotgroep
- Semi-Annual Enterprise-kanaal voor updates voor de brede groep

Omdat het Halfjaarlijkse Enterprise-kanaal (voorbeeld) een versie van Microsoft 365-apps voor ondernemingen vier maanden eerder dan het Halfjaarlijkse Enterprise-kanaal uitgeeft, heeft Contoso de tijd om de updates te valideren zonder deze te moeten beheren.

## <a name="deployment-process"></a>Implementatieproces

Contoso implementeerde het volgende proces, met de aanbevolen procedures van Microsoft om de implementatie van de Office te voltooien:

1. Vóór de implementatie heeft Contoso de invoegapp Gereedheid Toolkit voor Office en VBA gebruikt om hun apps en Office-invoegvoegingen te testen om de compatibiliteit met Microsoft 365-apps voor ondernemingen.
1. In Configuration Manager hebben ze peercache ingeschakeld op hun clientapparaten, wat helpt bij beperkte netwerkcapaciteit bij het implementeren naar clientapparaten op externe locaties. 
1. Contoso heeft twee implementatiegroepen gedefinieerd als apparaatverzamelingen in Configuration Manager: een testgroep en een brede groep. De testgroep, die een kleine set representatieve apparaten in de hele organisatie bevatte, is gebruikt voor aanvullende tests van apps, invoegapparaten en hardware met Windows 10 Enterprise en Microsoft 365-apps voor ondernemingen.
1. Ze hebben implementatiepakketten voor Office gemaakt met het Office clientbeheerdashboard en de wizard Office 365 Installer, die beide deel uitmaken van de configuratiebeheerconsole. Zij bouwden twee pakketten van Microsoft 365-apps voor ondernemingen, één voor de pilotgroep op het Halfjaarlijkse Enterprise-kanaal (voorbeeld) en één voor de brede groep op het Halfjaarlijkse Enterprise-kanaal.
2. Elk Office pakket bevat Engels, Frans en Duits. Als voor een apparaat een taal is vereist die niet is opgenomen in het Office-pakket, is dat taalpakket automatisch gedownload van de Office Content Delivery Network (CDN).
3. Ze gebruikten de ingebouwde functie in het Office-pakket om alle bestaande MSI-versies van Office automatisch te verwijderen voordat Microsoft 365-apps voor ondernemingen werd geïnstalleerd.
4. In Configuration Manager hebben ze de Windows en Office pakketten geïmplementeerd op distributiepunten in hun netwerk. Vervolgens hebben ze de implementatietaakreeksen van Configuration Manager uitgevoerd om het pilotpakket Microsoft 365-apps voor ondernemingen de testgroep te implementeren.
5. Nadat ze compatibiliteitsproblemen met de testgroep hebben opgelost, heeft Contoso de taakreeksen uitgevoerd om het Microsoft 365-apps voor ondernemingen te implementeren voor de brede groep.

Contoso heeft ervoor gekozen om apparaten automatisch bij te werken vanuit de cloud. Het was niet nodig om het proces in Configuration Manager te beheren. Hun apparaten worden automatisch rechtstreeks vanuit de cloud bijgewerkt op basis van het updatekanaal dat is gedefinieerd in de eerste implementatie.

Hier is de contoso-Microsoft 365-apps voor ondernemingen installatie- en doorlopende implementatiearchitectuur voor updates.

![De Contoso-implementatie-infrastructuur voor Microsoft 365-apps voor ondernemingen](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Volgende stap

Meer informatie over hoe Contoso Microsoft Intune [in](contoso-mdm.md) Microsoft 365 voor bedrijven gebruikt voor het beheren van de apparaten en de apps die ze in de hele organisatie uitvoeren.

## <a name="see-also"></a>Zie ook

[Microsoft 365-apps voor ondernemingen](/deployoffice/deployment-guide-microsoft-365-apps)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)