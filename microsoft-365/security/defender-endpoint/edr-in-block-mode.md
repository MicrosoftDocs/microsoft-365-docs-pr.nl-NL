---
title: Eindpuntdetectie en -reactie in de blokmodus
description: Meer informatie over eindpuntdetectie en -respons in de blokmodus
keywords: Microsoft Defender voor Eindpunt, mde, EDR in blokmodus, passieve modus blokkeren
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 07/13/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 1915a57becb1cba14605f4512ff123c1bca846bb
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415597"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Endpoint detection and response (EDR) in block mode

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Wat is EDR in de blokmodus?

[Eindpuntdetectie en -antwoord](overview-endpoint-detection-response.md) (EDR) in de blokmodus biedt extra bescherming tegen schadelijke artefacten wanneer Microsoft Defender Antivirus niet het primaire antivirusproduct is en in de passieve modus wordt uitgevoerd. EDR in de blokmodus herstelt schadelijke artefacten die worden gedetecteerd met behulp van EDR. Dergelijke artefacten zijn mogelijk gemist door het primaire, niet-Microsoft-antivirusproduct. EDR in de blokmodus werkt achter de schermen om schadelijke artefacten te corrigeren die worden gedetecteerd, na een inbreuk op een apparaat. 

> [!IMPORTANT]
> EDR in de blokmodus biedt niet alle beveiliging die beschikbaar is wanneer Microsoft Defender Antivirus realtimebeveiliging is ingeschakeld. Alle functies die afhankelijk zijn van Microsoft Defender Antivirus de actieve antivirusoplossing, werken niet, inclusief de volgende belangrijke voorbeelden: 
> 
> - Realtime beveiliging, inclusief scannen via toegang, is niet beschikbaar wanneer Microsoft Defender Antivirus in de passieve modus is. Zie Beveiliging in realtime inschakelen en configureren Microsoft Defender Antivirus voor meer informatie over realtime **[beveiligingsbeleidsinstellingen.](configure-real-time-protection-microsoft-defender-antivirus.md)**
> - Functies zoals **[netwerkbeveiliging en](network-protection.md)** **[attack surface reduction rules](attack-surface-reduction.md)** zijn alleen beschikbaar wanneer Microsoft Defender Antivirus wordt uitgevoerd in de actieve modus. 
> 
> De verwachting is dat uw niet-Microsoft-antivirusoplossing deze mogelijkheden biedt. 

EDR in de blokmodus is geïntegreerd met [bedreigingen & vulnerability management.](next-gen-threat-and-vuln-mgt.md) Het beveiligingsteam van uw [](tvm-security-recommendation.md) organisatie krijgt een beveiligingsaanbeveling om de EDR in de blokmodus in te schakelen als dit nog niet is ingeschakeld. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="aanbeveling om de EDR in te schakelen in de blokmodus":::

