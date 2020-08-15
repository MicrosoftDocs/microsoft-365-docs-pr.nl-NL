---
title: Monitoring van Microsoft 365 en zelfherstel
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over de functies voor het bewaken en zelfherstel van Microsoft 365.
ms.openlocfilehash: 459fdb50577c255d3cf27a31dbbbdd5768392c44
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689517"
---
# <a name="microsoft-365-monitoring-and-self-healing"></a>Monitoring van Microsoft 365 en zelfherstel

Op basis van de schaal van Microsoft 365 is het niet mogelijk om de klantgegevens van malware te beschermen en te beschermen zonder dat u beschikt over een allesomvattende, waarschuwings gerichte functie en een snelle herstelfunctie die snel en betrouwbaar is. Het bewaken van een set services onder de schaal van Microsoft 365 is zeer moeilijk. Nieuwe mindsets en methodologieën die moeten worden geïntroduceerd, en alle nieuwe sets technologieën die nodig zijn om de service in een verbonden wereldwijde omgeving te kunnen beheren en beheren. Voor het maken van waarschuwingen voor het verzamelen en filteren van gegevens is het niet mogelijk om waarschuwingen te maken op basis van gegevensanalyse; het maken van signalen en vertrouwen in deze gegevens en vervolgens automatisering gebruiken om het probleem te herstellen of op te lossen. Met deze methode kunt u de werkwijze van de herstel vergelijking verzorgen, wat in werking minder kost en sneller en minder fout gevoeliger is. 

