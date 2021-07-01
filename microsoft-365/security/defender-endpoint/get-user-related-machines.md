---
title: API voor gebruikersgerelateerde machines krijgen
description: Lees hoe u de API Voor gebruikersgerelateerde machines ophalen kunt gebruiken om een verzameling apparaten op te halen die betrekking hebben op een gebruikers-id in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, gebruiker, gebruikersgerelateerde waarschuwingen
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
ms.openlocfilehash: ead0558bfff90c29ec8717fbb39876afda5c42af
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229453"
---
# <a name="get-user-related-machines-api"></a>API voor gebruikersgerelateerde machines krijgen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving
Hiermee wordt een verzameling apparaten opgehaald die betrekking hebben op een bepaalde gebruikers-id.

## <a name="limitations"></a>Beperkingen

Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |Machtiging|Weergavenaam machtiging
:---|:---|:---
Toepassing |Machine.Read.All|'Alle machineprofielen lezen'
Toepassing |Machine.ReadWrite.All |'Alle computergegevens lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) | Machine.Lezen | 'Machinegegevens lezen'
Gedelegeerd (werk- of schoolaccount) | Machine.ReadWrite | 'Machinegegevens lezen en schrijven'

> [!NOTE]
> Bij het verkrijgen van een token met gebruikersreferenties:
>
> - De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven'. Zie Rollen maken [en beheren voor meer informatie](user-roles.md).
> - Antwoord bevat alleen apparaten die de gebruiker kan openen, op basis van de instellingen van de apparaatgroep. Zie Apparaatgroepen maken en beheren voor meer [informatie.](machine-groups.md)

## <a name="http-request"></a>HTTP-aanvraag

```http
GET /api/users/{id}/machines
```

**De id is niet de volledige UPN, maar alleen de gebruikersnaam. (bijvoorbeeld om machines op te halen voor user1@contoso.com /api/users/user1/machines)**

## <a name="request-headers"></a>Aanvraagheaders

Naam | Type | Omschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-body"></a>Aanvraagtekst

Leeg

## <a name="response"></a>Antwoord

Als dit is gelukt en de gebruiker bestaat- 200 OK met een lijst met [machine-entiteiten](machine.md) in de body. Als gebruiker niet bestaat- 404 Niet gevonden.

## <a name="example"></a>Voorbeeld

### <a name="request"></a>Aanvraag

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
