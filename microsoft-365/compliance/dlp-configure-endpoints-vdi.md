---
title: Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten
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
description: Implementeer het configuratiepakket op VDI-apparaat (Virtual Desktop Infrastructure) zodat ze zijn onboarded bij de Microsoft 365 Endpoint Data Loss Prevention Service.
ms.openlocfilehash: 64d9bfed3d1d5600b5843c697e894577f83527fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226873"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten

**Van toepassing op:**
- [Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)](./endpoint-dlp-learn-about.md)

- VDI-apparaten (Virtual Desktop Infrastructure)

> [!WARNING]
> Microsoft 365 Ondersteuning voor preventie van eindpunten voor gegevensverlies Windows virtuele bureaublad ondersteunt scenario's voor één sessie. Scenario's met meerdere sessies op Windows virtuele bureaublad worden momenteel niet ondersteund.

## <a name="onboard-vdi-devices"></a>Onboard VDI-apparaten

Microsoft 365 Preventie van verlies van eindpunten ondersteunt niet-permanente VDI-sessie onboarding.

> [!NOTE]
> Als u niet-permanente VDI-sessies wilt onboarden, moeten VDI-apparaten zijn Windows 10 1809 of hoger.

Er kunnen gekoppelde uitdagingen zijn bij het onboarden van VDIs. Hier volgen de volgende typische uitdagingen voor dit scenario:

- Direct vroeg onboarding van een sessies van korte duur, die moeten worden onboarded om Microsoft 365 endpoint-preventie van gegevensverlies te voorkomen vóór de feitelijke inrichting.
- De naam van het apparaat wordt meestal opnieuw gebruikt voor nieuwe sessies.

VDI-apparaten kunnen als Microsoft 365 worden weergegeven in het compliancecentrum:

- Eén invoer voor elk apparaat.
Houd er rekening mee dat in dit geval dezelfde *apparaatnaam* moet worden geconfigureerd wanneer de sessie wordt gemaakt, bijvoorbeeld met een onbeheerd antwoordbestand.
- Meerdere items voor elk apparaat: één voor elke sessie.

De volgende stappen helpen u bij het onboarden van VDI-apparaten en markeren stappen voor enkele en meerdere items.

> [!WARNING]
> Voor omgevingen met lage resourceconfiguraties kan de VDI-opstartprocedure de onboarding van Microsoft 365 endpoint-gegevensverlies vertragen.

1. Open het VDI-configuratiepakket .zip bestand *(DeviceCompliancePackage.zip)* dat u hebt gedownload van de wizard Service onboarding.

2. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding van**  >  **apparaat.**

3. Selecteer in **het veld** Implementatiemethode **VDI-onboarding-scripts voor niet-permanente eindpunten.**

4. Klik **op Pakket downloaden** en sla het .zip op.

5. Kopieer de bestanden uit de map DeviceCompliancePackage die is geëxtraheerd uit het .zip naar de `golden/master` afbeelding onder het `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pad.

6. Als u geen enkele vermelding voor elk apparaat implementeert, kopieert u DeviceComplianceOnboardingScript.cmd.

7. Als u één invoer implementeert voor elk apparaat, kopieert u zowel Onboard-NonPersistentMachine.ps1 als DeviceComplianceOnboardingScript.cmd.

    > [!NOTE]
    > Als u de map niet `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ziet, is deze mogelijk verborgen. U moet de optie  Verborgen bestanden en mappen weergeven kiezen in Verkenner.

8. Open een venster Van lokale groepsbeleidseditor en navigeer naar **Computerconfiguratie**  >  **Windows Instellingen**  >  **scripts**  >  **opstarten.**

   > [!NOTE]
   > Domeingroepsbeleid kan ook worden gebruikt voor onboarding van niet-permanente VDI-apparaten.

9. Volg de juiste stappen, afhankelijk van de methode die u wilt implementeren:

   **Voor één invoer voor elk apparaat**

   Selecteer het **tabblad PowerShell-scripts** en klik vervolgens op Toevoegen **(Windows** Explorer wordt rechtstreeks geopend in het pad waar u het onboarding-script eerder hebt gekopieerd). Navigeer naar onboarding PowerShell-script `Onboard-NonPersistentMachine.ps1` .

   **Voor meerdere vermeldingen voor elk apparaat:**

   Selecteer het **tabblad Scripts** en klik vervolgens op **Toevoegen** (Windows Explorer wordt rechtstreeks geopend in het pad waar u het onboarding-script eerder hebt gekopieerd). Ga naar het onboarding `DeviceComplianceOnboardingScript.cmd` bash-script.

10. Test uw oplossing:
    1. Maak een groep met één apparaat.
    1. Aanmelding bij apparaat.
    1. Logoff van apparaat.
    1. Aanmelding bij apparaat met een andere gebruiker.
    1. **Voor één invoer voor elk apparaat:** Controleer slechts één item in Microsoft Defender-beveiligingscentrum.
       **Voor meerdere items voor elk apparaat:** Controleer meerdere vermeldingen in Microsoft Defender-beveiligingscentrum.

11. Klik **op De lijst Apparaten** in het navigatiedeelvenster.

12. Gebruik de zoekfunctie door de naam van het apparaat in te geven en **Apparaat te selecteren** als zoektype.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Niet-permanente VDI-afbeeldingen (Virtual Desktop Infrastructure) bijwerken

Het is raadzaam om offline servicehulpmiddelen te gebruiken om gouden/hoofdafbeeldingen te patchen.

U kunt bijvoorbeeld de onderstaande opdrachten gebruiken om een update te installeren terwijl de afbeelding offline blijft:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Zie de artikelen hieronder voor meer informatie over DISM-opdrachten en offlineonderhoud:

- [Een afbeelding Windows DISM wijzigen](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM Image Management Command-Line Opties](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [De grootte van het onderdelenbestand in een offline-Windows verkleinen](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Als offline service geen haalbare optie is voor uw niet-permanente VDI-omgeving, moeten de volgende stappen worden genomen om consistentie en sensortoestand te waarborgen:

1. Nadat u de hoofdafbeelding voor online onderhoud of patching heeft opgestart, kunt u een offboarding-script uitvoeren om de Microsoft 365 endpoint-sensor voor preventie van gegevensverlies uit te schakelen. Zie Offboard-apparaten met [een lokaal script voor meer informatie.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)

2. Zorg ervoor dat de sensor wordt gestopt door de onderstaande opdracht uit te voeren in een CMD-venster:

   ```console
   sc query sense
   ```

3. Service de afbeelding zo nodig.

4. Voer de onderstaande opdrachten uit PsExec.exe (waaruit kan worden gedownload om de inhoud van de cybermap op te schonen die de sensor mogelijk heeft verzameld sinds het https://download.sysinternals.com/files/PSTools.zip) opstarten:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Verzegel de afbeelding van het gouden/hoofdmodel opnieuw zoals u dat normaal zou doen.

## <a name="related-topics"></a>Gerelateerde onderwerpen

- [Onboard Windows 10 apparaten met groepsbeleid](dlp-configure-endpoints-gp.md)
- [Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management](dlp-configure-endpoints-mdm.md)
- [Onboarden Windows 10-apparaten met een lokaal script](dlp-configure-endpoints-script.md)
- [Problemen met de onboarding van Microsoft Defender Advanced Threat Protection oplossen](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
