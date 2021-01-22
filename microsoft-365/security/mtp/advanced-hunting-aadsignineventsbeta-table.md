---
title: AADSignInEventsBeta-tabel in het geavanceerde schema voor zoeken
description: Meer informatie over de gegevens die zijn gekoppeld aan de tabel met aanmeldingsgebeurtenissen van Azure Active Directory van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, file, IP address, device, machine, user, account, identity, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: b574717d0ba5621d85c8e73f36ddc72b062a1494
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931036"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Van toepassing op:**

- Microsoft 365 Defender

>[!IMPORTANT]
> De tabel is momenteel beschikbaar als bètaversie en wordt op korte termijn aangeboden zodat u kunt zoeken in `AADSignInEventsBeta` Azure Active Directory (AAD) aanmeldingsgebeurtenissen. Uiteindelijk worden alle gegevens van het aanmeldingsschema naar de tabel `IdentityLogonEvents` verplaatst.<br><br>
> Klanten die toegang hebben tot Microsoft 365 Defender via de geïntegreerde oplossing microsoft Defender for Endpoint van het Azure-beveiligingscentrum, maar geen licenties hebben voor Microsoft Defender voor Office, Microsoft Defender voor identiteit of Microsoft Cloud App-beveiliging, kunnen dit schema niet bekijken. 

 

De `AADSignInEventsBeta` tabel in het geavanceerde zoekschema bevat informatie over interactieve en niet-interactieve Azure Active Directory-aanmeldingen. Meer informatie over aanmeldingen in [Azure Active Directory-rapporten met aanmeldactiviteiten - preview.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.
Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)

 

 

