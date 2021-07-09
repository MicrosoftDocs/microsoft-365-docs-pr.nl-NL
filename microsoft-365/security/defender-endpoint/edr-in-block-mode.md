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
ms.date: 06/11/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: ae170ecf0fc0f354c9975300e5f2f7cd014b0c47
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339684"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Endpoint detection and response (EDR) in block mode

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Wat is EDR in de blokmodus?

[Eindpuntdetectie en -respons](overview-endpoint-detection-response.md) (EDR) in de blokmodus biedt bescherming tegen schadelijke artefacten, zelfs wanneer Microsoft Defender Antivirus actief is in de passieve modus. Wanneer deze functie is ingeschakeld, EDR in de blokmodus schadelijke artefacten of gedragingen die op een apparaat worden gedetecteerd, geblokkeerd. EDR in de blokmodus werkt achter de schermen om schadelijke artefacten te corrigeren die na een inbreuk worden gedetecteerd. 

EDR in de blokmodus is ook geïntegreerd met [bedreigingen & vulnerability management.](next-gen-threat-and-vuln-mgt.md) Het beveiligingsteam van uw [](tvm-security-recommendation.md) organisatie krijgt een beveiligingsaanbeveling om de EDR in de blokmodus in te schakelen als dit nog niet is ingeschakeld. 

:::image type="content" source="images/enable-edr-in-block-mode.png" alt-text="aanbeveling om de EDR in te schakelen in de blokmodus":::

