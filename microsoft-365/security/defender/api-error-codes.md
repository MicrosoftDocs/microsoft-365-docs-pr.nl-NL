---
title: Veelgebruikte Microsoft 365 Defender REST API-foutcodes
description: Meer informatie over de algemene Microsoft 365 Defender REST API-foutcodes
keywords: api, fout, codes, veelvoorkomende fouten, Microsoft 365 Defender, api-foutcodes
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
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932879"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Veelgebruikte Microsoft 365 Defender REST API-foutcodes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

Foutcodes kunnen worden geretourneerd door een bewerking op een van de Microsoft 365 Defender-API's. Elke foutreactie bevat een foutbericht, waarmee het probleem kan worden opgelost. De kolom met foutberichten in de tabelsectie bevat enkele voorbeeldberichten. De inhoud van de werkelijke berichten verschilt op basis van de factoren die de reactie hebben veroorzaakt. Variabele inhoud wordt in de tabel aangegeven met hoekhaken.

## <a name="error-codes"></a>Foutcodes

Foutcode | HTTP-statuscode | Bericht
-|-|-
BadRequest | BadRequest (400) | Foutbericht algemeen slecht verzoek.
ODataError | BadRequest (400) | Ongeldige OData URI-query \<the specific error is specified\> .
InvalidInput | BadRequest (400) | Ongeldige invoer \<the invalid input\> .
InvalidRequestBody | BadRequest (400) | Ongeldige aanvraag body.
OngeldigeHashValue | BadRequest (400) | De \<the invalid hash\> hashwaarde is ongeldig.
InvalidDomainName | BadRequest (400) | Domeinnaam \<the invalid domain\> is ongeldig.
InvalidIpAddress | BadRequest (400) | IP-adres \<the invalid IP\> is ongeldig.
InvalidUrl | BadRequest (400) | URL \<the invalid URL\> is ongeldig.
MaximumBatchSizeExceeded | BadRequest (400) | De maximale batchgrootte is overschreden. Ontvangen: \<batch size received\> , toegestaan: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | Parameter \<the missing parameter\> ontbreekt.
OsPlatformNotSupported | BadRequest (400) | Os Platform \<the client OS Platform\> wordt niet ondersteund voor deze actie.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> wordt ondersteund in clientversie \<supported client version\> en hoger.
Onbevoegden | Onbevoegden (401) | Onbevoegden <br /><br />*Opmerking: Meestal veroorzaakt door een ongeldige of verlopen autorisatiekoptekst.*
Verboden | Verboden (403) | Verboden <br /><br />*Opmerking: Geldig token, maar onvoldoende machtiging voor de actie.*
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

## <a name="body-parameters"></a>Parameters van de body

> [!IMPORTANT]
> Bodyparameters zijn case-sensitive.

Als er een fout is opgetreden bij *InvalidRequestBody* of *MissingRequiredParameter,* kan dit worden veroorzaakt door een typefout. Controleer de API-documentatie en controleer of de ingediende parameters overeenkomen met het relevante voorbeeld.

## <a name="tracking-id"></a>Tracking-id

Elke foutreactie bevat een unieke id-parameter voor het bijhouden. De eigenschapsnaam van deze parameter is *doel*. Wanneer u contact met ons op neemt over een fout, kunnen we met deze id de hoofdoorzaak van het probleem vinden.

## <a name="related-articles"></a>Aanverwante artikelen

- [Microsoft 365 Overzicht van DEFENDER-API's](api-overview.md)
- [Ondersteunde Microsoft 365 Defender-API's](api-supported.md)
- [Toegang tot Microsoft 365 Defender-API's](api-access.md)
- [Meer informatie over API-limieten en -licenties](api-terms.md)
