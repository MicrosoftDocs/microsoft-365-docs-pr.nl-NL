---
title: Eén herstelactiviteit per id
description: Retourneert gegevens voor de opgegeven herstelactiviteit.
keywords: api's, herstel, herstel-api, get, hersteltaken, herstel per id,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2b7afef2c090df709f9209f450d8d3aab0424bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772147"
---
# <a name="get-one-remediation-activity-by-id"></a>Eén herstelactiviteit per id

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving

Retourneert gegevens voor de opgegeven herstelactiviteit. Geeft dezelfde kolommen weer als [Alle herstelactiviteit](get-remediation-all-activities.md)', maar geeft alleen resultaten als resultaat voor de opgegeven _herstelactiviteit._

[Meer informatie over herstelactiviteiten.](tvm-remediation.md)

## <a name="list-a-specified-remediation-activity-for-id"></a>Een opgegeven herstelactiviteit voor (id)

**URL:** GET: /api/remediationTasks/ \{ id\}

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype | Machtiging | Weergavenaam machtiging
:---|:---|:---
Toepassing | RemediationTask.Read.All | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'
Gedelegeerd (werk- of schoolaccount) | RemediationTask.Read.Read | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'

## <a name="properties"></a>Eigenschappen

Eigenschap (id) | Gegevenstype | Beschrijving | Voorbeeld van een geretourneerde waarde
:---|:---|:---|:---
categorie | Tekenreeks | Categorie van de herstelactiviteit (software-/beveiligingsconfiguratie) | Software
completerEmail | Tekenreeks | Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom zijn of haar e-mail | null
completerId | Tekenreeks | Als de herstelactiviteit handmatig is voltooid door iemand, bevat deze kolom de object-id | null
completionMethod | Tekenreeks | Een herstelactiviteit kan 'automatisch' worden voltooid (als alle apparaten zijn gepatcht) of 'handmatig' door een persoon die 'markeren als voltooid' selecteert. | Automatisch
gemaaktOn | DateTime | Tijd dat deze herstelactiviteit is gemaakt | 2021-01-12T18:54:11.5499478Z
beschrijving | Tekenreeks | Beschrijving van deze herstelactiviteit | Werk Microsoft Silverlight bij naar een latere versie om bekende beveiligingsproblemen op uw apparaten te beperken.
dueOn | DateTime | Einddatum die de maker heeft ingesteld voor deze herstelactiviteit | 2021-01-13T00:00:00Z
fixedDevices |  | Het aantal apparaten dat is opgelost | 2
id | Tekenreeks | Id van deze herstelactiviteit | 097d9735-5479-4899-b1b7-77398899df92
nameId | Tekenreeks | Verwante productnaam | Microsoft Silverlight
prioriteit | Tekenreeks | Prioriteit die de maker heeft ingesteld voor deze herstelactiviteit (Hoog\Gemiddeld\Laag) | Hoog
productId | Tekenreeks | Gerelateerde product-id | microsoft-_-silverlight
productiviteitImpactRemediationType | Tekenreeks | Er kunnen alleen enkele configuratiewijzigingen worden aangevraagd voor apparaten zonder dat dit gevolgen heeft voor de gebruiker. Deze waarde geeft de selectie aan tussen 'alle blootgestelde apparaten' of 'alleen apparaten zonder invloed van de gebruiker'. | AllExposedAssets
rbacGroupNames | Tekenreeks | Namen van gerelateerde apparaatgroep | [ "Windows Servers", "Windows 10" ]
aanbevolenProgram | Tekenreeks | Aanbevolen programma om een upgrade uit te voeren naar | null
aanbevolenVendor | Tekenreeks | Aanbevolen leverancier om een upgrade uit te voeren naar | null
aanbevolenVersie | Tekenreeks | Aanbevolen versie om bij te werken/upgraden naar | null
relatedComponent | Tekenreeks | Gerelateerd onderdeel van deze herstelactiviteit (vergelijkbaar met het gerelateerde onderdeel voor een beveiligingsaanbeveling) | Microsoft Microsoft Silverlight
requesterEmail | Tekenreeks | E-mailadres maker | globaladmin@UserName.contoso.com
requesterId | Tekenreeks | Creator-object-id | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | Tekenreeks | De notities (vrije tekst) die de maker heeft toegevoegd voor deze herstelactiviteit | null
scid | Tekenreeks | SCID van de gerelateerde beveiligingsaanbeveling | null
status | Tekenreeks | Status van herstelactiviteit (actief/voltooid) | Actief
statusLastModifiedOn | DateTime | Datum waarop het statusveld is bijgewerkt | 2021-01-12T18:54:11.5499487Z
targetDevices | Lang | Het aantal blootgestelde apparaten dat door deze herstel wordt toegepast op | 43
titel | Tekenreeks | Titel van deze herstelactiviteit | Microsoft Silverlight
type | Tekenreeks | Hersteltype | Update
vendorId | Tekenreeks | Naam van gerelateerde leverancier | Microsoft

## <a name="example"></a>Voorbeeld

### <a name="request-example"></a>Voorbeeld aanvragen

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a>Voorbeeld van antwoord

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
    "relatedComponent": "Microsoft Silverlight", 
    "targetDevices": 18511, 
    "rbacGroupNames": [ 
        "UnassignedGroup", 
        "hhh" 
    ], 
    "fixedDevices": 2866, 
    "requesterNotes": "test", 
    "dueOn": "2021-02-11T00:00:00Z", 
    "category": "Software", 
    "productivityImpactRemediationType": null, 
    "priority": "Medium", 
    "completionMethod": null, 
    "completerId": null, 
    "completerEmail": null, 
    "scid": null, 
    "type": "Update", 
    "productId": "microsoft-_-silverlight", 
    "vendorId": "microsoft", 
    "nameId": "silverlight", 
    "recommendedVersion": null, 
    "recommendedVendor": null, 
    "recommendedProgram": null 
} 
```

## <a name="see-also"></a>Zie ook

- [Herstelmethoden en -eigenschappen](get-remediation-methods-properties.md)

- [Alle herstelactiviteiten weergeven](get-remediation-all-activities.md)

- [Weergegeven apparaten van één herstelactiviteit weergeven](get-remediation-exposed-devices-activities.md)

- [Risicogebaseerd & vulnerability management](next-gen-threat-and-vuln-mgt.md)

- [Beveiligingslekken in uw organisatie](tvm-weaknesses.md)
