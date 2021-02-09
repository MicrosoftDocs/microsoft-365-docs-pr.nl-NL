---
title: AADSpnSignInEventsBeta-tabel in het geavanceerde schema voor zoeken
description: Meer informatie over informatie die is gekoppeld aan Azure Active Directory service principal en de tabel met beheerde identiteitsgegevens van het geavanceerde schema voor zoeken
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
ms.openlocfilehash: 3eba2459fd9a0af1963ca8d1446b22fc0b1bdb93
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145401"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Van toepassing op:**

- Microsoft 365 Defender

>[!IMPORTANT]
> De tabel is momenteel beschikbaar in de bètaversie en wordt op korte termijn aangeboden zodat u kunt zoeken in `AADSpnSignInEventsBeta` azure Active Directory (AAD)-service-principal en beheerde aanmeldingsgebeurtenissen voor identiteiten. Uiteindelijk worden alle gegevens van het aanmeldingsschema naar de tabel `IdentityLogonEvents` verplaatst.<br><br>
> Klanten die toegang hebben tot Microsoft 365 Defender via de geïntegreerde oplossing microsoft Defender for Endpoint van het Azure-beveiligingscentrum, maar geen licenties hebben voor Microsoft Defender voor Office, Microsoft Defender voor identiteit of Microsoft Cloud App-beveiliging, kunnen dit schema niet bekijken. 



De `AADSpnSignInEventsBeta` tabel in het geavanceerde schema voor zoeken bevat informatie over Azure Active Directory-service-principal en beheerde identiteitsgegevens. U kunt meer informatie krijgen over de verschillende soorten aanmeldingsrapporten in [Azure Active Directory-activiteitsrapporten - preview.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)





| Kolomnaam     | Gegevenstype | Beschrijving   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Datum en tijd waarop de record is gegenereerd                                                                                                     |
| `Application`          | tekenreeks        | Toepassing die de opgenomen actie heeft uitgevoerd                                                                                                   |
| `ApplicationId`        | tekenreeks        | Unieke id voor de toepassing                                                                                                           |
| `IsManagedIdentity`    | boolean       | Geeft aan of de aanmelding is gestart met een beheerde identiteit                                                                               |
| `ErrorCode`            | int        | Bevat de foutcode als er een aanmeldingsfout optreedt. Als u een beschrijving van een specifieke foutcode wilt vinden, gaat u naar <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | tekenreeks        | Unieke id van de aanmeldingsgebeurtenis                                                                                                          |
| `ServicePrincipalName` | tekenreeks        | Naam van de service-principal die de aanmelding heeft geïnitieerd                                                                                        |
| `ServicePrincipalId`   | tekenreeks        | Unieke id van de service-principal die de aanmelding heeft geïnitieerd                                                                           |
| `ResourceDisplayName`  | tekenreeks        | Weergavenaam van de bron die is gebruikt                                                                                                           |
| `ResourceId`           | tekenreeks        | Unieke id van de bron die wordt gebruikt                                                                                                      |
| `ResourceTenantId`     | tekenreeks        | Unieke id van de tenant van de bron die is gebruikt                                                                                        |
| `IPAddress`            | tekenreeks        | IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie                                                              |
| `Country`          | tekenreeks        | Tweeletterige code die het land aangeeft waar het IP-adres van de client geo-toegewezen is                                                                |
| `State`                | tekenreeks        | Provincie waar de aanmelding heeft plaatsgevonden, indien beschikbaar                                                                                                  |
| `City`                 | tekenreeks        | Plaats waar de accountgebruiker zich bevindt                                                                                                          |
| `Latitude`             | tekenreeks        | De coördinaten van de aanmeldingslocatie van Noord naar Zuid                                                                                          |
| `Longitude`            | tekenreeks        | De coördinaten van Oost naar West van de aanmeldingslocatie                                                                                            |
| `RequestId`            | tekenreeks        | Unieke id van de aanvraag                                                                                                                |
|`ReportId` | tekenreeks | Unieke id voor de gebeurtenis | 

 

## <a name="related-articles"></a>Verwante artikelen

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Overzicht van geavanceerd opsporen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [De querytaal leren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Meer informatie over het schema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

