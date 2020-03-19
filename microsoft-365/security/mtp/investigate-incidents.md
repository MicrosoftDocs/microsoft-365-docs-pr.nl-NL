---
title: Incidenten onderzoeken in Microsoft Threat Protection
description: Analyseer incidenten met betrekking tot apparaten, gebruikers en postvakken.
keywords: incidenten, incidenten, machines, apparaten, gebruikers, identiteiten, e-mail, e-mail, mailbox, onderzoek, grafiek, bewijs
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
ms.openlocfilehash: 82069224a3f38357e52c2772c984d20d6597342d
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857485"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a>Incidenten onderzoeken in Microsoft Threat Protection

**Van toepassing op:**

- Microsoft-bedreigingsbeveiliging

Microsoft Threat Protection verzamelt alle gerelateerde waarschuwingen, assets, onderzoeken en bewijsmateriaal van alle apparaten, gebruikers en postvakken om u een uitgebreid overzicht te geven van de gehele breedte van een aanval.

Onderzoek de waarschuwingen die van invloed zijn op uw netwerk, begrijp wat ze betekenen en collate bewijs in verband met de incidenten, zodat u een effectief herstelplan bedenken.

## <a name="investigate-an-incident"></a>Een incident onderzoeken

1. Selecteer een incident in de wachtrij voor incidenten. <BR> Hiermee wordt een zijpaneel geopend en wordt een voorbeeld gegeven van belangrijke informatie zoals status, ernst, categorieën en de getroffen entiteiten.

    ![Afbeelding van het zijpaneel van incidenten](../../media/incident-side-panel.png)

2. Selecteer **Incidentpagina openen**. <BR> Hiermee wordt de incidentenpagina geopend waar u meer informatievindt over incidentgegevens, opmerkingen en acties, tabbladen (overzicht, waarschuwingen, apparaten, gebruikers, onderzoeken, bewijsmateriaal).

3. Bekijk de waarschuwingen, apparaten, gebruikers, andere entiteiten die betrokken zijn bij het incident.

## <a name="incident-overview"></a>Incidentoverzicht

De overzichtspagina geeft u een momentopname een blik in de bovenste dingen om op te merken over het incident.

![Afbeelding van de overzichtspagina incidenten](../../media/incidents-overview.png)

