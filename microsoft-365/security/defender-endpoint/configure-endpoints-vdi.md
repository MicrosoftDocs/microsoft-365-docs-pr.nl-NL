---
title: Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten
description: Implementeer het configuratiepakket op VDI-apparaat (Virtual Desktop Infrastructure), zodat ze zijn onboarded bij de Microsoft Defender for Endpoint-service.
keywords: VDI-apparaat (Virtual Desktop Infrastructure) configureren, vdi, apparaatbeheer, Windows ATP-eindpunten configureren, Microsoft Defender configureren voor eindpunten
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
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 1e970be7967e221c29017be804a98770a778654f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892791"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- VDI-apparaten (Virtual Desktop Infrastructure)
- Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten

Defender for Endpoint ondersteunt niet-permanente VDI-sessie onboarding. 


Er kunnen gekoppelde uitdagingen zijn bij het onboarden van VDIs. Hier volgen de volgende typische uitdagingen voor dit scenario:

- Direct vroeg onboarding van een sessies van korte duur, die vóór de feitelijke inrichting moeten worden onboarded bij Defender for Endpoint.
- De naam van het apparaat wordt meestal opnieuw gebruikt voor nieuwe sessies.

VDI-apparaten kunnen als een van de volgende apparaten worden weergegeven in de Portal van Defender voor Eindpunt:

- Eén invoer voor elk apparaat.

  > [!NOTE]
  > In dit geval moet *dezelfde* apparaatnaam worden geconfigureerd wanneer de sessie wordt gemaakt, bijvoorbeeld met een onbeheerd antwoordbestand.

- Meerdere items voor elk apparaat: één voor elke sessie.

De volgende stappen helpen u bij het onboarden van VDI-apparaten en markeren stappen voor enkele en meerdere items.

>[!WARNING]
> Voor omgevingen met lage resourceconfiguraties kan de VDI-opstartprocedure de onboarding van de Defender voor Eindpunt-sensor vertragen. 


### <a name="for-windows-10-or-windows-server-2019"></a>Voor Windows 10 of Windows Server 2019

1.  Open het VDI-configuratiepakket .zip-bestand *(WindowsDefenderATPOnboardingPackage.zip)* dat u hebt gedownload van de wizard Service onboarding. U kunt het pakket ook in [het Microsoft Defender-beveiligingscentrum kopen:](https://securitycenter.windows.com/)

    1.  Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding**.

    1. Selecteer Windows 10 als het besturingssysteem.

    1.  Selecteer in **het veld** Implementatiemethode **VDI-onboarding-scripts voor niet-permanente eindpunten.**

    1. Klik **op Pakket downloaden** en sla het ZIP-bestand op.

2. Kopieer de bestanden uit de map WindowsDefenderATPOnboardingPackage die is geëxtraheerd uit het ZIP-bestand naar de `golden/master` afbeelding onder het `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pad. 

    1. Als u geen enkele vermelding voor elk apparaat implementeert, kopieert u WindowsDefenderATPOnboardingScript.cmd.

    1. Als u één invoer implementeert voor elk apparaat, kopieert u zowel Onboard-NonPersistentMachine.ps1 als WindowsDefenderATPOnboardingScript.cmd.
    
    > [!NOTE]
    > Als u de map niet `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ziet, is deze mogelijk verborgen. U moet de optie  Verborgen bestanden en mappen weergeven kiezen in Verkenner.

3. Open een venster Lokaal groepsbeleidseditor en navigeer naar **Computerconfiguratie**  >  **Windows Settings** Scripts  >    >  **Opstarten**.

   > [!NOTE]
   > Domeingroepsbeleid kan ook worden gebruikt voor onboarding van niet-permanente VDI-apparaten.

4. Volg de juiste stappen, afhankelijk van de methode die u wilt implementeren:

   - Voor één invoer voor elk apparaat:
   
     Selecteer het **tabblad PowerShell-scripts** en klik vervolgens op Toevoegen **(Windows** Verkenner wordt rechtstreeks geopend in het pad waar u het onboarding-script eerder hebt gekopieerd). Navigeer naar onboarding PowerShell-script `Onboard-NonPersistentMachine.ps1` . U hoeft het andere bestand niet op te geven, omdat het automatisch wordt geactiveerd.
   
   - Voor meerdere vermeldingen voor elk apparaat:
   
     Selecteer het **tabblad Scripts** en klik vervolgens **op Toevoegen** (Windows Verkenner wordt rechtstreeks geopend in het pad waar u het onboarding-script eerder hebt gekopieerd). Ga naar het onboarding `WindowsDefenderATPOnboardingScript.cmd` bash-script.

5. Test uw oplossing:

   1. Maak een groep met één apparaat.
      
   1. Aanmelding bij apparaat.
      
   1. Logoff van apparaat.

   1. Aanmelding bij apparaat met een andere gebruiker.
      
   1. Volg de juiste stappen, afhankelijk van de methode die u wilt implementeren:
   
      - Voor één invoer voor elk apparaat: 
    
        Controleer slechts één item in het Microsoft Defender-beveiligingscentrum.

      - Voor meerdere vermeldingen voor elk apparaat: 
       
        Controleer meerdere items in het Microsoft Defender-beveiligingscentrum.

6. Klik **op De lijst Apparaten** in het navigatiedeelvenster.

7. Gebruik de zoekfunctie door de naam van het apparaat in te geven en **Apparaat te selecteren** als zoektype.


## <a name="for-downlevel-skus"></a>Voor downlevel-SKU's

> [!NOTE]
> Het volgende register is alleen relevant als het doel is om een 'Enkelvoudige vermelding voor elk apparaat' te bereiken.

1. Registerwaarde instellen op:

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    of met opdrachtregel:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. Volg het [onboardingproces van de server.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016) 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Niet-permanente VDI-afbeeldingen (Virtual Desktop Infrastructure) bijwerken
Het is raadzaam om offline servicehulpmiddelen te gebruiken om gouden/hoofdafbeeldingen te patchen.<br>
U kunt bijvoorbeeld de onderstaande opdrachten gebruiken om een update te installeren terwijl de afbeelding offline blijft:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Zie de artikelen hieronder voor meer informatie over DISM-opdrachten en offlineonderhoud:
- [Een Windows-afbeelding wijzigen met DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM Image Management Command-Line Opties](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [De grootte van de onderdelenwinkel in een offline-Windows-afbeelding verkleinen](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Als offline service geen haalbare optie is voor uw niet-permanente VDI-omgeving, moeten de volgende stappen worden genomen om consistentie en sensortoestand te waarborgen:

1. Nadat u de hoofdafbeelding voor online onderhoud of patching heeft opgestart, kunt u een offboarding-script uitvoeren om de Defender voor Eindpunt-sensor uit te schakelen. Zie Offboard-apparaten met [een lokaal script voor meer informatie.](configure-endpoints-script.md#offboard-devices-using-a-local-script)

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

## <a name="related-topics"></a>Verwante onderwerpen
- [Onboard Windows 10-apparaten met groepsbeleid](configure-endpoints-gp.md)
- [Onboard Windows 10-apparaten met Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management](configure-endpoints-mdm.md)
- [Onboarden Windows 10-apparaten met een lokaal script](configure-endpoints-script.md)
- [Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen](troubleshoot-onboarding.md)
