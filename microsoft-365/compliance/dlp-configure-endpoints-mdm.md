---
title: Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Gebruik hulpprogramma's voor mobiel apparaatbeheer om het configuratiepakket op apparaten te implementeren, zodat ze zijn aan boord van de service.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161911"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management

**Van toepassing op:**

- [Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)](./endpoint-dlp-learn-about.md)

U kunt MDM-oplossingen (Mobile Device Management) gebruiken om apparaten te configureren. Microsoft 365 Preventie van gegevensverlies in eindpunten ondersteunt MDM's door OMA-URIs om beleid te maken voor het beheren van apparaten.


## <a name="before-you-begin"></a>Voordat u begint
Als u een Microsoft Intune gebruikt, moet u het apparaat MDM-inschrijving hebben. Anders worden de instellingen niet toegepast. 

Zie [Apparaatinschrijving (Microsoft Intune)](/mem/intune/enrollment/device-enrollment)voor meer informatie over het inschakelen van MDM met Microsoft Intune.

## <a name="onboard-devices-using-microsoft-intune"></a>Onboard-apparaten met Microsoft Intune

Volg de instructies van [Intune](/intune/advanced-threat-protection).

> [!NOTE]
> - Het **beleid Statusstatus voor onboarded-apparaten** gebruikt alleen-lezen eigenschappen en kan niet worden gesaneerd.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Apparaten offboarden en bewaken met behulp van hulpprogramma's voor mobiel apparaatbeheer

Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload. Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd. Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.

> [!NOTE]
> Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.

1. Haal het offboarding-pakket op in [het Microsoft Compliance Center.](https://compliance.microsoft.com/)

2. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding**  >  **offboarding** voor apparaten.

3. Selecteer in **het veld** Implementatiemethode de optie Mobile Device **Management /Microsoft Intune.**
    
4. Klik **op Pakket downloaden** en sla het .zip op.

5. Haal de inhoud van het .zip bestand op naar een gedeelde, alleen-lezen locatie die kan worden gebruikt door de netwerkbeheerders die het pakket zullen implementeren. U moet een bestand met de naam *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding hebben.*

6. Gebruik het Microsoft Intune aangepast configuratiebeleid om de volgende ondersteunde OMA-URI-instellingen te implementeren.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Datumtype: tekenreeks      
      Waarde: [De waarde kopiëren en plakken uit de inhoud van het DeviceCompliance_valid_until_YYYY-MM-DD.offboarding-bestand]

Zie voor meer informatie over Microsoft Intune beleidsinstellingen [Windows 10 beleidsinstellingen in Microsoft Intune.](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> In **het beleid Statusstatus voor niet-geboarde apparaten** worden alleen-lezen eigenschappen gebruikt en deze kunnen niet worden gesaneerd.

> [!IMPORTANT]
> Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van het apparaat, inclusief verwijzingen naar eventuele waarschuwingen die het heeft ontvangen, blijven maximaal 6 maanden bewaard.

## <a name="related-topics"></a>Verwante onderwerpen
- [Onboard Windows 10 apparaten met groepsbeleid](dlp-configure-endpoints-gp.md)
- [Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarden Windows 10-apparaten met een lokaal script](dlp-configure-endpoints-script.md)
- [Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten](dlp-configure-endpoints-vdi.md)
- [Problemen met Microsoft Defender Advanced Threat Protection onboarding oplossen](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)