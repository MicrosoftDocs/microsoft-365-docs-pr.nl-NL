---
title: AADSignInEventsBeta-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over informatie die is gekoppeld aan azure Active Directory-aanmeldingsgebeurtenissentabel van het geavanceerde schema voor de jacht
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
ms.openlocfilehash: 50f112f6e7198136171d070dc483ad5f84d20d57
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925760"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Van toepassing op:**

- Microsoft 365 Defender

>[!IMPORTANT]
> De tabel is momenteel in bètaversie en wordt op korte termijn aangeboden, zodat u kunt zoeken op aanmeldingsgebeurtenissen van `AADSignInEventsBeta` Azure Active Directory (AAD). Uiteindelijk worden alle aanmeldingsschemagegevens naar de tabel `IdentityLogonEvents` verplaatst.<br><br>
> Klanten die toegang hebben tot Microsoft 365 Defender via de geïntegreerde Microsoft Defender voor Eindpunt-oplossing van het Azure Security Center, maar geen licenties hebben voor Microsoft Defender voor Office, Microsoft Defender voor identiteit of Microsoft Cloud App Security, kunnen dit schema niet bekijken. 

 

De `AADSignInEventsBeta` tabel in het geavanceerde schema bevat informatie over interactieve en niet-interactieve aanmeldingen van Azure Active Directory. Meer informatie over aanmeldingen in [Azure Active Directory-aanmeldingsactiviteitsrapporten - preview.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.
Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)

 

 

