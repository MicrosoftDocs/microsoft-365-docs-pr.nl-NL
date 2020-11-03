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
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846006"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Veelgebruikte foutcodes voor Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

De foutcodes in de volgende tabel kunnen als resultaat worden gegeven door een bewerking voor een van de Microsoft 365-Api's.

Elk foutbericht bevat een foutbericht dat kan worden opgelost om het probleem te verhelpen.

Het bericht is een vrije tekst die kan worden gewijzigd.

Onder aan de pagina vindt u antwoord voorbeelden.

Foutcode |HTTP-statuscode |Bericht 
:---|:---|:---
BadRequest | BadRequest (400) | Foutbericht over algemene onjuiste aanvraag.
ODataError | BadRequest (400) | Ongeldige OData URI-query (de specifieke fout is opgegeven).
InvalidInput | BadRequest (400) | Ongeldige invoer {de ongeldige invoer}.
InvalidRequestBody | BadRequest (400) | Ongeldige hoofdtekst van aanvraag.
InvalidHashValue | BadRequest (400) | Hashwaarde {de ongeldige hash} is ongeldig.
InvalidDomainName | BadRequest (400) | Domeinnaam {ongeldig domein} is ongeldig.
InvalidIpAddress | BadRequest (400) | IP-adres {ongeldig IP-adres}.
InvalidUrl | BadRequest (400) | URL {de ongeldige URL} is ongeldig.
MaximumBatchSizeExceeded | BadRequest (400) | Maximale grootte van de batch overschreden. Ontvangen: {batchgrootte ontvangen}, toegestaan: {batchgrootte toegestaan}.
MissingRequiredParameter | BadRequest (400) | Parameter {de ontbrekende parameter} ontbreekt.
OsPlatformNotSupported | BadRequest (400) | OS platform {het clientbesturingssysteem platform} wordt niet ondersteund voor deze actie.
ClientVersionNotSupported | BadRequest (400) | {De gevraagde actie} wordt ondersteund op de clientversie {ondersteunde clientversie} en hoger.
Onbevoegde | Onbevoegd (401) | Niet toegestaan (meestal ongeldig of vervallen autorisatie-header).
Slag | Niet toegestaan (403) | Niet toegestaan (geldig token maar onvoldoende machtigingen voor de actie).
DisabledFeature | Niet toegestaan (403) | De Tenant functie is niet ingeschakeld.
DisallowedOperation | Niet toegestaan (403) | {de niet-toegestane bewerking en de reden}.
NotFound | Niet gevonden (404) | Foutbericht algemeen niet gevonden.
ResourceNotFound | Niet gevonden (404) | Resource {de gevraagde resource} is niet gevonden.
InternalServerError | Interne server fout (500) | (Geen foutbericht, probeer het opnieuw of neem contact met ons op als dit niet wordt opgelost)

## <a name="body-parameters-are-case-sensitive"></a>Hoofd parameters zijn hoofdletters en kleine letters

De ingediende parameters voor de hoofdtekst zijn momenteel hoofdlettergevoelig.
<br>Als u een **InvalidRequestBody** -of **MissingRequiredParameter** -fout ondervindt, wordt dit mogelijk veroorzaakt door een onjuist parameter kapitaal of een kleine letter.
<br>We raden u aan de API-documentatie pagina te bekijken en te controleren of de verzonden parameters overeenkomen met het relevante voorbeeld.

## <a name="correlation-request-id"></a>ID van correlatie aanvraag

Elke foutmelding bevat een unieke ID-parameter voor bijhouden.
<br>De naam van de eigenschap van deze parameter is ' doel '.
<br>Als u over een fout contact met ons opneemt, kunt u met deze ID de hoofdoorzaak van het probleem achterhalen.

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

