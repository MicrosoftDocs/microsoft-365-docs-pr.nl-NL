---
title: De juiste instellingen voor een uitgebreide jacht-overeenkomst
description: Controle-instellingen controleren op Windows-apparaten en andere instellingen om ervoor te zorgen dat u de meest uitgebreide gegevens opneemt in de geavanceerde jacht
keywords: geavanceerde jacht, incident, Pivot, entiteit, controle-instellingen, Gebruikersaccountbeheer, beheer van beveiligingsgroepen, bedreigings jacht, Cyber Threat jacht, zoeken, query, telemetrie, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 82faff2599cd61fa1a4deb3129e1e6780d3f529c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842474"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>De juiste instellingen voor een uitgebreide jacht-overeenkomst

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[Geavanceerde jacht](advanced-hunting-overview.md) is afhankelijk van gegevens die afkomstig zijn van verschillende bronnen, waaronder uw apparaten, uw Office 365-werkruimten, Azure AD en Microsoft Defender voor identiteit. Als u de meest uitgebreide gegevens wilt weergeven, controleert u of u de juiste instellingen hebt in de bijbehorende gegevensbronnen.

## <a name="advanced-security-auditing-on-windows-devices"></a>Geavanceerde beveiligingscontrole op Windows-apparaten
Schakel deze geavanceerde controle-instellingen in om ervoor te zorgen dat u gegevens ontvangt over activiteiten op uw apparaten, waaronder lokaal accountbeheer, beheer van lokale beveiligingsgroepen en het maken van services.

| Data | Beschrijving | Schema tabel | Configureren |
| --- | --- | --- | --- |
| Account beheer | Gebeurtenissen die als verschillende `ActionType` waarden zijn vastgelegd voor het maken, verwijderen en andere activiteiten van accounts | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Een geavanceerd beveiligingscontrolebeleid implementeren: [Gebruikersaccountbeheer-account beheer controleren](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Meer informatie over geavanceerde beveiligings beleidsregels voor beveiliging](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Beheer van beveiligingsgroepen | Gebeurtenissen die zijn vastgelegd als verschillende `ActionType` waarden die het maken van lokale beveiligingsgroepen en andere activiteiten van lokale groepsbeheer aangeven | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Een geavanceerd beveiligingscontrolebeleid implementeren: [beveiligingsbeheer van groepen controleren](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Meer informatie over geavanceerde beveiligings beleidsregels voor beveiliging](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Service-installatie | Gebeurtenissen die zijn vastgelegd met de `ActionType` waarde `ServiceInstalled` , om aan te geven dat er een service is gemaakt | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Een geavanceerd beveiligingscontrolebeleid toepassen: [uitbreiding van beveiligingssysteem controleren](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Meer informatie over geavanceerde beveiligings beleidsregels voor beveiliging](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender for Identity-sensor op de domeincontroller
Als u gebruikmaakt van Active Directory on-premises, moet u de Microsoft Defender for Identity-sensor installeren op de domeincontroller om gegevens voor Microsoft Defender-identiteit te kunnen weergeven. Wanneer deze gegevens zijn geïnstalleerd en correct zijn geconfigureerd, worden deze gegevens ook opgenomen in de geavanceerde jacht via Microsoft Defender voor identiteit en wordt een meer holistische afbeelding van identiteitsinformatie en gebeurtenissen in uw netwerk geboden. Met deze gegevens wordt de mogelijkheid van Microsoft Defender ook uitgebreid voor het maken van relevante waarschuwingen die ook onder de geavanceerde jacht vallen. 

| Data | Beschrijving | Schema tabel | Configureren |
| --- | --- | --- | --- |
| Domeincontroller | Gegevens uit on-premises Active Directory verzonden naar Microsoft Defender voor identiteit, verrijkende informatie over identiteiten, zoals accountgegevens, aanmeldingsactiviteit en Active Directory-query's | Meerdere tabellen, waaronder [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)en [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Microsoft Defender voor de identiteits sensor installeren](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Relevante Windows-gebeurtenissen inschakelen](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