> [!NOTE]
> Als u de beste beveiliging wilt, moet u Microsoft Defender voor eindpunten **[implementeren.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>Wat gebeurt er wanneer er iets wordt gedetecteerd?

Wanneer EDR in de blokmodus is ingeschakeld en er een schadelijk artefact wordt gedetecteerd, blokkeert en herstelt Microsoft Defender voor eindpunten dat artefact. Uw beveiligingsbewerkingsteam ziet de detectiestatus **als** Geblokkeerd of Voorkomen **in** het [Actiecentrum,](respond-machine-alerts.md#check-activity-details-in-action-center)weergegeven als voltooide acties.

In de volgende afbeelding ziet u een exemplaar van ongewenste software die is gedetecteerd en geblokkeerd via EDR in de blokmodus:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR in de blokmodus iets gedetecteerd":::


## <a name="enable-edr-in-block-mode"></a>De EDR in de blokmodus inschakelen

> [!IMPORTANT]
> Zorg ervoor dat [aan de vereisten](#requirements-for-edr-in-block-mode) wordt voldaan voordat u EDR in de blokmodus.

1. Ga naar de [Microsoft 365 Defender portal](microsoft-defender-security-center.md) en meld u aan. 

2. Kies **Instellingen**  >  **Geavanceerde functies.**

3. Schakel de **EDR in de blokmodus in.**

> [!NOTE]
> EDR in de blokmodus kan alleen worden ingeschakeld in de Microsoft 365 Defender portal. U kunt registersleutels, Intune- of groepsbeleid niet gebruiken om de EDR in of uit te schakelen in de blokmodus.

## <a name="requirements-for-edr-in-block-mode"></a>Vereisten voor EDR in blokmodus

|Vereiste  |Details  |
|---------|---------|
|Machtigingen |Globale beheerder of beveiligingsbeheerder die is toegewezen in [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) Zie [Basismachtigingen.](basic-permissions.md) |
|Besturingssysteem     |Een van de volgende versies: <br/>- Windows 10 (alle releases) <br/>- Windows Server, versie 1803 of hoger <br/>- Windows Server 2019 <br/>- Windows Server 2016 (alleen als Microsoft Defender Antivirus actief is)     |
|Windows E5-inschrijving     |Windows E5 is opgenomen in de volgende abonnementen: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 samen met het aanbod voor identiteits- & bedreigingsbeveiliging <br/><br/>Zie [Onderdelen](/microsoft-365/enterprise/microsoft-365-overview#components) en [functies en mogelijkheden voor elk abonnement.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Microsoft Defender Antivirus  |Microsoft Defender Antivirus moet zijn geïnstalleerd en uitgevoerd in de actieve of passieve modus. (U kunt Microsoft Defender Antivirus naast een niet-Microsoft-antivirusoplossing gebruiken.) [Bevestig Microsoft Defender Antivirus actief of passief is.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Cloudbeveiliging |Zorg ervoor dat Microsoft Defender Antivirus zodanig is geconfigureerd dat beveiliging in de [cloud is ingeschakeld.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Microsoft Defender Antivirus antimalwareclient |Zorg ervoor dat uw client up-to-date is. Voer met PowerShell de [cmdlet Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) uit als beheerder. In de **REGEL AMProductVersion** ziet u **4.18.2001.10** of hoger. |
|Microsoft Defender Antivirus engine |Zorg ervoor dat uw motor up-to-date is. Voer met PowerShell de [cmdlet Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) uit als beheerder. In de **REGEL AMEngineVersion** ziet u **1.1.16700.2** of hoger. |

> [!IMPORTANT]
> Als u de beste [beschermingswaarde](configure-exclusions-microsoft-defender-antivirus.md)wilt krijgen, moet u ervoor zorgen dat uw antivirusoplossing is geconfigureerd voor regelmatige updates en essentiële functies en dat uw uitsluitingen zijn geconfigureerd. EDR in de blokmodus respecteert uitsluitingen die zijn gedefinieerd voor Microsoft Defender Antivirus.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Moet ik de EDR in de blokmodus inschakelen, zelfs wanneer ik Microsoft Defender Antivirus apparaten heb uitgevoerd?

Het is raadzaam de EDR in de blokmodus aan te houden, ongeacht Microsoft Defender Antivirus actief is in de passieve modus of in de actieve modus. EDR in de blokmodus biedt een andere verdedigingslaag met Microsoft Defender voor Eindpunt. Hiermee kan Defender voor Eindpunt acties uitvoeren op basis van gedragsproblemen na inbreuk EDR detecties. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Is EDR in de blokmodus van invloed op de antivirusbeveiliging van een gebruiker? 

EDR in de blokmodus heeft geen invloed op antivirusbeveiliging van derden die wordt uitgevoerd op apparaten van gebruikers. EDR in de blokmodus werkt als de primaire antivirusoplossing iets mist of als er een detectie na inbreuk is. EDR in de blokmodus werkt net als Microsoft Defender Antivirus in passieve modus, behalve dat schadelijke artefacten of gedragingen die worden gedetecteerd, ook worden geblokkeerd en gesaneerd.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Waarom moet ik mijn Microsoft Defender Antivirus up-to-date houden? 

Omdat Microsoft Defender Antivirus schadelijke items detecteert en herstelt, is het belangrijk om deze up-to-date te houden. Om EDR in de blokmodus effectief te maken, worden de nieuwste leermodellen, gedragsdetecties en heuristische toepassingen gebruikt. De [stapel mogelijkheden van Defender](microsoft-defender-endpoint.md) voor eindpunten werkt op een geïntegreerde manier. Als u de beste beschermingswaarde wilt, moet u Microsoft Defender Antivirus up-to-date houden. Zie [Het Microsoft Defender Antivirus updates beheren en basislijnen toepassen.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-on"></a>Waarom hebben we cloudbeveiliging nodig? 

Cloudbeveiliging is nodig om de functie op het apparaat in te zetten. Met cloudbeveiliging kan [Defender for Endpoint](microsoft-defender-endpoint.md) de nieuwste en beste beveiliging bieden op basis van onze uitgebreide en uitgebreide beveiligingsinformatie, samen met modellen voor het leren van gedrag en apparaten.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Hoe stel ik de Microsoft Defender Antivirus in op passieve modus?

Afhankelijk van besturingssystemen kunnen apparaten die een niet-Microsoft-antivirus-/antimalware-oplossing uitvoeren, automatisch worden aangesloten bij Defender voor Eindpunt, Microsoft Defender Antivirus in de passieve modus gaan. Zie De werking van [Defender Microsoft Defender Antivirus endpoint](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality)voor meer informatie. 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Hoe bevestig ik dat Microsoft Defender Antivirus actief of passief is?

U Microsoft Defender Antivirus kunt opdrachtprompt of PowerShell gebruiken op een apparaat met Windows.


|Methode  |Procedure  |
|---------|---------|
| PowerShell     | 1. Selecteer de Startmenu, begin te typen en open Windows PowerShell `PowerShell` in de resultaten. <p>2. Typ `Get-MpComputerStatus` . <p>3. Zoek in de lijst met resultaten in de rij **AMRunningMode** naar een van de volgende waarden: <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Zie [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)voor meer informatie.        |
|Opdrachtprompt     | 1. Selecteer de Startmenu, begin te typen en open Windows `Command Prompt` opdrachtprompt in de resultaten. <p>2. Typ `sc query windefend` . <p>3. Bevestig in de lijst met resultaten in de rij **STATE** dat de service wordt uitgevoerd.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Hoeveel tijd duurt het om de EDR in de blokmodus uit te schakelen?

Als u ervoor kiest om de EDR in de blokmodus uit te schakelen, kan het tot 30 minuten duren voordat het systeem deze mogelijkheid heeft uitgeschakeld.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Wordt EDR in de blokmodus ondersteund op Windows Server 2016?

Als Microsoft Defender Antivirus in de actieve modus of passieve modus wordt uitgevoerd, wordt EDR in de blokmodus ondersteund van de volgende versies van Windows:

- Windows 10 (alle releases)
- Windows Server, versie 1803 of hoger 
- Windows Server 2019 

Als Windows Server 2016 in Microsoft Defender Antivirus modus actief is en het eindpunt is onboarded bij Defender voor Eindpunt, wordt EDR in de blokmodus technisch ondersteund. De EDR in de blokmodus is echter bedoeld als extra beveiliging wanneer Microsoft Defender Antivirus niet de primaire antivirusoplossing op een eindpunt is. In dat geval wordt Microsoft Defender Antivirus uitgevoerd in de passieve modus. Op dit moment wordt Microsoft Defender Antivirus in passieve modus niet ondersteund op Windows Server 2016. Zie voor meer informatie [Microsoft Defender Antivirus en niet-Microsoft antivirus-/antimalware-oplossingen.](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)

## <a name="see-also"></a>Zie ook

- [Tech Community-blog: Introductie van EDR in de blokmodus: Aanvallen stoppen](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Gedragsblokkering en -insluiting](behavioral-blocking-containment.md)

