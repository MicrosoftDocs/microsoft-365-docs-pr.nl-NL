---
title: Diagnostische logboeken
description: Logboeken die kunnen worden verzameld van apparaten tijdens het oplossen van problemen en hoe ze worden opgeslagen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272889"
---
# <a name="diagnostic-logs"></a>Diagnostische logboeken

Wanneer we een probleem oplossen op een apparaat dat wordt beheerd door Microsoft Managed Desktop, of u nu een apparaat hebt gerapporteerd of een apparaat dat door onze service is geïdentificeerd, moeten we mogelijk bepaalde diagnostische logboeken van het apparaat verzamelen zonder tussenkomst van de gebruiker. We verzamelen geen door de gebruiker gegenereerde inhoud of informatie uit gebruikers directories. We verzamelen alleen diagnostische en logboekgegevens die betrekking hebben op de status en status van het apparaat.

We slaan verzamelde logboeken op voor 28 dagen en verwijderen ze vervolgens. Alle logboeken die vanaf een apparaat worden verzameld, worden verwerkt volgens onze standaarden [voor gegevensafhandeling.](privacy-personal-data.md)

## <a name="data-collected"></a>Verzamelde gegevens

Deze lijst bevat alle mappen, gebeurtenislogboeken, uitvoerbare bestanden of registerlocaties waaruit Microsoft Managed Desktop diagnostische logboeken kunnen verzamelen. De werkelijke verzamelde gegevens zijn een subset van deze lijst en zijn afhankelijk van het geïdentificeerde probleem.

### <a name="registry-keys"></a>Registersleutels

- HKLM \\ SYSTEM \\ CurrentControlSet \\ Services
- HKLM \\ SOFTWARE \\ Microsoft \\ Surface
- HKLM \\ SOFTWARE Policies Microsoft Windows \\ \\ \\ \\ WindowsUpdate
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages
- \\HKLM-softwarebeleid \\ \\ Microsoft \\ WindowsStore
- HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ NT \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ NT \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ AppModel
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Appx
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ NT \\ CurrentVersion \\ Superfetch
- HKLM \\ SYSTEM \\ Setup
- HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension
- HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot
- HKLM \\ SOFTWARE Microsoft Windows Advanced Threat \\ \\ Protection
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Authentication \\ \\ LogonUI
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Internet \\ Instellingen
- HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ Uninstall
- \\HKLM-softwarebeleid \\
- HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Cryptography \\ Configuration \\ SSL
- HKLM \\ SOFTWARE Policies Microsoft Windows Advanced Threat \\ \\ \\ Protection
- HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Uninstall
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL

### <a name="commands"></a>Opdrachten

- %programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles
- %windir% \\ system32 \\certutil.exe -store
- %windir% \\ system32 \\certutil.exe -store -user my
- %windir% \\ system32 \\Dsregcmd.exe /status
- %windir% \\ system32 \\ipconfig.exe /all
- %windir% \\ system32 \\ipconfig.exe /displaydns
- %windir% \\ system32 \\mdmdiagnosticstool.exe
- %windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log
- %windir% \\ system32 \\netsh.exe advfirewall show allprofiles
- %windir% \\ system32 \\netsh.exe advfirewall show global
- %windir% \\ system32 \\netsh.exe lan show profiles
- %windir% \\ system32 \\netsh.exe winhttp show proxy
- %windir% \\ system32 \\netsh.exe wlan show profiles
- %windir% \\ system32 \\netsh.exe wlan show wlanreport
- %windir% \\ system32 \\ping.exe -n 50 localhost
- %windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html
- %windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html
- bitsadmin /list /allusers /verbose
- fltMC.exe
- bcdedit /enum all /v
- manage-bde -protectors -get
- Windows PowerShell opdrachten:
    - Get-appxpackage -allusers
    - Get-appxpackage -packagetype bundle
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject -Class \_ win32-product
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32 \_ PnPSignedDriver

### <a name="event-logs"></a>Gebeurtenislogboeken

- Toepassing
- Microsoft-Windows-AppLocker/EXE en DLL
- Microsoft-Windows-AppLocker/MSI en Script
- Microsoft-Windows-AppLocker/Packaged app-Deployment
- Microsoft-Windows-AppLocker/Packaged app-Execution
- Microsoft-Windows-Bitlocker/Bitlocker Management
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operational
- Configuratie
- Systeem

### <a name="files"></a>Bestanden

- %ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ \\ \* Collectoren .etl
- %ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ Logs \\ \* .\*
- %ProgramData% \\ Microsoft Windows Defender Ondersteuning \\ \\ \\MpSupportFiles.cab
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html
- %windir% \\ ccm \\ logs \* .log
- %windir% \\ ccmsetup \\ logs \* .log
- %windir% \\ logs \\ CBS \\ cbs.log
- %windir% \\ logs \\ measuredboot \* .\*
- %windir% \\ Logs \\ WindowsUpdate \* .etl
- %windir% \\ inf \\ \* .log
- %windir% \\ \\ servicesessies \\ActionList.xml
- %windir% \\ \\ servicesessies \\Sessions.xml
- %windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log
- %windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb
- %windir% \\ \\ logt dism \\ dism.log
- %SystemRoot% \\ System32 \\ Winevt \\ Logs\\
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl
- %appdata% \\ Microsoft \\ Teams \\logs.txt
- %windir% \\ Windows \\ System32 \\ winevt \\ \* .\*