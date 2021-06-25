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
ms.openlocfilehash: b852071c3fbfe12aac62e1d309fa130a4cd81e9c
ms.sourcegitcommit: b42dd3e706ebf9638cd893b35f75eaa56dd8fd7e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "53125396"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender preview-functies

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> De preview-versies worden geleverd zonder serviceovereenkomst en worden niet aanbevolen voor productiebelastingen. Bepaalde functies worden mogelijk niet ondersteund of hebben mogelijk beperkte mogelijkheden.

**Van toepassing op:**
- Microsoft 365 Defender

De Microsoft 365 Defender-service wordt voortdurend bijgewerkt met nieuwe functieverbeteringen en -mogelijkheden.

Lees meer over nieuwe functies in Microsoft 365 Defender preview-release en probeer als een van de eersten de komende functies door de preview-ervaring in te- of uitschakelen.

Zie Nieuwe functies in de Microsoft 365 Defender voor meer informatie over nieuwe mogelijkheden die algemeen [beschikbaar zijn.](whats-new.md)

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
