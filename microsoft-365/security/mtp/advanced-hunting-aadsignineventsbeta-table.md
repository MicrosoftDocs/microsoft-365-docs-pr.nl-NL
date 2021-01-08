---
title: AADSignInEventsBeta-tabel in het geavanceerde jacht schema
description: Meer informatie over informatie die is gekoppeld aan de tabel aanmeld gebeurtenissen van Azure Active Directory van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber bedreigings jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema Reference, kusto, tabel, bestand, gegevenstype, beschrijving, bestand, IP-adres, apparaat, computer, gebruiker, account, identiteit, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 1830eeec674c4948bd6492780ef8a0a8039111b8
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784285"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Van toepassing op:**

- Microsoft 365 Defender

>[!IMPORTANT]
> De `AADSignInEventsBeta` tabel bevindt zich momenteel in bèta en wordt kort weer geboden, zodat u zich kunt aanmelden via Azure Active Directory (Aad) aanmeld gebeurtenissen. We zullen uiteindelijk alle gegevens van het aanmeldings schema naar de `IdentityLogonEvents` tabel verplaatsen.<br><br>
> Klanten die de Microsoft 365-app hebben geopend via de geïntegreerde Microsoft-app voor eindpunten van het Azure-Beveiligingscentrum, maar geen licenties voor Microsoft Defender for Office, Microsoft Defender for Identity, of Microsoft Cloud app Security, kunnen dit schema niet weergeven. 

 

De `AADSignInEventsBeta` tabel in het geavanceerde jacht-schema bevat informatie over Azure Active Directory Interactive en niet-interactieve aanmeldinformatie. Meer informatie over registraties in [Azure Active Directory-aanmeldings activiteitenrapporten-preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.
Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)zoeken.

 

 

