---
title: Beoordeling van beveiligingsproblemen met software per apparaat exporteren
description: De API-reactie is per apparaat en bevat kwetsbare software die is geïnstalleerd op uw blootgestelde apparaten en eventuele bekende beveiligingslekken in deze softwareproducten. Deze tabel bevat ook informatie over het besturingssysteem, CVE-ID's en ernst van de kwetsbaarheid.
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
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689211"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>Beoordeling van beveiligingsproblemen met software per apparaat exporteren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Retourneert alle bekende softwareproblemen en hun gegevens voor alle apparaten, per apparaat.

Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen. Omdat de hoeveelheid gegevens erg groot kan zijn, kunnen deze op twee manieren worden opgehaald:

- [Beoordeling van beveiligingsproblemen met software exporteren OData](#1-export-software-vulnerabilities-assessment-odata)  De API haalt alle gegevens in uw organisatie op als Json-antwoorden, volgens het OData-protocol. Deze methode is het beste _voor kleine organisaties met minder dan 100 K-apparaten._ Het antwoord is paginated, zodat u het veld odata.nextLink uit het antwoord kunt gebruiken \@ om de volgende resultaten op te halen.

- [Beoordeling van beveiligingsproblemen met software via bestanden exporteren](#2-export-software-vulnerabilities-assessment-via-files) Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100 K-apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden:

  - Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens.

  - Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

Gegevens die worden verzameld (met _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens. Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.

> [!Note]
>
> Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**

## <a name="1-export-software-vulnerabilities-assessment-odata"></a>1. Evaluatie van softwareproblemen exporteren (OData)

### <a name="11-api-method-description"></a>Beschrijving van API-methode 1.1

Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat. Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="limitations"></a>Beperkingen

>- De maximale paginagrootte is 200.000.
>
>- Tariefbeperkingen voor deze API zijn 30 oproepen per minuut en 1000 oproepen per uur.

### <a name="12-permissions"></a>1.2 Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype | Machtiging | Weergavenaam machtiging
---|---|---
Toepassing | Kwetsbaarheid.Read.All | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'
Gedelegeerd (werk- of schoolaccount) | Kwetsbaarheid.Lezen | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'

### <a name="13-url"></a>1,3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1,4 Parameters

- pageSize (standaard = 50.000) – aantal resultaten in antwoord
- $top – aantal resultaten dat moet worden retourneren (wordt niet als resultaat @odata.nextLink en dus niet alle gegevens)

### <a name="15-properties"></a>1,5 eigenschappen
>
>[!Note]
>
>- Elke record is ongeveer 1 KB aan gegevens. U moet hiermee rekening houden bij het kiezen van de juiste paginaSize-parameter voor u.
>
>- Sommige extra kolommen kunnen worden geretourneerd in het antwoord. Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.
>
>- De eigenschappen die in de volgende tabel zijn gedefinieerd, worden alfabetisch weergegeven op eigenschap-id.  Bij het uitvoeren van deze API wordt de resulterende uitvoer niet noodzakelijkerwijs geretourneerd in dezelfde volgorde als in deze tabel.
>

Eigenschap (id) | Gegevenstype | Omschrijving | Voorbeeld van een geretourneerde waarde
:---|:---|:---|:---
CveId | tekenreeks | Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures). | CVE-2020-15992
CvssScore | tekenreeks | De CVSS-score van de CVE. | 6.2
DeviceId | tekenreeks | Unieke id voor het apparaat in de service. | 9eaf3a8b5962e0e6b1af9ec75664a9b823df2d1
Apparaatnaam | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat. | johnlaptop.europe.contoso.com
DiskPaths  | \[Matrixreeks\] | Schijf bewijs dat het product is geïnstalleerd op het apparaat. | [ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel | tekenreeks | Het gebruiksniveau van dit beveiligingsprobleem (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit
FirstSeenTimestamp | tekenreeks | De eerste keer dat de CVE van dit product op het apparaat werd gezien. | 2020-11-03 10:13:34.8476880
Id | tekenreeks | Unieke id voor de record. | 123ABG55_573AG&mnp!
LastSeenTimestamp | tekenreeks | De laatste keer dat de CVE werd gezien op het apparaat. | 2020-11-03 10:13:34.8476880
OSPlatform | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie. | Windows10
RbacGroupName  | tekenreeks | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'. | Servers
RecommendationReference | tekenreeks | Een verwijzing naar de aanbevelings-id met betrekking tot deze software. | va-_-microsoft-_-silverlight
RecommendedSecurityUpdate (optioneel) | tekenreeks | Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken. | Beveiligingsupdates van april 2020
AanbevolenSecurityUpdateId (optioneel) | tekenreeks | Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base) | 4550961
RegistryPaths  | \[Matrixreeks\] | Registergegevens dat het product op het apparaat is geïnstalleerd. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName | tekenreeks | Naam van het softwareproduct. | chrome
SoftwareVendor | tekenreeks | Naam van de softwareleverancier. | google
SoftwareVersion | tekenreeks | Versienummer van het softwareproduct. | 81.0.4044.138
VulnerabilitySeverityLevel  | tekenreeks | Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap. | Gemiddeld

### <a name="16-examples"></a>1.6 Voorbeelden

#### <a name="161-request-example"></a>1.6.1 Voorbeeld van aanvraag

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 Voorbeeld van antwoord

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. Evaluatie van softwareproblemen exporteren (via bestanden)

### <a name="21-api-method-description"></a>Beschrijving van API-methode 2.1

Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat. Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="212-limitations"></a>2.1.2 Beperkingen

Tariefbeperkingen voor deze API zijn 5 oproepen per minuut en 20 oproepen per uur.

### <a name="22-permissions"></a>2.2 Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype | Machtiging | Weergavenaam machtiging
---|---|---
Toepassing | Kwetsbaarheid.Read.All | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'
Gedelegeerd (werk- of schoolaccount) | Kwetsbaarheid.Lezen | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4 Parameters

- sasValidHours: het aantal uren dat de download-URL's geldig zijn (maximaal 24 uur)

### <a name="25-properties"></a>2,5 eigenschappen

>[!Note]
>
>- De bestanden zijn gzip gecomprimeerde & in de Json-indeling met meerdere lijnen.
>
>- De DOWNLOAD-URL's zijn slechts 3 uur geldig. anders kunt u de parameter gebruiken.
>
>- Voor maximale downloadsnelheid van uw gegevens kunt u ervoor zorgen dat u downloadt vanuit dezelfde Azure-regio als uw gegevens.
>

>[!Note]
>
>- Elke record is ongeveer 1 KB aan gegevens. U moet hiermee rekening houden bij het kiezen van de juiste paginaSize-parameter voor u.
>
>- Sommige extra kolommen kunnen worden geretourneerd in het antwoord. Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.
>

Eigenschap (id) | Gegevenstype | Omschrijving | Voorbeeld van een geretourneerde waarde
:---|:---|:---|:---
Bestanden exporteren | \[matrixreeks\]  | Een lijst met download-URL's voor bestanden met de huidige momentopname van de organisatie. | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | tekenreeks | De tijd dat de export is gegenereerd. | 2021-05-20T08:00:00Z

### <a name="26-examples"></a>2.6 Voorbeelden

#### <a name="261-request-example"></a>2.6.1 Voorbeeld van aanvraag

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>2.6.2 Voorbeeld van antwoord

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Zie ook

- [Beoordelingsmethoden en -eigenschappen per apparaat exporteren](get-assessmnt-1methods-properties.md)

- [Veilige configuratiebeoordeling per apparaat exporteren](get-assessmnt-secure-cfg.md)

- [Beoordeling van de softwarevoorraad per apparaat exporteren](get-assessmnt-software-inventory.md)

Andere gerelateerde

- [Risicogebaseerd & vulnerability management](next-gen-threat-and-vuln-mgt.md)

- [Beveiligingslekken in uw organisatie](tvm-weaknesses.md)
