---
title: Waarschuwingen controleren in Microsoft Defender voor Eindpunt
description: Bekijk waarschuwingsgegevens, inclusief een gevisualiseerd waarschuwingsverhaal en details voor elke stap van de keten.
keywords: incident, incidenten, machines, apparaten, gebruikers, waarschuwingen, waarschuwing, onderzoek, grafiek, bewijs
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b17af7931b181a5fa30271a3eee07c7abf10a010
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844020"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a>Waarschuwingen controleren in Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

De waarschuwingspagina in Microsoft Defender voor Eindpunt biedt volledige context voor de waarschuwing door aanvalssignalen en waarschuwingen met betrekking tot de geselecteerde waarschuwing te combineren om een gedetailleerd waarschuwingsverhaal te maken.

Maak snel een triage, onderzoek en onderneemt effectieve actie bij waarschuwingen die van invloed zijn op uw organisatie. Begrijp waarom ze zijn geactiveerd en hun impact vanaf één locatie. Meer informatie in dit overzicht.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a>Aan de slag met een waarschuwing

Als u de naam van een waarschuwing selecteert in Defender voor Eindpunt, wordt u op de waarschuwingspagina geplaatst. Op de waarschuwingspagina worden alle gegevens weergegeven in de context van de geselecteerde waarschuwing. Elke waarschuwingspagina bestaat uit 4 secties:

1. **De waarschuwingstitel** toont de naam van de waarschuwing en is er om u eraan te herinneren welke waarschuwing uw huidige onderzoek is gestart, ongeacht wat u op de pagina hebt geselecteerd.
2. [**Getroffen assets**](#review-affected-assets) bevat kaarten van apparaten en gebruikers die door deze waarschuwing worden beïnvloed en die klikbaar zijn voor meer informatie en acties.
3. In **het waarschuwingsverhaal** worden alle entiteiten weergegeven die betrekking hebben op de waarschuwing, verbonden door een boomweergave. De waarschuwing in de titel is de waarschuwing in focus wanneer u voor het eerst op de pagina van de geselecteerde waarschuwing komt. Entiteiten in het waarschuwingsverhaal kunnen worden uitgebreid en erop klikken om aanvullende informatie te verstrekken en de reactie te versnellen doordat u acties kunt uitvoeren in de context van de waarschuwingspagina. Gebruik het waarschuwingsverhaal om uw onderzoek te starten. Lees hoe u waarschuwingen [kunt onderzoeken in Microsoft Defender voor Eindpunt.](/microsoft-365/security/defender-endpoint/investigate-alerts)
4. In **het detailvenster** worden eerst de details van de geselecteerde waarschuwing weergegeven, met details en acties met betrekking tot deze waarschuwing. Als u een van de getroffen activa of entiteiten in het waarschuwingsverhaal selecteert, wordt het detailvenster gewijzigd in contextuele informatie en acties voor het geselecteerde object.

Noteer de detectiestatus voor uw waarschuwing. 
- Voorkomen: de poging tot verdachte actie is vermeden. Een bestand is bijvoorbeeld niet op schijf geschreven of uitgevoerd.
![Een waarschuwingspagina met bedreiging is voorkomen](images/detstat-prevented.png)
- Geblokkeerd: verdacht gedrag is uitgevoerd en vervolgens geblokkeerd. Een proces is bijvoorbeeld uitgevoerd, maar omdat het vervolgens verdacht gedrag vertoonde, is het proces beëindigd.
![Een waarschuwingspagina met bedreiging is geblokkeerd](images/detstat-blocked.png)
- Gedetecteerd: er is een aanval gedetecteerd en is mogelijk nog actief.
![Er is een waarschuwingspagina met bedreiging gedetecteerd](images/detstat-detected.png)




U kunt vervolgens ook de geautomatiseerde onderzoeksdetails *bekijken* in het detailvenster van uw waarschuwing, om te zien welke acties al zijn ondernomen en de beschrijving van de waarschuwing voor aanbevolen acties te lezen.

![Een fragment van het detailvenster met de waarschuwingsbeschrijving en de secties voor automatisch onderzoek gemarkeerd](images/alert-air-and-alert-description.png)

Andere informatie die beschikbaar is in het detailvenster wanneer de waarschuwing wordt geopend, omvat MITRE-technieken, bron en aanvullende contextuele details.




## <a name="review-affected-assets"></a>Beïnvloede activa controleren

Als u een apparaat of een gebruikerskaart selecteert in de betreffende activasecties, schakelt u over naar de details van het apparaat of de gebruiker in het detailvenster.

- **Voor apparaten** worden in het detailvenster gegevens over het apparaat zelf weergegeven, zoals Domein, Besturingssysteem en IP. Actieve waarschuwingen en de aangemelde gebruikers op dat apparaat zijn ook beschikbaar. U kunt direct actie ondernemen door het apparaat te isoleren, de uitvoering van apps te beperken of een antivirusscan uit te voeren. U kunt ook een onderzoekspakket verzamelen, een geautomatiseerd onderzoek starten of naar de apparaatpagina gaan om het te onderzoeken vanuit het oogpunt van het apparaat.

   ![Een fragment van het detailvenster wanneer een apparaat is geselecteerd](images/device-page-details.png)

- **Voor gebruikers** worden in het detailvenster gedetailleerde gebruikersgegevens weergegeven, zoals de SAM-naam en de SID van de gebruiker, evenals aanmeldingstypen die door deze gebruiker zijn uitgevoerd en eventuele waarschuwingen en incidenten die hiermee verband houden. U kunt *Gebruikerspagina openen selecteren om* het onderzoek voort te zetten vanuit het standpunt van die gebruiker.

   ![Een fragment van het detailvenster wanneer een gebruiker is geselecteerd](images/user-page-details.png)


## <a name="related-topics"></a>Verwante onderwerpen

- [De wachtrij voor incidenten weergeven en ordenen](view-incidents-queue.md)
- [Incidenten onderzoeken](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
