---
title: Prioriteit geven aan incidenten in Microsoft Threat Protection
description: Meer informatie over het prioriteren van incidenten in de wachtrij voor incidenten in Microsoft Threat Protection
keywords: incident, wachtrij, overzicht, apparaten, identiteiten, gebruikers, postvak, e-mail, incidenten
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: ef10eede38128bbf9b23537d860113b71f603089
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42805719"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>Prioriteit geven aan incidenten in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



Microsoft Threat Protection past correlatieanalyses toe en verzamelt alle gerelateerde waarschuwingen en onderzoeken van verschillende producten in één incident. Microsoft Threat Protection activeert ook unieke waarschuwingen over activiteiten die alleen kunnen worden geïdentificeerd als kwaadaardig gezien de end-to-end zichtbaarheid die Microsoft Threat Protection heeft over het hele landgoed en de suite van producten. Door dit te doen, Microsoft Threat Protection vertelt de bredere aanval verhaal, waardoor een security operations analist te begrijpen en te gaan met complexe bedreigingen in de hele organisatie.


**In de wachtrij Incidenten** wordt een verzameling incidenten weergegeven die zijn gemarkeerd vanaf verschillende apparaten, gebruikers en postvakken. Het helpt u bij het sorteren van incidenten om prioriteiten te stellen en een weloverwogen reactiebeslissing over cyberbeveiliging te maken.


![Afbeelding van incidentenwachtrij](../../media/incidents-queue.png) 

Standaard worden in de wachtrij in het Microsoft 365-beveiligingscentrum incidenten weergegeven die in de afgelopen 30 dagen zijn gezien, waarbij het meest recente incident bovenaan de lijst wordt weergegeven, zodat u eerst de meest recente incidenten zien.

De wachtrij voor incidenten stelt aanpasbare kolommen bloot die u inzicht geven in de verschillende kenmerken van het incident of de opgenomen entiteiten, zodat u een weloverwogen beslissing nemen over prioritering van te behandelen incidenten. 

De incidentwachtrij stelt ook meerdere filteropties bloot, die u bij het toepassen in staat stellen om een brede sweep van alle bestaande incidenten in uw omgeving uit te voeren of te besluiten zich te concentreren op een specifiek scenario of bedreiging. Het toepassen van filters in de incidentenwachtrij kan helpen bepalen welk incident onmiddellijke aandacht vereist. 

## <a name="available-filters"></a>Beschikbare filters

### <a name="status"></a>Status
U ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke incidenten actief of opgelost zijn.

### <a name="severity"></a>Ernst
De ernst van een incident is indicatief voor de impact die het kan hebben op uw activa. Hoe hoger de ernst, hoe groter de impact en vereist meestal de meest directe aandacht. 

### <a name="assigned-to-owner"></a>Toegewezen aan (eigenaar)
U ervoor kiezen de lijst te filteren door toegewezen te selecteren aan iedereen of degenen die aan u zijn toegewezen.

### <a name="multiple-alerts"></a>Meerdere waarschuwingen 
Filter om alleen incidenten te zien die meer dan één waarschuwing bevatten. Dit kan een indicatie zijn voor een aanval die complexer is of vorderde in de kill chain. 


### <a name="multiple-service-sources"></a>Meerdere servicebronnen 
Filteren om alleen incidenten te zien die waarschuwingen uit verschillende bronnen bevatten (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)
### <a name="service-sources"></a>Servicebronnen
Door een specifieke bron te kiezen, u zich richten op incidenten die ten minste één waarschuwing van die gekozen bron bevatten. 

### <a name="multiple-categories"></a>Meerdere categorieën 
U ervoor kiezen om alleen incidenten te zien die in kaart zijn gebracht in meerdere categorieën van de kill chain en mogelijk meer schade kunnen veroorzaken. 

### <a name="categories"></a>Categorieën
Kies specifieke categorieën om u te concentreren op een specifieke stap in de kill chain

### <a name="data-sensitivity"></a>Gegevensgevoeligheid
Sommige aanvallen richten zich op targeting om gevoelige of waardevolle gegevens te exfiltreren. Door een filter toe te passen om te zien of gevoelige gegevens betrokken zijn bij het incident, u snel bepalen of gevoelige informatie mogelijk is gecompromitteerd en prioriteit geven aan het aanpakken van die incidenten.

>[!NOTE]
>Alleen van toepassing als Microsoft Information Protection is ingeschakeld.


## <a name="next-steps"></a>Volgende stappen
Nadat u hebt vastgesteld welk incident de hoogste prioriteit vereist, u verder onderzoek doen naar een incident.
- [Incidenten onderzoeken](investigate-incidents.md)


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten onderzoeken](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
