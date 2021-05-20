---
title: AADSpnSignInEventsBeta-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over informatie die is gekoppeld aan Azure Active Directory en de tabel met beheerde identiteitsgegevens van het geavanceerde schema voor het zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583542"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Van toepassing op:**

- Microsoft 365 Defender

>[!IMPORTANT]
> De tabel is momenteel in bètaversie en wordt op korte termijn aangeboden, zodat u kunt zoeken in `AADSpnSignInEventsBeta` Azure Active Directory (AAD) service principal en managed identity sign-in events. Uiteindelijk worden alle aanmeldingsschemagegevens naar de tabel `IdentityLogonEvents` verplaatst.



De tabel in het geavanceerde schema voor het zoeken bevat `AADSpnSignInEventsBeta` informatie Azure Active Directory service principal en beheerde identiteits aanmelden. U kunt meer informatie over de verschillende soorten aanmeldingen in Azure Active Directory [aanmeldingsactiviteitsrapporten - preview.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

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