---
title: Symantec to Microsoft Defender for Endpoint - Phase 2, Setting Up
description: Dit is fase 2, Setup, van de migratie van Symantec naar Microsoft Defender voor Eindpunt
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 3fbe7ca11ca168f2af75b76252acf4d3a97b35f0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059669"
---
# <a name="migrate-from-symantec---phase-2-set-up-microsoft-defender-for-endpoint"></a>Migreren van Symantec - Fase 2: Microsoft Defender instellen voor eindpunt

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Voorbereiden](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fase 1: Voorbereiden](symantec-to-microsoft-defender-atp-prepare.md) |![Fase 2: Instellen](images/phase-diagrams/setup.png)<br/>Fase 2: Instellen |[![Fase 3: Onboard](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fase 3: Onboard](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
||*U bent er!* | |


**Welkom bij de installatiefase van [de migratie van Symantec naar Microsoft Defender voor Eindpunt.](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)** Deze fase bevat de volgende stappen:
1. [Microsoft Defender Antivirus (voor bepaalde versies van Windows) in- of opnieuw installeren.](#enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows)
2. [Microsoft Defender Antivirus inschakelen.](#enable-microsoft-defender-antivirus)
3. [Updates voor Microsoft Defender Antivirus downloaden.](#get-updates-for-microsoft-defender-antivirus)
4. [Voeg Microsoft Defender voor Eindpunt toe aan de uitsluitingslijst voor Symantec.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec)
5. [Voeg Symantec toe aan de uitsluitingslijst voor Microsoft Defender Antivirus.](#add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus)
6. [Voeg Symantec toe aan de uitsluitingslijst voor Microsoft Defender voor Eindpunt](#add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint).
7. [Stel uw apparaatgroepen, apparaatverzamelingen en organisatie-eenheden in.](#set-up-your-device-groups-device-collections-and-organizational-units)
8. [Antimalware-beleid en realtimebeveiliging configureren.](#configure-antimalware-policies-and-real-time-protection)

## <a name="enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows"></a>Microsoft Defender Antivirus in- of opnieuw installeren (voor bepaalde versies van Windows)

> [!TIP]
> Als u Windows 10 gebruikt, hoeft u deze taak niet uit te voeren. Ga verder **[met Microsoft Defender Antivirus inschakelen.](#enable-microsoft-defender-antivirus)**

In bepaalde versies van Windows is Microsoft Defender Antivirus mogelijk verwijderd of uitgeschakeld. Microsoft Defender Antivirus voert namelijk geen passieve of uitgeschakelde modus in wanneer u een antivirusproduct van derden, zoals Symantec, installeert. Zie Compatibiliteit met [Microsoft Defender Antivirus voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility) 

Nu u overstapt van Symantec naar Microsoft Defender voor Eindpunt, moet u Microsoft Defender Antivirus in- of opnieuw installeren en instellen op passieve modus. 

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender Antivirus opnieuw installeren op Windows Server

> [!NOTE]
> De volgende procedure is alleen van toepassing op eindpunten of apparaten met de volgende versies van Windows:
> - Windows Server 2019
> - Windows Server, versie 1803 (alleen-kernmodus)
> - Windows Server 2016
> 
> Microsoft Defender Antivirus is ingebouwd in Windows 10, maar kan worden uitgeschakeld. Ga in dit geval verder met [Microsoft Defender Antivirus inschakelen.](#enable-microsoft-defender-antivirus)

1. Open Windows PowerShell als lokale beheerder op het eindpunt of apparaat.
2. Voer de volgende PowerShell-cmdlets uit: `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`

   > [!NOTE]
   > Wanneer u de opdracht DISM gebruikt in een taakreeks met PS, is het volgende pad naar cmd.exe vereist.
   > Voorbeeld:<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>
3. Gebruik de volgende PowerShell-cmdlet om te controleren of Microsoft Defender Antivirus actief is: <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Gebruikt u Windows Server 2016?

Als u Windows Server 2016 gebruikt en problemen hebt met het inschakelen van Microsoft Defender Antivirus, gebruikt u de volgende PowerShell-cmdlet:

`mpcmdrun -wdenable`

> [!TIP]
> Meer hulp nodig? Zie [Microsoft Defender Antivirus op Windows Server 2016 en 2019](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Microsoft Defender Antivirus instellen op passieve modus op Windows Server

Omdat uw organisatie nog steeds gebruik maakt van Symantec, moet u Microsoft Defender Antivirus instellen op passieve modus. Op die manier kunnen Antivirusprogramma's van Microsoft Defender en Microsoft Defender naast elkaar worden uitgevoerd totdat u klaar bent met onboarding bij Microsoft Defender voor Eindpunt.

1. Registereditor openen en vervolgens naar <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.
2. Bewerk (of maak) een DWORD-item met de naam **ForceDefenderPassiveMode** en geef de volgende instellingen op:
   - Stel de waarde van DWORD in op **1**.
   - Selecteer **onder Basis** de optie **Hexadecimaal**.

> [!NOTE]
> U kunt andere methoden gebruiken om de registersleutel in te stellen, zoals de volgende:
>- [Groepsbeleidsvoorkeur](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Object voor lokaal groepsbeleid](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Een pakket in Configuration Manager](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="enable-microsoft-defender-antivirus"></a>Microsoft Defender Antivirus inschakelen

Omdat uw organisatie Symantec heeft gebruikt als uw primaire antivirusoplossing, is Microsoft Defender Antivirus waarschijnlijk uitgeschakeld op de Windows-apparaten van uw organisatie. Bij deze stap van het migratieproces wordt Microsoft Defender Antivirus inschakelen. 

Als u Microsoft Defender Antivirus wilt inschakelen, raden we u aan Intune te gebruiken. U kunt echter een van de methoden in de volgende tabel gebruiken:

|Methode  |Wat moet u doen?  |
|---------|---------|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**OPMERKING:** Intune is nu Microsoft Endpoint Manager. |1. Ga naar het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en meld u aan.<br/>2. Selecteer **Apparaten**  >  **configuratieprofielen** en selecteer vervolgens het profieltype dat u wilt configureren. Zie **Apparaatbeperkingsinstellingen** configureren [in Microsoft Intune](https://docs.microsoft.com/intune/device-restrictions-configure)als u nog geen profieltype Apparaatbeperkingen hebt gemaakt of als u een nieuw profiel wilt maken.<br/>3. Selecteer **Eigenschappen** en selecteer **vervolgens Configuratie-instellingen: Bewerken.**<br/>4. Breid **Microsoft Defender Antivirus uit.** <br/>5. **Beveiliging via de cloud inschakelen.**<br/>6. Selecteer in **de vervolgkeuze van** Gebruikers vragen vóór voorbeeldinzending de optie **Alle voorbeelden automatisch verzenden.**<br/>7. Selecteer in **de vervolgkeuze** van Mogelijk ongewenste toepassingen detecteren de optie **Inschakelen** of **Controleren.**<br/>8. Selecteer **Controleren + opslaan** en kies vervolgens **Opslaan.**<br/>Zie Wat zijn Microsoft Intune-apparaatprofielen? voor meer informatie over [Intune-apparaatprofielen,](https://docs.microsoft.com/intune/device-profiles)waaronder hoe u hun instellingen kunt maken en configureren.|
|Configuratiescherm in Windows     |Volg de richtlijnen hier: [Schakel Microsoft Defender Antivirus in.](https://docs.microsoft.com/mem/intune/user-help/turn-on-defender-windows) <br/>**OPMERKING:** In sommige versies van Windows ziet u *mogelijk Windows Defender Antivirus* in plaats van Microsoft Defender *Antivirus.*        |
|[Geavanceerd groepsbeleidsbeheer](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) <br/>of<br/>[Groepsbeleidsbeheerconsole](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Ga naar `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <br/>2. Zoek naar een beleid genaamd **Microsoft Defender Antivirus uitschakelen.**<br/>3. Kies **Beleidsinstelling bewerken** en zorg ervoor dat beleid is uitgeschakeld. Hierdoor wordt Microsoft Defender Antivirus mogelijk. <br/>**OPMERKING:** In sommige versies van Windows ziet u *mogelijk Windows Defender Antivirus* in plaats van Microsoft Defender *Antivirus.* |

### <a name="verify-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Controleren of Microsoft Defender Antivirus in passieve modus is

Microsoft Defender Antivirus kan samen met Symantec worden uitgevoerd als u Microsoft Defender Antivirus in de passieve modus in stelt. U kunt opdrachtprompt of PowerShell gebruiken om deze taak uit te voeren, zoals wordt beschreven in de volgende tabel:

|Methode  |Wat moet u doen?  |
|---------|---------|
|Opdrachtprompt     |1. Open opdrachtprompt op een Windows-apparaat als beheerder. <br/>2. Typ `sc query windefend` en druk op Enter.<br/>3. Bekijk de resultaten om te bevestigen dat Microsoft Defender Antivirus actief is in de passieve modus.         |
|PowerShell     |1. Open Windows PowerShell op een Windows-apparaat als beheerder.<br/>2. Voer de [cmdlet Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/Get-MpComputerStatus) uit. <br/>3. Zoek in de lijst met resultaten naar **AMRunningMode: Passive Mode** of **AMRunningMode: SxS Passive Mode.**|

> [!NOTE]
> Mogelijk ziet u *Windows Defender Antivirus* in plaats van Microsoft Defender *Antivirus* in sommige versies van Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Updates voor Microsoft Defender Antivirus downloaden

Het up-to-date houden van Microsoft Defender Antivirus is essentieel om ervoor te zorgen dat uw apparaten de nieuwste technologie en functies hebben die nodig zijn om te beschermen tegen nieuwe malware en aanvalstechnieken, zelfs als Microsoft Defender Antivirus in de passieve [modus wordt uitgevoerd.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Er zijn twee soorten updates die betrekking hebben op het up-to-date houden van Microsoft Defender Antivirus:
- Beveiligingsintelligentie-updates
- Productupdates

Als u updates wilt ontvangen, volgt u de richtlijnen in [Microsoft Defender Antivirus-updates beheren en basislijnen toepassen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec"></a>Microsoft Defender voor Eindpunt toevoegen aan de uitsluitingslijst voor Symantec

In deze stap van het installatieproces wordt Microsoft Defender voor Eindpunt toegevoegd aan de uitsluitingslijst voor Symantec en andere beveiligingsproducten die uw organisatie gebruikt. Welke specifieke uitsluitingen u moet configureren, is afhankelijk van welke versie van Windows uw eindpunten of apparaten worden uitgevoerd en worden weergegeven in de volgende tabel:

|BESTURINGSSYSTEEM |Uitsluitingen |
|--|--|
|- Windows 10, [versie 1803](https://docs.microsoft.com/windows/release-health/status-windows-10-1803) of hoger (Zie Releasegegevens van [Windows 10](https://docs.microsoft.com/windows/release-health/release-information))<br/>- Windows 10, versie 1703 of [1709](https://docs.microsoft.com/windows/release-health/status-windows-10-1709) met [KB4493441](https://support.microsoft.com/help/4493441) geïnstalleerd <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, versie 1803](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
|- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**OPMERKING:** Waar tijdelijke bestanden van hostcontrole 6\45 verschillende genummerde submappen kunnen zijn.<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Symantec toevoegen aan de uitsluitingslijst voor Microsoft Defender Antivirus

Tijdens deze stap van het installatieproces voegt u Symantec en uw andere beveiligingsoplossingen toe aan de uitsluitingslijst van Microsoft Defender Antivirus. 

> [!NOTE]
> Zie Broadcom's Processen en services die worden gebruikt door [Endpoint Protection 14](https://knowledge.broadcom.com/external/article/170706/processes-and-services-used-by-endpoint.html)voor een idee van welke processen en services u moet uitsluiten.

Wanneer u [uitsluitingen toevoegt aan Microsoft Defender Antivirus scans,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)moet u pad- en procesuitsluitingen toevoegen. Houd rekening met de volgende punten:
- Paduitsluitingen sluiten specifieke bestanden en toegang tot die bestanden uit.
- Uitsluitingen van processen sluiten uit wat een proces raakt, maar sluit het proces zelf niet uit.
- Als u elke uitvoerbare (.exe) als zowel een paduitsluiting als een procesuitsluiting oplijst, wordt het proces en wat het ook raakt, uitgesloten.
- Vermeld uw procesuitsluitingen met hun volledige pad en niet alleen op hun naam. (De methode voor alleen-naam is minder veilig.)

U kunt kiezen uit verschillende methoden om uw uitsluitingen toe te voegen aan Microsoft Defender Antivirus, zoals vermeld in de volgende tabel:

|Methode | Wat moet u doen?|
|--|--|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**OPMERKING:** Intune is nu Microsoft Endpoint Manager. |1. Ga naar het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en meld u aan.<br/>2. Selecteer  >  **Apparaatconfiguratieprofielen** en selecteer vervolgens het profiel dat u wilt configureren.<br/>3. Selecteer **onder Beheren** de optie **Eigenschappen**. <br/>4. Selecteer **Configuratie-instellingen: Bewerken**.<br/>5. Vouw **Microsoft Defender Antivirus uit** en vouw microsoft Defender Antivirus **Exclusions uit.**<br/>6. Geef de bestanden en mappen, extensies en processen op die u wilt uitsluiten van Antivirusscans van Microsoft Defender. Zie Microsoft [Defender Antivirus exclusions](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)voor meer informatie.<br/>7. Kies **Controleren + opslaan** en kies vervolgens **Opslaan.**  |
|[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/) |1. Ga met [de console Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/manage/admin-console)naar Assets and Compliance   >  **Endpoint Protection**  >  **Antimalware Policies** en selecteer vervolgens het beleid dat u wilt wijzigen. <br/>2. Geef uitsluitingsinstellingen op voor bestanden en mappen, extensies en processen die moeten worden uitgesloten van Antivirusscans van Microsoft Defender. |
|[Groepsbeleidsobject](https://docs.microsoft.com/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Open op uw computer [](https://technet.microsoft.com/library/cc731212.aspx)voor groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**<br/>2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en klik op **Beheersjablonen.**<br/>3. Vouw de structuur uit naar **Windows-onderdelen > Microsoft Defender Antivirus > Exclusions**.<br/>**OPMERKING:** In sommige versies van Windows ziet u *mogelijk Windows Defender Antivirus* in plaats van Microsoft Defender *Antivirus.*<br/>4. Dubbelklik op de instelling **Paduitsluitingen** en voeg de uitsluitingen toe.<br/>- Stel de optie in op **Ingeschakeld.**<br/>- Klik onder **de** sectie Opties op **Toon...**.<br/>- Geef elke map op een eigen regel op onder de **kolom Waardenaam.**<br/>- Als u een bestand opgeeft, moet u een volledig gekwalificeerd pad naar het bestand invoeren, inclusief de stationletter, het mappenpad, de bestandsnaam en de extensie. Voer **0** in de kolom **Waarde** in.<br/>5. Klik op **OK**.<br/>6. Dubbelklik op de instelling Uitsluitingen voor **extensies** en voeg de uitsluitingen toe.<br/>- Stel de optie in op **Ingeschakeld.**<br/>- Klik onder **de** sectie Opties op **Toon...**.<br/>- Voer elke bestandsextensie op een eigen regel in onder de **kolom Waardenaam.**  Voer **0** in de kolom **Waarde** in.<br/>7. Klik op **OK**. |
|Lokaal groepsbeleidsobject |1. Open de Editor voor lokaal groepsbeleid op het eindpunt of apparaat. <br/>2. Ga naar **Beheersjablonen voor computerconfiguratie**  >    >  **Windows Components**  >  **Microsoft Defender Antivirus**  >  **Exclusions**. <br/>**OPMERKING:** In sommige versies van Windows ziet u *mogelijk Windows Defender Antivirus* in plaats van Microsoft Defender *Antivirus.*<br/>3. Geef uw pad en procesuitsluitingen op. |
|Registersleutel |1. Exporteert u de volgende registersleutel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/>2. Importeer de registersleutel. Hier zijn twee voorbeelden:<br/>- Lokaal pad: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Netwerk delen: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Add Symantec to the exclusion list for Microsoft Defender for Endpoint

Als u uitsluitingen wilt toevoegen aan Microsoft Defender voor Eindpunt, maakt u [indicatoren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files).

1. Ga naar het Microsoft Defender-beveiligingscentrum [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () en meld u aan.
2. Kies in het navigatiedeelvenster **Instellingen**  >  **regelsindicatoren**  >  .
3.  Kies op **het tabblad Bestandshashes** de optie **Indicator toevoegen.**
4. Geef op **het** tabblad Indicator de volgende instellingen op:
   - Bestandshash (Hulp nodig? Zie [Een bestandshash zoeken met CMPivot](#find-a-file-hash-using-cmpivot) in dit artikel.)
   - Kies **onder Verloopt op (UTC)** de optie **Nooit.**
5. Geef op **het** tabblad Actie de volgende instellingen op:
   - **Reactieactie:** **Toestaan**
   - Titel en beschrijving
6. Selecteer op **het** tabblad Bereik onder **Apparaatgroepen** de optie **Alle apparaten in mijn bereik** of Selecteer uit **lijst.**
7. Controleer op **het** tabblad Overzicht de instellingen en klik vervolgens op **Opslaan.**

### <a name="find-a-file-hash-using-cmpivot"></a>Een bestandshash zoeken met CMPivot

CMPivot is een hulpprogramma voor Configuratiebeheer in de console. CMPivot biedt toegang tot de realtime status van apparaten in uw omgeving. Er wordt onmiddellijk een query uitgevoerd op alle apparaten die momenteel zijn verbonden in de doelverzameling en geeft de resultaten als resultaat. Zie [CMPivot-overzicht](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot-overview)voor meer informatie.

Als u CMPivot wilt gebruiken om uw bestandshash op te halen, volgt u de volgende stappen:

1. Controleer de [vereisten.](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#prerequisites)
2. [CMPivot starten.](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot) 
3. Verbinding maken met Configuration Manager ( `SCCM_ServerName.DomainName.com` ).
4. Selecteer het **tabblad** Query.
5. Kies in **de lijst Apparaatverzameling** de optie **Alle systemen (standaard).**
6. Typ in het queryvak de volgende query:<br/>
   ```kusto
   File(c:\\windows\\notepad.exe)
   | project Hash
   ```
   
   > [!NOTE]
   > Vervang in de bovenstaande query *notepad.exe* door de naam van het beveiligingsproduct van derden. 
   

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Uw apparaatgroepen, apparaatverzamelingen en organisatie-eenheden instellen

| Verzamelingstype | Wat moet u doen? |
|--|--|
|[Met apparaatgroepen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) (voorheen machinegroepen genoemd) kan uw beveiligingsteam beveiligingsfuncties configureren, zoals geautomatiseerd onderzoek en herstel.<br/> Apparaatgroepen zijn ook handig voor het toewijzen van toegang tot deze apparaten, zodat uw team voor beveiligingsbewerkingen indien nodig herstelacties kan uitvoeren. <br/>Apparaatgroepen worden gemaakt in het Microsoft Defender-beveiligingscentrum. |1. Ga naar het Microsoft Defender-beveiligingscentrum ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<br/>2. Kies in het navigatiedeelvenster aan de linkerkant de optie **Instellingen**  >  **Machtigingen**  >  **Apparaatgroepen**.  <br/>3. Kies **+ Apparaatgroep toevoegen.**<br/>4. Geef een naam en beschrijving op voor de apparaatgroep.<br/>5. Selecteer een optie in de lijst **Automatiseringsniveau.** (We raden **u aan om bedreigingen automatisch te** corrigeren .) Zie Hoe bedreigingen worden gesaneerd voor meer informatie over de verschillende [automatiseringsniveaus.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/>6. Geef voorwaarden op voor een overeenkomende regel om te bepalen welke apparaten tot de apparaatgroep behoren. U kunt bijvoorbeeld een domein, besturingssysteemversies of zelfs apparaatlabels [gebruiken.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags) <br/>7. Geef op **het tabblad Gebruikerstoegang** rollen op die toegang moeten hebben tot de apparaten die zijn opgenomen in de apparaatgroep. <br/>8. Kies **Klaar**. |
|[Met apparaatverzamelingen](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/introduction-to-collections) kan uw beveiligingsteam toepassingen beheren, nalevingsinstellingen implementeren of software-updates installeren op de apparaten in uw organisatie. <br/>Apparaatverzamelingen worden gemaakt met [Configuration Manager.](https://docs.microsoft.com/mem/configmgr/) |Volg de stappen in [Een verzameling maken.](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[Met organisatie-eenheden](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) kunt u objecten, zoals gebruikersaccounts, serviceaccounts of computeraccounts, logisch groeperen. Vervolgens kunt u beheerders toewijzen aan specifieke organisatie-eenheden en groepsbeleid toepassen om gerichte configuratie-instellingen af te dwingen.<br/> Organisatie-eenheden worden gedefinieerd in [Azure Active Directory Domain Services.](https://docs.microsoft.com/azure/active-directory-domain-services) | Volg de stappen in [Een organisatie-eenheid maken in een beheerd domein van Azure Active Directory Domain Services.](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Antimalware-beleid en realtimebeveiliging configureren

Configureer uw antimalwarebeleid met Behulp van Configuration Manager en uw apparaatverzameling(en).

- Zie [Antimalware-beleid maken en implementeren voor Endpoint Protection in Configuration Manager.](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- Terwijl u uw antimalwarebeleid maakt en configureert, controleert u de [realtime](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) beveiligingsinstellingen en stelt u blok op het [eerste gezicht in.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> U kunt het beleid implementeren vóór de apparaten van uw organisatie in onboarded.

## <a name="next-step"></a>Volgende stap

**Gefeliciteerd!** U hebt de installatiefase van de migratie van Symantec naar [Microsoft Defender voor Eindpunt voltooid.](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)
- [Doorgaan naar fase 3: Onboard to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-atp-onboard.md)
