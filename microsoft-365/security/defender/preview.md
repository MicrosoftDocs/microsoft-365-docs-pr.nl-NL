---
title: Preview-functies in Microsoft 365 Defender
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
ms.openlocfilehash: 291ee6d2f72579a6daf731c121265164b2aaa547
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059633"
---
# <a name="microsoft-365-defender-preview-features"></a>Preview-functies van Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> De preview-versies worden geleverd zonder serviceovereenkomst en worden niet aanbevolen voor productiebelastingen. Bepaalde functies worden mogelijk niet ondersteund of hebben mogelijk beperkte mogelijkheden.

**Van toepassing op:**
- Microsoft 365 Defender

De Microsoft 365 Defender-service wordt voortdurend bijgewerkt met nieuwe functies en mogelijkheden.

Lees meer over nieuwe functies in de preview-release van Microsoft 365 Defender en probeer als een van de eersten toekomstige functies door de preview-ervaring in te dagen.

Zie Nieuw [in Microsoft 365 Defender](whats-new.md)voor meer informatie over nieuwe mogelijkheden die algemeen beschikbaar zijn.

## <a name="required-permissions"></a>Vereiste machtigingen

Accounts die de volgende Azure Active Directory-rollen (Azure AD) hebben toegewezen, kunnen Microsoft 365 Defender Preview-functies in- en uit- zetten:

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

### <a name="improved-microsoft-365-security-center"></a>Verbeterd Microsoft 365-beveiligingscentrum
Het verbeterde [Microsoft 365-beveiligingscentrum](https://security.microsoft.com) is nu beschikbaar in de openbare preview. Deze nieuwe ervaring brengt Defender voor Eindpunt, Defender voor Office 365, Microsoft 365 Defender en meer naar het Microsoft 365-beveiligingscentrum. Dit is de nieuwe thuisbasis voor het beheren van uw beveiligingsbesturingselementen. [Ontdek wat er nieuw is](./overview-security-center.md).

- **[Microsoft 365 Defender threat analytics report](threat-analytics.md)** - Threat Analytics helpt u bij het reageren op en minimaliseren van de impact van actieve aanvallen. U kunt ook meer informatie krijgen over aanvalspogingen die zijn geblokkeerd door Microsoft 365 Defender-oplossingen en preventief optreden om het risico op verdere blootstelling te beperken en de tolerantie te vergroten. Als onderdeel van de geïntegreerde beveiligingservaring is bedreigingsanalyse nu beschikbaar voor licentiehouders van Microsoft Defender voor Eindpunt en Microsoft Defender voor Office E5.
- **[Microsoft 365 Defender API's](api-overview.md)** : met de api's op het hoogste niveau van Microsoft 365 Defender kunt u werkstromen automatiseren op basis van het gedeelde incident en geavanceerde zoektabellen. 
- **[Actie ondernemen in geavanceerde jacht](advanced-hunting-take-action.md)**: snel bedreigingen bevatten of gecompromitteerde activa die u vindt in geavanceerde [jacht.](advanced-hunting-overview.md)
- **[In-portal schemaverwijzing:](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** informatie over geavanceerde schematabellen voor jagen rechtstreeks in het beveiligingscentrum. Naast tabel- en kolombeschrijvingen bevat deze verwijzing ondersteunde gebeurtenistypen `ActionType` (waarden) en voorbeeldquery's.
- **[DeviceFromIP(), functie:](advanced-hunting-devicefromip-function.md)** informatie over welke apparaten een specifiek IP-adres of een specifiek IP-adres op een bepaald tijdstip hebben gekregen.