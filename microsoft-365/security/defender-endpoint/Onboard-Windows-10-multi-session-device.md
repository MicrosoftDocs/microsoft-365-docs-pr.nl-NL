---
title: Onboard Windows 10 multi-session devices in Windows Virtual Desktop
description: Lees meer in dit artikel over Onboarding Windows 10 multi-session devices in Windows Virtual Desktop
keywords: Windows Virtual Desktop, WVD, microsoft defender, eindpunt, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.date: 09/10/2020
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: bfd447120e171fed063b3224e3a47c2ef38f0f16
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222609"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a>Onboard Windows 10 multi-session devices in Windows Virtual Desktop 
6 minuten om te lezen 

Van toepassing op: 
- Windows 10 multi-session running on Windows Virtual Desktop (WVD) 

> [!WARNING]
> Microsoft Defender voor endpoint-ondersteuning voor scenario's met meerdere sessies voor Windows Virtual Desktop is momenteel beschikbaar in Preview en beperkt tot 25 gelijktijdige sessies per host/VM. Scenario's voor één sessie op Windows Virtual Desktop worden echter volledig ondersteund.

Microsoft Defender voor Eindpunt ondersteunt het controleren van zowel VDI- als Windows Virtual Desktop-sessies. Afhankelijk van de behoeften van uw organisatie, moet u mogelijk VDI- of Windows Virtual Desktop-sessies implementeren om uw werknemers toegang te geven tot bedrijfsgegevens en apps vanaf een niet-beheerd apparaat, externe locatie of vergelijkbaar scenario. Met Microsoft Defender voor Eindpunt kunt u deze virtuele machines controleren op afwijkende activiteiten.

 ## <a name="before-you-begin"></a>Voordat u begint
Vertrouwd raken met de [overwegingen voor niet-permanente VDI.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1) Hoewel [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) geen niet-persistente opties biedt, biedt het wel manieren om een gouden Windows-afbeelding te gebruiken die kan worden gebruikt voor het inrichten van nieuwe hosts en herdeploy-machines. Dit verhoogt de vluchtigheid in de omgeving en is dus van invloed op de items die worden gemaakt en onderhouden in de Microsoft Defender for Endpoint-portal, waardoor de zichtbaarheid voor uw beveiligingsanalisten mogelijk wordt verkleind.

> [!NOTE]
> Afhankelijk van de keuze van de onboarding-methode, kunnen apparaten als een van beide worden weergegeven in de Microsoft Defender voor Endpoint-portal: 
> - Eén invoer voor elk virtueel bureaublad 
> - Meerdere items voor elk virtueel bureaublad 

Microsoft raadt onboarding van Windows Virtual Desktop aan als één item per virtueel bureaublad. Dit zorgt ervoor dat de onderzoekservaring in de Microsoft Defender Endpoint-portal binnen de context van één apparaat valt op basis van de computernaam. Organisaties die vaak WVD-hosts verwijderen en opnieuw deployeren, moeten deze methode sterk overwegen omdat hiermee wordt voorkomen dat meerdere objecten voor dezelfde computer worden gemaakt in de Microsoft Defender voor Eindpunt-portal. Dit kan leiden tot verwarring bij het onderzoeken van incidenten. Voor test- of niet-vluchtige omgevingen kunt u ervoor kiezen om anders te kiezen. 

Microsoft raadt aan het onboardingscript van Microsoft Defender voor eindpunt toe te voegen aan de gouden afbeelding van WVD. Op deze manier kunt u er zeker van zijn dat dit onboarding-script direct bij het opstarten wordt uitgevoerd. Het wordt uitgevoerd als een opstartscript bij het opstarten op alle WVD-machines die zijn ingericht vanuit de gouden afbeelding van WVD. Als u echter een van de galerieafbeeldingen zonder wijziging gebruikt, zet u het script op een gedeelde locatie en belt u het vanuit lokaal of domeingroepsbeleid. 

> [!NOTE]
> De plaatsing en configuratie van het VDI onboarding-opstartscript op de gouden afbeelding van WVD configureert het script als een opstartscript dat wordt uitgevoerd wanneer de WVD wordt gestart. Het is NIET raadzaam om de werkelijke gouden afbeelding van WVD aan te boord te nemen. Een andere overweging is de methode die wordt gebruikt om het script uit te voeren. Het moet zo vroeg mogelijk in het opstart-/inrichtingsproces worden uitgevoerd om de tijd tussen de machine die beschikbaar is voor het ontvangen van sessies en de onboarding van het apparaat bij de service te verminderen. In onderstaande scenario'& 2 wordt hiermee rekening gehouden.

### <a name="scenarios"></a>Scenario's
Er zijn verschillende manieren om een WVD-hostcomputer aan te boord te nemen:

- Voer het script uit in de gouden afbeelding (of vanaf een gedeelde locatie) tijdens het opstarten.
- Gebruik een beheerhulpmiddel om het script uit te voeren.

#### <a name="scenario-1-using-local-group-policy"></a>*Scenario 1: Lokaal groepsbeleid gebruiken*
In dit scenario moet het script in een gouden afbeelding worden geplaatst en wordt lokaal groepsbeleid gebruikt om het begin van het opstartproces uit te voeren.

Gebruik de instructies in [VDI-apparaten met niet-permanente virtuele bureaubladinfrastructuur](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)aan boord.

Volg de instructies voor één vermelding voor elk apparaat.

#### <a name="scenario-2-using-domain-group-policy"></a>*Scenario 2: Domeingroepsbeleid gebruiken*
In dit scenario wordt een centraal gelegen script gebruikt en wordt het uitgevoerd met een groepsbeleid op basis van een domein. U kunt het script ook in de gouden afbeelding plaatsen en op dezelfde manier uitvoeren.

