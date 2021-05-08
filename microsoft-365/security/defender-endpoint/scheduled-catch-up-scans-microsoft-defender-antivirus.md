---
title: Plan regelmatig snelle en volledige scans met Microsoft Defender Antivirus
description: Terugkerende (geplande) scans instellen, inclusief wanneer ze moeten worden uitgevoerd en of ze als volledige of snelle scans moeten worden uitgevoerd
keywords: quick scan, full scan, quick vs full, schedule scan, daily, weekly, time, scheduled, recurring, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 038818b711400eb16fea89573dc70664a442fc1d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245898"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Geplande snelle of volledige Microsoft Defender Antivirus-scans configureren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Standaard wordt Microsoft Defender Antivirus 15 minuten vóór de tijd van geplande scans gecontroleerd op een update. U kunt [de planning beheren voor wanneer beveiligingsupdates moeten worden gedownload](manage-protection-update-schedule-microsoft-defender-antivirus.md) en toegepast om deze standaard te overschrijven. 

Naast realtime-beveiliging en scans op [](run-scan-microsoft-defender-antivirus.md) aanvraag kunt u ook regelmatige, geplande scans instellen. 

U kunt het type scan configureren, wanneer de scan moet [](manage-protection-updates-microsoft-defender-antivirus.md) plaatsvinden en of de scan moet plaatsvinden na een beveiligingsupdate of als het eindpunt wordt gebruikt. U kunt ook opgeven wanneer speciale scans moeten worden uitgevoerd om herstel te voltooien.

In dit artikel wordt beschreven hoe u geplande scans configureert met groepsbeleid, PowerShell-cmdlets en WMI. U kunt ook planningsscans configureren [met Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) of [Microsoft Intune.](/mem/intune/configuration/device-restrictions-windows-10)

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>De instellingen voor groepsbeleid configureren die in dit artikel worden beschreven

1. Ga op uw groepsbeleidsbeheercomputer in de groepsbeleidseditor naar **Beheersjablonen** voor computerconfiguratie Windows  >    >  **Onderdelen**  >  **Microsoft Defender Antivirus**  >  **scannen.**

2. Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**

3. Geef instellingen op voor het groepsbeleidsobject en selecteer **OK.** 

4. Herhaal stap 1-4 voor elke instelling die u wilt configureren.

5. Implementeer het groepsbeleidsobject zoals u dat normaal doet. Zie Een groepsbeleidsobject maken als u hulp nodig hebt bij [groepsbeleidsobjecten.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

Zie ook de [onderwerpen Beheren wanneer beveiligingsupdates](manage-protection-update-schedule-microsoft-defender-antivirus.md) moeten worden gedownload en toegepast en Voorkomen of [toestaan](configure-local-policy-overrides-microsoft-defender-antivirus.md) dat gebruikers beleidsinstellingen lokaal kunnen wijzigen.

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Snelle scan versus volledige scan en aangepaste scan

Wanneer u geplande scans in stelt, kunt u instellen of de scan een volledige scan of een snelle scan moet zijn.


|Snelle scan  |Volledige scan  | Aangepaste scan |
|---------|---------|---------|
|Een snelle scan bekijkt alle locaties waar malware kan zijn geregistreerd om te beginnen met het systeem, zoals registersleutels en bekende Windows opstartmappen. <p>In de meeste gevallen is een snelle scan voldoende en wordt aanbevolen voor geplande scans. |Een volledige scan begint met een snelle scan en gaat vervolgens verder met een sequentiële bestandsscan van alle vaste schijven en verwisselbare/netwerkstations (als de volledige scan is geconfigureerd om dit te doen). <p>Een volledige scan kan enkele uren of dagen duren, afhankelijk van de hoeveelheid en het type gegevens dat moet worden gescand.<p>Wanneer de volledige scan is voltooid, is er nieuwe beveiligingsinformatie beschikbaar en is een nieuwe scan vereist om ervoor te zorgen dat er geen andere bedreigingen worden gedetecteerd met de nieuwe beveiligingsintelligentie.   | Een aangepaste scan is een snelle scan die wordt uitgevoerd op de bestanden en mappen die u opgeeft. U kunt er bijvoorbeeld voor kiezen om een USB-station of een specifieke map op het lokale station van uw apparaat te scannen. <p> | 

>[!NOTE]
>Standaard worden snelle scans uitgevoerd op geïnstalleerde verwisselbare apparaten, zoals USB-stations.

### <a name="how-do-i-know-which-scan-type-to-choose"></a>Hoe weet ik welk scantype ik moet kiezen?

Gebruik de volgende tabel om een scantype te kiezen.


|Scenario  |Aanbevolen scantype  |
|---------|---------|
|U wilt normale, geplande scans instellen     | Snelle scan <p>Met een snelle scan worden de processen, het geheugen, de profielen en bepaalde locaties op het apparaat gecontroleerd. In combinatie [met realtime-beveiliging](configure-real-time-protection-microsoft-defender-antivirus.md)die altijd wordt gebruikt, biedt een snelle scan een sterke dekking voor malware die begint met het systeem en malware op kernelniveau. Realtime beveiliging controleert bestanden wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map navigeert.         |
|Bedreigingen, zoals malware, worden gedetecteerd op een apparaat     | Volledige scan <p>Een volledige scan kan helpen bepalen of er inactieve onderdelen zijn die een grondigere opruiming vereisen.         |
|U wilt een [scan op aanvraag uitvoeren](run-scan-microsoft-defender-antivirus.md)     | Volledige scan  <p>Een volledige scan bekijkt alle bestanden op de apparaatschijf, inclusief bestanden die verouderd, gearchiveerd en niet dagelijks worden geopend.      |
| U wilt ervoor zorgen dat een draagbaar apparaat, zoals een USB-station, geen malware bevat | Aangepaste scan <p>Met een aangepaste scan kunt u specifieke locaties, mappen of bestanden selecteren en een snelle scan uitvoeren. |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>Wat moet ik nog meer weten over snelle en volledige scans?

- Schadelijke bestanden kunnen worden opgeslagen op locaties die niet zijn opgenomen in een snelle scan. In realtime-beveiliging worden echter alle bestanden die worden geopend en gesloten, en alle bestanden in mappen die door een gebruiker worden geopend, gereviewd. De combinatie van realtimebeveiliging en een snelle scan biedt een sterke bescherming tegen malware.

- On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) help ensure that all the files accessed on the system are being scand with the latest security intelligence and cloud machine learning models.

