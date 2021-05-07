---
title: Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager helpt organisaties bij het vereenvoudigen en automatiseren van risicobeoordelingen en stelt aanbevolen acties voor om risico's aan te pakken.
ms.openlocfilehash: f938bb6b82ee7e24dd58b66597f0af7a3a00a9a2
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162528"
---
# <a name="microsoft-compliance-manager"></a>Microsoft Compliance Manager

**In dit artikel:** Lees wat Compliance Manager is, hoe compliance wordt vereenvoudigd en risico's worden verkleind en wat de belangrijkste onderdelen zijn.

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>Nieuw: de GA-release van Compliance Manager

Compliance manager is nu algemeen beschikbaar (GA) als end-to-end compliancebeheeroplossing in [het Microsoft 365 compliancecentrum.](microsoft-365-compliance-center.md) Met deze release voltooit Compliance Manager de overgang van de vorige locatie in de Microsoft Service Trust Portal. Compliance manager is ook beschikbaar voor klanten van de Amerikaanse overheidsgemeenschap (GCC) GCC High en Ministerie van Defensie (DoD).

Wat begon als het openbare voorbeeld van compliancescore, is uitgegroeid tot een gecentraliseerde tool met verbeterde mogelijkheden voor compliancebeheer en een groter gebruiksgemak.  De GA-release bevat een grotere verzameling vooraf gebouwde evaluaties om u te helpen uw complianceactiviteiten te schalen.

