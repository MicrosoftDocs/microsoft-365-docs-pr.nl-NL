---
title: Microsoft Defender voor Eindpunt beheren met PowerShell, WMI en MPCmdRun.exe
description: Meer informatie over het beheren van Microsoft Defender voor Eindpunt met PowerShell, WMI en MPCmdRun.exe
keywords: post-migration, manage, operations, maintenance, utilization, PowerShell, WMI, MPCmdRun.exe, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: d2238703e3b1205287d4ab6239af20095b51df13
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841908"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Microsoft Defender voor Eindpunt beheren met PowerShell, WMI en MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> We raden u [aan Microsoft Endpoint Manager](/mem) voor het beheren van de beveiligingsfuncties voor bedreigingen van uw organisatie voor apparaten (ook wel eindpunten genoemd). Endpoint Manager bevat [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) en [Microsoft Endpoint Configuration Manager.](/mem/configmgr/core/understand/introduction) 
> - [Meer informatie over Endpoint Manager](/mem/endpoint-manager-overview)
> - [Co-manage Microsoft Defender for Endpoint op Windows 10 apparaten met Configuration Manager en Intune](manage-atp-post-migration-intune.md)
> - [Microsoft Defender voor eindpunt beheren met Intune](manage-atp-post-migration-intune.md) 

U kunt sommige Microsoft Defender Antivirus-instellingen beheren op apparaten met [PowerShell,](#configure-microsoft-defender-for-endpoint-with-powershell) [Windows Management Instrumentation](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI) en de [Microsoft Malware Protection Command Line Utility](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe). U kunt bijvoorbeeld bepaalde instellingen Microsoft Defender Antivirus beheren. En in sommige gevallen kunt u de regels voor de beperking van uw aanvalsoppervlak aanpassen en beveiligingsinstellingen gebruiken. 

> [!IMPORTANT]
> Functies voor bedreigingsbeveiliging die u configureert met PowerShell, WMI of MCPmdRun.exe kunnen worden overschreven door configuratie-instellingen die worden geïmplementeerd met Intune of Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Microsoft Defender voor eindpunt configureren met PowerShell

U kunt PowerShell gebruiken om uw Microsoft Defender Antivirus te beheren, bescherming te gebruiken en de surface reduction-regels voor uw aanval te gebruiken.

|Taak  |Informatiebronnen  |
|---------|---------|
|**Beheer Microsoft Defender Antivirus** <br/><br/>*Bekijk de status van antimalwarebeveiliging, configureer voorkeuren voor antivirusscans & updates en pas andere wijzigingen aan in uw antivirusbeveiliging.*    |[PowerShell-cmdlets gebruiken voor het configureren en beheren van Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[PowerShell-cmdlets gebruiken om beveiliging via de cloud in te stellen](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**Misbruikbeveiliging configureren** om bedreigingen op de apparaten van uw organisatie te beperken<br/><br/> *Het is raadzaam om eerst exploitbeveiliging te gebruiken in [de auditmodus.](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) Op die manier kunt u zien hoe misbruikbeveiliging van invloed is op apps die uw organisatie gebruikt.*     | [Bescherming tegen misbruik aanpassen](/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[PowerShell-cmdlets voor bescherming tegen misbruik](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|**Surface Reduction-regels voor aanvallen configureren** met PowerShell <br/><br/>*U kunt PowerShell gebruiken om bestanden en mappen uit te sluiten van de regels voor het verlagen van het oppervlak van de aanval.* |[Surface Reduction-regels voor aanvallen aanpassen: PowerShell gebruiken om bestanden uit te sluiten & mappen](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>Zie ook het grafische gebruikersinterfaceprogramma van [António Vasconcelo](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)voor het instellen van de regels voor het verlagen van de surface attack met PowerShell. |
|**Netwerkbeveiliging inschakelen** met PowerShell <br/><br/>*U kunt PowerShell gebruiken om Netwerkbeveiliging in te stellen.* |[Netwerkbeveiliging in- en uit te zetten met PowerShell](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**Beheerde maptoegang configureren om** te beschermen tegen ransomware <br/><br/>*[Gecontroleerde maptoegang](/microsoft-365/security/defender-endpoint/controlled-folders) wordt ook wel antiransomwarebeveiliging genoemd.* |[Gecontroleerde maptoegang inschakelen met PowerShell](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**Configureer Microsoft Defender Firewall** om niet-geautoriseerd netwerkverkeer te blokkeren dat in of uit de apparaten van uw organisatie stroomt |[Microsoft Defender Firewall advanced security administration using Windows PowerShell](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|**Versleuteling en BitLocker** configureren om gegevens te beveiligen op de apparaten van uw organisatie met Windows |[BitLocker PowerShell-naslaggids](/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Microsoft Defender voor eindpunt configureren met Windows Management Instrumentation (WMI)

WMI is een scripting-interface waarmee u instellingen kunt ophalen, wijzigen en bijwerken. Zie [WMI gebruiken](/windows/win32/wmisdk/using-wmi)voor meer informatie. 

|Taak  |Informatiebronnen  |
|---------|---------|
|**Beveiliging via de cloud inschakelen** op een apparaat    |[Gebruik Windows Management Instruction (WMI) om beveiliging via de cloud in te stellen](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|**Instellingen voor het ophalen, wijzigen en bijwerken** van Microsoft Defender Antivirus     | [WMI gebruiken om uw gegevens te configureren en Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[De lijst met beschikbare WMI-klassen en voorbeeldscripts bekijken](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>Zie ook de gearchiveerde [Windows Defender WMIv2-providerverwijzingsgegevens](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Microsoft Defender voor eindpunt configureren met Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

Op een afzonderlijk apparaat kunt u een scan uitvoeren, diagnostische tracering starten, controleren op beveiligingsinformatie-updates en meer met behulp van mpcmdrun.exe opdrachtregelprogramma. U vindt het hulpprogramma in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Voer deze uit vanuit een opdrachtprompt.

|Taak  |Informatiebronnen  |
|---------|---------|
|**Beheer Microsoft Defender Antivirus**  |[Uw Microsoft Defender Antivirus configureren en beheren met mpcmdrun.exe](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>Uw Microsoft Defender-beveiligingscentrum

Als u dit nog niet hebt gedaan, configureert u uw **Microsoft Defender-beveiligingscentrum** ( ) om waarschuwingen weer te geven, functies voor bedreigingsbeveiliging te configureren en gedetailleerde informatie weer te geven over de algehele beveiligingsstatus van uw [https://securitycenter.windows.com](https://securitycenter.windows.com) organisatie. 

U kunt ook configureren of en welke functies eindgebruikers kunnen zien in de Microsoft Defender-beveiligingscentrum.

- [Overzicht van de Microsoft Defender-beveiligingscentrum](/microsoft-365/security/defender-endpoint/use)

- [Eindpuntbeveiliging: Microsoft Defender-beveiligingscentrum](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>Volgende stappen

- [Een overzicht van Threat and Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Ga naar het Microsoft Defender-beveiligingscentrum dashboard voor beveiligingsbewerkingen](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Microsoft Defender voor eindpunt beheren met Intune](manage-atp-post-migration-intune.md)
