---
title: De opdrachtregel gebruiken om Microsoft Defender Antivirus te beheren
description: Voer Microsoft Defender Antivirus-scans uit en configureer beveiliging van de volgende generatie met een speciaal hulpprogramma voor opdrachtregel.
keywords: Windows Defender-scan uitvoeren, antivirusscan uitvoeren vanaf opdrachtregel, Windows Defender-scan uitvoeren vanaf opdrachtregel, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 1b357f7c1e02211f3949383a380666cb7444f814
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764625"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Microsoft Defender Antivirus configureren en beheren met mpcmdrun.exe opdrachtregelprogramma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt verschillende Microsoft Defender Antivirus-functies uitvoeren met het speciale opdrachtregelprogramma **mpcmdrun.exe.** Dit hulpprogramma is handig als u het gebruik van Microsoft Defender Antivirus wilt automatiseren. U vindt het hulpprogramma in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . U moet deze uitvoeren vanuit een opdrachtprompt.

> [!NOTE]
> Mogelijk moet u een versie op beheerdersniveau van de opdrachtprompt openen. Wanneer u in het menu **Start naar opdrachtprompt** zoekt, kiest u **Uitvoeren als beheerder.**
> Als u een bijgewerkte Versie van het Microsoft Defender-platform gebruikt, kunt u vanaf `**MpCmdRun**` de volgende locatie uitvoeren: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .

Het hulpprogramma heeft de volgende opdrachten:

```console
MpCmdRun.exe [command] [-options]
```
Hier is een voorbeeld:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| Opdracht  | Beschrijving   |
|:----|:----|
| `-?`**of**`-h`   | Hiermee worden alle beschikbare opties voor dit hulpprogramma weergegeven |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Scant op schadelijke software. Waarden voor **ScanType** zijn: **0** Standaard, volgens uw configuratie, **-1** Snelle scan, **-2** Volledige scan, **-3** Aangepaste scan van bestand en adreslijst.  CpuThrottling zal de geconfigureerde CPU-beperking van beleid eren |
| `-Trace [-Grouping #] [-Level #]` | Diagnostische tracering starten |
| `-GetFiles [-SupportLogLocation <path>]` | Verzamelt ondersteuningsgegevens. Zie['diagnostische gegevens verzamelen'](collect-diagnostic-data.md)  |
| `-GetFilesDiagTrack`  | Hetzelfde als `-GetFiles` , maar wordt uitgevoerd naar een tijdelijke DiagTrack-map |
| `-RemoveDefinitions [-All]` | Herstelt de geïnstalleerde beveiligingsinformatie naar een vorige back-upkopie of naar de oorspronkelijke standaardset |
| `-RemoveDefinitions [-DynamicSignatures]` | Verwijdert alleen de dynamisch gedownloade beveiligingsinformatie |
| `-RemoveDefinitions [-Engine]` | Herstelt de vorige geïnstalleerde engine |
| `-SignatureUpdate [-UNC \| -MMPC]` | Controleert op nieuwe beveiligingsinformatie-updates |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | Herstelt of lijsten met in quarantaine geplaatste items(en) |
| `-AddDynamicSignature [-Path]` | Dynamische beveiligingsintelligentie laden |
| `-ListAllDynamicSignatures` | Bevat de geladen dynamische beveiligingsinformatie |
| `-RemoveDynamicSignature [-SignatureSetID]` | Hiermee verwijdert u dynamische beveiligingsinformatie |
| `-CheckExclusion -path <path>` | Hiermee wordt gecontroleerd of een pad is uitgesloten |
| `-ValidateMapsConnection` | Controleert of uw netwerk kan communiceren met de Microsoft Defender Antivirus-cloudservice. Deze opdracht werkt alleen in Windows 10, versie 1703 of hoger.|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Veelvoorkomende fouten bij het uitvoeren van opdrachten via mpcmdrun.exe 

|Foutbericht | Mogelijke reden
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | De Microsoft Defender Antivirus-service is uitgeschakeld. Schakel de service in en probeer het opnieuw. <br>   **Opmerking:**  In Windows 10 1909 of ouder, en Windows Server 2019 of ouder, heette de service 'Windows Defender Antivirus'-service.|
| `0x80070667` | U gebruikt de opdracht vanaf een computer die `-ValidateMapsConnection` Windows 10 versie 1607 of ouder is, of Windows Server 2016 of ouder. Voer de opdracht uit vanaf een computer die Windows 10 versie 1703 of hoger is, of Windows Server 2019 of hoger.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | Het hulpprogramma moet worden uitgevoerd vanaf een van beide: of (waar kan verschillen `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` omdat `2012.4-0` platformupdates maandelijks zijn, behalve maart)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | Niet genoeg bevoegdheden. Gebruik de opdrachtprompt (cmd.exe) als beheerder.|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | De firewall blokkeert de verbinding of voert SSL-inspectie uit. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | Mogelijke netwerkgerelateerde problemen, zoals problemen met naamoplossing|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | De firewall blokkeert de verbinding of voert SSL-inspectie uit. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | De firewall blokkeert de verbinding of voert SSL-inspectie uit. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | De firewall blokkeert de verbinding of voert SSL-inspectie uit. |

## <a name="see-also"></a>Zie ook

- [Microsoft Defender Antivirus-functies configureren](configure-microsoft-defender-antivirus-features.md)
- [Microsoft Defender Antivirus beheren in uw bedrijf](configuration-management-reference-microsoft-defender-antivirus.md)
- [Referentieonderwerpen voor beheer- en configuratiehulpmiddelen](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)