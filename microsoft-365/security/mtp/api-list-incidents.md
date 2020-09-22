---
title: API voor lijst incidenten in Microsoft Threat Protection
description: Ontdek hoe u met API kunt vermelden in Microsoft Threat Protection
keywords: lijst, incident, incidenten, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 9defc9c0f8fa04e019c0108ca0f4111de54edb5f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195377"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a>API voor lijst incidenten in Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.


## <a name="api-description"></a>API-beschrijving

Met behulp van de incident-API kunt u sorteren op een weloverwogen Cyber Security-antwoord, zodat u deze kunt voorzien van een prioriteit. Dit maakt een verzameling van incidenten die zijn gemarkeerd vanaf apparaten, e-mailaccounts en gebruikers in uw netwerk, binnen de periode die u hebt opgegeven in het bewaarbeleid voor de omgeving. De meest recente incidenten worden bovenaan de lijst weergegeven. Elk incident bevat een matrix met gerelateerde waarschuwingen en de gerelateerde entiteiten.

<br>De API biedt ondersteuning voor de volgende **OData** -operatoren:
<br>```$filter``` op: ```lastUpdateTime``` , ```createdTime``` ```status``` en ```assignedTo``` Eigenschappen.
<br>```$top``` met de maximale waarde van **100**
<br>```$skip```

## <a name="limitations"></a>Beperkingen

1. Het maximale paginaformaat is **100 incidenten**.
2. Het maximale aantal aanvragen is **50 oproepen per minuut** en **1500-oproepen per uur**.

## <a name="permissions"></a>Machtigingen

