---
title: Migreren van hips van derden naar ASR-regels
description: Hier wordt beschreven hoe u een migratie van een HIPS-oplossing (Host Intrusion Prevention System) van derden naar ASR-regels kunt benaderen.
keywords: Attack surface reduction rules, asr, asr rules, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: de65c134560ecca219de9174ff222d31dd578d31
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933779"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>Migreren van hips van derden naar ASR-regels

In dit artikel kunt u algemene regels aan Microsoft Defender voor eindpunten toe te passen.

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>Scenario's bij het migreren van een HIPS-product van derden naar ASR-regels

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Het maken van specifieke bestanden en registersleutels blokkeren

- **Van toepassing op**- Alle processen
- **Bewerking**- Bestandscreatie
- **Voorbeelden van Bestanden/Mappen, Registersleutels/Waarden, Processen, Services**- *.zepto, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab
- **Attack Surface Reduction rules**- ASR rules block the attack techniques and not the Indicators of Compromise (IOC). Het blokkeren van een specifieke bestandsextensie is niet altijd handig, omdat hiermee niet wordt voorkomen dat een apparaat in gevaar komt. Een aanval wordt slechts gedeeltelijk getypt totdat aanvallers een nieuw type extensie voor de payload maken.
- **Andere aanbevolen functies:** Microsoft Defender AV is ingeschakeld, samen met cloudbeveiliging en gedragsanalyse wordt ten zeerste aanbevolen. U wordt aangeraden andere preventie te gebruiken, zoals de ASR-regel 'Geavanceerde beveiliging tegen ransomware gebruiken'. Dit biedt meer bescherming tegen ransomware-aanvallen. Bovendien worden veel van deze registersleutels gecontroleerd door Microsoft Defender voor eindpunten, zoals ASEP-technieken, waardoor specifieke waarschuwingen worden veroorzaakt. Voor de gebruikte registersleutels is een minimum aan bevoegdheden voor lokale beheerders of vertrouwde installatieprogramma's vereist. Het is raadzaam een vergrendelde omgeving te gebruiken met minimale beheerdersaccounts of -rechten. Andere systeemconfiguraties kunnen worden ingeschakeld, zoals 'SeDebug uitschakelen voor niet-vereiste rollen' die deel uitmaken van onze bredere beveiligingsaanbevelingen.

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Het maken van specifieke bestanden en registersleutels blokkeren

- **Van toepassing op**- Alle processen
- **Processen**- N/B
- **Bewerking**- Registerwijzigingen
- **Voorbeelden van bestanden/mappen, registersleutels/waarden, processen, services** -  *\Software*,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File* Execution Options \Debugger, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcess
- **Attack Surface Reduction rules**- ASR rules block the attack techniques and not the Indicators of Compromise (IOC). Het blokkeren van een specifieke bestandsextensie is niet altijd handig, omdat hiermee niet wordt voorkomen dat een apparaat in gevaar komt. Een aanval wordt slechts gedeeltelijk getypt totdat aanvallers een nieuw type extensie voor de payload maken.
- **Andere aanbevolen functies:** Microsoft Defender AV is ingeschakeld, samen met cloudbeveiliging en gedragsanalyse wordt ten zeerste aanbevolen. U wordt aangeraden extra preventie te gebruiken, zoals de ASR-regel 'Geavanceerde beveiliging tegen ransomware gebruiken'. Dit biedt meer bescherming tegen ransomware-aanvallen. Bovendien worden verschillende van deze registersleutels gecontroleerd door Microsoft Defender voor Eindpunt, zoals ASEP-technieken, die specifieke waarschuwingen activeren. Bovendien is voor de gebruikte registersleutels een minimum aan bevoegdheden voor lokale beheerders of vertrouwde installatieprogramma's vereist. Het is raadzaam een vergrendelde omgeving te gebruiken met minimale beheerdersaccounts of -rechten. Andere systeemconfiguraties kunnen worden ingeschakeld, zoals 'SeDebug uitschakelen voor niet-vereiste rollen' die deel uitmaken van onze bredere beveiligingsaanbevelingen.

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>Niet-vertrouwde programma's blokkeren voor het uitvoeren van verwisselbare stations

- **Van toepassing op**- Niet-vertrouwde programma's vanaf USB
- **Processen**- *
- **Bewerking**- Procesuitvoering
- **Voorbeelden van bestanden/mappen, registersleutels/waarden, Processen, Services:-*
- **Surface Reduction-regels** aanvallen: ASR-regels hebben een ingebouwde regel om te voorkomen dat niet-vertrouwde en niet-ondertekende programma's worden uitgevoerd op verwisselbare stations: 'Block untrusted and unsigned processes that run from USB', GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".
- **Andere aanbevolen functies-** Bekijk aanvullende besturingselementen voor USB-apparaten en andere verwisselbare media met Microsoft Defender voor eindpunt: Usb-apparaten en andere verwisselbare media beheren met [Microsoft Defender voor Eindpunt.](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)