- Wanneer realtimebeveiliging malware detecteert en de omvang van de getroffen bestanden in eerste instantie niet wordt bepaald, wordt Microsoft Defender Antivirus een volledige scan gestart als onderdeel van het herstelproces.

- Met een volledige scan kunnen schadelijke bestanden worden gedetecteerd die niet zijn gedetecteerd door andere scans, zoals een snelle scan. Een volledige scan kan echter even duren en kostbare systeembronnen gebruiken om deze te voltooien.

- Als een apparaat langere tijd offline is, kan het langer duren om een volledige scan te voltooien. 

## <a name="set-up-scheduled-scans"></a>Geplande scans instellen

Geplande scans worden uitgevoerd op de dag en tijd die u opgeeft. U kunt Groepsbeleid, PowerShell en WMI gebruiken om geplande scans te configureren.

> [!NOTE]
> Als een apparaat wordt losgekoppeld en op de batterij wordt uitgevoerd tijdens een geplande volledige scan, stopt de geplande scan met gebeurtenis 1002, waarin staat dat de scan is gestopt vóór voltooiing. Microsoft Defender Antivirus wordt op de volgende geplande tijd een volledige scan uitgevoerd.

### <a name="use-group-policy-to-schedule-scans"></a>Groepsbeleid gebruiken om scans te plannen

|Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd) |
|:---|:---|:---|:---|
|Scannen | Het scantype opgeven dat moet worden gebruikt voor een geplande scan | Snelle scan |
|Scannen | De dag van de week opgeven om een geplande scan uit te voeren | Geef de dag (of nooit) op om een scan uit te voeren. | Nooit |
|Scannen | De tijd van de dag opgeven om een geplande scan uit te voeren | Geef het aantal minuten na middernacht op (bijvoorbeeld **60** voor 01.00 uur). | 02:00 uur |
|Hoofdmap | Geplande taaktijden willekeurig maken |In Microsoft Defender Antivirus de begintijd van de scan willekeurig instellen op een interval van 0 tot 4 uur. <p>In [SCEP](/mem/intune/protect/certificates-scep-configure)kunt u een willekeurige scan instellen op een interval plus of min 30 minuten. Dit kan handig zijn in virtuele machines of VDI-implementaties. | Ingeschakeld |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>PowerShell-cmdlets gebruiken om scans te plannen

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Gebruik Windows Management Instruction (WMI) om scans te plannen

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


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

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken voor het configureren en uitvoeren van Microsoft Defender Antivirus [defender-cmdlets](/powershell/module/defender/)voor meer informatie.

### <a name="use-windows-management-instruction-wmi"></a>Gebruik Windows Management Instruction (WMI)

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
ScanOnlyIfIdleEnabled
```

Zie voor meer informatie over API's en toegestane parameters [Windows Defender WMIv2-API's.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Configureren wanneer volledige scans moeten worden uitgevoerd om herstel te voltooien

Voor sommige bedreigingen is mogelijk een volledige scan vereist om de verwijdering en herstel ervan te voltooien. U kunt opgeven wanneer deze scans moeten plaatsvinden met Groepsbeleid, PowerShell of WMI.

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

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi"></a>Gebruik Windows Management Instruction (WMI)

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).


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

Zie [PowerShell-cmdlets gebruiken om powershell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) te configureren en uit te voeren Microsoft Defender Antivirus [en Defender-cmdlets](/powershell/module/defender/)voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Gebruik Windows Management Instruction (WMI) om dagelijkse scans te plannen

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
ScanScheduleQuickScanTime
```

Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).


## <a name="enable-scans-after-protection-updates"></a>Scans inschakelen na beveiligingsupdates

U kunt een scan dwingen [](manage-protection-updates-microsoft-defender-antivirus.md) na elke beveiligingsupdate met groepsbeleid.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Groepsbeleid gebruiken om scans te plannen na beveiligingsupdates

|Locatie | Instelling | Beschrijving | Standaardinstelling (indien niet geconfigureerd)|
|:---|:---|:---|:---|
|Handtekeningupdates | Scannen in-/uit-/uit-2014 in- en | Er wordt direct na het downloaden van een nieuwe beveiligingsupdate een scan uitgevoerd | Ingeschakeld |

## <a name="see-also"></a>Zie ook

- [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus-scans op aanvraag configureren en uitvoeren](run-scan-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus-scanopties configureren](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Updates Microsoft Defender Antivirus en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)