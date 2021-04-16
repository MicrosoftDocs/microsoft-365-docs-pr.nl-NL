---
title: Eerdere versies van Windows aan boord van Microsoft Defender voor Eindpunt
description: Ondersteunde eerdere versies van Windows-apparaten aan boord, zodat ze sensorgegevens kunnen verzenden naar de Microsoft Defender voor Eindpunt-sensor
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 945645e0f20f316c094f746adb6ba193f6806f86
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861357"
---
# <a name="onboard-previous-versions-of-windows"></a>Onboarden eerdere versies van Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Platforms**
- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)

Defender voor Eindpunt breidt de ondersteuning uit met besturingssystemen op lager niveau, met geavanceerde mogelijkheden voor detectie van aanvallen en onderzoeksmogelijkheden voor ondersteunde Windows-versies.

Als u windows-client-eindpunten op een lager niveau wilt in- en onboarden bij Defender voor Eindpunt, moet u het volgende doen:
- System Center Endpoint Protection-clients configureren en bijwerken.
- Installeer en configureer Microsoft Monitoring Agent (MMA) om sensorgegevens te rapporteren aan Defender voor Eindpunt, zoals hieronder wordt beschreven.

> [!TIP]
> Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of het apparaat correct is aan boord van de service. Zie Een detectietest uitvoeren op een nieuw ingebouwde [Defender voor eindpunten voor meer informatie.](run-detection-test.md)

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>System Center Endpoint Protection-clients configureren en bijwerken
> [!IMPORTANT]
> Deze stap is alleen vereist als uw organisatie System Center Endpoint Protection (SCEP) gebruikt.

Defender for Endpoint is geïntegreerd met System Center Endpoint Protection om malwaredetecties zichtbaar te maken en de verspreiding van een aanval in uw organisatie te stoppen door potentieel schadelijke bestanden of verdachte malware te verbieden. 

De volgende stappen zijn vereist om deze integratie mogelijk te maken: 
- De update [van het anti-malwareplatform van januari 2017 installeren voor endpoint protection-clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- Het lidmaatschap van de SCEP-client Cloud Protection Service configureren op **de instelling Geavanceerd**
- Configureer uw netwerk om verbindingen met de Microsoft Defender Antivirus-cloud toe te staan. Zie Verbindingen toestaan [met de Microsoft Defender Antivirus-cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud) voor meer informatie.

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Microsoft Monitoring Agent (MMA) installeren en configureren om sensorgegevens te rapporteren aan Microsoft Defender voor Eindpunt

### <a name="before-you-begin"></a>Voordat u begint
Bekijk de volgende details om de minimale systeemvereisten te controleren:
- De maandelijkse update van [februari 2018 installeren](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Alleen van toepassing op Windows 7 SP1 Enterprise en Windows 7 SP1 Pro. 

- De [update voor klantervaring en diagnostische telemetrie installeren](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Installeer [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) of [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Alleen van toepassing op Windows 7 SP1 Enterprise en Windows 7 SP1 Pro.
    > Installeer .NET Framework 4.0.x niet, omdat de bovenstaande installatie wordt ontbonden.

- Voldoe aan de minimale systeemvereisten voor Azure Log Analytics-agent. Zie Gegevens verzamelen van computers in uw omgeving met Log Analytics voor [meer informatie.](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. Download het installatiebestand van de agent: [Windows 64-bits agent](https://go.microsoft.com/fwlink/?LinkId=828603) of [Windows 32-bits agent.](https://go.microsoft.com/fwlink/?LinkId=828604)

2. De werkruimte-id verkrijgen:
   - Selecteer in het navigatiedeelvenster Defender voor eindpunt de optie **Instellingen > Apparaatbeheer > Onboarding**
   - Selecteer **Windows 7 SP1 en 8.1** als het besturingssysteem
   - De werkruimte-id en -werkruimtecode kopiëren

3. Kies een van de volgende installatiemethoden om de agent te installeren met behulp van de werkruimte-id en de werkruimtetoets:
    - [Installeer de agent handmatig met installatie](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
      Selecteer op **de pagina Opties voor** agentconfiguratie de optie Verbinding maken met Azure Log Analytics **(OMS)**
    - [Installeer de agent met de opdrachtregel](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configureer de agent met behulp van een script.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)

   > [!NOTE]
   > Als u een klant van de Amerikaanse overheid bent [,](gov.md)moet u onder 'Azure Cloud' de parameter 'Azure US Government' kiezen als u de installatiewizard gebruikt of als u een opdrachtregel of een script gebruikt. Stel de parameter 'OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE' in op 1.

4. Zie de sectie Proxyinstellingen configureren als u een proxy gebruikt om verbinding te maken met internet.

Wanneer u klaar bent, ziet u binnen een uur onboarded eindpunten in de portal.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Proxy- en internetconnectiviteitsinstellingen configureren
 
- Elk Windows-eindpunt moet verbinding kunnen maken met internet via HTTPS. Deze verbinding kan rechtstreeks zijn, met behulp van een proxy of via de [OMS Gateway.](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)
- Als een proxy of firewall standaard al het verkeer blokkeert en alleen specifieke domeinen via of HTTPS-scannen (SSL-inspectie) is ingeschakeld, moet u ervoor zorgen dat u toegang tot URL's van de Defender voor [Eindpunt-service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)inschakelen.

## <a name="offboard-client-endpoints"></a>Offboard client-eindpunten
Als u offboard wilt, kunt u de MMA-agent van het eindpunt verwijderen of deze loskoppelen van de rapportage naar uw Werkruimte Defender voor Eindpunt. Na het offboarden van de agent verzendt het eindpunt geen sensorgegevens meer naar Defender voor Eindpunt. 

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)

