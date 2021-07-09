---
title: Apparaatproxy- en internetverbindingsinstellingen configureren
description: Configureer de Microsoft Defender voor eindpuntproxy- en internetinstellingen om communicatie met de cloudservice in te stellen.
keywords: configureren, proxy, internet, internetverbinding, instellingen, proxy-instellingen, netsh, winhttp, proxyserver
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6a3bbc46bb5859743d5170451b0d1c68793f93bf
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338707"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Instellingen voor apparaatproxy en internetverbinding configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Voor de Defender for Endpoint-sensor moet Microsoft Windows HTTP (WinHTTP) sensorgegevens rapporteren en communiceren met de Defender for Endpoint-service.

De ingesloten Defender voor Eindpunt-sensor wordt uitgevoerd in systeemcontext met behulp van het LocalSystem-account. De sensor gebruikt Microsoft Windows HTTP Services (WinHTTP) om communicatie met de Defender for Endpoint-cloudservice in te stellen.

> [!TIP]
> Organisaties die forward proxy's gebruiken als gateway voor internet, kunt netwerkbeveiliging gebruiken om een proxy te onderzoeken. Zie [Verbindingsgebeurtenissen achter forward proxy's onderzoeken](investigate-behind-proxy.md) voor meer informatie.

De configuratie-instelling WinHTTP is onafhankelijk van de instellingen Windows Internet (WinINet) voor internetbrowsingsproxy en kan alleen een proxyserver vinden met behulp van de volgende detectiemethoden:

- Methoden voor automatische detectie:

  - Transparante proxy

  - WPAD (Web Proxy Auto Discovery Protocol)

    > [!NOTE]
    > Als u Transparante proxy of WPAD gebruikt in de netwerktopologie, hebt u geen speciale configuratie-instellingen nodig. Zie Access [to Defender for Endpoint service URLLs in](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)de proxy inschakelen voor meer informatie over URL-uitsluitingen van Defender voor eindpunten in de proxy.

- Hnadmatige statische proxyconfiguratie

  - Configuratie op basis van register

  - WinHTTP geconfigureerd met de Netsh-opdracht– Alleen geschikt voor desktops in een stabiele topologie (bijvoorbeeld: een bureaublad in een bedrijfsnetwerk achter dezelfde proxy)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>De proxyserver handmatig configureren met een statische proxy op basis van het register

Configureer een statische proxy op basis van het register zodat alleen defender voor eindpunten-sensor diagnostische gegevens kan rapporteren en kan communiceren met Defender voor eindpuntservices als een computer geen verbinding mag maken met internet.

> [!NOTE]
> Wanneer u deze optie gebruikt op Windows 10 of Windows Server 2019, wordt het aanbevolen om de volgende (of latere) build- en cumulatieve update-rollup te hebben:
>
> - Windows 10 versie 1809 of Windows Server 2019 -https://support.microsoft.com/kb/5001384
> - Windows 10, versie 1909 -https://support.microsoft.com/kb/4601380
> - Windows 10, versie 2004 -https://support.microsoft.com/kb/4601382
> - Windows 10, versie 20H2 -https://support.microsoft.com/kb/4601382
>
> Deze updates verbeteren de connectiviteit en betrouwbaarheid van het CnC-kanaal (Command and Control).

De statische proxy kan worden geconfigureerd via Group Policy (GP). U vindt het groepsbeleid onder:

- **Beheersjablonen > Windows Onderdelen > Gegevensverzameling en Preview-builds > Geverifieerd proxygebruik configureren voor de verbonden gebruikerservaring en telemetrieservice**

  Stel deze in **op Ingeschakeld en** selecteer Geverifieerd **proxygebruik uitschakelen.**

  ![Afbeelding van groepsbeleidsinstelling1](images/atp-gpo-proxy1.png)

- **Beheersjablonen > Windows Onderdelen > Gegevensverzameling en Preview-builds > Verbonden gebruikerservaringen en telemetrie configureren:**

  De peoxy configureren

  ![Afbeelding van groepsbeleidsinstelling2](images/atp-gpo-proxy2.png)

  Met het beleid worden twee registerwaarden, `TelemetryProxyServer` als REG_SZ en `DisableEnterpriseAuthProxy` REG_DWORD, onder de registersleutel. `HKLM\Software\Policies\Microsoft\Windows\DataCollection`

  De registerwaarde `TelemetryProxyServer` heeft de volgende tekenreeksindeling:

  ```text
  <server name or ip>:<port>
  ```

  Bijvoorbeeld: 10.0.0.6:8080

  De registerwaarde `DisableEnterpriseAuthProxy` moet worden ingesteld op 1.

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>De proxyserver handmatig configureren met de opdracht Netsh

