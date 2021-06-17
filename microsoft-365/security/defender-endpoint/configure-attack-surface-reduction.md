---
title: Mogelijkheden voor het verminderen van kwetsbaarheid voor aanvallen configureren
description: Gebruik Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell-cmdlets en Groepsbeleid om de oppervlakbeperking van aanvallen te configureren.
keywords: asr, attack surface reduction, windows defender, microsoft defender, antivirus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984446"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>Mogelijkheden voor het verminderen van kwetsbaarheid voor aanvallen configureren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender voor Eindpunt bevat verschillende mogelijkheden voor het verminderen van de surface van de aanval. Zie Overzicht van de mogelijkheden voor het verminderen van de surface [van de aanval voor meer informatie.](overview-attack-surface-reduction.md) Als u de beperking van het oppervlak van de aanval in uw omgeving wilt configureren, gaat u als volgt te werk:

1. [Schakel isolatie op basis van hardware in voor Microsoft Edge.](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)

2. Toepassingsbeheer inschakelen.

   1. Bekijk basisbeleid in Windows. Zie [Voorbeeldbasisbeleid.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)
   2. Zie de [Windows Defender ontwerphandleiding voor toepassingsbeheer.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)
   3. Raadpleeg [Implementatie van Windows Defender WDAC-beleid (Application Control).](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)

3. [Gecontroleerde maptoegang inschakelen.](enable-controlled-folders.md)

4. [Schakel Netwerkbeveiliging in.](enable-network-protection.md)

5. [Exploitbeveiliging inschakelen.](enable-exploit-protection.md)

6. [Regels voor het verlagen van het oppervlak van de aanval configureren.](enable-attack-surface-reduction.md)

7. Stel uw netwerkfirewall in.

   1. Krijg een overzicht van [Windows Defender Firewall met geavanceerde beveiliging.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
   2. Gebruik de [Windows Defender Firewall-ontwerphandleiding](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) om te bepalen hoe u uw firewallbeleid wilt ontwerpen.
   3. Gebruik de [Windows Defender firewall-implementatiehandleiding](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) om de firewall van uw organisatie in te stellen met geavanceerde beveiliging.

> [!TIP]
> In de meeste gevallen kunt u bij het configureren van de mogelijkheden voor het verlagen van het oppervlak van de aanval kiezen uit verschillende methoden:

> - Microsoft Endpoint Manager (die nu Microsoft Intune en Microsoft Endpoint Configuration Manager)
> - Groepsbeleid
> - PowerShell-cmdlets