**Het WindowsDefenderATPOnboardingPackage.zip downloaden van het Windows Defender-beveiligingscentrum**
1. Open het VDI-configuratiepakket .zip-bestand (WindowsDefenderATPOnboardingPackage.zip)  
    - Selecteer in het navigatiedeelvenster van het Microsoft Defender-beveiligingscentrum **de** optie  >  **Instellingen Onboarding**. 
    - Selecteer Windows 10 als het besturingssysteem. 
    - Selecteer in **het veld** Implementatiemethode VDI-onboarding-scripts voor niet-permanente eindpunten. 
    - Klik **op Pakket downloaden** en sla het ZIP-bestand op. 
2. Haal de inhoud van het ZIP-bestand op naar een gedeelde, alleen-lezen locatie die toegankelijk is voor het apparaat. U hebt een map met de naam **OptionalParamsPolicy** en de bestanden **WindowsDefenderATPOnboardingScript.cmd** en **Onboard-NonPersistentMachine.ps1.**

**Groepsbeleidsbeheerconsole gebruiken om het script uit te voeren wanneer de virtuele machine wordt gestart**
1. Open de GPMC (Group Policy Management Console), klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**
1. Ga in de Editor voor groepsbeleidsbeheer naar Instellingen van het **Configuratiescherm voor** \>  \> **computerconfiguratie**. 
1. Klik met de **rechtermuisknop op Geplande taken,** klik **op Nieuw** en klik vervolgens op **Onmiddellijke taak** (ten minste Windows 7). 
1. Ga in het venster Taak dat wordt geopend naar het **tabblad** Algemeen. Klik **onder Beveiligingsopties** **op Gebruiker of Groep wijzigen en** typ SYSTEEM. Klik **op Namen controleren** en klik vervolgens op OK. NT AUTHORITY\SYSTEM wordt weergegeven als het gebruikersaccount dat de taak als wordt uitgevoerd. 
1. Schakel **Uitvoeren in of de gebruiker al** dan niet is aangemeld en schakel het selectievakje Uitvoeren met hoogste **bevoegdheden** in. 
1. Ga naar het **tabblad Acties** en klik op **Nieuw.** Zorg ervoor **dat Een programma starten** is geselecteerd in het veld Actie. Voer het volgende in: 

> Actie = 'Een programma starten' <br>
> Programma/script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe <br>
> Argumenten toevoegen (optioneel) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"

Klik **op OK** en sluit alle geopende GPMC-vensters.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*Scenario 3: Onboarding met behulp van beheerhulpmiddelen*

Als u van plan bent om uw machines te beheren met behulp van een beheerhulpmiddel, kunt u apparaten onboarden met Microsoft Endpoint Configuration Manager.

Zie Voor meer informatie: [Windows 10-apparaten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) aan boord met Configuration Manager 

> [!WARNING]
> Als u van plan bent Om De Surface-beperkingsregels voor aanvallen te [gebruiken,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)moet u er rekening mee houden dat regel ' Procescreaties blokkeren die afkomstig zijn van[PSExec-](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)en WMI-opdrachten' niet mag worden gebruikt omdat deze niet compatibel is met beheer via Microsoft Endpoint Configuration Manager, omdat deze regel WMI-opdrachten blokkeert die de Configuration Manager-client gebruikt om correct te werken. 

> [!TIP]
> Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of het apparaat correct is aan boord van de service. Zie Een detectietest uitvoeren op een nieuw ingebouwde [Microsoft Defender voor eindpuntapparaat](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)voor meer informatie. 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>Uw machines labelen bij het maken van uw gouden afbeelding 

Als onderdeel van uw onboarding kunt u overwegen om een machinelabel in te stellen om WVD-machines gemakkelijker van elkaar te onderscheiden in het Microsoft-beveiligingscentrum. Zie Apparaatlabels toevoegen door een registersleutelwaarde in te stellen voor [meer informatie.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value) 

#### <a name="other-recommended-configuration-settings"></a>Andere aanbevolen configuratie-instellingen 

Wanneer u een gouden afbeelding opbouwt, wilt u mogelijk ook de eerste beveiligingsinstellingen configureren. Zie Overige aanbevolen [configuratie-instellingen voor meer informatie.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings) 

Als u FSlogix-gebruikersprofielen gebruikt, raden we u aan de volgende bestanden uit te sluiten van de always-on-beveiliging: 

**Bestanden uitsluiten:** 

> %ProgramFiles%\FSLogix\Apps\frxdrv.sys <br>
> %ProgramFiles%\FSLogix\Apps\frxdrvvt.sys <br>
> %ProgramFiles%\FSLogix\Apps\frxccd.sys <br>
> %TEMP% \* . VHD <br>
> %TEMP% \* . VHDX <br>
> %Windir%\TEMP \* . VHD <br>
> %Windir%\TEMP \* . VHDX <br>
> \\storageaccount.file.core.windows.net\share \* \* . VHD <br>
> \\storageaccount.file.core.windows.net\share \* \* . VHDX <br>

**Processen uitsluiten:**

> %ProgramFiles%\FSLogix\Apps\frxccd.exe <br>
> %ProgramFiles%\FSLogix\Apps\frxccds.exe <br>
> %ProgramFiles%\FSLogix\Apps\frxsvc.exe <br>

#### <a name="licensing-requirements"></a>Licentievereisten 

Windows 10 Multi-session is een client-besturingssysteem. Licentievereisten voor Microsoft Defender voor eindpunten vindt u op: [Licentievereisten.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)
