---
title: Voorbeeld van de resultaten van een eDiscovery-zoekopdracht bekijken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Bekijk een voorbeeld van de resultaten die worden geretourneerd door een inhoudszoekactie of een basiszoekactie in eDiscovery in het Microsoft 365-compliancecentrum.
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538584"
---
# <a name="preview-ediscovery-search-results"></a>Voorbeeld van eDiscovery-zoekresultaten bekijken

Nadat u een inhoudszoekactie of een zoekopdracht die is gekoppeld aan een kern-eDiscovery-zaak hebt uitgevoerd, kunt u een voorbeeld bekijken van de resultaten die door de zoekopdracht worden geretourneerd. Door voorbeelden te bekijken van items die door de zoekquery worden geretourneerd, kunt u bepalen of de zoekopdracht de resultaten retourneert waar u op hoopte, of dat u de zoekquery moet wijzigen en de zoekopdracht opnieuw moet uitvoeren.

Een voorbeeld bekijken van de resultaten die door een zoekopdracht worden geretourneerd:

1. Ga in het Microsoft 365-compliancecentrum naar de pagina Inhoud zoeken of een belangrijke eDiscovery-zaak.

2. Selecteer de zoekfunctie om de flyoutpagina weer te geven.

3. Klik onderaan de flyoutpagina op **Voorbeeld controleren**.

   ![Klik op Voorbeeld bekijken op de flyoutpagina om de resultaten te bekijken](../media/PreviewSearchResults1.png)

   Er wordt een pagina weergegeven met daarin een voorbeeld van de zoekresultaten.

4. Selecteer een item om de inhoud ervan weer te geven in het leesvenster.

   ![Voorbeelden van items weergeven in het leesvenster.](../media/PreviewSearchResults2.png)

   In de vorige schermopname ziet u dat trefwoorden uit de zoekquery zijn gemarkeerd wanneer u een voorbeeld van items bekijkt.

## <a name="how-the-search-result-samples-are-selected"></a>Hoe de voorbeelden van zoekresultaten worden geselecteerd

Er kunnen maximaal 1000 willekeurig geselecteerde items als voorbeeld worden weergegeven. Items die beschikbaar zijn om als voorbeeld te worden weergegeven, moeten niet alleen willekeurig worden geselecteerd, maar moeten ook voldoen aan de volgende criteria:

- Er kan maximaal 100 items uit één inhoudslocatie (een postvak of een site) als voorbeeld worden bekeken. Dit betekent dat er mogelijk minder dan 1000 items beschikbaar zijn om als voorbeeld te worden bekeken. Als u bijvoorbeeld in vier postvakken zoekt en u 1500 geschatte items als gevolg hebt, zijn er slechts 400 beschikbaar om als voorbeeld te worden bekeken, omdat er slechts 100 items uit elk postvak als voorbeeld kunnen worden bekeken.

- Voor postvakitems zijn alleen e-mailberichten beschikbaar om als voorbeeld te worden bekeken. Van items zoals taken, agenda-items en contactpersonen kan geen voorbeeld worden weergegeven.

- Voor site-items zijn alleen documenten beschikbaar om als voorbeeld worden bekeken. Er kan geen voorbeeld worden weergegeven van items zoals mappen, lijsten of lijstbijlagen.

## <a name="file-types-supported-when-previewing-search-results"></a>Ondersteunde bestandstypen bij het bekijken van zoekresultaten

U kunt ondersteunde bestandstypen vooraf bekijken in het voorbeeldvenster. Als een bestandstype niet wordt ondersteund, moet u een kopie van het bestand downloaden naar uw lokale computer (door te klikken op **Oorspronkelijk item downloaden**). Voor .aspx-webpagina's wordt de URL voor de pagina opgenomen, hoewel u mogelijk geen machtigingen hebt voor toegang tot de pagina. Houd er ook rekening mee dat niet-geïndexeerde items niet beschikbaar zijn om als voorbeeld te bekijken.

De volgende bestandstypen worden ondersteund en kunnen vooraf worden bekeken in het deelvenster met zoekresultaten.
  
- .txt, .html, .mhtml

- .eml

- .doc, .docx, .docm

- .pptm, .pptx

- .pdf

De volgende bestandscontainertypen worden ook ondersteund. U kunt de lijst met bestanden in de container bekijken in het voorbeeldvenster.
  
- .zip

- .gzip