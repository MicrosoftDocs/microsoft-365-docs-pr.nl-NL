---
title: Microsoft Defender Offline in Windows 10
description: U kunt Microsoft Defender Offline rechtstreeks vanuit de Windows Defender Antivirus-app gebruiken. U kunt ook beheren hoe deze wordt geïmplementeerd in uw netwerk.
keywords: scannen, defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1e7e70c6ca217d3ad8859c1493598d71054f84
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765333"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>De resultaten van een Microsoft Defender Offline-scan uitvoeren en bekijken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline is een antimalware scanprogramma waarmee u een scan kunt starten en uitvoeren vanuit een vertrouwde omgeving. De scan wordt uitgevoerd van buiten de normale Windows-kernel, zodat deze zich kan richten op malware die probeert de Windows-shell te omzeilen, zoals virussen en rootkits die de master boot record (MBR) infecteren of overschrijven.

U kunt Microsoft Defender Offline gebruiken als u vermoedt dat er een malware-infectie is, of als u wilt bevestigen dat het eindpunt grondig is opschoond na een malware-uitbraak.

In Windows 10 kan Microsoft Defender Offline met één klik rechtstreeks vanuit de [Windows Security-app worden uitgevoerd.](microsoft-defender-security-center-antivirus.md) In eerdere versies van Windows moest een gebruiker Microsoft Defender Offline installeren om opstartbare media te installeren, het eindpunt opnieuw op te starten en de opstartbare media te laden.

## <a name="prerequisites-and-requirements"></a>vereisten en vereisten

Microsoft Defender Offline in Windows 10 heeft dezelfde hardwarevereisten als Windows 10. 

Zie de volgende onderwerpen voor meer informatie over windows 10-vereisten:

- [Minimale hardwarevereisten](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Richtlijnen voor hardwarecomponenten](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline wordt niet ondersteund op machines ARM processors of op Windows Server Stock Keeping Units.

Als u Microsoft Defender Offline wilt uitvoeren vanaf het eindpunt, moet de gebruiker zijn aangemeld met beheerdersbevoegdheden.
 
## <a name="microsoft-defender-offline-updates"></a>Offlineupdates van Microsoft Defender

Microsoft Defender Offline gebruikt de meest recente beveiligingsupdates die beschikbaar zijn op het eindpunt. deze wordt bijgewerkt wanneer Windows Defender Antivirus wordt bijgewerkt. 

> [!NOTE]
> Voordat u een offlinescan uitwerkt, moet u proberen microsoft Defender AV-beveiliging bij te werken. U kunt een update met groepsbeleid forcen of updates naar eindpunten implementeren, of u kunt handmatig de meest recente beveiligingsupdates downloaden en installeren vanuit het [Microsoft Malware Protection Center.](https://www.microsoft.com/security/portal/definitions/adl.aspx)

Zie het [onderwerp Updates van Microsoft Defender Antivirus Security Intelligence beheren](manage-protection-updates-microsoft-defender-antivirus.md) voor meer informatie.

## <a name="usage-scenarios"></a>Gebruiksscenario's

In Windows 10, versie 1607, kunt u handmatig een offlinescan forcen. Als Windows Defender bepaalt dat Microsoft Defender Offline moet worden uitgevoerd, wordt de gebruiker op het eindpunt gevraagd. 

De noodzaak om een offlinescan uit te voeren, wordt ook in Microsoft Endpoint Manager onthuld als u deze gebruikt om uw eindpunten te beheren.

De prompt kan optreden via een melding, vergelijkbaar met de volgende:

![Windows-melding met de vereiste om Microsoft Defender Offline uit te voeren](images/defender/notification.png)

De gebruiker krijgt ook een melding binnen de Windows Defender-client.

In Configuration Manager kunt u de status van eindpunten identificeren door te navigeren naar Monitoring **> Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**. 

Microsoft Defender Offline scans worden aangegeven onder **Malware herstelstatus** als **Offline scannen vereist**.

![Microsoft Endpoint Manager die aangeeft dat een Microsoft Defender Offline-scan is vereist](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>Meldingen configureren

Microsoft Defender Offline-meldingen zijn geconfigureerd in dezelfde beleidsinstelling als andere AV-meldingen van Microsoft Defender.

Zie de meldingen configureren die worden weergegeven in het onderwerp Eindpunten voor meer [informatie](configure-notifications-microsoft-defender-antivirus.md) over meldingen in Windows Defender.

## <a name="run-a-scan"></a>Een scan uitvoeren 

> [!IMPORTANT]
> Voordat u Microsoft Defender Offline gebruikt, moet u bestanden opslaan en lopende programma's afsluiten. De offlinescan van Microsoft Defender duurt ongeveer 15 minuten. Het eindpunt wordt opnieuw gestart wanneer de scan is voltooid. De scan wordt uitgevoerd buiten de gebruikelijke Windows-besturingssysteemomgeving. De gebruikersinterface wordt anders weergegeven dan een normale scan die wordt uitgevoerd door Windows Defender. Nadat de scan is voltooid, wordt het eindpunt opnieuw gestart en wordt Windows normaal geladen.

U kunt een Microsoft Defender Offline-scan uitvoeren met de volgende opties:

- PowerShell
- Windows Management Instrumentation (WMI)
- De Windows Security-app



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>PowerShell-cmdlets gebruiken om een offlinescan uit te voeren

Gebruik de volgende cmdlets:

```PowerShell
Start-MpWDOScan
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus- en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Windows Management Instruction (WMI) gebruiken om een offlinescan uit te voeren

Gebruik de [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) om een offlinescan uit te voeren.

In het volgende WMI-scriptfragment wordt onmiddellijk een Microsoft Defender Offline-scan uitgevoerd, waardoor het eindpunt opnieuw wordt gestart, de offlinescan wordt uitgevoerd en vervolgens opnieuw wordt gestart en opgestart in Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Zie het volgende voor meer informatie:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>De Windows Defender-beveiligingsapp gebruiken om een offlinescan uit te voeren

1. Open de Windows Security-app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **Defender.**

2. Klik op **de tegel & virusbeveiliging** (of het schildpictogram op de linkermenubalk) en klik vervolgens op **het** label Geavanceerd scannen:
    
3. Selecteer **Microsoft Defender Offline scannen** en klik op Nu **scannen.**

    > [!NOTE]
    > In Windows 10, versie 1607, kan de offlinescan worden uitgevoerd onder **Windows Settings** Update & security Windows Defender of vanuit de  >    >   Windows Defender-client.


## <a name="review-scan-results"></a>Scanresultaten controleren

Microsoft Defender Offline scanresultaten worden weergegeven in de [sectie Scangeschiedenis van de Windows Security-app.](microsoft-defender-security-center-antivirus.md) 


## <a name="related-articles"></a>Verwante artikelen

- [De resultaten van scans en herstel aanpassen, starten en controleren](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)