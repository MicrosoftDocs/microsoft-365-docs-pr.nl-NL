---
title: Waarschuwingen onderzoeken in Microsoft 365 Defender
description: Onderzoeken van waarschuwingen die worden gezien op apparaten, gebruikers en postvakken.
keywords: incidenten, waarschuwingen, onderzoeken, analyseren, reactie, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
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
ms.openlocfilehash: 6a34269c414f59d40c9160d5728159ed9cddf976
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651345"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Waarschuwingen onderzoeken in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Waarschuwingen vormen de basis van alle incidenten en geven aan dat er schadelijke of verdachte gebeurtenissen in uw omgeving voorkomen. Waarschuwingen maken meestal deel uit van een bredere aanval en geven aanwijzingen over een incident.

In Microsoft 365 Defender worden gerelateerde waarschuwingen samengevoegd tot [incidenten.](incidents-overview.md) Incidenten bieden altijd de bredere context van een aanval, maar het analyseren van waarschuwingen kan waardevol zijn wanneer een diepere analyse is vereist. 

In **de wachtrij Waarschuwingen** ziet u de huidige set waarschuwingen. U krijgt toegang tot de waarschuwingenwachtrij van **Incidenten & waarschuwingen > Waarschuwingen** bij de snelle start van het Microsoft 365 beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com)

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Voorbeeld van de waarschuwingenwachtrij":::

Waarschuwingen van verschillende Microsoft-beveiligingsoplossingen, zoals Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365 en Microsoft 365 Defender, worden hier weergegeven.

Standaard worden in de waarschuwingenwachtrij in Microsoft 365 beveiligingscentrum de nieuwe waarschuwingen van de afgelopen 30 dagen weergegeven. De meest recente waarschuwing staat boven aan de lijst, zodat u deze als eerste kunt zien. 

In de wachtrij met standaardwaarschuwingen kunt u **Filters** selecteren om een deelvenster **Filters** te zien, waaruit u een subset van de waarschuwingen kunt opgeven. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Voorbeeld van het filtervenster voor de waarschuwingenwachtrij":::

U kunt waarschuwingen filteren op basis van deze criteria:

- Ernst
- Status
- Categorie
- Detectiebron
- Tags
- Beleid
- Beïnvloede activa

## <a name="analyze-an-alert"></a>Een waarschuwing analyseren

Als u de hoofdwaarschuwingspagina wilt zien, selecteert u de naam van de waarschuwing. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Voorbeeld van de detailspagina van een waarschuwing in het Microsoft 365 beveiligingscentrum":::

U kunt ook de actie **De hoofdwaarschuwingspagina openen** selecteren in **het deelvenster Waarschuwing** beheren.

Een waarschuwingspagina bestaat uit deze secties: 

- Waarschuwingsverhaal, de reeks gebeurtenissen en waarschuwingen met betrekking tot deze waarschuwing in chronologische volgorde
- Overzichtsdetails

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Voorbeeld van de detailspagina van een waarschuwing in het Microsoft 365 beveiligingscentrum":::

Op een waarschuwingspagina kunt u de drie puntjes **(...)** naast een entiteit selecteren om beschikbare acties te bekijken, zoals het openen van de waarschuwingspagina of het koppelen van de waarschuwing aan een ander incident.

### <a name="analyze-affected-assets"></a>Beïnvloede activa analyseren

De **sectie Acties ondernomen** heeft een lijst met beïnvloede activa, zoals postvakken, apparaten en gebruikers die door deze waarschuwing worden beïnvloed. 

U kunt ook Weergeven in het  **actiecentrum** selecteren om het tabblad Geschiedenis van het **actiecentrum** in het Microsoft 365 te bekijken. 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>De rol van een waarschuwing in het waarschuwingsverhaal traceren

