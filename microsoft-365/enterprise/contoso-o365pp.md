---
title: Implementatie van Microsoft 365-apps voor ondernemingen voor Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Ontdek hoe Contoso Microsoft Endpoint Configuration Manager gebruikt om Microsoft 365-apps voor ondernemingen te implementeren.
ms.openlocfilehash: 63993a27f23843fd2d75ef9bf08ae064ec46dc77
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637161"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Implementatie van Microsoft 365-apps voor ondernemingen voor Contoso

Contoso heeft hun pc's geüpgraded naar Windows 10 Enterprise en Microsoft 365-apps voor ondernemingen om effectievere samenwerking, betere beveiliging en een modernere bureaubladervaring mogelijk te maken. Na beoordeling van de infrastructuur en de bedrijfsbehoeften heeft Contoso de volgende sleutel vereisten voor de implementatie aangegeven:

- Voor alle Pc's moet Microsoft 365-apps voor Enterprise worden uitgevoerd.
- Implementatie dient indien mogelijk bestaande beheerprogramma's en infrastructuur te gebruiken.
- Implementatie moet meerdere talen en bestaande architecturen op de apparaten van gebruikers ondersteunen.
- Pc's moeten up-to-date blijven en veilig zijn met minimale IT-beheerkosten en de minimale impact voor gebruikers.

## <a name="deployment-tools"></a>Implementatiehulpmiddelen

Op basis van de vereisten is contoso besloten om Windows 10 Enterprise en Microsoft 365-apps voor Enterprise via Configuration Manager (huidige tak) te implementeren. Configuration Manager is schaalbaar voor grote omgevingen en biedt uitgebreide controle over installatie, updates en instellingen. Er zijn ook ingebouwde functies waarmee het eenvoudiger en efficiënter wordt om Office te implementeren en te beheren, waaronder:

- Peer cache, waarmee kan worden gecommuniceerd met beperkte netwerkcapaciteit wanneer ze op externe locaties implementeren.
- Het dashboard van Office-client, waarmee u eenvoudig Office kunt implementeren en bijwerken en beheerderstoegang kunt krijgen tot de meest recente functies voor het implementeren en beheren van functies.
- Intelligent taalpakket implementeren, waaronder automatisch de taal van het besturingssysteem.
- Een volledig ondersteunde en eenvoudig te gebruiken manier om bestaande versies van Office te verwijderen uit een client tijdens de implementatie.

Naast de configuratie manager heeft Contoso de [gereedheids Toolkit voor Office-invoegtoepassingen en VBA](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), een gratis tool van Microsoft gebruikt om compatibiliteitsproblemen met hun Office-macro's en-invoegtoepassingen te beoordelen.

## <a name="managing-deployment-and-updates"></a>Implementatie en updates beheren

Microsoft 365-apps voor ondernemingen heeft een nieuw releasemodel: Office-als-een-service. Met het servicemodel kunt u gemakkelijk up-to-date blijven met nieuwe functies. Maar de IT-afdelingen moeten vaak veranderen hoe ze nieuwe versies implementeren en testen. Om compatibiliteitsproblemen te minimaliseren en om ervoor te zorgen dat hun computers up-to-date blijven, door contoso geïmplementeerde Vensters en Office in twee fasen:

- Eerst hebben ze Microsoft 365-apps voor Enterprise geïmplementeerd voor een kleine groep representatieve apparaten in de gehele organisatie. Deze testgroep werd gebruikt voor het testen van apps, invoegtoepassingen en hardware met Microsoft 365-apps voor ondernemingen.
- Vier maanden later, nadat alle kritieke problemen met apps, invoegtoepassingen en hardware in de pilotgroep waren verholpen, heeft Contoso Microsoft 365-apps voor ondernemingen toegepast op de rest van de apparaten in de organisatie (de brede groep).

In plaats van updates voor Office te beheren via Configuration Manager, met Contoso geautomatiseerde updates van de Cloud. Voor de updates van de Cloud wordt de beheerskosten beperkt en zorg ervoor dat de apparaten up-to-date blijven.