### <a name="block-mshta-from-launching-certain-child-processes"></a>Blokkeren dat Mshta bepaalde onderliggende processen start

- **Van toepassing op**- Mshta
- **Processen**- mshta.exe
- **Bewerking**- Procesuitvoering
- **Voorbeelden van Bestanden/mappen, Registersleutels/Waarden, Processen, Services**- powershell.exe, cmd.exe, regsvr32.exe
- **Surface Reduction-regels aanvallen:** ASR-regels bevatten geen specifieke regel om te voorkomen dat onderliggende processen 'mshta.exe'. Dit besturingselement valt onder de taak van Exploit Protection of Windows Defender Application Control.
- **Andere aanbevolen functies:** schakel Windows Defender toepassingsbeheer in om te voorkomen dat mshta.exe worden uitgevoerd. Als uw organisatie 'mshta.exe' voor zakelijke apps vereist, configureert u een specifieke Windows Defender Exploit Protection-regel om te voorkomen dat mshta.exe onderliggende processen start.

### <a name="block-outlook-from-launching-child-processes"></a>Het starten Outlook onderliggende processen blokkeren

- **Is van toepassing op**- Outlook
- **Processen**- outlook.exe
- **Bewerking**- Procesuitvoering
- **Voorbeelden van Bestanden/mappen, Registersleutels/Waarden, Processen, Services**- powershell.exe
- Surface **Reduction-regels** aanvallen: ASR-regels hebben een ingebouwde regel om te voorkomen dat Office communicatie-apps (Outlook, Skype en Teams) onderliggende processen starten: 'Block Office communication application from creating child processes', GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".
- **Andere aanbevolen functies:** u wordt aangeraden de taalmodus voor beperkte PowerShell in te schakelen om het aanvalsoppervlak van PowerShell te minimaliseren.


### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Voorkomen Office apps om onderliggende processen te starten en uitvoerbare inhoud te maken

- **Is van toepassing op**- Office  
- **Processen**: winword.exe, powerpnt.exe, excel.exe
- **Bewerking**- Procesuitvoering
- **Voorbeelden van Bestanden/mappen, Registersleutels/Waarden, Processen, Services**- powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe
- **Surface Reduction-regels** aanvallen: ASR-regels hebben een ingebouwde regel om te voorkomen dat Office-apps onderliggende processen starten: 'Alle Office-toepassingen blokkeren om onderliggende processen te maken', GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A".
- **Andere aanbevolen functies**- N/B
    
### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Voorkomen Office apps om onderliggende processen te starten en uitvoerbare inhoud te maken

- **Is van toepassing op**- Office
- **Processen**: winword.exe, powerpnt.exe, excel.exe
- **Bewerking**- Bestandscreatie
- **Voorbeelden van bestanden/mappen, registersleutels/waarden, Processen,** Services - C:\Gebruikers *\AppData **.exe, C:\ProgramData**.exe, C:\ProgramData**.com, C:\Users* AppData\Local\Temp **.com, C:\Users*\Downloads**.exe, C:\Users *\AppData **.scf, C:\ProgramData**.scf, C:\Users\Public*.exe, C:\Users*\Desktop***.exe
- **Attack Surface Reduction rules**- N/A.

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Wscript blokkeren om bepaalde typen bestanden te lezen

- **Van toepassing op**- Wscript
- **Processen**- wscript.exe
- **Bewerking**- Bestand gelezen
- **Voorbeelden van Bestanden/mappen, Registersleutels/Waarden, Processen, Services**- C:\Gebruikers *\AppData**.js, C:\Gebruikers*\Downloads**.js
- **Surface Reduction-regels aanvallen:** vanwege betrouwbaarheids- en prestatieproblemen kunnen ASR-regels niet voorkomen dat een bepaald proces een bepaald scriptbestandstype leest. Er is wel een regel om te voorkomen dat aanvalsvectoren afkomstig zijn van deze scenario's. De regelnaam is 'JavaScript of VBScript blokkeren om gedownloade uitvoerbare inhoud te starten' (GUID "D3E037E1-3EB8-44C8-A917-57927947596D") en de 'Blokuitvoering van mogelijk obfuscated scripts' (GUID " 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC").
- Andere aanbevolen **functies:** hoewel er specifieke ASR-regels zijn die bepaalde aanvalsvectoren in deze scenario's beperken, is het belangrijk om te vermelden dat AV standaard scripts (PowerShell, Windows Script Host, JavaScript, VBScript en meer) in realtime kan controleren via de Antimalware Scan Interface (AMSI). Meer informatie vindt u hier: [Antimalware Scan Interface (AMSI)](/windows/win32/amsi/antimalware-scan-interface-portal).

