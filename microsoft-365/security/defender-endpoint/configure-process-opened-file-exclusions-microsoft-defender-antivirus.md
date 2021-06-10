---
title: Uitsluitingen configureren voor bestanden die door specifieke processen zijn geopend
description: U kunt bestanden uitsluiten van scans als ze zijn geopend door een specifiek proces.
keywords: Microsoft Defender Antivirus, proces, uitsluiting, bestanden, scans
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2fdc646cf616ff6a6fa36a83be3d2b1dd0432fbe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274608"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>Uitsluitingen configureren voor bestanden die door processen zijn geopend

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt bestanden die door specifieke processen zijn geopend, uitsluiten van Microsoft Defender Antivirus scans. Zie Aanbevelingen voor het definiëren van uitsluitingen voordat u uw [uitsluitingslijsten](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) definieert.

In dit artikel wordt beschreven hoe u uitsluitingslijsten configureert. 

## <a name="examples-of-exclusions"></a>Voorbeelden van uitsluitingen

|Uitsluiting | Voorbeeld |
|---|---|
|Elk bestand op de computer dat wordt geopend door een proces met een specifieke bestandsnaam | Als u `test.exe` opgeeft, worden bestanden die worden geopend, uitgesloten door: <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|Een bestand op de computer dat wordt geopend door een proces onder een specifieke map | Als u `c:\test\sample\*` opgeeft, worden bestanden die worden geopend, uitgesloten door:<br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|Een bestand op de computer dat wordt geopend door een specifiek proces in een specifieke map | Als u `c:\test\process.exe` opgeeft, worden bestanden alleen geopend door `c:\test\process.exe` |


