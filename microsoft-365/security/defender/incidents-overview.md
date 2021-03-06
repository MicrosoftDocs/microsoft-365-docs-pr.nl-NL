---
title: Incidenten in Microsoft 365 Defender
description: Incidenten op verschillende apparaten, gebruikers en postvakken in de Microsoft 365 Defender onderzoeken.
keywords: incidenten, waarschuwingen, onderzoeken, analyseren, reactie, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365, incidentrespons, cyberaanvallen
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
ms.openlocfilehash: b6830c77a0c5cc93ea202844a8793c5f69f07650
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028521"
---
# <a name="incidents-in-microsoft-365-defender"></a>Incidenten in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

> Wilt u Microsoft 365 Defender ervaren? U kunt het [evalueren in een testomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of [uw pilotproject uitvoeren in een productieomgeving](m365d-pilot.md?ocid=cx-evalpilot).
>

Een incident in Microsoft 365 Defender is een verzameling van gecorreleerde waarschuwingen en bijbehorende gegevens die het verhaal van een aanval bevatten. 

Microsoft 365 services en apps maken waarschuwingen wanneer ze een verdachte of schadelijke gebeurtenis of activiteit detecteren. Afzonderlijke waarschuwingen geven waardevolle aanwijzingen over een voltooide of lopende aanval. Aanvallen gebruiken echter meestal verschillende technieken voor verschillende typen entiteiten, zoals apparaten, gebruikers en postvakken. Het resultaat is meerdere waarschuwingen voor meerdere entiteiten in uw tenant. 

Omdat het lastig en tijdrovend kan zijn om de afzonderlijke waarschuwingen samen te cirkelen om inzicht te krijgen in een aanval Microsoft 365 Defender, worden de waarschuwingen en de bijbehorende informatie automatisch samengevoegd tot een incident.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hoe Microsoft 365 Defender gebeurtenissen van entiteiten correleert in een incident":::

Bekijk dit korte overzicht van incidenten in Microsoft 365 Defender (4 minuten).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Door gerelateerde waarschuwingen in een incident te groeperen, krijgt u een uitgebreide weergave van een aanval. U kunt bijvoorbeeld het volgende zien:

- Waar de aanval is begonnen.
- Welke tactieken zijn gebruikt.
- Hoe ver de aanval is gegaan in uw tenant.
- Het bereik van de aanval, zoals het aantal apparaten, gebruikers en postvakken dat is beïnvloed. 
- Alle gegevens die aan de aanval zijn gekoppeld.

Als [dit is ingeschakeld,](m365d-enable.md)Microsoft 365 Defender [waarschuwingen automatisch](m365d-autoir.md) onderzoeken en oplossen via automatisering en kunstmatige intelligentie. U kunt ook aanvullende herstelstappen uitvoeren om de aanval op te lossen. 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>Incidenten en waarschuwingen in de Microsoft 365 Defender portal

U beheert incidenten vanuit **Incidenten & waarschuwingen > incidenten** op de snelle start van de Microsoft 365 Defender portal [(security.microsoft.com).](https://security.microsoft.com) Hier is een voorbeeld.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="De pagina Incidenten in de Microsoft 365 Defender portal":::

Als u een incidentnaam selecteert, wordt een overzicht van het incident weergegeven en krijgt u toegang tot tabbladen met aanvullende informatie.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Voorbeeld van de pagina Overzicht voor een incident in de Microsoft 365 Defender portal":::

De extra tabbladen voor een incident zijn:

- Waarschuwingen 

  Alle waarschuwingen met betrekking tot het incident en de bijbehorende informatie.

- Apparaten

  Alle apparaten die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.

- Gebruikers

  Alle gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.

- Postvakken

  Alle postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.

- Onderzoeken

  Alle automatische [onderzoeken die worden veroorzaakt](m365d-autoir.md) door waarschuwingen bij het incident.

- Bewijs en antwoord

  Alle ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen in het incident.

- Graph (in voorbeeld)

  Een afbeelding met de verbinding van waarschuwingen met de beïnvloede activa in uw organisatie.

Hier is de relatie tussen een incident en de gegevens en de tabbladen van een incident in de Microsoft 365 Defender portal.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="De relatie van een incident en de gegevens ervan met de tabbladen van een incident in de Microsoft 365 Defender portal":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Voorbeeld van de werkstroom incidentrespons voor Microsoft 365 Defender

Hier is een voorbeeldwerkstroom voor het reageren op incidenten in Microsoft 365 met de Microsoft 365 Defender portal.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Voorbeeld van een werkstroom voor incidentrespons voor Microsoft 365":::

Identificeer doorlopend de incidenten met de hoogste prioriteit voor analyse en oplossing in de incidentwachtrij en maak ze klaar voor reactie. Dit is een combinatie van:

- [Triaging](incident-queue.md) om de incidenten met de hoogste prioriteit te bepalen door de wachtrij voor incidenten te filteren en te sorteren.
- [U](manage-incidents.md) kunt incidenten beheren door de titel te wijzigen, deze toe te wijzen aan een analist en tags en opmerkingen toe te voegen.

1. Voor elk incident start u een [aanval en een waarschuwingsonderzoek en -analyse:](investigate-incidents.md)
 
   1. Bekijk de samenvatting van het incident om te begrijpen wat het bereik en de ernst is en welke entiteiten worden beïnvloed (het **tabblad** Overzicht).

   1. Begin met het analyseren van de waarschuwingen om de herkomst, het bereik en de ernst ervan te begrijpen (het **tabblad** Waarschuwingen).

   1. Verzamel zo nodig informatie over beïnvloede apparaten, gebruikers en postvakken **(de** tabbladen **Apparaten,** Gebruikers en **Postvakken).**

   1. Bekijk hoe Microsoft 365 Defender [waarschuwingen automatisch](m365d-autoir.md) heeft opgelost (het **tabblad** Onderzoeken).
   
   1. Gebruik zo nodig informatie in de gegevensset voor het incident voor meer informatie (het **tabblad Bewijs en** antwoord).

2. Voer na of tijdens uw analyse insluiting uit om eventuele extra gevolgen van de aanval en de uitbanning van de beveiligingsrisico's te beperken.

3. Herstel zoveel mogelijk van de aanval door de tenantbronnen te herstellen in de status waarin ze zich vóór het incident hebben voordeden.

4. [Los](manage-incidents.md#resolve-an-incident) het incident op en neem de tijd om na het incident te leren:

   - Inzicht in het type van de aanval en de impact ervan.
   - Onderzoek de aanval in [Threat Analytics](threat-analytics.md) en de beveiligingsgemeenschap voor een beveiligingsaanvaltrend.
   - De werkstroom inroepen die u hebt gebruikt om het incident op te lossen en uw standaardwerkstromen, processen, beleidsregels en playbooks zo nodig bij te werken.
   - Bepaal of wijzigingen in uw beveiligingsconfiguratie nodig zijn en implementeert deze.

Als u nog niet bekend bent met beveiligingsanalyse, bekijkt u de inleiding tot het reageren op uw eerste [incident](incidents-overview.md) voor meer informatie en een voorbeeldincident door te nemen.

Zie dit artikel voor meer informatie over de reactie op incidenten [in Microsoft-producten.](/security/compass/incident-response-overview)

## <a name="example-security-operations-for-microsoft-365-defender"></a>Voorbeeld van beveiligingsbewerkingen voor Microsoft 365 Defender

Hier volgen een voorbeeld van beveiligingsbewerkingen (SecOps) voor Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Een voorbeeld van beveiligingsbewerkingen voor Microsoft 365 Defender":::

Dagelijkse taken kunnen bestaan uit:

- [Incidenten](manage-incidents.md) beheren
- Acties voor [automatisch onderzoek en antwoord (AIR)](m365d-action-center.md) bekijken in het Actiecentrum
- De meest recente [Threat Analytics bekijken](threat-analytics.md)
- [Reageren op](investigate-incidents.md) incidenten

Maandelijkse taken kunnen bestaan uit:

- [Air-instellingen controleren](m365d-configure-auto-investigation-response.md)
- Secure [Score and](microsoft-secure-score-improvement-actions.md) [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Rapporteren aan uw IT-beveiligingsbeheerketen

Driemaandelijkse taken kunnen een rapport en een briefing van beveiligingsresultaten bevatten aan de Ciso (Chief Information Security Officer).

Jaarlijkse taken kunnen bestaan uit het uitvoeren van een grote incident- of inbreukoefening om uw personeel, systemen en processen te testen. 

Dagelijkse, maandelijkse, kwartaal- en jaarlijkse taken kunnen worden gebruikt om processen, beleidsregels en beveiligingsconfiguraties bij te werken of te verfijnen.

### <a name="secops-resources-across-microsoft-products"></a>SecOps-resources voor Microsoft-producten

Zie de volgende bronnen voor meer informatie over SecOps voor alle Microsoft-producten:

- [Mogelijkheden](/security/compass/security-operations-capabilities)
- [Aanbevolen procedures](/security/compass/security-operations)
- [Video's en dia's](/security/compass/security-operations-videos-and-decks)

## <a name="next-steps"></a>Volgende stappen

**Als u nog niet bekend bent** met beveiligingsanalyse en incidentrespons:

- Zie de [walkthrough](first-incident-overview.md) Reageren op uw eerste incident om een rondleiding te krijgen van een typisch proces van analyse, herstel en beoordeling na het incident in de Microsoft 365 Defender portal met een voorbeeldaanval.

**Als u ervaring hebt met** beveiligingsanalyse en incidentrespons:

- Ga aan de slag met de incidentwachtrij vanaf **de pagina Incidenten** van de Microsoft 365 Defender portal. Hier kunt u het volgende doen:

  - Bekijk welke incidenten prioriteit [moeten krijgen op](incident-queue.md) basis van ernst en andere factoren. 

  - [Beheer incidenten,](manage-incidents.md)waaronder het wijzigen van de naam, het toewijzen, classificeren en toevoegen van tags en opmerkingen op basis van uw werkstroom voor incidentbeheer.

  - Voer [onderzoeken van](investigate-incidents.md) incidenten uit.

- Bekijk deze [playbooks voor incidentreacties](/security/compass/incident-response-playbooks) voor gedetailleerde richtlijnen voor phishing- en wachtwoordincidenten en app-toestemmingsverleningsaanvallen.

