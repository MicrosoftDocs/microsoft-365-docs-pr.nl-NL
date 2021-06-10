---
title: Beoordeling van de softwarevoorraad per apparaat exporteren
description: Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.
keywords: api's, api's, exportbeoordeling, per apparaat, rapport over kwetsbaarheidsbeoordeling, beoordeling van kwetsbaarheid van apparaten, rapport over apparaatproblemen, beveiligingsprobleemrapport, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 3a65fb6d5d3e5c6e68e100aa3ea2b4cf896dc281
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789346"
---
# <a name="export-software-inventory-assessment-per-device"></a>Beoordeling van de softwarevoorraad per apparaat exporteren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen. Omdat de hoeveelheid gegevens groot kan zijn, kunnen deze op twee manieren worden opgehaald:

- [OData-evaluatie van **softwarevoorraad exporteren**](#1-export-software-inventory-assessment-odata)  De API haalt alle gegevens in uw organisatie op als Json-antwoorden, volgens het OData-protocol. Deze methode is het beste _voor kleine organisaties met minder dan 100 K-apparaten._ Het antwoord is paginated, zodat u het veld odata.nextLink uit het antwoord kunt gebruiken \@ om de volgende resultaten op te halen.

- [Beoordeling van softwarevoorraad **exporteren via bestanden**](#2-export-software-inventory-assessment-via-files)  Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100 K-apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden:

  - Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens.

  - Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

Gegevens die worden verzameld (met _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens. Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.

> [!Note]
>
> Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**

## <a name="1-export-software-inventory-assessment-odata"></a>1. Evaluatie van de softwarevoorraad exporteren (OData)

### <a name="11-api-method-description"></a>Beschrijving van API-methode 1.1

Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat. Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="limitations"></a>Beperkingen

- De maximale paginagrootte is 200.000.

- Tariefbeperkingen voor deze API zijn 30 oproepen per minuut en 1000 oproepen per uur.

### <a name="12-permissions"></a>1.2 Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype | Machtiging | Weergavenaam machtiging
---|---|---
Toepassing | Software.Read.All | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'
Gedelegeerd (werk- of schoolaccount) | Software.Lezen | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'

### <a name="13-url"></a>1,3 URL

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>1,4 Parameters

- pageSize (standaard = 50.000) – aantal resultaten in antwoord.

- $top – aantal resultaten dat moet worden retourneren (wordt niet als resultaat @odata.nextLink en dus niet alle gegevens)

### <a name="15-properties"></a>1,5 eigenschappen

>[!NOTE]
>
>-Elke record is ongeveer 0,5 KB aan gegevens. U moet hiermee rekening houden bij het kiezen van de juiste paginaSize-parameter voor u.

>-De eigenschappen die in de volgende tabel zijn gedefinieerd, worden alfabetisch weergegeven op eigenschap-id. Bij het uitvoeren van deze API wordt de resulterende uitvoer niet noodzakelijkerwijs geretourneerd in dezelfde volgorde als in deze tabel.
>
>-Sommige extra kolommen kunnen worden geretourneerd in het antwoord. Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.

Eigenschap (id) | Gegevenstype | Beschrijving | Voorbeeld van een geretourneerde waarde
:---|:---|:---|:---
DeviceId | tekenreeks | Unieke id voor het apparaat in de service. | 9eaf3a8b5962e0e6b1af9ec75664a9b823df2d1
Apparaatnaam | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat. | johnlaptop.europe.contoso.com
DiskPaths | Matrix[tekenreeks]  | Schijf bewijs dat het product is geïnstalleerd op het apparaat. | [ "C: \\ Program Files (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]
EndOfSupportDate | tekenreeks | De datum waarop de ondersteuning voor deze software is of eindigt. | 2020-12-30
EndOfSupportStatus | tekenreeks | Einde van de ondersteuningsstatus. Kan deze mogelijke waarden bevatten: Geen, EOS-versie, aankomende EOS-versie, EOS-software, aankomende EOS-software. | Aankomende EOS
Id | tekenreeks | Unieke id voor de record. | 123ABG55_573AG&mnp!
NumberOfWeaknesses | int | Aantal zwakke punten in deze software op dit apparaat | 3
OSPlatform | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie. | Windows10
RbacGroupName | tekenreeks | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'. | Servers
RegistryPaths | Matrix[tekenreeks] | Registergegevens dat het product op het apparaat is geïnstalleerd. | [ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Uninstall Microsoft \\ Silverlight" ]
SoftwareFirstSeenTimestamp | tekenreeks | De eerste keer dat deze software op het apparaat werd gezien. | 2019-04-07 02:06:47
SoftwareName | tekenreeks | Naam van het softwareproduct. | Silverlight
SoftwareVendor | tekenreeks | Naam van de softwareleverancier. | microsoft
SoftwareVersion | tekenreeks | Versienummer van het softwareproduct. | 81.0.4044.138

### <a name="16-examples"></a>1.6 Voorbeelden

#### <a name="161-request-example"></a>1.6.1 Voorbeeld van aanvraag

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a>1.6.2 Voorbeeld van antwoord

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a>2. Evaluatie van de softwarevoorraad exporteren (via bestanden)

### <a name="21-api-method-description"></a>Beschrijving van API-methode 2.1

Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat. Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="211-limitations"></a>2.1.1 Beperkingen

Tariefbeperkingen voor deze API zijn 5 oproepen per minuut en 20 oproepen per uur.

### <a name="22-permissions"></a>2.2 Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype | Machtiging | Weergavenaam machtiging
---|---|---
Toepassing | Software.Read.All | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'
Gedelegeerd (werk- of schoolaccount) | Software.Lezen | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>Parameters

- sasValidHours: het aantal uren dat de download-URL's geldig zijn (maximaal 24 uur)

### <a name="25-properties"></a>2,5 eigenschappen

>[!Note]
>
>- De bestanden zijn gzip gecomprimeerde & in de Json-indeling met meerdere lijnen.
>
>- De DOWNLOAD-URL's zijn slechts 3 uur geldig. Anders kunt u de parameter gebruiken.
>
>_ Voor een maximale downloadsnelheid van uw gegevens kunt u ervoor zorgen dat u downloadt vanuit dezelfde Azure-regio als uw gegevens.
>
Eigenschap (id) | Gegevenstype | Beschrijving | Voorbeeld van een geretourneerde waarde
:---|:---|:---|:---
Bestanden exporteren | \[matrixreeks\] | Een lijst met DOWNLOAD-URL's voor bestanden met de huidige momentopname van de organisatie | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | tekenreeks | De tijd dat de export is gegenereerd. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Voorbeelden

#### <a name="261-request-example"></a>2.6.1 Voorbeeld van aanvraag

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>2.6.2 Voorbeeld van antwoord

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Zie ook

- [Beoordelingsmethoden en -eigenschappen per apparaat exporteren](get-assessment-methods-properties.md)

- [Veilige configuratiebeoordeling per apparaat exporteren](get-assessment-secure-config.md)

- [Beoordeling van beveiligingsproblemen met software per apparaat exporteren](get-assessment-software-vulnerabilities.md)

Andere gerelateerde

- [Risicogebaseerd & vulnerability management](next-gen-threat-and-vuln-mgt.md)

- [Beveiligingslekken in uw organisatie](tvm-weaknesses.md)
