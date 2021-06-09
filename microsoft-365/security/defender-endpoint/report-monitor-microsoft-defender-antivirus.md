---
title: Controleren en rapporteren over Microsoft Defender Antivirus beveiliging
description: Gebruik Configuratiebeheer of hulpprogramma's voor beveiligingsgegevens en gebeurtenisbeheer (SIEM) om rapporten te gebruiken en Microsoft Defender AV te controleren met PowerShell en WMI.
keywords: siem, monitor, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5780daaa65a4d83376dd7977e03e88e2d828befc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269584"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Rapporteren in Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus is ingebouwd in Windows 10, Windows Server 2019 en Windows Server 2016. Microsoft Defender Antivirus is van uw volgende generatie beveiliging in Microsoft Defender voor Eindpunt. Beveiliging van de volgende generatie helpt uw apparaten te beschermen tegen softwaredreigingen zoals virussen, malware en spyware in e-mail, apps, de cloud en het web.

Met Microsoft Defender Antivirus hebt u verschillende opties voor het controleren van de beveiligingsstatus en waarschuwingen. U kunt de Microsoft Endpoint Manager gebruiken om [de Microsoft Defender Antivirus te](/configmgr/protect/deploy-use/monitor-endpoint-protection) controleren of [e-mailwaarschuwingen te maken.](/configmgr/protect/deploy-use/endpoint-configure-alerts) U kunt ook de beveiliging controleren [met](/intune/introduction-intune)Microsoft Intune.  

Microsoft Operations Management Suite heeft een [update compliance-invoegvoeging](/windows/deployment/update/update-compliance-get-started) die rapporteert over belangrijke Microsoft Defender Antivirus problemen, waaronder beveiligingsupdates en realtime beveiligingsinstellingen.

Als u een SIEM-server (Security Information and Event Management) van derden hebt, kunt u ook de clientgebeurtenissen Windows Defender [gebruiken.](/windows/win32/events/windows-events) 

Windows gebeurtenissen bestaan uit verschillende bronnen voor beveiligingsgebeurtenissen, waaronder SAM-gebeurtenissen (verbeterd voor[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), zie ook het onderwerp [Beveiligingsaudit)](/windows/device-security/auditing/security-auditing-overview) [en Windows Defender gebeurtenissen.](troubleshoot-microsoft-defender-antivirus.md) 

Deze gebeurtenissen kunnen centraal worden samengevoegd met de [Windows gebeurtenisverzamelaar.](/windows/win32/wec/windows-event-collector) SIEM-servers hebben vaak connectors voor Windows gebeurtenissen, zodat u alle beveiligingsgebeurtenissen in uw SIEM-server kunt correleren. 

U kunt ook [malwaregebeurtenissen controleren met behulp van de malwarebeoordelingsoplossing in Log Analytics.](/azure/log-analytics/log-analytics-malware)

Zie de tabel [(Implementatie,](deploy-manage-report-microsoft-defender-antivirus.md#ref2)beheer en rapportageopties) voor het controleren of bepalen van de status met PowerShell, WMI of Microsoft Azure.

## <a name="related-articles"></a>Aanverwante artikelen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus op Windows Server 2016 en 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Implementatie van Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)