---
title: Licentie en Gebruiksvoorwaarden Microsoft 365 Defender API
description: Beschrijving van de licentie en gebruiksvoorwaarden voor Api's in Microsoft 365 Defender
keywords: API, api's, licentie, termen, API, juridisch, kennisgevingen, gedragscode
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: d9b3c48e4b9e89ef7648086b05c9fdd9f078f51e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719296"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Licentie en Gebruiksvoorwaarden Microsoft 365 Defender API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

## <a name="official-terms"></a>Officiële voorwaarden

Microsoft 365 Defender-Api's zijn onderworpen aan de [Microsoft api's-licentie en de gebruiksvoorwaarden](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use).

## <a name="legal-notices"></a>Juridische kennisgevingen

Microsoft en elke medewerker verlenen u een licentie aan de Microsoft-documentatie en andere inhoud in [deze bibliotheek](https://github.com/MicrosoftDocs/microsoft-365-docs), onder de openbare licentie van 4,0 internationale internationale licentie. Voor meer informatie raadpleegt u het [licentie](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) bestand.

Microsoft, Windows, Microsoft Azure en/of andere Microsoft-producten en-services waarnaar wordt verwezen in de documentatie, kunnen handelsmerken of geregistreerde handelsmerken zijn van Microsoft in de Verenigde Staten en/of in andere landen.

De licenties voor dit project geven u geen rechten voor het gebruik van Microsoft-namen,-logo's of-handelsmerken. Microsofts richtlijnen voor algemeen handelsmerken vindt u op [Microsoft-handelsmerken](https://go.microsoft.com/fwlink/?LinkID=254653).

U vindt informatie over privacy [voor de privacyverklaring bij Microsoft](https://privacy.microsoft.com).

Microsoft en elke medewerker behoudt zich alle andere rechten voor, ongeacht of deze onder hun eigen auteursrecht, octrooien of handelsmerken onder hun eigen auteursrecht, estoppel of anderszins.

## <a name="other-restrictions"></a>Andere beperkingen

De Advanced jacht-API bevat enkele [beperkingen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) voor het aantal geretourneerde resultaten en de gegevens waarop u kunt worden opgezocht.

1. U kunt alleen de gegevens van de afgelopen 30 dagen opvragen.
1. De resultaten hebben een maximum van 100.000 rijen.

### <a name="quotas-and-resource-allocation"></a>Quota's en resources toewijzen

De Microsoft 365-Api's voor het beperken van drempelwaarden.

- **API voor incidenten**: tot 50-oproepen per minuut of 1500 bellen per uur.
- **Geavanceerde jacht-API**: tot 15 oproepen per minuut, 10 minuten van uitvoering per uur en 4 uur tijd per dag.

De statuscode van het HTTP-antwoord aangeeft vertraging is `429` .

Als uw aanvraag is vertraagd, zal de tekst van het antwoord de tijd aangeven waarop u kunt beginnen met het maken van aanvragen.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-Api's](api-overview.md)
- [Ondersteunde Microsoft 365 Defender-API's](api-supported.md)
- [Toegang tot de Microsoft 365 Defender-Api's](api-access.md)
