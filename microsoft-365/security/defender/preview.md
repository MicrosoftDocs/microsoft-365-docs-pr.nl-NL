---
title: Voorbeeldfuncties in Microsoft 365 Defender
description: Meer informatie over nieuwe functies in Microsoft 365-beveiliging
keywords: voorbeeld, nieuw, m365-beveiliging, beveiliging, 365, mogelijkheden
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 088dbd16c3667331843ff934c80f85aa8d3a837f
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430814"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender preview-functies

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

De Microsoft 365 Defender-service wordt voortdurend bijgewerkt met nieuwe functieverbeteringen en -mogelijkheden.

Lees meer over nieuwe functies in Microsoft 365 Defender preview-release en probeer als een van de eersten de komende functies door de preview-ervaring in te- of uitschakelen.

Zie Nieuwe functies in de Microsoft 365 Defender voor meer informatie over nieuwe mogelijkheden die algemeen [beschikbaar zijn.](whats-new.md)

 ## <a name="what-you-need-to-know"></a>Wat u moet weten

Als u werkt met functies in een openbaar voorbeeld, zijn deze functies:

- Kan beperkte of beperkte functionaliteit hebben. De functie kan bijvoorbeeld slechts op één platform van toepassing zijn.
- Meestal worden functiewijzigingen doorgevoerd voordat ze algemeen beschikbaar zijn (GA).
- Worden volledig ondersteund door Microsoft.
- Is mogelijk alleen beschikbaar in geselecteerde geografische regio's of cloudomgevingen. De functie bestaat bijvoorbeeld mogelijk niet in de cloud van de overheid.
- Afzonderlijke functies in de preview-versie hebben mogelijk meer gebruiks- en ondersteuningsbeperkingen. Als dat zo is, wordt deze informatie meestal vermeld in de documentatie van de functie.
- De preview-versies worden geleverd met een standaardondersteuningsniveau en kunnen worden gebruikt voor productieomgevingen. 



## <a name="required-permissions"></a>Vereiste machtigingen

Accounts die aan de volgende Azure Active Directory (Azure AD) zijn toegewezen, kunnen de Microsoft 365 Defender Preview-functies in:

- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator

## <a name="turn-on-preview-features"></a>Preview-functies inschakelen

U hebt toegang tot toekomstige functies waar u feedback over kunt geven om de algehele ervaring te verbeteren voordat functies algemeen beschikbaar zijn.

Schakel de preview-ervaringsinstelling in om een van de eersten te zijn om nieuwe functies uit te proberen.

1. Kies **Instellingen** in het navigatiedeelvenster.
2. Selecteer **Microsoft 365 Defender**.
3. Kies **Preview-functies** > **Preview-functies inschakelen**. 
4. Kies **Opslaan**.

U weet dat u preview-functies hebt ingeschakeld wanneer u ziet dat het selectievakje **Preview-functies inschakelen** is aangevinkt. 

## <a name="preview-features"></a>Preview-functies

De volgende functies en verbeteringen zijn momenteel beschikbaar in de preview-versie:

- **[Rapporten per bedreigingslabels weergeven:](threat-analytics.md#view-reports-per-threat-tags)** met bedreigingslabels kunt u zich richten op specifieke bedreigingscategorieën en de meest relevante rapporten bekijken.
- **[Streaming API](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender ondersteunt het streamen van alle gebeurtenissen die beschikbaar zijn via Advanced Hunting naar een Event Hubs en/of Azure-opslagaccount.
- **[Microsoft 365 Defender API's:](api-overview.md)** met de api'Microsoft 365 Defender op het hoogste niveau kunt u werkstromen automatiseren op basis van het gedeelde incident en geavanceerde zoektabellen. 
- **[Actie ondernemen in geavanceerde jacht](advanced-hunting-take-action.md)** : snel bedreigingen bevatten of gecompromitteerde activa die u vindt in geavanceerde [jacht.](advanced-hunting-overview.md)
- **[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - Informatie over geavanceerde schematabellen voor het jagen rechtstreeks in het beveiligingscentrum. Naast tabel- en kolombeschrijvingen bevat deze verwijzing ondersteunde gebeurtenistypen `ActionType` (waarden) en voorbeeldquery's.
- **[DeviceFromIP() functie:](advanced-hunting-devicefromip-function.md)** informatie over welke apparaten een specifiek IP-adres of een specifiek IP-adres op een bepaald tijdstip hebben gekregen.
