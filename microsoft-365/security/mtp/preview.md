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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1636b1deb5f35d8286b33238a8f4bbfff0b33521
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288123"
---
# <a name="microsoft-365-defender-preview-features"></a>Preview-functies van Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> De preview-versies worden geleverd zonder serviceovereenkomst en worden niet aanbevolen voor werkbelasting van de productie. Bepaalde functies worden mogelijk niet ondersteund of hebben beperkte mogelijkheden.

**Van toepassing op:**
- Microsoft 365 Defender

De Microsoft 365 Defender-service wordt voortdurend bijgewerkt met nieuwe functieverbeteringen en mogelijkheden.

Lees meer over nieuwe functies in de preview-versie van Microsoft 365 Defender en probeer als een van de eersten komende functies door de preview-versie in te spelen.

Zie Wat is er nieuw [in Microsoft 365 Defender](whats-new.md)voor meer informatie over nieuwe mogelijkheden die algemeen beschikbaar zijn.

## <a name="required-permissions"></a>Vereiste machtigingen

Accounts die zijn toegewezen aan de volgende Azure Active Directory-rollen (Azure AD), kunnen functies van Microsoft 365 Defender Preview in bedrijf nemen:

- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator

## <a name="turn-on-preview-features"></a>Preview-functies inschakelen

U hebt toegang tot toekomstige functies die u kunt voorzien van feedback om de algehele ervaring te verbeteren voordat functies algemeen beschikbaar zijn.

Schakel de preview-ervaringsinstelling in om een van de eersten te zijn om nieuwe functies uit te proberen.

1. Kies **Instellingen** in het navigatiedeelvenster.
2. Selecteer **Microsoft 365 Defender.**
3. Kies **Preview-functies** > **Preview-functies inschakelen**. 
4. Kies **Opslaan**.

U weet dat u preview-functies hebt ingeschakeld wanneer u ziet dat het selectievakje **Preview-functies inschakelen** is aangevinkt. 

## <a name="preview-features"></a>Preview-functies

De volgende functies en verbeteringen zijn momenteel beschikbaar in de preview-versie:

### <a name="improved-microsoft-365-security-center"></a>Verbeterd Microsoft 365-beveiligingscentrum
Het verbeterde [Microsoft 365-beveiligingscentrum](https://security.microsoft.com) is nu beschikbaar in de openbare preview. Deze nieuwe ervaring brengt Defender voor eindpunt, Defender voor Office 365, Microsoft 365 Defender en meer naar het Microsoft 365-beveiligingscentrum. Dit is de nieuwe thuisbasis voor het beheren van uw besturingselementen voor beveiliging. [Ontdek wat er nieuw is](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).

- **[Microsoft 365 Defender threat analytics report](threat-analytics.md)** - Bedreigingsanalyse helpt u om te reageren op en de impact van actieve aanvallen te minimaliseren. U kunt ook meer te weten komen over aanvallen die worden geblokkeerd door Microsoft 365 Defender-oplossingen en voor het nemen van voorzorgsacties die het risico op verdere blootstelling beperken en tolerantie verhogen. Als onderdeel van de geïntegreerde beveiligingservaring is bedreigingsanalyse nu beschikbaar voor licentiehouders van Microsoft Defender voor Eindpunt en Microsoft Defender voor Office E5.
- **[Microsoft 365 Defender API's](api-overview.md)** - de Microsoft 365 Defender API's op het hoogste niveau stelt u in staat werkstromen te automatiseren op basis van het gedeelde incident en geavanceerde zoektabellen. 
- **[Onderneemt actie bij geavanceerd zoeken:](advanced-hunting-take-action.md)** snel bedreigingen bevatten of gecompromitteerde assets vinden in [geavanceerd zoeken.](advanced-hunting-overview.md)
- **[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—Get information about advanced hunting schema tables directly in the security center. Naast tabel- en kolombeschrijvingen bevat deze verwijzing ondersteunde gebeurtenistypen `ActionType` (waarden) en voorbeeldquery's.
- **[DeviceFromIP(),](advanced-hunting-devicefromip-function.md)** functie — Informatie krijgen over welke apparaten in een bepaald tijdsbereik een specifiek IP-adres of specifieke adressen zijn toegewezen.
