---
title: Api voor lijstincidenten in Microsoft 365 Defender
description: Informatie over het op een lijst zetten van incidenten API in Microsoft 365 Defender
keywords: list, incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 39a170a1845ab33f67d77b2de3d5f298f67fdc99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932068"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Api voor lijstincidenten in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.


## <a name="api-description"></a>API-beschrijving

Met de API voor lijstincidenten kunt u incidenten sorteren om een weloverwogen reactie te krijgen. Er wordt een verzameling incidenten beschreven die in uw netwerk zijn gemarkeerd binnen het tijdsbereik dat u hebt opgegeven in het bewaarbeleid voor omgevingen. De meest recente incidenten worden boven aan de lijst weergegeven. Elk incident bevat een matrix met gerelateerde waarschuwingen en de bijbehorende entiteiten.

De API ondersteunt de volgende **OData-operators:**

- `$filter`in de `lastUpdateTime` `createdTime` eigenschappen , `status` en `assignedTo`
- `$top`, met een maximumwaarde van **100**
- `$skip`

## <a name="limitations"></a>Beperkingen

1. Het maximale paginaformaat is **100 incidenten.**
2. Het maximale aantal aanvragen is **50 oproepen per minuut** en **1500 oproepen per uur.**

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API aan te roepen. Zie [Access Microsoft 365 Defender API's (Access Microsoft 365 Defender-API's)](api-access.md) voor meer informatie, waaronder het kiezen van machtigingen.

Machtigingstype | Machtiging | Weergavenaam van machtiging
-|-|-
Toepassing | Incident.Read.All | Alle incidenten lezen
Toepassing | Incident.ReadWrite.All | Alle incidenten lezen en schrijven
Gedelegeerd (werk- of schoolaccount) | Incident.Read | Incidenten lezen
Gedelegeerd (werk- of schoolaccount) | Incident.ReadWrite | Incidenten lezen en schrijven

> [!Note]
> Wanneer u een token verkrijgt met behulp van gebruikersreferenties:
>
> - De gebruiker moet weergavemachtigingen hebben voor incidenten in de portal.
> - De reactie omvat alleen incidenten die de gebruiker te zien krijgt.

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Berichtkoppen aanvragen

Naam | Type | Beschrijving
-|-|-
Autorisatie | Tekenreeks | Beller {token}. **Vereist**


## <a name="request-body"></a>Aanvraag in de eerste instantie

Geen.

## <a name="response"></a>Antwoord

Als dit is gelukt, worden met deze methode de incidenten in de antwoord zelf `200 OK` weergegeven. [](api-incident.md)

## <a name="schema-mapping"></a>Schematoewijzing

### <a name="incident-metadata"></a>Metagegevens voor incidenten

Veldnaam | Beschrijving | Voorbeeldwaarde
-|-|-
incidentId | Unieke id die het incident vertegenwoordigt | 924565
redirectIncidentId | Alleen ingevuld voor het geval een incident wordt gegroepeerd met een ander incident, als onderdeel van de incidentverwerkingslogica. | 924569
incidentName | De waarde van de tekenreeks die beschikbaar is voor elk incident. | Ransomware-activiteit
createdTime | Tijdstip waarop het incident voor het eerst is gemaakt. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Het tijdstip waarop het incident voor het laatst is bijgewerkt op de back-back<br /><br /> Dit veld kan worden gebruikt wanneer u de parameter Aanvraag instelt voor het tijdsbereik waarin incidenten worden opgehaald. | 2020-09-06T14:46:57.29Z
toegewezen Aan | Eigenaar van het incident of *null* als er geen eigenaar is toegewezen. | secop2@contoso.com
classificatie | De specificatie voor het incident. De eigenschapswaarden *zijn: Onbekend,* *FalsePositive,* *TruePositive* | Unknown
besluit | Bepaalt de vaststelling van het incident. De eigenschapswaarden zijn: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other* | Niet beschikbaar
status | Incidenten categoriseren (als *Actief* of *Opgelost).* Het kan u helpen uw reacties op incidenten te ordenen en te beheren. | Actief
ernst | Geeft de mogelijke invloed op activa aan. Hoe hoger de ernst, hoe groter de impact. Items met een hogere ernst vereisen meestal de meest directe aandacht.<br /><br />Een van de volgende waarden: *Informatief,* *Laag,**Normaal en *Hoog.* | Gemiddeld
tags | Matrix van aangepaste tags die betrekking hebben op een incident, bijvoorbeeld om een groep incidenten met een gemeenschappelijke kenmerken te markeren. | \[\]
waarschuwingen | Matrix met alle waarschuwingen die betrekking hebben op het incident, plus andere informatie, zoals ernst, entiteiten die zijn betrokken bij de waarschuwing en de bron van de waarschuwingen. | \[\] (zie de details van waarschuwingsvelden hieronder)