Contoso heeft dezelfde aanpak met twee fasen gevolgd voor de functie-updates die worden gebruikt voor de implementatie van Office: apparaten in de testgroep ontvangen vier maanden eerder de optie updates van de rest van de organisatie (de grote groep). Om dit in te schakelen voor Office, heeft Contoso twee aanbevolen [updatekanalen](https://docs.microsoft.com/DeployOffice/overview-update-channels) gebruikt:

- Halfjaarlijks Enterprise-kanaal (voorbeeld) voor updates voor de pilotgroep
- Semi-Annual Enterprise-kanaal voor updates voor de grote groep

Omdat het Halfjaarlijkse Enterprise-kanaal (voorbeeld) een versie van Microsoft 365-apps voor ondernemingen vier maanden eerder dan het Halfjaarlijkse Enterprise-kanaal uitgeeft, heeft Contoso de tijd om de updates te valideren zonder deze te moeten beheren.

## <a name="deployment-process"></a>Implementatieproces

Contoso implementeerde het volgende proces, met de aanbevolen procedures van Microsoft om de implementatie van de Office te voltooien:

1. Contoso gebruikt de Readiness Toolkit voor Office-invoegtoepassing en VBA om de apps en Office-invoegtoepassingen te testen om de compatibiliteit met Microsoft 365-apps voor Enterprise te beoordelen.
1. In Configuration Manager hebben ze de peercache op hun clientapparaten ingeschakeld, wat helpt met beperkte netwerkcapaciteit wanneer ze op externe locaties worden geïmplementeerd op clientapparaten. 
1. Contoso heeft twee implementatie groepen gedefinieerd als Apparaatsets in Configuration Manager: een testgroep en een grote groep. De testgroep, die een klein aantal representatieve apparatuur voor de hele organisatie omvat, werd gebruikt voor het extra testen van apps, invoegtoepassingen en hardware met Windows 10 Enterprise en Microsoft 365-apps voor Enterprise.
1. Ze hebben implementatiepakketten voor Office gemaakt met behulp van het beheer dashboard voor Office-clients en de installatiewizard van Office 365, dat beide deel uitmaakt van de console van de Configuration Manager. Zij bouwden twee pakketten van Microsoft 365-apps voor ondernemingen, één voor de pilotgroep op het Halfjaarlijkse Enterprise-kanaal (voorbeeld) en één voor de brede groep op het Halfjaarlijkse Enterprise-kanaal.
2. Voor elk Office-pakket zijn Engelse taalpakketten Engels, Frans en Duits inbegrepen. Als een apparaat vereist is voor een taal die niet is opgenomen in het Office-pakket, wordt dat taalpakket automatisch gedownload van het Office Content Delivery Network (CDN).
3. Ze gebruikten de ingebouwde functie in het Office-pakket om alle bestaande MSI-versies van Office automatisch te verwijderen voordat Microsoft 365-apps voor ondernemingen werd geïnstalleerd.
4. In Configuration Manager hebben ze de Windows-en Office-pakketten geïmplementeerd op distributiepunten in hun netwerk. Vervolgens hebben ze de takenreeksen voor de implementatie van Configuration Manager voor het implementeren van de prototype Microsoft 365 apps for Enterprise package voor de groep prototype.
5. Nadat de persoon de compatibiliteitsproblemen met de testgroep heeft opgelost, heeft Contoso de takenreeksen uitgevoerd om de Microsoft 365-apps voor Enterprise pakket voor de grote groep te implementeren.

Contoso heeft ervoor gekozen om apparaten automatisch bij te werken vanuit de cloud. Het was niet nodig om het proces in Configuration Manager te beheren. De apparaten worden automatisch bijgewerkt vanuit de Cloud op basis van het update kanaal dat is gedefinieerd in de eerste implementatie.

Hier is de contoso Microsoft 365-apps for Enterprise Installation en continue update Deployment Architecture.

![De implementatie-infrastructuur contoso voor Microsoft 365-apps voor ondernemingen](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Volgende stap

[Meer informatie](contoso-mdm.md) over hoe contoso gebruikmaakt van Microsoft intune in microsoft 365 for Enterprise voor het beheren van de apparaten en de apps die ze binnen de organisatie uitvoeren.

## <a name="see-also"></a>Zie ook

[Microsoft 365-apps voor ondernemingen](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