In het waarschuwingsverhaal worden alle activa of entiteiten weergegeven die betrekking hebben op de waarschuwing in een processtructuurweergave. De waarschuwing in de titel is de waarschuwing in focus wanneer u voor het eerst op de pagina van de geselecteerde waarschuwing komt. Activa in het waarschuwingsverhaal kunnen worden uitvuwbaar en kunnen worden geklikt. Ze bieden extra informatie en versnellen uw antwoord doordat u direct actie kunt ondernemen in de context van de waarschuwingspagina. 

> [!NOTE]
> De sectie Waarschuwingsverhaal kan meer dan één waarschuwing bevatten, met aanvullende waarschuwingen die betrekking hebben op dezelfde uitvoeringsstructuur die wordt weergegeven vóór of na de waarschuwing die u hebt geselecteerd.

### <a name="view-more-alert-information-on-the-details-page"></a>Meer informatie over waarschuwingen weergeven op de detailspagina

Op de detailspagina ziet u de details van de geselecteerde waarschuwing, met details en acties die daaraan zijn gerelateerd. Als u een van de getroffen activa of entiteiten in het waarschuwingsverhaal selecteert, wordt de pagina details gewijzigd in contextuele informatie en acties voor het geselecteerde object.

Nadat u een entiteit van belang hebt geselecteerd, wordt op de detailspagina informatie weergegeven over het geselecteerde entiteitstype, historische informatie wanneer deze beschikbaar is en opties om rechtstreeks vanaf de waarschuwingspagina actie te ondernemen op deze entiteit.

## <a name="manage-alerts"></a>Waarschuwingen beheren

Als u een waarschuwing wilt beheren, selecteert u de waarschuwing in de waarschuwingenwachtrij in de rij om het deelvenster **Waarschuwing beheren te** zien. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Voorbeeld van het overzichtsvenster voor een waarschuwing":::

In **het deelvenster Waarschuwing beheren** kunt u het volgende opgeven:

- De status van de waarschuwing (Nieuw, Opgelost, In uitvoering).
- De classificatie van de waarschuwing (Niet ingesteld, Waar-waarschuwing, Foutmelding).
- Voor de classificatie als een echte waarschuwing, het type bedreiging voor de waarschuwing in **het veld Bepaling.**
- Een opmerking over de waarschuwing.

> [!NOTE]
> Een manier om waarschuwingen te beheren via het gebruik van tags. De labelfunctie voor Microsoft Defender voor Office 365 wordt stapsgewijs uitgerold en wordt momenteel in preview uitgevoerd. <br>
> Op dit moment worden gewijzigde tagnamen alleen toegepast op waarschuwingen die *na de* update zijn gemaakt. Waarschuwingen die zijn gegenereerd vóór de wijziging, geven niet de naam van de bijgewerkte tag weer. 

In dit deelvenster kunt u ook de volgende aanvullende acties uitvoeren: 

- De hoofdwaarschuwingspagina openen
- Een Bedreigingsexpert van Microsoft raadplegen
- Inzending weergeven
- Koppeling maken naar een ander incident
- De waarschuwing in een tijdlijn bekijken
- Een onderdrukkingsregel maken

Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Voorbeeld van de acties op een waarschuwing in het Microsoft 365 beveiligingscentrum":::

De lijst met aanvullende acties is afhankelijk van het type waarschuwing.

## <a name="resolve-an-alert"></a>Een waarschuwing oplossen

Wanneer u klaar bent met het analyseren van een waarschuwing en deze kan worden opgelost,  gaat u naar het  deelvenster Waarschuwing beheren voor de waarschuwing en markeert u de status van de waarschuwing als Opgelost en classificeert u deze als een foutmelding of **True-waarschuwing.**  Geef voor echte waarschuwingen het bedreigingstype van de waarschuwing op in **het veld Bepaling.**

Als u waarschuwingen classificeert en de bepaling opgeeft, Microsoft 365 Defender meer waar waarschuwingen en minder onwaar waarschuwingen.

## <a name="next-steps"></a>Volgende stappen

Ga zo nodig door met uw onderzoek als dit nodig is voor incidenten in [de procedure.](investigate-incidents.md)

## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten beheren](manage-incidents.md)
- [Incidenten onderzoeken](investigate-incidents.md)
