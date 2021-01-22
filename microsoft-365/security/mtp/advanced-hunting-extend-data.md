---
title: Geavanceerde zoekdekking uitbreiden met de juiste instellingen
description: Controleer de controle-instellingen op Windows-apparaten en andere instellingen om ervoor te zorgen dat u de meest uitgebreide gegevens in geavanceerd zoeken krijgt
keywords: advanced hunting, incident, pivot, entity, audit settings, user account management, security group management, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929584"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Geavanceerde zoekdekking uitbreiden met de juiste instellingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[Geavanceerd zoeken](advanced-hunting-overview.md) vertrouwt op gegevens uit diverse bronnen, waaronder uw apparaten, uw Office 365-werkruimten, Azure AD en Microsoft Defender for Identity. Voor de meest uitgebreide gegevens moet u ervoor zorgen dat u de juiste instellingen in de bijbehorende gegevensbronnen hebt.

## <a name="advanced-security-auditing-on-windows-devices"></a>Geavanceerde beveiligingscontrole op Windows-apparaten
Schakel deze geavanceerde controle-instellingen in om ervoor te zorgen dat u gegevens over activiteiten op uw apparaten krijgt, zoals lokaal accountbeheer, lokaal beveiligingsgroepsbeheer en het maken van een service.

| Data | Beschrijving | Schematabel | Configureren |
| --- | --- | --- | --- |
| Accountbeheer | Gebeurtenissen vastgelegd als verschillende waarden die het maken, verwijderen en andere activiteiten in verband met een `ActionType` lokaal account aangeven | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingscontrolebeleid implementeren: [Gebruikersaccountbeheer controleren](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Meer informatie over geavanceerde beveiligingscontrolebeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Beheer van beveiligingsgroep | Gebeurtenissen vastgelegd als verschillende `ActionType` waarden die het maken van lokale beveiligingsgroep en andere lokale groepbeheeractiviteiten aangeven | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingscontrolebeleid implementeren: [Beveiligingsgroepsbeheer controleren](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Meer informatie over geavanceerde beveiligingscontrolebeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Service-installatie | Gebeurtenissen vastgelegd met de `ActionType` waarde om aan te geven dat er een service is `ServiceInstalled` gemaakt | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingscontrolebeleid implementeren: [Systeemextensie voor controle](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Meer informatie over geavanceerde beveiligingscontrolebeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender for Identity sensor op de domeincontroller
Als u Active Directory on-premises gebruikt, moet u de microsoft Defender for Identity-sensor op de domeincontroller installeren om gegevens voor Microsoft Defender voor identiteit op te halen. Wanneer deze gegevens zijn geïnstalleerd en correct geconfigureerd, worden deze ook gebruikt voor geavanceerd zoeken naar Microsoft Defender for Identity en krijgt u een beter beeld van identiteitsgegevens en -gebeurtenissen in uw netwerk. Deze gegevens verbeteren ook de mogelijkheid van Microsoft Defender voor identiteit om relevante waarschuwingen te genereren die ook worden gedekt door geavanceerd zoeken. 

| Data | Beschrijving | Schematabel | Configureren |
| --- | --- | --- | --- |
| Domeincontroller | Gegevens uit on-premises Active Directory die naar Microsoft Defender worden verzonden voor identiteiten, wat identiteitsgerelateerde informatie is, zoals accountgegevens, aanmeldingsactiviteit en Active Directory-query's | Meerdere tabellen, waaronder [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)en [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [De Microsoft Defender for Identity-sensor installeren](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Relevante Windows-gebeurtenissen in te schakeln](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
