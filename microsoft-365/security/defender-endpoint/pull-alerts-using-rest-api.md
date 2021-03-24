---
title: Microsoft Defender voor eindpuntdetecties trekken met REST API
description: Lees hoe u een Microsoft Defender for Endpoint API-eindpunt belt om detecties in JSON-indeling op te halen met behulp van de SIEM REST-API.
keywords: detecties, pulldetecties, rest-api, aanvraag, antwoord
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: c8baf74d5f838c583b98fddd7d7d706c6e116a40
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058198"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>Microsoft Defender voor eindpuntdetecties trekken met behulp van SIEM REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- [Microsoft Defender for Endpoint Alert](alerts.md) is samengesteld uit een of meer detecties.
>- [Microsoft Defender voor eindpuntdetectie](api-portal-mapping.md) is samengesteld uit de verdachte gebeurtenis op het apparaat en de bijbehorende waarschuwingsgegevens.
>-De Microsoft Defender for Endpoint Alert API is de nieuwste API voor waarschuwingsverbruik en bevat een gedetailleerde lijst met verwante gegevens voor elke waarschuwing. Zie Waarschuwingsmethoden en [-eigenschappen](alerts.md) en [Lijstwaarschuwingen](get-alerts.md)voor meer informatie.

Microsoft Defender voor Eindpunt ondersteunt het OAuth 2.0-protocol om detecties uit de API te halen.

In het algemeen ondersteunt het OAuth 2.0-protocol vier typen stromen:
- Autorisatieverleningsstroom
- Impliciete stroom
- Clientreferentiesstroom
- Stroom resourceeigenaar

