---
title: Incidenten prioriteren in Microsoft Threat Protection
description: Meer informatie over het instellen van een prioriteit aan de incidenten wachtrij in Microsoft Threat Protection
keywords: incident, wachtrij, overzicht, apparaten, identiteiten, gebruikers, postvak, e-mail, incidenten
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
ms.openlocfilehash: a08ff27d6d33317df9bd4bf61c0c2ee4cf0ee14e
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797756"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>Incidenten prioriteren in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft Threat Protection



Microsoft Threat Protection past correlatie analyses toe en voegt alle bijbehorende waarschuwingen en onderzoek van verschillende producten samen tot één voorval. Microsoft Threat Protection zorgt ook voor unieke meldingen over activiteiten die alleen als schadelijk kunnen worden geïdentificeerd aan de end-to-end zichtbaarheid van Microsoft Threat Protection voor het hele erfgoed en de suite met producten. Op deze manier beschermt Microsoft Threat Protection het bredere verhaal van een verhaal, waardoor een beveiligings analist de analist begrijpt en begrijpt met ingewikkelde bedreigingen binnen de organisatie.


In de **wachtrij incidenten** wordt een verzameling incidenten weergegeven die zijn gemarkeerd voor alle apparaten, gebruikers en postvakken. Met deze functie kunt u een weloverwogen Cyber Security-antwoord beslissing stellen en een weloverwogen antwoord beslissing stellen.


![Afbeelding van een wachtrij voor incidenten](../../media/incidents-queue.png) 

Standaard worden in de wachtrij in het Microsoft 365-Beveiligingscentrum de incidenten weergegeven die in de afgelopen 30 dagen worden weergegeven, met het meest recente incident dat bovenaan de lijst wordt weergegeven, zodat u eerst de meest recente aanvragen kunt zien.

In de wachtrij voor incidenten worden aanpasbare kolommen gemaakt waarmee u inzicht krijgt in verschillende kenmerken van het incident of de opgenomen entiteiten, zodat u een weloverwogen beslissing moet nemen over de prioriteit van incidenten.

Voor meer inzicht in één oogopslag worden namen van geadresseerden automatisch de naam van een incident gegenereerd op basis van waarschuwings kenmerken, zoals het aantal desbetreffende eindpunten, gebruikers die worden getroffen, detectie bronnen of categorieën. Zo kunt u snel inzicht krijgen in de reikwijdte van het incident.

Voorbeeld: een *incident van meerdere stappen op meerdere eindpunten, gerapporteerd door meerdere bronnen.*

> [!NOTE]
> Voor incidenten die bestonden vóór de implementatie van de naam van het automatische incident, is de naam niet gewijzigd.

In de wachtrij voor incidenten worden ook meerdere filteropties getoond die u kunt gebruiken om ervoor te zorgen dat al uw bestaande incidenten in uw omgeving meerdere keren worden opruimen of dat u zich kunt richten op een specifiek scenario of bedreiging. Door filters toe te passen op de incident wachtrij, kunt u bepalen welk incident directe aandacht vereist. 

## <a name="available-filters"></a>Beschikbare filters

### <a name="status"></a>Status
U kunt ervoor kiezen de lijst te beperken van de namen die worden weergegeven op basis van hun status, zodat u kunt zien welke gebeurtenissen actief zijn of worden opgelost.

### <a name="severity"></a>Ernst
De ernst van een incident is van invloed op de invloed die dit kan hebben op uw activa. Hoe hoger de ernst, hoe groter de impact en is meestal de enige directe aandacht. 

### <a name="assigned-to-owner"></a>Toegewezen aan (eigenaar)
Als u de lijst wilt filteren, selecteert u de gewenste optie voor iedereen of degene die aan u is toegewezen.

### <a name="multiple-alerts"></a>Meerdere meldingen 
Filteren om alleen aanvragen weer te geven die meer dan één waarschuwing bevatten. Dit kan een aanwijzing zijn voor een aanval met een complexere of een afgang van de werk keten. 


### <a name="multiple-service-sources"></a>Meerdere servicebronnen 
Filteren om alleen incidenten weer te geven die waarschuwingen van verschillende bronnen bevatten (Microsoft Defender ATP, beveiliging van Microsoft Cloud app, Azure ATP, Office 365 ATP)
### <a name="service-sources"></a>Service bronnen
Als u een specifieke bron kiest, kunt u zich richten op incidenten met minstens één waarschuwing van de gekozen bron. 

### <a name="multiple-categories"></a>Meerdere categorieën 
U kunt ervoor kiezen om alleen aanvragen weer te geven die zijn toegewezen aan meerdere categorieën van de Kill-chain en hierdoor meer schade kan veroorzaken. 

### <a name="categories"></a>Categorieën
Kies specifieke categorieën om te focussen op een specifieke stap in de keten afbreken

### <a name="data-sensitivity"></a>Gegevens gevoeligheid
Sommige aanvallen richten op het bereiken van exfiltrate gevoelige of waardevolle gegevens. Door een filter toe te passen om te zien of de gevoelige gegevens bij het incident passen, kunt u snel vaststellen of gevoelige informatie al mogelijk is aangetast en de prioriteit van die incidenten bepalen.

>[!NOTE]
>Alleen van toepassing als Microsoft-informatiebeveiliging is ingeschakeld.


## <a name="next-steps"></a>Volgende stappen
Nadat u hebt vastgesteld voor welk incident de hoogste prioriteit is vereist, kunt u doorgaan met het verdere onderzoek verder werken aan een incident.
- [Incidenten onderzoeken](investigate-incidents.md)


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten onderzoeken](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
