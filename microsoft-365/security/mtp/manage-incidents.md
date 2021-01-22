---
title: Incidenten beheren in Microsoft 365 Defender
description: Informatie over het toewijzen, bijwerken van de status,
keywords: incident, incidenten, waarschuwingen, correleren waarschuwingen, toewijzen, bijwerken, status, beheren, classificatie, microsoft, 365, m365
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
ms.openlocfilehash: 90d9d397b8baf0ffdb9844a0f068f142a5c7fd48
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930628"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Incidenten beheren in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



Het beheren van incidenten is essentieel om ervoor te zorgen dat bedreigingen worden opgenomen en aangepakt. In Microsoft 365 Defender hebt u toegang tot het beheren van incidenten op apparaten, gebruikers en postvakken. 


U kunt incidenten beheren door een incident te selecteren in de **wachtrij Incidenten.** 

U kunt de naam van een incident bewerken, deze oplossen en de classificatie en bepalingen bepalen. U kunt het incident ook aan uzelf toewijzen en incidentlabels en opmerkingen toevoegen.

In gevallen waarin u tijdens het onderzoeken waarschuwingen tussen twee incidenten wilt verplaatsen, kunt u dit ook doen vanaf het tabblad Waarschuwingen, waardoor een groter of kleiner incident wordt gemaakt dat alle relevante waarschuwingen bevat.

## <a name="edit-incident-name"></a>Naam van incident bewerken
Incidenten krijgen automatisch een naam toegewezen op basis van waarschuwingskenmerken, zoals het aantal beïnvloede eindpunten, betrokken gebruikers, detectiebronnen of categorieën. Op deze manier kunt u snel de omvang van het incident begrijpen.

Bijvoorbeeld: *Incident met meerdere stadiums voor meerdere eindpunten gerapporteerd door meerdere bronnen.*

U kunt de naam van het incident aanpassen om deze beter aan te passen aan de naamconventie van uw voorkeur.

> [!NOTE]
> Incidenten die bestond vóór de implementatie van de functie voor automatische naamgeving van incidenten behouden hun naam.



## <a name="assign-incidents"></a>Incidenten toewijzen
Als een incident nog niet is toegewezen, kunt u Aan mij toewijzen selecteren om **het** incident aan uzelf toe te wijzen. Als u dit doet, wordt ervan uit gegaan dat u niet alleen eigenaar bent van het incident, maar ook van alle waarschuwingen die aan het incident zijn gekoppeld.

## <a name="set-status-and-classification"></a>Status en classificatie instellen
### <a name="incident-status"></a>Incidentstatus
U kunt incidenten categoriseren (als **Actief** of **Opgelost)** door de status te wijzigen naarmate het onderzoek vordert. Zo kunt u organiseren en beheren hoe uw team op incidenten kan reageren.

Uw SOC-analist kan bijvoorbeeld  de urgent actieve incidenten voor die dag beoordelen en deze toewijzen voor onderzoek.

Uw SOC-analist kan het  incident ook instellen als Opgelost als het incident is opgelost. Door een incident op te lossen, worden automatisch alle waarschuwingen gesloten die deel uitmaken van het incident en nog steeds zijn geopend. 

### <a name="classification-and-determination"></a>Classificatie en bepalingen
U kunt ervoor kiezen geen classificatie in te stellen of te bepalen of een incident waar of onwaar is. Hierdoor kan het team patronen zien en van deze patronen leren. 

## <a name="add-comments"></a>Opmerkingen toevoegen
U kunt opmerkingen toevoegen en historische gebeurtenissen over een incident bekijken om eerdere wijzigingen in het incident te bekijken.

Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze vastgelegd in de sectie Opmerkingen en geschiedenis.

Toegevoegde opmerkingen worden direct weergegeven in het deelvenster.

## <a name="add-incident-tags"></a>Incidentlabels toevoegen
U kunt aangepaste tags toevoegen aan een incident, bijvoorbeeld om een groep incidenten met gemeenschappelijke kenmerken te markeren. U kunt de wachtrij met incidenten later filteren op alle incidenten die een specifieke tag bevatten.
