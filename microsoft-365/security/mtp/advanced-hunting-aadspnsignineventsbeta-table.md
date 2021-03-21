---
title: AADSpnSignInEventsBeta-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over informatie die is gekoppeld aan de azure Active Directory-service principal en de tabel met beheerde identiteitsgegevens van het geavanceerde schema voor het zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: 5050f4f91d61369e927eae15ca7c156a17792c24
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924538"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Van toepassing op:**

- Microsoft 365 Defender

>[!IMPORTANT]
> De tabel is momenteel in bètaversie en wordt op korte termijn aangeboden, zodat u kunt zoeken in `AADSpnSignInEventsBeta` azure Active Directory (AAD) service principal en managed identity sign-in events. Uiteindelijk worden alle aanmeldingsschemagegevens naar de tabel `IdentityLogonEvents` verplaatst.<br><br>
> Klanten die toegang hebben tot Microsoft 365 Defender via de geïntegreerde Microsoft Defender voor Eindpunt-oplossing van het Azure Security Center, maar geen licenties hebben voor Microsoft Defender voor Office, Microsoft Defender voor identiteit of Microsoft Cloud App Security, kunnen dit schema niet bekijken. 



De `AADSpnSignInEventsBeta` tabel in het geavanceerde schema bevat informatie over azure Active Directory-service principal en beheerde identiteits aanmelden. U kunt meer informatie krijgen over de verschillende soorten aanmeldingen in [Azure Active Directory-aanmeldingsactiviteitsrapporten - preview.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)





| Kolomnaam     | Gegevenstype | Beschrijving   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Datum en tijd waarop de record is gegenereerd                                                                                                     |
| `Application`          | tekenreeks        | Toepassing die de opgenomen actie heeft uitgevoerd                                                                                                   |
| `ApplicationId`        | tekenreeks        | Unieke id voor de toepassing                                                                                                           |
| `IsManagedIdentity`    | booleaanse       | Geeft aan of de aanmelding is gestart door een beheerde identiteit                                                                               |
| `ErrorCode`            | int        | Bevat de foutcode als er een aanmeldingsfout optreedt. Als u een beschrijving van een specifieke foutcode wilt zoeken, gaat u naar <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | tekenreeks        | Unieke id van de aanmeldingsgebeurtenis                                                                                                          |
| `ServicePrincipalName` | tekenreeks        | Naam van de serviceprincipaal die de aanmelding heeft gestart                                                                                        |
| `ServicePrincipalId`   | tekenreeks        | Unieke id van de serviceprincipaal die de aanmelding heeft gestart                                                                           |
| `ResourceDisplayName`  | tekenreeks        | Weergavenaam van de resource die wordt gebruikt                                                                                                           |
| `ResourceId`           | tekenreeks        | Unieke id van de resource die wordt gebruikt                                                                                                      |
| `ResourceTenantId`     | tekenreeks        | Unieke id van de tenant van de resource die wordt gebruikt                                                                                        |
| `IPAddress`            | tekenreeks        | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie                                                              |
| `Country`          | tekenreeks        | Code met twee letters waarmee het land wordt aangegeven waar het IP-adres van de client is geloceerd                                                                |
| `State`                | tekenreeks        | Geef aan waar de aanmelding heeft plaatsgevonden, indien beschikbaar                                                                                                  |
| `City`                 | tekenreeks        | Plaats waar de accountgebruiker zich bevindt                                                                                                          |
| `Latitude`             | tekenreeks        | De coördinaten van noord naar zuid van de aanmeldingslocatie                                                                                          |
| `Longitude`            | tekenreeks        | De coördinaten van de aanmeldingslocatie                                                                                            |
| `RequestId`            | tekenreeks        | Unieke id van de aanvraag                                                                                                                |
|`ReportId` | tekenreeks | Unieke id voor de gebeurtenis | 

 

## <a name="related-articles"></a>Verwante artikelen

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [Overzicht van geavanceerd opsporen](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [De querytaal leren](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Meer informatie over het schema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)