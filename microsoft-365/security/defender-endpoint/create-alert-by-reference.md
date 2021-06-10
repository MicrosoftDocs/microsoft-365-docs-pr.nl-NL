---
title: Waarschuwing maken via gebeurtenis-API
description: Meer informatie over het gebruik van de WAARSCHUWINGS-API maken om een nieuwe waarschuwing te maken boven aan Gebeurtenis in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, alert, information, id
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
ms.openlocfilehash: 8b05dde015bc96e1ccd3f80e25c416a371e03199
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772387"
---
# <a name="create-alert-api"></a>Waarschuwings-API maken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Hiermee maakt [u een nieuwe](alerts.md) waarschuwing boven op **Gebeurtenis.**
<br>**Microsoft Defender voor eindpuntgebeurtenis** is vereist voor het maken van waarschuwingen.
<br>U moet 3 parameters uit de gebeurtenis opgeven in de aanvraag: **Gebeurtenistijd,** **Machine-id** en **Rapport-id.** Zie het onderstaande voorbeeld.
<br>U kunt een gebeurtenis gebruiken die is gevonden in Advanced Hunting API of Portal.
<br>Als er een geopende waarschuwing bestaat op hetzelfde apparaat met dezelfde titel, wordt de nieuwe gemaakte waarschuwing samengevoegd.
<br>Er wordt automatisch een onderzoek gestart naar waarschuwingen die zijn gemaakt via de API.


## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 15 oproepen per minuut.


## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Alerts.ReadWrite.All |  'Alle waarschuwingen lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) | Alert.ReadWrite | 'Waarschuwingen lezen en schrijven'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Alerts investigation' (Zie Rollen maken [en](user-roles.md) beheren voor meer informatie)
>- De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.
Inhoudstype | Tekenreeks | toepassing/json. **Vereist**.

## <a name="request-body"></a>Body aanvragen

In de aanvraag-body moet u de volgende waarden leveren (alle waarden zijn vereist):

Eigenschap | Type | Beschrijving
:---|:---|:---
eventTime | DateTime(UTC) | De exacte tijd van de gebeurtenis als tekenreeks, zoals verkregen uit geavanceerde jacht. bijvoorbeeld Vereist ```2018-08-03T16:45:21.7115183Z``` .
reportId | Tekenreeks | Het rapportId of the event, as obtained from advanced hunting. **Vereist**.
machineId | Tekenreeks | Id van het apparaat waarop de gebeurtenis is geïdentificeerd. **Vereist**.
ernst | Tekenreeks | Ernst van de waarschuwing. De eigenschapswaarden zijn: 'Laag', 'Gemiddeld' en 'Hoog'. **Vereist**.
titel | Tekenreeks | Titel voor de waarschuwing. **Vereist**.
beschrijving | Tekenreeks | Beschrijving van de waarschuwing. **Vereist**.
aanbevolenActie| Tekenreeks | Actie die wordt aanbevolen door de beveiligingsmedewerker bij het analyseren van de waarschuwing. **Vereist**.
categorie| Tekenreeks | Categorie van de waarschuwing. De eigenschapswaarden zijn: "Algemeen", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistent", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.

## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode 200 OK en een nieuw [waarschuwingsobject](alerts.md) in de antwoord body. Als gebeurtenis met de opgegeven eigenschappen _(reportId_, _eventTime_ en _machineId)_ niet is gevonden - 404 Niet gevonden.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
