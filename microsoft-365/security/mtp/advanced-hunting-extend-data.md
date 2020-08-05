---
title: Geavanceerde jachtdekking uitbreiden met de juiste instellingen
description: Controleer de controle-instellingen op Windows-apparaten en andere instellingen om ervoor te zorgen dat u de meest uitgebreide gegevens in geavanceerde jacht
keywords: geavanceerde jacht, incident, pivot, entiteit, audit-instellingen, user account management, security group management, threat hunting, cyber threat hunting, search, query, telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 07c010a78d297a4a3c932c0d9a0e32cce0c43bfa
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560905"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Geavanceerde jachtdekking uitbreiden met de juiste instellingen

**Van toepassing op:**
- Microsoft Threat Protection

[Geavanceerde jacht](advanced-hunting-overview.md) is afhankelijk van gegevens afkomstig uit verschillende bronnen, waaronder uw apparaten, uw Office 365-werkruimten, Azure AD en Azure ATP. Om de meest uitgebreide gegevens mogelijk te krijgen, moet u ervoor zorgen dat u over de juiste instellingen in de bijbehorende gegevensbronnen beschikt.

## <a name="advanced-security-auditing-on-windows-devices"></a>Geavanceerde beveiligingscontrole op Windows-apparaten
Schakel deze geavanceerde controle-instellingen in om ervoor te zorgen dat u gegevens krijgt over activiteiten op uw apparaten, waaronder lokaal accountbeheer, lokaal beheer van beveiligingsgroepen en het maken van service.

| Data | Beschrijving | Schematabel | Configureren |
| --- | --- | --- | --- |
| Accountbeheer | Gebeurtenissen vastgelegd als verschillende `ActionType` waarden die duiden op het maken, verwijderen en andere accountgerelateerde activiteiten | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingscontrolebeleid implementeren: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Meer informatie over geavanceerd beveiligingscontrolebeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Beheer van beveiligingsgroepen | Gebeurtenissen vastgelegd als verschillende `ActionType` waarden die aangeven voor het maken van lokale beveiligingsgroepen en andere lokale groepsbeheeractiviteiten | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingscontrolebeleid implementeren: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Meer informatie over geavanceerd beveiligingscontrolebeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Service-installatie | Gebeurtenissen die zijn vastgelegd met de `ActionType` `ServiceInstalled` waarde, wat aangeeft dat een service is gemaakt | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Een geavanceerd beveiligingscontrolebeleid implementeren: [Extensie van het auditbeveiligingssysteem](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Meer informatie over geavanceerd beveiligingscontrolebeleid](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="azure-atp-sensor-on-the-domain-controller"></a>Azure ATP-sensor op de domeincontroller
Als u Active Directory on premises uitvoert, moet u de Azure ATP-sensor op de domeincontroller installeren om gegevens voor Azure ATP op te halen. Wanneer deze gegevens zijn geïnstalleerd en correct zijn geconfigureerd, worden deze gegevens ook verwerkt in geavanceerde jacht via Azure ATP en biedt u een meer holistisch beeld van identiteitsinformatie en gebeurtenissen in uw netwerk. Deze gegevens verbeteren ook de mogelijkheid van Azure ATP om relevante waarschuwingen te genereren die ook worden gedekt door geavanceerde jacht. 

| Data | Beschrijving | Schematabel | Configureren |
| --- | --- | --- | --- |
| Domeincontroller | Gegevens van on-premises Active Directory die naar Azure ATP worden verzonden, waarbij identiteitsgerelateerde informatie wordt verrijkt, zoals accountgegevens, aanmeldingsactiviteit en Active Directory-query's | Meerdere tabellen, waaronder [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)en [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [De Azure ATP-sensor installeren](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Relevante Windows-gebeurtenissen inschakelen](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)