### <a name="alerts-metadata"></a>Metagegevens waarschuwingen

Veldnaam | Beschrijving | Voorbeeldwaarde
-|-|-
alertId | Unieke id die de waarschuwing vertegenwoordigt | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | Unieke id die het incident vertegenwoordigt dat aan deze waarschuwing is gekoppeld | 924565
serviceSource | Service waar de waarschuwing van afkomstig is, zoals Microsoft Defender voor eindpunt, Microsoft Cloud App-beveiliging, Microsoft Defender voor identiteit of Microsoft Defender voor Office 365. | MicrosoftCloudAppSecurity
creationTime | Het tijdstip waarop de waarschuwing voor het eerst is gemaakt. | 2020-09-06T14:46:55.7182276Z
lastUpdatedTime | Het tijdstip waarop de waarschuwing voor het laatst is bijgewerkt bij de back-back | 2020-09-06T14:46:57.2433333Z
resolvedTime | Het tijdstip waarop de waarschuwing is opgelost. | 2020-09-10T05:22:59Z
firstActivity | Het tijdstip waarop de waarschuwing de eerste keer heeft gerapporteerd dat de activiteit is bijgewerkt op de back-back-backend.| 2020-09-04T05:22:59Z
titel | Kort de waarde die beschikbaar is voor elke waarschuwing. | Ransomware-activiteit
beschrijving | De waarde van de tekenreeks die elke waarschuwing beschrijft. | De gebruiker test gebruiker2 (testUser2@contoso.com) manipuleerde 99 bestanden met meerdere extensies die eindigt op de ongebruikelijke extensie *herunter laden.* Dit is een ongebruikelijk aantal bestandsmanipulaties en wordt beïnvloed door een mogelijke aanval van ransomware.
categorie | Visuele en numerieke weergave van hoe ver de aanval is gegaan langs de kill chain. Afgestemd op de [MITRE ATT&CK™ framework.](https://attack.mitre.org/) | Gevolg
status | Waarschuwingen categoriseren *(als Nieuw,* *Actief* *of Opgelost).* Het kan u helpen bij het organiseren en beheren van uw reactie op waarschuwingen. | Nieuw
ernst | Geeft de mogelijke invloed op activa aan. Hoe hoger de ernst, hoe groter de impact. Items met een hogere ernst vereisen meestal de meest directe aandacht.<br>Een van de volgende waarden: *Informatief,* *Laag,**Normaal en *Hoog.* | Gemiddeld
investigationId | De automatische onderzoeks-id die is geactiveerd door deze waarschuwing. | 1234
investigationState | Informatie over de huidige status van het onderzoek. Een van de volgende waarden: *Unknown,* *Terminated*, *SuccessfullyRemediated,* *Benign,* *Failed,* *PartiallyRemediated,* *Running*, *PendingApproval,* *PendingResource,* *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*. | UnsupportedAlertType
classificatie | De specificatie voor het incident. De eigenschapswaarden *zijn: Onbekend,* *FalsePositive,* *TruePositive* of *null* | Unknown
besluit | Bepaalt de vaststelling van het incident. De eigenschapswaarden zijn: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other* of  *null* | Pt
toegewezen Aan | Eigenaar van het incident of *null* als er geen eigenaar is toegewezen. | secop2@contoso.com
actorName | De activiteitengroep, indien van gebruik, die is gekoppeld aan deze waarschuwing. | BORON
threatFamilyName | Bedreigingsfamilie gekoppeld aan deze waarschuwing. | null
mitreTechniques | De technieken voor aanvallen, die zijn uitgelijnd met de [MITRE ATT&CK](https://attack.mitre.org/)™ framework. | \[\]
apparaten | Alle apparaten waarop waarschuwingen met betrekking tot het incident zijn verzonden. | \[\] (zie de details van entiteitsvelden hieronder)

### <a name="device-format"></a>Apparaatindeling

Veldnaam | Beschrijving | Voorbeeldwaarde
-|-|-
DeviceId | De apparaat-id zoals aangegeven in Microsoft Defender ATP. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  De apparaat-id zoals aangegeven in [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) Alleen beschikbaar voor apparaten die lid zijn van een domein. | null
deviceDnsName | De volledig gekwalificeerde domeinnaam voor het apparaat. | user5cx.middleeast.corp.contoso.com
osPlatform | Het besturingssysteemplatform waarop het apparaat wordt uitgevoerd.| WindowsServer2016
osBuild | De buildversie van het besturingssysteem dat op het apparaat wordt uitgevoerd. | 14393
rbacGroupName | De [groep toegangsbeheer](https://docs.microsoft.com/azure/role-based-access-control/overview) op basis van rollen die aan het apparaat is gekoppeld. | WDATP-Ring0
firstSeen | Het tijdstip waarop het apparaat voor het eerst werd gezien. | 2020-02-06T14:16:01.9330135Z
statusstatus | De status van het apparaat. | Actief
riskScore | De risicoscore voor het apparaat. | Hoog
entiteiten | Alle entiteiten die zijn geïdentificeerd als onderdeel van, of gerelateerd aan, een bepaalde waarschuwing. | \[\] (zie de details van entiteitsvelden hieronder)

### <a name="entity-format"></a>Entiteitsindeling

Veldnaam | Beschrijving | Voorbeeldwaarde
-|-|-
entityType | Entiteiten die zijn geïdentificeerd als onderdeel van of gerelateerd aan een bepaalde waarschuwing.<br>De eigenschappenwaarden zijn: *Gebruiker*, *IP*, *URL*, *Bestand*, *Proces*, *MailBox*, *MailMessage*, *MailCluster*, *Registry* | Gebruiker
sha1 | Beschikbaar als entityType *Bestand* is.<br>De bestandshash voor waarschuwingen die zijn gekoppeld aan een bestand of proces. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Beschikbaar als entityType *Bestand* is.<br>De bestandshash voor waarschuwingen die zijn gekoppeld aan een bestand of proces. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName | Beschikbaar als entityType *Bestand* is.<br>De bestandsnaam voor waarschuwingen die zijn gekoppeld aan een bestand of proces | Detector.UnitTests.dll
filePath | Beschikbaar als entityType *Bestand* is.<br>Het bestandspad voor waarschuwingen die aan een bestand of proces zijn gekoppeld | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId | Beschikbaar als entityType *Process* is. | 24348
processCommandLine | Beschikbaar als entityType *Process* is. | "Your File is ready to Download \_1911150169.exe"
processCreationTime | Beschikbaar als entityType *Process* is. | 2020-07-18T03:25:38.5269993Z
parentProcessId | Beschikbaar als entityType *Process* is. | 16840
parentProcessCreationTime | Beschikbaar als entityType *Process* is. | 2020-07-18T02:12:32.8616797Z
ipAddress | Beschikbaar als entityType *Ip* is. <br>HET IP-adres voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals Communicatie *met een schadelijk netwerkdoel.* | 62.216.203.204
url | Beschikbaar als entityType *URL* is. <br>Url voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals Communicatie *met een schadelijk netwerkdoel.* | down.esales360.cn
accountName | Beschikbaar als entityType *Gebruiker* is. | testUser2
domainName | Beschikbaar als entityType *Gebruiker* is. | europe.corp.contoso
userSid | Beschikbaar als entityType *Gebruiker* is. | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Beschikbaar als entityType *Gebruiker* is. | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Beschikbaar als entityType *User* / *MailBox* / *MailMessage is.* | testUser2@contoso.com
mailboxDisplayName | Beschikbaar als entityType *MailBox* is. | gebruiker2 testen
mailboxAddress | Beschikbaar als entityType *User* / *MailBox* / *MailMessage is.* | testUser2@contoso.com
clusterBy | Beschikbaar als entityType  *MailCluster* is. | Onderwerp; P2SenderDomain; ContentType
afzender | Beschikbaar als entityType *User* / *MailBox* / *MailMessage is.* | user.abc@mail.contoso.co.in
geadresseerde | Beschikbaar als entityType *MailMessage* is. | testUser2@contoso.com
Onderwerp | Beschikbaar als entityType *MailMessage* is. | \[EXTERNE \] aandacht
deliveryAction | Beschikbaar als entityType *MailMessage* is. | Geleverd
securityGroupId | Beschikbaar als entityType  *SecurityGroup* is. | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Beschikbaar als entityType  *SecurityGroup* is. | Netwerkconfiguratieoperatoren
registryHive | Beschikbaar als entityType het  *register* is. | LOKALE \_ \_ HKEY-COMPUTER |
registryKey | Beschikbaar als entityType het  *register* is. | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType | Beschikbaar als entityType het  *register* is. | Tekenreeks
registryValue | Beschikbaar als entityType het  *register* is. | 31-00-00-00
deviceId | De id van het apparaat dat is gerelateerd aan de entiteit. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Voorbeeld

**Aanvraag**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**Antwoord**

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

- [Toegang tot de Microsoft 365 Defender-API's](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Meer te weten komen over foutcodes](api-error-codes.md)
- [Overzicht van incidenten](incidents-overview.md)
- [API's voor incidenten](api-incident.md)
- [Update-incident-API](api-update-incidents.md)
