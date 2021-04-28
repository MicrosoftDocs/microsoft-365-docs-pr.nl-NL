---
title: Ondersteunde API's voor Microsoft Defender voor Eindpunt
ms.reviewer: ''
description: Meer informatie over de specifieke ondersteunde Microsoft Defender voor eindpunten waar u API-oproepen naar kunt maken.
keywords: api's, ondersteunde api's, actor, waarschuwingen, apparaat, gebruiker, domein, ip, bestand, geavanceerde query's, geavanceerd zoeken
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
ms.technology: mde
ms.openlocfilehash: 656aa26d80db73bfc52511f9dd94e58e771f3ac6
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073827"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Ondersteunde API's voor Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>Endpoint URI en versieverken

### <a name="endpoint-uri"></a>Eindpunt-URI

> De servicebasis URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> De query's op basis van OData hebben het voorvoegsel '/api'. Als u bijvoorbeeld waarschuwingen wilt ontvangen, kunt u GET-aanvraag verzenden naar [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>Versiering

> De API ondersteunt versieversies.
>
> De huidige versie is **V1.0**.
>
> Als u een specifieke versie wilt gebruiken, gebruikt u deze indeling: `https://api.securitycenter.microsoft.com/api/{Version}` . Bijvoorbeeld: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> Als u geen versie opgeeft (bijvoorbeeld) gaat u `https://api.securitycenter.microsoft.com/api/alerts` naar de nieuwste versie.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Meer informatie over de afzonderlijke ondersteunde entiteiten waar u API-oproepen naar kunt uitvoeren en details zoals HTTP-aanvraagwaarden, aanvraagkoppen en verwachte antwoorden.

## <a name="in-this-section"></a>In deze sectie

Onderwerp | Beschrijving
:---|:---
[Geavanceerd opsporen](run-advanced-query-api.md) | Query's uitvoeren vanuit API.
[Waarschuwingsmethoden en -eigenschappen](alerts.md) | Voer API-oproepen uit, \- zoals waarschuwingen ontvangen, waarschuwing maken, waarschuwing bijwerken en meer.
[Methoden en eigenschappen voor geautomatiseerd onderzoek](investigation.md) | Voer API-oproepen uit, \- zoals ophalen van onderzoek.
[Waarschuwingen met betrekking tot domeinen ophalen](get-domain-related-alerts.md) | Voer API-oproepen uit, \- zoals domeingerelateerde apparaten, domeinstatistieken en meer.
[Bestandsmethoden en -eigenschappen](files.md) | Voer API-oproepen uit, \- zoals bestandsgegevens, bestandsgerelateerde waarschuwingen, bestandsgerelateerde apparaten en bestandsstatistieken.
[Methoden en eigenschappen van indicatoren](ti-indicator.md) | Voer API-oproep uit, \- zoals Indicatoren op halen, Indicator maken en indicatoren verwijderen.
[Waarschuwingen met betrekking tot IP ophalen](get-ip-related-alerts.md) | Voer API-oproepen uit, \- zoals IP-gerelateerde waarschuwingen ontvangen en IP-statistieken krijgen.
[Computermethoden en -eigenschappen](machine.md) | Voer API-oproepen uit, zoals apparaten op te halen, apparaten op te vragen via id, informatie over \- aangemelde gebruikers, tags bewerken en meer.
[Actiemethoden en -eigenschappen van computer](machineaction.md) | Voer API-oproep uit, \- zoals Isolatie, Anti-virusscan uitvoeren en meer.
[Aanbevelingsmethoden en -eigenschappen](recommendation.md) | Voer API-oproepen uit, \- zoals een aanbeveling per id.
[Scoringsmethoden en -eigenschappen](score.md) | Voer API-oproepen uit, \- zoals blootstellingsscore krijgen of apparaatveilige score krijgen.
[Softwaremethoden en -eigenschappen](software.md) | Voer API-oproepen uit, \- zoals lijstproblemen met software.
[Gebruikersmethoden](user.md) | Voer API-oproepen uit, \- zoals waarschuwingen voor gebruikers en apparaten die aan de gebruiker zijn gerelateerd.
[Methoden en eigenschappen van beveiligingsproblemen](vulnerability.md) | Voer API-oproepen uit, zoals \- lijstapparaten op kwetsbaarheid.

## <a name="see-also"></a>Zie ook

- [Microsoft Defender voor eindpunt-API's](apis-intro.md)

- [Releasenotities van Microsoft Defender for Endpoint API](api-release-notes.md)
