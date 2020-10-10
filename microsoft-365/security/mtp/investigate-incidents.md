---
title: Onderzoek incidenten in Microsoft Threat Protection
description: Analyseren van incidenten met betrekking tot apparaten, gebruikers en postvakken.
keywords: incident, incidenten, computers, apparaten, gebruikers, identiteiten, e-mail, e-mail, postvak, onderzoek, Graph, bewijzen
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 2ad9fa49cd5abfad1ed4ea0210939018eedd9402
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412908"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a>Onderzoek incidenten in Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**

- Microsoft Threat Protection

Microsoft Threat Protection integreert alle gerelateerde waarschuwingen, middelen, onderzoeken en bewijzen van op uw apparaten, gebruikers en postvakken, zodat u een allesomvattende uitstraling krijgt voor de hele aanval.

Onderzoek welke meldingen van invloed zijn op uw netwerk, begrijpt wat ze betekenen, en sorteer het bewijs dat u een effectief herstelabonnement kunt opstellen.

## <a name="investigate-an-incident"></a>Een incident onderzoeken

1. Selecteer een incident in de wachtrij met incidenten. <BR> Hiermee opent u een zijlade en krijgt u een voorbeeld van belangrijke informatie, zoals de status, de ernst, categorieën en de beïnvloede entiteiten.

    ![Afbeelding van het deelvenster incidenten](../../media/incident-side-panel.png)

2. Selecteer **incident pagina openen**. <BR> De incident pagina wordt geopend, waar u meer informatie kunt vinden over de details van uw incident, opmerkingen en acties, tabbladen (overzicht, waarschuwingen, apparaten, gebruikers, onderzoek, bewijs).

3. Bekijk de waarschuwingen, apparaten, gebruikers, andere entiteiten die betrokken zijn bij het incident.

## <a name="incident-overview"></a>Overzicht van incident

De pagina overzicht bevat een overzicht van de belangrijkste punten die u moet weten over het incident.

![Afbeelding van de pagina overzicht van incidenten](../../media/incidents-overview.png)

De categorieën aanval bieden u een visuele en numerieke weergave van de werking van de aanval waarmee de aanval verloopt. Net zoals bij andere Microsoft-beveiligingsproducten, is Microsoft Threat Protection uitgelijnd met de [Mitre ATT&VERzonken &trade; ](https://attack.mitre.org/) raam.

De sectie bereik biedt een lijst met de meest voorkomende activa die deel uitmaken van dit incident. Als er specifieke informatie is over dit activum, zoals risiconiveau, prioriteit van onderzoek en labels voor de activa, wordt dit ook in deze sectie weergegeven.

De tijdlijn van waarschuwingen biedt een sneak peek in de chronologische volgorde waarin de waarschuwingen zijn opgetreden, en de redenen waarom deze meldingen zijn gekoppeld aan dit incident.

En last-the documentatie-sectie biedt een overzicht van het aantal verschillende artefacten in het incident en de status van herstel, zodat u direct kunt nagaan of een actie aan uw end is vereist.

Dit overzicht is een overzicht van de belangrijkste kenmerken van het incident waarvan u op de hoogte moet zijn.

## <a name="alerts"></a>Waarschuwingen

U kunt alle meldingen weergeven die zijn gerelateerd aan het incident en andere informatie over de meldingen, zoals Ernst, entiteiten die betrokken zijn bij de waarschuwing, de bron van de waarschuwingen (Azure ATP, Microsoft Defender ATP, Office 365 ATP) en de reden waarop ze zijn gekoppeld.

![Afbeelding van de pagina incident waarschuwingen](../../media/incident-alerts.png)

Standaard worden de waarschuwingen chronologisch geordend, zodat u eerst kunt zien hoe de aanval gedurende een bepaalde periode wordt afgespeeld. Als u op een melding klikt, gaat u naar de desbetreffende waarschuwingspagina waar u een uitgebreid onderzoek van die waarschuwing kunt uitvoeren.

## <a name="devices"></a>Apparaten

Op het tabblad apparaten worden alle apparaten weergegeven waarop waarschuwingen met betrekking tot het incident zijn weergegeven.

Als u op de naam van de computer klikt waarop de aanval is uitgevoerd, gaat u naar de pagina met de computer waar u meldingen kunt bekijken die zijn geactiveerd voor de computer en voor gerelateerde gebeurtenissen die zijn ingeschakeld om onderzoek te vereenvoudigen.

![Afbeelding van het tabblad machines van een incident](../../media/incident-machines.png)

Als u het tabblad tijdlijn selecteert, kunt u door de tijdlijn op de computer schuiven en alle gebeurtenissen en gedragingen op de computer in chronologische volgorde weergeven, waarbij de waarschuwingen zijn getreden.

## <a name="users"></a>Gebruikers

Gebruikers weergeven die zijn geïdentificeerd om deel te nemen aan of die zijn gerelateerd aan een bepaald incident.

Als u op de gebruikersnaam klikt, gaat u naar de pagina beveiliging van de Cloud app van de gebruiker waar u verder onderzoek kunt verrichten.

![Afbeelding van het tabblad gebruikers van een incident](../../media/incident-users.png)

## <a name="mailboxes"></a>Postbus

Onderzoek postvakken die zijn geïdentificeerd om deel te nemen aan of die zijn gerelateerd aan een incident. Om verder onderzoek te doen, wordt het selecteren van de melding mail gerelateerde geopend en wordt Office 365 Advanced Threat Protection geopend, waar u herstelbewerkingen kunt uitvoeren.

![Afbeelding van het tabblad Postvak van een incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Tests

Selecteer **onderzoek** om alle geautomatiseerde onderzoeken te zien die zijn geactiveerd door waarschuwingen in dit incident. Het onderzoek voert herstelacties uit of wacht op goedkeuring van de analist van acties, afhankelijk van de manier waarop u uw geautomatiseerde onderzoek hebt geconfigureerd voor het uitvoeren van Microsoft Defender ATP en Office 365 Advanced Threat Protection.

![Afbeelding van het tabblad onderzoek van een incident](../../media/incident-investigations.png)

Selecteer een onderzoek om te navigeren naar de pagina met het onderzoeksteam voor volledige informatie over de status van onderzoek en herstel. Als er acties in behandeling zijn om te worden goedgekeurd als onderdeel van het onderzoek, worden deze weergegeven op het tabblad acties in behandeling. Onderneem actie als onderdeel van het herstel van incidenten.

## <a name="evidence"></a>Voldoende

Microsoft Threat Protection onderzoekt automatisch de ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u automatisch antwoord en informatie krijgt over de belangrijkste bestanden, processen, services, e-mailberichten en meer. Hiermee kunt u potentiële bedreigingen in het incident snel detecteren en blokkeren.

![Afbeelding van het tabblad bewijs van een incident](../../media/incident-evidence.png)

Alle geanalyseerde entiteiten worden gemarkeerd met een Verdict (kwaadaardige, verdacht, schoon) en een herstelstatus. Dit helpt u bij de informatie over de herstelstatus van het hele incident en de volgende stappen waarmee u verder kunt herstellen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten beheren](manage-incidents.md)

