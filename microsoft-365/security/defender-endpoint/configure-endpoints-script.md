---
title: Onboarden Windows 10-apparaten met een lokaal script
description: Gebruik een lokaal script om het configuratiepakket op apparaten te implementeren, zodat ze zijn aan boord van de service.
keywords: apparaten configureren met behulp van een lokaal script, apparaatbeheer, Microsoft Defender configureren voor eindpuntapparaten
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
ms.openlocfilehash: 056268ed093d371d39a6136dd0b272c12ab6f9d7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933911"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Onboarden Windows 10-apparaten met een lokaal script

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

U kunt ook afzonderlijke apparaten handmatig aan boord brengen van Defender voor Eindpunt. Mogelijk wilt u dit eerst doen bij het testen van de service voordat u alle apparaten in uw netwerk gaat onboarden.

> [!IMPORTANT]
> Dit script is geoptimaliseerd voor gebruik op maximaal 10 apparaten.
>
> Gebruik andere implementatieopties om op schaal [te implementeren.](configure-endpoints.md) U kunt bijvoorbeeld een onboarding-script implementeren op meer dan 10 apparaten in productie met het script dat beschikbaar is op Onboard [Windows 10-apparaten met groepsbeleid.](configure-endpoints-gp.md)

## <a name="onboard-devices"></a>Onboard-apparaten 

[![Afbeelding van het PDF-bestand met de verschillende implementatiepaden](images/onboard-script.png)](images/onboard-script.png#lightbox)


Bekijk het [PDF-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  of  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) om de verschillende paden te bekijken bij de implementatie van Defender voor Eindpunt. 


1.  Open het GP-configuratiepakket .zip-bestand *(WindowsDefenderATPOnboardingPackage.zip)* dat u hebt gedownload van de wizard Service onboarding. U kunt het pakket ook in [het Microsoft Defender-beveiligingscentrum kopen:](https://securitycenter.windows.com/)

    1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding**.

    1. Selecteer Windows 10 als het besturingssysteem.

    1. Selecteer **lokaal** script in het veld **Implementatiemethode.**

    1. Klik **op Pakket downloaden** en sla het ZIP-bestand op.

  
2.  Haal de inhoud van het configuratiepakket op naar een locatie op het apparaat dat u wilt inpakken (bijvoorbeeld het bureaublad). U moet een bestand met de naam *WindowsDefenderATPOnboardingScript.cmd hebben.*

3.  Open een opdrachtregelprompt met verhoogde opdrachtregel op het apparaat en voer het script uit:

    1.  Ga naar **Start** en typ **cmd.**

    1.  Klik met de rechtermuisknop **op Opdrachtprompt** en selecteer **Uitvoeren als beheerder.**

        ![Venster startmenu dat verwijst naar Uitvoeren als beheerder](images/run-as-admin.png)

4.  Typ de locatie van het scriptbestand. Als u het bestand naar het bureaublad hebt gekopieerd, typt u: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

5.  Druk op **Enter** of klik op **OK.**

Zie Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen voor informatie over hoe u handmatig kunt valideren dat het apparaat compatibel is en sensorgegevens correct [rapporteert.](troubleshoot-onboarding.md)


>[!TIP]
> Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of een apparaat correct is aan boord van de service. Zie Een detectietest uitvoeren op een nieuw ingebouwde [Microsoft Defender voor eindpunten voor meer informatie.](run-detection-test.md)

## <a name="configure-sample-collection-settings"></a>Voorbeeldverzamelingsinstellingen configureren
Voor elk apparaat kunt u een configuratiewaarde instellen om aan te geven of er steekproeven kunnen worden verzameld vanaf het apparaat wanneer een aanvraag wordt gedaan via het Microsoft Defender-beveiligingscentrum om een bestand in te dienen voor uitgebreide analyse.

U kunt de instelling voor het delen van voorbeelden op het apparaat handmatig configureren met behulp van *regedit* of het maken en uitvoeren van *een REG-bestand.*  

De configuratie wordt ingesteld via de volgende registersleutelinvoer:

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Waarbij:<br>
Naamtype is een D-WORD. <br>
Mogelijke waarden zijn:
- 0 - is het delen van voorbeelden vanaf dit apparaat niet toegestaan
- 1 : hiermee kunt u alle bestandstypen vanaf dit apparaat delen

De standaardwaarde voor het geval de registersleutel niet bestaat, is 1.


## <a name="offboard-devices-using-a-local-script"></a>Offboard-apparaten met een lokaal script
Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload. Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd. Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.

> [!NOTE]
> Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.

1. Ontvang het offboarding-pakket van [het Microsoft Defender-beveiligingscentrum:](https://securitycenter.windows.com/)

    1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Offboarding**.

    1. Selecteer Windows 10 als het besturingssysteem.

    1. Selecteer **lokaal** script in het veld **Implementatiemethode.**

    1. Klik **op Pakket downloaden** en sla het ZIP-bestand op.

2. Haal de inhoud van het ZIP-bestand op naar een gedeelde, alleen-lezen locatie die toegankelijk is voor de apparaten. U moet een bestand met de *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd hebben.*

3.  Open een opdrachtregelprompt met verhoogde opdrachtregel op het apparaat en voer het script uit:

    1.  Ga naar **Start** en typ **cmd.**

    1.  Klik met de rechtermuisknop **op Opdrachtprompt** en selecteer **Uitvoeren als beheerder.**

        ![Venster startmenu dat verwijst naar Uitvoeren als beheerder](images/run-as-admin.png)

4.  Typ de locatie van het scriptbestand. Als u het bestand naar het bureaublad hebt gekopieerd, typt u: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5.  Druk op **Enter** of klik op **OK.**

> [!IMPORTANT]
> Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van het apparaat, inclusief verwijzingen naar eventuele waarschuwingen die het heeft ontvangen, blijven maximaal 6 maanden bewaard.


## <a name="monitor-device-configuration"></a>Apparaatconfiguratie controleren
U kunt de verschillende verificatiestappen volgen in de [onboarding-problemen](troubleshoot-onboarding.md) oplossen om te controleren of het script is voltooid en of de agent wordt uitgevoerd.

Controle kan ook rechtstreeks in de portal of met behulp van de verschillende implementatiehulpmiddelen worden uitgevoerd.

### <a name="monitor-devices-using-the-portal"></a>Apparaten controleren met behulp van de portal
1. Ga naar het Microsoft Defender-beveiligingscentrum.

2. Klik **op De lijst Apparaten**.

3. Controleer of apparaten worden weergegeven.


## <a name="related-topics"></a>Verwante onderwerpen
- [Onboard Windows 10-apparaten met groepsbeleid](configure-endpoints-gp.md)
- [Onboard Windows 10-apparaten met Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management](configure-endpoints-mdm.md)
- [Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten](configure-endpoints-vdi.md)
- [Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaat](run-detection-test.md)
- [Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen](troubleshoot-onboarding.md)