De aanvalscategorieën geven u een visueel en numeriek beeld van hoe geavanceerd de aanval is gevorderd tegen de kill chain. Net als bij andere Microsoft-beveiligingsproducten is Microsoft Threat Protection afgestemd op het [MITRE&trade; ATT-&CK-framework.](https://attack.mitre.org/)

De sectie bereik geeft u een lijst met de belangrijkste beïnvloede activa die deel uitmaken van dit incident. Als er specifieke informatie over dit actief, zoals risiconiveau, onderzoek prioriteit evenals eventuele tagging op de activa zal dit ook opduiken in deze sectie.

De tijdlijn met waarschuwingen biedt een voorproefje van de chronologische volgorde waarin de waarschuwingen zijn opgetreden, evenals de redenen dat deze waarschuwingen verband houden met dit incident.

En als laatste - de bewijssectie geeft een samenvatting van hoeveel verschillende artefacten zijn opgenomen in het incident en hun herstelstatus, zodat u onmiddellijk identificeren of er actie nodig is aan uw kant.

Dit overzicht kan helpen bij de eerste triage van het incident door inzicht te geven in de topkenmerken van het incident waarvan u op de hoogte moet zijn.

## <a name="alerts"></a>Waarschuwingen

U alle waarschuwingen met betrekking tot het incident en andere informatie over het incident bekijken, zoals de ernst, entiteiten die betrokken waren bij de waarschuwing, de bron van de waarschuwingen (Azure ATP, Microsoft Defender ATP, Office 365 ATP) en de reden waarom ze met elkaar zijn verbonden.

![Afbeelding van de pagina incidentwaarschuwingen](../../media/incident-alerts.png)

Standaard worden de waarschuwingen chronologisch geordend, zodat u eerst zien hoe de aanval zich in de loop van de tijd heeft afgespeeld. Als u op elke waarschuwing klikt, leidt u naar de relevante waarschuwingspagina waar u een diepgaand onderzoek naar die waarschuwing uitvoeren.

## <a name="devices"></a>Apparaten

Het tabblad Apparaten bevat alle apparaten waar waarschuwingen met betrekking tot het incident worden gezien.

Als u op de naam van de machine klikt waar de aanval is uitgevoerd, navigeert u naar de machinepagina waar u waarschuwingen zien die daarop zijn geactiveerd en gerelateerde gebeurtenissen die zijn verstrekt om het onderzoek te vergemakkelijken.

![Afbeelding van het tabblad machines van een incident](../../media/incident-machines.png)

Als u het tabblad Tijdlijn selecteert, u door de tijdlijn van de machine bladeren en alle gebeurtenissen en gedragingen bekijken die op de machine in chronologische volgorde worden waargenomen, afgewisseld met de opgehaalde waarschuwingen.

## <a name="users"></a>Gebruikers

Bekijk gebruikers waarvan is vastgesteld dat ze deel uitmaken van of verband houden met een bepaald incident.

Als u op de gebruikersnaam klikt, gaat u naar de cloudappbeveiligingspagina van de gebruiker waar verder onderzoek kan worden uitgevoerd.

![Afbeelding van het tabblad gebruikers van een incident](../../media/incident-users.png)

## <a name="mailboxes"></a>Postvakken

Onderzoek mailboxen waarvan is vastgesteld dat ze deel uitmaken van of verband houden met een incident. Als u verder onderzoekswerk wilt doen, opent u office 365 Advanced Threat Protection bij het selecteren van de e-mail, waar u herstelacties uitvoeren.

![Afbeelding van postvakrekening van een incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Onderzoeken

Selecteer **Onderzoeken** om alle geautomatiseerde onderzoeken te zien die worden geactiveerd door waarschuwingen in dit incident. De onderzoeken voeren herstelacties uit of wachten op goedkeuring door analisten van acties, afhankelijk van hoe u uw geautomatiseerde onderzoeken hebt geconfigureerd om te worden uitgevoerd in Microsoft Defender ATP en Office 365 Advanced Threat Protection.

![Afbeelding van het tabblad onderzoeken van een incident](../../media/incident-investigations.png)

Selecteer een onderzoek om naar de pagina Onderzoeksgegevens te navigeren om volledige informatie te krijgen over de onderzoeks- en herstelstatus. Als er acties in behandeling zijn voor goedkeuring als onderdeel van het onderzoek, worden ze weergegeven op het tabblad In behandeling zijnde acties. Onderneem actie in het kader van incidentsanering.

## <a name="evidence"></a>Bewijs

Microsoft Threat Protection onderzoekt automatisch alle ondersteunde gebeurtenissen en verdachte entiteiten van de incidenten in de waarschuwingen, zodat u automatisch reageren en informatie krijgt over de belangrijke bestanden, processen, services, e-mails en meer. Dit helpt bij het snel detecteren en blokkeren van potentiële bedreigingen in het incident.

![Afbeelding van het bewijstabblad van een incident](../../media/incident-evidence.png)

Elk van de geanalyseerde entiteiten wordt gemarkeerd met een vonnis (Kwaadaardig, Verdacht, Schoon) en een herstelstatus. Dit helpt u bij het begrijpen van de herstelstatus van het hele incident en wat zijn de volgende stappen die kunnen worden genomen om verder te saneren.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten prioriteren](incident-queue.md)
- [Incidenten beheren](manage-incidents.md)
- [Gebeurtenissen en waarschuwingen op een specifieke machine bekijken](machine-profile.md)
