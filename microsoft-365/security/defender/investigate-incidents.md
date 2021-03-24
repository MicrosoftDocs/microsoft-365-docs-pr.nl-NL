---
title: Incidenten in Microsoft 365 Defender onderzoeken
description: Incidenten met betrekking tot apparaten, gebruikers en postvakken analyseren.
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
ms.openlocfilehash: 10fa2765a4fe5bd256e0588af0db51f5a22339a2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057269"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Incidenten in Microsoft 365 Defender onderzoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**

- Microsoft 365 Defender

Microsoft 365 Defender verzamelt alle gerelateerde waarschuwingen, activa, onderzoeken en bewijzen van al uw apparaten, gebruikers en postvakken om u een uitgebreid overzicht te geven van de hele breedte van een aanval.

Onderzoek de waarschuwingen die van invloed zijn op uw netwerk, begrijp wat ze betekenen en beslep bewijs dat aan de incidenten is gekoppeld, zodat u een effectief herstelplan kunt bedenken.

## <a name="investigate-an-incident"></a>Een incident onderzoeken

1. Selecteer een incident in de wachtrij voor incidenten. <BR> Een zijpaneel wordt geopend en geeft een voorbeeld van belangrijke informatie, zoals status, ernst, categorieën en de beïnvloede entiteiten.

    ![Afbeelding van het zijpaneel incident](../../media/incident-side-panel.png)

2. Selecteer **Incidentpagina openen.** <BR> Hiermee opent u de pagina met incidenten waar u meer informatie vindt over incidentgegevens, opmerkingen en acties, tabbladen (overzicht, waarschuwingen, apparaten, gebruikers, onderzoeken, bewijs).

3. Controleer de waarschuwingen, apparaten, gebruikers en andere entiteiten die betrokken zijn bij het incident.

## <a name="incident-overview"></a>Overzicht van incidenten

Op de overzichtspagina ziet u een momentopname van de belangrijkste dingen die u kunt zien over het incident.

![Afbeelding van de overzichtspagina incidenten](../../media/incidents-overview.png)

De aanvalscategorieën geven u een visuele en numerieke weergave van de voortgang van de aanval ten opzichte van de kill chain. Net als bij andere Microsoft-beveiligingsproducten is Microsoft 365 Defender uitgelijnd op het [MITRE ATT-&&trade; CK-framework.](https://attack.mitre.org/)

In de sectie bereik ziet u een lijst met de belangrijkste beïnvloede activa die deel uitmaken van dit incident. Als er specifieke informatie over dit activum is, zoals risiconiveau, onderzoeksprioriteit en taggen op de activa, wordt dit ook in deze sectie aan de oppervlakte gebracht.

De tijdlijn voor waarschuwingen biedt een voorproefje van de chronologische volgorde waarin de waarschuwingen zijn opgetreden, evenals de redenen waarom deze waarschuwingen zijn gekoppeld aan dit incident.

En als laatste: de sectie bewijs bevat een overzicht van het aantal verschillende artefacten dat is opgenomen in het incident en de herstelstatus, zodat u direct kunt vaststellen of er actie moet worden ondernomen aan uw kant.

Dit overzicht kan helpen bij de eerste triage van het incident door inzicht te geven in de belangrijkste kenmerken van het incident dat u moet weten.

## <a name="alerts"></a>Waarschuwingen

U kunt alle waarschuwingen bekijken die betrekking hebben op het incident en andere informatie over het incident, zoals ernst, entiteiten die betrokken waren bij de waarschuwing, de bron van de waarschuwingen (Microsoft Defender voor identiteit, Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365) en de reden waarom ze aan elkaar zijn gekoppeld.

![Afbeelding van de pagina met incidentenwaarschuwingen](../../media/incident-alerts.png)

Standaard worden de waarschuwingen chronologisch geordend, zodat u eerst kunt zien hoe de aanval in de tijd is uitgevoerd. Als u op elke waarschuwing klikt, gaat u naar de relevante waarschuwingspagina waar u een uitgebreid onderzoek naar die waarschuwing kunt uitvoeren. Informatie over het gebruik van waarschuwingspagina's en de geïntegreerde waarschuwingswachtrij in [Waarschuwingen onderzoeken](investigate-alerts.md)

## <a name="devices"></a>Apparaten

Het tabblad Apparaten bevat alle apparaten waar waarschuwingen met betrekking tot het incident worden weergegeven.

Als u op de naam klikt van de computer waarop de aanval is uitgevoerd, gaat u naar de pagina Machine, waar u waarschuwingen kunt zien die zijn geactiveerd op de computer en gerelateerde gebeurtenissen die zijn verstrekt om het onderzoek te soepeeren.

![Afbeelding van het tabblad Machines van een incident](../../media/incident-machines.png)

Als u het tabblad Tijdlijn selecteert, kunt u door de tijdlijn van de machine bladeren en alle gebeurtenissen en gedragingen op de computer in chronologische volgorde bekijken, afgewisseld met de waarschuwingen die worden weergegeven.

## <a name="users"></a>Gebruikers

Zie gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan een bepaald incident.

Als u op de gebruikersnaam klikt, gaat u naar de pagina Cloud App-beveiliging van de gebruiker, waar verder onderzoek kan worden uitgevoerd.

![Afbeelding van het tabblad Gebruikers van een incident](../../media/incident-users.png)

## <a name="mailboxes"></a>Postvakken

Onderzoek postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan een incident. Als u verder onderzoek wilt doen, opent u Microsoft Defender voor Office 365 door de waarschuwing voor e-mail te selecteren, waar u herstelacties kunt uitvoeren.

![Afbeelding van het tabblad Postvak van een incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Onderzoeken

Selecteer **Onderzoeken om** alle geautomatiseerde onderzoeken te zien die worden veroorzaakt door waarschuwingen in dit incident. De onderzoeken zullen herstelacties uitvoeren of wachten op goedkeuring door analisten van acties, afhankelijk van hoe u uw geautomatiseerde onderzoeken hebt geconfigureerd voor uitvoering in Microsoft Defender voor Eindpunt en Defender voor Office 365.

![Afbeelding van het tabblad Onderzoeken van een incident](../../media/incident-investigations.png)

Selecteer een onderzoek om naar de pagina Details van het onderzoek te gaan voor volledige informatie over de status van het onderzoek en de herstelstatus. Als er acties in behandeling zijn voor goedkeuring als onderdeel van het onderzoek, worden deze weergegeven op het tabblad Acties in behandeling. Actie ondernemen als onderdeel van het herstellen van incidenten.

## <a name="evidence"></a>Bewijs

Microsoft 365 Defender onderzoekt automatisch alle door incidenten ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u automatisch kunt reageren en informatie krijgt over de belangrijke bestanden, processen, services, e-mailberichten en meer. Op deze manier kunt u potentiële bedreigingen in het incident snel opsporen en blokkeren.

![Afbeelding van het tabblad Bewijs van een incident](../../media/incident-evidence.png)

Elk van de geanalyseerde entiteiten wordt gemarkeerd met een vonnis (Schadelijk, Verdacht, Schoon) en een herstelstatus. Dit helpt u bij het begrijpen van de herstelstatus van het hele incident en wat de volgende stappen zijn die kunnen worden genomen om verder te corrigeren.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten beheren](manage-incidents.md)

