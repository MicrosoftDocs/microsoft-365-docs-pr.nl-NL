---
title: Gebruik de opdrachtregel om de Microsoft Defender Antivirus
description: Voer Microsoft Defender Antivirus scans uit en configureer de beveiliging van de volgende generatie met een speciaal opdrachtregelprogramma.
keywords: Windows Defender-scan uitvoeren, antivirusscan uitvoeren vanaf opdrachtregel, Windows Defender-scan uitvoeren vanaf opdrachtregel, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: efeb49b2741bdc45f7924032c2deb8a27458ca29
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289413"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Uw Microsoft Defender Antivirus configureren en beheren met mpcmdrun.exe opdrachtregelhulpmiddel

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt verschillende functies in Microsoft Defender Antivirus uitvoeren met behulp van het speciale opdrachtregelprogramma **mpcmdrun.exe.** Dit hulpprogramma is handig als u taken wilt automatiseren Microsoft Defender Antivirus taken. U vindt het hulpprogramma in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Voer deze uit vanuit een opdrachtprompt.

> [!TIP]
> Mogelijk moet u een versie op beheerdersniveau van de opdrachtprompt openen. Wanneer u op het Startmenu **opdrachtprompt** zoekt, kiest u **Uitvoeren als beheerder.** Als u een bijgewerkte Versie van het Microsoft Defender-platform gebruikt, kunt u vanaf `MpCmdRun` de volgende locatie uitvoeren: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` . Zie voor meer informatie over het antimalwareplatform [Microsoft Defender Antivirus updates en basislijnen.](manage-updates-baselines-microsoft-defender-antivirus.md)

Het hulpprogramma MpCmdRun gebruikt de volgende syntaxis:

```console
MpCmdRun.exe [command] [-options]
```

Hier volgt een voorbeeld:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

In ons voorbeeld start het hulpprogramma MpCmdRun een volledige antivirusscan op het apparaat.

## <a name="commands"></a>Opdrachten

| Opdracht  | Omschrijving   |
|:----|:----|
| `-?` **of** `-h`   | Hiermee worden alle beschikbare opties voor het hulpprogramma MpCmdRun weergegeven |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Scant op schadelijke software. Waarden voor **ScanType** zijn:<p>**0** Standaard, volgens uw configuratie<p>**1** Snelle scan<p>**2** Volledige scan<p>**3** Aangepaste bestands- en adreslijstscan.<p>CpuThrottling wordt uitgevoerd op basis van beleidsconfiguraties |
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
| `-ValidateMapsConnection` | Controleert of uw netwerk kan communiceren met de Microsoft Defender Antivirus cloudservice. Deze opdracht werkt alleen op Windows 10, versie 1703 of hoger.|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Veelvoorkomende fouten bij het uitvoeren van opdrachten via mpcmdrun.exe 

De volgende tabel bevat veelvoorkomende fouten die kunnen optreden tijdens het gebruik van het hulpprogramma MpCmdRun.

|Foutbericht | Mogelijke reden |
|:----|:----|
| **ValiderenMapsConnection is mislukt (800106BA)** of **0x800106BA** | De Microsoft Defender Antivirus is uitgeschakeld. Schakel de service in en probeer het opnieuw. Als u hulp nodig hebt bij het opnieuw inschakelen van Microsoft Defender Antivirus, zie Uw Microsoft Defender Antivirus op uw eindpunten opnieuw [installeren/inschakelen.](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)<p> **TIP**: In Windows 10 1909 of ouder, en Windows Server 2019 of ouder, werd de service voorheen *Windows Defender Antivirus.* |
| **0x80070667** | U gebruikt de opdracht vanaf een computer Windows 10 versie 1607 of ouder, of Windows Server 2016 `-ValidateMapsConnection` of ouder. Voer de opdracht uit vanaf een computer Windows 10 versie 1703 of hoger, of Windows Server 2019 of hoger.|
| **MpCmdRun wordt niet herkend als een interne of externe opdracht, een bedienbaar programma of een batchbestand.** | Het hulpprogramma moet worden uitgevoerd vanaf een van beide of (waar kan verschillen `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` omdat `2012.4-0` platformupdates maandelijks zijn, behalve maart)|
| **ValidMapsConnection kan geen verbinding tot stand brengen met KAARTEN (hr=80070005 httpcode=450)** | De opdracht is geprobeerd onvoldoende bevoegdheden te gebruiken. Gebruik de opdrachtprompt (cmd.exe) als beheerder.|
| **ValidMapsConnection kan geen verbinding tot stand brengen met KAARTEN (hr=80070006 httpcode=451)** | De firewall blokkeert de verbinding of voert SSL-inspectie uit. |
| **ValidErenMapsConnection kan geen verbinding tot stand brengen met KAARTEN (hr=80004005 httpcode=450)** | Mogelijke netwerkgerelateerde problemen, zoals problemen met naamoplossing|
| **ValidErenMapsConnection kan geen verbinding tot stand brengen met KAARTEN (hr=0x80508015** | De firewall blokkeert de verbinding of voert SSL-inspectie uit. |
| **ValidErenMapsConnection kan geen verbinding tot stand brengen met KAARTEN (hr=800722F0D** | De firewall blokkeert de verbinding of voert SSL-inspectie uit. |
| **ValidMapsConnection kan geen verbinding tot stand brengen met KAARTEN (hr=80072EE7 httpcode=451)** | De firewall blokkeert de verbinding of voert SSL-inspectie uit. |

## <a name="see-also"></a>Zie ook

- [Microsoft Defender Antivirus-functies configureren](configure-microsoft-defender-antivirus-features.md)
- [Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren](configure-network-connections-microsoft-defender-antivirus.md)
- [Referentieonderwerpen voor beheer- en configuratiehulpmiddelen](configuration-management-reference-microsoft-defender-antivirus.md)
