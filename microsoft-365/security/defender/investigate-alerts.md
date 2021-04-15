---
title: Waarschuwingen onderzoeken in Microsoft 365 Defender
description: Onderzoeken van waarschuwingen die worden gezien op apparaten, gebruikers en postvakken.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
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
ms.openlocfilehash: 601a8674327c424592c65014793599dc19b2bcd3
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51759430"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Waarschuwingen onderzoeken in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Waarschuwingen vormen de basis van alle incidenten en geven aan dat er schadelijke of verdachte gebeurtenissen in uw omgeving voorkomen. Waarschuwingen maken meestal deel uit van een bredere aanval en bevatten aanwijzingen over een incident.

In Microsoft 365 Defender worden gerelateerde waarschuwingen samengevoegd tot incidenten. Incidenten bieden altijd de bredere context van een aanval, maar het onderzoeken van waarschuwingen kan waardevol zijn wanneer een diepere analyse is vereist. 



## <a name="using-alert-pages-in-investigations"></a>Waarschuwingspagina's gebruiken in onderzoeken

Als u op het tabblad Waarschuwingen van een incidentpagina een waarschuwing selecteert, gaat u naar de afzonderlijke waarschuwingspagina's. Een waarschuwingspagina bestaat uit drie secties: de betreffende activa, het waarschuwingsverhaal en het detailvenster.

![Afbeelding van voorbeeldwaarschuwingspagina](../../media/new-alert-page2.png)

Op een waarschuwingspagina kunt u het pictogram met drie puntjes **(...)** naast een entiteit selecteren, zodat u beschikbare acties kunt zien, zoals het openen van de specifieke activapagina of het uitvoeren van specifieke herstelstappen.

### <a name="analyze-affected-assets"></a>Beïnvloede activa analyseren
De sectie betreffende activa bevat postvakken, apparaten en gebruikers die door deze waarschuwing worden beïnvloed. Als u een van de activakaarten selecteert, wordt het detaildeelvenster gevuld met informatie, inclusief andere waarschuwingen die zijn opgetreden met betrekking tot de activa, indien van de gegevens.


### <a name="trace-an-alerts-role-in-the-alert-story"></a>De rol van een waarschuwing in het waarschuwingsverhaal traceren
In het waarschuwingsverhaal worden alle activa of entiteiten weergegeven die betrekking hebben op de waarschuwing in een processtructuurweergave. De waarschuwing in de titel is de waarschuwing in focus wanneer u voor het eerst op de pagina van de geselecteerde waarschuwing komt. Activa in het waarschuwingsverhaal kunnen worden uitvuwbaar en kunnen worden geklikt. Ze bieden extra informatie en versnellen de reactie doordat u acties kunt uitvoeren in de context van de waarschuwingspagina. 

> [!NOTE]
> De sectie Waarschuwingsverhaal kan meer dan één waarschuwing bevatten, met aanvullende waarschuwingen die betrekking hebben op dezelfde uitvoeringsstructuur die wordt weergegeven vóór of na de waarschuwing die u hebt geselecteerd.

### <a name="view-more-alert-information-in-the-details-pane"></a>Meer waarschuwingsgegevens weergeven in het detailvenster

In het detailvenster ziet u eerst de details van de geselecteerde waarschuwing, met details en acties die daaraan zijn gerelateerd. Als u een van de getroffen activa of entiteiten in het waarschuwingsverhaal selecteert, wordt het detailvenster gewijzigd in contextuele informatie en acties voor het geselecteerde object.

Nadat u een entiteit van belang hebt geselecteerd, wordt in het detailvenster informatie weergegeven over het geselecteerde entiteitstype, historische informatie wanneer deze beschikbaar is en opties om rechtstreeks vanaf de waarschuwingspagina actie te ondernemen op deze entiteit.

### <a name="manage-alerts"></a>Waarschuwingen beheren

Nadat u klaar bent met het onderzoeken van de waarschuwingen, kunt u teruggaan naar de waarschuwing die u hebt gestart, de status van de waarschuwing markeren als Opgelost en deze classificeren als een foutmelding of Een waar-waarschuwing. Als u waarschuwingen classificeert, kunt u uw product afstemmen op meer waar waarschuwingen en minder onwaar waarschuwingen.

> [!NOTE]
> Een manier om waarschuwingen te beheren via het gebruik van tags. De labelfunctie voor Microsoft Defender voor Office 365 wordt stapsgewijs uitgerold en wordt momenteel in preview weergegeven. <br>
> Op dit moment worden gewijzigde tagnamen alleen toegepast op waarschuwingen die *na de* update zijn gemaakt. Waarschuwingen die vóór de wijziging zijn gegenereerd, geven de bijgewerkte labelnaam niet weer. 


## <a name="manage-the-unified-alert-queue"></a>De geïntegreerde waarschuwingswachtrij beheren

Als u Waarschuwingen selecteert & meldingen in het navigatiedeelvenster van het Microsoft 365-beveiligingscentrum, wordt u in de geïntegreerde waarschuwingswachtrij geplaatst. Waarschuwingen van verschillende Microsoft-beveiligingsoplossingen, zoals Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365 en Microsoft 365 Defender, worden weergegeven in deze sectie. 

![Afbeelding van voorbeeldwaarschuwingspagina](../../media/unified-alert-queue.png)

In de wachtrij Waarschuwingen ziet u een lijst met waarschuwingen die zijn gemarkeerd in uw netwerk. Standaard worden in de wachtrij waarschuwingen weergegeven die de afgelopen 30 dagen zijn weergegeven. De meest recente waarschuwingen worden boven aan de lijst weergegeven, zodat u eerst de meest recente waarschuwingen kunt zien.

> [!NOTE]
> Op het moment van de lancering is in de wachtrij voor geïntegreerde waarschuwingen slechts 7 dagen aan Microsoft Defender voor Office 365-waarschuwingen beschikbaar. De wachtrij blijft in de tijd worden opgebouwd. Gebruik de waarschuwingenwachtrij in het Beveiligings- en compliancecentrum als u waarschuwingen wilt triagen vóór de start van de geïntegreerde [waarschuwingenwachtrij.](https://protection.office.com/viewalerts)


Op de bovenste navigatiebalk kunt u het volgende doen:

- Filters toepassen
- Kolommen aanpassen om kolommen toe te voegen of te verwijderen
- Gegevens exporteren

U kunt waarschuwingen ook filteren op basis van verschillende criteria:

- Ernst
- Status
- Categorie
- Detectiebron
- Beleid
- Beïnvloede activa
- Eerste activiteit
- Laatste activiteit


Als u een onderzoek naar een incident wilt starten, leest [u Incidenten onderzoeken in Microsoft 365 Defender](investigate-incidents.md)
## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten onderzoeken](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
