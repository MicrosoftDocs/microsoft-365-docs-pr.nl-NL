---
title: Overwegingen voor het beheerplan voor de bedrijfscontinuïteit van uw onderneming
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Overwegingen bij het ontwikkelen van een bedrijfscontinuïteitsplan met de cloud.
ms.openlocfilehash: f8518a96461d33093b9d736f890f6166dc6b3c97
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807333"
---
# <a name="developing-your-continuity-plan"></a>Uw continuïteitsplan ontwikkelen

In dit onderwerp vindt u richtlijnen voor het ontwikkelen van een bedrijfscontinuïteitsplan dat rekening houdt met Microsoft 365-afhankelijkheden. We raden hier methoden aan voor het analyseren van uw bedrijfsfuncties en het identificeren van de functies die afhankelijk zijn van Microsoft 365-services. U voert deze analyse uit met het oog op mogelijke servicefouten omdat u hierop voorbereid wilt zijn.

Het plannen van bedrijfscontinuïteit omvat in het algemeen vier aspecten, namelijk beoordeling, planning, validatie van de mogelijkheden, en communicatie en coördinatie.

## <a name="assessment"></a>Beoordeling
Eerst moet u de bedrijfsfuncties van uw organisatie identificeren en nagaan door welke services en processen ze worden ondersteund. Dit omvat het uitvoeren van een analyse van de gevolgen voor het bedrijf, waarbij elke bedrijfsfunctie wordt gerangschikt op basis van hoe belangrijk deze is en u de processen en services identificeert waarvan de functies afhankelijk zijn. Hier ziet u een voorbeeldtabel die u kunt raadplegen om aan de slag te gaan met uw eigen beoordeling.

**Voorbeeld van effectbeoordeling**

Dit is een effectbeoordelingsdocument voor `name of the service, system, process, or function`

|Velden van effectbeoordeling|Beschrijving|
|---------|---------|
|Type effectbeoordeling|`is it a business process or technology, service or system?`|
|Naam effectbeoordeling|`name of the service/system/function/process`|
|Servicebeschrijving|`give a full description of the service, process, or function`|
|Bedrijfsfunctie|`some examples: customer services; legal; marketing; risk management, security, sales, information technology, production, manufacturing`|
|Fiscaal jaar|`the current fiscal year, re-evaluate these on a regular basis`|
|Ernst|`develop your own classifications, but here are some examples: mission critical, important, deferrable`|
|Bedrijfseenheid|`name of the business unit that owns this business function`|
|Proces (service, functie)|`the name of the process, service, or feature`|
|Hoofdleidinggevende bedrijfsgroep|`the name and contact information of the senior leader of the business group that owns this business process`|
|Heeft de technologie een tot stand gebrachte **interne** SLA of OLA?|`please explain in as much detail as possible`|
|Heeft de technologie een tot stand gebrachte **externe** SLA of OLA?|`please explain in as much detail as possible`|
|Heeft de technologie een bekend uitvoeringsmandaat om een specifieke proces-SLA mogelijk te maken? Zo ja, beschrijf dit in detail.|`details here`|
|Leidt het verlies van of de inbreuk op gegevens die zijn gekoppeld aan deze services, tot een belangrijke gebeurtenis? Zo ja, beschrijf dit in detail.|`details here`|
|Is er een tijdelijke oplossing of alternatief voor de service voor enkele of alle belangrijke functies van de service? Zo ja, beschrijf dit in detail.|`details here`|
|Worden er met het de service klantgegevens verwerkt, opgeslagen of verzonden, zoals bijvoorbeeld persoonsgegevens? Zo ja, beschrijf dit in detail.|`details here`|
|Status effectbeoordeling|`develop your own status classification, here are some examples: planned, started, in-progress, complete, on-hold, expired`|
|Voltooiingsdatum|`the date this BIA was completed`|
|Facilitator effectbeoordeling|`name of the person or group who is responsible for developing and maintaining this BIA`|
|Goedkeuring effectbeoordeling|`name of the person or group who is the executive sponsor of this BIA and who has responsibility for approving it.`|
|Bijdragers|`optional list of the people who helped develop this BIA and their contact information`|
|Locatie goedkeuring effectbeoordeling|`indicate where the executive approval is located, or attach proof to this document`|