> [!TIP]
> Als u de beste beveiliging wilt, moet u Microsoft Defender voor eindpunten **[implementeren.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>Wat gebeurt er wanneer er iets wordt gedetecteerd?

Wanneer EDR in de blokmodus is ingeschakeld en er een schadelijk artefact wordt gedetecteerd, blokkeert en herstelt Microsoft Defender voor eindpunten dat artefact. Uw beveiligingsbewerkingsteam ziet de detectiestatus **als** Geblokkeerd of Voorkomen **in** het [Actiecentrum,](respond-machine-alerts.md#check-activity-details-in-action-center)weergegeven als voltooide acties.

In de volgende afbeelding ziet u een exemplaar van ongewenste software die is gedetecteerd en geblokkeerd via EDR in de blokmodus:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR in de blokmodus iets gedetecteerd":::


## <a name="enable-edr-in-block-mode"></a>De EDR in de blokmodus inschakelen

> [!TIP]
> Zorg ervoor dat [aan de vereisten](#requirements-for-edr-in-block-mode) wordt voldaan voordat u EDR in de blokmodus.

1. Ga naar de Microsoft 365 Defender portal [https://security.microsoft.com/](https://security.microsoft.com/) () en meld u aan. 

2. Kies **Instellingen**  >  **endpoints**  >  **General**  >  **Advanced-functies**.

3. Schuif omlaag en vervolgens urn op **Inschakelen EDR in de blokmodus.**

> [!NOTE]
> EDR in de blokmodus kan alleen worden ingeschakeld in de Microsoft 365 Defender portal ( ) of de voormalige [https://security.microsoft.com](https://security.microsoft.com) Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). U kunt registersleutels, Microsoft Intune groepsbeleid niet gebruiken om de EDR in- of uit te schakelen in de blokmodus.

## <a name="requirements-for-edr-in-block-mode"></a>Vereisten voor EDR in blokmodus

| Vereiste  | Details  |
|---------|---------|
| Machtigingen | U moet de rol globale beheerder of beveiligingsbeheerder hebben toegewezen in [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) Zie [Basismachtigingen voor meer informatie.](basic-permissions.md) |
| Besturingssysteem     | Apparaten moeten een van de volgende versies van Windows: <br/>- Windows 10 (alle releases) <br/>- Windows Server, versie 1803 of hoger <br/>- Windows Server 2019 <br/>- Windows Server 2016 (alleen als Microsoft Defender Antivirus actief is)     |
| Microsoft Defender voor Eindpunt     | Apparaten moeten zijn onboarded bij Defender voor Eindpunt. Zie [Minimumvereisten voor Microsoft Defender voor Eindpunt](minimum-requirements.md).       |
| Microsoft Defender Antivirus  | Apparaten moeten zijn Microsoft Defender Antivirus geïnstalleerd en uitgevoerd in de actieve of passieve modus. [Bevestig Microsoft Defender Antivirus actief of passief is.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
| Cloudbeveiliging | Microsoft Defender Antivirus moet zodanig zijn geconfigureerd dat beveiliging in de [cloud is ingeschakeld.](enable-cloud-protection-microsoft-defender-antivirus.md) |
| Microsoft Defender Antivirus platform | Apparaten moeten up-to-date zijn. Als u wilt bevestigen dat u met PowerShell de [cmdlet Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) als beheerder wilt uitvoeren. In de **REGEL AMProductVersion** ziet u **4.18.2001.10** of hoger. <p> Raadpleeg voor meer informatie [Updates voor Microsoft Defender Antivirus beheren en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md). |
| Microsoft Defender Antivirus engine | Apparaten moeten up-to-date zijn. Als u wilt bevestigen dat u met PowerShell de [cmdlet Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) als beheerder wilt uitvoeren. In de **REGEL AMEngineVersion** ziet u **1.1.16700.2** of hoger. <p> Raadpleeg voor meer informatie [Updates voor Microsoft Defender Antivirus beheren en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md). |

> [!IMPORTANT]
> Als u de beste [beschermingswaarde](configure-exclusions-microsoft-defender-antivirus.md)wilt krijgen, moet u ervoor zorgen dat uw antivirusoplossing is geconfigureerd voor regelmatige updates en essentiële functies en dat uw uitsluitingen zijn geconfigureerd. EDR in de blokmodus respecteert uitsluitingen die zijn gedefinieerd voor [](manage-indicators.md) Microsoft Defender Antivirus, maar niet indicatoren die zijn gedefinieerd voor Microsoft Defender voor Eindpunt.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>Moet ik de EDR in de blokmodus inschakelen als ik Microsoft Defender Antivirus op apparaten?

Het primaire doel van EDR in de blokmodus is het corrigeren van detecties na inbreuk die zijn gemist door een niet-Microsoft-antivirusproduct. Het is echter raadzaam de EDR in de blokmodus ingeschakeld te houden, ongeacht of Microsoft Defender Antivirus actief is in de passieve modus of in de actieve modus. 

- Wanneer Microsoft Defender Antivirus in de passieve modus staat, EDR in de blokmodus een andere verdedigingslaag samen met Microsoft Defender voor Eindpunt. 
- Wanneer Microsoft Defender Antivirus in de actieve modus staat, biedt EDR in de blokmodus geen extra scan, maar kan Defender for Endpoint wel automatische acties uitvoeren bij detecties na inbreuk, gedrag EDR detecties.

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>Is EDR in de blokmodus van invloed op de antivirusbeveiliging van een gebruiker? 

EDR in de blokmodus heeft geen invloed op antivirusbeveiliging van derden die wordt uitgevoerd op apparaten van gebruikers. EDR in de blokmodus werkt als de primaire antivirusoplossing iets mist of als er een detectie na inbreuk is. EDR in de blokmodus werkt net als Microsoft Defender Antivirus in passieve modus, behalve dat EDR in de blokmodus ook schadelijke artefacten of gedragingen blokkeert en herstelt die worden gedetecteerd.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Waarom moet ik mijn Microsoft Defender Antivirus up-to-date houden? 

Omdat Microsoft Defender Antivirus schadelijke items detecteert en herstelt, is het belangrijk om deze up-to-date te houden. Om EDR in de blokmodus effectief te maken, worden de nieuwste leermodellen, gedragsdetecties en heuristische toepassingen gebruikt. De [stapel mogelijkheden van Defender](microsoft-defender-endpoint.md) voor eindpunten werkt op een geïntegreerde manier. Als u de beste beschermingswaarde wilt, moet u Microsoft Defender Antivirus up-to-date houden. Zie [Het Microsoft Defender Antivirus updates beheren en basislijnen toepassen.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-maps-on"></a>Waarom hebben we cloudbeveiliging (MAPS) nodig? 

Cloudbeveiliging is nodig om de functie op het apparaat in te zetten. Met cloudbeveiliging kan [Defender for Endpoint](microsoft-defender-endpoint.md) de nieuwste en beste beveiliging bieden op basis van onze uitgebreide en uitgebreide beveiligingsinformatie, samen met modellen voor het leren van gedrag en apparaten.

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>Wat is het verschil tussen actieve en passieve modus?

Voor eindpunten met Windows 10, Windows Server, versie 1803 of hoger of Windows Server 2019 wordt Microsoft Defender Antivirus in de actieve modus gebruikt als primaire antivirusprogramma op het apparaat. Wanneer u in de passieve modus werkt, Microsoft Defender Antivirus niet het primaire antivirusproduct. In dit geval worden bedreigingen niet in realtime door Microsoft Defender Antivirus worden gesaneerd.

> [!NOTE]
> Microsoft Defender Antivirus kan alleen in de passieve modus worden uitgevoerd wanneer het apparaat is onboarded bij Microsoft Defender voor Eindpunt.

Zie Microsoft Defender Antivirus [compatibiliteit voor meer informatie.](microsoft-defender-antivirus-compatibility.md)

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Hoe bevestig ik dat Microsoft Defender Antivirus actief of passief is?

U Microsoft Defender Antivirus kunt opdrachtprompt of PowerShell gebruiken op een apparaat met Windows.

|Methode  |Procedure  |
|---------|---------|
| PowerShell     | 1. Selecteer de Startmenu, begin te typen en open Windows PowerShell `PowerShell` in de resultaten. <p>2. Typ `Get-MpComputerStatus` . <p>3. Zoek in de lijst met resultaten in de rij **AMRunningMode** naar een van de volgende waarden: <br/>- `Normal` <br/>- `Passive Mode` <p>Zie [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)voor meer informatie.        |
|Opdrachtprompt     | 1. Selecteer de Startmenu, begin te typen en open Windows `Command Prompt` opdrachtprompt in de resultaten. <p>2. Typ `sc query windefend` . <p>3. Bevestig in de lijst met resultaten in de rij **STATE** dat de service wordt uitgevoerd.         |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>Hoe bevestig ik dat EDR in de blokmodus is ingeschakeld met Microsoft Defender Antivirus in passieve modus?

U kunt PowerShell gebruiken om te bevestigen dat EDR in de blokmodus is ingeschakeld met Microsoft Defender Antivirus in passieve modus.

1. Selecteer de Startmenu, begin te `PowerShell` typen en open Windows PowerShell in de resultaten. 

2. Typ `Get-MPComputerStatus | select AMRunningMode`.

3. Controleer of het resultaat `EDR Block Mode` wordt weergegeven.

   > [!TIP]
   > Als Microsoft Defender Antivirus in de actieve modus staat, ziet u in `Normal` plaats van `EDR Block Mode` . Zie [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)voor meer informatie.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Wordt EDR in de blokmodus ondersteund op Windows Server 2016?

Als Microsoft Defender Antivirus in de actieve modus of passieve modus wordt uitgevoerd, wordt EDR in de blokmodus ondersteund van de volgende versies van Windows:

- Windows 10 (alle releases)
- Windows Server, versie 1803 of hoger 
- Windows Server 2019 

#### <a name="what-about-windows-server-2016"></a>Hoe zit het met Windows Server 2016? 

Als Windows Server 2016 in Microsoft Defender Antivirus modus actief is en het eindpunt is onboarded bij Defender voor Eindpunt, wordt EDR in de blokmodus technisch ondersteund. De EDR in de blokmodus is echter bedoeld als extra beveiliging wanneer Microsoft Defender Antivirus niet de primaire antivirusoplossing op een eindpunt is. In dat geval wordt Microsoft Defender Antivirus uitgevoerd in de passieve modus. 

Op dit moment wordt Microsoft Defender Antivirus in passieve modus niet ondersteund op Windows Server 2016. Zie voor meer informatie [Microsoft Defender Antivirus en niet-Microsoft antivirus-/antimalware-oplossingen.](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Hoeveel tijd duurt het om de EDR in de blokmodus uit te schakelen?

Als u ervoor kiest om de EDR in de blokmodus uit te schakelen, kan het tot 30 minuten duren voordat het systeem deze mogelijkheid heeft uitgeschakeld.

## <a name="see-also"></a>Zie ook

- [Tech Community-blog: Introductie van EDR in de blokmodus: Aanvallen stoppen](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Gedragsblokkering en -insluiting](behavioral-blocking-containment.md)

