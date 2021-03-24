---
title: Prioriteit geven aan incidenten in Microsoft 365 Defender
description: Informatie over het filteren van incidenten in de incidentwachtrij in Microsoft 365 Defender
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
localization_priority: Normal
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
ms.openlocfilehash: 0683e0f2c9f4d46b3b644e2fec882a126aaab9b9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057273"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Prioriteit geven aan incidenten in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



Microsoft 365 Defender past correlatieanalyse toe en verzamelt alle gerelateerde waarschuwingen en onderzoeken van verschillende producten tot één incident. Microsoft 365 Defender activeert ook unieke waarschuwingen voor activiteiten die alleen kunnen worden geïdentificeerd als schadelijk, gezien de end-to-end zichtbaarheid die Microsoft 365 Defender heeft in het hele domein en de hele suite met producten. In deze weergave krijgt uw beveiligingsanalist het bredere aanvalsverhaal, waarmee ze complexe bedreigingen in de hele organisatie beter kunnen begrijpen en kunnen omgaan.


De **wachtrij Incidenten** toont een verzameling incidenten die zijn gemarkeerd op verschillende apparaten, gebruikers en postvakken. Het helpt u incidenten te sorteren om prioriteit te geven en een weloverwogen antwoordbesluit voor cyberbeveiliging te maken.


![Afbeelding van incidentenwachtrij](../../media/incidents-queue.png) 

Standaard worden in de wachtrij in het Microsoft 365-beveiligingscentrum incidenten weergegeven die de afgelopen 30 dagen zijn gezien. Het meest recente incident staat bovenaan de lijst, zodat u het eerst kunt zien.

De incidentwachtrij bevat aanpasbare kolommen die u inzicht geven in verschillende kenmerken van het incident of de opgenomen entiteiten. Op deze manier kunt u een weloverwogen beslissing nemen over de prioriteit van incidenten die moeten worden verwerkt.

Voor extra zichtbaarheid in één oogopslag worden met automatische naamgeving voor incidenten incidentnamen gegenereerd op basis van waarschuwingskenmerken, zoals het aantal eindpunten dat is beïnvloed, de betreffende gebruikers, detectiebronnen of categorieën. Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.

Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*

> [!NOTE]
> Incidenten die vóór de implementatie van automatische naamgeving voor incidenten hebben bestaan, worden niet gewijzigd.

In de wachtrij voor incidenten worden ook meerdere filteropties beschikbaar, waarmee u, wanneer deze wordt toegepast, alle bestaande incidenten in uw omgeving breed kunt opsnuiven of kunt besluiten zich te concentreren op een specifiek scenario of bedreiging. Door filters toe te passen op de incidentwachtrij, kan worden bepaald welk incident direct aandacht nodig heeft. 

## <a name="available-filters"></a>Beschikbare filters

### <a name="assigned-to"></a>Toegewezen aan
U kunt ervoor kiezen om waarschuwingen weer te geven die aan u zijn toegewezen of waarschuwingen die door automatisering worden verwerkt.

### <a name="categories"></a>Categorieën
Kies categorieën om zich te richten op specifieke tactieken, technieken of aanvalsonderdelen. 

### <a name="classification"></a>Classificatie
Filter incidenten op basis van de setclassificaties van de gerelateerde waarschuwingen. De waarden omvatten waar waarschuwingen, onwaar waarschuwingen of niet ingesteld.

### <a name="data-sensitivity"></a>Gegevensgevoeligheid
Sommige aanvallen richten zich op targeting om gevoelige of waardevolle gegevens te exfiltreren. Door een filter toe te passen om te zien of er gevoelige gegevens bij het incident betrokken zijn, kunt u snel bepalen of gevoelige informatie mogelijk is gehackt en kunt u prioriteit geven aan het oplossen van deze incidenten.

>[!NOTE]
>Alleen van toepassing als Microsoft Information Protection is ingeschakeld.

### <a name="device-group"></a>Apparaatgroep
Filteren op gedefinieerde apparaatgroepen.

### <a name="investigation-state"></a>Onderzoekstoestand
Filter incidenten op basis van de status van automatisch onderzoek. 

### <a name="multiple-categories"></a>Meerdere categorieën 
U kunt ervoor kiezen om alleen incidenten te zien die zijn toegesneden op meerdere categorieën en zo mogelijk meer schade kunnen veroorzaken. 

### <a name="multiple-service-sources"></a>Meerdere servicebronnen 
Filter om alleen incidenten te zien die waarschuwingen uit verschillende bronnen bevatten (Microsoft Defender voor Eindpunt, Microsoft Cloud App-beveiliging, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365).

### <a name="os-platform"></a>BESTURINGSSYSTEEM-platform
Beperk de weergave van de incidentwachtrij per besturingssysteem.

### <a name="service-sources"></a>Servicebronnen
Door een specifieke bron te kiezen, kunt u zich richten op incidenten die ten minste één waarschuwing uit die gekozen bron bevatten. 

### <a name="severity"></a>Ernst
De ernst van een incident is een indicatie van de invloed die het kan hebben op uw activa. Hoe hoger de ernst, hoe groter de impact en meestal de meest directe aandacht. 

### <a name="status"></a>Status
U kunt ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke actief of opgelost zijn.




## <a name="next-steps"></a>Volgende stappen
Nadat u hebt vastgesteld welk incident de hoogste prioriteit heeft, kunt u verder onderzoek doen naar een incident.
- [Incidenten onderzoeken](investigate-incidents.md)


## <a name="see-also"></a>Zie ook
- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten onderzoeken](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
