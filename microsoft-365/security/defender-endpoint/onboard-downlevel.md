---
title: Eerdere versies van Windows op Microsoft Defender voor Eindpunt
description: Ondersteunde eerdere versies van apparaten Windows, zodat ze sensorgegevens kunnen verzenden naar de Microsoft Defender for Endpoint-sensor
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
ms.openlocfilehash: d0cb4a3d01c1380f4fd06999c8f81a4054e2fd00
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844428"
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

Defender voor Eindpunt breidt de ondersteuning uit met besturingssystemen op downniveau, met geavanceerde mogelijkheden voor aanvalsdetectie en onderzoek op ondersteunde Windows versies.

Als u down-level Windows client-eindpunten wilt gebruiken bij Defender voor Eindpunt, moet u het volgende doen:
- Configureer en werk System Center Endpoint Protection clients.
- Installeer en configureer Microsoft Monitoring Agent (MMA) om sensorgegevens te rapporteren aan Defender voor Eindpunt, zoals hieronder wordt beschreven.

> [!TIP]
> Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of het apparaat correct is aan boord van de service. Zie Een detectietest uitvoeren op een nieuw ingebouwde [Defender voor eindpunten voor meer informatie.](run-detection-test.md)

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Configureer en werk System Center Endpoint Protection clients
> [!IMPORTANT]
> Deze stap is alleen vereist als uw organisatie gebruikmaakt van System Center Endpoint Protection (SCEP).

Defender for Endpoint is geïntegreerd met System Center Endpoint Protection om malwaredetecties zichtbaar te maken en om de verspreiding van een aanval in uw organisatie te stoppen door potentieel schadelijke bestanden of verdachte malware te verbieden. 

De volgende stappen zijn vereist om deze integratie mogelijk te maken: 
- Installeer de update van het anti-malwareplatform van januari [2017 voor Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- Het lidmaatschap van de SCEP-client Cloud Protection Service configureren op **de instelling Geavanceerd**
- Configureer uw netwerk om verbindingen met de Microsoft Defender Antivirus toestaan. Zie Verbindingen met de Microsoft Defender Antivirus [cloud toestaan voor meer informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Microsoft Monitoring Agent (MMA) installeren en configureren om sensorgegevens te rapporteren aan Microsoft Defender voor Eindpunt

### <a name="before-you-begin"></a>Voordat u begint
Bekijk de volgende details om de minimale systeemvereisten te controleren:
- De maandelijkse update van [februari 2018 installeren](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Alleen van toepassing voor Windows 7 SP1 Enterprise en Windows 7 SP1 Pro. 

- De [update voor klantervaring en diagnostische telemetrie installeren](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Installeer [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) of [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Alleen van toepassing voor Windows 7 SP1 Enterprise en Windows 7 SP1 Pro.
    > Installeer de .NET Framework 4.0.x niet, omdat de bovenstaande installatie wordt ontbonden.

- Voldoe aan de minimale systeemvereisten voor Azure Log Analytics-agent. Zie Gegevens verzamelen van computers in uw omgeving met [Log Analytics voor meer informatie.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. Download het installatiebestand van [de agent: Windows 64-bits agent](https://go.microsoft.com/fwlink/?LinkId=828603) [of Windows 32-bits agent](https://go.microsoft.com/fwlink/?LinkId=828604).

2. De werkruimte-id verkrijgen:
   - Selecteer in het navigatiedeelvenster Defender voor eindpunt **Instellingen > Apparaatbeheer > Onboarding**
   - Selecteer **Windows 7 SP1 en 8.1** als het besturingssysteem
   - De werkruimte-id en -werkruimtecode kopiëren

3. Kies een van de volgende installatiemethoden om de agent te installeren met behulp van de werkruimte-id en de werkruimtetoets:
    - [Installeer de agent handmatig met installatie](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
      Selecteer op **de pagina Opties** voor agentinstellingen Verbinding maken agent naar Azure Log Analytics **(OMS)**
    - [Installeer de agent met de opdrachtregel](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configureer de agent met behulp van een script.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)

   > [!NOTE]
   > Als u een klant van de Amerikaanse overheid bent [,](gov.md)moet u onder 'Azure Cloud' de parameter 'Azure US Government' kiezen als u de installatiewizard gebruikt of als u een opdrachtregel of een script gebruikt. Stel de parameter 'OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE' in op 1.

4. Zie de sectie Proxyinstellingen configureren als u een proxy gebruikt om verbinding te maken met internet.

Wanneer u klaar bent, ziet u binnen een uur onboarded eindpunten in de portal.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Proxy- en internetconnectiviteitsinstellingen configureren
 
- Elk Windows eindpunt moet verbinding kunnen maken met internet via HTTPS. Deze verbinding kan rechtstreeks zijn, met behulp van een proxy of via de [OMS Gateway.](/azure/log-analytics/log-analytics-oms-gateway)
- Als een proxy of firewall standaard al het verkeer blokkeert en alleen specifieke domeinen via of HTTPS-scannen (SSL-inspectie) is ingeschakeld, moet u ervoor zorgen dat u toegang tot URL's van de Defender voor [Eindpunt-service](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)inschakelen.

## <a name="offboard-client-endpoints"></a>Offboard client-eindpunten
Als u offboard wilt, kunt u de MMA-agent van het eindpunt verwijderen of deze loskoppelen van de rapportage naar uw Werkruimte Defender voor Eindpunt. Na het offboarden van de agent verzendt het eindpunt geen sensorgegevens meer naar Defender voor Eindpunt. 

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)