Wanneer u een proces toevoegt aan de lijst met procesuitsluitingen, worden Microsoft Defender Antivirus bestanden die door dat proces worden geopend niet gescand, ongeacht waar de bestanden zich bevinden. Het proces zelf wordt echter gescand, tenzij het ook is toegevoegd aan de lijst met [bestandsuitsluitingen.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

De uitsluitingen zijn alleen van toepassing op realtime-beveiliging en -monitoring in [realtime.](configure-real-time-protection-microsoft-defender-antivirus.md) Ze zijn niet van toepassing op geplande of on-demand scans.

Wijzigingen die zijn aangebracht met groepsbeleid in de uitsluitingslijsten, worden **in** de lijsten in de [Windows-beveiliging app.](microsoft-defender-security-center-antivirus.md) Wijzigingen die zijn aangebracht in de Windows-beveiliging worden **echter niet in** de lijsten met groepsbeleidslijsten vermeld.

U kunt lijsten toevoegen, verwijderen en controleren op uitsluitingen in groepsbeleid, Microsoft Endpoint Configuration Manager, Microsoft Intune en met de Windows-beveiliging-app en u kunt jokertekens gebruiken om de lijsten verder aan te passen.

U kunt ook PowerShell-cmdlets en WMI gebruiken om de uitsluitingslijsten te configureren, inclusief het controleren van uw lijsten.

Standaard worden lokale wijzigingen in de lijsten (door gebruikers met beheerdersbevoegdheden; wijzigingen aangebracht met PowerShell en WMI) samengevoegd met de lijsten zoals gedefinieerd (en geïmplementeerd) door Groepsbeleid, Configuratiebeheer of Intune. De lijsten met groepsbeleid hebben voorrang bij conflicten.

U kunt [configureren hoe lijsten met](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) lokaal en globaal gedefinieerde uitsluitingen worden samengevoegd, zodat lokale wijzigingen de beheerde implementatie-instellingen kunnen overschrijven.

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>De lijst met uitsluitingen configureren voor bestanden die zijn geopend met opgegeven processen

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Gebruik Microsoft Intune om bestanden die zijn geopend door opgegeven processen uit scans uit te sluiten

Zie [Instellingen voor apparaatbeperkingen configureren in Microsoft Intune](/intune/device-restrictions-configure) en [Microsoft Defender Antivirus-apparaatbeperkingsinstellingen voor Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) voor meer informatie.

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Gebruik Microsoft Endpoint Manager om bestanden die zijn geopend door opgegeven processen uit scans uit te sluiten

Zie [Antimalware-beleid](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) maken en implementeren: Uitsluitingsinstellingen voor meer informatie over het configureren van Microsoft Endpoint Manager (huidige vertakking).

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Groepsbeleid gebruiken om bestanden die zijn geopend door opgegeven processen uit scans uit te sluiten

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**

3. Vouw de boom uit **Windows onderdelen > Microsoft Defender Antivirus > Uitsluitingen.**

4. Dubbelklik op **Uitsluitingen verwerken** en voeg de uitsluitingen toe:

    1. Stel de optie in op **Ingeschakeld.**
    2. Klik onder **de** sectie Opties op **Toon...**.
    3. Voer elk proces op een eigen regel in onder de kolom **Waardenaam.** Zie de voorbeeldtabel voor de verschillende typen uitsluitingen van processen.  Voer **0** in de kolom **Waarde** in voor alle processen.

5. Klik op **OK**.

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>PowerShell-cmdlets gebruiken om bestanden die door bepaalde processen zijn geopend, uit te sluiten van scans

Als u PowerShell gebruikt om uitsluitingen toe te voegen of te verwijderen voor bestanden die door processen zijn geopend, moet u een combinatie van drie cmdlets met de `-ExclusionProcess` parameter gebruiken. De cmdlets zijn allemaal in de [Defender-module.](/powershell/module/defender/)

De indeling voor de cmdlets is:

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

De volgende opties zijn toegestaan \<cmdlet> als:

|Configuratieactie | PowerShell-cmdlet |
|---|---|
|De lijst maken of overschrijven | `Set-MpPreference` |
|Toevoegen aan de lijst | `Add-MpPreference` |
|Items uit de lijst verwijderen | `Remove-MpPreference` |

>[!IMPORTANT]
>Als u een lijst hebt gemaakt, met of , wordt de bestaande lijst opnieuw overschreven door de `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` cmdlet te gebruiken.

Het volgende codefragment zorgt er bijvoorbeeld voor dat microsoft Defender AV-scans een bestand uitsluiten dat wordt geopend door het opgegeven proces:

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Zie Antivirus beheren met PowerShell-cmdlets en Microsoft Defender Antivirus [cmdlets](/powershell/module/defender)voor meer informatie over het gebruik Microsoft Defender Antivirus PowerShell.

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Gebruik Windows Management Instruction (WMI) om bestanden die zijn geopend door opgegeven processen uit scans uit te sluiten

Gebruik de [ **methoden Set,** **Add** en **Remove** van](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) de MSFT_MpPreference voor de volgende eigenschappen:

```WMI
ExclusionProcess
```

Het gebruik van **Set,** **Add** en **Remove** is vergelijkbaar met hun tegenhangers in PowerShell: `Set-MpPreference` , en `Add-MpPreference` `Remove-MpPreference` .

Zie voor meer informatie en toegestane parameters [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Gebruik de Windows-beveiliging app om bestanden die zijn geopend door opgegeven processen uit scans uit te sluiten

Zie [Uitsluitingen toevoegen in de Windows-beveiliging app](microsoft-defender-security-center-antivirus.md) voor instructies.

## <a name="use-wildcards-in-the-process-exclusion-list"></a>Jokertekens gebruiken in de lijst met procesuitsluitingen

Het gebruik van jokertekens in de lijst met procesuitsluitingen verschilt van het gebruik ervan in andere uitsluitingslijsten.

U kunt met name het jokerteken vraagteken () niet gebruiken en het `?` sterretje () jokerteken kan alleen worden gebruikt aan het einde `*` van een volledig pad. U kunt nog steeds omgevingsvariabelen (zoals ) als jokertekens gebruiken bij het definiëren van `%ALLUSERSPROFILE%` items in de lijst met procesuitsluitingen.

In de volgende tabel wordt beschreven hoe de jokertekens kunnen worden gebruikt in de lijst met uitsluitingen van processen:

|Jokerteken | Voorbeeldgebruik | Voorbeeld van overeenkomsten |
|:---|:---|:---|
|`*` (sterretje) <br/><br/> Vervangt een aantal tekens | `C:\MyData\*` | Een bestand dat wordt geopend door `C:\MyData\file.exe` |
|Omgevingsvariabelen <br/><br/> De gedefinieerde variabele wordt ingevuld als een pad wanneer de uitsluiting wordt geëvalueerd | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | Een bestand dat wordt geopend door `C:\ProgramData\CustomLogFiles\file.exe` |

## <a name="review-the-list-of-exclusions"></a>De lijst met uitsluitingen bekijken

U kunt de items in de uitsluitingslijst ophalen met MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)of de [Windows-beveiliging app.](microsoft-defender-security-center-antivirus.md)

Als u PowerShell gebruikt, kunt u de lijst op twee manieren ophalen:

- De status van alle Microsoft Defender Antivirus ophalen. Elk van de lijsten wordt weergegeven op afzonderlijke regels, maar de items in elke lijst worden gecombineerd tot dezelfde regel.
- Schrijf de status van alle voorkeuren op een variabele en gebruik deze variabele om alleen de specifieke lijst te bellen waarin u geïnteresseerd bent. Elk gebruik van `Add-MpPreference` is geschreven naar een nieuwe regel.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>De uitsluitingslijst valideren met MpCmdRun

Als u uitsluitingen wilt controleren met de speciale [opdrachtregelfunctie mpcmdrun.exe, ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)gebruikt u de volgende opdracht:

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> Voor het controleren van uitsluitingen met MpCmdRun Microsoft Defender Antivirus CAMP-versie 4.18.1812.3 (uitgebracht in december 2018) of hoger.


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Bekijk de lijst met uitsluitingen naast alle andere Microsoft Defender Antivirus met PowerShell

Gebruik de volgende cmdlet:

```PowerShell
Get-MpPreference
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Een specifieke lijst met uitsluitingen ophalen met PowerShell

Gebruik het volgende codefragment (voer elke regel in als een afzonderlijke opdracht); vervang **WDAVprefs door** het label dat u de variabele wilt noemen:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

## <a name="related-articles"></a>Aanverwante artikelen

- [Uitsluitingen configureren en valideren in Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md)
- [Uitsluitingen configureren en valideren op basis van bestandsnaam, extensie en maplocatie](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Uitsluitingen Microsoft Defender Antivirus configureren op Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [De resultaten van scans en herstel van Microsoft Defender Antivirus aanpassen, starten en controleren](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)