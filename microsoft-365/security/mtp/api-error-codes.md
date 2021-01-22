---
title: Veelvoorkomende foutcodes voor Microsoft 365 Defender REST API
description: Meer informatie over de veelgebruikte foutcodes voor Microsoft 365 Defender REST API
keywords: api, fout, codes, veelvoorkomende fouten, mtp, api-foutcodes
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
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928388"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Veelvoorkomende foutcodes voor Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.

Foutcodes kunnen worden geretourneerd door een bewerking op een van de Microsoft 365 Defender-API's. Elk foutbericht bevat een foutbericht waarmee het probleem kan worden opgelost. De kolom foutbericht in de tabelsectie bevat enkele voorbeeldberichten. De inhoud van feitelijke berichten is afhankelijk van de factoren die de reactie hebben veroorzaakt. Variabele inhoud wordt in de tabel aangegeven met haakjes.

## <a name="error-codes"></a>Foutcodes

Foutcode | HTTP-statuscode | Bericht
-|-|-
BadRequest | BadRequest (400) | Foutbericht over algemene bad request.
ODataError | BadRequest (400) | Ongeldige OData \<the specific error is specified\> URI-query.
InvalidInput | BadRequest (400) | Ongeldige \<the invalid input\> invoer.
InvalidRequest Heely | BadRequest (400) | Ongeldige aanvraag body.
InvalidHashValue | BadRequest (400) | De hashwaarde \<the invalid hash\> is ongeldig.
InvalidDomainName | BadRequest (400) | Domeinnaam \<the invalid domain\> is ongeldig.
InvalidIpAddress | BadRequest (400) | HET \<the invalid IP\> IP-adres is ongeldig.
InvalidUrl | BadRequest (400) | URL \<the invalid URL\> is ongeldig.
MaximumBatchSizeExceeded | BadRequest (400) | De maximale batchgrootte is overschreden. Ontvangen: \<batch size received\> , toegestaan: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | De parameter \<the missing parameter\> ontbreekt.
OsPlatformNotSupported | BadRequest (400) | Het \<the client OS Platform\> besturingssysteemplatform wordt niet ondersteund voor deze actie.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> wordt ondersteund in de clientversie \<supported client version\> en hoger.
Niet geautoriseerd | Niet geautoriseerd (401) | Niet geautoriseerd <br /><br />*Opmerking: Meestal veroorzaakt door een ongeldige of verlopen autorisatiekop.*
Verboden | Verboden (403) | Verboden <br /><br />*Opmerking: Geldig token, maar onvoldoende machtigingen voor de actie.*
DisabledFeature | Verboden (403) | Tenantfunctie is niet ingeschakeld.
DisallowedOperation | Verboden (403) | \<the disallowed operation and the reason\>.
NotFound | Niet gevonden (404) | Foutbericht Algemeen niet gevonden.
ResourceNotFound | Niet gevonden (404) | Resource \<the requested resource\> is niet gevonden.
InternalServerError | Interne serverfout (500) | *Opmerking: Geen foutbericht, de bewerking opnieuw uitvoeren of contact opnemen met Microsoft als dit niet wordt opgelost*

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

## <a name="body-parameters"></a>Parameters voor de body

> [!IMPORTANT]
> Bodyparameters zijn case-sensitive.

Als er een invalidRequest Wordt weergegeven in de fout *InvalidRequestAntwoordy* of *MissingRequiredParameter,* wordt deze mogelijk veroorzaakt door een typfout. Raadpleeg de DOCUMENTATIE van de API en controleer of de ingediende parameters overeenkomen met het desbetreffende voorbeeld.

## <a name="tracking-id"></a>Tracerings-id

Elke foutreactie bevat een unieke id-parameter om bij te houden. De eigenschapsnaam van deze parameter is *doel.* Wanneer u contact met ons op neemt over een fout, helpt het koppelen van deze id ons om de oorzaak van het probleem te vinden.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender API's](api-overview.md)
- [Ondersteunde Microsoft 365 Defender-API's](api-supported.md)
- [Toegang tot de Microsoft 365 Defender-API's](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
