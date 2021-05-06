---
title: Juridische onderzoeken beheren in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
ms.custom:
- seo-marvel-apr2020
description: Gebruik eDiscovery-zaken in het Beveiligings- & compliancecentrum in Office 365 om het juridische onderzoek van uw organisatie te beheren.
ms.openlocfilehash: c052daab8de33e21cccc3c638ab4995a007f60fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161756"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Juridische onderzoeken beheren in Microsoft 365

Organisaties hebben veel redenen om te reageren op een juridische zaak waarbij bepaalde leidinggevenden of andere werknemers in uw organisatie betrokken zijn. Dit kan betekenen dat u snel specifieke informatie kunt vinden en bewaren in e-mail, documenten, chatgesprekken en andere inhoudslocaties die door personen worden gebruikt in hun dagelijkse werktaken. U kunt deze en veel andere soortgelijke activiteiten uitvoeren met behulp van de eDiscovery-casehulpmiddelen in het beveiligings- en compliancecentrum.
  
**Wilt u weten hoe Microsoft zijn eDiscovery-onderzoeken beheert?** Hier is een technisch [whitepaper](https://go.microsoft.com/fwlink/?linkid=852161) dat u kunt downloaden waarin wordt uitgelegd hoe we dezelfde zoek- en onderzoekshulpmiddelen gebruiken om onze interne eDiscovery-werkstroom te beheren.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Juridische onderzoeken beheren met eDiscovery-zaken

Met eDiscovery-zaken kunt u bepalen wie eDiscovery-zaken in uw organisatie kan maken, openen en beheren. Gebruik cases om leden toe te voegen en te bepalen welke soorten acties ze kunnen uitvoeren, plaats inhoudslocaties die relevant zijn voor een juridische zaak, en gebruik het hulpprogramma Inhoud zoeken om de locaties in de wacht te zetten voor inhoud die mogelijk reageert op uw zaak. Vervolgens kunt u deze resultaten ook exporteren en downloaden voor verder onderzoek door externe revisoren.
  
- [Beheer uw eDiscovery-werkstroom](./get-started-core-ediscovery.md) door eDiscovery-zaken te maken en te gebruiken voor elk juridisch onderzoek dat uw organisatie moet uitvoeren.

- [Wijs eDiscovery-machtigingen toe om](assign-ediscovery-permissions.md) te bepalen wie eDiscovery-zaken in uw organisatie kan maken en beheren.

- [Stel compliancegrenzen in om de inhoudslocaties](set-up-compliance-boundaries.md) van gebruikers te bepalen die eDiscovery-beheerders kunnen zoeken.

- [Zoek naar inhoud](search-for-content.md) in uw organisatie.

### <a name="use-scripts-for-advanced-scenarios"></a>Scripts gebruiken voor geavanceerde scenario's

Net als in de vorige sectie met scripts voor zoekscenario's voor inhoud, hebben we ook enkele PowerShell-scripts van het Beveiligings- & Compliancecentrum gemaakt om u te helpen bij het beheren van eDiscovery-gevallen.
  
- [Maak een eDiscovery-holdrapport](create-a-report-on-holds-in-ediscovery-cases.md) dat informatie bevat over alle in-holds die zijn gekoppeld aan eDiscovery-zaken in uw organisatie.

- [Voeg postvakken en OneDrive voor](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) een lijst met gebruikers toe aan een eDiscovery-wachtlijst.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Juridische onderzoeken beheren met de Advanced eDiscovery oplossing in Microsoft 365

De Advanced eDiscovery in Microsoft 365 is gebaseerd op de bestaande eDiscovery- en analysemogelijkheden in Office 365. Deze nieuwe oplossing, *Advanced eDiscovery,* biedt een end-to-end werkstroom voor het bewaren, verzamelen, controleren, analyseren en exporteren van inhoud die reageert op interne en externe onderzoeken van uw organisatie. Daarnaast kunnen juridische teams de volledige werkstroom voor meldingen over juridische in- en uit te houden beheren om te communiceren met bewaarders die betrokken zijn bij een zaak.

Advanced eDiscovery is een E5-abonnement vereist voor uw Microsoft 365 of Office 365 organisatie. Zie Een licentie instellen voor [meer Advanced eDiscovery.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)

Hier is een kort overzicht van de ingebouwde werkstroom in Advanced eDiscovery. Zie De werkstroom Advanced eDiscovery [beheren voor meer informatie.](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

- [Maak een zaak om](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) aan de slag te gaan.

- [Beheerders beheren door](managing-custodians.md) ze toe te voegen aan een zaak en inhoud in hun postvak, OneDrive account en Microsoft Teams waar ze lid van zijn.

- [Beheer communicatie](managing-custodian-communications.md) met bewaarders door het proces voor de melding van de wettelijke bewaarplicht te automatiseren.

- [Index bewaargegevens en](processing-data-for-case.md) fixeer indexeringsfouten, zodat u effectief gegevens kunt verzamelen voor uw onderzoeken.

- [Verzamel gegevens](collecting-data-for-ediscovery.md) voor een zaak en voeg [deze toe aan een revisieset](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) voor verder onderzoek.

- [Documenten,](view-documents-in-review-set.md) [querygegevens en](review-set-search.md) [tagitems](tagging-documents.md) weergeven in een revisieset.

- [Analyseer casegegevens met](analyzing-data-in-review-set.md) geavanceerde analysehulpmiddelen.

- [Export case data](exporting-data-ediscover20.md) for review by outside counsel.

- [Langlopende taken beheren](managing-jobs-ediscovery20.md) in Advanced eDiscovery.