### <a name="block-launch-of-child-processes"></a>Start van onderliggende processen blokkeren

- **Is van toepassing op**- Adobe Acrobat
- **Processen**- AcroRd32.exe, Acrobat.exe
- **Bewerking**- Procesuitvoering
- **Voorbeelden van Bestanden/mappen, Registersleutels/Waarden, Processen, Services**- cmd.exe, powershell.exe, wscript.exe
- **Surface Reduction-regels aanvallen:** asr-regels staan het blokkeren van Adobe Reader toe om onderliggende processen te starten. De regelnaam is 'Adobe Reader blokkeren om onderliggende processen te maken', GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c".
- **Andere aanbevolen functies**- N/B


### <a name="block-download-or-creation-of-executable-content"></a>Downloaden of maken van uitvoerbare inhoud blokkeren

- **Van toepassing op**- CertUtil: Download of creatie van uitvoerbaar blokkeren 
- **Processen**- certutil.exe
- **Bewerking**- Bestandscreatie
- **Voorbeelden van Bestanden/mappen, Registersleutels/Waarden, Processen, Services**- *.exe
- **Surface Reduction-regels aanvallen:** ASR-regels ondersteunen deze scenario's niet omdat ze deel uitmaken van Microsoft Defender Antivirus beveiliging.
- **Andere aanbevolen functies:** Microsoft Defender AV voorkomt dat CertUtil uitvoerbare inhoud maakt of downloadt.


### <a name="block-processes-from-stopping-critical-system-components"></a>Voorkomen dat processen kritieke systeemonderdelen stoppen

- **Van toepassing op**- Alle processen
- **Processen**- *
- **Bewerking**- Procesbeëindiging
- Voorbeelden van **Bestanden/mappen, Registersleutels/Waarden, Processen, Services**- MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe*, services.exe, csrss.exe, smss.exe, wininit.exe en meer.
- **Surface Reduction-regels aanvallen:** ASR-regels ondersteunen deze scenario's niet omdat ze zijn beveiligd met Windows 10 ingebouwde beveiligingsbeveiliging.
- **Andere aanbevolen functies:** ELAM (Early Launch AntiMalware), PPL (Protection Process Light), PPL AntiMalware Light en System Guard.

### <a name="block-specific-launch-process-attempt"></a>Specifieke procespoging voor starten blokkeren

- **Van toepassing op**- Specifieke processen
- **Processen**- 'Uw proces een naam geven'
- **Bewerking**- Procesuitvoering
- **Voorbeelden van bestanden/mappen, registersleutels/waarden, processen, services**- tor.exe, bittorrent.exe, cmd.exe, powershell.exe en meer
- **Surface Reduction-regels aanvallen:** over het algemeen zijn ASR-regels niet ontworpen om te functioneren als toepassingsbeheer.
- **Andere aanbevolen functies:** als u wilt voorkomen dat gebruikers specifieke processen of programma's starten, wordt u aangeraden om de toepassingsbeheer Windows Defender gebruiken. Microsoft Defender for Endpoint File and Cert indicators, can be used in a Incident Response scenario (shouldn't be seen as an application control mechanism).
    
### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>Niet-geautoriseerde wijzigingen in Microsoft Defender Antivirus blokkeren

- **Van toepassing op**- Alle processen
- **Processen**- *
- **Bewerking**- Registerwijzigingen
- Voorbeelden van **Bestanden/mappen, Registersleutels/Waarden, Processen, Services**- HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring, en ga zo maar door.
- **Surface Reduction-regels aanvallen:** ASR-regels dekken deze scenario's niet omdat ze deel uitmaken van de ingebouwde beveiliging van Microsoft Defender voor eindpunten.
- Andere aanbevolen **functies:** Tamper Protection (opt-in, beheerd vanuit Intune) voorkomt ongeautoriseerde wijzigingen in DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring en DisableIOAVProtection registry keys (en meer).

Zie ook

- [Veelgestelde vragen over het verminderen van kwetsbaarheid voor aanvallen](attack-surface-reduction-faq.md)
- [Regels voor het verminderen van aanvalsoppervlakken inschakelen](enable-attack-surface-reduction.md)
- [Regels voor het verminderen van kwetsbaarheid voor aanvallen evalueren](evaluate-attack-surface-reduction.md)