| Kolomnaam                 | Gegevenstype | Beschrijving          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Datum en tijd waarop de record is gegenereerd                                                                                                                                         |
| `Application`                     | tekenreeks        | Toepassing die de opgenomen actie heeft uitgevoerd                                                                                                                                       |
| `ApplicationId`                   | tekenreeks        | Unieke id voor de toepassing                                                                                                                                               |
| `LogonType`                       | tekenreeks        | Type aanmeldingssessie, speciaal interactief, extern interactief (RDP), netwerk, batch en service                                                                              |
| `ErrorCode`                       | int        | Bevat de foutcode als er een aanmeldingsfout optreedt. Als u een beschrijving van een specifieke foutcode wilt vinden, gaat u naar <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | tekenreeks        | Unieke id van de aanmeldingsgebeurtenis                                                                                                                                              |
| `SessionId`                       | tekenreeks        | Een uniek nummer dat aan een gebruiker is toegewezen door de server van een website gedurende de duur van het bezoek of de sessie                                                                                     |
| `AccountDisplayName`              | tekenreeks        | De naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste initiitie en een achternaam of achternaam.                             |
| `AccountObjectId`                 | tekenreeks        | Unieke id voor het account in Azure AD                                                                                                                                       |
| `AccountUpn`                      | tekenreeks        | UPN (User Principal Name) van het account                                                                                                                                            |
| `IsExternalUser`                  | int        | Hiermee wordt aangegeven of de gebruiker die zich heeft aangemeld extern is. Mogelijke waarden: -1 (niet ingesteld), 0 (niet extern), 1 (extern).                                                                   |
| `IsGuestUser`                     | boolean       | Geeft aan of de gebruiker die zich heeft aangemeld een gast is in de tenant                                                                                                                  |
| `AlternateSignInName`             | tekenreeks        | UPN (On-premises User Principal Name) van de gebruiker die zich aanmeldt bij Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Datum en tijd waarop de gebruiker die zich het laatst heeft aangemeld zijn of haar wachtwoord heeft gewijzigd                                                                                                              |
| `ResourceDisplayName`             | tekenreeks        | Weergavenaam van de bron die is gebruikt                                                                                                                                               |
| `ResourceId`                      | tekenreeks        | Unieke id van de bron die wordt gebruikt                                                                                                                                          |
| `ResourceTenantId`                | tekenreeks        | Unieke id van de tenant van de bron die is gebruikt                                                                                                                            |
| `DeviceName`                      | tekenreeks        | FQDN (Fully Qualified Domain Name) van de computer                                                                                                                                   |
| `AadDeviceId`                     | tekenreeks   |      Unieke id voor het apparaat in Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | tekenreeks        | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.  |
| `DeviceTrustType`                 | tekenreeks        | Geeft het vertrouwenstype aan van het apparaat dat zich heeft aangemeld. Alleen voor beheerde apparaatscenario's. Mogelijke waarden zijn Workplace, AzureAd en ServerAd.                                     |
| `IsManaged`                       | int       | Geeft aan of het apparaat dat de aanmelding is gestart een beheerd apparaat (1) is of geen beheerd apparaat (0)                                                                         |
| `IsCompliant`                     | int       | Hiermee wordt aangegeven of het apparaat dat de aanmelding is gestart compatibel is (1) of niet voldoet (0).                                                                                       |
| `AuthenticationProcessingDetails` | tekenreeks        | Details over de verificatieverwerker                                                                                                                                          |
| `AuthenticationRequirement`       | tekenreeks        | Het type verificatie dat vereist is voor de aanmelding. Mogelijke waarden: multiFactorAuthentication (MFA was vereist) en singleFactorAuthentication (er was geen MFA vereist).                |
| `TokenIssuerType`                 | int        | Hiermee wordt aangegeven of de tokenuitgever Azure Active Directory (0) of Active Directory Federation Services (1) is.                                                                             |
| `RiskLevelAggregated`                       | int        | Geaggregeerd risiconiveau tijdens het aanmelden. Mogelijke waarden: 0 (geaggregeerd risiconiveau niet ingesteld), 1 (geen), 10 (laag), 50 (gemiddeld) of 100 (hoog).                               |
| `RiskDetails`                      | int        | Details over de risicotoestand van de gebruiker die zich heeft aangemeld                                                                                                                            |
| `RiskState`                       | int        | Geeft risicovolle gebruikerstoestand aan. Mogelijke waarden: 0 (geen), 1 (veilig bevestigd), 2 (opgelost), 3 (gesloten), 4 (risico loopt) of 5 (bevestigd).                                |
| `UserAgent`                       | tekenreeks        | Gegevens van de gebruikersagent vanuit de webbrowser of een andere clienttoepassing                                                                                                             |
| `ClientAppUsed`                   | tekenreeks        | Geeft de gebruikte client-app aan                                                                                                                                                       |
| `Browser`                         | tekenreeks        | Meer informatie over de versie van de browser waarmee u zich heeft aanmelden                                                                                                                            |
| `ConditionalAccessPolicies`       | tekenreeks        | Details van het beleid voor voorwaardelijke toegang dat is toegepast op de aanmeldingsgebeurtenis                                                                                                             |
| `ConditionalAccessStatus`         | int        | Status van het beleid voor voorwaardelijke toegang dat op de aanmelding is toegepast. Mogelijke waarden zijn 0 (beleid dat is toegepast), 1 (poging om beleid toe te passen is mislukt) of 2 (beleid dat niet is toegepast).      |
| `IPAddress`                       | tekenreeks        | IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie                                                                                                  |
| `CountryCode`                     | tekenreeks        | Tweeletterige code die het land aangeeft waar het IP-adres van de client geo-toegewezen is                                                                                                    |
| `State`                           | tekenreeks        | Provincie waar de aanmelding heeft plaatsgevonden, indien beschikbaar                                                                                                                                      |
| `City`                            | tekenreeks        | Plaats waar de accountgebruiker zich bevindt                                                                                                                                              |
| `Latitude`                        | tekenreeks        | De coördinaten van de aanmeldingslocatie van Noord naar Zuid                                                                                                                              |
| `Longitude`                       | tekenreeks        | De coördinaten van Oost naar West van de aanmeldingslocatie                                                                                                                                |
| `NetworkLocationDetails`          | tekenreeks        | Netwerklocatiedetails van de verificatieverwerker van de aanmeldingsgebeurtenis                                                                                                       |
| `RequestId`                       | tekenreeks        |  Unieke id van de aanvraag                                                                                                                                                   |
|`ReportId` | tekenreeks | Unieke id voor de gebeurtenis |

 

 

## <a name="related-articles"></a>Verwante artikelen

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [Overzicht van geavanceerd opsporen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [De querytaal leren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Meer informatie over het schema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