**Meer informatie over de GA-release:**
- Met [onze veelgestelde vragen](compliance-manager-faq.md) wordt u uitgebreider door de ontwikkeling heen geslopen.
- Lees meer over verbeteringen van ga-functies in [dit blogbericht.](https://aka.ms/compliancemanager/GAblog)

Bekijk de onderstaande video om te zien hoe Compliance Manager kan helpen bij het vereenvoudigen van het beheer van compliance door uw organisatie:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>Wat is Compliance Manager

[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) is een functie in het [Microsoft 365 compliancecentrum](microsoft-365-compliance-center.md) waarmee u de nalevingsvereisten van uw organisatie met meer gemak en gemak kunt beheren. Compliance manager kan u helpen tijdens uw compliancetraject, van het inventariseren van uw risico's voor gegevensbescherming tot het beheren van de complexiteit van het implementeren van besturingselementen, het actueel houden van regelgeving en certificeringen en het rapporteren aan auditors.

Compliance manager helpt compliance te vereenvoudigen en risico's te beperken door:

- Vooraf gemaakte evaluaties voor algemene industrie- en regionale standaarden en -voorschriften, of aangepaste beoordelingen om te voldoen aan uw unieke nalevingsbehoeften (beschikbare beoordelingen zijn afhankelijk van uw licentieovereenkomst; [meer informatie).](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

- Werkstroommogelijkheden om u te helpen uw risicobeoordelingen efficiënt te voltooien met één hulpmiddel.

- Gedetailleerde stapsgewijs richtlijnen voor voorgestelde verbeteracties om u te helpen voldoen aan de standaarden en voorschriften die het meest relevant zijn voor uw organisatie. Voor acties die worden beheerd door Microsoft, ziet u implementatiedetails en controleresultaten.

- Een compliancescore op basis van risico's om inzicht te krijgen in uw nalevingshouding door uw voortgang bij het voltooien van verbeteracties te meten.

Uw Compliance Manager-dashboard toont uw huidige compliancescore, helpt u te zien wat er aandacht nodig heeft en begeleidt u bij belangrijke verbeteracties. Hieronder ziet u een voorbeeld van hoe uw Compliance Manager-dashboard eruit zal zien:

![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager-dashboard")

## <a name="understanding-your-compliance-score"></a>Inzicht krijgen in de nalevingsscore

Compliance Manager kent u punten toe voor het voltooien van verbeteracties die zijn ondernomen om te voldoen aan een verordening, standaard of beleid en combineert deze punten in een algemene compliancescore. Elke actie heeft een andere invloed op uw score, afhankelijk van de mogelijke risico's. Uw compliancescore kan helpen bij het bepalen van welke actie u zich moet concentreren om uw algemene nalevingsstatus te verbeteren.

Compliance Manager geeft u een eerste score op basis van de Microsoft 365 basislijn voor gegevensbescherming. Deze basislijn is een set besturingselementen met belangrijke voorschriften en standaarden voor gegevensbescherming en algemeen gegevensbeheer.

##### <a name="learn-more"></a>Meer informatie

[Meer inzicht in de berekening van de nalevingsscore.](compliance-score-calculation.md)

[Meer informatie over het werken met verbeteracties.](compliance-manager-improvement-actions.md)

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>Belangrijke elementen: besturingselementen, beoordelingen, sjablonen, verbeteracties

Compliance Manager gebruikt verschillende gegevenselementen om u te helpen bij het beheren van uw complianceactiviteiten. Terwijl u Compliance Manager gebruikt om complianceactiviteiten toe te wijzen, te testen en te controleren, is het handig om een basiskennis te hebben van de belangrijkste elementen: besturingselementen, beoordelingen, sjablonen en verbeteracties.

### <a name="controls"></a>Besturingselementen

Een besturingselement is een vereiste van een verordening, standaard of beleid. Het definieert hoe u systeemconfiguratie, organisatieproces en personen die verantwoordelijk zijn voor het voldoen aan een specifieke vereiste van een regelgeving, standaard of beleid, beoordeelt en beheert.

Compliance Manager houdt de volgende typen besturingselementen bij:

1. **Beheerde besturingselementen** van Microsoft: besturingselementen voor Microsoft-cloudservices, die microsoft verantwoordelijk is voor de implementatie
2. **Uw** besturingselementen: ook wel beheerde besturingselementen voor klanten genoemd, dit zijn besturingselementen die zijn geïmplementeerd en beheerd door uw organisatie
3. **Gedeelde** besturingselementen: dit zijn besturingselementen die zowel uw organisatie als Microsoft verantwoordelijkheid delen voor de implementatie

##### <a name="learn-more"></a>Meer informatie

[De voortgang van uw besturingselementen controleren.](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)

[Lees hoe Compliance Manager besturingselementen continu beoordeelt.](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)

### <a name="assessments"></a>Evaluaties

Een beoordeling bestaat uit het groeperen van besturingselementen uit een specifieke verordening, standaard of beleid. Als u de acties in een evaluatie voltooit, voldoet u aan de vereisten van een standaard, regelgeving of wet. U hebt bijvoorbeeld een beoordeling die, wanneer u alle acties binnen het programma voltooit, helpt om uw Microsoft 365 in overeenstemming te brengen met iso 27001-vereisten.

Beoordelingen bevatten verschillende onderdelen:

- **In-scopeservices:** de specifieke set Microsoft-services die van toepassing is op de beoordeling
- **Beheerde besturingselementen** van Microsoft: besturingselementen voor Microsoft-cloudservices, die Microsoft namens u implementeert
- **Uw** besturingselementen: ook wel beheerde besturingselementen voor klanten genoemd, dit zijn besturingselementen die zijn geïmplementeerd en beheerd door uw organisatie
- **Gedeelde** besturingselementen: dit zijn besturingselementen die zowel uw organisatie als Microsoft verantwoordelijkheid delen voor de implementatie
- **Beoordelingsscore:** toont uw voortgang bij het bereiken van totaal mogelijke punten uit acties binnen de beoordeling die worden beheerd door uw organisatie en door Microsoft

Wanneer u evaluaties maakt, wijst u deze toe aan een groep. U kunt groepen configureren op elke manier die het meest logisch is voor uw organisatie. U kunt bijvoorbeeld beoordelingen groepeert per auditjaar, regio, oplossing, teams binnen uw organisatie of op een andere manier. Wanneer u groepen hebt gemaakt, kunt u [uw Compliance Manager-dashboard filteren](compliance-manager-setup.md#filtering-your-dashboard-view) om uw score te bekijken op een of meer groepen.

##### <a name="learn-more"></a>Meer informatie

[Evaluaties maken en beheren in Compliance Manager.](compliance-manager-assessments.md)

### <a name="templates"></a>Sjablonen

Compliance Manager biedt sjablonen om u te helpen snel evaluaties te maken. U kunt deze sjablonen wijzigen om een beoordeling te maken die is geoptimaliseerd voor uw behoeften. U kunt ook een aangepaste beoordeling maken door een sjabloon te maken met uw eigen besturingselementen en acties. U wilt bijvoorbeeld dat een sjabloon betrekking heeft op een intern beheer van bedrijfsprocessen of een regionale gegevensbeschermingsstandaard die niet wordt gedekt door een van onze 325+ vooraf gebouwde beoordelingssjablonen.

##### <a name="learn-more"></a>Meer informatie

[Bekijk de lijst met beoordelingssjablonen die door Compliance Manager worden geleverd.](compliance-manager-templates-list.md)

[Gedetailleerde instructies voor het maken en wijzigen van sjablonen voor beoordelingen.](compliance-manager-templates.md)

### <a name="improvement-actions"></a>Verbeteracties

Verbeteracties helpen uw complianceactiviteiten te centraliseren. Elke verbeteringsactie biedt aanbevolen richtlijnen die bedoeld zijn om u te helpen bij het afstemmen op de regelgeving en standaarden voor gegevensbescherming. Verbeteracties kunnen worden toegewezen aan gebruikers in uw organisatie om implementatie- en testwerk uit te voeren. U kunt ook documentatie, notities en statusupdates opnemen in de actie voor verbetering.

##### <a name="learn-more"></a>Meer informatie

[Verbeteracties gebruiken om uw compliancewerkstroom te beheren.](compliance-manager-improvement-actions.md)

[Lees hoe acties van invloed zijn op uw nalevingsscore.](compliance-score-calculation.md#action-types-and-points)

## <a name="supported-languages"></a>Ondersteunde talen

Compliance manager is beschikbaar in de volgende talen:

- Engels
- Bahasa Indonesisch
- Bahasa Maleis
- Chinees (vereenvoudigd)
- Chinees (traditioneel)
- Czech
- Danish
- Dutch
- Finnish
- French
- German
- Hebrew
- Hungarian
- Italian
- Japanese
- Korean
- Noors
- Polish
- Portugees (Braziliaans)
- Russian
- Spanish
- Swedish
- Thai
- Turkish

## <a name="next-steps-set-up-and-customize"></a>Volgende stappen: instellen en aanpassen

Lees hoe u zich kunt aanmelden, machtigingen en rollen kunt toewijzen, instellingen kunt configureren en uw dashboardweergave kunt aanpassen in Aan de slag [met Compliance Manager.](compliance-manager-setup.md)

Pas Vervolgens Compliance Manager aan om u te helpen voldoen aan industriestandaarden die het belangrijkst zijn voor uw organisatie door [evaluaties in te stellen.](compliance-manager-assessments.md)