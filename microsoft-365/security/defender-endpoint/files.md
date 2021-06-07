---
title: Bestandsresourcetype
description: Recente waarschuwingen van Microsoft Defender voor eindpunten voor bestanden ophalen.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
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
ms.openlocfilehash: c4d392c9c7777a5ab5435d70e36822e11aa39dae
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771187"
---
# <a name="file-resource-type"></a>Bestandsresourcetype

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Vertegenwoordig een bestandsentiteit in Defender voor Eindpunt.

## <a name="methods"></a>Methoden
Methode|Retourtype |Omschrijving
:---|:---|:---
[Bestand downloaden](get-file-information.md) | [bestand](files.md) | Eén bestand downloaden 
[Gerelateerde waarschuwingen voor lijstbestand](get-file-related-alerts.md) | [waarschuwingsverzameling](alerts.md) | Haal [](alerts.md) de waarschuwingsentiteiten op die aan het bestand zijn gekoppeld.
[Lijstbestandsgerelateerde machines](get-file-related-machines.md) | [machineverzameling](machine.md) | De [machine-entiteiten](machine.md) die aan de waarschuwing zijn gekoppeld, krijgen.
[bestandsstatistieken](get-file-statistics.md) | Overzicht van statistieken | Hiermee wordt de prevalentie voor het opgegeven bestand opgehaald.


## <a name="properties"></a>Eigenschappen
|Eigenschap | Type    |   Omschrijving |
|:---|:---|:---|
|sha1 | Tekenreeks | Sha1 hash van de bestandsinhoud |
|sha256 | Tekenreeks | Sha256-hash van de bestandsinhoud |
|globalPrevalence | Nullable long | Bestandspresentpresies in de hele organisatie |
|globalFirstObserved | DateTimeOffset | De eerste keer dat het bestand is waargenomen |
|globalLastObserved | DateTimeOffset | De laatste keer dat het bestand is waargenomen |
|grootte | Nullable long | Grootte van het bestand |
|fileType | Tekenreeks | Type van het bestand |
|isPeFile | Booleaanse waarde | waar als het bestand draagbaar is (bijvoorbeeld 'DLL', 'EXE', enz.) |
|filePublisher | Tekenreeks | Bestandsuitgever |
|fileProductName | Tekenreeks | Productnaam |
|ondertekenaar | Tekenreeks | Bestands ondertekenaar |
|uitgevende gever | Tekenreeks | Bestands issuer |
|signerHash | Tekenreeks | Hash van het handtekeningcertificaat |
|isValidCertificate | Booleaanse waarde | Is het ondertekenen van certificaat geverifieerd door Microsoft Defender voor Endpoint-agent |
|determinationType | Tekenreeks | Het bepalingstype van het bestand |
|bepalingWaarde | Tekenreeks | Bepalingswaarde |


## <a name="json-representation"></a>Json-representatie

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
