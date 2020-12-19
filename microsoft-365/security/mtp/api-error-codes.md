---
title: Veelgebruikte foutcodes voor Microsoft 365 Defender REST API
description: Meer informatie over de veelvoorkomende foutcodes voor Microsoft 365 Defender REST API
keywords: API, fout, code, veelvoorkomende fouten, MTP, API-foutcodes
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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719212"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Veelgebruikte foutcodes voor Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

Foutcodes kunnen als resultaat worden gegeven door een bewerking op een van de Microsoft 365 Defender-Api's. Telkens wanneer een foutbericht wordt weergegeven, wordt een foutbericht weergegeven dat u kunt helpen dit probleem op te lossen. De kolom foutbericht in de tabel sectie bevat enkele voorbeeldberichten. De inhoud van werkelijke berichten kan variëren, afhankelijk van de factoren die het antwoord hebben veroorzaakt. Variabele-inhoud wordt in de tabel aangegeven met punthaken.

## <a name="error-codes"></a>Foutcodes

Foutcode | HTTP-statuscode | Bericht
-|-|-
BadRequest | BadRequest (400) | Foutbericht over algemene onjuiste aanvraag.
ODataError | BadRequest (400) | Ongeldige OData URI-query \<the specific error is specified\> .
InvalidInput | BadRequest (400) | Ongeldige invoer \<the invalid input\> .
InvalidRequestBody | BadRequest (400) | Ongeldige hoofdtekst van aanvraag.
InvalidHashValue | BadRequest (400) | Ongeldige hash-waarde \<the invalid hash\> .
InvalidDomainName | BadRequest (400) | Domeinnaam \<the invalid domain\> is ongeldig.
InvalidIpAddress | BadRequest (400) | Het IP-adres \<the invalid IP\> is ongeldig.
InvalidUrl | BadRequest (400) | URL \<the invalid URL\> ongeldig is.
MaximumBatchSizeExceeded | BadRequest (400) | Maximale grootte van de batch overschreden. Ontvangen: \<batch size received\> , toegestaan: {batchgrootte toegestaan}.
MissingRequiredParameter | BadRequest (400) | Parameter \<the missing parameter\> ontbreekt.
OsPlatformNotSupported | BadRequest (400) | Het besturingssysteem platform \<the client OS Platform\> wordt niet ondersteund voor deze actie.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> wordt ondersteund op clientversie \<supported client version\> en hoger.
Onbevoegde | Onbevoegd (401) | Onbevoegde <br /><br />*Opmerking: doorgaans veroorzaakt een ongeldige of verlopen autorisatie header.*
Slag | Niet toegestaan (403) | Slag <br /><br />*Opmerking: geldig token maar onvoldoende machtigingen voor de actie*.
DisabledFeature | Niet toegestaan (403) | De Tenant functie is niet ingeschakeld.
DisallowedOperation | Niet toegestaan (403) | \<the disallowed operation and the reason\>.
NotFound | Niet gevonden (404) | Foutbericht algemeen niet gevonden.
ResourceNotFound | Niet gevonden (404) | De resource \<the requested resource\> is niet gevonden.
InternalServerError | Interne server fout (500) | *Opmerking: geen foutbericht, probeer de bewerking of neem contact op met Microsoft als deze niet wordt weergegeven.*

## <a name="examples"></a>Voorbeelden

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a>Hoofd parameters

> [!IMPORTANT]
> Hoofd parameters zijn hoofdlettergevoelig.

Als u een *InvalidRequestBody* -of *MissingRequiredParameter* -fout ondervindt, wordt dit mogelijk veroorzaakt door een type fout. Bekijk de API-documentatie en controleer of de verzonden parameters overeenkomen met het relevante voorbeeld.

## <a name="tracking-id"></a>Tracking-ID

Elke foutmelding bevat een unieke ID-parameter voor bijhouden. De naam van de eigenschap van deze parameter is *doel*. Als u bij ons contact met ons opneemt, kunt u met deze ID de hoofdoorzaak van het probleem achterhalen.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-Api's](api-overview.md)
- [Ondersteunde Microsoft 365 Defender-API's](api-supported.md)
- [Toegang tot de Microsoft 365 Defender-Api's](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