| Kolomnaam                 | Gegevenstype | Beschrijving          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | tijd      | De datum en tijd waarop de record is gegenereerd                                                                                                                                         |
| `Application`                     | tekenreeks        | De toepassing die de opgenomen actie heeft uitgevoerd                                                                                                                                       |
| `ApplicationId`                   | tekenreeks        | Unieke id voor de toepassing                                                                                                                                               |
| `LogonType`                       | tekenreeks        | Type aanmeldingssessie, met name Interactive, Remote Interactive (RDP), netwerk, batch en service                                                                              |
| `ErrorCode`                       | int        | Bevat de foutcode als een aanmeldingsfout optreedt. Ga naar voor een beschrijving van een bepaalde foutcode <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | tekenreeks        | Unieke id van de aanmeld gebeurtenis                                                                                                                                              |
| `SessionId`                       | tekenreeks        | Unieke nummer dat is toegewezen aan een gebruiker op de server van een website gedurende de periode van het bezoek of de sessie                                                                                     |
| `AccountDisplayName`              | tekenreeks        | Naam van de account gebruiker die in het adresboek wordt weergegeven. Meestal een combinatie van een bepaalde of voornaam, een tweede initiaal en een achternaam of achternaam.                             |
| `AccountObjectId`                 | tekenreeks        | Unieke id voor het account in azure AD                                                                                                                                       |
| `AccountUpn`                      | tekenreeks        | UPN (User Principal Name) van het account                                                                                                                                            |
| `IsExternalUser`                  | int        | Geeft aan of de gebruiker van wie de aanmelding extern is. Mogelijke waarden:-1 (niet ingesteld), 0 (niet extern), 1 (extern).                                                                   |
| `IsGuestUser`                     | Boolean       | Geeft aan of de gebruiker die zich heeft aangemeld, een gast in de Tenant is                                                                                                                  |
| `AlternateSignInName`             | tekenreeks        | Lokale UPN (User Principal Name) van de gebruiker die zich aanmeldt bij Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | tijd        | Datum en tijd wanneer de gebruiker die zich het laatst heeft aangemeld hun wachtwoord heeft gewijzigd                                                                                                              |
| `ResourceDisplayName`             | tekenreeks        | De weergavenaam van de resource die wordt geopend                                                                                                                                               |
| `ResourceId`                      | tekenreeks        | Unieke id van de geopente resource                                                                                                                                          |
| `ResourceTenantId`                | tekenreeks        | Unieke id van de Tenant van de geopente bron                                                                                                                            |
| `DeviceName`                      | tekenreeks        | FQDN-naam (Fully Qualified Domain Name) van de computer                                                                                                                                   |
| `AadDeviceId`                     | tekenreeks   |      Unieke id voor het apparaat in azure AD                                                                                                                                                                               |
| `OSPlatform`                      | tekenreeks        | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, met inbegrip van variaties in dezelfde familie, zoals Windows 10 en Windows 7.  |
| `DeviceTrustType`                 | tekenreeks        | Hiermee wordt het type vertrouwen aangegeven van het apparaat dat zich heeft aangemeld. Alleen voor scenario's met een beheerd apparaat. Mogelijke waarden zijn Workplace, AzureAd en ServerAd.                                     |
| `IsManaged`                       | int       | Geeft aan of het apparaat dat de aanmelding heeft gestart, een beheerd apparaat (1) is of geen beheerd apparaat (0)                                                                         |
| `IsCompliant`                     | int       | Geeft aan of het apparaat dat de aanmelding heeft gestart, compatibel is (1) of niet-compatibel (0) is.                                                                                       |
| `AuthenticationProcessingDetails` | tekenreeks        | Details van de verificatie processor                                                                                                                                          |
| `AuthenticationRequirement`       | tekenreeks        | Type verificatie vereist voor de aanmelding. Mogelijke waarden: multiFactorAuthentication (MFA is vereist) en singleFactorAuthentication (geen MFA vereist).                |
| `TokenIssuerType`                 | int        | Geeft aan of de verleners van het token Azure Active Directory (0) of Active Directory Federation Services (1) is.                                                                             |
| `RiskLevelAggregated`                       | int        | Samengeteld risiconiveau tijdens aanmelding. Mogelijke waarden: 0 (samengevoegd risiconiveau niet ingesteld), 1 (geen), 10 (laag), 50 (normaal) of 100 (hoog).                               |
| `RiskDetails`                      | int        | Details van de riskante status van de gebruiker die zich heeft aangemeld                                                                                                                            |
| `RiskState`                       | int        | Geeft risicovolle gebruikersstatus aan. Mogelijke waarden: 0 (geen), 1 (bevestigd veilig), 2 (hersteld), 3 (genegeerd), 4 (risico) of 5 (bevestigde gerisicode).                                |
| `UserAgent`                       | tekenreeks        | Gegevens van de gebruikersagent van de webbrowser of een andere clienttoepassing                                                                                                             |
| `ClientAppUsed`                   | tekenreeks        | Geeft de gebruikte client-app aan.                                                                                                                                                       |
| `Browser`                         | tekenreeks        | Details over de versie van de browser waarmee u zich aanmeldt                                                                                                                            |
| `ConditionalAccessPolicies`       | tekenreeks        | Details van het beleid voor voorwaardelijke toegang dat is toegepast op de aanmeld gebeurtenis                                                                                                             |
| `ConditionalAccessStatus`         | int        | De status van het beleid voor voorwaardelijke toegang dat is toegepast op de aanmelding. Mogelijke waarden zijn 0 (beleidsregels van toepassing), 1 (beleidsregels voor het toepassen van een beleid mislukt) of 2 (beleidsregels niet toegepast).      |
| `IPAddress`                       | tekenreeks        | Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie                                                                                                  |
| `CountryCode`                     | tekenreeks        | Tweeletterige code die het land aangeeft waarin het IP-adres van de client geolocatie is                                                                                                    |
| `State`                           | tekenreeks        | De status van de aanmelding, indien beschikbaar                                                                                                                                      |
| `City`                            | tekenreeks        | Plaats waar de account gebruiker zich bevindt                                                                                                                                              |
| `Latitude`                        | tekenreeks        | De Noord-to-Zuid-coördinaten van de aanmeldingslocatie                                                                                                                              |
| `Longitude`                       | tekenreeks        | De Oost-en West-coördinaten van de aanmeldingslocatie                                                                                                                                |
| `NetworkLocationDetails`          | tekenreeks        | Netwerklocatie Details van de verificatie processor van de aanmeld gebeurtenis                                                                                                       |
| `RequestId`                       | tekenreeks        |  Unieke id van de aanvraag                                                                                                                                                   |
|`ReportId` | tekenreeks | Unieke id voor de gebeurtenis |

 

 

## <a name="related-articles"></a>Verwante artikelen

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [Overzicht van geavanceerd opsporen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [De querytaal leren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Meer informatie over het schema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
