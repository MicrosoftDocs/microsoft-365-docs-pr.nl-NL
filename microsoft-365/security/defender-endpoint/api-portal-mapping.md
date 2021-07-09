---
title: API-velden van Microsoft Defender voor eindpuntdetecties
description: Meer informatie over de manier waarop de API-velden detecties aan de waarden in Microsoft 365 Defender
keywords: detecties, detectievelden, velden, api, velden, pull Detecties, rest api, aanvraag, antwoord
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
ms.openlocfilehash: f9a0d4ddeee5c1dc49c53e324854cabccc5f79e5
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339548"
---
# <a name="microsoft-defender-for-endpoint-detections-api-fields"></a>API-velden van Microsoft Defender voor eindpuntdetecties

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-apiportalmapping-abovefoldlink)

Meer informatie over welke gegevensvelden worden weergegeven als onderdeel van de DETECTIE-API en hoe ze worden Microsoft 365 Defender.

>[!Note]
>- [Defender for Endpoint Alert](alerts.md) is samengesteld uit een of meer detecties.
>- **Microsoft Defender ATP Detection** is samengesteld uit de verdachte gebeurtenis op het apparaat en de bijbehorende **waarschuwingsgegevens.**
>- De Microsoft Defender for Endpoint Alert API is de nieuwste API voor waarschuwingsverbruik en bevat een gedetailleerde lijst met verwante gegevens voor elke waarschuwing. Zie Waarschuwingsmethoden en [-eigenschappen](alerts.md) en [Lijstwaarschuwingen](get-alerts.md)voor meer informatie.

## <a name="detections-api-fields-and-portal-mapping"></a>Detecties API-velden en portaltoewijzing
De volgende tabel bevat de beschikbare velden die worden blootgesteld aan de detecties van API-payload. Hier ziet u voorbeelden van de ingevulde waarden en een verwijzing naar de manier waarop gegevens worden weerspiegeld in de portal.

De kolom ArcSight-veld bevat de standaardtoewijzing tussen de velden Defender voor eindpunten en de ingebouwde velden in ArcSight. U kunt het toewijzingsbestand downloaden van de portal wanneer u de siem-integratiefunctie inschakelen en u kunt het aanpassen aan de behoeften van uw organisatie. Zie [SiEM-integratie inschakelen in Defender voor eindpunt](enable-siem-integration.md)voor meer informatie.

Veldnummers komen overeen met de getallen in de onderstaande afbeeldingen.