| Kolomnaam                 | Gegevenstype | Beschrijving          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | Datum en tijd waarop de record is gegenereerd                                                                                                                                         |
| `Application`                     | tekenreeks        | Toepassing die de opgenomen actie heeft uitgevoerd                                                                                                                                       |
| `ApplicationId`                   | tekenreeks        | Unieke id voor de toepassing                                                                                                                                               |
| `LogonType`                       | tekenreeks        | Type aanmeldingssessie, specifiek interactief, extern interactief (RDP), netwerk, batch en service                                                                              |
| `ErrorCode`                       | int        | Bevat de foutcode als er een aanmeldingsfout optreedt. Als u een beschrijving van een specifieke foutcode wilt zoeken, gaat u naar <https://aka.ms/AADsigninsErrorCodes> .                                     |
| `CorrelationId`                   | tekenreeks        | Unieke id van de aanmeldingsgebeurtenis                                                                                                                                              |
| `SessionId`                       | tekenreeks        | Uniek nummer dat aan een gebruiker is toegewezen door de server van een website voor de duur van het bezoek of de sessie                                                                                     |
| `AccountDisplayName`              | tekenreeks        | Naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste initial en een achternaam of achternaam.                             |
| `AccountObjectId`                 | tekenreeks        | Unieke id voor het account in Azure AD                                                                                                                                       |
| `AccountUpn`                      | tekenreeks        | Gebruikersnaam (UPN) van het account                                                                                                                                            |
| `IsExternalUser`                  | int        | Hiermee wordt aangegeven of de gebruiker die zich heeft aangemeld, extern is. Mogelijke waarden: -1 (niet ingesteld), 0 (niet extern), 1 (extern).                                                                   |
| `IsGuestUser`                     | booleaanse       | Geeft aan of de gebruiker die zich heeft aangemeld een gast is in de tenant                                                                                                                  |
| `AlternateSignInName`             | tekenreeks        | On-premises gebruikersnaam (UPN) van de gebruiker die zich aanmeldt bij Azure AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | datetime        | Datum en tijd waarop de gebruiker die zich het laatst heeft aangemeld, zijn wachtwoord heeft gewijzigd                                                                                                              |
| `ResourceDisplayName`             | tekenreeks        | Weergavenaam van de resource die wordt gebruikt                                                                                                                                               |
| `ResourceId`                      | tekenreeks        | Unieke id van de resource die wordt gebruikt                                                                                                                                          |
| `ResourceTenantId`                | tekenreeks        | Unieke id van de tenant van de resource die wordt gebruikt                                                                                                                            |
| `DeviceName`                      | tekenreeks        | Volledig gekwalificeerde domeinnaam (FQDN) van de computer                                                                                                                                   |
| `AadDeviceId`                     | tekenreeks   |      Unieke id voor het apparaat in Azure AD                                                                                                                                                                               |
| `OSPlatform`                      | tekenreeks        | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.  |
| `DeviceTrustType`                 | tekenreeks        | Geeft het vertrouwenstype aan van het apparaat dat is aangemeld. Alleen voor beheerde apparaatscenario's. Mogelijke waarden zijn Workplace, AzureAd en ServerAd.                                     |
| `IsManaged`                       | int       | Geeft aan of het apparaat dat de aanmelding heeft gestart een beheerd apparaat is (1) of niet een beheerd apparaat (0)                                                                         |
| `IsCompliant`                     | int       | Geeft aan of het apparaat dat de aanmelding heeft gestart compatibel is (1) of niet-compatibel (0)                                                                                       |
| `AuthenticationProcessingDetails` | tekenreeks        | Details over de verificatieprocessor                                                                                                                                          |
| `AuthenticationRequirement`       | tekenreeks        | Type verificatie vereist voor de aanmelding. Mogelijke waarden: multiFactorAuthentication (MFA was vereist) en singleFactorAuthentication (er was geen MFA vereist).                |
| `TokenIssuerType`                 | int        | Geeft aan of de token-issuer Azure Active Directory (0) of Active Directory Federation Services (1) is                                                                             |
| `RiskLevelAggregated`                       | int        | Geaggregeerd risiconiveau tijdens aanmelding. Mogelijke waarden: 0 (geaggregeerd risiconiveau niet ingesteld), 1 (geen), 10 (laag), 50 (gemiddeld) of 100 (hoog).                               |
| `RiskDetails`                      | int        | Details over de risicovolle status van de gebruiker die zich heeft aangemeld                                                                                                                            |
| `RiskState`                       | int        | Geeft riskante gebruikerstoestand aan. Mogelijke waarden: 0 (geen), 1 (veilig bevestigd), 2 (opgelost), 3 (afgewezen), 4 (met risico) of 5 (bevestigd gecompromitteerd).                                |
| `UserAgent`                       | tekenreeks        | Gebruikersagentgegevens uit de webbrowser of een andere clienttoepassing                                                                                                             |
| `ClientAppUsed`                   | tekenreeks        | Geeft de gebruikte client-app aan                                                                                                                                                       |
| `Browser`                         | tekenreeks        | Details over de versie van de browser waarmee u zich kunt aanmelden                                                                                                                            |
| `ConditionalAccessPolicies`       | tekenreeks        | Details van het beleid voor voorwaardelijke toegang dat is toegepast op de aanmeldingsgebeurtenis                                                                                                             |
| `ConditionalAccessStatus`         | int        | Status van het beleid voor voorwaardelijke toegang dat is toegepast op de aanmelding. Mogelijke waarden zijn 0 (beleidsregels toegepast), 1 (poging om beleidsregels toe te passen is mislukt) of 2 (beleid dat niet wordt toegepast).      |
| `IPAddress`                       | tekenreeks        | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie                                                                                                  |
| `Country`                     | tekenreeks        | Code met twee letters waarmee het land wordt aangegeven waar het IP-adres van de client is geloceerd                                                                                                    |
| `State`                           | tekenreeks        | Geef aan waar de aanmelding heeft plaatsgevonden, indien beschikbaar                                                                                                                                      |
| `City`                            | tekenreeks        | Plaats waar de accountgebruiker zich bevindt                                                                                                                                              |
| `Latitude`                        | tekenreeks        | De coördinaten van noord naar zuid van de aanmeldingslocatie                                                                                                                              |
| `Longitude`                       | tekenreeks        | De coördinaten van de aanmeldingslocatie                                                                                                                                |
| `NetworkLocationDetails`          | tekenreeks        | Netwerklocatiedetails van de verificatieprocessor van de aanmeldingsgebeurtenis                                                                                                       |
| `RequestId`                       | tekenreeks        |  Unieke id van de aanvraag                                                                                                                                                   |
|`ReportId` | tekenreeks | Unieke id voor de gebeurtenis |

 

 

## <a name="related-articles"></a>Verwante artikelen

-   [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
-   [Overzicht van geavanceerd opsporen](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [De querytaal leren](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Meer informatie over het schema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 