De basis Microsoft 365 monitoring is een verzameling technologieën die onze data Insights-engine vormen, die is gebaseerd op Azure, SQL Azure en de [database streaming database](https://cassandra.apache.org/). Het is bedoeld om gegevens te verzamelen en samen te voegen en conclusies te bereiken. Op dit moment wordt er op dit moment meer dan 500.000.000 gebeurtenissen per uur verwerkt vanaf meer dan 100.000 servers (maximaal 15 TB per dag) verspreid over tientallen datacenters in vele regio's en worden deze nummers steeds groter. 

Microsoft 365 maakt gebruik *van externe controle*functies, waarbij synthetische transacties worden gemaakt om alles wat belangrijk is te testen. In Exchange Online wordt elk scenario bijvoorbeeld elke vijf minuten overal ter wereld getest op een gestrooide manier, zodat alles wat binnen het systeem valt, voortdurend wordt gedekt. Vanaf meerdere locaties worden testtransacties per dag van 250.000.000 uitgevoerd voor het maken van een krachtige basislijn of levenslijn voor de service. 

In Microsoft 365 wordt ook het concept van de *rode waarschuwing*gebruikt, waarmee alle controle signalen van alle computers in ons datacenter worden verkleind, zodat iets beter kan worden beheerd door een menselijk. Het concept is een simpel simpel: als er een probleem optreedt in meerdere signalen, moet u iets aan het doen zijn. Het maakt niet uit of het gaat om het maken van een vertrouwens zekerheid in één signaal, wat betekent dat u voor elk signaal een goede kwaliteit krijgt, zodat u nauwkeuriger kunt zijn. Dit monitoring systeem is zo krachtig dat wij geen last hebben van het bekijken van de monitoren; alles wat u hebt, is de machine die de slaapstand ophaalt als er een probleem wordt gedetecteerd, in welk geval de IT-afdeling de toepasselijke medewerkers of vaker als het geval is, is het handig om het probleem te verhelpen. Wanneer we beginnen met het verzamelen van signalen en het maken van rode waarschuwingen, kunnen we de triangulatie in al onze service partities starten. 

Op basis van een combinatie van de foutmelding en de rode waarschuwingen wordt in deze melding exact aangegeven welke onderdelen kunnen worden gevonden en wordt het systeem geprobeerd het probleem door zichzelf op te lossen door een postvakserver opnieuw te starten. 

Daarnaast bevat Exchange Online diverse functies waarmee u de functionaliteit van de eindgebruikers kunt volgen en de functies die het meest worden gebruikt voor het behoud van de functionaliteit voor automatische herstelfuncties, zoals het herstellen van enkele pagina's. Dit omvat *beschikbare beschikbaarheid*, waaronder ingebouwde acties voor het uitvoeren van bewerkingen en herstelfuncties, waarbij de database automatisch wordt hersteld na een schijfstoring. 

## <a name="managed-availability"></a>Begeleide beschikbaarheid 

Begeleide beschikbaarheid biedt een systeemeigen controle-en hersteloplossing waarmee de werking van de eindgebruiker via hersteltaken wordt gecontroleerd en beschermd. Begeleide beschikbaarheid is de integratie van ingebouwde acties voor het uitvoeren van controle en herstel met het Exchange High Availability platform. Het is bedoeld om problemen te detecteren en op te lossen zodra ze zich voordoen en worden gedetecteerd door het systeem. In tegenstelling tot eerdere oplossingen en technieken van extern volgen voor Exchange wordt in de beschikbaarheid beheerd niet geprobeerd de hoofdoorzaak van een probleem te identificeren of te communiceren. In plaats daarvan is de nadruk op de situatie met betrekking tot de werking van de eindgebruikers:

- **Beschikbaarheid** : gebruikers kunnen toegang krijgen tot de service? 
- **Vertraging** voor gebruikers? 
- **Fouten** -kunnen gebruikers wat ze willen doen? 

Begeleide beschikbaarheid is een interne functie die wordt uitgevoerd op elke Microsoft 365-server met Exchange Online. Met deze functie wordt de honderden statuswaarden van elke seconde gecontroleerd en geanalyseerd. Als er iets mis is, is het meestal automatisch opgelost. De beschikbaarheid van de beschikbaarheid van de beschikbaarheid kan niet zelf worden opgelost. In deze gevallen wordt met de beschikbaarheid van de beschikbaarheid van een ondersteuningsteam voor Microsoft 365 het probleem met behulp van gebeurtenissen vastgelegd.

## <a name="autoreseed"></a>AutoReseed

Exchange Online-servers worden geïmplementeerd met een configuratie waarin meerdere databases en de bijbehorende logboek streaming op dezelfde niet-RAID-schijf worden opgeslagen. Deze configuratie wordt vaak wel een reeks *schijven* (JBOD) genoemd, omdat er geen opslagruimte is, zoals RAID, wordt gebruikt om de gegevens op de schijf te dupliceren. Wanneer een schijf in een JBOD-omgeving uitvalt, gaan de gegevens op die schijf verloren. 

Met de grootte van Exchange Online en het feit dat u de implementatie binnen de cd maakt, zijn er miljoenen schijfstations een regelmatige plaats in Exchange Online. In feite zijn er elke dag meer dan 100 fouten. Wanneer een schijf in een on-premises Enterprise-implementatie mislukt, moet een beheerder de defecte schijf handmatig vervangen en de betreffende gegevens herstellen. In een Cloud implementatie de grootte van Microsoft 365, met operatoren (Cloud beheerders) het handmatig vervangen van schijven is niet praktisch noch economisch haalbaar. 

Automatische herseeding of *AutoReseed*is een functie die de vervangende actie van een door de operator gerichte actie veroorzaakt in antwoord op een schijfstoring, een database beschadigd of een ander probleem waarbij een opnieuw seeding van een database-kopie is vereist. AutoReseed is ontworpen voor het automatisch herstellen van databaseherstel na een schijfstoring met behulp van reserve schijven die aan het systeem zijn ingericht. Als een schijf uitvalt, worden de databasekopieën die op deze schijf zijn opgeslagen, automatisch opnieuw geseedd naar een vooraf geconfigureerde reserveschijf op de server, waardoor u de gegevens kunt herstellen. 