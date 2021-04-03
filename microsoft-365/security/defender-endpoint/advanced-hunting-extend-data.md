---
title: Geavanceerde dekking voor jagen uitbreiden met de juiste instellingen
description: Controleer de controle-instellingen op Windows-apparaten en andere instellingen om ervoor te zorgen dat u de meest uitgebreide gegevens krijgt in geavanceerde jacht
keywords: advanced hunting, incident, pivot, entity, audit settings, user account management, security group management, threat hunting, cyber threat hunting, search, query, telemetry, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500620"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Geavanceerde dekking voor jagen uitbreiden met de juiste instellingen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[Geavanceerde jacht](advanced-hunting-overview.md) is afhankelijk van gegevens die afkomstig zijn uit uw hele organisatie. Als u de meest uitgebreide gegevens wilt krijgen, moet u ervoor zorgen dat u de juiste instellingen hebt in de bijbehorende gegevensbronnen.

## <a name="advanced-security-auditing-on-windows-devices"></a>Geavanceerde beveiligingsaudits op Windows-apparaten

Schakel deze geavanceerde controle-instellingen in om ervoor te zorgen dat u gegevens krijgt over activiteiten op uw apparaten, zoals lokaal accountbeheer, lokaal beveiligingsgroepbeheer en het maken van service.

Data | Omschrijving | Schematabel | Configureren
-|-|-|-
Accountbeheer | Gebeurtenissen die zijn vastgelegd als verschillende waarden die het maken, verwijderen en `ActionType` andere accountgerelateerde activiteiten aangeven | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingsauditbeleid implementeren: [Gebruikersaccountbeheer controleren](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Meer informatie over geavanceerd beveiligingsauditbeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Beveiligingsgroepsbeheer | Gebeurtenissen die zijn vastgelegd als verschillende waarden die het maken van `ActionType` lokale beveiligingsgroepen en andere lokale activiteiten voor groepsbeheer aangeven | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingsauditbeleid implementeren: [Beveiligingsgroepsbeheer controleren](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Meer informatie over geavanceerd beveiligingsauditbeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Service-installatie | Gebeurtenissen die zijn vastgelegd met de waarde, waarmee wordt `ActionType` aangegeven dat er een service is `ServiceInstalled` gemaakt | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingsauditbeleid implementeren: [Systeemextensie voor auditbeveiliging](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Meer informatie over geavanceerd beveiligingsauditbeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](overview-custom-detections.md)
