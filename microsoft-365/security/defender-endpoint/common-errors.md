---
title: Veelvoorkomende fouten in microsoft Defender voor endpoint-API
description: Lijst met veelvoorkomende Microsoft Defender voor Endpoint API-fouten met beschrijvingen.
keywords: API's, Microsoft Defender voor Endpoint API, fouten, probleemoplossing
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2e52b7074dcd15e7f6852a11ccb7793572cd9b5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771007"
---
# <a name="common-rest-api-error-codes"></a>Algemene REST API-foutcodes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* De foutcodes die in de volgende tabel worden vermeld, kunnen worden geretourneerd door een bewerking op een van de API's van Microsoft Defender voor eindpunten.
* Naast de foutcode bevat elk foutbericht een foutbericht, waarmee het probleem kan worden opgelost.
* Het bericht is een gratis tekst die kan worden gewijzigd.
* Onder aan de pagina vindt u antwoordvoorbeelden.

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Foutcode |HTTP-statuscode |Bericht 
:---|:---|:---
BadRequest | BadRequest (400) | Foutbericht algemeen slecht verzoek.
ODataError | BadRequest (400) | Ongeldige OData URI-query (de specifieke fout is opgegeven).
InvalidInput | BadRequest (400) | Ongeldige invoer {de ongeldige invoer}.
InvalidRequestBody | BadRequest (400) | Ongeldige aanvraag body.
OngeldigeHashValue | BadRequest (400) | Hashwaarde {de ongeldige hash} is ongeldig.
InvalidDomainName | BadRequest (400) | Domeinnaam {het ongeldige domein} is ongeldig.
InvalidIpAddress | BadRequest (400) | IP-adres {het ongeldige IP} is ongeldig.
InvalidUrl | BadRequest (400) | URL {de ongeldige URL} is ongeldig.
MaximumBatchSizeExceeded | BadRequest (400) | De maximale batchgrootte is overschreden. Ontvangen: {batch size received}, allowed: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | Parameter {de ontbrekende parameter} ontbreekt.
OsPlatformNotSupported | BadRequest (400) | Os Platform {the client OS Platform} wordt niet ondersteund voor deze actie.
ClientVersionNotSupported | BadRequest (400) | {De aangevraagde actie} wordt ondersteund in clientversie {ondersteunde clientversie} en hoger.
Onbevoegden | Onbevoegden (401) | Onbevoegden (ongeldige of verlopen autorisatiekoptekst).
Verboden | Verboden (403) | Verboden (geldig token, maar onvoldoende toestemming voor de actie).
DisabledFeature | Verboden (403) | Tenantfunctie is niet ingeschakeld.
DisallowedOperation | Verboden (403) | {de niet-goedgekeurde bewerking en de reden}.
NotFound | Niet gevonden (404) | Foutbericht Algemeen niet gevonden.
ResourceNotFound | Niet gevonden (404) | Resource {de aangevraagde resource} is niet gevonden.
InternalServerError | Interne serverfout (500) | (Geen foutbericht, de bewerking opnieuw proberen)
TooManyRequests | Te veel aanvragen (429) | Antwoord vertegenwoordigt het bereiken van quotumlimiet per aantal aanvragen of per CPU.

## <a name="body-parameters-are-case-sensitive"></a>Bodyparameters zijn case-sensitive

De ingediende bodyparameters zijn momenteel case-sensitive.
<br>Als er fouten optreden bij **InvalidRequestBody** of **MissingRequiredParameter,** kan dit worden veroorzaakt door een verkeerde parameterhoofdletter of kleine letter.
<br>Controleer de api-documentatiepagina en controleer of de ingediende parameters overeenkomen met het relevante voorbeeld.

## <a name="correlation-request-id"></a>Correlatieaanvraag-id

Elke foutreactie bevat een unieke id-parameter voor het bijhouden.
<br>De eigenschapsnaam van deze parameter is 'doel'.
<br>Wanneer u contact met ons op neemt over een fout, helpt u bij het koppelen van deze id de oorzaak van het probleem te vinden.

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
