---
title: Limieten voor bewaarbeleid en retentielabelbeleid
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Meer informatie over het maximum aantal beleidsregels en items per beleid voor bewaarbeleid en bewaarlabelbeleid
ms.openlocfilehash: 007ca6eec50b243e1b820938ffa67553d7882c7b
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162868"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>Limieten voor bewaarbeleid en retentielabelbeleid

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Als u [bewaarbeleid en retentielabelbeleid](retention.md#retention-policies-and-retention-labels) gebruikt om gegevens automatisch te behouden of verwijderen voor uw organisatie, moet u rekening houden met deze limieten.

## <a name="maximum-number-of-policies-per-tenant"></a>Maximaal aantal gebruikers per tenant

Een enkele tenant kan maximaal 10.000 beleidsregels hebben (in iedere configuratie). Binnen dit maximale aantal vallen ook de verschillende beleidsregels voor retentie en andere beleidsregels voor compliance, zoals DLP-beleidsregels.

Maximale aantal beleidsregels voor retentie per workload:

- Exchange Online (in iedere configuratie): 1.800
- SharePoint of OneDrive: (alle sites automatisch inbegrepen): 13
- SharePoint of OneDrive (specifieke locaties inbegrepen of uitgesloten): 2.600

## <a name="maximum-number-of-items-per-policy"></a>Maximale aantal items per beleidsregel

Als u de optionele configuratie gebruikt om uw bewaarinstellingen te beperken tot specifieke gebruikers, specifieke Microsoft 365-groepen, of specifieke sites, moet u rekening houden met deze limieten per beleidsregel: 

Maximale aantal items per beleidsregel voor retentie:

  - 1.000 postvakken (gebruikerspostvakken of groepspostvakken)
  - 1.000 Microsoft 365-groepen
  - 1.000 gebruikers voor privéchats in Teams
  - 100 sites (OneDrive of SharePoint)

Omdat deze limieten per beleid gelden, moet u mogelijk specifieke items opnemen of uitsluiten, waardoor u de limiet overschijdt. In dat geval kunt u aanvullende beleidsregels maken die dezelfde bewaarinstellingen hebben. Zie de volgende sectie voor [voorbeelden van scenario's en oplossingen](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) waarin om deze reden meerdere bewaarbeleidsregels zijn gebruikt.

Meerdere beleidsregels zorgen wel voor hogere administratiekosten, dus controleer altijd of u specifieke items werkelijk moet opnemen of uitsluiten. Onthoud dat er voor de standaardconfiguratie, die van toepassing is op de gehele locatie, geen limieten gelden en dat deze configuratie een betere oplossing kan zijn dan het maken en onderhouden van meerdere beleidsregels.

> [!TIP]
> Als u toch meerdere beleidsregels moet maken en onderhouden voor dit scenario, overweeg dan [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) te gebruiken voor efficiëntere configuratie.

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>Voorbeelden van het gebruik van meerdere beleidsregels om het overschrijden van limieten te voorkomen

De volgende voorbeelden bevatten oplossingen voor situaties waarin u niet alleen de locatie kunt opgeven voor het bewaarbeleid en rekening moet houden met het maximum voor het aantal vastgelegde items dat in de voorgaande sectie is besproken.

Voorbeeld met Exchange:

- **Scenario**: in een organisatie met ruim 40.000 gebruikerspostvakken worden de e-mailberichten van de meeste gebruikers 7 jaar behouden, maar van bepaalde gebruikers (425) binnen deze groep moeten de e-mailberichten slechts 5 jaar worden behouden.

- **Oplossing**: maak een bewaarbeleid voor Exchange-e-mail met een retentieperiode van 7 jaar en sluit de geïdentificeerde gebruikers uit. Maak vervolgens een bewaarbeleid voor Exchange-e-mail met een retentieperiode van 5 jaar waarin de geïdentificeerde gebruikers zijn opgenomen. 
    
    In beide gevallen ligt het aantal opgenomen en uitgesloten postvakken onder het maximale aantal postvakken voor een enkele beleidsregel en moeten de geïdentificeerde gebruikers expliciet worden uitgesloten van de eerste beleidsregel, omdat deze een [langere retentieperiode](retention.md#the-principles-of-retention-or-what-takes-precedence) heeft dan de tweede beleidsregel. Als de subset van gebruikers een langer bewaarbeleid vereist, hoeft u ze niet uit te sluiten van het eerste beleid.
     
    Als er in de organisatie een nieuw personeelslid is, wordt het postvak van die persoon door deze oplossing automatisch opgenomen in het 7 jaar-beleid en zijn er geen gevolgen voor het maximale aantal ondersteunde items. Als er echter nieuwe gebruikers zijn voor wie een retentieperiode van 5 jaar nodig is, neemt het aantal opgenomen en uitgesloten items toe richting de limiet van 1.000.

Voorbeeld met SharePoint:

- **Scenario**: een organisatie heeft duizenden SharePoint-sites, maar voor slechts 2.000 sites is er een retentieperiode van 10 jaar nodig en voor 8.000 sites een retentieperiode van 4 jaar.

- **Oplossing**: maak 20 bewaarbeleidsregels voor SharePoint met een retentieperiode van 10 jaar waarin 100 specifieke sites zijn opgenomen en 80 bewaarbeleidsregels voor SharePoint met een retentieperiode van 4 jaar waarin 100 specifieke sites zijn opgenomen.
    
    Omdat u niet alle SharePoint-sites hoeft te behouden, maakt u bewaarbeleidsregels waarin specifieke sites zijn opgenomen. Omdat een bewaarbeleidsregel niet meer dan 100 specifieke sites ondersteunt, moet u meerdere beleidsregels maken voor beide retentieperiodes. Deze bewaarbeleidsregels hebben een maximaal aantal opgenomen sites, dus voor de volgende nieuwe site is er een nieuwe bewaarbeleidsregel nodig, ongeacht de retentieperiode.