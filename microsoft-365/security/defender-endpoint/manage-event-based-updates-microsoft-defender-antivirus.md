---
title: Updates Microsoft Defender Antivirus na bepaalde gebeurtenissen toepassen
description: Beheer hoe Microsoft Defender Antivirus beveiligingsintelligentie-updates na het opstarten of ontvangen van door de cloud geleverde detectierapporten.
keywords: updates, beveiliging, force updates, gebeurtenissen, opstarten, controleren op recentste, meldingen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82aff7adedc9e490520851ad8c8e87fad60abf0a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926077"
---
# <a name="manage-event-based-forced-updates"></a>Op basis van gebeurtenissen afgedwongen updates beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus kunt u bepalen of updates wel (of niet) moeten plaatsvinden na bepaalde gebeurtenissen, zoals bij het opstarten of na het ontvangen van specifieke rapporten van de door de cloud geleverde beveiligingsservice.

## <a name="check-for-protection-updates-before-running-a-scan"></a>Controleren op beveiligingsupdates voordat u een scan gaat uitvoeren

U kunt Microsoft Endpoint Configuration Manager, Groepsbeleid, PowerShell-cmdlets en WMI gebruiken om Microsoft Defender Antivirus beveiligingsupdates te controleren en downloaden voordat u een geplande scan uit te voeren.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Configuration Manager gebruiken om te controleren op beveiligingsupdates voordat u een scan gaat uitvoeren

1. Open op Microsoft Endpoint Manager console het antimalwarebeleid dat u wilt wijzigen (klik **op** Activa en naleving in het navigatiedeelvenster aan de linkerkant en vouw de structuur uit naar Overzicht  >  **Endpoint Protection**  >  **Antimalware-beleid**)

2. Ga naar de **sectie Geplande scans** en stel Controleren op de meest recente **beveiligingsinformatie-updates in voordat u een scan op** Ja gaat **uitvoeren.**

3. Klik op **OK**.

4. [Implementeer het bijgewerkte beleid zoals gewoonlijk.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>Groepsbeleid gebruiken om te controleren op beveiligingsupdates voordat u een scan gaat uitvoeren

1. Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beleid** en vervolgens op **Beheersjablonen.**

4. Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Scannen.**

5. Dubbelklik op **Controleren op de meest recente virus-** en spywaredefinities voordat u een geplande scan gaat uitvoeren en stel de optie in **op Ingeschakeld.**

6. Klik op **OK**.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>PowerShell-cmdlets gebruiken om te controleren op beveiligingsupdates voordat u een scan gaat uitvoeren

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

Zie [PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te configureren en uit te voeren](use-powershell-cmdlets-microsoft-defender-antivirus.md) en [Defender-cmdlets](/powershell/module/defender/index) voor meer informatie.

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Gebruik Windows Management Instruction (WMI) om te controleren op beveiligingsupdates voordat u een scan gaat uitvoeren

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
CheckForSignaturesBeforeRunningScan
```

Zie voor meer informatie [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="check-for-protection-updates-on-startup"></a>Controleren op beveiligingsupdates bij opstarten

U kunt groepsbeleid gebruiken om Microsoft Defender Antivirus beveiligingsupdates te controleren en downloaden wanneer de computer wordt gestart.

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beleid** en vervolgens op **Beheersjablonen.**

4. Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Beveiligingsinformatieupdates.**

5. Dubbelklik bij het opstarten op Controleren op de meest recente **virus-** en spywaredefinities en stel de optie in **op Ingeschakeld.** 

6. Klik op **OK**.

U kunt ook Groepsbeleid, PowerShell of WMI gebruiken om Microsoft Defender Antivirus te configureren om te controleren op updates bij het opstarten, zelfs wanneer het programma niet wordt uitgevoerd.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Groepsbeleid gebruiken om updates te downloaden wanneer Microsoft Defender Antivirus niet aanwezig is

1. Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga met **de Groepsbeleidsbeheereditor** naar **Computerconfiguratie.**

3. Klik **op Beleid** en vervolgens op **Beheersjablonen.**

4. Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Beveiligingsinformatieupdates.**

5. Dubbelklik bij **het opstarten op Beveiligingsinformatieupdate starten** en stel de optie in op **Ingeschakeld.**

6. Klik op **OK**.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>PowerShell-cmdlets gebruiken om updates te downloaden wanneer Microsoft Defender Antivirus niet aanwezig is

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/index) te beheren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Gebruik Windows Management Instruction (WMI) om updates te downloaden wanneer Microsoft Defender Antivirus niet aanwezig is

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

Zie voor meer informatie [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>Ad-hocwijzigingen toestaan voor beveiliging op basis van beveiliging in de cloud

Microsoft Defender AV kan wijzigingen aanbrengen in de beveiliging op basis van beveiliging in de cloud. Dergelijke wijzigingen kunnen optreden buiten normale of geplande beveiligingsupdates.

Als u beveiliging via de cloud hebt ingeschakeld, stuurt Microsoft Defender AV bestanden die verdacht zijn naar de Windows Defender cloud. Als de cloudservice meldt dat het bestand schadelijk is en het bestand wordt gedetecteerd in een recente beveiligingsupdate, kunt u Groepsbeleid gebruiken om Microsoft Defender AV zo te configureren dat deze beveiligingsupdate automatisch wordt ontvangen. Andere belangrijke beveiligingsupdates kunnen ook worden toegepast.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>Groepsbeleid gebruiken om recente updates automatisch te downloaden op basis van beveiliging in de cloud

1. Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beleid** en vervolgens op **Beheersjablonen.**

4. Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Beveiligingsinformatieupdates.**

5. Dubbelklik op **Updates voor realtime beveiligingsinformatie toestaan** op basis van rapporten in Microsoft MAPS en stel de optie in op **Ingeschakeld.** Klik daarna op **OK**.

6. **Meldingen toestaan om rapporten op basis van definities uit** te schakelen in Microsoft MAPS en de optie in te stellen op **Ingeschakeld.** Klik daarna op **OK**.
    
> [!NOTE]
> **Als u meldingen toestaat om rapporten op basis van definities** uit te schakelen, kan Microsoft MAPS de definities uitschakelen die bekend staan als fout-positieve rapporten. U moet uw computer zo configureren dat u deel kunt nemen aan Microsoft MAPS, om deze functie te laten werken.

## <a name="see-also"></a>Zie ook

- [Implementatie van Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Updates Microsoft Defender Antivirus en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Updates beheren voor mobiele apparaten en virtuele machines (VM's)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)