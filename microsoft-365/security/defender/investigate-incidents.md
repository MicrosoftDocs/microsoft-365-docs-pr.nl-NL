---
title: Incidenten in Microsoft 365 Defender onderzoeken
description: Incidenten met betrekking tot apparaten, gebruikers en postvakken onderzoeken.
keywords: incident, incidenten, analyseren, reactie, machines, apparaten, gebruikers, identiteiten, e-mail, e-mail, postvak, onderzoek, grafiek, bewijs
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
ms.openlocfilehash: 7abc99a14ec538afea8cdbd4d8f3b4940bcccd9f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300083"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Incidenten in Microsoft 365 Defender onderzoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

Microsoft 365 Defender verzamelt alle gerelateerde waarschuwingen, activa, onderzoeken en bewijs van al uw apparaten, gebruikers en postvakken tot een incident om u een uitgebreid overzicht te geven van de hele breedte van een aanval.

In een incident analyseert u de waarschuwingen die van invloed zijn op uw netwerk, begrijpt u wat ze betekenen en colleert u het bewijs zodat u een effectief herstelplan kunt maken.

## <a name="initial-investigation"></a>Eerste onderzoek

Voordat u de details bekijkt, bekijkt u de eigenschappen en samenvatting van het incident.

U kunt beginnen met het selecteren van het incident in de kolom vinkje. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Voorbeeld van het selecteren van een incident in de kolom vinkje":::

