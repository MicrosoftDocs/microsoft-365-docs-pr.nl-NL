---
title: Windows-servers aan boord van de Microsoft Defender voor Eindpunt-service
description: Onboard Windows-servers, zodat ze sensorgegevens kunnen verzenden naar de Microsoft Defender for Endpoint-sensor.
keywords: onboard server, server, 2012r2, 2016, 2019, server onboarding, device management, configure Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 17aca5fb388aef26504902ee63b22410420c8827
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952486"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>Windows-servers aan boord van de Microsoft Defender voor Eindpunt-service

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- Windows Server 2008 R2 SP1
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server (SAC) versie 1803 en hoger
- Windows Server 2019 en hoger
- Windows Server 2019 core edition

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

Defender voor Eindpunt breidt de ondersteuning uit met het Windows Server-besturingssysteem. Deze ondersteuning biedt geavanceerde mogelijkheden voor detectie en onderzoek van aanvallen naadloos via de Microsoft Defender-beveiligingscentrumconsole.

Zie [Windows-servers](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)beveiligen met Defender voor eindpunt voor praktische richtlijnen over wat er moet worden gebruikt voor licenties en infrastructuur.

Zie [Windows-beveiligingslijnlijnen](https://docs.microsoft.com/windows/device-security/windows-security-baselines)voor informatie over het downloaden en gebruiken van Windows-beveiligingslijnlijnen voor Windows-servers.

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2008 R2 SP1, Windows Server 2012 R2 en Windows Server 2016

U kunt Windows Server 2008 R2 SP1, Windows Server 2012 R2 en Windows Server 2016 met behulp van een van de volgende opties aan boord nemen van Defender voor Eindpunt:

- **Optie 1**: [Onboard door Microsoft Monitoring Agent (MMA) te](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) installeren en te configureren
- **Optie 2**: [Onboard via Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)
- **Optie 3:** [Onboard via Microsoft Endpoint Manager versie 2002 en hoger](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)

Nadat u de onboarding-stappen hebt doorlopen met een van de opgegeven opties, moet u [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
> Defender for Endpoint standalone server license is vereist, per knooppunt, om een Windows-server aan te sluiten via Microsoft Monitoring Agent (Optie 1) of via Microsoft Endpoint Manager (optie 3). U kunt ook per knooppunt een Azure Defender for Servers-licentie gebruiken om een Windows-server aan te sluiten via Azure Security Center (optie 2), zie Ondersteunde functies die beschikbaar zijn [in Azure Defender.](https://docs.microsoft.com/azure/security-center/security-center-services)

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a>Optie 1: Onboard door Microsoft Monitoring Agent (MMA) te installeren en te configureren

U moet MMA voor Windows-servers installeren en configureren om sensorgegevens te rapporteren aan Defender voor Eindpunt. Zie Logboekgegevens verzamelen [met Azure Log Analytics-agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)voor meer informatie.

Als u System Center Operations Manager (SCOM) of Azure Monitor (voorheen Bekend als Operations Management Suite (OMS) al gebruikt, koppelt u de Microsoft Monitoring Agent (MMA) om via multihoming-ondersteuning te rapporteren aan uw Werkruimte van Defender voor Eindpunt.

Over het algemeen moet u de volgende stappen ondernemen:

1. Voldoe aan de onboarding-vereisten die worden beschreven in **De sectie Voordat u begint.**
2. Schakel servercontrole in vanuit het Microsoft Defender-beveiligingscentrum.
3. Installeer en configureer MMA voor de server om sensorgegevens te rapporteren aan Defender voor Eindpunt.
4. System Center Endpoint Protection-clients configureren en bijwerken.

> [!TIP]
> Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of het apparaat correct is aan boord van de service. Zie Een detectietest uitvoeren op een nieuw ingebouwde [Defender voor eindpunten voor meer informatie.](run-detection-test.md)

#### <a name="before-you-begin"></a>Voordat u begint

Voer de volgende stappen uit om te voldoen aan de vereisten voor onboarding:

Voor Windows Server 2008 R2 SP1 of Windows Server 2012 R2 moet u het volgende hotfix installeren:

- [Bijwerken voor klantervaring en diagnostische telemetrie](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

Controleer Windows Server 2008 R2 SP1 of u aan de volgende vereisten voldoet:

- De maandelijkse [update-rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598) van februari installeren
- Installeer [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) of [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Als u uw Windows Server 2008 R2 SP1 met SCCM beheert, installeert de SCCM-clientagent .Net Framework 4.5.2. U hoeft dus het .NET framework 4.5 (of hoger) niet te installeren.

Voor Windows Server 2008 R2 SP1 en Windows Server 2012 R2: [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
> Deze stap is alleen vereist als uw organisatie System Center Endpoint Protection (SCEP) gebruikt en u Windows Server 2008 R2 SP1 en Windows Server 2012 R2 onboardt.

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Microsoft Monitoring Agent (MMA) installeren en configureren om sensorgegevens te rapporteren aan Microsoft Defender voor Eindpunt

1. Download het installatiebestand van de agent: [Windows 64-bits agent](https://go.microsoft.com/fwlink/?LinkId=828603).

2. Kies een van de volgende installatiemethoden om de agent op de Windows-server te installeren met behulp van de werkruimte-id en de werkruimtesleutel die in de vorige procedure is verkregen:
    - [Installeer de agent handmatig met installatie](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). 
    Kies op **de pagina Opties voor** agentconfiguratie de optie Verbinding maken met Azure Log Analytics **(OMS)**.
    - [Installeer de agent met de opdrachtregel](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configureer de agent met behulp van een script.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)

> [!NOTE]
> Als u een klant van de Amerikaanse overheid bent [,](gov.md)moet u onder 'Azure Cloud' de parameter 'Azure US Government' kiezen als u de installatiewizard gebruikt of als u een opdrachtregel of een script gebruikt. Stel de parameter 'OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE' in op 1.

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a>Instellingen voor Windows-serverproxy en internetverbinding configureren indien nodig

Als uw servers een proxy moeten gebruiken om te communiceren met Defender voor Eindpunt, gebruikt u een van de volgende methoden om de MMA te configureren voor het gebruik van de proxyserver:

- [De MMA configureren voor het gebruik van een proxyserver](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [Windows configureren voor het gebruik van een proxyserver voor alle verbindingen](configure-proxy-internet.md)

Als er een proxy of firewall wordt gebruikt, moet u ervoor zorgen dat servers rechtstreeks en zonder SSL-interceptie toegang hebben tot alle URL's van de Microsoft Defender-service voor eindpunten. Zie Access to [Defender for Endpoint service URL's inschakelen](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)voor meer informatie. Het gebruik van SSL-onderschepping voorkomt dat het systeem communiceert met de Defender for Endpoint-service.

Wanneer u klaar bent, ziet u binnen een uur onboarded Windows-servers in de portal.

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a>Optie 2: Onboard Windows-servers via Azure Security Center

1. Selecteer in het navigatiedeelvenster van het Microsoft Defender-beveiligingscentrum de optie **Instellingen**  >  **Apparaatbeheer**  >  **Onboarding**.

2. Selecteer **Windows Server 2008 R2 SP1, 2012 R2 en 2016** als het besturingssysteem.

3. Klik **op Onboard Servers in Azure Security Center**.

4. Volg de onboarding-instructies in [Microsoft Defender voor](https://docs.microsoft.com/azure/security-center/security-center-wdatp) Eindpunt met Azure Defender en Als u Azure ARC gebruikt, volgt u de onboarding-instructies in Microsoft Defender voor [endpoint-integratie inschakelen.](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)

Nadat u de onboarding-stappen hebt doorlopen, moet u [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
>
> - Als onboarding via Azure Defender voor servers naar verwachting werkt, moet de server een geschikte werkruimte en sleutel hebben die is geconfigureerd binnen de MMA-instellingen (Microsoft Monitoring Agent).
> - Nadat de configuratie is geconfigureerd, wordt het juiste cloudbeheerpakket op de computer geïmplementeerd en wordt het sensorproces (MsSenseS.exe) geïmplementeerd en gestart.
> - Dit is ook vereist als de server is geconfigureerd voor het gebruik van een OMS Gateway-server als proxy.

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a>Optie 3: Windows-servers inschakelen via Microsoft Endpoint Manager versie 2002 en hoger

U kunt Windows Server 2012 R2 en Windows Server 2016 inschakelen met Microsoft Endpoint Manager versie 2002 en hoger. Zie Microsoft [Defender for Endpoint in Microsoft Endpoint Manager current branch (Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch) voor meer informatie.](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)

Nadat u de onboarding-stappen hebt doorlopen, moet u [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a>Windows Server (SAC) versie 1803, Windows Server 2019 en Windows Server 2019 Core edition

U kunt windows Server-versie 1803, Windows Server 2019 of Windows Server 2019 Core edition inschakelen met behulp van de volgende implementatiemethoden:

- [Lokaal script](configure-endpoints-script.md)
- [Groepsbeleid](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [System Center Configuration Manager 2012 / 2012 R2 1511 / 1602](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [VDI-onboarding-scripts voor niet-permanente apparaten](configure-endpoints-vdi.md)

> [!NOTE]
>
> - Het Onboarding-pakket voor Windows Server 2019 tot en met Microsoft Endpoint Manager verzendt momenteel een script. Zie Pakketten en programma's in Configuration Manager voor meer informatie over het implementeren van scripts [in Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)
> - Een lokaal script is geschikt voor een proof of concept, maar mag niet worden gebruikt voor productie-implementatie. Voor een productie-implementatie wordt aangeraden groepsbeleid of Microsoft Endpoint Configuration Manager te gebruiken.

Ondersteuning voor Windows Server biedt meer inzicht in serveractiviteiten, dekking voor detectie van kernel- en geheugenaanval en maakt reactieacties mogelijk.

1. Configureer instellingen voor onboarding van Defender voor eindpunten op de Windows-server met dezelfde hulpmiddelen en methoden voor Windows 10-apparaten. Zie Onboard [Windows 10-apparaten](configure-endpoints.md)voor meer informatie.

2. Als u een anti-malwareoplossing van derden gebruikt, moet u de volgende instellingen voor de passieve av-modus van Microsoft Defender toepassen. Controleer of deze correct is geconfigureerd:

    1. Stel de volgende registerinvoer in:
       - Pad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
       - Naam: ForceDefenderPassiveMode
       - Type: REG_DWORD
       - Waarde: 1

    1. Voer de volgende PowerShell-opdracht uit om te controleren of de passieve modus is geconfigureerd:

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. Controleer of er een recente gebeurtenis met de gebeurtenis in de passieve modus is gevonden:

       ![Afbeelding van het resultaat van verificatie in de passieve modus](images/atp-verify-passive-mode.png)

3. Voer de volgende opdracht uit om te controleren of Microsoft Defender AV is geïnstalleerd:

   ```sc.exe query Windefend```

    Als het resultaat 'De opgegeven service bestaat niet als een geïnstalleerde service' is, moet u Microsoft Defender AV installeren. Zie Microsoft [Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)voor meer informatie.

    Zie Groepsbeleidsinstellingen gebruiken om Microsoft Defender Antivirus te configureren en te beheren voor informatie over het gebruik van groepsbeleid voor het configureren en beheren van Microsoft Defender Antivirus op uw [Windows-servers.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)

## <a name="integration-with-azure-defender"></a>Integratie met Azure Defender

Defender voor Eindpunt kan worden geïntegreerd met Azure Defender om een uitgebreide windows-serverbeveiligingsoplossing te bieden. Met deze integratie kan Azure Defender de kracht van Defender voor Eindpunt gebruiken om de detectie van bedreigingen voor Windows-servers te verbeteren.

De volgende mogelijkheden zijn opgenomen in deze integratie:

- Geautomatiseerde onboarding: De Defender voor Eindpunt-sensor is automatisch ingeschakeld op Windows-servers die zijn onboarded bij Azure Defender. Zie De geïntegreerde Licentie voor [Microsoft Defender voor eindpunt](https://docs.microsoft.com/azure/security-center/security-center-wdatp)gebruiken voor meer informatie over onboarding van Azure Defender.

    > [!NOTE]
    > De integratie tussen Azure Defender voor servers en Microsoft Defender voor Eindpunt is uitgebreid met ondersteuning voor [Windows Server 2019 en Windows Virtual Desktop (WVD).](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)

- Windows-servers die worden gecontroleerd door Azure Defender, zijn ook beschikbaar in Defender voor Eindpunt: Azure Defender maakt naadloos verbinding met de Defender voor Eindpunttender, waardoor er één weergave beschikbaar is voor clients en servers.  Daarnaast zijn defender voor eindpuntwaarschuwingen beschikbaar in de Azure Defender-console.
- Serveronderzoek: Azure Defender-klanten hebben toegang tot het Microsoft Defender-beveiligingscentrum om gedetailleerd onderzoek uit te voeren om het bereik van een mogelijke inbreuk aan het licht te brengen.

> [!IMPORTANT]
> - Wanneer u Azure Defender gebruikt om servers te controleren, wordt automatisch een Defender voor Eindpunt-tenant gemaakt (in de VS voor Amerikaanse gebruikers, in de EU voor Europese en Britse gebruikers).<br>
Gegevens die door Defender voor Eindpunt worden verzameld, worden opgeslagen op de geografische locatie van de tenant die tijdens de inrichting is geïdentificeerd.
> - Als u Defender voor Eindpunt gebruikt voordat u Azure Defender gebruikt, worden uw gegevens opgeslagen op de locatie die u hebt opgegeven toen u uw tenant maakte, zelfs als u op een later tijdstip integreert met Azure Defender.
> - Nadat de gegevens zijn geconfigureerd, kunt u de locatie waarop uw gegevens zijn opgeslagen niet wijzigen. Als u uw gegevens naar een andere locatie wilt verplaatsen, moet u contact opnemen met Microsoft Support om de tenant opnieuw in te stellen. <br>
Server-eindpuntcontrole met behulp van deze integratie is uitgeschakeld voor Office 365 GCC-klanten.

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>System Center Endpoint Protection-clients configureren en bijwerken

Defender for Endpoint is geïntegreerd met System Center Endpoint Protection. De integratie biedt zichtbaarheid voor malwaredetecties en om de verspreiding van een aanval in uw organisatie te stoppen door potentieel schadelijke bestanden of verdachte malware te verbieden.

De volgende stappen zijn vereist om deze integratie mogelijk te maken:

- Installeer de update van het anti-malwareplatform van januari [2017 voor endpoint protection-clients.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)

- [Configureer het lidmaatschap van de SCEP-client Cloud Protection Service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) op **de instelling Geavanceerd.**

## <a name="offboard-windows-servers"></a>Offboard Windows-servers

U kunt Windows Server (SAC), Windows Server 2019 en Windows Server 2019 Core edition offboarden volgens dezelfde methode die beschikbaar is voor Windows 10-clientapparaten.

Voor andere Windows-serverversies hebt u twee opties voor offboard Windows-servers van de service:

- De MMA-agent verwijderen
- De configuratie van de Defender voor Eindpunt-werkruimte verwijderen

> [!NOTE]
> Offboarding zorgt ervoor dat de Windows-server stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van de Windows-server, inclusief verwijzingen naar eventuele waarschuwingen die de server heeft ontvangen, blijven maximaal 6 maanden bewaard.

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a>Windows-servers verwijderen door de MMA-agent te verwijderen

Als u de Windows-server wilt offboarden, kunt u de MMA-agent van de Windows-server verwijderen of loskoppelen van rapportage naar uw Defender voor Eindpunt-werkruimte. Na het offboarden van de agent verzendt de Windows-server geen sensorgegevens meer naar Defender voor Eindpunt.
Zie Een agent uitschakelen voor [meer informatie.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>De configuratie van de Defender voor Eindpunt-werkruimte verwijderen

Als u de Windows-server wilt uitschakelen, kunt u een van de volgende methoden gebruiken:

- De configuratie van de Defender voor eindpuntwerkruimte verwijderen uit de MMA-agent
- Een PowerShell-opdracht uitvoeren om de configuratie te verwijderen

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>De configuratie van de Defender voor eindpuntwerkruimte verwijderen uit de MMA-agent

1. Selecteer op **het tabblad Microsoft Monitoring Agent Properties** het tabblad Azure Log Analytics **(OMS).**

2. Selecteer de werkruimte Defender voor eindpunt en klik op **Verwijderen.**

    ![Afbeelding van Eigenschappen van Microsoft Monitoring Agent](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>Een PowerShell-opdracht uitvoeren om de configuratie te verwijderen

1. Uw werkruimte-id krijgen:

   1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding**.

   1. Selecteer **Windows Server 2008 R2 SP1, 2012 R2 en 2016** als het besturingssysteem en ontvang uw werkruimte-id:

      ![Afbeelding van windows-server onboarding](images/atp-server-offboarding-workspaceid.png)

2. Open een verhoogde PowerShell en voer de volgende opdracht uit. Gebruik de werkruimte-id die u hebt verkregen en `WorkspaceID` vervangt:

    ```powershell
    $ErrorActionPreference = "SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a>Onboarding Servers zonder beheeroplossing

### <a name="using-group-policy"></a>Groepsbeleid gebruiken

**Stap-1: Maak de benodigde bestanden om naar de servers te kopiëren.**

1. Ga naar c:\windows\sysvol\domain\scripts (Besturingselement wijzigen kan nodig zijn op een van de domeincontrollers.)
1. Maak een map met de naam MMA.
1. Download het volgende en plaats in de map MMA:

    **Bijwerken voor klantervaring en diagnostische telemetrie (Windows Server 2008 R2 en Windows Server 2012 R2)**

    [Voor Windows 2008 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [Voor Windows 2012 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > In dit artikel wordt ervan uitgenomen dat u x64-servers gebruikt (MMA Agent .exe x64 [New SHA-2 compliant version)](https://go.microsoft.com/fwlink/?LinkId=828603)

**Stap-2: Een bestandsnaam maken DeployMMA.cmd (met kladblok)** Voeg de volgende regels toe aan het cmd-bestand. Houd er rekening mee dat u uw werkruimte-id en -sleutel nodig hebt.

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a>Groepsbeleidsconfiguratie

Maak een nieuw groepsbeleid speciaal voor onboarding-apparaten, zoals 'Microsoft Defender for Endpoint Onboarding'.

- Een groepsbeleidsmap maken met de naam 'c:\windows\MMA'

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="mappen":::

    **Hiermee wordt op elke server een nieuwe map toegevoegd waarin het GPO wordt toegepast, genaamd MMA, en wordt deze opgeslagen in c:\windows. Dit bevat de installatiebestanden voor het MMA, de vereisten en het installatiescript.**

- Maak een groepsbeleidsbestandenvoorkeur voor elk van de bestanden die zijn opgeslagen in Net-aanmelding.

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="afbeelding groepsbeleid1":::

De bestanden worden gekopieerd van DOMAIN\NETLOGON\MMA\filename naar C:\windows\MMA\filename. De installatiebestanden zijn dus lokaal op **de server:**

:::image type="content" source="images/deploymma.png" alt-text="mma-cmd implementeren":::

Voor de twee KBs (een voor Windows Server 2008R2/Windows 7 en de andere voor Windows Server 2012 R2) herhaalt u het proces, maar maakt u op het tabblad COMMON het itemniveau, zodat het bestand alleen wordt gekopieerd naar de juiste versie van het platform/besturingssysteem in het bereik:

:::image type="content" source="images/targeteditor.png" alt-text="doeleditor":::

- Voor Windows Server 2008 R2 hebt u Windows6.1-BJ3080149-x64.msu nodig (en deze wordt alleen naar beneden kopiëren).
- Voor Windows Server 2012 R2 hebt u Windows8.1-BJ3080149-x64.msu nodig (en deze wordt alleen naar beneden kopiëren).

Wanneer dit is gedaan, moet u een opstartscriptbeleid maken:

:::image type="content" source="images/startupprops.png" alt-text="Opstarteigenschappen":::

De naam van het bestand dat hier moet worden uitgevoerd, is c:\windows\MMA\DeployMMA.cmd.
Zodra de server opnieuw is gestart als onderdeel van het opstartproces, wordt de UPDATE voor klantervaring en diagnostische telemetrie KB geïnstalleerd en vervolgens de MMA-agent geïnstalleerd, terwijl de werkruimte-id en -sleutel worden ingesteld en wordt de server aan boord gemaakt.

U kunt ook een **directe taak gebruiken om** de deployMMA.cmd uit te voeren als u niet alle servers opnieuw wilt opstarten.
Dit kan in twee fasen. Maak eerst **de bestanden en de** map in GPO: Geef het systeem de tijd om ervoor te zorgen dat het GPO is toegepast en alle servers hebben de installatiebestanden. Voeg vervolgens de directe taak toe. Dit resulteert in hetzelfde resultaat zonder dat u opnieuw moet opstarten.

Aangezien het script een exitmethode heeft en gewoon opnieuw wordt uitgevoerd als de MMA is geïnstalleerd, kunt u ook een dagelijkse geplande taak gebruiken om hetzelfde resultaat te bereiken. Net als bij een compliancebeleid van Configuration Manager wordt dagelijks gechecked om te controleren of de MMA aanwezig is.

:::image type="content" source="images/schtask.png" alt-text="planningstaak":::

:::image type="content" source="images/newtaskprops.png" alt-text="nieuwe taakeigenschappen":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="mma download props implementeren":::

:::image type="content" source="images/tasksch.png" alt-text="taakplanning":::

Zoals vermeld in de onboarding-documentatie voor Server specifiek rond Server 2008 R2, raadpleegt u hieronder:

Controleer Windows Server 2008 R2 PS1 of u voldoet aan de volgende vereisten:

- De maandelijkse update van [februari 2018 installeren](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
- Installeer [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) of [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

Controleer of de KBs aanwezig zijn voordat u Windows Server 2008 R2 Met dit proces kunt u alle servers aan boord nemen als u geen Configuration Manager-beheerservers hebt.

## <a name="related-topics"></a>Verwante onderwerpen

- [Onboarden Windows 10-apparaten](configure-endpoints.md)
- [Onboarden niet-Windows-apparaten](configure-endpoints-non-windows.md)
- [Proxy- en internetconnectiviteitsinstellingen configureren](configure-proxy-internet.md)
- [Een detectietest uitvoeren op een nieuw ingebouwde Defender voor eindpuntapparaat](run-detection-test.md)
- [Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen](troubleshoot-onboarding.md)
