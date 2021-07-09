---
title: Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management
description: Gebruik hulpprogramma's voor mobiel apparaatbeheer om het configuratiepakket op apparaten te implementeren, zodat de apparaten zijn aan boord van de service.
keywords: onboard devices using mdm, device management, onboard Microsoft Defender for Endpoint devices, mdm
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
ms.openlocfilehash: f0a0a35d41d56abfcc7975c9e79ff7d537b72f40
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338575"
---
# <a name="onboard-the-windows-10-devices-using-mobile-device-management-tools"></a>Onboard the Windows 10 devices using Mobile Device Management tools

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

U kunt MDM-oplossingen (Mobile Device Management) gebruiken om apparaten te configureren. Defender voor Eindpunt ondersteunt MDM's door OMA-URIs om beleid te maken voor het beheren van apparaten.

Zie [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection CSP and WindowsAdvancedThreatProtection DDF file (WindowsAdvancedThreatProtection DDF-bestand)](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)voor meer informatie over het gebruik van Defender voor Endpoint CSP.

## <a name="before-you-begin"></a>Voordat u begint
Als u een Microsoft Intune gebruikt, moet u het apparaat MDM-inschrijving hebben. Anders worden de instellingen niet toegepast. 

Zie [Apparaatinschrijving (Microsoft Intune)](/mem/intune/enrollment/device-enrollment)voor meer informatie over het inschakelen van MDM met Microsoft Intune.

## <a name="onboard-devices-using-microsoft-intune"></a>Onboard-apparaten met Microsoft Intune

[![Afbeelding van het PDF-bestand met onboarding-apparaten voor Defender voor Eindpunt met Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)

Bekijk het [PDF-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) of [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) om de verschillende paden te bekijken bij de implementatie van Defender voor Eindpunt. 

Volg de instructies van [Intune](/intune/advanced-threat-protection).

Zie [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection CSP and WindowsAdvancedThreatProtection DDF file (WindowsAdvancedThreatProtection DDF-bestand)](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)voor meer informatie over het gebruik van Defender voor Endpoint CSP.


> [!NOTE]
> - Het **beleid Statusstatus voor onboarded-apparaten** gebruikt alleen-lezen eigenschappen en kan niet worden gesaneerd.
> - Configuratie van de rapportagefrequentie voor diagnostische gegevens is alleen beschikbaar voor apparaten Windows 10, versie 1703.


>[!TIP]
> Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of een apparaat correct is aan boord van de service. Zie Een detectietest uitvoeren op een nieuw ingebouwde [Microsoft Defender voor eindpuntapparaat](run-detection-test.md)voor meer informatie.


Bekijk het [PDF-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) of [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) om de verschillende paden te bekijken bij de implementatie van Microsoft Defender voor Eindpunt.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Apparaten offboarden en bewaken met behulp van hulpprogramma's voor mobiel apparaatbeheer
Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload. Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd. Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.

> [!NOTE]
> Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.

1. Haal het offboarding-pakket van [Microsoft 365 Defender portal:](https://security.microsoft.com/)

   1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Endpoints**  >  **Device management**  >  **Offboarding**.

   1. Selecteer Windows 10 als het besturingssysteem.

   1. Selecteer in **het veld** Implementatiemethode de optie Mobile Device **Management /Microsoft Intune.**
    
   1. Klik **op Pakket downloaden** en sla het .zip op.

2. Haal de inhoud van het .zip bestand op naar een gedeelde, alleen-lezen locatie die kan worden gebruikt door de netwerkbeheerders die het pakket zullen implementeren. U moet een bestand met de *naam WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding hebben.*

3. Gebruik het Microsoft Intune aangepast configuratiebeleid om de volgende ondersteunde OMA-URI-instellingen te implementeren.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding<br/>
      Datumtype: tekenreeks<br/>
      Waarde: [De waarde kopiëren en plakken uit de inhoud van het WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding-bestand]

Zie voor meer informatie over Microsoft Intune beleidsinstellingen [Windows 10 beleidsinstellingen in Microsoft Intune.](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)


> [!NOTE]
> In **het beleid Statusstatus voor niet-geboarde apparaten** worden alleen-lezen eigenschappen gebruikt en deze kunnen niet worden gesaneerd.

> [!IMPORTANT]
> Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van het apparaat, inclusief verwijzingen naar eventuele waarschuwingen die het heeft ontvangen, blijven maximaal 6 maanden bewaard.

## <a name="related-topics"></a>Gerelateerde onderwerpen
- [Onboard Windows 10 apparaten met groepsbeleid](configure-endpoints-gp.md)
- [Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarden Windows 10-apparaten met een lokaal script](configure-endpoints-script.md)
- [Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten](configure-endpoints-vdi.md)
- [Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaat](run-detection-test.md)
- [Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen](troubleshoot-onboarding.md)