Gebruik netsh om een statische proxy voor het hele systeem te configureren.

> [!NOTE]
>
> - Dit is van invloed op alle toepassingen, inclusief Windows-services die WinHTTP met standaardproxy gebruiken.</br>
> - Laptops die de topologie wijzigen (bijvoorbeeld van kantoor naar thuis) werken niet goed met netsh. Gebruik de statische proxyconfiguratie op basis van het register.

1. Open een verhoogde opdrachtregel:

   1. Go to **Start** and type **cmd**.

   1. Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.

2. Voer de volgende opdracht in en druk op **Enter**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Bijvoorbeeld:`netsh winhttp set proxy 10.0.0.6:8080`

Voer de volgende opdracht in en druk op **Enter** om de winhttp proxy opnieuw in te stellen:

```PowerShell
netsh winhttp reset proxy
```

Zie [Syntaxis, contexten en opmaak van Netsh](/windows-server/networking/technologies/netsh/netsh-contexts) meer informatie.

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>Toegang tot URL's van microsoft Defender voor eindpuntservice inschakelen op de proxyserver

Als door een proxy of firewall standaard al het verkeer wordt geblokkeerd en alleen bepaalde domeinen worden toegestaan, voegt u de domeinen die worden vermeld in het downloadbare blad toe aan de lijst met toegestane domeinen.

In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken. U moet ervoor zorgen dat er geen firewall- of netwerkfilterregels zijn die de  toegang tot deze URL's weigeren, of u moet mogelijk een regel voor toestaan speciaal voor deze url's maken.

| Spreadsheet met domeinenlijst | Omschrijving |
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem. <br><br>[Download de spreadsheet hier.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

Als https-scannen (SSL-controle) is ingeschakeld voor een proxy of firewall, moet u de domeinen in de bovenstaande tabel uitsluiten van HTTPS-scannen.

> [!NOTE]
> settings-win.data.microsoft.com is alleen nodig als u Windows 10 hebt met versie 1803 of eerder.<br>
>
> URL's die v20 bevatten, zijn alleen nodig als u Windows 10 apparaten met versie 1803 of hoger hebt. Dit is bijvoorbeeld nodig voor een Windows 10 met versie 1803 of hoger en is aan boord van us `us-v20.events.data.microsoft.com` Data Storage regio.
>
> Zie Netwerkverbindingen configureren Microsoft Defender Antivirus cloudservice als u Microsoft Defender Antivirus [in uw omgeving gebruikt.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)

Als een proxy of firewall anoniem verkeer blokkeert, aangezien defender voor eindpunten vanuit de systeemcontext verbinding maakt, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA) - proxy- en firewallvereisten voor oudere versies van Windows client of Windows Server

In de onderstaande informatie vindt u de configuratiegegevens van de proxy en firewall die nodig zijn om te communiceren met loganalyseagent (ook wel Microsoft Monitoring Agent genoemd) voor de vorige versies van Windows, zoals Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 en Windows Server 2016.

|Agent-resource|Poorten |Richting |HTTPS-inspectie omzeilen|
|------|---------|--------|--------|
|*.ods.opinsights.azure.com |Poort 443 |Uitgaand|Ja |  
|*.oms.opinsights.azure.com |Poort 443 |Uitgaand|Ja |  
|*.blob.core.windows.net |Poort 443 |Uitgaand|Ja |
|*.azure-automation.net |Poort 443 |Uitgaand|Ja |  

> [!NOTE]
> Als cloudoplossing kan het IP-bereik veranderen. U wordt aangeraden over te gaan naar de instelling VOOR DNS-oplossing.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Microsoft Monitoring Agent (MMA) Service URL-vereisten bevestigen 

Raadpleeg de volgende richtlijnen om de vereiste jokerteken (*) voor uw specifieke omgeving te verwijderen wanneer u de Microsoft Monitoring Agent (MMA) gebruikt voor eerdere versies van Windows.

1. Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see Onboard previous [versions of Windows](https://go.microsoft.com/fwlink/p/?linkid=2010326) on Defender for Endpoint and Onboard Windows [servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).

2. Controleer of de computer succesvol rapporteert in de Microsoft 365 Defender portal.

3. Voer het TestCloudConnection.exe uit van 'C:\Program Files\Microsoft Monitoring Agent\Agent' om de connectiviteit te valideren en om de vereiste URL's voor uw specifieke werkruimte te bekijken.

4. Controleer de lijst MET URL's van Microsoft Defender voor eindpunten voor de volledige lijst met vereisten voor uw regio (raadpleeg het spreadsheet [Service-URL's](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).

    ![Afbeelding van beheerder in Windows PowerShell](images/admin-powershell.png)

De jokertekens () die worden gebruikt \* in \* .ods.opinsights.azure.com, .oms.opinsights.azure.com en .agentsvc.azure-automation.net URL-eindpunten kunnen worden vervangen door uw specifieke \* werkruimte-id. \* De werkruimte-id is specifiek voor uw omgeving en werkruimte en is te vinden in de sectie Onboarding van uw tenant binnen de Microsoft 365 Defender portal.

Het .blob.core.windows.net URL-eindpunt kan worden vervangen door de URL's die worden weergegeven in de sectie \* Firewallregel: \* .blob.core.windows.net' van de testresultaten.

> [!NOTE]
> In het geval van onboarding via Azure Defender worden mogelijk meerdere werkruimten gebruikt. U moet de bovenstaande TestCloudConnection.exe uitvoeren op een onboarded machine vanuit elke werkruimte (om te bepalen of er wijzigingen zijn in de *.blob.core.windows.net-URL's tussen de werkruimten).

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>Clientconnectiviteit verifiëren met URL's van Microsoft Defender voor endpoint-service

Controleer of de proxyconfiguratie is voltooid, of WinHTTP de proxyserver in uw omgeving kan vinden en communiceren, en of via de proxyserver verkeer wordt toegestaan naar de URL's van de Defender for Endpoint-service.

1. Download het [hulpprogramma MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) naar de pc waarop de Defender for Endpoint-sensor wordt uitgevoerd.

2. Pak de inhoud van MDATPClientAnalyzer.zip uit op het apparaat.

3. Open een verhoogde opdrachtregel:

   1. Go to **Start** and type **cmd**.

   1. Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.

4. Voer de volgende opdracht in en druk op **Enter**:

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    Vervang *HardDrivePath* door het pad waar het hulpprogramma MDATPClientAnalyzer naar is gedownload, bijvoorbeeld:

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. Haal het *MDATPClientAnalyzerResult.zip* bestand op dat is gemaakt met het hulpprogramma in de map die wordt gebruikt in *HardDrivePath.*

6. Open *MDATPClientAnalyzerResult.txt* en controleer of u de configuratiestappen voor de proxy hebt uitgevoerd om serverdetectie en toegang tot de service-URL's in te stellen.

   Het hulpprogramma controleert de verbindingen van URL's van Defender voor Endpoint-service die voor Defender voor Endpoint-client zijn geconfigureerd voor interactie. Vervolgens worden de resultaten afgedrukt in het bestand *MDATPClientAnalyzerResult.txt* voor elke URL die mogelijk kan worden gebruikt voor communicatie met Defender voor Endpoint-services. Bijvoorbeeld:

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

Als minimaal één van de connectiviteitsopties een status (200) retourneert, kan de Defender voor Endpoint-client met deze connectiviteitsmethode correct communiceren met de geteste URL.

Als de resultaten van de connectiviteitscontrole echter aangeven dat er een fout is, wordt een HTTP-fout weergegeven (zie HTTP-statuscodes). U kunt vervolgens de URL's in de tabel gebruiken die wordt weergegeven in Toegang tot URL's van de Defender voor [eindpuntservice inschakelen op de proxyserver.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) De URL's die u gebruikt, zijn afhankelijk van de regio die tijdens de onboardingprocedure is geselecteerd.

> [!NOTE]
> Het hulpprogramma Connectivity Analyzer is niet compatibel met de ASR-regel [Maken van processen via PSExec- en WMI-opdrachten blokkeren](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules). Schakel deze regel tijdelijk uit om het hulpprogramma Connectivity Analyzer uit te voeren.
>
> Wanneer de TelemetryProxyServer is ingesteld, in register of via groepsbeleid, valt Defender voor Eindpunt terug naar direct als deze geen toegang heeft tot de gedefinieerde proxy.

## <a name="related-topics"></a>Gerelateerde onderwerpen

- [Onboarden Windows 10-apparaten](configure-endpoints.md)
- [Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen](troubleshoot-onboarding.md)
