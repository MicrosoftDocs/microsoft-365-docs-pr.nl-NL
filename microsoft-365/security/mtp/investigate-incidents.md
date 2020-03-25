---
title: Incidenten in Microsoft Threat Protection onderzoeken
description: Analyseer incidenten met betrekking tot apparaten, gebruikers en postvakken.
keywords: incidenten, machines, apparaten, gebruikers, identiteiten, e-mail, e-mail, postvak, onderzoek, grafiek, bewijs
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
ms.openlocfilehash: 1883f61f50dad9b601329369bf180ddecba70138
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928960"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a>Incidenten in Microsoft Threat Protection onderzoeken

**Van toepassing op:**

- Microsoft-bedreigingsbeveiliging

Microsoft Threat Protection verzamelt alle gerelateerde waarschuwingen, activa, onderzoeken en bewijsmateriaal van al uw apparaten, gebruikers en postvakken om u een uitgebreide blik te geven op de gehele breedte van een aanval.

Onderzoek de waarschuwingen die van invloed zijn op uw netwerk, begrijp wat ze betekenen en verwerk bewijsmateriaal in verband met de incidenten, zodat u een effectief herstelplan opstellen.

## <a name="investigate-an-incident"></a>Onderzoek een incident

1. Selecteer een incident in de wachtrij voor incidenten. <BR> Hiermee wordt een zijpaneel geopend en wordt een voorbeeld gegeven van belangrijke informatie zoals status, ernst, categorieën en de getroffen entiteiten.

    ![Afbeelding van het zijpaneel van incident](../../media/incident-side-panel.png)

2. Selecteer **De pagina Incident openen openen**. <BR> Hiermee wordt de incidentpagina geopend waar u meer informatie vindt over incidentdetails, opmerkingen en acties, tabbladen (overzicht, waarschuwingen, apparaten, gebruikers, onderzoeken, bewijsmateriaal).

3. Bekijk de waarschuwingen, apparaten, gebruikers, andere entiteiten die betrokken zijn bij het incident.

## <a name="incident-overview"></a>Overzicht van incidenten

De overzichtspagina geeft u een momentopname van de belangrijkste dingen om op te merken over het incident.

![Afbeelding van de overzichtspagina voor incidenten](../../media/incidents-overview.png)

De aanvalscategorieën geven u een visueel en numeriek beeld van hoe geavanceerd de aanval is gevorderd tegen de kill chain. Net als bij andere Microsoft-beveiligingsproducten is Microsoft Threat Protection afgestemd op het [MITRE&trade; ATT-&CK-framework.](https://attack.mitre.org/)

De sectie scope geeft u een lijst met de belangrijkste getroffen activa die deel uitmaken van dit incident. Als er specifieke informatie over dit actief, zoals risiconiveau, onderzoek prioriteit evenals eventuele tagging op de activa zal dit ook naar boven komen in deze sectie.

De tijdlijn van waarschuwingen biedt een voorproefje van de chronologische volgorde waarin de waarschuwingen hebben plaatsgevonden, evenals de redenen waarom deze waarschuwingen verband houden met dit incident.

En ten slotte - het bewijs sectie biedt een samenvatting van hoeveel verschillende artefacten werden opgenomen in het incident en hun herstelstatus, zodat u onmiddellijk identificeren of er actie nodig is aan uw kant.

Dit overzicht kan helpen bij de eerste triage van het incident door inzicht te geven in de belangrijkste kenmerken van het incident waar u zich bewust van moet zijn.

## <a name="alerts"></a>Waarschuwingen

U alle waarschuwingen met betrekking tot het incident en andere informatie over het incident bekijken, zoals ernst, entiteiten die betrokken waren bij de waarschuwing, de bron van de waarschuwingen (Azure ATP, Microsoft Defender ATP, Office 365 ATP) en de reden waarom ze aan elkaar zijn gekoppeld.

![Afbeelding van de pagina incidentmeldingen](../../media/incident-alerts.png)

Standaard worden de waarschuwingen chronologisch geordend, zodat u eerst zien hoe de aanval in de loop van de tijd is afgespeeld. Als u op elke waarschuwing klikt, leidt u naar de relevante waarschuwingspagina waar u een diepgaand onderzoek naar die waarschuwing uitvoeren.

## <a name="devices"></a>Apparaten

Op het tabblad Apparaten worden alle apparaten weergegeven waar waarschuwingen met betrekking tot het incident worden weergegeven.

Als u op de naam klikt van de machine waar de aanval is uitgevoerd, navigeert u naar de machinepagina, waar u waarschuwingen zien die erop zijn geactiveerd en gerelateerde gebeurtenissen die worden verstrekt om het onderzoek te vergemakkelijken.

![Afbeelding van het tabblad machines van een incident](../../media/incident-machines.png)

Als u het tabblad Tijdlijn selecteert, u door de tijdlijn van de machine bladeren en alle gebeurtenissen en gedragingen die op de machine worden waargenomen in chronologische volgorde bekijken, afgewisseld met de opgehaalde waarschuwingen.

## <a name="users"></a>Gebruikers

Bekijk gebruikers waarvan is vastgesteld dat ze deel uitmaken van of gerelateerd zijn aan een bepaald incident.

Als u op de gebruikersnaam klikt, navigeert u naar de cloud-appbeveiligingspagina van de gebruiker, waar verder onderzoek kan worden uitgevoerd.

![Afbeelding van het tabblad gebruikers van een incident](../../media/incident-users.png)

## <a name="mailboxes"></a>Postvakken

Onderzoek postvakken waarvan is vastgesteld dat ze deel uitmaken van of gerelateerd zijn aan een incident. Als u verder onderzoekswerk wilt doen, opent u de waarschuwing voor e-mailgerelateerde meldingen van Office 365 Advanced Threat Protection, waar u herstelacties uitvoeren.

![Afbeelding van het postvaktabblad van een incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Onderzoeken

Selecteer **Onderzoeken** om alle geautomatiseerde onderzoeken te zien die worden geactiveerd door waarschuwingen in dit incident. De onderzoeken voeren herstelacties uit of wachten op goedkeuring door analisten van acties, afhankelijk van hoe u uw geautomatiseerde onderzoeken hebt geconfigureerd om uit te voeren in Microsoft Defender ATP en Office 365 Advanced Threat Protection.

![Afbeelding van het tabblad onderzoeken van een incident](../../media/incident-investigations.png)

Selecteer een onderzoek om naar de pagina Details van het Onderzoek te navigeren om volledige informatie over de status van het onderzoek en de herstelstatus te krijgen. Als er acties in behandeling zijn voor goedkeuring als onderdeel van het onderzoek, worden ze weergegeven op het tabblad In behandeling zijnde acties. Onderneem actie als onderdeel van incidentherstel.

## <a name="evidence"></a>Bewijs

Microsoft Threat Protection onderzoekt automatisch de ondersteunde gebeurtenissen en verdachte entiteiten van alle incidenten in de waarschuwingen, zodat u automatisch wordt gereageerd en informatie krijgt over de belangrijke bestanden, processen, services, e-mails en meer. Dit helpt bij het snel detecteren en blokkeren van potentiële bedreigingen in het incident.

![Afbeelding van het bewijstabblad van een incident](../../media/incident-evidence.png)

Elk van de geanalyseerde entiteiten zal worden gemarkeerd met een vonnis (Kwaadaardig, Verdacht, Schoon) en een herstelstatus. Dit helpt u bij het begrijpen van de herstelstatus van het gehele incident en wat de volgende stappen zijn die kunnen worden genomen om verder te herstellen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten beheren](manage-incidents.md)

