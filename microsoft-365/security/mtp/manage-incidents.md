---
title: Incidenten beheren in Microsoft Threat Protection
description: Meer informatie over het toewijzen, bijwerken van de status,
keywords: incident, incidenten, waarschuwingen, gecorreleerde waarschuwingen, toewijzen, bijwerken, status, beheren, classificatie, Microsoft, 365, m365
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
ms.openlocfilehash: f711cc2ff38f15dfd22097e37a1dec42719eb5aa
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148112"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a>Incidenten beheren in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft Threat Protection



Het beheren van incidenten is essentieel om ervoor te zorgen dat bedreigingen worden beperkt en aangepakt. In Microsoft Threat Protection hebt u toegang tot het beheren van incidenten op apparaten, gebruikers en postvakken. 


U incidenten beheren door een incident te selecteren in de **wachtrij Incidenten**. 

U de naam van een incident bewerken, oplossen, de classificatie en bepaling instellen. U het incident ook aan uzelf toewijzen, incidenttags en opmerkingen toevoegen.

In gevallen waarin u tijdens het onderzoek waarschuwingen van het ene incident naar het andere wilt verplaatsen, u dit ook doen vanaf het tabblad Waarschuwingen, waardoor een groter of kleiner incident ontstaat dat alle relevante waarschuwingen bevat.

## <a name="edit-incident-name"></a>Incidentnaam bewerken
Standaard krijgt een incident een getal toegewezen. U de naam van het incident wijzigen om beter af te stemmen op uw voorkeursnaamgevingsconventie.

> [!TIP]
> Voor extra zichtbaarheid in één oogopslag genereert automatische incidentnaamgeving, die momenteel in openbare preview is, incidentnamen op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, de getroffen gebruikers, detectiebronnen of categorieën. Hierdoor u snel inzicht krijgen in de omvang van het incident.
>
> Bijvoorbeeld: *Multi-stage incident op meerdere eindpunten gerapporteerd door meerdere bronnen.*
>
> Incidenten die vóór de uitrol van automatische incidentnaamgeving bestonden, worden niet gewijzigd.
>
> Meer informatie over [het inschakelen van voorbeeldfuncties](preview.md#turn-on-preview-features).

## <a name="assign-incidents"></a>Incidenten toewijzen
Als er nog geen incident is toegewezen, u **Toewijzen aan mij** selecteren om het incident aan uzelf toe te wijzen. Daarbij neemt eigendom van niet alleen het incident, maar ook alle waarschuwingen in verband met het.

## <a name="set-status-and-classification"></a>Status en classificatie instellen
### <a name="incident-status"></a>Incidentstatus
U incidenten categoriseren (als **Actief**of **Opgelost)** door hun status te wijzigen naarmate uw onderzoek vordert. Zo u organiseren en beheren hoe uw team kan reageren op incidenten.

Uw SOC-analist kan bijvoorbeeld de urgente **Actieve** incidenten voor de dag bekijken en besluiten deze aan zichzelf toe te wijzen voor onderzoek.

Als alternatief kan uw SOC-analist het incident instellen als **Opgelost** als het incident is verholpen. Als u een incident op lost, worden automatisch alle waarschuwingen gesloten die deel uitmaken van het incident en nog steeds worden geopend. 

### <a name="classification-and-determination"></a>Indeling en bepaling
U ervoor kiezen om geen classificatie in te stellen of te beslissen om aan te geven of een incident waar of onwaar is. Hierdoor helpt het team patronen te zien en ervan te leren. 

## <a name="add-comments"></a>Opmerkingen toevoegen
U opmerkingen toevoegen en historische gebeurtenissen over een incident bekijken om eerdere wijzigingen te zien.

Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze opgenomen in de sectie Opmerkingen en geschiedenis.

Toegevoegde opmerkingen verschijnen direct in het deelvenster.

## <a name="add-incident-tags"></a>Incidenttags toevoegen
U aangepaste tags toevoegen aan een incident, bijvoorbeeld om een groep incidenten met een gemeenschappelijke kenmerken te markeren. U later de wachtrij voor incidenten filteren op alle incidenten die een specifieke tag bevatten.