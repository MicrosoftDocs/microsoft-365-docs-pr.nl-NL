---
title: McAfee naar Microsoft Defender voor Eindpunt - Onboard
description: Dit is fase 3, Onboard, voor het migreren van McAfee naar Microsoft Defender voor Eindpunt.
keywords: migratie, windows defender advanced threat protection, atp, edr
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
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 54130848867c4fa6830f475712a08e226add9361
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060530"
---
# <a name="migrate-from-mcafee---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Migreren van McAfee - Fase 3: Onboard to Microsoft Defender for Endpoint

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


|[![Fase 1: Voorbereiden](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[Fase 1: Voorbereiden](mcafee-to-microsoft-defender-prepare.md) |[![Fase 2: Instellen](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Fase 2: Instellen](mcafee-to-microsoft-defender-setup.md) |![Fase 3: Onboard](images/phase-diagrams/onboard.png)<br/>Fase 3: Onboard |
|--|--|--|
|| |*U bent er!* |

**Welkom bij fase 3 van de migratie van [McAfee Endpoint Security (McAfee) naar Microsoft Defender Advanced Threat Protection (Microsoft Defender for Endpoint)](mcafee-to-microsoft-defender-migration.md#the-migration-process)**. Deze migratiefase bevat de volgende stappen:

1. [Onboard devices to Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Voer een detectietest uit.](#run-a-detection-test)
3. [Verwijder McAfee.](#uninstall-mcafee)
4. [Zorg ervoor dat Microsoft Defender voor Eindpunt in de actieve modus staat.](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Onboard devices to Microsoft Defender for Endpoint

1. Ga naar het Microsoft Defender-beveiligingscentrum [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () en meld u aan.

2. Kies **Instellingen**  >  **Apparaatbeheer**  >  **Onboarding**. 

3. Selecteer een besturingssysteem in de lijst Besturingssysteem selecteren om **het onboardingproces** te starten. 

4. Selecteer **onder Implementatiemethode** een optie. Volg de koppelingen en aanwijzingen om de apparaten van uw organisatie aan te nemen. Hulp nodig? Zie [Onboarding-methoden](#onboarding-methods) (in dit artikel).

### <a name="onboarding-methods"></a>Onboarding-methoden
 
Implementatiemethoden variëren, afhankelijk van het besturingssysteem dat is geselecteerd. Raadpleeg de bronnen in de onderstaande tabel voor hulp bij onboarding.

|Besturingssysteem  |Methode  |
|---------|---------|
|Windows 10     |- [Groepsbeleid](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)<br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)<br/>- [Mobile Device Management (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)<br/>- [Lokaal script](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/><br/>**OPMERKING:** Een lokaal script is geschikt voor een conceptbewijs, maar mag niet worden gebruikt voor productie-implementatie. Voor een productie-implementatie wordt aangeraden groepsbeleid, Microsoft Endpoint Configuration Manager of Intune te gebruiken.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/>**OPMERKING:** Microsoft Monitoring Agent is nu Azure Log Analytics-agent. Zie Logboekanalyse-agentoverzicht voor [meer informatie.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 en hoger <br/>- Windows Server 2019 Core Edition <br/>- Windows Server versie 1803 en hoger |- [Lokaal script](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/>- [Groepsbeleid](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp) <br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) <br/>- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager) <br/>- [VDI-onboarding-scripts voor niet-permanente apparaten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi) <br/><br/>**OPMERKING:** Een lokaal script is geschikt voor een conceptbewijs, maar mag niet worden gebruikt voor productie-implementatie. Voor een productie-implementatie wordt aangeraden groepsbeleid, Microsoft Endpoint Configuration Manager of Intune te gebruiken.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender-beveiligingscentrum](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)<br/>- [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave)<br/>- 10,13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS of hoger LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Onboard niet-Windows-apparaten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a>Een detectietest uitvoeren

Als u wilt controleren of uw onboarded-apparaten correct zijn verbonden met Microsoft Defender voor Eindpunt, kunt u een detectietest uitvoeren.


|Besturingssysteem  |Richtlijnen  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, versie 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Zie [Een detectietest uitvoeren.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test) <br/><br/>Ga naar de site met demoscenario's voor Microsoft Defender voor eindpunten () en [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) probeer een of meer van de scenario's. Probeer bijvoorbeeld het **door de cloud geleverde beveiligingsdemoscenario.**         |
|macOS<br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave)<br/>- 10,13 (High Sierra)     |Download en gebruik de doe-het-zelf-app op [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Zie [Microsoft Defender ATP voor Mac voor](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)meer informatie.        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS of hoger LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Voer de volgende opdracht uit en zoek naar een resultaat van **1:** <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Open een terminalvenster en voer de volgende opdracht uit: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Voer de volgende opdracht uit om gedetecteerde bedreigingen op te geven: <br/>`mdatp threat list`. <br/><br/>Zie [Microsoft Defender ATP for Linux voor meer informatie.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux) |

## <a name="uninstall-mcafee"></a>McAfee verwijderen

Nu u de apparaten van uw organisatie hebt ge onboarded bij Microsoft Defender voor Eindpunt, is het de volgende stap om McAfee te verwijderen.

Als u hulp bij deze stap wilt krijgen, gaat u naar uw McAfee ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) ).

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Zorg ervoor dat Microsoft Defender voor Eindpunt actief is

Nu u McAfee hebt verwijderd, moet u ervoor zorgen dat De antivirus- en eindpuntdetectie en -reactie van Microsoft Defender zijn ingeschakeld en in de actieve modus.

Ga hiervoor naar de site met demoscenario's voor Microsoft Defender for Endpoint [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) (). Probeer een of meer van de demoscenario's op die pagina, inclusief ten minste de volgende:
- Beveiliging in de cloud
- Potentieel ongewenste toepassingen (PUA)
- Netwerkbeveiliging (NP)

> [!IMPORTANT]
> Als u Windows Server 2016 gebruikt, moet u mogelijk Microsoft Defender Antivirus handmatig starten. U kunt dit doen met de PowerShell-cmdlet `mpcmdrun.exe -wdenable` op het apparaat.

## <a name="next-steps"></a>Volgende stappen

**Gefeliciteerd!** U hebt de migratie van McAfee naar [Microsoft Defender voor Eindpunt voltooid!](mcafee-to-microsoft-defender-migration.md#the-migration-process) 

- [Ga naar het dashboard voor beveiligingsbewerkingen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) in het Microsoft Defender-beveiligingscentrum ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Microsoft Defender Advanced Threat Protection beheren, na de migratie.](manage-atp-post-migration.md)
