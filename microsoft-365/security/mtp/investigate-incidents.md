---
title: Incidenten in Microsoft 365 Defender onderzoeken
description: Analyseer incidenten met betrekking tot apparaten, gebruikers en postvakken.
keywords: incident, incidenten, machines, apparaten, gebruikers, identiteiten, e-mail, e-mail, postvak, onderzoek, grafiek, bewijs
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6a3bd6be81b4ea4ef11a366267d7a36d45e622b9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926892"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Incidenten in Microsoft 365 Defender onderzoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**

- Microsoft 365 Defender

Microsoft 365 Defender verzamelt alle gerelateerde waarschuwingen, activa, onderzoeken en bewijsstukken van al uw apparaten, gebruikers en postvakken, zodat u een uitgebreid overzicht krijgt van de volledige breedte van een aanval.

Onderzoek de waarschuwingen die van invloed zijn op uw netwerk, begrijp wat deze betekenen en bewaa gegevens die bij de incidenten horen, zodat u een effectief herstelplan kunt bedenken.

## <a name="investigate-an-incident"></a>Een incident onderzoeken

1. Selecteer een incident in de incidentwachtrij. <BR> Er wordt een zijpaneel geopend met een voorbeeld van belangrijke informatie, zoals status, ernst, categorieën en de beïnvloede entiteiten.

    ![Afbeelding van het zijpaneel voor incidenten](../../media/incident-side-panel.png)

2. Selecteer **Incidentpagina openen.** <BR> Hiermee opent u de pagina voor incidenten, waar u meer informatie over incidenten, opmerkingen en acties, tabbladen (overzicht, waarschuwingen, apparaten, gebruikers, onderzoeken, bewijs) vindt.

3. Bekijk de waarschuwingen, apparaten, gebruikers, andere entiteiten die betrokken zijn bij het incident.

## <a name="incident-overview"></a>Overzicht van incidenten

Op de overzichtspagina ziet u een momentopname van de belangrijkste dingen die u moet zien over het incident.

![Afbeelding van de overzichtspagina voor incidenten](../../media/incidents-overview.png)

De aanvalscategorieën geven u een visuele en numerieke weergave van hoe geavanceerd de aanval is vorderen ten opzichte van de kill chain. Microsoft 365 Defender is, net als andere beveiligingsproducten van Microsoft, afgestemd op de [MITRE ATT &trade;&CK-framework.](https://attack.mitre.org/)

De sectie Bereik bevat een lijst met belangrijkste beïnvloede activa die deel uitmaken van dit incident. Als er specifieke informatie over deze activum is, zoals risiconiveau, prioriteit van het onderzoek en labelen op de assets, wordt dit ook in deze sectie be gegeven.

De tijdlijn met waarschuwingen biedt een voorproefje van de chronologische volgorde waarin de waarschuwingen hebben plaatsgevonden, evenals de redenen waarom deze waarschuwingen aan dit incident zijn gekoppeld.

Ten laatste bevat de informatiesectie een overzicht van hoeveel verschillende artefacten bij het incident zijn betrokken en wat de herstelstatus is, zodat u onmiddellijk kunt bepalen of er aan uw kant actie moet worden ondernomen.

Dit overzicht kan helpen bij de eerste triage van het incident door inzicht te bieden in de belangrijkste kenmerken van het incident waar u rekening mee moet houden.

## <a name="alerts"></a>Waarschuwingen

U kunt alle waarschuwingen met betrekking tot het incident en andere informatie over deze meldingen weergeven, zoals ernst, entiteiten die zijn betrokken bij de waarschuwing, de bron van de waarschuwingen (Microsoft Defender voor identiteit, Microsoft Defender voor eindpunt, Microsoft Defender voor Office 365) en de reden waarom deze aan elkaar zijn gekoppeld.

![Afbeelding van de pagina voor incidentenwaarschuwingen](../../media/incident-alerts.png)

Standaard worden de waarschuwingen chronologisch geordend, zodat u eerst kunt zien hoe de aanval in de tijd heeft afgespeeld. Als u op een waarschuwing klikt, wordt u naar de relevante waarschuwingspagina geleid, waar u een uitgebreid onderzoek naar die waarschuwing kunt uitvoeren.

## <a name="devices"></a>Apparaten

Het tabblad Apparaten bevat alle apparaten waarop waarschuwingen met betrekking tot het incident worden weergegeven.

Als u op de naam klikt van de computer waarop de aanval is uitgevoerd, gaat u naar de pagina Computer van de computer waar u waarschuwingen kunt zien die hierop zijn geactiveerd en gerelateerde gebeurtenissen die zijn verstrekt om onderzoek te gemakt.

![Afbeelding van het tabblad computers van een incident](../../media/incident-machines.png)

Als u het tabblad Tijdlijn selecteert, kunt u door de tijdlijn van de computer bladeren en alle gebeurtenissen en het gedrag op de computer in chronologische volgorde bekijken, afgewisseld met de waarschuwingen omhoog.

## <a name="users"></a>Gebruikers

Bekijk gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan een bepaald incident.

Als u op de gebruikersnaam klikt, gaat u naar de pagina Cloud-app-beveiliging van de gebruiker, waar nader onderzoek kan worden uitgevoerd.

![Afbeelding van het tabblad Gebruikers van een incident](../../media/incident-users.png)

## <a name="mailboxes"></a>Postvakken

Onderzoek postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan een incident. Als u nog meer werk wilt doen, opent u Microsoft Defender voor Office 365 wanneer u de e-mailwaarschuwing selecteert, waar u herstelacties kunt ondernemen.

![Afbeelding van het tabblad Postvak van een incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Onderzoeken

Selecteer **Onderzoeken om** alle geautomatiseerde onderzoeken te zien die zijn geactiveerd door waarschuwingen in dit incident. De onderzoeken zullen herstelacties uitvoeren of wachten op goedkeuring van acties door analisten, afhankelijk van hoe u uw geautomatiseerde onderzoeken hebt geconfigureerd voor uitvoering in Microsoft Defender voor Eindpunt en Defender voor Office 365.

![Afbeelding van het tabblad Onderzoeken van een incident](../../media/incident-investigations.png)

Selecteer een onderzoek om naar de pagina met onderzoeksgegevens te gaan voor volledige informatie over het onderzoek en de herstelstatus. Als er acties in behandeling zijn voor goedkeuring als onderdeel van het onderzoek, worden ze weergegeven op het tabblad Acties in behandeling. Actie ondernemen als onderdeel van de oplossing voor incidenten.

## <a name="evidence"></a>Bewijs

Microsoft 365 Defender onderzoekt automatisch alle door incidenten ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u automatisch kunt reageren en informatie krijgt over de belangrijke bestanden, processen, services, e-mails en meer. Hiermee kunt u potentiële bedreigingen in het incident snel detecteren en blokkeren.

![Afbeelding van het tabblad Bewijs van een incident](../../media/incident-evidence.png)

Elk van de geanalyseerde entiteiten wordt gemarkeerd met een uitspraak (Schadelijk, Verdacht, Opsschoon), evenals een herstelstatus. Dit helpt u inzicht te krijgen in de herstelstatus van het hele incident en wat de volgende stappen zijn die kunnen worden ondernomen om het incident verder te herstellen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten beheren](manage-incidents.md)