Wanneer u dit doet, wordt een overzichtsvenster geopend met belangrijke informatie over het incident, zoals ernst, aan wie het is toegewezen en de [MITRE-att-&CK-categorieën &trade; ](https://attack.mitre.org/) voor het incident. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Voorbeeld van het overzichtsvenster voor een incident":::

Hier kunt u Incidentpagina **openen selecteren.** Hiermee opent u de hoofdpagina voor het incident, waar u meer overzichtsinformatie en tabbladen vindt voor waarschuwingen, apparaten, gebruikers, onderzoeken en bewijs.

U kunt ook de hoofdpagina voor een incident openen door de naam van het incident te selecteren in de incidentwachtrij.

## <a name="summary"></a>Samenvatting

Op **de** pagina Overzicht ziet u een momentopname van de belangrijkste dingen die u van het incident kunt zien.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Voorbeeld van de pagina Overzicht voor een incident in het Microsoft 365 beveiligingscentrum":::

De aanvalscategorieën geven u een visuele en numerieke weergave van de voortgang van de aanval ten opzichte van de kill chain. Net als bij andere Microsoft-beveiligingsproducten is Microsoft 365 Defender uitgelijnd op het [MITRE ATT-&&trade; CK-framework.](https://attack.mitre.org/)

In de sectie bereik ziet u een lijst met de belangrijkste beïnvloede activa die deel uitmaken van dit incident. Als er specifieke informatie over dit activum is, zoals risiconiveau, onderzoeksprioriteit en taggen op de activa, wordt dit ook in deze sectie aan de oppervlakte gebracht.

De tijdlijn met waarschuwingen biedt een voorproefje van de chronologische volgorde waarin de waarschuwingen zijn opgetreden, evenals de redenen waarom deze waarschuwingen zijn gekoppeld aan dit incident.

En als laatste: de sectie bewijs bevat een overzicht van het aantal verschillende artefacten dat is opgenomen in het incident en de herstelstatus, zodat u direct kunt vaststellen of u actie moet ondernemen.

Dit overzicht kan helpen bij de eerste triage van het incident door inzicht te geven in de belangrijkste kenmerken van het incident waar u rekening mee moet houden.

## <a name="alerts"></a>Waarschuwingen

Op het **tabblad** Waarschuwing kunt u de waarschuwingswachtrij weergeven voor waarschuwingen met betrekking tot het incident en andere informatie over het incident, zoals:

- Ernst.
- De entiteiten die betrokken waren bij de waarschuwing.
- De bron van de waarschuwingen (Microsoft Defender voor identiteit, Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365).
- De reden waarom ze aan elkaar zijn gekoppeld.

Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Voorbeeld van een pagina Waarschuwingen voor een incident":::

Standaard worden de waarschuwingen chronologisch geordend, zodat u kunt zien hoe het incident zich in de tijd heeft afgespeeld. Als u elke waarschuwing selecteert, gaat u naar de hoofdpagina van de waarschuwing, waar u een grondige analyse van die waarschuwing kunt uitvoeren. 

Lees hoe u de waarschuwingswachtrij en waarschuwingspagina's kunt gebruiken in [waarschuwingen onderzoeken.](investigate-alerts.md)

## <a name="devices"></a>Apparaten

Op **het** tabblad Apparaten vindt u alle apparaten die met het incident te maken hebben. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Voorbeeld van een pagina Apparaten voor een incident":::

U kunt het vinkje voor een apparaat selecteren om details van het apparaat, adreslijstgegevens, actieve waarschuwingen en aangemelde gebruikers te bekijken. Selecteer de naam van het apparaat om apparaatgegevens weer te geven in de apparaatvoorraad van Microsoft Defender for Endpoints.

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Voorbeeld van een pagina met apparaten voor Microsoft Defender voor eindpunten":::

Op de apparaatpagina kunt u aanvullende informatie over het apparaat verzamelen, zoals alle waarschuwingen, een tijdlijn en beveiligingsaanbevelingen. Op het tabblad  Tijdlijn kunt u bijvoorbeeld door de tijdlijn van de machine bladeren en alle gebeurtenissen en gedragingen bekijken die op de computer in chronologische volgorde worden waargenomen, afgewisseld met de waarschuwingen die zijn opgeheven.

> [!TIP]
> U kunt op aanvraag scans uitvoeren op een apparaatpagina. Kies in Microsoft 365 beveiligingscentrum de optie **Eindpunten > Apparaatvoorraad.** Selecteer een apparaat met waarschuwingen en voer een antivirusscan uit. Acties, zoals antivirusscans, worden bijgespoord en zijn zichtbaar op de **pagina Apparaatvoorraad.** Zie De scan uitvoeren [Microsoft Defender Antivirus apparaten voor meer informatie.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)

## <a name="users"></a>Gebruikers

Het **tabblad** Gebruikers bevat alle gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Voorbeeld van een pagina Gebruikers voor een incident":::

U kunt het vinkje selecteren voor een gebruiker om details van de bedreiging, blootstelling en contactgegevens van het gebruikersaccount te bekijken. Selecteer de gebruikersnaam om meer details van het gebruikersaccount te zien.

## <a name="mailboxes"></a>Postvakken

Het **tabblad Postvakken** bevat alle postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Voorbeeld van een pagina Postvakken voor een incident":::

U kunt het vinkje voor een postvak selecteren om een lijst met actieve waarschuwingen weer te geven. Selecteer de naam van het postvak om extra postvakgegevens te zien op de explorerpagina voor Microsoft Defender voor Office 365.

## <a name="investigations"></a>Onderzoeken

Het **tabblad Onderzoeken** bevat alle geautomatiseerde onderzoeken [die](m365d-autoir.md) worden veroorzaakt door waarschuwingen bij dit incident. De onderzoeken zullen herstelacties uitvoeren of wachten op goedkeuring door analisten van acties, afhankelijk van hoe u uw geautomatiseerde onderzoeken hebt geconfigureerd voor uitvoering in Microsoft Defender voor Eindpunt en Defender voor Office 365.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Voorbeeld van een pagina Onderzoeken voor een incident":::

Selecteer een onderzoek om naar de pagina Details van het onderzoek te gaan voor volledige informatie over de status van het onderzoek en de herstelstatus. Als er acties in behandeling zijn voor goedkeuring als onderdeel van het onderzoek, worden deze weergegeven op het tabblad Acties in behandeling. Actie ondernemen als onderdeel van het herstellen van incidenten.

Zie Geautomatiseerd onderzoek en antwoord [in Microsoft 365 Defender voor meer informatie.](m365d-autoir.md)

## <a name="evidence-and-response"></a>Bewijs en antwoord

Op **het tabblad Bewijs** en antwoord ziet u alle ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen in het incident. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Voorbeeld van een pagina Bewijs en antwoord voor een incident":::

Microsoft 365 Defender onderzoekt automatisch alle door incidenten ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen, zodat u informatie krijgt over de belangrijke e-mailberichten, bestanden, processen, services, IP-adressen en meer. Op deze manier kunt u potentiële bedreigingen in het incident snel opsporen en blokkeren.

Elk van de geanalyseerde entiteiten is gemarkeerd met een vonnis (Schadelijk, Verdacht, Schoon) en een herstelstatus. Op deze manier begrijpt u de herstelstatus van het hele incident en welke volgende stappen u kunt ondernemen.

## <a name="graph-in-preview"></a>Graph (in voorbeeld)

Met het nieuwe **Graph** (in voorbeeld), kunt u het volgende zien:

- De verbinding van waarschuwingen met de beïnvloede activa in uw organisatie.
- Welke entiteiten zijn gerelateerd aan welke waarschuwingen en hoe ze deel uitmaken van het verhaal van de aanval.
- De waarschuwingen voor het incident.

Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="Voorbeeld van een Graph pagina voor een incident":::

De incidentgrafiek helpt u snel het volledige bereik van de aanval te begrijpen door de verschillende verdachte entiteiten die deel uitmaken van de aanval te verbinden met hun gerelateerde assets, zoals gebruikers, apparaten en postvakken. 

U kunt nu begrijpen hoe de aanval zich in de afgelopen tijd via uw netwerk heeft verspreid, waar de aanval is gestart en hoe ver de aanval is gegaan.

## <a name="next-steps"></a>Volgende stappen

Zo nodig:

- [De waarschuwingen van een incident onderzoeken](investigate-alerts.md)
- [De gebruikers van een incident onderzoeken](investigate-users.md)

## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten beheren](manage-incidents.md)

