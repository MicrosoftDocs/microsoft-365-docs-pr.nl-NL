---
title: McAfee naar Microsoft Defender voor Eindpunt - Onboard
description: Dit is fase 3, Onboard, voor het migreren van McAfee naar Microsoft Defender voor Eindpunt.
keywords: migratie, Microsoft Defender voor Eindpunt, edr
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
- m365solution-McAfeemigrate
- m365solution-scenario
ms.custom: migrationguides
ms.topic: article
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 8a9d1ea36ae0778892768e3b39f4ffbed2a8d732
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538025"
---
# <a name="migrate-from-mcafee---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Migreren van McAfee - Fase 3: Onboard to Microsoft Defender for Endpoint

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


|[![Fase 1: Voorbereiden](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[Fase 1: Voorbereiden](mcafee-to-microsoft-defender-prepare.md) |[![Fase 2: Instellen](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Fase 2: Instellen](mcafee-to-microsoft-defender-setup.md) |![Fase 3: Onboarden](images/phase-diagrams/onboard.png)<br/>Fase 3: Onboarden |
|--|--|--|
|| |*U bent er!* |

**Welkom bij fase 3 van de migratie van [McAfee Endpoint Security (McAfee) naar Microsoft Defender voor Eindpunt](mcafee-to-microsoft-defender-migration.md#the-migration-process)**. Deze migratiefase bevat de volgende stappen:

1. [Onboard devices to Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).

2. [Voer een detectietest uit.](#run-a-detection-test)

3. [Controleer of Microsoft Defender Antivirus in de passieve modus staat.](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode)

4. [Updates voor Microsoft Defender Antivirus.](#get-updates-for-microsoft-defender-antivirus)

5. [Verwijder McAfee.](#uninstall-mcafee)

6. [Zorg ervoor dat Defender voor Eindpunt correct werkt.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Onboarden apparaten naar Microsoft Defender voor Eindpunt

1. Ga naar het Microsoft Defender-beveiligingscentrum ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) en meld u aan.

2. Kies **Instellingen**  >  **Onboarding voor**  >  **apparaatbeheer.** 

3. Selecteer een besturingssysteem in de lijst Besturingssysteem selecteren om **het onboardingproces** te starten. 

4. Selecteer **onder Implementatiemethode** een optie. Volg de koppelingen en aanwijzingen om de apparaten van uw organisatie aan te nemen. Hulp nodig? Zie [Onboarding-methoden](#onboarding-methods) (in dit artikel).

### <a name="onboarding-methods"></a>Onboarding-methoden
 
Implementatiemethoden variëren, afhankelijk van het besturingssysteem dat is geselecteerd. Raadpleeg de bronnen in de onderstaande tabel voor hulp bij onboarding.

| Besturingssysteem  |Methode  |
|---------|---------|
| Windows 10     | [Groepsbeleid](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Mobile Device Management (Intune)](configure-endpoints-mdm.md)<p>[Lokaal script](configure-endpoints-script.md) <br/>**OPMERKING:** Een lokaal script is geschikt voor een conceptbewijs, maar mag niet worden gebruikt voor productie-implementatie. Voor een productie-implementatie wordt aangeraden groepsbeleid, Microsoft Endpoint Configuration Manager of Intune te gebruiken.         |
| Windows 8.1 Enterprise <p>Windows 8.1 Pro <p>Windows 7 SP1 Enterprise<p>Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<br/>**OPMERKING:** Microsoft Monitoring Agent is nu Azure Log Analytics-agent. Zie Logboekanalyse-agentoverzicht voor [meer informatie.](/azure/azure-monitor/platform/log-analytics-agent)        |
| Windows Server 2019 en hoger<p>Windows Server 2019 Core Edition<p>Windows Serverversie 1803 en hoger | [Lokaal script](configure-endpoints-script.md)<p>[Groepsbeleid](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[System Center Configuration Manager](configure-endpoints-sccm.md)<p>[VDI-onboarding-scripts voor niet-permanente apparaten](configure-endpoints-vdi.md) <br/>**OPMERKING:** Een lokaal script is geschikt voor een conceptbewijs, maar mag niet worden gebruikt voor productie-implementatie. Voor een productie-implementatie wordt aangeraden groepsbeleid, Microsoft Endpoint Configuration Manager of Intune te gebruiken.    |
| Windows Server 2016 <p>Windows Server 2012 R2<p>Windows Server 2008 R2 SP1  | [Microsoft Defender-beveiligingscentrum](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS:<p>11.3.1 (Big Sur)<p>10,15 (Catalina)<p>10,14 (Mojave) |[Niet-Windows-apparaten onboarden](configure-endpoints-non-windows.md)  |
|iOS |[Niet-Windows-apparaten onboarden](configure-endpoints-non-windows.md)  |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS of hoger LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |[Niet-Windows-apparaten onboarden](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Een detectietest uitvoeren

Als u wilt controleren of uw onboarded-apparaten correct zijn verbonden met Microsoft Defender voor Eindpunt, kunt u een detectietest uitvoeren.

|Besturingssysteem  |Richtlijnen  |
|---------|---------|
| Windows 10<p>Windows Server 2019 <p>Windows Server, versie 1803 <p>Windows Server 2016 <p>Windows Server 2012 R2     |Zie [Een detectietest uitvoeren.](run-detection-test.md) <p>Ga naar de site met demoscenario's voor Microsoft Defender voor eindpunten () en [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) probeer een of meer van de scenario's. Probeer bijvoorbeeld het **door de cloud geleverde beveiligingsdemoscenario.**         |
|macOS<p>11.3.1 (Big Sur)<p>10,15 (Catalina)<p>10,14 (Mojave)     |Download en gebruik de doe-het-zelf-app op [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <p>Zie Microsoft Defender voor Eindpunt op Mac voor [meer informatie.](microsoft-defender-endpoint-mac.md)        |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS of hoger LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |1. Voer de volgende opdracht uit en zoek naar een resultaat van **1:** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Open een terminalvenster en voer de volgende opdracht uit: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Voer de volgende opdracht uit om gedetecteerde bedreigingen op te geven: <br/>`mdatp threat list`. <p>Zie [Microsoft Defender for Endpoint on Linux voor meer informatie.](microsoft-defender-endpoint-linux.md) |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Controleren of Microsoft Defender Antivirus in de passieve modus is

Nu uw eindpunten zijn onboarded bij Defender for Endpoint, moet u ervoor zorgen dat Microsoft Defender Antivirus in passieve modus wordt uitgevoerd. U kunt opdrachtprompt of PowerShell gebruiken om deze taak uit te voeren, zoals wordt beschreven in de volgende tabel:

|Methode  |Wat moet u doen?  |
|---------|---------|
|Opdrachtprompt     |1. Open opdrachtprompt op Windows apparaat als beheerder.<p> 2. Typ `sc query windefend` en druk op Enter.<p> 3. Bekijk de resultaten om te controleren of Microsoft Defender Antivirus actief is in de passieve modus.         |
|PowerShell     |1. Open op Windows apparaat Windows PowerShell als beheerder.<p> 2. Voer de [cmdlet Get-MpComputerStatus](/powershell/module/defender/Get-MpComputerStatus) uit. <p> 3. Zoek in de lijst met resultaten naar **AMRunningMode: Passive Mode** of **AMRunningMode: SxS Passive Mode.**|

> [!NOTE]
> Mogelijk ziet u *Windows Defender Antivirus* in plaats *van Microsoft Defender Antivirus* in sommige versies van Windows.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>De Microsoft Defender Antivirus op Windows Server handmatig instellen op passieve modus

Als u Microsoft Defender Antivirus passieve modus wilt instellen op Windows Server, versie 1803 of hoger of Windows Server 2019, volgt u de volgende stappen:

1. Open registereditor en navigeer naar `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` .

2. Bewerk (of maak) een DWORD-item met de naam **ForcePassiveMode** en geef de volgende instellingen op:

   - Stel de waarde van DWORD in op `1` .
   - Selecteer **onder Basis** de optie **Hexadecimaal**.
 
   > [!NOTE]
   > U kunt andere methoden gebruiken om de registersleutel in te stellen, zoals de volgende:
   > - Groepsbeleidsvoorkeur
   > - Object voor lokaal groepsbeleid
   > - Een pakket in Configuration Manager

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Start Microsoft Defender Antivirus op Windows Server 2016

Als u een Windows Server 2016 gebruikt, moet u de Microsoft Defender Antivirus starten. U kunt dit doen met de PowerShell-cmdlet `mpcmdrun.exe -wdenable` op het apparaat.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Updates voor Microsoft Defender Antivirus

Het Microsoft Defender Antivirus up-to-date houden is essentieel om ervoor te zorgen dat uw apparaten de nieuwste technologie en functies hebben die nodig zijn om te beschermen tegen nieuwe malware en aanvalstechnieken, zelfs als Microsoft Defender Antivirus in passieve modus wordt uitgevoerd.

Er zijn twee soorten updates die betrekking hebben op het up-to-date Microsoft Defender Antivirus houden:
- Beveiligingsintelligentie-updates
- Productupdates

Als u updates wilt ontvangen, volgt u de richtlijnen in [Microsoft Defender Antivirus updates beheren en basislijnen toepassen.](manage-updates-baselines-microsoft-defender-antivirus.md)


## <a name="uninstall-mcafee"></a>McAfee verwijderen

Nu u de apparaten van uw organisatie hebt ge onboarded bij Microsoft Defender voor Eindpunt, is het de volgende stap om McAfee te verwijderen. Als u hulp bij deze stap wilt krijgen, gaat u naar uw McAfee ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) ).

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Zorg ervoor dat Defender voor Eindpunt correct werkt

Nu u McAfee hebt verwijderd, moet u ervoor zorgen dat Microsoft Defender Antivirus en eindpuntdetectie en -respons zijn ingeschakeld en in de actieve modus.

Ga hiervoor naar de site met demoscenario's voor Microsoft Defender for Endpoint [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) (). Probeer een of meer van de demoscenario's op die pagina, inclusief ten minste de volgende:
- Cloudbeveiliging
- Potentieel ongewenste toepassingen (PUA)
- Netwerkbeveiliging (NP)

> [!IMPORTANT]
> Als u een Windows Server 2016 gebruikt, moet u de Microsoft Defender Antivirus starten. U kunt dit doen met de PowerShell-cmdlet `mpcmdrun.exe -wdenable` op het apparaat.

## <a name="next-steps"></a>Volgende stappen

**Gefeliciteerd!** U hebt de migratie van McAfee naar [Microsoft Defender voor Eindpunt voltooid!](mcafee-to-microsoft-defender-migration.md#the-migration-process) 

- [Ga naar het dashboard voor beveiligingsbewerkingen](security-operations-dashboard.md) in Microsoft Defender-beveiligingscentrum ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Beheer Microsoft Defender voor Eindpunt, na de migratie.](manage-atp-post-migration.md)
