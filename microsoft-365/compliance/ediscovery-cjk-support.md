---
title: Ondersteuning voor CJK/Double Byte voor Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lees hoe Advanced eDiscovery in Microsoft 365 Chinese, Japanse en Koreaanse talen (CJK) ondersteunt, waarbij een dubbele bytetekenset wordt gebruikt.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162160"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>CJK-taalondersteuning voor Advanced eDiscovery

Advanced eDiscovery ondersteunt dubbel bytetekensettalen (zoals Vereenvoudigd Chinees, Traditioneel Chinees, Japans en Koreaans, die gezamenlijk *CJK-talen* worden genoemd) voor de volgende geavanceerde scenario's in een revisieset:

- Wanneer u [een query uitvoert op de gegevens in een revisieset.](review-set-search.md)

- Wanneer u [documenten tagt in een revisieset.](tagging-documents.md)

- Wanneer u [casegegevens in een revisieset analyseert](analyzing-data-in-review-set.md) met behulp van bijna dubbele detectie, e-mailthreading en themaanalyse.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

**Hoe maak ik een zoekopdracht om items te verzamelen die CJK-tekens bevatten?**

U kunt CJK-tekens gebruiken [](keyword-queries-and-search-conditions.md) voor [zoektermen,](building-search-queries.md#keyword-searches)trefwoordquery's en zoekvoorwaarden bij het zoeken naar inhoud in Advanced eDiscovery. Het zoeken naar CJK-tekens wordt ook ondersteund bij het zoeken naar inhoud in Core eDiscovery en Inhoud zoeken.

We bieden CJK-ondersteuning voor [](keyword-queries-and-search-conditions.md#search-conditions)alle [zoekoperatoren](keyword-queries-and-search-conditions.md#search-operators) en **zoekvoorwaarden,** inclusief de booleaanse operatoren **AND,** **OR,** **NOT** en NEAR.

Als u er zeker van bent dat inhoudslocaties of -items CJK-tekens bevatten, maar zoekopdrachten geen resultaten opleveren, klikt u op het pictogram querytaal/regio ![Pictogram Querytaal/regio in zoeken naar inhoud](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) en selecteer de bijbehorende cultuurcodewaarde voor taalland voor de zoekopdracht. De standaardtaal/-regio is neutraal.

**Kan ik meerdere talen tegelijk zoeken?**

Dit is afhankelijk van uw zoekscenario.

- Wanneer u [gegevens opvraagt in een revisieset](review-set-search.md) in Advanced eDiscovery, kunt u naar meerdere talen zoeken.

- Wanneer u [een zoekopdracht maakt om gegevens te verzamelen,](create-search-to-collect-data.md)maakt u een afzonderlijke zoekopdracht voor elke taal die u wilt gebruiken. Als u bijvoorbeeld zoekt naar een document dat zowel Chinees als Koreaans bevat, selecteert u Chinees voor uw eerste query en selecteert u Koreaans voor uw tweede query.

**Ik zie het pictogram querytaal/regio niet om een taal voor query's in een revisieset te selecteren. Hoe kan ik een querytaal opgeven in een zoekopdracht voor revisiesets?**

Voor revisiesetquery's hoeft u geen documenttaal op te geven. Advanced eDiscovery detecteert automatisch documenttalen wanneer u inhoud toevoegt aan een revisieset. Dit helpt u bij het optimaliseren van de queryresultaten in een revisieset.

**Kan ik gedetecteerde talen in bestandsmetagegevens [zien?](view-documents-in-review-set.md#file-metadata)**

Nee, u kunt gedetecteerde talen niet zien in bestandsmetagegevens.

**Kan ik filteren op documenttalen in een revisieset?**

Nee, u kunt niet filteren, sorteren of zoeken op documenttalen in een revisieset.

**Is deze CJK-release voor revisiesetscenario's van invloed op een van mijn bestaande zoekopdrachten en revisiesets?**

Nee, geen van uw bestaande zoekopdrachten en revisiesets wordt gewijzigd. U hoeft bestaande gegevens niet opnieuw te indexeren en de zoekresultaten voor Engelse tekst zijn hetzelfde.

**Hoe wijzig ik mijn weergavetaal in Chinees, Japans of Koreaans?**

Zie Taal- en regio-instellingen instellen voor meer informatie over het wijzigen van weergavetaal en -tijdzone voor [Office 365.](/office365/troubleshoot/access-management/set-language-and-region)

## <a name="known-issues"></a>Bekende problemen

- OCR biedt geen ondersteuning voor CJK-tekens uit afbeeldingsbestanden

- E-mailbestanden (zoals *.eml en *.msg) [in](view-documents-in-review-set.md#annotate-view) de aantekeningenweergave worden niet ondersteund voor CJK-talen.

- Zoeken in de [tekstweergave wordt](view-documents-in-review-set.md#text-view) niet ondersteund voor CJK-talen.

- De [relevantiemodule die](using-relevance.md) wordt gebruikt om gegevens te analyseren, ondersteunt geen CJK-talen.

- [Query's worden](managing-holds.md#manage-non-custodial-holds) niet ondersteund voor CJK-talen.