> [!div class="mx-tableFixed"]
> 
> | Portal-label   | SIEM-veldnaam           | ArcSight-veld      | Voorbeeldwaarde                                                                      | Omschrijving                                                                                                                                                                    |
> |------------------|---------------------------|---------------------|------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
> | 1                | Waarschuwingstitel                | naam                | Microsoft Defender AV heeft malware met hoge ernst 'Mikatz' gedetecteerd | Waarde die beschikbaar is voor elke detectie.                                                                                                                                               |
> | 2                | Ernst                  | deviceSeverity      | Hoog                                                                             | Waarde die beschikbaar is voor elke detectie.                                                                                                                                               |
> | 3                | Categorie                  | deviceEventCategory | Malware                                                               | Waarde die beschikbaar is voor elke detectie.                                                                                                                                               |
> | 4                | Detectiebron                    | sourceServiceName   | Antivirus                                                                 | Microsoft Defender Antivirus of Defender voor Eindpunt. Waarde die beschikbaar is voor elke detectie.                                                                                         |
> | 5                | MachineName               | sourceHostName      | desktop-4a5ngd6                                                                           | Waarde die beschikbaar is voor elke detectie.                                                                                                                                               |
> | 6                | Bestandsnaam                  | bestandsnaam            | Robocopy.exe                                                                       | Beschikbaar voor detecties die zijn gekoppeld aan een bestand of proces.                                                                                                                      |
> | 7                | FilePath                  | filePath            | C:\Windows\System32\Robocopy.exe                                                   | Beschikbaar voor detecties die zijn gekoppeld aan een bestand of proces.                                                                                                                     |
> | 8                | UserDomain                | sourceNtDomain      | CONTOSO                                                                            | Het domein van de gebruikerscontext waarin de activiteit wordt uitgevoerd, beschikbaar voor detecties op basis van gedrag van eindpunten van Defender voor eindpunten.                                                           |
> | 9                | Gebruikersnaam                  | sourceUserName      | liz.bean                                                                           | De context van de gebruiker die de activiteit uitwerkt, beschikbaar voor detecties op basis van gedrag van eindpunten van Defender.                                                                           |
> | 10               | Sha1                      | fileHash            | 3da065e07b990034e9db7842167f70b63aa5329                                           | Beschikbaar voor detecties die zijn gekoppeld aan een bestand of proces.                                                                                                                      |
> | 11               | Sha256                    | deviceCustomString6 | ebf54f745dc81e1958f75e4ca91dd0ab989fc9787bb6b0bf993e2f5                   | Beschikbaar voor AV-detecties van Microsoft Defender.                                                                                                                                    |
> | 12               | Md5                       | deviceCustomString5 | db979c04a99b96d370988325bb5a8b21                                                   | Beschikbaar voor AV-detecties van Microsoft Defender.                                                                                                                                    |
> | 13               | ThreatName                | deviceCustomString1  | HackTool:Win32/Mikatz!dha                                                         | Beschikbaar voor AV-detecties van Microsoft Defender.                                                                                                                                    |
> | 14               | IpAddress                 | sourceAddress       | 218.90.204.141                                                                     | Beschikbaar voor detecties die zijn gekoppeld aan netwerkgebeurtenissen. Bijvoorbeeld 'Communicatie naar een schadelijke netwerkbestemming'.                                                        |
> | 15               | Url                       | requestUrl          | down.esales360.cn                                                                  | Beschikbaar voor detecties die zijn gekoppeld aan netwerkgebeurtenissen. Bijvoorbeeld 'Communicatie naar een schadelijke netwerkbestemming'.                                                         |
> | 16               | HerstelIsSuccess      | deviceCustomNumber2 | WAAR                                                                               | Beschikbaar voor AV-detecties van Microsoft Defender. ArcSight-waarde is 1 wanneer WAAR en 0 wanneer ONWAAR.                                                                                    |
> | 17               | WasExecutingWhileDetected | deviceCustomNumber1 | ONWAAR                                                                              | Beschikbaar voor AV-detecties van Microsoft Defender. ArcSight-waarde is 1 wanneer WAAR en 0 wanneer ONWAAR.                                                                                    |
> | 18               | AlertId                   | externalId          | 636210704265059241_673569822                                                       | Waarde die beschikbaar is voor elke detectie.                                                                                                                                               |
> | 19               | LinkToWDATP               | flexString1         | `https://securitycenter.windows.com/alert/636210704265059241_673569822`            | Waarde die beschikbaar is voor elke detectie.                                                                                                                                               |
> | 20               | AlertTime                 | deviceReceiptTime   | 2017-05-07T01:56:59.3191352Z                                                       | De tijd dat de gebeurtenis heeft plaatsgevonden. Waarde die beschikbaar is voor elke detectie.                                                                                       |
> | 21               | MachineDomain             | sourceDnsDomain     | contoso.com                                                                        | Domeinnaam is niet relevant voor AAD-apparaten die lid zijn van AAD. Waarde die beschikbaar is voor elke detectie.                                                                                           |
> | 22               | Actor                     | deviceCustomString4 | BORON                                                                                   | Beschikbaar voor waarschuwingen met betrekking tot een bekende actorgroep.                                                                                                                         |
> | 21+5             | ComputerDnsName           | Geen toewijzing          | liz-bean.contoso.com                                                               | De volledig gekwalificeerde domeinnaam van het apparaat. Waarde die beschikbaar is voor elke detectie.                                                                                                    |
> |                  | LogOnUsers                | sourceUserId        | contoso\liz-bean;   contoso\jay-hardee                                             | Het domein en de gebruiker van de interactieve aanmeldingsgebruiker/gebruikers op het moment van de gebeurtenis. Opmerking: Voor apparaten op Windows 10 versie 1607 zijn de domeingegevens niet beschikbaar. |
> |                  | InternalIPv4List          | Geen toewijzing          | 192.168.1.7, 10.1.14.1                                                             | Lijst met interne IPV4-IPs voor actieve netwerkinterfaces.                                                                                                                                                                               |
> |                  | InternalIPv6List          | Geen toewijzing          | fd30:0000:0000:0001:ff4e:003e:0009:000e, FE80:CD00:0000:0CDE:1257:0000:211E:729C | Lijst met interne IPV6-IPs voor actieve netwerkinterfaces.                                                                                                                                                                               |
| | LinkToMTP | Geen toewijzing | `https://security.microsoft.com/alert/da637370718981685665_16349121` | Waarde die beschikbaar is voor elke detectie.
| | IncidentLinkToMTP | Geen toewijzing | `"https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM` | Waarde die beschikbaar is voor elke detectie.
| | IncidentLinkToWDATP | Geen toewijzing | `https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM` | Waarde die beschikbaar is voor elke detectie.
> | Intern veld | LastProcessedTimeUtc      | Geen toewijzing          | 2017-05-07T01:56:58.9936648Z                                                       | Tijd waarop de gebeurtenis bij de back-end is aangekomen. Dit veld kan worden gebruikt bij het instellen van de aanvraagparameter voor het tijdsbereik dat detecties worden opgehaald.                         |
> |                  | Geen onderdeel van het schema    | apparaatVendor        |                                                                                    | Statische waarde in de ArcSight-toewijzing - 'Microsoft'.                                                                                                                          |
> |                  | Geen onderdeel van het schema    | deviceProduct       |                                                                                    | Statische waarde in de ArcSight-toewijzing - 'Microsoft Defender ATP'.                                                                                                               |
> |                  | Geen onderdeel van het schema    | deviceVersion       |                                                                                    | Statische waarde in de ArcSight-toewijzing - '2.0', die wordt gebruikt om de toewijzingsversies te identificeren.                                                                                         


![Afbeelding van waarschuwing met getallen](images/atp-alert-page.png)

![Afbeelding van deelvenster waarschuwingsdetails met getallen](images/atp-siem-mapping13.png)

![Afbeelding van artefacttijdlijn met getallen1](images/atp-siem-mapping3.png)

![Afbeelding van artefacttijdlijn met getallen2](images/atp-siem-mapping4.png)

![Afbeeldingsmachineweergave](images/atp-mapping6.png)

![URL van afbeeldingsbrowser](images/atp-mapping5.png)

![Waarschuwing voor afbeeldingsacacteur](images/atp-mapping7.png)


## <a name="related-topics"></a>Gerelateerde onderwerpen
- [SIEM-integratie inschakelen in Microsoft Defender voor Eindpunt](enable-siem-integration.md)
- [ArcSight configureren om Microsoft Defender te gebruiken voor eindpuntdetecties](configure-arcsight.md)
- [Microsoft Defender voor eindpuntdetecties trekken met REST API](pull-alerts-using-rest-api.md)
- [Problemen met de integratie van SIEM-hulpprogramma's oplossen](troubleshoot-siem.md)
