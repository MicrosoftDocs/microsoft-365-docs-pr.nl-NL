---
title: Lijst incidenten API in Microsoft 365 Defender
description: Meer informatie over het vermelden van incidenten-API in Microsoft 365 Defender
keywords: lijst, incident, incidenten, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572151"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Lijst incidenten API in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.


## <a name="api-description"></a>API-beschrijving

Met de API voor lijstincidenten kunt u incidenten sorteren om een geïnformeerde cyberbeveiligingsrespons te maken. Het toont een verzameling incidenten die zijn gemarkeerd in uw netwerk, binnen het tijds bereik dat u hebt opgegeven in uw beleid voor het bewaren van omgevingen. De meest recente incidenten worden bovenaan de lijst weergegeven. Elk incident bevat een matrix met gerelateerde waarschuwingen en de bijbehorende entiteiten.

De API ondersteunt de volgende **OData-operators:**

- `$filter` op de `lastUpdateTime` , `createdTime` , en `status` `assignedTo` eigenschappen
- `$top`, met een maximumwaarde van **100**
- `$skip`

## <a name="limitations"></a>Beperkingen

1. De maximale paginagrootte is **100 incidenten**.
2. Het maximale aantal aanvragen is **50 oproepen per minuut** en **1500 oproepen per uur**.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API aan te roepen. Zie [Access Microsoft 365 Defender API's](api-access.md) voor meer informatie, inclusief het kiezen van machtigingen

Machtigingstype | Machtiging | Naam van machtigingsweergave
-|-|-
Toepassing | Incident.read.all | Lees alle incidenten
Toepassing | Incident.ReadWrite.All | Lees en schrijf alle incidenten
Gedelegeerd (werk- of schoolaccount) | Incident.Lees | Incidenten lezen
Gedelegeerd (werk- of schoolaccount) | Incident.ReadWrite | Lees en schrijf incidenten

> [!Note]
> Bij het verkrijgen van een token met behulp van gebruikers referenties:
>
> - De gebruiker moet weergavemachtigingen hebben voor incidenten in de portal.
> - Het antwoord bevat alleen incidenten waaraan de gebruiker wordt blootgesteld.

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Headers aanvragen

Naam | Type | Omschrijving
-|-|-
machtiging | Tekenreeks | Aan toonder {token}. **Vereist**


## <a name="request-body"></a>Instantie aanvragen

geen.

## <a name="response"></a>antwoord

Als dit is gelukt, retourneert deze methode `200 OK` en een lijst met [incidenten](api-incident.md) in de hoofdtekst van de reactie.

## <a name="schema-mapping"></a>Schematoewijzing

### <a name="incident-metadata"></a>Metagegevens van incidenten

Veldnaam | Omschrijving | Voorbeeldwaarde
-|-|-
incidentId | Unieke identificatie om het incident weer te geven | 924565
omleidingIncidentId | Alleen ingevuld in het geval dat een incident wordt gegroepeerd met een ander incident, als onderdeel van de logica voor het verwerken van incidenten. | 924569
incidentNaam | Tekenreekswaarde beschikbaar voor elk incident. | Ransomware-activiteit
gemaaktTijd | Tijdstip waarop het incident voor het eerst werd gemaakt. | 2020-09-06T14:46:57.0733333Z
laatsteUpdateTime | Tijdstip waarop het incident voor het laatst is bijgewerkt op de back-end.<br /><br /> Dit veld kan worden gebruikt wanneer u de aanvraagparameter instelt voor het tijdsbereik waarin incidenten worden opgehaald. | 09-09-2020T14:46:57.29Z
toegewezenTo | Eigenaar van het incident, of *null* als er geen eigenaar is toegewezen. | secop2@contoso.com
classificatie | De specificatie voor het incident. De eigenschapswaarden zijn: *Onbekend*, *FalsePositive*, *TruePositive* | Unknown
vastberadenheid | Hiermee geeft u de bepaling van het incident op. De eigenschapswaarden zijn: *Niet beschikbaar*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *Ongewenste Software*, *Overig* | Niet beschikbaar
status | Incidenten categoriseren (als *Actief* of *Opgelost*). Het kan u helpen bij het organiseren en beheren van uw reactie op incidenten. | Actief
strengheid | Geeft de mogelijke impact op activa aan. Hoe hoger de ernst, hoe groter de impact. Items met een hogere ernst vereisen meestal de meest directe aandacht.<br /><br />Een van de volgende waarden: *Informatief*, *Laag*, *Gemiddeld en *Hoog*. | Gemiddeld
Tags | Matrix met aangepaste tags die aan een incident zijn gekoppeld, bijvoorbeeld om een groep incidenten met een gemeenschappelijk kenmerk te markeren. | \[\]
Opmerkingen | Matrix met opmerkingen die door secops zijn gemaakt bij het beheren van het incident, bijvoorbeeld aanvullende informatie over de classificatieselectie. | \[\]
Waarschuwingen | Array met alle waarschuwingen met betrekking tot het incident, plus andere informatie, zoals ernst, entiteiten die betrokken waren bij de waarschuwing en de bron van de waarschuwingen. | \[\] (zie details over waarschuwingsvelden hieronder)

### <a name="alerts-metadata"></a>Metagegevens waarschuwen

Veldnaam | Omschrijving | Voorbeeldwaarde
-|-|-
alertId | Unieke id om de waarschuwing weer te geven | CaD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | Unieke id om het incident weer te geven waaraan deze waarschuwing is gekoppeld | 924565
serviceBron | Service waar de waarschuwing vandaan komt, zoals Microsoft Defender voor eindpunt, Microsoft Cloud App Security, Microsoft Defender voor identiteit of Microsoft Defender voor Office 365. | MicrosoftCloudAppSecurity
creatieTijd | Tijd waarop de waarschuwing voor het eerst is gemaakt. | 2020-09-06T14:46:55.7182276Z
laatstUpdatedTime | Tijdstip waarop de waarschuwing voor het laatst is bijgewerkt op de back-end. | 2020-09-06T14:46:57.2433333Z
opgelostTime | Tijdstip waarop de waarschuwing is opgelost. | 2020-09-10T05:22:59Z
eersteActiviteit | Tijdstip waarop de waarschuwing voor het eerst meldde dat de activiteit is bijgewerkt op de back-end.| 09-09-2020T05:22:59Z
titel | Korte identificatie van de tekenreekswaarde die beschikbaar is voor elke waarschuwing. | Ransomware-activiteit
beschrijving | Tekenreekswaarde die elke waarschuwing beschrijft. | De gebruiker Test User2 (testUser2@contoso.com) manipuleerde 99 bestanden met meerdere extensies eindigend op de ongewone extensie *herunterladen*. Dit is een ongewoon aantal bestandsmanipulaties en is indicatief voor een mogelijke ransomware-aanval.
categorie | Visuele en numerieke weergave van hoe ver de aanval is gevorderd langs de kill chain. Afgestemd op het [MITRE ATT&CK™ framework](https://attack.mitre.org/). | Gevolg
status | Waarschuwingen categoriseren (als *Nieuw,* *Actief* of *Opgelost*). Het kan u helpen bij het organiseren en beheren van uw reactie op waarschuwingen. | Nieuw
strengheid | Geeft de mogelijke impact op activa aan. Hoe hoger de ernst, hoe groter de impact. Items met een hogere ernst vereisen meestal de meest directe aandacht.<br>Een van de volgende waarden: *Informatief*, *Laag*, *Gemiddeld en *Hoog*. | Gemiddeld
onderzoekId | De geautomatiseerde onderzoeks-ID die door deze waarschuwing wordt geactiveerd. | 1234
onderzoekStaat | Informatie over de huidige status van het onderzoek. Een van de volgende waarden: *Onbekend*, *Beëindigd*, *Met succesgemedieerd*, *Goedaardig*, *Mislukt*, *Gedeeltelijk hersteld*, *Actief*, *PendingApproval*, *PendingResource*, *Gedeeltelijk onderzocht*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*. | Niet-ondersteundAlertType
classificatie | De specificatie voor het incident. De eigenschapswaarden zijn: *Onbekend*, *FalsePositive*, *TruePositive* of *null* | Unknown
vastberadenheid | Hiermee geeft u de bepaling van het incident op. De eigenschapswaarden zijn: *Niet beschikbaar*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *Ongewenste Software*, *Andere* of  *null* | gepast
toegewezenTo | Eigenaar van het incident, of *null* als er geen eigenaar is toegewezen. | secop2@contoso.com
actorNaam | De activiteitengroep, indien aanwezig, is gekoppeld aan deze waarschuwing. | boor
bedreigingFamilieNaam | Bedreigingsfamilie die aan deze waarschuwing is gekoppeld. | nul
mitreTechniek | De aanvalstechnieken, zoals afgestemd op de [MITRE ATT&CK](https://attack.mitre.org/)™ framework. | \[\]
Apparaten | Alle apparaten waar waarschuwingen met betrekking tot het incident zijn verzonden. | \[\] (zie details over entiteitsvelden hieronder)

### <a name="device-format"></a>Apparaatindeling

Veldnaam | Omschrijving | Voorbeeldwaarde
-|-|-
DeviceId | De apparaat-ID zoals aangegeven in Microsoft Defender voor eindpunt. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  De apparaat-ID zoals aangegeven in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis). Alleen beschikbaar voor apparaten die lid zijn van een domein. | nul
deviceDnsName | De volledig gekwalificeerde domeinnaam voor het apparaat. | user5cx.middleeast.corp.contoso.com
osPlatform | Het besturingssysteemplatform waarop het apparaat wordt uitgevoerd.| WindowsServer2016
osBouw | De buildversie voor het besturingssysteem waarop het apparaat wordt uitgevoerd. | 14393
rbacGroupName | De op [rollen gebaseerde groep voor toegangsbeheer](/azure/role-based-access-control/overview) (RBAC) die aan het apparaat is gekoppeld. | WDATP-Ring0
eersteSeen | Tijd waarop het apparaat voor het eerst werd gezien. | 2020-02-06T14:16:01.9330135Z
gezondheidStatus | De gezondheidstoestand van het apparaat. | Actief
risicoScore | De risicoscore voor het apparaat. | Hoog
Entiteiten | Alle entiteiten waarvan is vastgesteld dat ze deel uitmaken van of verband houden met een bepaalde waarschuwing. | \[\] (zie details over entiteitsvelden hieronder)

### <a name="entity-format"></a>Entiteitsindeling

Veldnaam | Omschrijving | Voorbeeldwaarde
-|-|-
entityType | Entiteiten waarvan is vastgesteld dat ze deel uitmaken van of verband houden met een bepaalde waarschuwing.<br>De eigenschappenwaarden zijn: *Gebruiker*, *Ip*, *URL*, *Bestand*, *Proces*, *MailBox*, *MailMessage*, *MailCluster*, *Register* | Gebruiker
sha1 | Beschikbaar als entityType *Bestand* is.<br>De bestandshash voor waarschuwingen die aan een bestand of proces zijn gekoppeld. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Beschikbaar als entityType *Bestand* is.<br>De bestandshash voor waarschuwingen die aan een bestand of proces zijn gekoppeld. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
Bestandsnaam | Beschikbaar als entityType *Bestand* is.<br>De bestandsnaam voor waarschuwingen die aan een bestand of proces zijn gekoppeld | Detector.UnitTests.dll
filePath | Beschikbaar als entityType *Bestand* is.<br>Het bestandspad voor waarschuwingen die aan een bestand of proces zijn gekoppeld | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId | Beschikbaar als entityType *Proces* is. | 24348
procesCommandLine | Beschikbaar als entityType *Proces* is. | "Uw bestand is klaar om1911150169.exe te \_ downloaden"
procesCreatietijd | Beschikbaar als entityType *Proces* is. | 2020-07-18T03:25:38.5269993Z
ouderProcessId | Beschikbaar als entityType *Proces* is. | 16840
ouderProcessCreationTime | Beschikbaar als entityType *Proces* is. | 2020-07-18T02:12:32.8616797Z
ipAdres | Beschikbaar als entityType *Ip* is. <br>IP-adres voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals *Communicatie naar een schadelijke netwerkbestemming*. | 62.216.203.204
url | Beschikbaar als entityType *url* is. <br>URL voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals *Communicatie naar een schadelijke netwerkbestemming*. | down.esales360.cn
accountNaam | Beschikbaar als entityType *gebruiker* is . | testUser2
domeinnaamName | Beschikbaar als entityType *gebruiker* is . | europa.corp.contoso
gebruikerSid | Beschikbaar als entityType *gebruiker* is . | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Beschikbaar als entityType *gebruiker* is . | fc8f7484-f813-4db2-afab-bc1507913fb6
gebruikerPrincipalName | Beschikbaar als entityType *User* / *MailBox* / *MailMessage* is . | testUser2@contoso.com
postvakDisplayName | Beschikbaar als entityType *MailBox* is. | test gebruiker2
mailboxAdres | Beschikbaar als entityType *User* / *MailBox* / *MailMessage* is . | testUser2@contoso.com
clusterDoor | Beschikbaar als entityType  *MailCluster* is . | Onderwerp; P2SenderDomein; InhoudType
afzender | Beschikbaar als entityType *User* / *MailBox* / *MailMessage* is . | user.abc@mail.contoso.co.in
ontvanger | Beschikbaar als entityType *MailMessage* is . | testUser2@contoso.com
Onderwerp | Beschikbaar als entityType *MailMessage* is . | \[EXTERNE \] aandacht
leveringActie | Beschikbaar als entityType *MailMessage* is . | Geleverd
beveiligingGroupId | Beschikbaar als entityType  *SecurityGroup* is. | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Beschikbaar als entityType  *SecurityGroup* is. | Netwerkconfiguratieoperators
registerHive | Beschikbaar als entityType  *Register* is. | HKEY \_ LOKALE \_ MACHINE |
registerSleutel | Beschikbaar als entityType  *Register* is. | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registerValueType | Beschikbaar als entityType  *Register* is. | Tekenreeks
registerWaarde | Beschikbaar als entityType  *Register* is. | 31-00-00-00
deviceId | De id, indien aanwezig, van het apparaat dat betrekking heeft op de entiteit. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Voorbeeld

**verzoek**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**antwoord**

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a>Verwante artikelen

- [Toegang tot de API's van Microsoft 365 Defender](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Foutcodes begrijpen](api-error-codes.md)
- [Overzicht incidenten](incidents-overview.md)
- [API's voor incidenten](api-incident.md)
- [Api voor incident bijwerken](api-update-incidents.md)
