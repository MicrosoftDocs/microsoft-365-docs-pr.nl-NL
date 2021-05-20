---
title: Overschakelen naar Microsoft Defender voor eindpunt - Setup
description: Fase 2, het installatieproces, wanneer u overschakelt naar Microsoft Defender voor Eindpunt.
keywords: migratie, Microsoft Defender voor Eindpunt, edr, Windows Defender
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
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: e8abf10bd036b5e6e76d08e86ab4963629d2f994
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537989"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Overschakelen naar Microsoft Defender voor eindpunt - Fase 2: Setup

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Voorbereiden](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fase 1: Voorbereiden](switch-to-microsoft-defender-prepare.md) |![Fase 2: Instellen](images/phase-diagrams/setup.png)<br/>Fase 2: Instellen |[![Fase 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fase 3: Onboarden](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*U bent er!* | |

**Welkom bij de installatiefase van het [overstappen naar Defender voor Eindpunt.](switch-to-microsoft-defender-migration.md#the-migration-process)** Deze fase bevat de volgende stappen:

1. [U kunt de Microsoft Defender Antivirus eindpunten opnieuw installeren/inschakelen.](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)

2. [Configure Defender for Endpoint](#configure-defender-for-endpoint).

3. [Voeg Defender voor Eindpunt toe aan de lijst met uitsluitingen voor uw bestaande oplossing.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)

4. [Voeg uw bestaande oplossing toe aan de uitsluitingslijst voor Microsoft Defender Antivirus.](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)

5. [Stel uw apparaatgroepen, apparaatverzamelingen en organisatie-eenheden in.](#set-up-your-device-groups-device-collections-and-organizational-units)

6. [Antimalware-beleid en realtimebeveiliging configureren.](#configure-antimalware-policies-and-real-time-protection)


## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>Uw eindpunten opnieuw Microsoft Defender Antivirus of inschakelen

In bepaalde versies van Windows is Microsoft Defender Antivirus waarschijnlijk verwijderd of uitgeschakeld wanneer uw niet-Microsoft-antivirus-/antimalware-oplossing is geïnstalleerd. Zie Microsoft Defender Antivirus [compatibiliteit voor meer informatie.](microsoft-defender-antivirus-compatibility.md)

Wanneer Windows-clients een niet-Microsoft-antivirus-/antimalware-oplossing is geïnstalleerd, wordt Microsoft Defender Antivirus automatisch uitgeschakeld totdat deze apparaten zijn onboarded bij Defender voor Eindpunt. Wanneer de client-eindpunten zijn onboarded bij Defender voor Eindpunt, Microsoft Defender Antivirus in passieve modus totdat de niet-Microsoft-antivirusoplossing is verwijderd. Microsoft Defender Antivirus moet nog steeds worden geïnstalleerd, maar is waarschijnlijk uitgeschakeld op dit punt van het migratieproces. Tenzij Microsoft Defender Antivirus is verwijderd, hoeft u geen actie te ondernemen voor uw Windows clients.

Op Windows servers, wanneer een niet-Microsoft antivirus/antimalware is geïnstalleerd, wordt Microsoft Defender Antivirus handmatig uitgeschakeld (indien niet verwijderd). De volgende taken helpen ervoor te zorgen dat Microsoft Defender Antivirus is geïnstalleerd en ingesteld op passieve modus op Windows Server.

- [DisableAntiSpyware instellen op onwaar op Windows Server](#set-disableantispyware-to-false-on-windows-server) (alleen indien nodig)

- [Opnieuw Microsoft Defender Antivirus op Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server) 

- [De Microsoft Defender Antivirus op passieve modus instellen op Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)

### <a name="set-disableantispyware-to-false-on-windows-server"></a>DisableAntiSpyware instellen op onwaar op Windows Server

De [registersleutel DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is in het verleden gebruikt om Microsoft Defender Antivirus uit te schakelen en een ander antivirusproduct te implementeren, zoals McAfee, Symantec of andere. Over het algemeen moet u deze registersleutel niet op uw Windows apparaten en eindpunten hebben. Als u echter wel hebt geconfigureerd, kunt u als volgende de waarde instellen `DisableAntiSpyware` op onwaar:

1. Open registereditor op Windows serverapparaat.

2. Navigeer naar `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` .

3. Zoek in die map naar een DWORD-item **genaamd DisableAntiSpyware.**
   - Als u dat item niet ziet, bent u klaar.
   - Als u **DisableAntiSpyware ziet,** gaat u verder met stap 4.

4. Klik met de rechtermuisknop op DWORD DisableAntiSpyware en kies **Vervolgens Wijzigen.**

5. Stel de waarde in op `0` . (Met deze actie stelt u de waarde van de registersleutel in op *onwaar*.)

> [!TIP]
> Zie [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)voor meer informatie over deze registersleutel.

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Opnieuw Microsoft Defender Antivirus op Windows Server

> [!IMPORTANT]
> De volgende procedure is alleen van toepassing op eindpunten of apparaten met de volgende versies van Windows:
> - Windows Server 2019
> - Windows Server, versie 1803 (alleen-kernmodus)
> - Windows Server 2016 (zie de volgende [sectie, Gebruikt u Windows Server 2016?](#are-you-using-windows-server-2016))

1. Als een lokale beheerder op het eindpunt of apparaat, opent u Windows PowerShell.

2. Voer de volgende PowerShell-cmdlets uit: <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <p>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
    > [!NOTE]
    > Wanneer u de opdracht DISM gebruikt in een taakreeks met PS, is het volgende pad naar cmd.exe vereist.
    > Voorbeeld:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<p>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Gebruik de volgende PowerShell-cmdlet om te controleren of Microsoft Defender Antivirus wordt uitgevoerd: <br/>
   `Get-Service -Name windefend`

   Zoek naar een status van *Uitvoeren.*

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>De Microsoft Defender Antivirus op passieve modus instellen op Windows Server

1. Registereditor openen en vervolgens naar <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Bewerk (of maak) een DWORD-item met de naam **ForcePassiveMode** en geef de volgende instellingen op:
   - Stel de waarde van DWORD in op **1**.
   - Selecteer **onder Basis** de optie **Hexadecimaal**.

> [!NOTE]
> Na onboarding bij Defender voor Endpoint moet u mogelijk de Microsoft Defender Antivirus op passieve modus op Windows Server.

### <a name="are-you-using-windows-server-2016"></a>Gebruikt u Windows Server 2016?

Als u eindpunten hebt die Windows Server 2016, kunt u Microsoft Defender Antivirus naast een niet-Microsoft-antivirus-/antimalware-oplossing uitvoeren. Microsoft Defender Antivirus kan niet worden uitgevoerd in de passieve modus op Windows Server 2016. In dit geval moet u de niet-Microsoft-antivirus-/antimalware-oplossing verwijderen en in plaats daarvan Microsoft Defender Antivirus installeren/inschakelen. Zie Compatibiliteit van antivirusoplossingen met Defender voor Eindpunt voor [meer informatie.](microsoft-defender-antivirus-compatibility.md)

Als u een Windows Server 2016 gebruikt en problemen hebt met het inschakelen van Microsoft Defender Antivirus, gebruikt u de volgende PowerShell-cmdlet:

`mpcmdrun -wdenable`

Zie voor meer informatie [Microsoft Defender Antivirus op Windows Server.](microsoft-defender-antivirus-on-windows-server.md)

## <a name="configure-defender-for-endpoint"></a>Defender configureren voor eindpunt

Deze stap van het migratieproces omvat het configureren van Microsoft Defender Antivirus voor uw eindpunten. We raden u aan Intune te gebruiken. U kunt echter een van de methoden die in de volgende tabel worden weergegeven:

|Methode  |Wat moet u doen?  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**OPMERKING:** Intune maakt nu deel uit van Microsoft Endpoint Manager. | 1. Ga naar het [Microsoft Endpoint Manager en meld](https://go.microsoft.com/fwlink/?linkid=2109431) u aan.<p> 2. Selecteer **Apparaten**  >  **configuratieprofielen** en selecteer vervolgens het profieltype dat u wilt configureren. Als u nog geen  profieltype Apparaatbeperkingen hebt gemaakt of als u een nieuw profiel wilt maken, gaat u naar Instellingen voor apparaatbeperkingen [configureren in](/intune/device-restrictions-configure)Microsoft Intune.<p> 3. Selecteer **Eigenschappen** en selecteer **vervolgens Configuratie-instellingen: Bewerken.**<p> 4. Vouw **de Microsoft Defender Antivirus.** <p> 5. **Beveiliging via de cloud inschakelen.**<p> 6. Selecteer in **de vervolgkeuze van** Gebruikers vragen vóór voorbeeldinzending de optie **Alle voorbeelden automatisch verzenden.**<p> 7. Selecteer in **de vervolgkeuze** van Mogelijk ongewenste toepassingen detecteren de optie **Inschakelen** of **Controleren.**<p> 8. Selecteer **Controleren + opslaan** en kies vervolgens **Opslaan.**<p>**TIP**: Zie Wat zijn Microsoft Intune apparaatprofielen? voor meer informatie [over intune-apparaatprofielen,](/intune/device-profiles)waaronder hoe u hun instellingen kunt maken en configureren.|
|Configuratiescherm in Windows     |Volg de richtlijnen hier: [Schakel de Microsoft Defender Antivirus.](/mem/intune/user-help/turn-on-defender-windows) <p>**OPMERKING:** Mogelijk ziet *u* Windows Defender Antivirus in plaats van *Microsoft Defender Antivirus* in sommige versies van Windows.        |
|[Geavanceerd groepsbeleidsbeheer](/microsoft-desktop-optimization-pack/agpm/) <br/>of<br/>[Groepsbeleidsbeheerconsole](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  | 1. Ga naar **Beheersjablonen voor computerconfiguratie**  >    >  **Windows onderdelen**  >  **Microsoft Defender Antivirus**. <p> 2. Zoek naar een beleid met de naam **Uitschakelen Microsoft Defender Antivirus.**<p> 3. Kies **Beleidsinstelling bewerken** en zorg ervoor dat beleid is uitgeschakeld. Met deze actie kunt u Microsoft Defender Antivirus. <p>**OPMERKING:** Mogelijk ziet *u* Windows Defender Antivirus in plaats van *Microsoft Defender Antivirus* in sommige versies van Windows. |

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Microsoft Defender voor Eindpunt toevoegen aan de uitsluitingslijst voor uw bestaande oplossing

In deze stap van het installatieproces wordt Defender voor Eindpunt toegevoegd aan de uitsluitingslijst voor uw bestaande oplossing voor eindpuntbeveiliging en andere beveiligingsproducten die uw organisatie gebruikt. 

> [!TIP]
> Raadpleeg de documentatie van uw oplossingsprovider voor hulp bij het configureren van uitsluitingen.

De specifieke uitsluitingen die u moet configureren, zijn afhankelijk van de versie Windows uw eindpunten of apparaten worden uitgevoerd en worden weergegeven in de volgende tabel:

|BESTURINGSSYSTEEM |Uitsluitingen |
|--|--|
|Windows 10, [versie 1803](/windows/release-health/status-windows-10-1803) of hoger (Zie [Windows 10 releasegegevens](/windows/release-health/release-information))<p>Windows 10, versie 1703 of 1709 met [KB4493441 geïnstalleerd](https://support.microsoft.com/help/4493441) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server, versie 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**OPMERKING:** Tijdelijke hostbestanden bewaken 6\45 kan verschillende genummerde submappen zijn. <p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Voeg uw bestaande oplossing toe aan de lijst met uitsluitingen voor Microsoft Defender Antivirus

Tijdens deze stap van het installatieproces voegt u uw bestaande oplossing toe aan de Microsoft Defender Antivirus lijst met uitsluitingen. U kunt kiezen uit verschillende methoden om uw uitsluitingen toe te voegen aan Microsoft Defender Antivirus, zoals vermeld in de volgende tabel:

|Methode | Wat moet u doen?|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**OPMERKING:** Intune maakt nu deel uit van Microsoft Endpoint Manager. | 1. Ga naar het [Microsoft Endpoint Manager en meld](https://go.microsoft.com/fwlink/?linkid=2109431) u aan.<p> 2. Selecteer  >  **Apparaatconfiguratieprofielen** en selecteer vervolgens het profiel dat u wilt configureren.<p> 3. Selecteer **onder Beheren** de optie **Eigenschappen**.<p> 4. Selecteer **Configuratie-instellingen: Bewerken**.<p> 5. **Vouw** Microsoft Defender Antivirus uit en vouw de Microsoft Defender Antivirus **uitsluitingen uit.**<p> 6. Geef de bestanden en mappen, extensies en processen op die u wilt uitsluiten van Microsoft Defender Antivirus scans. Zie voor meer informatie [Microsoft Defender Antivirus uitsluitingen.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<p> 7. Kies **Controleren + opslaan** en kies vervolgens **Opslaan.**  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) | 1. Ga met [de console Configuration Manager](/mem/configmgr/core/servers/manage/admin-console)naar Assets and **Compliance**  >  **Endpoint Protection**  >  **Antimalware Policies** en selecteer vervolgens het beleid dat u wilt wijzigen. <p> 2. Geef uitsluitingsinstellingen op voor bestanden en mappen, extensies en processen die moeten worden uitgesloten van Microsoft Defender Antivirus scans. |
|[Groepsbeleidsobject](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Open op uw computer [](https://technet.microsoft.com/library/cc731212.aspx)voor groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**<p> 2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**<p> 3. Vouw de boom uit Windows **onderdelen > Microsoft Defender Antivirus > Uitsluitingen**.<br/>**OPMERKING:** Mogelijk ziet *u* Windows Defender Antivirus in plaats van *Microsoft Defender Antivirus* in sommige versies van Windows.<p> 4. Dubbelklik op de instelling **Paduitsluitingen** en voeg de uitsluitingen toe.<br/>- Stel de optie in op **Ingeschakeld.**<br/>- Selecteer onder **de** sectie Opties de optie **Toon...**.<br/>- Geef elke map op een eigen regel op onder de **kolom Waardenaam.**<br/>- Als u een bestand opgeeft, moet u een volledig gekwalificeerd pad naar het bestand invoeren, inclusief de stationletter, het mappenpad, de bestandsnaam en de extensie. Voer **0** in de kolom **Waarde** in.<p> 5. Selecteer **OK**.<p> 6. Dubbelklik op de instelling Uitsluitingen voor **extensies** en voeg de uitsluitingen toe.<br/>- Stel de optie in op **Ingeschakeld.**<br/>- Selecteer onder **de** sectie Opties de optie **Toon...**.<br/>- Voer elke bestandsextensie op een eigen regel in onder de **kolom Waardenaam.**  Voer **0** in de kolom **Waarde** in.<p> 7. Selecteer **OK**. |
|Lokaal groepsbeleidsobject |1. Open de Editor voor lokaal groepsbeleid op het eindpunt of apparaat. <p>2. Ga naar **Beheersjablonen voor computerconfiguratie**  >    >  **Windows onderdelen**  >  **Microsoft Defender Antivirus**  >  **Uitsluitingen**.<p>**OPMERKING:** Mogelijk ziet *u* Windows Defender Antivirus in plaats van *Microsoft Defender Antivirus* in sommige versies van Windows.<p>3. Geef uw pad en procesuitsluitingen op. |
|Registersleutel |1. Exporteert u de volgende registersleutel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Importeer de registersleutel. Hier zijn twee voorbeelden:<br/>- Lokaal pad: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Netwerk delen: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>Houd rekening met de volgende punten over uitsluitingen

Wanneer u [uitsluitingen toevoegt aan Microsoft Defender Antivirus scans,](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)moet u pad- en procesuitsluitingen toevoegen. Houd rekening met de volgende punten:

- *Paduitsluitingen sluiten* specifieke bestanden en toegang tot die bestanden uit.

- *Uitsluitingen van processen* sluiten uit wat een proces raakt, maar sluit het proces zelf niet uit.

- Vermeld uw procesuitsluitingen met hun volledige pad en niet alleen op hun naam. (De methode voor alleen-naam is minder veilig.)

- Als u elke uitvoerbare (.exe) als zowel een paduitsluiting als een procesuitsluiting oplijst, wordt het proces en wat het ook raakt, uitgesloten.


## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Uw apparaatgroepen, apparaatverzamelingen en organisatie-eenheden instellen

Apparaatgroepen, apparaatverzamelingen en organisatie-eenheden stellen uw beveiligingsteam in staat om beveiligingsbeleid efficiënt en effectief te beheren en toe te wijzen. In de volgende tabel worden deze groepen beschreven en wordt beschreven hoe u deze kunt configureren. Uw organisatie gebruikt mogelijk niet alle drie de verzamelingstypen.

| Verzamelingstype | Wat moet u doen? |
|--|--|
|[Met apparaatgroepen](/microsoft-365/security/defender-endpoint/machine-groups) (voorheen *machinegroepen* genoemd) kan uw beveiligingsteam beveiligingsfuncties configureren, zoals geautomatiseerd onderzoek en herstel.<p>Apparaatgroepen zijn ook handig voor het toewijzen van toegang tot deze apparaten, zodat uw team voor beveiligingsbewerkingen indien nodig herstelacties kan uitvoeren. <p>Apparaatgroepen worden gemaakt in de [Microsoft Defender-beveiligingscentrum.](microsoft-defender-security-center.md) |1. Ga naar de Microsoft Defender-beveiligingscentrum ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. Kies in het navigatiedeelvenster aan de linkerkant **Instellingen**  >  **Machtigingen**  >  **Apparaatgroepen**.  <p>3. Kies **+ Apparaatgroep toevoegen.**<p>4. Geef een naam en beschrijving op voor de apparaatgroep.<p>5. Selecteer een optie in de lijst **Automatiseringsniveau.** (We raden **u aan om bedreigingen automatisch te** corrigeren .) Zie Hoe bedreigingen worden gesaneerd voor meer informatie over de verschillende [automatiseringsniveaus.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<p>6. Geef voorwaarden op voor een overeenkomende regel om te bepalen welke apparaten tot de apparaatgroep behoren. U kunt bijvoorbeeld een domein, besturingssysteemversies of zelfs apparaatlabels [gebruiken.](/microsoft-365/security/defender-endpoint/machine-tags)<p>7. Geef op **het tabblad Gebruikerstoegang** rollen op die toegang moeten hebben tot de apparaten die zijn opgenomen in de apparaatgroep. <p>8. Kies **Klaar**. |
|[Met apparaatverzamelingen](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) kan uw beveiligingsteam toepassingen beheren, nalevingsinstellingen implementeren of software-updates installeren op de apparaten in uw organisatie.<p>Apparaatverzamelingen worden gemaakt met [Configuration Manager.](/mem/configmgr/) |Volg de stappen in [Een verzameling maken.](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[Met organisatie-eenheden](/azure/active-directory-domain-services/create-ou) kunt u objecten, zoals gebruikersaccounts, serviceaccounts of computeraccounts, logisch groeperen. Vervolgens kunt u beheerders toewijzen aan specifieke organisatie-eenheden en groepsbeleid toepassen om gerichte configuratie-instellingen af te dwingen.<p> Organisatie-eenheden worden gedefinieerd in [Azure Active Directory Domain Services.](/azure/active-directory-domain-services) | Volg de stappen in [Een organisatie-eenheid maken in een Azure Active Directory Domeinservices beheerd domein.](/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Antimalware-beleid en realtimebeveiliging configureren

Configureer uw antimalwarebeleid met Behulp van Configuration Manager en uw apparaatverzameling(en).

- Zie [Antimalware-beleid maken](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)en implementeren voor Endpoint Protection in Configuration Manager.

- Terwijl u uw antimalwarebeleid maakt en configureert, controleert u de [realtime](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) beveiligingsinstellingen en stelt u blok op het [eerste gezicht in.](configure-block-at-first-sight-microsoft-defender-antivirus.md)

> [!TIP]
> U kunt het beleid implementeren vóór de apparaten van uw organisatie in onboarded.

## <a name="next-step"></a>Volgende stap

**Gefeliciteerd!** U hebt de installatiefase van het [overstappen naar Defender voor Eindpunt voltooid!](switch-to-microsoft-defender-migration.md#the-migration-process)

- [Doorgaan naar fase 3: Onboard to Defender for Endpoint](switch-to-microsoft-defender-onboard.md)