U moet een van de volgende machtigingen hebben om deze API te kunnen bellen. Zie [Microsoft Threat Protection-Api's openen](api-access.md) voor meer informatie, waaronder de manier waarop u machtigingen kiest.

Type machtiging |   Machtigingsset  |   Weergavenaam van de machtiging
:---|:---|:---
Toepassing |   Incident. Read. all | ' Alle incidenten lezen '
Toepassing |   Incident. ReadWrite. all | ' Alle incidenten lezen en schrijven '
Gedelegeerd (werk-of schoolaccount) | Incident. Read | ' Lees incidenten '
Gedelegeerd (werk-of schoolaccount) | Incident. ReadWrite | ' Lees-en schrijf incident '

> [!Note]
> Bij het verkrijgen van een token met behulp van gebruikersreferenties:
> - De gebruiker moet de machtiging voor weergeven voor incidenten in de portal hebben.
> - Het antwoord bevat alleen incidenten waaraan de gebruiker is blootgesteld.

## <a name="http-request"></a>HTTP-aanvraag

```
GET /api/incidents
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Bevoegdheid | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Aanvraagtekst
Zonder.

## <a name="response"></a>Na
Als dit is gelukt, retourneert deze methode 200 OK en een lijst met [incidenten](api-incident.md) in de tekst van het antwoord.

## <a name="schema-mapping"></a>Schema toewijzingen

| Veld naam                                | Beschrijving                                                                                                                                                                                                                                                                                                                                                                                | Voorbeeldwaarde                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Metagegevens van incident**                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| incidentId                                | Unieke id die het incident voorstelt.                                                                                                                                                                                                                                                                                                                                                | 924565                                                                                                                                                                                                                                            |
| redirectIncidentId                        | Wordt alleen ingevuld wanneer een incident wordt gegroepeerd met een ander incident, als onderdeel van de logica voor het verwerken van incidenten.                                                                                                                                                                                                                                                           | 924569                                                                                                                                                                                                                                            |
| voorval                              | De tekenreekswaarde voor elk incident.                                                                                                                                                                                                                                                                                                                                                  | Ransomware-activiteit                                                                                                                                                                                                                               |
| createdTime                               | Tijdstip waarop het incident voor het eerst is gemaakt.                                                                                                                                                                                                                                                                                                                                                      | 2020-09-06T14:46:57.0733333 Z                                                                                                                                                                                                                      |
| lastUpdateTime                            | Tijdstip waarop het incident voor het laatst is bijgewerkt op de backend.<br> Dit veld kan worden gebruikt voor het instellen van de parameter Request voor het tijdsbereik dat incidenten worden opgehaald.                                                                                                                                                                                                                      | 2020-09-06T14:46:57.29 Z                                                                                                                                                                                                                           |
| ToegewezenAan                                | Eigenaar van het incident, of *Null* als er geen eigenaar wordt toegewezen.                                                                                                                                                                                                                                                                                                                         | secop2@contoso.com                                                                                                                                                                                                |
| Contactpersoonclassificatie                            | De specificatie van het incident. De eigenschapwaarden zijn: *onbekend*, *FalsePositive*, *TruePositive*                                                                                                                                                                                                                                                                           | Unknown                                                                                                                                                                                                                                           |
| relevant                             | Hiermee wordt het bepalen van het incident aangegeven. De eigenschapwaarden zijn: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Overig*                                                                                                                                                                                                                | NotAvailable                                                                                                                                                                                                                                      |
| status                                    | Incidenten categoriseren (als *actief*of *opgelost*). Hiermee kunt u uw antwoord op incidenten organiseren en beheren.                                                                                                                                                                                                                                                                  | Actief                                                                                                                                                                                                                                            |
| Ernst                                  | Geeft de mogelijke gevolgen voor activa aan. Hoe hoger de ernst, hoe groter de impact. Meestal hebt u de meest directe aandacht nodig voor hogere prioriteits items.<br>Een van de volgende waarden: *informatie*, *laag*, * medium en *hoog*.                                                                                                                                | Medium                                                                                                                                                                                                                                            |
| Tags                                      | Matrix van aangepaste labels die zijn gekoppeld aan een incident, bijvoorbeeld om een groep incidenten met een gemeenschappelijk kenmerk te markeren.                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| kennisgeving                                    | Matrix van alle meldingen met betrekking tot het incident en andere informatie, zoals Ernst, entiteiten die betrokken zijn bij de waarschuwing, de bron van de meldingen.                                                                                                                                                                                                                     | \[\] (Zie Details over waarschuwingsvelden hieronder)                                                                                                                                                                                                          |
| **Metagegevens van waarschuwingen**                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| alertId                                   | Unieke id die de waarschuwing voorstelt                                                                                                                                                                                                                                                                                                                                                   | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC                                                                                                                                                                                                            |
| incidentId                                | Unieke id waarmee het incident wordt aangegeven waaraan deze waarschuwing is gekoppeld                                                                                                                                                                                                                                                                                                                  | 924565                                                                                                                                                                                                                                            |
| serviceSource                             | Dienst waarvan de waarschuwing afkomstig is, zoals Microsoft Defender ATP, beveiliging van Microsoft Cloud-app, Azure ATP of Office 365 ATP.                                                                                                                                                                                                                                                                     | MicrosoftCloudAppSecurity                                                                                                                                                                                                                         |
| creationTime                              | Tijdstip waarop de waarschuwing voor het eerst is gemaakt.                                                                                                                                                                                                                                                                                                                                                         | 2020-09-06T14:46:55.7182276 Z                                                                                                                                                                                                                      |
| lastUpdatedTime                           | Tijdstip waarop de waarschuwing voor het laatst is bijgewerkt op de backend.                                                                                                                                                                                                                                                                                                                                           | 2020-09-06T14:46:57.2433333 Z                                                                                                                                                                                                                      |
| resolvedTime                              | Tijdstip waarop de waarschuwing is opgelost.                                                                                                                                                                                                                                                                                                                                                              | 2020-09-10T05:22:59Z                                                                                                                                                                                                                              |
| firstActivity                             | Tijd waarop de waarschuwing voor het eerst werd gerapporteerd dat de activiteit op de backend werd bijgewerkt.                                                                                                                                                                                                                                                                                                                             | 2020-09-04T05:22:59Z                                                                                                                                                                                                                              |
| begin                                     | Kort herkenbare identificatiewaarde voor elke waarschuwing.                                                                                                                                                                                                                                                                                                                                                     | Ransomware-activiteit                                                                                                                                                                                                                               |
| beschrijving                               | De tekenreekswaarde waarmee wordt gewaarschuwd.                                                                                                                                                                                                                                                                                                                                                        | De testUser2@contoso.com-bestanden () die zijn 99 bewerkt met een niet-gemeenschappelijke uitbreiding *herunterladen* Dit is een ongebruikelijk aantal bestandsbewerkingen en is een aanwijzing voor een potentiële aanval van Ransomware. |
| Categorie                                  | Visuele en numerieke weergave van de hoeveelheid aanval op de Kill-ketting. Uitgelijnd op de [Mitre ATT&a™ Framework](https://attack.mitre.org/).                                                                                                                                                                                                                           | Gevolg                                                                                                                                                                                                                                            |
| status                                    | Waarschuwingen categoriseren (als *Nieuw*, *actief*of *opgelost*) Hiermee kunt u uw antwoord op waarschuwingen organiseren en beheren.                                                                                                                                                                                                                                                                   | Nieuw                                                                                                                                                                                                                                               |
| Ernst                                  | Geeft de mogelijke gevolgen voor activa aan. Hoe hoger de ernst, hoe groter de impact. Meestal hebt u de meest directe aandacht nodig voor hogere prioriteits items.<br>Een van de volgende waarden: *informatie*, *laag*, * medium en *hoog*.                                                                                                                                   | Medium                                                                                                                                                                                                                                            |
| investigationId                           | De geautomatiseerde onderzoek-id die door deze melding wordt geactiveerd.                                                                                                                                                                                                                                                                                                                                | 1234                                                                                                                                                                                                                                              |
| investigationState                        | Informatie over de huidige status van het onderzoek. Een van de volgende: *onbekend*, *beëindigd*, *SuccessfullyRemediated*, *ongeluk, mislukt*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert.* *Benign* | UnsupportedAlertType                                                                                                                                                                                                                              |
| Contactpersoonclassificatie                            | De specificatie van het incident. De eigenschapwaarden zijn: *onbekend*, *FalsePositive*, *TruePositive* of *Null*                                                                                                                                                                                                                                                                   | Unknown                                                                                                                                                                                                                                           |
| relevant                             | Hiermee wordt het bepalen van het incident aangegeven. De eigenschapwaarden zijn: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* of  *Null*                                                                                                                                                                                                     | Apt                                                                                                                                                                                                                                               |
| ToegewezenAan                                | Eigenaar van het incident, of *Null* als er geen eigenaar wordt toegewezen.                                                                                                                                                                                                                                                                                                                            | secop2@contoso.com                                                                                                                                                                                                 |
| actor                                 | De groep activiteit, indien van toepassing, de koppeling met deze waarschuwing.                                                                                                                                                                                                                                                                                                                                        | EQUIVALENT                                                                                                                                                                                                                                             |
| threatFamilyName                          | Bedreigings familie van deze melding.                                                                                                                                                                                                                                                                                                                                                   | waarden                                                                                                                                                                                                                                              |
| mitreTechniques                           | De aantastings methoden, zoals afgestemd op de [Mitre ATT&a](https://attack.mitre.org/)™ Framework.                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| apparaten                                   | Alle apparaten waarop meldingen met betrekking tot het incident zijn verzonden.                                                                                                                                                                                                                                                                                                     | \[\] (Zie Details van de onderstaande entiteits velden)                                                                                                                                                                                                         |
| **Indeling van apparaat**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| DeviceId                                  | De apparaat-ID zoals aangegeven in Microsoft Defender ATP.                                                                                                                                                                                                                                                                                                                                                       | 24c222b0b60fe148eeece49ac83910cc6a7ef491                                                                                                                                                                                                          |
| aadDeviceId                               |  De apparaat-id zoals aangegeven in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (Aad). Alleen beschikbaar voor apparaten die lid zijn van een domein.                                                                                                                                                                                                                                                                                                                              | waarden                                                                                                                                                                                                                                              |
| deviceDnsName                             | De FQDN-naam (Fully Qualified Domain Name) voor het apparaat.                                                                                                                                                                                                                                                                                                                                                                        | user5cx.middleeast.corp.contoso.com                                                                                                                                                                                                    |
| osPlatform                                | Het OS-platform waarop het apparaat wordt uitgevoerd.                                                                                                                                                                                                                                                                                                                                                                     | WindowsServer2016                                                                                                                                                                                                                                 |
| osBuild                                   | De build-versie van het besturingssysteem dat het apparaat uitvoert.                                                                                                                                                                                                                                                                                                                                                                | 14393                                                                                                                                                                                                                                             |
| rbacGroupName                             | De groep [toegangsbeheer op basis van rollen](https://docs.microsoft.com/azure/role-based-access-control/overview) die is gekoppeld aan het apparaat.                                                                                                                                                                                                                                                                                                                             | WDATP-Ring0                                                                                                                                                                                                                                       |
| firstSeen                                 | Tijdstip waarop apparaat voor het eerst werd gezien.                                                                                                                                                                                                                                                                                                                                                           | 2020-02-06T14:16:01.9330135 Z                                                                                                                                                                                                                      |
| healthStatus                              | De status van het apparaat.                                                                                                                                                                                                                                                                                                                                                                        | Actief                                                                                                                                                                                                                                            |
| riskScore                                 | De risicoscore voor het apparaat.                                                                                                                                                                                                                                                                                                                                                                       | Hoog                                                                                                                                                                                                                                              |
| onderzoeksinstellingen                                  | Alle entiteiten die zijn geïdentificeerd om deel te nemen aan, of gerelateerd zijn aan een bepaalde melding.                                                                                                                                                                                                                                                                                | \[\] (Zie Details van de onderstaande entiteits velden)                                                                                                                                                                                                         |
| **Entiteits indeling**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| entityType                                | Entiteiten die zijn geïdentificeerd om deel te nemen aan een bepaalde melding, of betrekking hebben op een bepaalde melding.<br>De eigenschappen waarden zijn: *gebruiker*, *IP*, *URL*, *bestand*, *proces*, *Postvak*, *e-mailbericht, e-mail* *cluster*, *register*                                                                                                                                                                                                     | Gebruiker                                                                                                                                                                                                                                              |
| SHA1                                      | Beschikbaar als entityType een *bestand*is.<br>De bestands-hash voor waarschuwingen die zijn gekoppeld aan een bestand of proces.                                                                                                                                                                                                                                                                                    | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd                                                                                                                                                                                                          |
| sha256                                    | Beschikbaar als entityType een *bestand*is.<br>De bestands-hash voor waarschuwingen die zijn gekoppeld aan een bestand of proces.                                                                                                                                                                                                                                                                                    | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043                                                                                                                                                                                  |
| Namen                                  | Beschikbaar als entityType een *bestand*is.<br>De bestandsnaam van waarschuwingen die zijn gekoppeld aan een bestand of proces                                                                                                                                                                                                                                                                                    | Detector.UnitTests.dll                                                                                                                                                                                                                            |
| Bestandspad                                  | Beschikbaar als entityType een *bestand*is.<br>Het bestandspad voor waarschuwingen die zijn gekoppeld aan een bestand of proces                                                                                                                                                                                                                                                                                    | C: werk van de \\ \\ agent voor \\ \\ \_ \\ \\ \_ tijdelijke \\ \\ distributie van \_ systeem 2020-09-06 12 \_ 14 \_ 54 \\ \\ uit                                                                                                                                                                    |
| Proces                                 | Beschikbaar als entityType *proces*is.                                                                                                                                                                                                                                                                                                                                                     | 24348                                                                                                                                                                                                                                             |
| processCommandLine                        | Beschikbaar als entityType *proces*is.                                                                                                                                                                                                                                                                                                                                                     | " \\ " Het bestand kan worden gedownload \_1911150169.exe\\ ""                                                                                                                                                                                           |
| processCreationTime                       | Beschikbaar als entityType *proces*is.                                                                                                                                                                                                                                                                                                                                                     | 2020-7-18T03:25:38.5269993 Z                                                                                                                                                                                                                      |
| parentProcessId                           | Beschikbaar als entityType *proces*is.                                                                                                                                                                                                                                                                                                                                                   | 16840                                                                                                                                                                                                                                             |
| parentProcessCreationTime                 | Beschikbaar als entityType *proces*is.                                                                                                                                                                                                                                                                                                                                                     | 2020-7-18T02:12:32.8616797 Z                                                                                                                                                                                                                      |
| Adressen                                 | Beschikbaar als entityType een *IP-adres*is. <br>IP-adres voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals *communicatie met een kwaadaardige bestemming*.                                                                                                                                                                                                                                   | 62.216.203.204                                                                                                                                                                                                                                    |
| URL                                       | Beschikbaar als entityType de *URL*is. <br>URL voor meldingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals *communicatie met een kwaadaardige bestemming*.                                                                                                                                                                                                                                  | down.esales360.cn                                                                                                                                                                                                                                 |
| accountName                               | Beschikbaar als entityType een *gebruiker*is.                                                                                                                                                                                                                                                                                                                                                         | testUser2                                                                                                                                                                                                                                         |
| Domeinnaam                                | Beschikbaar als entityType een *gebruiker*is.                                                                                                                                                                                                                                                                                                                                                        | Europe. Corp. contoso                                                                                                                                                                                                                              |
| userSid                                   | Beschikbaar als entityType een *gebruiker*is.                                                                                                                                                                                                                                                                                                                                                        | S-1-5-21-1721254763-462695806-1538882281-4156657                                                                                                                                                                                                  |
| aadUserId                                 | Beschikbaar als entityType een *gebruiker*is.                                                                                                                                                                                                                                                                                                                                                        | fc8f7484-f813-4db2-afab-bc1507913fb6                                                                                                                                                                                                              |
| userPrincipalName                         | Beschikbaar als entityType de e-mail van het postvak van een *gebruiker*is / *MailBox* / *MailMessage*.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| mailboxDisplayName                        | Beschikbaar als entityType het *Postvak*is.                                                                                                                                                                                                                                                                                                                                                     | opmonsterset                                                                                                                                                                                                                                        |
| mailboxAddress                            | Beschikbaar als entityType de e-mail van het postvak van een *gebruiker*is / *MailBox* / *MailMessage*.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| clusterBy                                 | Beschikbaar als entityType een  *mailcluster*is.                                                                                                                                                                                                                                                                                                                                                 | Onderwerp P2SenderDomain; Invoer                                                                                                                                                                                                                |
| weet                                    | Beschikbaar als entityType de e-mail van het postvak van een *gebruiker*is / *MailBox* / *MailMessage*.                                                                                                                                                                                                                                                                                                                                  | user.abc@mail.contoso.co.in                                                                                                                                                                 |
| faxontvanger                                 | Beschikbaar als entityType een *e-mailbericht*is.                                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                       |
| Onderwerp                                   | Beschikbaar als entityType een *e-mailbericht*is.                                                                                                                                                                                                                                                                                                                                                 | \[EXTERNE \] aandacht                                                                                                                                                                                                                            |
| deliveryAction                            | Beschikbaar als entityType een *e-mailbericht*is.                                                                                                                                                                                                                                                                                                                                                 | Aflevering                                                                                                                                                                                                                                         |
| securityGroupId                           | Beschikbaar als entityType  *SecurityGroup*is.                                                                                                                                                                                                                                                                                                                                               | 301c47c8-e15f-4059-AB09-e2ba9ffd372b                                                                                                                                                                                                              |
| securityGroupName                         | Beschikbaar als entityType  *SecurityGroup*is.                                                                                                                                                                                                                                                                                                                                               | Netwerkconfiguratieoperators                                                                                                                                                                                                                   |
| registryHive                              | Beschikbaar als entityType de  *registersleutel*is.                                                                                                                                                                                                                                                                                                                                                    | \_lokale \_ machine van HKEY                                                                                                                                                                                                                              |
| registryKey                               | Beschikbaar als entityType de  *registersleutel*is.                                                                                                                                                                                                                                                                                                                                                     | SOFTWARE \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon                                                                                                                                                                                 |
| registryValueType                         | Beschikbaar als entityType de  *registersleutel*is.                                                                                                                                                                                                                                                                                                                                                    | Tekenreeks                                                                                                                                                                                                                                            |
| registryValue                             | Beschikbaar als entityType de  *registersleutel*is.                                                                                                                                                                                                                                                                                                                                                    | 31-00-00-00                                                                                                                                                                                                                                       |
| deviceId                                  | De ID, indien van toepassing, van het apparaat dat is gekoppeld aan de entiteit.                                                                                                                                                                                                                                                                                                                                           | 986e5df8b73dacd43c8917d17e523e76b13c75cd                                                                                                                                                                                                          |



## <a name="example"></a>Voorbeeld

**Webonderdeelverzoek**

```
GET https://api.security.microsoft.com/api/incidents
```

**Na**
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

## <a name="related-topic"></a>Verwante onderwerpen
- [API's voor incidenten](api-incident.md)
- [Incident bijwerken](api-update-incidents.md)
