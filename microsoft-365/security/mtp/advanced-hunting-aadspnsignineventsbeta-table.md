---
title: AADSpnSignInEventsBeta-tabel in het geavanceerde jacht schema
description: Meer informatie over informatie die is gekoppeld aan de Azure Active Directory-Service Principal en de lijst met aanmeld gebeurtenissen van de beheerde identiteit van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, Column, datatype, beschrijving, AlertInfo, waarschuwing, entiteit, bewijs, bestand, IP-adres, apparaat, computer, gebruiker, account, identiteit, AAD
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
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784297"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Van toepassing op:**

- Microsoft 365 Defender

>[!IMPORTANT]
> De `AADSpnSignInEventsBeta` tabel bevindt zich momenteel in de bètaversie en wordt kort weer geboden, zodat u de service-principal van Azure Active Directory (Aad) en de aanmeldingsgebeurtenissen van de beheerde identiteit kunt zoeken. We zullen uiteindelijk alle gegevens van het aanmeldings schema naar de `IdentityLogonEvents` tabel verplaatsen.<br><br>
> Klanten die de Microsoft 365-app hebben geopend via de geïntegreerde Microsoft-app voor eindpunten van het Azure-Beveiligingscentrum, maar geen licenties voor Microsoft Defender for Office, Microsoft Defender for Identity, of Microsoft Cloud app Security, kunnen dit schema niet weergeven. 



De `AADSpnSignInEventsBeta` tabel in het geavanceerde begeleidende schema bevat informatie over het aanmelden van Azure Active Directory-service en invoegtoepassingen voor beheerde id's. U vindt meer informatie over de verschillende soorten aanmeldinformatie in [Azure Active Directory-aanmeldings activiteitenrapporten-preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)zoeken.





| Kolomnaam     | Gegevenstype | Beschrijving   |
| ----- | ----- | ---- |
| `Timestamp` | tijd      | De datum en tijd waarop de record is gegenereerd                                                                                                     |
| `Application`          | tekenreeks        | De toepassing die de opgenomen actie heeft uitgevoerd                                                                                                   |
| `ApplicationId`        | tekenreeks        | Unieke id voor de toepassing                                                                                                           |
| `IsManagedIdentity`    | Boolean       | Geeft aan of de aanmelding is gestart door een beheerde identiteit                                                                               |
| `ErrorCode`            | int        | Bevat de foutcode als een aanmeldingsfout optreedt. Ga naar voor een beschrijving van een bepaalde foutcode <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | tekenreeks        | Unieke id van de aanmeld gebeurtenis                                                                                                          |
| `ServicePrincipalName` | tekenreeks        | Naam van de service-principal waarmee de aanmelding is gestart                                                                                        |
| `ServicePrincipalId`   | tekenreeks        | Unieke id van de service-principal waarmee de aanmelding werd geïnitieerd                                                                           |
| `ResourceDisplayName`  | tekenreeks        | De weergavenaam van de resource die wordt geopend                                                                                                           |
| `ResourceId`           | tekenreeks        | Unieke id van de geopente resource                                                                                                      |
| `ResourceTenantId`     | tekenreeks        | Unieke id van de Tenant van de geopente bron                                                                                        |
| `IPAddress`            | tekenreeks        | Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie                                                              |
| `CountryCode`          | tekenreeks        | Tweeletterige code die het land aangeeft waarin het IP-adres van de client geolocatie is                                                                |
| `State`                | tekenreeks        | De status van de aanmelding, indien beschikbaar                                                                                                  |
| `City`                 | tekenreeks        | Plaats waar de account gebruiker zich bevindt                                                                                                          |
| `Latitude`             | tekenreeks        | De Noord-to-Zuid-coördinaten van de aanmeldingslocatie                                                                                          |
| `Longitude`            | tekenreeks        | De Oost-en West-coördinaten van de aanmeldingslocatie                                                                                            |
| `RequestId`            | tekenreeks        | Unieke id van de aanvraag                                                                                                                |
|`ReportId` | tekenreeks | Unieke id voor de gebeurtenis | 

 

## <a name="related-articles"></a>Verwante artikelen

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [Overzicht van geavanceerd opsporen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [De querytaal leren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Meer informatie over het schema](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

