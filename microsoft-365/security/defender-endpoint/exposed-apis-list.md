---
title: Ondersteunde API's voor Microsoft Defender voor eindpunten
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
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198318"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Ondersteunde API's voor Microsoft Defender voor eindpunten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a>Endpoint URI en versieverken

### <a name="endpoint-uri"></a>Eindpunt-URI:

> De servicebasis URI is: https://api.securitycenter.microsoft.com
> 
> De query's op basis van OData hebben het voorvoegsel '/api'. Als u bijvoorbeeld waarschuwingen wilt ontvangen, kunt u GET-aanvraag verzenden naar https://api.securitycenter.microsoft.com/api/alerts

### <a name="versioning"></a>Versiering:

> De API ondersteunt versieversies.
> 
> De huidige versie is **V1.0**.
> 
> Als u een specifieke versie wilt gebruiken, gebruikt u deze indeling: `https://api.securitycenter.microsoft.com/api/{Version}` . Bijvoorbeeld: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
> 
> Als u geen versie opgeeft (bijvoorbeeld) gaat u https://api.securitycenter.microsoft.com/api/alerts naar de nieuwste versie.


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Meer informatie over de afzonderlijke ondersteunde entiteiten waar u API-oproepen naar kunt uitvoeren en details zoals HTTP-aanvraagwaarden, aanvraagkoppen en verwachte antwoorden.

## <a name="in-this-section"></a>In deze sectie

Onderwerp | Beschrijving
:---|:---
Geavanceerd jagen | Query's uitvoeren vanuit API.
Waarschuwingen | Voer API-oproepen uit, zoals waarschuwingen ontvangen, waarschuwing maken, waarschuwing bijwerken en meer.
Domeinen | Voer API-oproepen uit, zoals domeingerelateerde apparaten, domeinstatistieken en meer.
Bestanden | Voer API-oproepen uit, zoals bestandsgegevens, bestandsgerelateerde waarschuwingen, bestandsgerelateerde apparaten en bestandsstatistieken.
IPs | Voer API-oproepen uit, zoals IP-gerelateerde waarschuwingen ontvangen en IP-statistieken krijgen.
Machines | Voer API-oproepen uit, zoals apparaten op te halen, apparaten op te vragen via id, informatie over aangemelde gebruikers, tags bewerken en meer.
Machineacties | Voer API-oproep uit, zoals Isolatie, Anti-virusscan uitvoeren en meer.
Indicatoren | Voer API-oproep uit, zoals Indicator maken, Indicatoren op te halen en indicatoren te verwijderen.
Gebruikers | Voer API-oproepen uit, zoals waarschuwingen voor gebruikers en apparaten die aan de gebruiker zijn gerelateerd.
Score | Voer API-oproepen uit, zoals blootstellingsscore krijgen of apparaatveilige score krijgen.
Software | Voer API-oproepen uit, zoals lijstproblemen met software.
Kwetsbaarheid | Voer API-oproepen uit, zoals lijstapparaten op kwetsbaarheid.
Aanbeveling | Voer API-oproepen uit, zoals Aanbeveling per id ontvangen.

## <a name="see-also"></a>Zie ook
- [Microsoft Defender voor eindpunt-API's](apis-intro.md)
