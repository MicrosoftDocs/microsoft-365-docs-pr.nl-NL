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
ms.openlocfilehash: 9cb3cc67c3992773897ea8178f261d25dcd87da0
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594146"
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
- [Het incident aan uzelf toewijzen](#assign-incidents)
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

Als u een incident wilt toewijzen, **selecteert u Toewijzen aan mij.** Als u dit doet, worden de eigenaar van het incident en alle waarschuwingen die aan het incident zijn gekoppeld, toegewezen aan uw gebruikersaccount.

U kunt een lijst met incidenten krijgen die aan u zijn toegewezen door de wachtrij voor incidenten te filteren. 

1. Selecteer filters in de wachtrij voor **incidenten.**
2. schakel in **de sectie Incidenttoewijzing** **alles selecteren uit** en selecteer Toegewezen aan **mij.**
3. Selecteer **Toepassen** en sluit het **deelvenster** Filters.

Vervolgens kunt u de resulterende URL in uw browser opslaan als bladwijzer om snel de lijst met incidenten weer te geven die aan u zijn toegewezen.

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