Zie de website van OAuth voor meer informatie over de [OAuth-specificaties.](http://www.oauth.net)

Microsoft Defender for Endpoint ondersteunt  de _machtigingsstroom_ en de clientreferentiestroom om toegang te krijgen tot detecties voor pull-detecties, met Azure Active Directory (AAD) als autorisatieserver.

De _autorisatieverleningsstroom_ gebruikt gebruikersreferenties om een autorisatiecode te verkrijgen, die vervolgens wordt gebruikt om een toegangs token te verkrijgen.

De _clientreferentiestroom maakt_ gebruik van clientreferenties om te verifiëren tegen de URL van het Eindpunt van Microsoft Defender voor Eindpunt. Deze stroom is geschikt voor scenario's waarin een OAuth-client aanvragen maakt voor een API waarvoor geen gebruikersreferenties nodig zijn.

Gebruik de volgende methode in de Microsoft Defender for Endpoint API om detecties in JSON-indeling op te halen.

>[!NOTE]
>In het Microsoft Defender-beveiligingscentrum worden soortgelijke waarschuwingsdetecties samengevoegd tot één waarschuwing. Deze API haalt waarschuwingsdetecties in de onbewerkte vorm op basis van de queryparameters die u hebt ingesteld, zodat u uw eigen groepering en filtering kunt toepassen. 

## <a name="before-you-begin"></a>Voordat u begint
- Voordat u het Eindpunt van Microsoft Defender voor Eindpunt belt om detecties op te halen, moet u de SIEM-integratietoepassing inschakelen in Azure Active Directory (AAD). Zie [SiEM-integratie inschakelen in Microsoft Defender voor eindpunt voor meer informatie.](enable-siem-integration.md)

- Noteer de volgende waarden in uw Azure-toepassingsregistratie. U hebt deze waarden nodig om de OAuth-stroom in uw service of daemon-app te configureren:
  - Toepassings-id (uniek voor uw toepassing)
  - App-sleutel of geheim (uniek voor uw toepassing)
  - Het OAuth 2.0-token-eindpunt van uw app
    - Zoek deze waarde  door onder aan de Azure Management Portal op de pagina van uw app op Eindpunten weergeven te klikken. Het eindpunt ziet eruit als `https://login.microsoftonline.com/{tenantId}/oauth2/token` .

## <a name="get-an-access-token"></a>Een toegangs token krijgen
Voordat u oproepen naar het eindpunt maakt, moet u een toegangs token krijgen.

U gebruikt het access-token om toegang te krijgen tot de beveiligde resource, die detecties is in Microsoft Defender voor Eindpunt.

Als u een toegangs token wilt krijgen, moet u een POST-aanvraag indienen bij het eindpunt van het tokenuitvaardigingspunt. Hier is een voorbeeldaanvraag:

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
Het antwoord bevat een toegangs token en vervaldatumgegevens.

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
U kunt nu de  waarde in het veld access_token gebruiken in een aanvraag voor de Defender for Endpoint API.

## <a name="request"></a>Aanvraag
Met een access-token kan uw app geverifieerde aanvragen indienen bij de Microsoft Defender for Endpoint API. De app moet het toegangsken toevoegen aan de autorisatiekoptekst van elke aanvraag.

### <a name="request-syntax"></a>Syntaxis aanvragen
Methode | URI aanvragen
:---|:---|
Toevoegen| Gebruik de URI die van toepassing is op uw regio. <br><br> **Voor de EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts` </br> **Voor ons:**`https://wdatp-alertexporter-us.windows.com/api/alerts` <br> **Voor Groot-Brittannië:**`https://wdatp-alertexporter-uk.windows.com/api/alerts` 

### <a name="request-header"></a>Koptekst aanvragen
Koptekst | Type | Beschrijving|
:--|:--|:--
Autorisatie | tekenreeks | Vereist. Het Azure AD access-token in het formulier  &lt; *Bearer-token* &gt; . |

### <a name="request-parameters"></a>Parameters aanvragen

Gebruik optionele queryparameters om de hoeveelheid gegevens op te geven en te bepalen die in een antwoord worden geretourneerd. Als u deze methode zonder parameters noemt, bevat het antwoord alle waarschuwingen in uw organisatie in de afgelopen 2 uur.

Name | Value| Beschrijving
:---|:---|:---
sinceTimeUtc | DateTime | Hiermee definieert u de waarschuwingen met een lagere tijd die worden opgehaald op basis van het veld: <br> `LastProcessedTimeUtc` <br> Het tijdbereik is: van sinceTimeUtc-tijd tot huidige tijd. <br><br> **OPMERKING:** Als dit niet is opgegeven, worden alle waarschuwingen die in de afgelopen twee uur zijn gegenereerd, opgehaald.
untilTimeUtc | DateTime | Hiermee definieert u de waarschuwingen voor de hoogste tijdsgebonden waarschuwingen die worden opgehaald. <br> Het tijdbereik is: van `sinceTimeUtc` tijd tot `untilTimeUtc` tijd. <br><br> **OPMERKING:** Wanneer dit niet is opgegeven, is de standaardwaarde de huidige tijd.
geleden | tekenreeks | Haalt waarschuwingen in de volgende tijdsbereik op: van `(current_time - ago)` tijd tot `current_time` tijd. <br><br> Waarde moet worden ingesteld op basis van **de ISO 8601-duurnotatie** <br> Voorbeeld: in de afgelopen 10 minuten worden waarschuwingen `ago=PT10M` binnengekomen.
limiet | int | Hiermee wordt het aantal waarschuwingen definieerd dat moet worden opgehaald. De meest recente waarschuwingen worden opgehaald op basis van het gedefinieerde getal.<br><br> **OPMERKING:** Wanneer dit niet is opgegeven, worden alle beschikbare waarschuwingen in het tijdbereik opgehaald.
machinegroepen | tekenreeks | Hiermee geeft u apparaatgroepen op waar u waarschuwingen vandaan wilt halen. <br><br> **OPMERKING:** Wanneer dit niet is opgegeven, worden waarschuwingen van alle apparaatgroepen opgehaald. <br><br> Voorbeeld: <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/Alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
DeviceCreatedMachineTags | tekenreeks | Eén apparaatlabel uit het register.
CloudCreatedMachineTags | tekenreeks | Apparaatlabels die zijn gemaakt in het Microsoft Defender-beveiligingscentrum.

### <a name="request-example"></a>Voorbeeld aanvragen
In het volgende voorbeeld wordt gedemonstreerd hoe u alle detecties in uw organisatie kunt ophalen.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

In het volgende voorbeeld wordt een aanvraag gedemonstreerd voor de laatste 20 detecties sinds 2016-09-12 00:00:00: 00.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>Antwoord
De retourwaarde is een matrix met waarschuwingsobjecten in de JSON-indeling.

Hier is een voorbeeld van de retourwaarde:

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>Voorbeelden van code
### <a name="get-access-token"></a>Toegangs token krijgen
In de volgende codevoorbeelden wordt getoond hoe u een toegangs token kunt verkrijgen voor het bellen met de SIEM-API van Microsoft Defender voor Eindpunt.

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>Token gebruiken om verbinding te maken met het eindpunt detecties
In de volgende codevoorbeelden wordt gedemonstreerd hoe u een access-token gebruikt voor het bellen naar de DEFENDER for Endpoint SIEM API om waarschuwingen te ontvangen.

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>Foutcodes
De REST-API van Microsoft Defender voor eindpunt retourneert de volgende foutcodes die zijn veroorzaakt door een ongeldige aanvraag.

HTTP-foutcode | Beschrijving
:---|:---
401 | Ongeldige aanvraag of ongeldig token.
403 | Niet-geautoriseerde uitzondering: een van de domeinen wordt niet beheerd door de tenantbeheerder of tenantstaat wordt verwijderd.
500 | Fout in de service.

## <a name="related-topics"></a>Verwante onderwerpen
- [SIEM-integratie inschakelen in Microsoft Defender voor Eindpunt](enable-siem-integration.md)
- [ArcSight configureren om Microsoft Defender te gebruiken voor eindpuntdetecties](configure-arcsight.md)
- [Detecties naar uw SIEM-hulpprogramma's trekken](configure-siem.md)
- [Microsoft Defender voor eindpuntdetectievelden](api-portal-mapping.md)
- [Problemen met de integratie van SIEM-hulpprogramma's oplossen](troubleshoot-siem.md)
