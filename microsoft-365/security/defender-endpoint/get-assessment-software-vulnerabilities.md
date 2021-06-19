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
ms.openlocfilehash: 6243da415c5cc509be33eabffd12516367164bff
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022868"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>Beoordeling van beveiligingsproblemen met software per apparaat exporteren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
Retourneert alle bekende softwareproblemen en hun gegevens voor alle apparaten, per apparaat.

Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen. Omdat de hoeveelheid gegevens erg groot kan zijn, kunnen deze op twee manieren worden opgehaald:

1. [Beoordeling van **JSON-reactie** bij](#1-export-software-vulnerabilities-assessment-json-response) het exporteren van softwareproblemen  De API haalt alle gegevens in uw organisatie op als Json-antwoorden. Deze methode is het beste _voor kleine organisaties met minder dan 100 K-apparaten._ Het antwoord is paginated, zodat u het veld odata.nextLink uit het antwoord kunt gebruiken \@ om de volgende resultaten op te halen.

2. [Beoordeling van beveiligingsproblemen met software **via bestanden exporteren**](#2-export-software-vulnerabilities-assessment-via-files) Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Via-bestanden wordt aanbevolen voor grote organisaties, met meer dan 100 K-apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden:

   - Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens.

   - Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

3. [Delta Export software vulnerabilities assessment **JSON response**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Retourneert een tabel met een vermelding voor elke unieke combinatie van: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId en EventTimestamp.
De API haalt gegevens in uw organisatie op als Json-antwoorden. Het antwoord is paginated, zodat u het veld @odata.nextLink uit het antwoord kunt gebruiken om de volgende resultaten op te halen. <br><br> In tegenstelling tot de volledige beoordeling van softwareproblemen (JSON-antwoord) - die wordt gebruikt om een volledige momentopname van de beoordeling van de beveiligingsproblemen van de software van uw organisatie per apparaat te verkrijgen - wordt de delta export OData API-oproep gebruikt om alleen de wijzigingen op te halen die zijn gebeurd tussen een geselecteerde datum en de huidige datum (de delta-API-oproep). In plaats van elke keer een volledige export met een grote hoeveelheid gegevens te krijgen, krijgt u alleen specifieke informatie over nieuwe, opgeloste en bijgewerkte beveiligingslekken. Delta export JSON response API call can also be used to calculate different KPI's such as "how many vulnerabilities were fixed?" of 'hoeveel nieuwe beveiligingslekken zijn toegevoegd aan mijn organisatie?' <br><br> Omdat de Delta Export JSON response API call for software vulnerabilities data returns for only a targeted date range, it is not considered a _full export_.

Gegevens die worden verzameld (met _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens. Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.

> [!Note]
>
> Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a>1. Evaluatie van softwareproblemen exporteren (JSON-antwoord)

### <a name="11-api-method-description"></a>Beschrijving van API-methode 1.1

Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat. Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="111-limitations"></a>1.1.1 Beperkingen

- De maximale paginagrootte is 200.000.

- Tariefbeperkingen voor deze API zijn 30 oproepen per minuut en 1000 oproepen per uur.

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

>[!Note]
>
>- Elke record is ongeveer 1 KB aan gegevens. U moet hiermee rekening houden bij het kiezen van de juiste paginaSize-parameter voor u.
>
>- Sommige extra kolommen kunnen worden geretourneerd in het antwoord. Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.
>
>- De eigenschappen die in de volgende tabel zijn gedefinieerd, worden alfabetisch weergegeven op eigenschap-id.  Bij het uitvoeren van deze API wordt de resulterende uitvoer niet noodzakelijkerwijs geretourneerd in dezelfde volgorde als in deze tabel.

<br/>

Eigenschap (id) | Gegevenstype | Beschrijving | Voorbeeld van een geretourneerde waarde
:---|:---|:---|:---
CveId | string | Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures). | CVE-2020-15992
CvssScore | string | De CVSS-score van de CVE. | 6.2
DeviceId | string | Unieke id voor het apparaat in de service. | 9eaf3a8b5962e0e6b1af9ec75664a9b823df2d1
Apparaatnaam | string | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat. | johnlaptop.europe.contoso.com
DiskPaths  | \[Matrixreeks\] | Schijf bewijs dat het product is geïnstalleerd op het apparaat. | [ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel | string | Het gebruiksniveau van dit beveiligingsprobleem (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit
FirstSeenTimestamp | string | De eerste keer dat de CVE van dit product op het apparaat werd gezien. | 2020-11-03 10:13:34.8476880
Id | string | Unieke id voor de record. | 123ABG55_573AG&mnp!
LastSeenTimestamp | string | De laatste keer dat de CVE werd gezien op het apparaat. | 2020-11-03 10:13:34.8476880
OSPlatform | string | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Deze eigenschap geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie. | Windows10
RbacGroupName  | string | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'. | Servers
RecommendationReference | string | Een verwijzing naar de aanbevelings-id met betrekking tot deze software. | va-_-microsoft-_-silverlight
RecommendedSecurityUpdate (optioneel) | string | Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken. | Beveiligingsupdates van april 2020
AanbevolenSecurityUpdateId (optioneel) | string | Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base) | 4550961
RegistryPaths  | \[Matrixreeks\] | Registergegevens dat het product op het apparaat is geïnstalleerd. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName | string | Naam van het softwareproduct. | chrome
SoftwareVendor | string | Naam van de softwareleverancier. | google
SoftwareVersion | string | Versienummer van het softwareproduct. | 81.0.4044.138
VulnerabilitySeverityLevel  | string | Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap. | Gemiddeld

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

Eigenschap (id) | Gegevenstype | Beschrijving | Voorbeeld van een geretourneerde waarde
:---|:---|:---|:---
Bestanden exporteren | \[matrixreeks\]  | Een lijst met download-URL's voor bestanden met de huidige momentopname van de organisatie. | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | string | De tijd dat de export is gegenereerd. | 2021-05-20T08:00:00Z

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

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a>3. Evaluatie van beveiligingsproblemen bij Delta-exportsoftware (JSON-antwoord)

### <a name="31-api-method-description"></a>Beschrijving van API-methode 3.1

Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. De API haalt gegevens in uw organisatie op als Json-antwoorden. Het antwoord is paginated, zodat u het veld @odata.nextLink uit het antwoord kunt gebruiken om de volgende resultaten op te halen. In tegenstelling tot de evaluatie van de volledige softwareproblemen (JSON-antwoord), die wordt gebruikt om een volledige momentopname van de beoordeling van de beveiligingsproblemen in de software van uw organisatie per apparaat te verkrijgen, wordt de delta export JSON-antwoord-API-oproep gebruikt om alleen de wijzigingen op te halen die zijn gebeurd tussen een geselecteerde datum en de huidige datum (de 'delta' API-oproep). In plaats van elke keer een volledige export met een grote hoeveelheid gegevens te krijgen, krijgt u alleen specifieke informatie over nieuwe, opgeloste en bijgewerkte beveiligingslekken. Delta export JSON response API call can also be used to calculate different KPI's such as "how many vulnerabilities were fixed?" of 'hoeveel nieuwe beveiligingslekken zijn toegevoegd aan mijn organisatie?'

>[!NOTE]
>
>Het wordt ten zeerste aangeraden om ten minste één keer per week de volledige evaluatie van beveiligingsproblemen met de exportsoftware te gebruiken per apparaat-API-oproep, en deze extra exportsoftwareproblemen worden op alle andere dagen van de week gewijzigd door de apparaat-API(delta)-API- oproep.  In tegenstelling tot de andere beoordelings-JSON-antwoord-API's, is de 'delta-export' geen volledige export. De delta-export bevat alleen de wijzigingen tussen een geselecteerde datum en de huidige datum (de 'delta'-API-oproep).

#### <a name="311-limitations"></a>3.1.1 Beperkingen

- De maximale paginagrootte is 200.000.

- De parameter sinceTime heeft een maximum van 14 dagen.

- Tariefbeperkingen voor deze API zijn 30 oproepen per minuut en 1000 oproepen per uur.

### <a name="32-permissions"></a>3.2 Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype | Machtiging | Weergavenaam machtiging
---|---|---
Toepassing | Kwetsbaarheid.Read.All | 'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'
Gedelegeerd (werk- of schoolaccount) | Kwetsbaarheid.Lezen | 'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'

### <a name="33-url"></a>URL van 3,3

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a>3.4 Parameters

- sinceTime (vereist) – De gegevens tussen een geselecteerde tijd en vandaag.
- pageSize (standaard = 50.000) – aantal resultaten in antwoord
- $top – aantal resultaten dat moet worden retourneren (wordt niet als resultaat @odata.nextLink en dus niet alle gegevens)

### <a name="35-properties"></a>3,5 eigenschappen

Elke geretourneerde record bevat alle gegevens uit de volledige evaluatie van beveiligingsproblemen met software op het apparaat OData API, plus twee extra velden:  _**EventTimestamp**_ en _**Status**_.

>[!NOTE]
>- Sommige extra kolommen kunnen worden geretourneerd in het antwoord. Deze kolommen zijn tijdelijk en kunnen worden verwijderd, dus gebruik alleen de gedocumenteerde kolommen.
>
>- De eigenschappen die in de volgende tabel zijn gedefinieerd, worden alfabetisch weergegeven op eigenschap-id.  Bij het uitvoeren van deze API wordt de resulterende uitvoer niet noodzakelijkerwijs geretourneerd in dezelfde volgorde als in deze tabel.
<br><br/>

Eigenschap (id) | Gegevenstype | Beschrijving | Voorbeeld van geretourneerde waarde
:---|:---|:---|:---
CveId | string | Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures). | CVE-2020-15992  
CvssScore | string | De CVSS-score van de CVE. | 6.2  
DeviceId | string | Unieke id voor het apparaat in de service. | 9eaf3a8b5962e0e6b1af9ec75664a9b823df2d1  
Apparaatnaam | string | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat. | johnlaptop.europe.contoso.com  
DiskPaths | Matrix[tekenreeks] | Schijf bewijs dat het product is geïnstalleerd op het apparaat. | [ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]  
EventTimestamp | Tekenreeks | De tijd dat deze deltagebeurtenis is gevonden. | 2021-01-11T11:06:08.291Z
ExploitabilityLevel | string | Het gebruiksniveau van dit beveiligingsprobleem (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit  
FirstSeenTimestamp | string | De eerste keer dat de CVE van dit product op het apparaat werd gezien. | 2020-11-03 10:13:34.8476880  
Id | string | Unieke id voor de record. | 123ABG55_573AG&mnp!  
LastSeenTimestamp | string | De laatste keer dat de CVE werd gezien op het apparaat. | 2020-11-03 10:13:34.8476880  
OSPlatform | string | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie. | Windows10  
RbacGroupName | string | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'. | Servers  
RecommendationReference | string | Een verwijzing naar de aanbevelings-id met betrekking tot deze software. | va--microsoft--silverlight  
AanbevolenSecurityUpdate  | string | Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken. | Beveiligingsupdates van april 2020  
AanbevolenSecurityUpdateId  | string | Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base) | 4550961  
RegistryPaths  | Matrix[tekenreeks] | Registergegevens dat het product op het apparaat is geïnstalleerd. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]  
SoftwareName | string | Naam van het softwareproduct. | chrome  
SoftwareVendor | string | Naam van de softwareleverancier. | google  
SoftwareVersion | string | Versienummer van het softwareproduct. | 81.0.4044.138  
Status | Tekenreeks | **Nieuw**   (voor een nieuw beveiligingsprobleem dat is geïntroduceerd op een apparaat)  (1) **Opgelost**(als dit beveiligingsprobleem niet meer bestaat op het apparaat, wat betekent dat het   is hersteld). (2)  **Bijgewerkt**   (als een beveiligingsprobleem op een apparaat is gewijzigd. De mogelijke wijzigingen zijn: CVSS-score, exploitabilityniveau, ernstniveau, DiskPaths, RegistryPaths, RecommendedSecurityUpdate). | Opgelost
VulnerabilitySeverityLevel | string | Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap. | Gemiddeld  

#### <a name="clarifications"></a>Verduidelijkingen

- Als de software is bijgewerkt van versie 1.0 naar versie 2.0 en beide versies worden blootgesteld aan CVE-A, ontvangt u twee afzonderlijke gebeurtenissen:  
   1. Opgelost : CVE-A op versie 1.0 is opgelost  
   1. Nieuw : CVE-A op versie 2.0 is toegevoegd

- Als een specifiek beveiligingsprobleem (bijvoorbeeld CVE-A) voor het eerst werd gezien op een specifiek tijdstip (bijvoorbeeld 10 januari) op software met versie 1.0 en een paar dagen later die software is bijgewerkt naar versie 2.0 die ook aan dezelfde CVE-A is blootgesteld, ontvangt u deze twee gescheiden gebeurtenissen:  
   1. Opgelost: CVE-X, FirstSeenTimestamp 10 januari, versie 1,0.  
   1. Nieuw : CVE-X, FirstSeenTimestamp 10 januari, versie 2.0.

### <a name="36-examples"></a>3.6 Voorbeelden

#### <a name="361-request-example"></a>3.6.1 Voorbeeld van aanvraag

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a>3.6.2 Voorbeeld van antwoord

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a>Zie ook

- [Beoordelingsmethoden en -eigenschappen per apparaat exporteren](get-assessment-methods-properties.md)

- [Veilige configuratiebeoordeling per apparaat exporteren](get-assessment-secure-config.md)

- [Beoordeling van de softwarevoorraad per apparaat exporteren](get-assessment-software-inventory.md)

Andere gerelateerde

- [Risicogebaseerd & vulnerability management](next-gen-threat-and-vuln-mgt.md)

- [Beveiligingslekken in uw organisatie](tvm-weaknesses.md)
