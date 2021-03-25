---
title: Netwerkbeveiliging gebruiken om verbindingen met slechte sites te voorkomen
description: Bescherm uw netwerk door te voorkomen dat gebruikers toegang krijgen tot bekende schadelijke en verdachte netwerkadressen
keywords: Netwerkbeveiliging, exploits, schadelijke website, ip, domein, domeinen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.openlocfilehash: 29844d72f4a081db18ab56941fec53eeaf76dd12
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186975"
---
# <a name="protect-your-network"></a>Uw netwerk beveiligen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Netwerkbeveiliging helpt het aanvalsoppervlak van uw apparaten te beperken door gebeurtenissen op internet. Hiermee voorkomt u dat werknemers elke toepassing gebruiken om toegang te krijgen tot gevaarlijke domeinen die phishingpraktijken, exploits en andere schadelijke inhoud op internet kunnen hosten. Netwerkbeveiliging breidt het bereik van [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) uit om al het uitgaande HTTP-verkeer te blokkeren dat probeert verbinding te maken met bronnen met een lage reputatie (op basis van het domein of de hostnaam).

Netwerkbeveiliging wordt ondersteund in Windows, te beginnen met Windows 10, versie 1709. 

Zie Netwerkbeveiliging inschakelen voor meer informatie over het inschakelen van [netwerkbeveiliging.](enable-network-protection.md) Gebruik Groepsbeleid, PowerShell- of MDM-CSP's om netwerkbeveiliging in uw netwerk in te stellen en te beheren.

> [!TIP]
> Zie de MICROSOFT Defender ATP-testsite op demo.wd.microsoft.com [om](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) te zien hoe netwerkbeveiliging werkt.

Netwerkbeveiliging werkt het beste met [Microsoft Defender voor](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)Eindpunt, waarmee u gedetailleerde rapportage krijgt over beveiligingsgebeurtenissen en blokken voor beveiligingsbeveiliging als onderdeel van [scenario's voor waarschuwingsonderzoek.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

Wanneer netwerkbeveiliging een verbinding blokkeert, wordt er een melding weergegeven vanuit het Actiecentrum. Uw beveiligingsteam kan [de melding aanpassen](customize-attack-surface-reduction.md#customize-the-notification) met de gegevens en contactgegevens van uw organisatie. Daarnaast kunnen afzonderlijke regels voor het verlagen van de aanvalsoppervlakken worden ingeschakeld en aangepast aan bepaalde technieken die u kunt controleren.

U kunt ook de [auditmodus gebruiken om](audit-windows-defender.md) te evalueren hoe netwerkbeveiliging van invloed is op uw organisatie als deze is ingeschakeld.

## <a name="requirements"></a>Vereisten

Netwerkbeveiliging vereist Windows 10 Pro of Enterprise en Microsoft Defender Antivirus realtime beveiliging.

| Windows-versie | Microsoft Defender Antivirus |
|:---|:---|
| Windows 10 versie 1709 of hoger <p>Windows Server 1803 of hoger | [Microsoft Defender Antivirus realtime-beveiliging](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) en [beveiliging in](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) de cloud moeten zijn ingeschakeld |

Nadat u de services hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om de verbindingen tussen de services en uw apparaten toe te staan (ook wel eindpunten genoemd).  

- .smartscreen.microsoft.com
- .smartscreen-prod.microsoft.com

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Gebeurtenissen op het gebied van netwerkbeveiliging bekijken in het Microsoft Defender for Endpoint Security Center

Microsoft Defender voor Eindpunt biedt gedetailleerde rapportage over gebeurtenissen en blokken als onderdeel van de [scenario's voor waarschuwingsonderzoek.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

U kunt Microsoft Defender opvragen voor eindpuntgegevens met behulp van [Geavanceerd zoeken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection) Als u de [auditmodus gebruikt,](audit-windows-defender.md)kunt u geavanceerd zoeken gebruiken om te zien hoe de netwerkbeveiligingsinstellingen van invloed zijn op uw omgeving als deze zijn ingeschakeld.

Hier is een voorbeeldquery

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Netwerkbeveiligingsgebeurtenissen bekijken in Windows Event Viewer

U kunt het Windows-gebeurtenislogboek bekijken om gebeurtenissen te bekijken die worden gemaakt wanneer netwerkbeveiligingsblokken (of audits) toegang tot een schadelijk IP- of domein blokkeert:

1. [Kopieer de XML rechtstreeks.](event-views.md)

2. Kies **OK**.

Met deze procedure wordt een aangepaste weergave gemaakt die filtert om alleen de volgende gebeurtenissen weer te geven die betrekking hebben op netwerkbeveiliging:

| Gebeurtenis-id | Beschrijving |
|:---|:---|
| 5007 | Gebeurtenis wanneer instellingen worden gewijzigd |
| 1125 | Gebeurtenis wanneer netwerkbeveiliging wordt uitgevoerd in de auditmodus |
| 1126 | Gebeurtenis wanneer netwerkbeveiliging wordt branden in de blokmodus |

## <a name="related-articles"></a>Verwante artikelen

- [Netwerkbeveiliging evalueren |](evaluate-network-protection.md) Maak een snel scenario waarin wordt gedemonstreerd hoe de functie werkt en welke gebeurtenissen gewoonlijk worden gemaakt.

- [Netwerkbeveiliging inschakelen](enable-network-protection.md) | Gebruik Groepsbeleid, PowerShell- of MDM-CSP's om netwerkbeveiliging in uw netwerk in te stellen en te beheren.
