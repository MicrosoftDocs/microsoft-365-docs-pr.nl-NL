---
title: Prioriteit geven aan incidenten in Microsoft 365 Defender
description: Informatie over het filteren van incidenten uit de wachtrij voor incidenten in Microsoft 365 Defender
keywords: incident, wachtrij, overzicht, apparaten, identiteiten, gebruikers, postvak, e-mail, incidenten
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929292"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Prioriteit geven aan incidenten in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



Microsoft 365 Defender past correlatieanalyses toe en verzamelt alle gerelateerde waarschuwingen en onderzoeken van verschillende producten tot één incident. Microsoft 365 Defender activeert ook unieke waarschuwingen voor activiteiten die alleen kunnen worden geïdentificeerd als schadelijk, gegeven de end-to-end zichtbaarheid die Microsoft 365 Defender heeft voor het hele domein en de suite met producten. Deze weergave geeft uw beveiligingsanalist de bredere verhaal over aanvallen, waardoor ze complexe bedreigingen in de hele organisatie beter kunnen begrijpen en kunnen omgaan.


De **wachtrij incidenten** toont een verzameling incidenten die werden gemarkeerd voor apparaten, gebruikers en postvakken. Het helpt u bij het sorteren van incidenten om prioriteiten te stellen en een weloverwogen antwoordbeslissing te maken.


![Afbeelding van de wachtrij met incidenten](../../media/incidents-queue.png) 

In de wachtrij in het Microsoft 365-beveiligingscentrum worden standaard incidenten weergegeven van de afgelopen 30 dagen. Het meest recente incident staat bovenaan de lijst, zodat u het als eerste kunt zien.

De incidentwachtrij bevat aanpasbare kolommen die u inzicht geven in verschillende kenmerken van het incident of de entiteiten in de gebeurtenis. Dit helpt u een weloverwogen beslissing te nemen met betrekking tot prioriteit van incidenten die moeten worden verwerkt.

Voor extra zichtbaarheid in een oogopslag worden met automatische naamgeving van incidenten incidentnamen gegenereerd op basis van waarschuwingskenmerken, zoals het aantal beïnvloede eindpunten, betrokken gebruikers, detectiebronnen of categorieën. Op deze manier kunt u snel de omvang van het incident begrijpen.

Bijvoorbeeld: *Incident met meerdere stadiums voor meerdere eindpunten gerapporteerd door meerdere bronnen.*

> [!NOTE]
> Incidenten die zich vóór de implementatie van automatische naamgeving van incidenten hebben voorgedaan, worden niet gewijzigd.

In de incidentwachtrij worden ook meerdere filteropties beschikbaar, waarmee u wanneer deze wordt toegepast, alle bestaande incidenten in uw omgeving breed kunt opruimen of kunt besluiten om te focussen op een bepaald scenario of risico. Door filters op de incidentwachtrij toe te passen, kunt u bepalen welk incident onmiddellijke aandacht vereist. 

## <a name="available-filters"></a>Beschikbare filters

### <a name="assigned-to"></a>Toegewezen aan
U kunt ervoor kiezen om waarschuwingen weer te geven die zijn toegewezen aan u of de waarschuwingen die worden verwerkt door automatisering.

### <a name="categories"></a>Categorieën
Kies categorieën om u te richten op specifieke technieken, technieken of elementen voor aanvallen. 

### <a name="classification"></a>Classificatie
Filter incidenten op basis van de classificaties van de gerelateerde waarschuwingen. De waarden zijn onder andere waar-waarschuwingen, onwaar-waarschuwingen of niet-ingesteld.

### <a name="data-sensitivity"></a>Gegevensgevoeligheid
Sommige aanvallen richten zich op het verzamelen van gevoelige of waardevolle gegevens. Door een filter toe te passen om te zien of er gevoelige gegevens bij het incident zijn betrokken, kunt u snel vaststellen of gevoelige informatie mogelijk is gehackt en prioriteit geven aan de adressering van die incidenten.

>[!NOTE]
>Alleen van toepassing als Microsoft Information Protection is ingeschakeld.

### <a name="device-group"></a>Apparaatgroep
Filteren op gedefinieerde apparaatgroepen.

### <a name="investigation-state"></a>Staat van onderzoek
Incidenten filteren op de status van geautomatiseerd onderzoek. 

### <a name="multiple-categories"></a>Meerdere categorieën 
U kunt ervoor kiezen om alleen incidenten te zien die zijn toegesneden aan meerdere categorieën en die daardoor meer schade kunnen veroorzaken. 

### <a name="multiple-service-sources"></a>Meerdere servicebronnen 
Filter om alleen incidenten te zien die waarschuwingen van verschillende bronnen bevatten (Microsoft Defender voor eindpunt, Microsoft Cloud App-beveiliging, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365).

### <a name="os-platform"></a>Besturingssysteemplatform
Beperk de weergave van de incidentenwachtrij per besturingssysteem.

### <a name="service-sources"></a>Servicebronnen
Door een specifieke bron te kiezen, kunt u zich richten op incidenten die ten minste één waarschuwing van die gekozen bron bevatten. 

### <a name="severity"></a>Ernst
De ernst van een incident is afhankelijk van de invloed die het op uw assets kan hebben. Hoe hoger de ernst, hoe groter de impact en meestal de meest directe aandacht vereist. 

### <a name="status"></a>Status
U kunt ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke actief of opgelost zijn.




## <a name="next-steps"></a>Volgende stappen
Nadat u hebt bepaald welk incident de hoogste prioriteit vereist, kunt u verder werken aan een incident.
- [Incidenten onderzoeken](investigate-incidents.md)


## <a name="see-also"></a>Zie ook
- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten onderzoeken](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
