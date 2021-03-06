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
ms.topic: how-to
ms.openlocfilehash: b6b664d471e238e2feb1e1aedd100c1299fc5bbe
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844260"
---
# <a name="protect-your-network"></a>Beveilig uw netwerk

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Netwerkbeveiliging helpt het aanvalsoppervlak van uw apparaten te beperken door gebeurtenissen op internet. Hiermee voorkomt u dat werknemers elke toepassing gebruiken om toegang te krijgen tot gevaarlijke domeinen die phishingpraktijken, exploits en andere schadelijke inhoud op internet kunnen hosten. Netwerkbeveiliging breidt het bereik van Microsoft Defender SmartScreen uit om al het uitgaande HTTP-verkeer te blokkeren dat probeert verbinding te maken met bronnen met een lage reputatie (op basis van het domein [of](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) de hostnaam).

Netwerkbeveiliging wordt ondersteund op Windows, te beginnen met Windows 10, versie 1709. Netwerkbeveiliging wordt nog niet ondersteund op andere besturingssystemen, maar webbeveiliging wordt ondersteund met de nieuwe Microsoft Edge op basis van Chromium. Zie Webbeveiliging voor [meer informatie.](web-protection-overview.md)

Netwerkbeveiliging breidt de beveiliging in [webbeveiliging uit](web-protection-overview.md) tot het besturingssysteemniveau. Het biedt functionaliteit voor webbeveiliging in Edge voor andere ondersteunde browsers en niet-browsertoepassingen. Daarnaast biedt netwerkbeveiliging zichtbaarheid en blokkering van indicatoren voor compromissen (IOC's) wanneer deze worden gebruikt met [de detectie en reactie van eindpunten.](overview-endpoint-detection-response.md) Netwerkbeveiliging werkt bijvoorbeeld met uw [aangepaste indicatoren.](manage-indicators.md)

Zie Netwerkbeveiliging inschakelen voor meer informatie over het inschakelen van [netwerkbeveiliging.](enable-network-protection.md) Gebruik Groepsbeleid, PowerShell- of MDM-CSP's om netwerkbeveiliging in uw netwerk in te stellen en te beheren.

> [!TIP]
> Zie de testsite van Microsoft Defender voor eindpunt op demo.wd.microsoft.com [om](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) te zien hoe netwerkbeveiliging werkt.

Netwerkbeveiliging werkt het beste met [Microsoft Defender voor](microsoft-defender-endpoint.md)Eindpunt, waarmee u gedetailleerde rapportage krijgt over beveiligingsgebeurtenissen en blokken voor beveiligingsbeveiliging als onderdeel van [scenario's voor waarschuwingsonderzoek.](investigate-alerts.md)

Wanneer netwerkbeveiliging een verbinding blokkeert, wordt er een melding weergegeven vanuit het Actiecentrum. Uw beveiligingsteam kan [de melding aanpassen](customize-attack-surface-reduction.md#customize-the-notification) met de gegevens en contactgegevens van uw organisatie. Daarnaast kunnen afzonderlijke regels voor het verlagen van de aanvalsoppervlakken worden ingeschakeld en aangepast aan bepaalde technieken die u kunt controleren.

U kunt ook de [auditmodus gebruiken om](audit-windows-defender.md) te evalueren hoe netwerkbeveiliging van invloed is op uw organisatie als deze is ingeschakeld.

## <a name="requirements"></a>Vereisten

Netwerkbeveiliging vereist Windows 10 Pro of Enterprise en Microsoft Defender Antivirus realtime beveiliging.

| Windows versie | Microsoft Defender Antivirus |
|:---|:---|
| Windows 10 versie 1709 of hoger <p>Windows Server 1803 of hoger | [Microsoft Defender Antivirus realtime beveiliging en](configure-real-time-protection-microsoft-defender-antivirus.md) [beveiliging in](enable-cloud-protection-microsoft-defender-antivirus.md) de cloud moeten zijn ingeschakeld |

Nadat u de services hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om de verbindingen tussen de services en uw apparaten toe te staan (ook wel eindpunten genoemd).  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Gebeurtenissen op het gebied van netwerkbeveiliging bekijken in het Microsoft Defender for Endpoint Security Center

Microsoft Defender voor Eindpunt biedt gedetailleerde rapportage over gebeurtenissen en blokken als onderdeel van de [scenario's voor waarschuwingsonderzoek.](investigate-alerts.md)

U kunt Microsoft Defender opvragen voor eindpuntgegevens met behulp van [geavanceerd zoeken.](advanced-hunting-overview.md) Als u de [auditmodus gebruikt,](audit-windows-defender.md)kunt u geavanceerd zoeken gebruiken om te zien hoe de netwerkbeveiligingsinstellingen van invloed zijn op uw omgeving als deze zijn ingeschakeld.

Hier is een voorbeeldquery

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Netwerkbeveiligingsgebeurtenissen bekijken in Windows Event Viewer

U kunt het logboek Windows gebeurtenissen bekijken die zijn gemaakt wanneer netwerkbeveiligingsblokken (of audits) toegang tot een schadelijk IP- of domein blokkeert:

1. [Kopieer de XML rechtstreeks.](event-views.md)

2. Selecteer **OK**.

Met deze procedure wordt een aangepaste weergave gemaakt die filtert om alleen de volgende gebeurtenissen weer te geven die betrekking hebben op netwerkbeveiliging:

| Gebeurtenis-id | Beschrijving |
|:---|:---|
| 5007 | Gebeurtenis wanneer instellingen worden gewijzigd |
| 1125 | Gebeurtenis wanneer netwerkbeveiliging wordt uitgevoerd in de auditmodus |
| 1126 | Gebeurtenis wanneer netwerkbeveiliging wordt branden in de blokmodus |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>Aandachtspunten voor Windows virtuele bureaublad met Windows 10 Enterprise multisessie

Houd rekening met de multigebruikers Windows 10 Enterprise de volgende punten:

1. Netwerkbeveiliging is een functie voor het hele apparaat en kan niet worden gericht op specifieke gebruikerssessies.

2. Filterbeleid voor webinhoud is ook apparaatbreed.

3. Als u onderscheid wilt maken tussen gebruikersgroepen, kunt u afzonderlijke Windows en toewijzingen voor virtuele bureaubladhosts maken.

4. Test netwerkbeveiliging in de auditmodus om het gedrag ervan te beoordelen voordat u deze uitrolt. 

5. U kunt het formaat van uw implementatie mogelijk ook als u een groot aantal gebruikers of een groot aantal sessies met meerdere gebruikers hebt.

### <a name="alternative-option-for-network-protection"></a>Alternatieve optie voor netwerkbeveiliging

Voor Windows 10 Enterprise Multi-Session 1909 en hoger, gebruikt in Windows Virtual Desktop op Azure, kan netwerkbeveiliging voor Microsoft Edge worden ingeschakeld met de volgende methode:

1. Gebruik [Netwerkbeveiliging in-en](enable-network-protection.md) volg de instructies om uw beleid toe te passen.

2. Voer de volgende PowerShell-opdracht uit: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>Problemen met netwerkbeveiliging oplossen

Vanwege de omgeving waarin Netwerkbeveiliging wordt uitgevoerd, kan Microsoft mogelijk geen proxy-instellingen voor het besturingssysteem detecteren. In sommige gevallen kunnen netwerkbeveiligings clients geen cloudservice bereiken. Als u het verbindingsprobleem wilt oplossen, moeten klanten met E5-licenties een van de volgende registersleutels van Defender configureren:

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a>Aanverwante artikelen

- [Netwerkbeveiliging evalueren |](evaluate-network-protection.md) Maak een snel scenario waarin wordt gedemonstreerd hoe de functie werkt en welke gebeurtenissen gewoonlijk worden gemaakt.

- [Netwerkbeveiliging inschakelen](enable-network-protection.md) | Gebruik Groepsbeleid, PowerShell- of MDM-CSP's om netwerkbeveiliging in uw netwerk in te stellen en te beheren.
