---
title: Incidenten beheren in Microsoft 365 Defender
description: Informatie over het toewijzen, bijwerken van de status,
keywords: incident, incidenten, analyseren, antwoord, waarschuwingen, gecorreleerd waarschuwingen, toewijzen, bijwerken, status, beheren, classificatie, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 725e6226a56b3aae3670cde18969afdda1ec1940
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530836"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Incidenten beheren in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Incidentbeheer is essentieel om ervoor te zorgen dat bedreigingen worden opgenomen en aangepakt.

U beheert incidenten van **incidenten & waarschuwingen > incidenten** tijdens de snelle start van het Microsoft 365 beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com) Hier is een voorbeeld.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Voorbeeld van de incidentwachtrij":::

Dit zijn de manieren waarop u uw incidenten kunt beheren:

- [De naam van het incident bewerken](#edit-the-incident-name)
- [Incidentlabels toevoegen](#add-incident-tags)
- [Het incident toewijzen aan een gebruikersaccount](#assign-incidents)
- [Deze oplossen](#resolve-an-incident)
- [De classificatie en bepaling ervan instellen](#set-the-classification-and-determination)
- [Opmerkingen toevoegen](#add-comments)

U kunt incidenten beheren vanuit het deelvenster **Incident beheren** voor een incident. Hier is een voorbeeld.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Voorbeeld van het deelvenster Incident beheren van een incident":::

U kunt dit deelvenster weergeven via de koppeling **Incident beheren** op het volgende:

- Deelvenster Eigenschappen van een incident in de incidentwachtrij.
- **Overzichtspagina** van een incident.

In gevallen waarin u waarschuwingen van het ene incident naar  het andere wilt verplaatsen, kunt u dit ook doen via het tabblad Waarschuwingen, waardoor een groter of kleiner incident wordt gemaakt met alle relevante waarschuwingen.

## <a name="edit-the-incident-name"></a>De naam van het incident bewerken

Microsoft 365 Defender wijst automatisch een naam toe op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, beïnvloede gebruikers, detectiebronnen of categorieën. Hierdoor kunt u snel inzicht krijgen in het bereik van het incident. Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*

U kunt de naam van het incident bewerken vanuit het **veld Incidentnaam** in **het deelvenster Incident** beheren.

> [!NOTE]
> Incidenten die vóór de implementatie van de functie voor automatische naamgeving van incidenten hebben bestaan, behouden hun naam.

## <a name="add-incident-tags"></a>Incidentlabels toevoegen

U kunt aangepaste tags toevoegen aan een incident, bijvoorbeeld om een vlag toe te voegen aan een groep incidenten met een gemeenschappelijke eigenschap. U kunt de wachtrij voor incidenten later filteren op alle incidenten die een specifieke tag bevatten.

Wanneer u begint te typen, hebt u de optie om te selecteren in een lijst met geselecteerde tags.

## <a name="assign-incidents"></a>Incidenten toewijzen

Als er nog geen incident is toegewezen, kunt u Toewijzen **aan** selecteren en het gebruikersaccount opgeven. Als u dit doet, worden de eigenaar van het incident en alle waarschuwingen die aan het incident zijn gekoppeld, toegewezen.

## <a name="resolve-an-incident"></a>Een incident oplossen

Als het incident is opgelost, selecteert u **Incident oplossen** om de schakelknop naar rechts te verplaatsen. Het oplossen van een incident lost ook alle gekoppelde en actieve waarschuwingen met betrekking tot het incident op.

Een incident dat niet is opgelost, wordt weergegeven als **Actief**.

## <a name="set-the-classification-and-determination"></a>De classificatie en bepaling instellen

De incidentclassificatie is of het een echte waarschuwing of een onwaar waarschuwing was, die u configureert vanuit het **veld Classificatie.** 

Als het een echte waarschuwing was, moet u ook opgeven welk type bedreiging het was met het **veld Bepaling.** Als u het type bedreiging opgeeft, kan uw beveiligingsteam bedreigingspatronen zien en uw organisatie tegen hen beschermen. 

## <a name="add-comments"></a>Opmerkingen toevoegen

U kunt meerdere opmerkingen toevoegen aan een incident met **het** veld Opmerking. Elke opmerking wordt toegevoegd aan de historische gebeurtenissen van het incident. U kunt de opmerkingen en geschiedenis van een incident zien via de koppeling **Opmerkingen en geschiedenis** op de **pagina** Overzicht.

## <a name="next-steps"></a>Volgende stappen

Voor nieuwe incidenten start u uw [onderzoek.](investigate-incidents.md)

Ga voor incidenten in proces verder met uw [onderzoek.](investigate-incidents.md)

Voer voor opgeloste incidenten een [beoordeling na het incident uit.](first-incident-post.md)

## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten onderzoeken](investigate-incidents.md)
