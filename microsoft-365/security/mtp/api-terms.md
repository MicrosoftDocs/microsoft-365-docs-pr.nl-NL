---
title: Gebruiksvoorwaarden en gebruiksvoorwaarden van Microsoft 365 Defender API's
description: Beschrijving van de gebruiksvoorwaarden en gebruiksvoorwaarden voor API's in Microsoft 365 Defender
keywords: api, apis, license, terms, apis, legal, notices, code of conduct
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
ms.openlocfilehash: 82f31c449ae2e102ac7464e0fef75277660844d1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930952"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Gebruiksvoorwaarden en gebruiksvoorwaarden van Microsoft 365 Defender API's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.

## <a name="official-terms"></a>Officiële voorwaarden

Op Microsoft 365 Defender API's zijn de licentie en gebruiksvoorwaarden van [de Microsoft API's van toepassing.](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Juridische mededelingen

Microsoft en andere medewerkers verlenen u een licentie voor de Microsoft-documentatie en andere inhoud in deze [opslagplaats](https://github.com/MicrosoftDocs/microsoft-365-docs)onder de Creative Commons Naamsvermelding 4.0 International Public License. Zie het bestand [LICENSE](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) voor meer informatie.

Microsoft, Windows, Microsoft Azure en/of andere Microsoft-producten en -services waarnaar in de documentatie wordt verwezen, kunnen handelsmerken of gedeponeerde handelsmerken van Microsoft in de Verenigde Staten en/of andere landen zijn.

De licenties voor dit project verlenen u geen rechten om Microsoft-namen, logo's of handelsmerken te gebruiken. De algemene handelsmerkrichtlijnen van Microsoft zijn te vinden in [handelsmerken van Microsoft.](https://go.microsoft.com/fwlink/?LinkID=254653)

Privacyinformatie vindt u op [Privacy bij Microsoft.](https://privacy.microsoft.com)

Microsoft en eventuele medewerkers behouden zich alle andere rechten voor, hetzij onder hun respectieve auteursrechten, octrooien of handelsmerken, hetzij bij implicatie, door estoppel of anderszins.

## <a name="other-restrictions"></a>Andere beperkingen

De geavanceerde api voor zoeken heeft enkele [beperkingen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) voor het aantal geretourneerde resultaten en de gegevens die opgevraagd kunnen worden.

1. U kunt alleen query's uitvoeren op gegevens van de afgelopen 30 dagen.
1. De resultaten bevatten maximaal 100.000 rijen.

### <a name="quotas-and-resource-allocation"></a>Quota en resourcetoewijzing

De Microsoft 365 Defender API's hebben beperkings drempelwaarden.

- **Incidenten-API:** maximaal 50 oproepen per minuut of 1500 oproepen per uur.
- **Advanced Hunting API:** maximaal 15 oproepen per minuut, 10 minuten aan doorlooptijd per uur en 4 uur aan gebruikstijden per dag.

De HTTP-antwoordstatuscode die aangeeft dat beperking `429` is.

Als uw aanvraag is beperkt, wordt in de hoofdreactie het tijdstip aangegeven waarop u opnieuw aanvragen kunt indienen.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender API's](api-overview.md)
- [Ondersteunde Microsoft 365 Defender-API's](api-supported.md)
- [Toegang tot de Microsoft 365 Defender-API's](api-access.md)
