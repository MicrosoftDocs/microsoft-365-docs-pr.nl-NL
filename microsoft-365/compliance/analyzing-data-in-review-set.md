---
title: Gegevens analyseren in een revisieset in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Meer informatie over de hulpprogramma's die beschikbaar zijn om documentsets te ordenen bij het analyseren van een Advanced eDiscovery geval.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/05/2021
ms.locfileid: "52161654"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Gegevens analyseren in een revisieset in Advanced eDiscovery

Wanneer het aantal verzamelde documenten groot is, kan het lastig zijn om ze allemaal te bekijken. Advanced eDiscovery bevat een aantal hulpprogramma's om de documenten te analyseren om het volume van de documenten te beperken dat moet worden gecontroleerd zonder dat er gegevens verloren gaan en om u te helpen de documenten op een samenhangende manier te ordenen. Zie het volgende voor meer informatie over deze mogelijkheden:

- [Detectie van bijna-duplicaten](near-duplicate-detection-in-advanced-ediscovery.md)

- [E-mailthreads](email-threading-in-advanced-ediscovery.md)

- [Thema's](themes-in-advanced-ediscovery.md)

Gegevens in een revisieset analyseren:

1. Configureer de analyse-instellingen voor uw zaak. Zie Zoek- en [analyseinstellingen configureren](configure-search-and-analytics-settings-in-advanced-ediscovery.md)voor meer informatie.

2. Open de revisieset die u wilt analyseren.

3. Klik **op Controleset beheren.**

4. Klik **op Analyse uitvoeren voor de revisieset.**

U kunt de voortgang van de analyse controleren op het **tabblad Taken** van de zaak.

 Nadat de analyse is voltooid, kunt u het analyserapport bekijken, query's in de revisieset uitvoeren op uitvoer van de analyse (zie [Query in](review-set-search.md)uw revisieset) en gerelateerde documenten van een bepaald document bekijken (zie Gegevens controleren [in](reviewing-data-in-review-set.md)revisieset).

## <a name="analytics-report"></a>Analyserapport

Een analyserapport weergeven voor een revisieset:

1. Open de revisieset.

2. Klik **op Controleset beheren.**

3. Klik **op Rapport weergeven.**

Het rapport bevat zeven onderdelen uit de analyse:

- **Doelpopulatie:** Het aantal e-mailberichten, bijlagen en losse documenten in de revisieset.

- **Documenten (met uitzondering van bijlagen):** Het aantal losse documenten dat draait, uniek in de buurt van duplicaten van een draaipunt of een exact duplicaat van een ander document.

- **E-mailberichten:** Het aantal e-mailberichten dat inclusief is, inclusief kopieën, inclusief minnen of geen van de bovenstaande.

- **Bijlagen:** Het aantal e-mailbijlagen dat uniek is of duplicaten van een andere e-mailbijlage in de revisieset.

- **Aantal bestanden per type:** Het aantal bestanden dat is geïdentificeerd met de bestandsextensie.

- **Documenten per bron:** Een overzicht van de inhoud door de oorspronkelijke gegevensbron.

- **Documenten die zijn samengevoegd per proces:** Een overzicht van de inhoud via revisiesetprocessen. 
