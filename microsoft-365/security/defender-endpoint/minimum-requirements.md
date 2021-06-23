---
title: Minimumvereisten voor Microsoft Defender voor Eindpunt
description: De licentievereisten en -vereisten voor onboarding-apparaten voor de service begrijpen
keywords: minimumvereisten, licenties, vergelijkingstabel
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 52fa73774933ba90e8ca92dd1b337f983f5446c5
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082910"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Minimumvereisten voor Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


Er zijn enkele minimumvereisten voor onboarding-apparaten voor de service. Meer informatie over de licentie-, hardware- en softwarevereisten en andere configuratie-instellingen voor het onboarden van apparaten bij de service.

> [!TIP]
> - Meer informatie over de nieuwste verbeteringen in Defender voor Eindpunt: [Defender voor Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).
> - Defender for Endpoint heeft in de recente MITRE-evaluatie de toonaangevende mogelijkheden voor optica en detectie gedemonstreerd. Lees: [Insights van de MITRE ATT-&op CK gebaseerde evaluatie](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

## <a name="licensing-requirements"></a>Licentievereisten

Voor Microsoft Defender voor Eindpunt is een van de volgende microsoft volumelicentieaanbiedingen vereist:

- Windows 10 Enterprise E5
- Windows 10 Education A5
- Microsoft 365 E5 (M365 E5) met Windows 10 Enterprise E5
- Microsoft 365 A5 (M365 A5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 Beveiliging
- Microsoft Defender voor Eindpunt

> [!NOTE]
> In aanmerking komende gebruikers met een licentie kunnen Microsoft Defender voor Eindpunt gebruiken op maximaal vijf gelijktijdige apparaten.
> Microsoft Defender voor Eindpunt is ook beschikbaar voor aankoop via een Cloud Solution Provider (CSP).
> Voor RDSH-VM's is geen aparte Defender voor eindpuntlicentie vereist.

Voor Microsoft Defender voor eindpunten voor servers is een van de volgende licentieopties vereist:

- [Azure Security Center met Azure Defender ingeschakeld](/azure/security-center/security-center-pricing)
- Microsoft Defender voor Eindpunt voor Server (één per gedekte server)

> [!NOTE]
> Klanten kunnen serverlicenties (één per gedekte besturingssysteemomgeving voor servers) voor Microsoft Defender voor eindpunten voor servers verkrijgen als ze een gecombineerd minimum van 50 licenties hebben voor een of meer van de volgende gebruikerslicenties:
>
> * Microsoft Defender voor Eindpunt
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5/A5-beveiliging

Zie de site Productvoorwaarden voor gedetailleerde licentiegegevens [en](https://www.microsoft.com/licensing/terms/) werk samen met uw accountteam voor meer informatie over de algemene voorwaarden.

Zie Vergelijken Windows 10 voor meer informatie over de matrix met functies in Windows 10 [versies.](https://www.microsoft.com/windowsforbusiness/compare)

Zie de vergelijking PDF voor een gedetailleerde vergelijkingstabel Windows 10 vergelijking van commerciële [edities.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)

## <a name="browser-requirements"></a>Browservereisten

Toegang tot Defender voor Eindpunt wordt uitgevoerd via een browser, ter ondersteuning van de volgende browsers:

- Microsoft Edge
- Google Chrome

> [!NOTE]
> Hoewel andere browsers mogelijk werken, worden de genoemde browsers ondersteund.


## <a name="hardware-and-software-requirements"></a>Hardware- en softwarevereisten

### <a name="supported-windows-versions"></a>Ondersteunde Windows versies

- Windows 7 SP1 Enterprise ([Vereist ESU voor ondersteuning](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 7 SP1 Pro ([Vereist ESU voor ondersteuning](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC 2016 (of hoger)](/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows server
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, versie 1803 of hoger
  - Windows Server 2019
- Windows Virtual Desktop

Apparaten op uw netwerk moeten een van deze edities uitvoeren.

De hardwarevereisten voor Defender voor Eindpunt op apparaten zijn hetzelfde voor de ondersteunde versies.

> [!NOTE]
> Machines met mobiele versies van Windows (zoals Windows CE en Windows 10 Mobile) worden niet ondersteund.
>
> Virtuele machines met Windows 10 Enterprise 2016 LTSB kunnen prestatieproblemen ondervinden als ze worden uitgevoerd op niet-Microsoft-virtualisatieplatforms.
>
> Voor virtuele omgevingen is het raadzaam om Windows 10 Enterprise LTSC 2019 of hoger te gebruiken.


### <a name="other-supported-operating-systems"></a>Andere ondersteunde besturingssystemen

- [Android](microsoft-defender-endpoint-android.md)
- [iOS](microsoft-defender-endpoint-ios.md)
- [Linux](microsoft-defender-endpoint-linux.md)
- [macOS](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> U moet bevestigen dat de Linux-distributies en -versies van Android, iOS en macOS compatibel zijn met Defender voor Eindpunt om de integratie te laten werken.



### <a name="network-and-data-storage-and-configuration-requirements"></a>Vereisten voor netwerk- en gegevensopslag en -configuratie

Wanneer u de onboardingwizard voor de eerste keer uitwerkt, moet u kiezen waar uw Microsoft Defender voor endpoint-gerelateerde informatie is opgeslagen: in de Europese Unie, het Verenigd Koninkrijk of het datacenter van de Verenigde Staten.

> [!NOTE]
> - U kunt de opslaglocatie voor gegevens niet wijzigen na de eerste keer instellen.
> - Bekijk de [Microsoft Defender voor endpoint-gegevensopslag en -privacy](data-storage-privacy.md) voor meer informatie over waar en hoe Microsoft uw gegevens opbergt.


### <a name="diagnostic-data-settings"></a>Instellingen voor diagnostische gegevens

> [!NOTE]
> Voor Microsoft Defender voor Eindpunt is geen specifiek diagnostisch niveau vereist, zolang dit is ingeschakeld.

Zorg ervoor dat de diagnostische gegevensservice is ingeschakeld op alle apparaten in uw organisatie.
Deze service is standaard ingeschakeld. Het is een goede gewoonte om te controleren of u sensorgegevens van deze gegevens krijgt.

**Gebruik de opdrachtregel om het opstarttype Windows 10 diagnostische gegevensservice te controleren:**

1. Open een opdrachtregelprompt met verhoogde opdrachtregel op het apparaat:

   1.  Go to **Start** and type **cmd**.

   1.  Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.

2. Voer de volgende opdracht in en druk op **Enter:**

   ```console
   sc qc diagtrack
   ```

   Als de service is ingeschakeld, ziet het resultaat eruit als de volgende schermafbeelding:

   ![Resultaat van de opdracht sc-query voor diagtrack](images/windefatp-sc-qc-diagtrack.png)


U moet instellen dat de service automatisch wordt start als de START_TYPE **niet** is ingesteld op **AUTO_START.**


**Gebruik de opdrachtregel om de Windows 10 diagnostische gegevensservice in te stellen om automatisch te starten:**

1.  Open een opdrachtregelprompt met verhoogde opdrachtregel op het eindpunt:

    1. Go to **Start** and type **cmd**.

    1. Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.

2.  Voer de volgende opdracht in en druk op **Enter:**

    ```console
    sc config diagtrack start=auto
    ```

3.  Er wordt een succesbericht weergegeven. Controleer de wijziging door de volgende opdracht in te voeren en druk op **Enter:**

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>Internetverbinding

Internetverbinding op apparaten is rechtstreeks of via proxy vereist.

De Defender for Endpoint-sensor kan een dagelijkse gemiddelde bandbreedte van 5 MB gebruiken om te communiceren met de Defender for Endpoint-cloudservice en om cybergegevens te rapporteren. Eenmalige activiteiten, zoals het uploaden van bestanden en het verzamelen van onderzoekspakketten, worden niet opgenomen in deze dagelijkse gemiddelde bandbreedte.

Zie Apparaatproxy- en [internetverbindingsinstellingen configureren](configure-proxy-internet.md)voor meer informatie over aanvullende instellingen voor proxyconfiguratie.

Voordat u apparaten aan boord gaat, moet de diagnostische gegevensservice zijn ingeschakeld. De service is standaard ingeschakeld in Windows 10.


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender Antivirus configuratievereiste

De Defender voor Eindpunt-agent is afhankelijk van de mogelijkheid Microsoft Defender Antivirus bestanden te scannen en informatie over deze bestanden te verstrekken.

Beveiligingsintelligentie-updates configureren op de Defender voor Endpoint-apparaten, ongeacht Microsoft Defender Antivirus het actieve antimalware is of niet. Zie Updates beheren Microsoft Defender Antivirus basislijnen voor [meer informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

Als Microsoft Defender Antivirus niet de actieve antimalware in uw organisatie is en u de Service Defender voor eindpunt gebruikt, wordt Microsoft Defender Antivirus passieve modus gebruikt.

Als uw organisatie de Microsoft Defender Antivirus groepsbeleid of andere methoden heeft uitgeschakeld, moeten apparaten die zijn ingeschakeld, worden uitgesloten van dit groepsbeleid.

Als u servers onboardt en Microsoft Defender Antivirus niet de actieve antimalware op uw servers is, moeten Microsoft Defender Antivirus worden geconfigureerd om in de passieve modus te gaan of te worden verwijderd. De configuratie is afhankelijk van de serverversie. Zie Microsoft Defender Antivirus [compatibiliteit voor meer informatie.](microsoft-defender-antivirus-compatibility.md)

> [!NOTE]
> Uw normale groepsbeleid is niet van toepassing op Tamper Protection en wijzigingen in Microsoft Defender Antivirus instellingen worden genegeerd wanneer Tamper Protection is ingesteld.


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender Antivirus Elam-stuurprogramma (Early Launch Antimalware) is ingeschakeld

Als u de Microsoft Defender Antivirus als het primaire antimalwareproduct op uw apparaten gebruikt, wordt de Defender for Endpoint-agent aan boord.

Als u een antimalwareclient van derden gebruikt en mobile device management-oplossingen of Microsoft Endpoint Manager (huidige vertakking) gebruikt, moet u ervoor zorgen dat het ELAM-stuurprogramma Microsoft Defender Antivirus is ingeschakeld. Zie Ervoor zorgen dat Microsoft Defender Antivirus [niet is uitgeschakeld door beleid voor meer informatie.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)


## <a name="related-topics"></a>Verwante onderwerpen

- [Microsoft Defender instellen voor endpoint-implementatie](production-deployment.md)
- [Onboard-apparaten](onboard-configure.md)
