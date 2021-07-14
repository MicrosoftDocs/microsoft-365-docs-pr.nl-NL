---
title: Zoek- en analyseinstellingen configureren - Advanced eDiscovery
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
ms.custom: seo-marvel-mar2020
description: Configureer Advanced eDiscovery instellingen die van toepassing zijn op alle revisiesets in een zaak. Dit omvat instellingen voor analyse en optische tekenherkenning.
ms.openlocfilehash: e0ad41354b265016ba67632162a8ead62f11068b
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430550"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>Zoek- en analyseinstellingen configureren in Advanced eDiscovery

U kunt instellingen configureren voor elke Advanced eDiscovery om de volgende functionaliteit te beheren.

- In de buurt van duplicaten en e-mailthreading

- Thema's

- Query automatisch gegenereerde revisieset

- Tekst negeren

- Optische tekenherkenning

Zoek- en analyse-instellingen configureren voor een zaak:

1. Selecteer op **Advanced eDiscovery** pagina het hoofdje.

2. Klik op **Instellingen** tabblad Zoeken & **op** **Selecteren.**

   De pagina met hoofd- en hoofdinstellingen wordt weergegeven. Deze instellingen worden toegepast op alle revisiesets in een zaak.

   ![Analyse- en zoekinstellingen voor een Advanced eDiscovery configureren](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>In de buurt van duplicaten en e-mailthreading

In deze sectie kunt u parameters instellen voor dubbele detectie, bijna dubbele detectie en e-mailthreading. Zie Near [duplicate detection and](near-duplicate-detection-in-advanced-ediscovery.md) Email threading (Bijna dubbele detectie en [E-mailthreading) voor meer informatie.](email-threading-in-advanced-ediscovery.md)

- **Near duplicates/email threading:** Wanneer deze is ingeschakeld, worden dubbele detectie, bijna dubbele detectie en e-mailthreading opgenomen als onderdeel van de werkstroom wanneer u analyses op de gegevens in een revisieset uitwerkt.

- **Drempelwaarde voor document- en e-mail gelijkenis:** Als het vergelijkbaarheidsniveau voor twee documenten boven de drempelwaarde ligt, worden beide documenten in dezelfde bijna dubbele set gezet.

- **Minimum/maximum aantal woorden:** In deze instellingen wordt aangegeven dat in de buurt van duplicaten en e-mailthreading alleen wordt uitgevoerd op documenten met ten minste het minimum aantal woorden en maximaal het maximum aantal woorden.

## <a name="themes"></a>Thema's

In deze sectie kunt u parameters voor thema's instellen. Zie Thema's voor [meer informatie.](themes-in-advanced-ediscovery.md)

- **Thema's:** Wanneer deze is ingeschakeld, wordt het clusteren van thema's uitgevoerd als onderdeel van de werkstroom wanneer u analyses op de gegevens in een revisieset uitwerkt.

- **Maximum aantal thema's:** Hiermee geeft u het maximum aantal thema's op dat kan worden gegenereerd wanneer u analyses op de gegevens in een revisieset uit te voeren.

- **Getallen opnemen in thema's:** Wanneer deze is ingeschakeld, worden getallen (waarmee een thema wordt vermeld) opgenomen bij het genereren van thema's. 

- **Het maximum aantal thema's dynamisch aanpassen:** In bepaalde situaties zijn er mogelijk onvoldoende documenten in een revisieset om het gewenste aantal thema's te produceren. Wanneer deze instelling is ingeschakeld, wordt Advanced eDiscovery het maximum aantal thema's dynamisch aangepast in plaats van het maximum aantal thema's af te dwingen.

## <a name="review-set-query"></a>Revisiesetquery

Als u het selectievakje **Automatisch een** opgeslagen zoekactie voor revisie maken na analyse in selecteert, Advanced eDiscovery query voor de autogenerates van de revisieset met de naam **Voor revisie.** 

![De automatisch gegenereerde query Voor revisie](../media/AeDForReviewQuery.png)

Met deze query worden in feite dubbele items uit de revisieset gefilterd. Hiermee kunt u de unieke items in de revisieset bekijken. Deze query wordt alleen gemaakt wanneer u analyses uitvoert voor een revisieset in de zaak. Zie Query's uitvoeren op de gegevens in een revisieset voor meer informatie over [revisiesetquery's.](review-set-search.md)

## <a name="ignore-text"></a>Tekst negeren

Er zijn situaties waarin bepaalde tekst de kwaliteit van de analyse vermindert, zoals lange vrijwaringen die worden toegevoegd aan e-mailberichten, ongeacht de inhoud van de e-mail. Als u weet van tekst die moet worden genegeerd, kunt u deze uitsluiten van analyse door de tekenreeks en de analysefunctionaliteit (Near-duplicates, Email threading, Themes en Relevantie) op te geven waarin de tekst moet worden uitgesloten. Het gebruik van reguliere expressies (RegEx) als genegeerde tekst wordt ook ondersteund. 

## <a name="optical-character-recognition-ocr"></a>OcR (Optical Character Recognition)

Wanneer deze instelling is ingeschakeld, wordt OCR-verwerking uitgevoerd op afbeeldingsbestanden. OCR-verwerking wordt uitgevoerd in de volgende situaties:

- Wanneer bewaarders en [niet-bewaardergegevensbronnen](non-custodial-data-sources.md) aan een zaak worden toegevoegd. OCR-verwerking wordt uitgevoerd tijdens het [proces voor geavanceerde indexering.](indexing-custodian-data.md) OCR wordt alleen uitgevoerd op items die tijdens geavanceerde indexering worden verwerkt. Als bijvoorbeeld een groot PDF-bestand dat gedeeltelijk is geïndexeerd of andere indexeringsfouten heeft gehad, wordt verwerkt tijdens geavanceerde indexering, wordt in het bestand ook OCR toegepast. Met andere woorden, OCR-verwerking vindt alleen plaats op bestanden die opnieuw worden geïndexeerd tijdens het proces voor geavanceerde indexering. Dit betekent dat situaties waarin bewaarders worden toegevoegd aan een zaak, sommige e-mailbijlagen niet worden verwerkt voor OCR omdat deze bestanden niet worden verwerkt tijdens geavanceerde indexering. Wanneer OCR wordt toegepast op afbeeldingsbestanden, kan de tekst in die afbeeldingsbestanden worden doorzocht tijdens een verzameling.

- Wanneer inhoud uit andere gegevensbronnen (die niet zijn gekoppeld aan een bewaarder en die in een niet-bewaardergegevensbron aan de zaak is toegevoegd) wordt toegevoegd aan een revisieset.

Nadat gegevens aan een revisieset zijn toegevoegd, kan afbeeldingstekst worden gecontroleerd, doorzocht, gelabeld en geanalyseerd. U kunt de uitgepakte tekst weergeven in de tekstviewer van het geselecteerde afbeeldingsbestand in de revisieset. Zie voor meer informatie:

- [Geavanceerde indexering van beheerdersgegevens](indexing-custodian-data.md)

- [Zoekresultaten toevoegen aan een controleset](add-data-to-review-set.md#optical-character-recognition)

- [Ondersteunde afbeeldingsbestandstypen](supported-filetypes-ediscovery20.md#image)
