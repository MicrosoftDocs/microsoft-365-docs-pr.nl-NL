---
title: Overschakelen naar Microsoft Defender voor Eindpunt - Onboard
description: Dit is fase 3, Onboard, voor het migreren van een niet-Microsoft-oplossing naar Microsoft Defender voor Eindpunt.
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
- m365solution-migratetomdatp
ms.custom: migrationguides
ms.topic: article
ms.date: 05/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 66d24f5a479a903c8d42d509f1bbe956293c9ac3
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346338"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Overschakelen naar Microsoft Defender voor Eindpunt - Fase 3: Onboard

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Fase 1: Voorbereiden3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fase 1: Voorbereiden](switch-to-microsoft-defender-prepare.md) | [![Fase 2: Instellen](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fase 2: Instellen](switch-to-microsoft-defender-setup.md) | ![Fase 3: Onboarden](images/phase-diagrams/onboard.png)<br/>Fase 3: Onboarden |
|--|--|--|
|| |*U bent er!* |


**Welkom bij fase 3 van het [overstappen naar Microsoft Defender voor Eindpunt.](switch-to-microsoft-defender-migration.md#the-migration-process)** Deze migratiefase bevat de volgende stappen:

1. [Onboard devices to Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).

2. [Voer een detectietest uit.](#run-a-detection-test)

3. [Verwijder uw niet-Microsoft-oplossing.](#uninstall-your-non-microsoft-solution)

4. [Zorg ervoor dat Microsoft Defender voor Eindpunt in de actieve modus staat.](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Onboarden apparaten naar Microsoft Defender voor Eindpunt

1. Ga naar het Microsoft Defender-beveiligingscentrum ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) en meld u aan.

2. Kies **Instellingen**  >  **Onboarding voor**  >  **apparaatbeheer.** 

3. Selecteer een besturingssysteem in de lijst Besturingssysteem selecteren om **het onboardingproces** te starten. 

4. Selecteer **onder Implementatiemethode** een optie. Volg de koppelingen en aanwijzingen om de apparaten van uw organisatie aan te nemen. Hulp nodig? Zie [Onboarding-methoden](#onboarding-methods) (in dit artikel).

### <a name="onboarding-methods"></a>Onboarding-methoden
 
Implementatiemethoden variëren, afhankelijk van het besturingssysteem dat is geselecteerd. Raadpleeg de bronnen in de onderstaande tabel voor hulp bij onboarding.

|Besturingssysteem  |Methode  |
|---------|---------|
|Windows 10     |- [Groepsbeleid](configure-endpoints-gp.md)<br/>- [Configuration Manager](configure-endpoints-sccm.md)<br/>- [Mobile Device Management (Intune)](configure-endpoints-mdm.md)<br/>- [Lokaal script](configure-endpoints-script.md) <p>**OPMERKING:** Een lokaal script is geschikt voor een conceptbewijs, maar mag niet worden gebruikt voor productie-implementatie. Voor een productie-implementatie wordt aangeraden groepsbeleid, Microsoft Endpoint Configuration Manager of Intune te gebruiken.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**OPMERKING:** Microsoft Monitoring Agent is nu Azure Log Analytics-agent. Zie Logboekanalyse-agentoverzicht voor [meer informatie.](/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 en hoger <br/>- Windows Server 2019 core edition <br/>- Windows Server versie 1803 en hoger |- [Lokaal script](configure-endpoints-script.md) <br/>- [Groepsbeleid](configure-endpoints-gp.md) <br/>- [Configuration Manager](configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md) <br/>- [VDI-onboarding-scripts voor niet-permanente apparaten](configure-endpoints-vdi.md) <p>**OPMERKING:** Een lokaal script is geschikt voor een conceptbewijs, maar mag niet worden gebruikt voor productie-implementatie. Voor een productie-implementatie wordt aangeraden groepsbeleid, Microsoft Endpoint Configuration Manager of Intune te gebruiken.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender-beveiligingscentrum](configure-server-endpoints.md)<br/>- [Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS<br/>- 11.3.1 (Big Sur) <br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave)<p>iOS<p>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS of hoger LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Niet-Windows-apparaten onboarden](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Een detectietest uitvoeren

Als u wilt controleren of uw onboarded-apparaten correct zijn verbonden met Microsoft Defender voor Eindpunt, kunt u een detectietest uitvoeren.

|Besturingssysteem  |Richtlijnen  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, versie 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Zie [Een detectietest uitvoeren.](run-detection-test.md) <p>Ga naar de site met demoscenario's voor Microsoft Defender voor eindpunten () en [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) probeer een of meer van de scenario's. Probeer bijvoorbeeld het **door de cloud geleverde beveiligingsdemoscenario.**         |
|macOS<br/>- 11.3.1 (Big Sur) <br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave)    |Download en gebruik de doe-het-zelf-app op [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <p>Zie [Microsoft Defender voor Eindpunt op macOS voor meer informatie.](microsoft-defender-endpoint-mac.md)        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS of hoger LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Voer de volgende opdracht uit en zoek naar een resultaat van **1:** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Open een terminalvenster en voer de volgende opdracht uit: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Voer de volgende opdracht uit om gedetecteerde bedreigingen op te geven: <br/>`mdatp threat list`. <p>Zie [Microsoft Defender for Endpoint on Linux voor meer informatie.](microsoft-defender-endpoint-linux.md) |

## <a name="uninstall-your-non-microsoft-solution"></a>Uw niet-Microsoft-oplossing verwijderen

Nu u de apparaten van uw organisatie hebt ge onboarded bij Microsoft Defender voor Eindpunt, is de volgende stap het verwijderen van uw oplossing voor niet-Microsoft-eindpuntbeveiliging.

Neem contact op met het technische ondersteuningsteam van uw oplossingsprovider om hulp te krijgen bij deze stap.

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Zorg ervoor dat Microsoft Defender voor Eindpunt actief is

Nu u uw oplossing voor niet-Microsoft-eindpuntbeveiliging hebt verwijderd, moet u ervoor zorgen dat Microsoft Defender Antivirus en Microsoft Defender voor Eindpunt zijn ingeschakeld en in de actieve modus.

Ga hiervoor naar de site met demoscenario's voor Microsoft Defender for Endpoint [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) (). Probeer een of meer van de demoscenario's op die pagina, inclusief ten minste de volgende:
- Cloudbeveiliging
- Potentieel ongewenste toepassingen (PUA)
- Netwerkbeveiliging (NP)

> [!IMPORTANT]
> Als u een Windows Server 2016 gebruikt, moet u de Microsoft Defender Antivirus starten. U kunt dit doen met de PowerShell-cmdlet `mpcmdrun.exe -wdenable` op het apparaat.

## <a name="next-steps"></a>Volgende stappen

**Gefeliciteerd!** U hebt de migratie [naar Microsoft Defender voor Eindpunt voltooid!](switch-to-microsoft-defender-migration.md#the-migration-process) 

- [Ga naar het dashboard voor beveiligingsbewerkingen](security-operations-dashboard.md) in Microsoft Defender-beveiligingscentrum ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

- [Beheer Microsoft Defender voor Eindpunt, na de migratie.](manage-atp-post-migration.md)
