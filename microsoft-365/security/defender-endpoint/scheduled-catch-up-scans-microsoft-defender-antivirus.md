---
title: Regelmatige snelle en volledige scans plannen met Microsoft Defender Antivirus
description: Terugkerende (geplande) scans instellen, inclusief wanneer ze moeten worden uitgevoerd en of ze als volledige of snelle scans moeten worden uitgevoerd
keywords: quick scan, full scan, quick vs full, schedule scan, daily, weekly, time, scheduled, recurring, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690629"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Geplande snelle of volledige Microsoft Defender Antivirus-scans configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Standaard wordt in Microsoft Defender Antivirus 15 minuten vóór de tijd van geplande scans gecontroleerd op een update. U kunt [de planning beheren voor wanneer beveiligingsupdates moeten worden gedownload](manage-protection-update-schedule-microsoft-defender-antivirus.md) en toegepast om deze standaard te overschrijven. 

Naast realtime-beveiliging en scans op [](run-scan-microsoft-defender-antivirus.md) aanvraag kunt u ook regelmatige, geplande scans instellen. 

U kunt het type scan configureren, wanneer de scan moet [](manage-protection-updates-microsoft-defender-antivirus.md) plaatsvinden en of de scan moet plaatsvinden na een beveiligingsupdate of als het eindpunt wordt gebruikt. U kunt ook opgeven wanneer speciale scans moeten worden uitgevoerd om herstel te voltooien.

In dit artikel wordt beschreven hoe u geplande scans configureert met groepsbeleid, PowerShell-cmdlets en WMI. U kunt ook planningsscans configureren met [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) of Microsoft [Intune.](/mem/intune/configuration/device-restrictions-windows-10)

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>De instellingen voor groepsbeleid configureren die in dit artikel worden beschreven

1.  Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

3.  Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

4.  Klik **op Beheersjablonen.**

5.  Vouw de structuur uit **naar Windows-onderdelen > Microsoft Defender Antivirus** en vervolgens de locatie die is opgegeven in de onderstaande tabel. 

6. Dubbelklik op de **beleidsinstelling** zoals aangegeven in de onderstaande tabel en stel de optie in op de gewenste configuratie. 

7. Klik **op OK** en herhaal dit voor andere instellingen.

Zie ook de [onderwerpen Beheren wanneer beveiligingsupdates](manage-protection-update-schedule-microsoft-defender-antivirus.md) moeten worden gedownload en toegepast en Voorkomen of [toestaan](configure-local-policy-overrides-microsoft-defender-antivirus.md) dat gebruikers beleidsinstellingen lokaal kunnen wijzigen.

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Snelle scan versus volledige scan en aangepaste scan

Wanneer u geplande scans in stelt, kunt u instellen of de scan een volledige scan of een snelle scan moet zijn.

Snelle scans bekijken alle locaties waar malware kan zijn geregistreerd om te beginnen met het systeem, zoals registersleutels en bekende opstartmappen van Windows. 

In combinatie met de [altijd-on-realtimebeveiligingsfunctie](configure-real-time-protection-microsoft-defender-antivirus.md) , die bestanden controleert wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map navigeert, biedt een snelle scan een sterke dekking voor malware die begint met het systeem en malware op kernelniveau.  

In de meeste gevallen betekent dit dat een snelle scan voldoende is om malware te vinden die niet is opgehaald door realtime beveiliging.

Een volledige scan kan handig zijn voor eindpunten die een malware-bedreiging hebben ondervonden om te bepalen of er inactieve onderdelen zijn die een grondigere opruiming vereisen. In dit geval wilt u mogelijk een volledige scan gebruiken bij het uitvoeren van een [on-demand scan.](run-scan-microsoft-defender-antivirus.md)

Met een aangepaste scan kunt u de bestanden en mappen opgeven die u wilt scannen, zoals een USB-station. 

>[!NOTE]
>Standaard worden snelle scans uitgevoerd op geïnstalleerde verwisselbare apparaten, zoals USB-stations.

## <a name="set-up-scheduled-scans"></a>Geplande scans instellen

Geplande scans worden uitgevoerd op de dag en tijd die u opgeeft. U kunt Groepsbeleid, PowerShell en WMI gebruiken om geplande scans te configureren.

>[!NOTE]
>Als een computer is losgekoppeld en tijdens een geplande volledige scan op de batterij werkt, stopt de geplande scan met gebeurtenis 1002, waarin staat dat de scan is gestopt vóór voltooiing. Microsoft Defender Antivirus zal een volledige scan uitvoeren op de volgende geplande tijd.

### <a name="use-group-policy-to-schedule-scans"></a>Groepsbeleid gebruiken om scans te plannen

|Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd) |
|:---|:---|:---|:---|
|Scannen | Het scantype opgeven dat moet worden gebruikt voor een geplande scan | Snelle scan |
|Scannen | De dag van de week opgeven om een geplande scan uit te voeren | Geef de dag (of nooit) op om een scan uit te voeren. | Nooit |
|Scannen | De tijd van de dag opgeven om een geplande scan uit te voeren | Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur). | 02:00 uur |
|Hoofdmap | Geplande taaktijden willekeurig maken |In Microsoft Defender Antivirus: De begintijd van de scan willekeurig instellen op een interval van 0 tot 4 uur. <br>In FEP/SCEP: randomize to any interval plus or minus 30 minutes. Dit kan handig zijn in VM- of VDI-implementaties. | Ingeschakeld |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>PowerShell-cmdlets gebruiken om scans te plannen

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Windows Management Instruction (WMI) gebruiken om scans te plannen

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Zie het volgende voor meer informatie en toegestane parameters:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>Geplande scans alleen starten als het eindpunt niet wordt gebruikt

U kunt instellen dat de geplande scan alleen wordt uitgevoerd wanneer het eindpunt is ingeschakeld, maar niet wordt gebruikt met Groepsbeleid, PowerShell of WMI.

> [!NOTE]
> Met deze scans wordt de configuratie voor het beperken van cpu's niet in ere gehouden en wordt optimaal gebruik gemaakt van de beschikbare bronnen om de scan zo snel mogelijk te voltooien.

### <a name="use-group-policy-to-schedule-scans"></a>Groepsbeleid gebruiken om scans te plannen

|Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd) |
|:---|:---|:---|:---|
|Scannen | De geplande scan alleen starten wanneer de computer is aan, maar niet in gebruik is | Geplande scans worden niet uitgevoerd, tenzij de computer is aan maar niet in gebruik is | Ingeschakeld |

### <a name="use-powershell-cmdlets"></a>PowerShell-cmdlets gebruiken

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi"></a>Windows Management Instruction (WMI) gebruiken

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
ScanOnlyIfIdleEnabled
```

Zie het volgende voor meer informatie en toegestane parameters:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Configureren wanneer volledige scans moeten worden uitgevoerd om herstel te voltooien

Voor sommige bedreigingen is mogelijk een volledige scan vereist om de verwijdering en herstel ervan te voltooien. U kunt plannen wanneer deze scans moeten plaatsvinden met Groepsbeleid, PowerShell of WMI.

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>Groepsbeleid gebruiken om herstel-vereiste scans te plannen

| Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd) |
|---|---|---|---|
|Herstellen | Geef de dag van de week op om een geplande volledige scan uit te voeren om herstel te voltooien | Geef de dag (of nooit) op om een scan uit te voeren. | Nooit |
|Herstellen | Geef de tijd van de dag op om een geplande volledige scan uit te voeren om de hersteltijd te voltooien | Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur) | 02:00 uur |

### <a name="use-powershell-cmdlets"></a>PowerShell-cmdlets gebruiken

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi"></a>Windows Management Instruction (WMI) gebruiken

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Zie het volgende voor meer informatie en toegestane parameters:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a>Dagelijkse snelle scans instellen

U kunt een dagelijkse snelle scan inschakelen die kan worden uitgevoerd naast uw andere geplande scans met Groepsbeleid, PowerShell of WMI.


### <a name="use-group-policy-to-schedule-daily-scans"></a>Groepsbeleid gebruiken om dagelijkse scans te plannen


|Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd) |
|:---|:---|:---|:---|
|Scannen | Geef het interval op om snelle scans per dag uit te voeren | Geef op hoeveel uren moeten worden verstreken vóór de volgende snelle scan. Als u bijvoorbeeld elke twee uur wilt uitvoeren, typt u **2**, voor één keer per dag, voert u **24 in.** Voer **0 in** om nooit een dagelijkse quick scan uit te voeren. | Nooit |
|Scannen | De tijd voor een dagelijkse snelle scan opgeven | Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur) | 02:00 uur |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>PowerShell-cmdlets gebruiken om dagelijkse scans te plannen

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Windows Management Instruction (WMI) gebruiken om dagelijkse scans te plannen

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
ScanScheduleQuickScanTime
```

Zie het volgende voor meer informatie en toegestane parameters:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>Scans inschakelen na beveiligingsupdates

U kunt een scan dwingen [](manage-protection-updates-microsoft-defender-antivirus.md) na elke beveiligingsupdate met groepsbeleid.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Groepsbeleid gebruiken om scans te plannen na beveiligingsupdates

|Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd)|
|:---|:---|:---|:---|
|Handtekeningupdates | Scannen in-/uit-/uit-2014 in- en | Er wordt direct na het downloaden van een nieuwe beveiligingsupdate een scan uitgevoerd | Ingeschakeld |

## <a name="see-also"></a>Zie ook
- [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [On-demand Microsoft Defender Antivirus scans configureren en uitvoeren](run-scan-microsoft-defender-antivirus.md)
- [Scanopties voor Microsoft Defender Antivirus configureren](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus-updates beheren en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)