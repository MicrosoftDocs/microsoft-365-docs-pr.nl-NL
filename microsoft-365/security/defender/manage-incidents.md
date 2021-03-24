---
title: Incidenten beheren in Microsoft 365 Defender
description: Informatie over het toewijzen, bijwerken van de status,
keywords: incident, incidenten, waarschuwingen, gecorreleerde waarschuwingen, toewijzen, bijwerken, status, beheren, classificatie, microsoft, 365, m365
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
ms.openlocfilehash: 4e216f841c8728b1cabd98a931e7326f53344a74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058601"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Incidenten beheren in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



Het beheren van incidenten is essentieel om ervoor te zorgen dat bedreigingen worden opgenomen en aangepakt. In Microsoft 365 Defender hebt u toegang tot het beheren van incidenten op apparaten, gebruikers en postvakken. 


U kunt incidenten beheren door een incident te selecteren in de **wachtrij Incidenten.** 

U kunt de naam van een incident bewerken, oplossen, de classificatie en bepaling ervan instellen. U kunt het incident ook aan uzelf toewijzen, incidentlabels en opmerkingen toevoegen.

In gevallen waarin u tijdens het onderzoeken waarschuwingen van het ene incident naar het andere wilt verplaatsen, kunt u dit ook doen via het tabblad Waarschuwingen, waardoor een groter of kleiner incident wordt gemaakt met alle relevante waarschuwingen.

## <a name="edit-incident-name"></a>Naam van incident bewerken
Incidenten krijgen automatisch een naam toegewezen op basis van waarschuwingskenmerken, zoals het aantal betrokken eindpunten, beïnvloede gebruikers, detectiebronnen of categorieën. Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.

Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*

U kunt de naam van het incident wijzigen om beter af te stemmen op de naamgevingsconventie van uw voorkeur.

> [!NOTE]
> Incidenten die vóór de implementatie van de functie voor automatische naamgeving van incidenten hebben bestaan, behouden hun naam.



## <a name="assign-incidents"></a>Incidenten toewijzen
Als er nog geen incident is toegewezen, kunt u Toewijzen aan **mij** selecteren om het incident aan uzelf toe te wijzen. Als u dit doet, wordt ervan uit gegaan dat u niet alleen eigenaar bent van het incident, maar ook van alle waarschuwingen die aan het incident zijn gekoppeld.

## <a name="set-status-and-classification"></a>Status en classificatie instellen
### <a name="incident-status"></a>Incidentstatus
U kunt incidenten categoriseren (als **Actief** of **Opgelost)** door hun status te wijzigen naarmate het onderzoek vordert. Op deze manier kunt u organiseren en beheren hoe uw team kan reageren op incidenten.

Uw SOC-analist kan bijvoorbeeld de **urgente** Actieve incidenten van vandaag bekijken en besluiten deze aan zichzelf toe te wijzen voor onderzoek.

Uw SOC-analist kan het incident ook instellen als **Opgelost** als het incident is opgelost. Door een incident op te lossen, worden automatisch alle waarschuwingen gesloten die deel uitmaken van het incident en worden ze nog steeds geopend. 

### <a name="classification-and-determination"></a>Classificatie en bepaling
U kunt ervoor kiezen geen classificatie in te stellen of te bepalen of een incident waar of onwaar is. Als u dit doet, kan het team patronen zien en er van leren. 

## <a name="add-comments"></a>Opmerkingen toevoegen
U kunt opmerkingen toevoegen en historische gebeurtenissen over een incident bekijken om eerdere wijzigingen in het incident weer te geven.

Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze opgenomen in de sectie Opmerkingen en geschiedenis.

Toegevoegde opmerkingen worden direct weergegeven in het deelvenster.

## <a name="add-incident-tags"></a>Incidentlabels toevoegen
U kunt aangepaste tags toevoegen aan een incident, bijvoorbeeld om een vlag toe te voegen aan een groep incidenten met een gemeenschappelijke kenmerken. U kunt later de wachtrij voor incidenten filteren op alle incidenten die een specifieke tag bevatten.
