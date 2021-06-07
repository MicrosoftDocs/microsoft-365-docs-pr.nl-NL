---
title: Veilige configuratiebeoordeling per apparaat exporteren
description: Retourneert een vermelding voor elke unieke combinatie van DeviceId, ConfigurationId.
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
ms.openlocfilehash: ab33db7fb7acf1969973a7af8f80ea97ef3d378f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778332"
---
# <a name="export-secure-configuration-assessment-per-device"></a>Veilige configuratiebeoordeling per apparaat exporteren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Retourneert alle configuraties en hun status, per apparaat.

Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen. Omdat de hoeveelheid gegevens groot kan zijn, kunnen deze op twee manieren worden opgehaald:

- [Veilige configuratiebeoordeling **OData**](#1-export-secure-configuration-assessment-odata)exporteren: de API haalt alle gegevens in uw organisatie op als Json-antwoorden, volgens het OData-protocol. Deze methode is het beste _voor kleine organisaties met minder dan 100 K-apparaten._ Het antwoord is paginated, zodat u het veld odata.nextLink uit het antwoord kunt gebruiken \@ om de volgende resultaten op te halen.

- [Veilige configuratiebeoordeling **exporteren via bestanden:**](#2-export-secure-configuration-assessment-via-files)met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen. Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100 K-apparaten. Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen. Het antwoord bevat URL's om alle gegevens uit de Azure Storage. Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden:

  - Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens.

  - Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.

Gegevens die worden verzameld (met _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens. Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.

> [!Note]
>
> Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**

## <a name="1-export-secure-configuration-assessment-odata"></a>1. Beveiligde configuratiebeoordeling exporteren (OData)

### <a name="11-api-method-description"></a>Beschrijving van API-methode 1.1

Deze API-reactie bevat de Secure Configuration Assessment op uw blootgestelde apparaten en retourneert een vermelding voor elke unieke combinatie van DeviceId, ConfigurationId.

#### <a name="111-limitations"></a>1.1.1 Beperkingen

- De maximale paginagrootte is 200.000.

- Tariefbeperkingen voor deze API zijn 30 oproepen per minuut en 1000 oproepen per uur.

### <a name="12-permissions"></a>1.2 Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype | Machtiging | Weergavenaam machtiging
---|---|---
Toepassing | Kwetsbaarheid.Read.All | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'
Gedelegeerd (werk- of schoolaccount) | Kwetsbaarheid.Lezen | \'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'

### <a name="13-url"></a>1,3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>1,4 Parameters

- pageSize \( default = 50.000 \) – aantal resultaten in antwoord

- \$boven: het aantal resultaten dat moet worden retourneren, geeft \( geen odata.nextLink als resultaat en haalt daarom niet alle \@ gegevens op\)

### <a name="15-properties"></a>1,5 eigenschappen

>[!Note]
>
>- De eigenschappen die in de volgende tabel zijn gedefinieerd, worden alfabetisch weergegeven op eigenschap-id.  Bij het uitvoeren van deze API wordt de resulterende uitvoer niet noodzakelijkerwijs geretourneerd in dezelfde volgorde als in deze tabel.
>
>- Sommige extra kolommen kunnen worden geretourneerd in het antwoord. Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.
>

Eigenschap (id) | Gegevenstype | Omschrijving | Voorbeeld van een geretourneerde waarde
:---|:---|:---|:---
ConfigurationCategory | tekenreeks | Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen | Beveiligingsbesturingselementen
ConfigurationId | tekenreeks | Unieke id voor een specifieke configuratie | scid-10000
ConfigurationImpact | tekenreeks | Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10) | 9
ConfigurationName | tekenreeks | Weergavenaam van de configuratie | Onboarden apparaten naar Microsoft Defender voor Eindpunt
ConfigurationSubcategory | tekenreeks | Subcategorie of subgroepering waarvan de configuratie deel uitmaken. In veel gevallen worden hier specifieke mogelijkheden of functies beschreven. | Onboard-apparaten
DeviceId | tekenreeks | Unieke id voor het apparaat in de service. | 9eaf3a8b5962e0e6b1af9ec75664a9b823df2d1
Apparaatnaam | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat. | johnlaptop.europe.contoso.com
IsApplicable | bool | Geeft aan of de configuratie of het beleid van toepassing is | waar
IsCompliant | bool | Geeft aan of de configuratie of het beleid juist is geconfigureerd | onwaar
IsExpectedUserImpact | bool | Geeft aan of er gevolgen voor de gebruiker zijn als de configuratie wordt toegepast | waar
OSPlatform | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie. | Windows10
RbacGroupName | tekenreeks | De groep Toegangsbeheer (RBAC) op basis van rollen. Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'. Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'. | Servers
RecommendationReference | tekenreeks | Een verwijzing naar de aanbevelings-id met betrekking tot deze software. | sca-_-scid-20000
Tijdstempel | tekenreeks | De laatste keer dat de configuratie op het apparaat is gezien | 2020-11-03 10:13:34.8476880

### <a name="16-examples"></a>1.6 Voorbeelden

#### <a name="161-request-example"></a>1.6.1 Voorbeeld van aanvraag

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a>1.6.2 Voorbeeld van antwoord

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. Beveiligde configuratiebeoordeling exporteren (via bestanden)

### <a name="21-api-method-description"></a>Beschrijving van API-methode 2.1

Deze API-reactie bevat de Secure Configuration Assessment op uw blootgestelde apparaten en retourneert een vermelding voor elke unieke combinatie van DeviceId, ConfigurationId.

#### <a name="212-limitations"></a>2.1.2 Beperkingen

Tariefbeperkingen voor deze API zijn 5 oproepen per minuut en 20 oproepen per uur.

### <a name="22-permissions"></a>2.2 Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype | Machtiging | Weergavenaam machtiging
---|---|---
Toepassing | Kwetsbaarheid.Read.All | \'Informatie over Threat and Vulnerability Management kwetsbaarheid lezen\'
Gedelegeerd (werk- of schoolaccount) | Kwetsbaarheid.Lezen | \'Informatie over Threat and Vulnerability Management kwetsbaarheid lezen\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>Parameters

- sasValidHours: het aantal uren dat de download-URL's geldig zijn (maximaal 24 uur).

### <a name="25-properties"></a>2,5 eigenschappen

>[!Note]
>
>- De bestanden zijn gzip gecomprimeerde & in de Json-indeling met meerdere lijnen.
>
>- De DOWNLOAD-URL's zijn slechts 3 uur geldig. anders kunt u de parameter gebruiken.
>
>- Voor maximale downloadsnelheid van uw gegevens kunt u ervoor zorgen dat u downloadt vanuit dezelfde Azure-regio waarin uw gegevens zich bevinden.
>
Eigenschap (id) | Gegevenstype | Omschrijving | Voorbeeld van een geretourneerde waarde
:---|:---|:---|:---
Bestanden exporteren | \[matrixreeks\] | Een lijst met DOWNLOAD-URL's voor bestanden met de huidige momentopname van de organisatie | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | tekenreeks | De tijd dat de export is gegenereerd. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Voorbeelden

#### <a name="261-request-example"></a>2.6.1 Voorbeeld van aanvraag

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>2.6.2 Voorbeeld van antwoord

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Zie ook

- [Beoordelingsmethoden en -eigenschappen per apparaat exporteren](get-assessmnt-1methods-properties.md)

- [Beoordeling van de softwarevoorraad per apparaat exporteren](get-assessmnt-software-inventory.md)

- [Beoordeling van beveiligingsproblemen met software per apparaat exporteren](get-assessmnt-software-vulnerabilities.md)

Andere gerelateerde

- [Risicogebaseerd & vulnerability management](next-gen-threat-and-vuln-mgt.md)

- [Beveiligingslekken in uw organisatie](tvm-weaknesses.md)
