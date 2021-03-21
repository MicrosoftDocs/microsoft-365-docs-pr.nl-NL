---
title: Microsoft 365 Defender API's licentie en gebruiksvoorwaarden
description: Beschrijving van de licentie en gebruiksvoorwaarden voor API's in Microsoft 365 Defender
keywords: api's, licentie, voorwaarden, api's, juridisch, kennisgevingen, gedragscode
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
ms.openlocfilehash: 06926bc58f29fcf80d09819545e2455813f27a5f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922160"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender API's licentie en gebruiksvoorwaarden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat mogelijk aanzienlijk wordt gewijzigd voordat het commercieel wordt uitgebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt verstrekt.

## <a name="official-terms"></a>Officiële voorwaarden

Microsoft 365 Defender API's zijn onderworpen aan de [Microsoft API's-licentie en gebruiksvoorwaarden.](/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Juridische kennisgevingen

Microsoft en eventuele inzenders verlenen u een licentie voor de Microsoft-documentatie en andere inhoud in deze [opslagplaats,](https://github.com/MicrosoftDocs/microsoft-365-docs)onder de Creative Commons Attribution 4.0 International Public License. Zie het LICENTIEbestand voor [meer](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) informatie.

Microsoft, Windows, Microsoft Azure en/of andere Microsoft-producten en -services waarnaar in de documentatie wordt verwezen, kunnen handelsmerken of geregistreerde handelsmerken van Microsoft zijn in de Verenigde Staten en/of andere landen.

De licenties voor dit project verlenen u geen rechten om microsoft-namen, logo's of handelsmerken te gebruiken. De algemene richtlijnen voor handelsmerken van Microsoft vindt u bij [Microsoft Trademarks.](https://go.microsoft.com/fwlink/?LinkID=254653)

Privacygegevens vindt u op [Privacy bij Microsoft](https://privacy.microsoft.com).

Microsoft en eventuele inzenders behouden alle andere rechten, hetzij onder hun respectieve auteursrechten, octrooien of handelsmerken, hetzij door implicaties, estoppels of anderszins.

## <a name="other-restrictions"></a>Andere beperkingen

De geavanceerde api voor jagen heeft [enkele beperkingen](/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) voor het aantal geretourneerde resultaten en de gegevens die kunnen worden opgevraagd.

1. U kunt alleen gegevens uit de afgelopen 30 dagen query's uitvoeren.
1. De resultaten bevatten maximaal 100.000 rijen.

### <a name="quotas-and-resource-allocation"></a>Quota en resourcetoewijzing

De Microsoft 365 Defender-API's hebben beperkingsdrempels.

- **Api incidenten:** maximaal 50 oproepen per minuut of 1500 oproepen per uur.
- **Advanced Hunting API:** maximaal 15 oproepen per minuut, 10 minuten aan gebruikstijden per uur en 4 uur aan gebruikstijden per dag.

De HTTP-antwoordstatuscode die aangeeft dat beperking is `429` .

Als uw aanvraag is beperkt, geeft de hoofdreactie het tijdstip aan waarop u opnieuw kunt beginnen met het indienen van aanvragen.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-API's](api-overview.md)
- [Ondersteunde Microsoft 365 Defender-API's](api-supported.md)
- [De Microsoft 365 Defender-API's openen](api-access.md)