---
title: Microsoft Defender Antivirusbeveiliging controleren en rapporteren
description: Gebruik Configuratiebeheer of hulpprogramma's voor beveiligingsgegevens en gebeurtenisbeheer (SIEM) om rapporten te gebruiken en Microsoft Defender AV te controleren met PowerShell en WMI.
keywords: siem, monitor, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f0065792f525827ccd1471087b8a707989ef61ef
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690701"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Rapport over Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus is ingebouwd in Windows 10, Windows Server 2019 en Windows Server 2016. Microsoft Defender Antivirus is van uw volgende generatie bescherming in Microsoft Defender voor Eindpunt. Beveiliging van de volgende generatie helpt uw apparaten te beschermen tegen softwaredreigingen zoals virussen, malware en spyware in e-mail, apps, de cloud en het web.

Met Microsoft Defender Antivirus hebt u verschillende opties voor het controleren van de beveiligingsstatus en waarschuwingen. U kunt Microsoft Endpoint Manager gebruiken om [Microsoft Defender Antivirus te](/configmgr/protect/deploy-use/monitor-endpoint-protection) controleren of [e-mailwaarschuwingen te maken.](/configmgr/protect/deploy-use/endpoint-configure-alerts) U kunt ook de beveiliging bewaken met [Microsoft Intune.](/intune/introduction-intune)  

Microsoft Operations Management Suite heeft een [update compliance-invoeging](/windows/deployment/update/update-compliance-get-started) die rapporteert over belangrijke Microsoft Defender Antivirus-problemen, waaronder beveiligingsupdates en realtime beveiligingsinstellingen.

Als u een SIEM-server (Security Information and Event Management) van derden hebt, kunt u ook [Windows Defender-clientgebeurtenissen gebruiken.](/windows/win32/events/windows-events) 

Windows-gebeurtenissen bestaan uit verschillende bronnen voor beveiligingsgebeurtenissen, waaronder SAM-gebeurtenissen (verbeterd voor[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), zie ook het onderwerp Beveiligingsaudit) en [Windows Defender-gebeurtenissen.](troubleshoot-microsoft-defender-antivirus.md) [](/windows/device-security/auditing/security-auditing-overview) 

Deze gebeurtenissen kunnen centraal worden samengevoegd met behulp van de [Windows-gebeurtenisverzamelaar.](/windows/win32/wec/windows-event-collector) SiEM-servers hebben vaak verbindingslijnen voor Windows-gebeurtenissen, zodat u alle beveiligingsgebeurtenissen in uw SIEM-server kunt correleren. 

U kunt ook [malwaregebeurtenissen controleren met behulp van de malwarebeoordelingsoplossing in Log Analytics.](/azure/log-analytics/log-analytics-malware)

Zie de tabel [(Implementatie, beheer](deploy-manage-report-microsoft-defender-antivirus.md#ref2)en rapportageopties) voor het bewaken of bepalen van de status met PowerShell, WMI of Microsoft Azure.

## <a name="related-articles"></a>Verwante artikelen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus op Windows Server 2016 en 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender Antivirus implementeren](deploy-manage-report-microsoft-defender-antivirus.md)