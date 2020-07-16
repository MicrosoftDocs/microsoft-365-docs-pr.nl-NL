---
title: Prioriteit geven aan incidenten in Microsoft Threat Protection
description: Meer informatie over het prioriteren van incidenten vanuit de wachtrij voor incidenten in Microsoft Threat Protection
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
ms.openlocfilehash: d827484a440b291bccd45b58e977fbcb280680f2
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148134"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>Prioriteit geven aan incidenten in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft Threat Protection



Microsoft Threat Protection past correlatieanalyses toe en verzamelt alle gerelateerde waarschuwingen en onderzoeken van verschillende producten in één incident. Microsoft Threat Protection activeert ook unieke waarschuwingen over activiteiten die alleen als kwaadaardig kunnen worden geïdentificeerd, gezien de end-to-end zichtbaarheid die Microsoft Threat Protection heeft over het hele landgoed en een reeks producten. Door dit te doen, Microsoft Threat Protection vertelt de bredere aanval verhaal, waardoor een security operations analist te begrijpen en omgaan met complexe bedreigingen in de hele organisatie.


In **de wachtrij Incidenten** wordt een verzameling incidenten weergegeven die zijn gemarkeerd vanaf verschillende apparaten, gebruikers en postvakken. Het helpt u bij het sorteren van incidenten om prioriteit te geven en een weloverwogen beslissing over cyberbeveiliging te creëren.


![Afbeelding van incidentenwachtrij](../../media/incidents-queue.png) 

Standaard wordt in de wachtrij in het Microsoft 365-beveiligingscentrum incidenten weergegeven die in de afgelopen 30 dagen zijn gezien, waarbij het meest recente incident bovenaan de lijst wordt weergegeven, zodat u eerst de meest recente incidenten zien.

De incidentwachtrij stelt aanpasbare kolommen bloot die u inzicht geven in verschillende kenmerken van het incident of de opgenomen entiteiten, zodat u een weloverwogen beslissing nemen over prioritering van incidenten die moeten worden verwerkt.

Voor extra zichtbaarheid in één oogopslag genereert automatische incidentnaamgeving, die momenteel in openbare preview is, incidentnamen op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, de getroffen gebruikers, detectiebronnen of categorieën. Hierdoor u snel inzicht krijgen in de omvang van het incident.

Bijvoorbeeld: *Multi-stage incident op meerdere eindpunten gerapporteerd door meerdere bronnen.*

> [!NOTE]
> Incidenten die vóór de uitrol van automatische incidentnaamgeving bestonden, worden niet gewijzigd.

Meer informatie over [het inschakelen van voorbeeldfuncties](preview.md#turn-on-preview-features).

De incidentwachtrij stelt ook meerdere filteropties bloot, waarmee u, wanneer deze wordt toegepast, kiezen om een breed onderzoek uit te voeren van alle bestaande incidenten in uw omgeving, of besluit zich te concentreren op een specifiek scenario of bedreiging. Het toepassen van filters op de incidentwachtrij kan helpen bepalen welk incident onmiddellijke aandacht vereist. 

## <a name="available-filters"></a>Beschikbare filters

### <a name="status"></a>Status
U ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke incidenten actief of opgelost zijn.

### <a name="severity"></a>Ernst
De ernst van een incident is indicatief voor de impact die het kan hebben in uw activa. Hoe hoger de ernst, hoe groter de impact en vereist meestal de meest directe aandacht. 

### <a name="assigned-to-owner"></a>Toegewezen aan (eigenaar)
U ervoor kiezen om de lijst te filteren door toegewezen te selecteren aan iedereen of degenen die aan u zijn toegewezen.

### <a name="multiple-alerts"></a>Meerdere waarschuwingen 
Filter alleen incidenten met meer dan één waarschuwing. Dit kan een indicatie zijn voor een aanval die complexer is of vorderde in de kill chain. 


### <a name="multiple-service-sources"></a>Meerdere servicebronnen 
Filter alleen om incidenten te zien die waarschuwingen uit verschillende bronnen bevatten (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)
### <a name="service-sources"></a>Servicebronnen
Door een specifieke bron te kiezen, u zich richten op incidenten die ten minste één waarschuwing van die gekozen bron bevatten. 

### <a name="multiple-categories"></a>Meerdere rubrieken 
U ervoor kiezen om alleen incidenten te zien die zijn toegewezen aan meerdere categorieën van de kill chain en mogelijk meer schade kunnen veroorzaken. 

### <a name="categories"></a>Categorieën
Kies specifieke categorieën om je te concentreren op een specifieke stap in de kill chain

### <a name="data-sensitivity"></a>Gegevensgevoeligheid
Sommige aanvallen richten zich op targeting om gevoelige of waardevolle gegevens te exfiltreren. Door een filter toe te passen om te zien of er gevoelige gegevens bij het incident betrokken zijn, u snel bepalen of gevoelige informatie mogelijk is gecompromitteerd en prioriteit geven aan het aanpakken van deze incidenten.

>[!NOTE]
>Alleen van toepassing als Microsoft Information Protection is ingeschakeld.


## <a name="next-steps"></a>Volgende stappen
Nadat u hebt vastgesteld welk incident de hoogste prioriteit vereist, u verder onderzoek doen naar een incident.
- [Incidenten onderzoeken](investigate-incidents.md)


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten onderzoeken](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