## <a name="planning"></a>Planning

Vervolgens zoekt u in de bedrijfsprocessen waar trapsgewijze afhankelijkheidsrelaties bestaan. Op basis van het resultaat kunt u prioriteiten stellen, en tolerantiestrategieën en ondersteunende standaardbedrijfsprocedures bedenken.

U kunt [Microsoft Service Map](https://docs.microsoft.com/azure/azure-monitor/insights/service-map) gebruiken om u bij deze toewijzing te helpen. Met Microsoft Service Map worden automatisch toepassingsonderdelen van Windows- en Linux-systemen gedetecteerd en worden alle TCP-afhankelijkheden toegewezen, worden verbindingen geïdentificeerd en wordt bepaald van welke externe systemen de app afhankelijk is. Ook worden hiermee afhankelijkheden toegewezen aan gebieden van uw netwerk die traditioneel donker zijn, zoals Active Directory.

Hier ziet u een voorbeeld van een afhankelijkheidsanalyse die u als beginpunt kunt gebruiken. In de afhankelijkheidsanalyse identificeert en onderzoekt u de procesafhankelijkheden. Zorg ervoor dat u personen, leveranciers, klanten, partnerschappen en faciliteiten opneemt. De gegevens van deze analyse worden gebruikt om hiaten te identificeren tussen de herstelvereisten van een proces en de herstelmogelijkheden voor het ondersteunen van afhankelijkheden.


|veld|beschrijving|
|---------|---------|
|procestype|         |
|facilitator|         |
|voltooid door|         |
|voltooiingsdatum|         |
|bijdragers|         |
  
## <a name="capability-validation"></a>Validatie van mogelijkheden

Wanneer u uw bedrijfsprocessen hebt geïnventariseerd en relaties met andere processen en technologieën in kaart hebt gebracht, moet u validatiescenario's voor alle processen maken. U gaat in feite na hoe u uw plannen voor de bedrijfscontinuïteit gaat valideren. U zult waarschijnlijk merken dat sommige belangrijker zijn dan andere en dat u aan de belangrijke prioriteit wilt geven.
Vergeet niet dat het belangrijk is regelmatig werknemers te trainen hoe ze op incidenten moeten reageren en wat de maatregelen voor het behoud van de continuïteit zijn zodra het plan is opgesteld. Gebruik evaluaties van incidenten achteraf om uw tolerantiestrategieën te verbeteren met wat u van elke validatie of test hebt geleerd.

## <a name="incident-coordination-and-communication"></a>Coördinatie en communicatie bij incidenten

In het geval van een service-incident kan het voorkomen dat normale communicatiekanalen worden beïnvloed of gedegradeerd. Daarom moet u vooraf alternatieven bedenken om uw organisatie verbonden te houden tijdens het incident. Het is van essentieel belang dat de communicatiekanalen tot stand worden gebracht en worden getest op beveiliging en compliance en dat gebruikers voor hun gebruik zijn getraind voordat er storingen optreden. Een failover van een bekende status naar een andere bekende status heeft veruit de voorkeur voor gebruikers in plaats van midden in een crisis met ad-hoc-oplossingen te komen waarmee werknemers niet vertrouwd zijn.

Bij Microsoft heeft elk serviceteam interne alternatieve communicatiekanalen ingesteld om ons te helpen bij het coördineren wanneer onze normale communicatiekanalen niet beschikbaar zijn. Dit zijn onder meer back-upoplossingen voor telefonie en audiovergaderingen, Yammer-groepen, Teams-groepen, interne servicestatusdashboards en interne software voor incidentenbeheer.

Bij het analyseren van de gevolgen voor het bedrijf en de afhankelijkheden wijst u kritieke processen en de technologieën of services waarvan ze afhankelijk zijn toe. Let met name op de communicatie tijdens deze planningsfase en bedenk alternatieven. Dit zijn enkele voorbeelden.

- Als e-mail de belangrijkste methode is om uw gebruikers en belanghebbenden op de hoogte te houden, en uw e-mailservice is verslechterd of niet beschikbaar is, kunt u een andere service, zoals Microsoft Teams, Yammer of een andere service van derden, als back-up gebruiken. Het is belangrijk dat u deze vooraf instelt en uw gebruikers traint waar ze naartoe moeten gaan. Een Yammer-thread is niet handig als er niemand bekend is met het bestaan of als niemand er een bladwijzer voor heeft ingesteld.  
- Als uw interne processen voor het beheren van incidenten zijn gebaseerd op spraakcommunicatie om uw antwoorden te coördineren, moet u een alternatieve telefonieoplossing voor gebruik tijdens een crisis kiezen. Deze oplossing hoeft geen volledige pariteit te hebben met uw primaire service, maar moet het minimale samenwerkingsniveau bieden om uw teams voor bedrijfscontinuïteit en incidentenbeheer te coördineren. Verder kunt u gebruikers vragen hun mobiele telefoonnummer in uw algemene adreslijst te publiceren om een extra laag met back-upcommunicatie voor extreme situaties te maken.
- Mogelijk wilt u een aangepast servicestatusdashboard, of een andere dergelijke site, maken om statusupdates tijdens een incident te leveren. Als u gebruikers vooraf traint waar ze heen moeten gaan voor informatie, zal dit onnodige vragen aan de helpdesk beperken en zullen gebruikers er vertrouwen in hebben dat de situatie snel en efficiënt wordt afgehandeld. Gebruik de O365 Service Communications-API om dit te koppelen aan M365 voor een nog betere zichtbaarheid.  
- Het is essentieel dat de locatie van uw bedrijfscontinuïteitsplannen en standaardbedrijfsprocedures bekend is. U wordt aangeraden online- en offlinekopieën van kritieke documentatie te bewaren, zoals met SharePoint Online of OneDrive voor Bedrijven waarmee automatisch wordt gesynchroniseerd naar lokale apparaten. Voor operationele centra voor services/netwerken en andere soortgelijke teams die voor herstel absoluut essentieel zijn, wilt u mogelijk ook papieren kopieën hebben die in noodgevallen kunnen worden gebruikt.

## <a name="know-your-external-points-of-integration"></a>De externe integratiepunten kennen

Ongeacht het bedrijfsmodel heeft elk bedrijf integratiepunten met hun klanten, partners en leveranciers. De toeleveringsketen voor de bedrijfswaarde is gebaseerd op integratie met externe entiteiten. Bij het verbeteren van de bedrijfscontinuïteit bij servicestoringen moeten alle integratiepunten worden bekeken en beveiligd.  
Als u uw toeleveringsketen analyseert, moet externe communicatie op dezelfde manier als interne communicatie worden geanalyseerd. Zijn uw klanten afhankelijk van uw Exchange Online-servers als de enige manier om contact met u op te nemen? Hebt u bij uptime-onderbrekingen alternatieve communicatiemethoden beschikbaar en hebt u uw leveranciers hiervan op de hoogte gesteld? Hier ziet u een voorbeeld van een tabel waarin u kunt zien hoe u uw gedachten kunt organiseren.

|naam van externe entiteit|scenario gevolgen incident|geïntegreerde Microsoft 365-services|alternatieven|
|---------|---------|---------|---------|
|`vendor name`|e-mailstroom|Exchange Online is het enige communicatiemiddel met Contoso|externe Microsoft Teams-kanalen of samenwerkingssoftware van derden instellen          |
|`service supplier name`|chatten|Microsoft Teams|chatberichten van derden|
|`partner name`|spraak|Microsoft Teams|mobiele of openbare PSTN      |
|`supplier name`|bestandsdeling|extern gedeelde SharePoint-sites en OneDrive|bestandsdeling van derden         |
