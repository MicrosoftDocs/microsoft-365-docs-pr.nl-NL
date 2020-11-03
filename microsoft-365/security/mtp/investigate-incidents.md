---
title: Gebeurtenissen onderzoeken in Microsoft 365 Defender
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
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846746"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Gebeurtenissen onderzoeken in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**

- Microsoft 365 Defender

Microsoft 365 Defender verzamelt alle gerelateerde waarschuwingen, assets, onderzoeken en bewijzen van op uw apparaten, gebruikers en postvakken, zodat u een allesomvattende uitstraling krijgt.

Onderzoek welke meldingen van invloed zijn op uw netwerk, begrijpt wat ze betekenen, en sorteer het bewijs dat u een effectief herstelabonnement kunt opstellen.

## <a name="investigate-an-incident"></a>Een incident onderzoeken

1. Selecteer een incident in de wachtrij met incidenten. <BR> Er wordt een deelvenster geopend met een voorbeeld van belangrijke informatie, zoals status, Ernst, categorieën en de beïnvloede entiteiten.

    ![Afbeelding van het deelvenster incidenten](../../media/incident-side-panel.png)

2. Selecteer **incident pagina openen**. <BR> De incident pagina wordt geopend, waar u meer informatie, opmerkingen en acties, tabbladen (overzicht, waarschuwingen, apparaten, gebruikers, onderzoek, bewijs) kunt vinden.

3. Bekijk de waarschuwingen, apparaten, gebruikers, andere entiteiten die betrokken zijn bij het incident.

## <a name="incident-overview"></a>Overzicht van incident

De pagina overzicht bevat een overzicht van de belangrijkste punten die u moet weten over het incident.

![Afbeelding van de pagina overzicht van incidenten](../../media/incidents-overview.png)

De categorieën aanval bieden een visuele en numerieke weergave van de werking van de aanval waarmee de aanval verloopt. Net als met andere Microsoft-beveiligingsproducten is Microsoft 365 Defender uitgelijnd met de [Mitre &trade; att&verzonken](https://attack.mitre.org/) raam.

De sectie bereik biedt een lijst met de meest voorkomende activa die deel uitmaken van dit incident. Als er specifieke informatie is over dit activum, zoals risiconiveau, prioriteit van onderzoek en labels voor de activa, wordt dit ook in deze sectie weergegeven.

De tijdlijn van waarschuwingen biedt een sneak peek in de chronologische volgorde waarin de waarschuwingen zijn opgetreden, en de redenen waarom deze meldingen zijn gekoppeld aan dit incident.

En last-the documentatie-sectie biedt een overzicht van het aantal verschillende artefacten in het incident en de status van herstel, zodat u direct kunt nagaan of een actie aan uw end is vereist.

Dit overzicht is een overzicht van de belangrijkste kenmerken van het incident waarvan u op de hoogte moet zijn.

## <a name="alerts"></a>Waarschuwingen

U kunt alle meldingen weergeven die zijn gerelateerd aan het incident en andere informatie over de meldingen, zoals Ernst, entiteiten die betrokken zijn bij de waarschuwing, de bron van de waarschuwingen (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender voor Office 365) en de reden waarop ze zijn gekoppeld.

![Afbeelding van de pagina incident waarschuwingen](../../media/incident-alerts.png)

Standaard worden de waarschuwingen chronologisch geordend, zodat u eerst kunt zien hoe de aanval gedurende een bepaalde periode wordt afgespeeld. Als u op een melding klikt, gaat u naar de desbetreffende waarschuwingspagina waar u een uitgebreid onderzoek van de melding kunt uitvoeren.

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

Onderzoek postvakken die zijn geïdentificeerd om deel te nemen aan of die zijn gerelateerd aan een incident. Om verder onderzoek te doen, wordt het selecteren van de e-mail gerelateerde melding geopend Microsoft Defender voor Office 365, waarop u herstelbewerkingen kunt uitvoeren.

![Afbeelding van het tabblad Postvak van een incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Tests

Selecteer **onderzoek** om alle geautomatiseerde onderzoeken te zien die zijn geactiveerd door waarschuwingen in dit incident. Het onderzoek voert herstelacties uit of wacht op goedkeuring van de analist van acties, afhankelijk van de manier waarop u uw geautomatiseerde onderzoek hebt geconfigureerd voor het uitvoeren van Microsoft Defender voor eindpunten en Defender voor Office 365.

![Afbeelding van het tabblad onderzoek van een incident](../../media/incident-investigations.png)

Selecteer een onderzoek om te navigeren naar de pagina met het onderzoeksteam voor volledige informatie over de status van onderzoek en herstel. Als er voor de goedkeuring een actie is ondergebracht, wordt deze weergegeven in het tabblad acties in behandeling. Onderneem actie als onderdeel van het herstel van incidenten.

## <a name="evidence"></a>Voldoende

Microsoft 365 Defender onderzoekt automatisch de ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u automatisch antwoord en informatie krijgt over de belangrijkste bestanden, processen, services, e-mailberichten en meer. Hiermee kunt u potentiële bedreigingen in het incident snel detecteren en blokkeren.

![Afbeelding van het tabblad bewijs van een incident](../../media/incident-evidence.png)

Alle geanalyseerde entiteiten worden gemarkeerd met een Verdict (kwaadaardige, verdacht, schoon) en een herstelstatus. Dit helpt u bij de informatie over de herstelstatus van het hele incident en de volgende stappen waarmee u verder kunt herstellen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten beheren](manage-incidents.md)

