---
title: Eindpuntdetectie en -reactie in de blokmodus
description: Meer informatie over eindpuntdetectie en -antwoorden in de blokmodus
keywords: Microsoft Defender ATP, EDR in blokmodus, passieve modus blokkeren
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
ms.date: 01/26/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 7bee6c99d2c1c5ad3cec8f2e317b729a0a4e1f8b
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379476"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Endpoint detection and response (EDR) in block mode

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Wat is EDR in de blokmodus?

[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) in block mode biedt bescherming tegen schadelijke artefacten, zelfs wanneer Microsoft Defender Antivirus wordt uitgevoerd in de passieve modus. Wanneer EDR is ingeschakeld, blokkeert EDR in de blokmodus schadelijke artefacten of gedragingen die worden gedetecteerd op een apparaat. EDR in de blokmodus werkt achter de schermen om schadelijke artefacten te corrigeren die worden gedetecteerd na een inbreuk. 

EDR in de blokmodus is ook geïntegreerd met [& beveiligingsprobleembeheer.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) Het beveiligingsteam van uw [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) organisatie krijgt een beveiligingsaanbeveling om EDR in de blokmodus in te schakelen als dit nog niet is ingeschakeld. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="aanbeveling om EDR in te schakelen in de blokmodus":::

> [!NOTE]
> Als u de beste beveiliging wilt, moet u Microsoft Defender voor eindpunten **[implementeren.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>Wat gebeurt er wanneer er iets wordt gedetecteerd?

Wanneer EDR in de blokmodus is ingeschakeld en er een schadelijk artefact wordt gedetecteerd, blokkeert en herstelt Microsoft Defender voor Eindpunten dat artefact. U ziet de detectiestatus als **Geblokkeerd** of Voorkomen **als** voltooide acties in het [Actiecentrum.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)

In de volgende afbeelding ziet u een exemplaar van ongewenste software die is gedetecteerd en geblokkeerd via EDR in de blokmodus:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR in blokmodus heeft iets gedetecteerd":::


## <a name="enable-edr-in-block-mode"></a>EDR inschakelen in de blokmodus

> [!IMPORTANT]
> Zorg ervoor dat [aan de vereisten](#requirements-for-edr-in-block-mode) wordt voldaan voordat u EDR in de blokmodus inschakelen.

1. Ga naar het Microsoft Defender-beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) () en meld u aan. 

2. Kies **Instellingen Geavanceerde**  >  **functies.**

3. Schakel **EDR in de blokmodus in.**

> [!NOTE]
> EDR in de blokmodus kan alleen worden ingeschakeld in het Microsoft Defender-beveiligingscentrum. U kunt registersleutels, Intune- of groepsbeleid niet gebruiken om EDR in of uit te schakelen in de blokmodus.

## <a name="requirements-for-edr-in-block-mode"></a>Vereisten voor EDR in de blokmodus

|Vereiste  |Details  |
|---------|---------|
|Machtigingen |Globale beheerder of beveiligingsbeheerder die is toegewezen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Zie [Basismachtigingen.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions) |
|Besturingssysteem     |Een van de volgende versies: <br/>- Windows 10 (alle releases) <br/>- Windows Server, versie 1803 of hoger <br/>- Windows Server 2019         |
|Windows E5-inschrijving     |Windows E5 is opgenomen in de volgende abonnementen: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 samen met de identity & Threat Protection-aanbieding <br/><br/>Zie [Onderdelen](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) en [functies en mogelijkheden voor elk abonnement.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Microsoft Defender Antivirus  |Microsoft Defender Antivirus moet zijn geïnstalleerd en uitgevoerd in de actieve of passieve modus. (U kunt Microsoft Defender Antivirus naast een niet-Microsoft-antivirusoplossing gebruiken.) [Bevestig dat Microsoft Defender Antivirus actief of passief is.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Beveiliging in de cloud |Zorg ervoor dat Microsoft Defender Antivirus zodanig is geconfigureerd dat beveiliging in de [cloud is ingeschakeld.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) |
|Microsoft Defender Antivirus antimalware-client |Zorg ervoor dat uw client up-to-date is. Voer met PowerShell de [cmdlet Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) uit als beheerder. In de **REGEL AMProductVersion** ziet u **4.18.2001.10** of hoger. |
|Microsoft Defender Antivirus-engine |Zorg ervoor dat uw motor up-to-date is. Voer met PowerShell de [cmdlet Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) uit als beheerder. In de **REGEL AMEngineVersion** ziet u **1.1.16700.2** of hoger. |

> [!IMPORTANT]
> Als u de beste [beschermingswaarde](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)wilt krijgen, moet u ervoor zorgen dat uw antivirusoplossing is geconfigureerd voor regelmatige updates en essentiële functies en dat uw uitsluitingen zijn geconfigureerd. EDR in de blokmodus respecteert uitsluitingen die zijn gedefinieerd voor Microsoft Defender Antivirus.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Moet ik EDR in de blokmodus inschakelen, zelfs als Microsoft Defender Antivirus op apparaten wordt uitgevoerd?

Het is raadzaam om EDR in de blokmodus aan te houden, ongeacht of Microsoft Defender Antivirus actief is in de passieve modus of in de actieve modus. EDR in de blokmodus biedt een andere verdedigingslaag met Microsoft Defender voor eindpunt. Hiermee kan Defender voor Eindpunt acties uitvoeren op basis van gedrags-EDR-detecties na inbreuk. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Heeft EDR in de blokmodus invloed op de antivirusbeveiliging van een gebruiker? 

EDR in de blokmodus heeft geen invloed op antivirusbeveiliging van derden die wordt uitgevoerd op apparaten van gebruikers. EDR in de blokmodus werkt als de primaire antivirusoplossing iets mist of als er een detectie na inbreuk is. EDR in de blokmodus werkt net als Microsoft Defender Antivirus in passieve [modus,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)maar blokkeert en herstelt ook schadelijke artefacten of gedragingen die worden gedetecteerd. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Waarom moet ik Microsoft Defender Antivirus up-to-date houden? 

Omdat Microsoft Defender Antivirus schadelijke items detecteert en herstelt, is het belangrijk om deze up-to-date te houden. Om EDR in de blokmodus effectief te laten zijn, worden de nieuwste leermodellen, gedragsdetecties en heuristische toepassingen gebruikt. De [stapel mogelijkheden van Defender](https://docs.microsoft.com/windows/security/threat-protection) voor eindpunten werkt op een geïntegreerde manier. Om de beste beschermingswaarde te krijgen, moet u Microsoft Defender Antivirus up-to-date houden.  

### <a name="why-do-we-need-cloud-protection-on"></a>Waarom hebben we cloudbeveiliging nodig? 

Cloudbeveiliging is nodig om de functie op het apparaat in te zetten. Met cloudbeveiliging kan [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) de nieuwste en beste beveiliging bieden op basis van onze uitgebreide en uitgebreide beveiligingsinformatie, samen met modellen voor het leren van gedrag en apparaten.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Hoe stel ik Microsoft Defender Antivirus in op passieve modus?

Zie [Microsoft Defender Antivirus inschakelen en bevestig dat deze in de passieve modus staat.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Hoe kan ik bevestigen dat Microsoft Defender Antivirus actief of passief is?

Als u wilt controleren of Microsoft Defender Antivirus actief of passief is, kunt u Opdrachtprompt of PowerShell gebruiken op een apparaat met Windows.

#### <a name="use-powershell"></a>PowerShell gebruiken

1. Selecteer het menu Start, begin te `PowerShell` typen en open Vervolgens Windows PowerShell in de resultaten.

2. Type `Get-MpComputerStatus`.

3. Zoek in de lijst met resultaten in de **rij AMRunningMode** naar een van de volgende waarden:   
   - `Normal`
   - `Passive Mode`  
   - `SxS Passive Mode`

Zie [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)voor meer informatie.

#### <a name="use-command-prompt"></a>Opdrachtprompt gebruiken

1. Selecteer het menu Start, begin te `Command Prompt` typen en open vervolgens De opdrachtprompt van Windows in de resultaten.

2. Type `sc query windefend`.

3. Controleer in de lijst met resultaten in de **rij STATE** of de service wordt uitgevoerd.

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Hoeveel tijd duurt het om EDR in de blokmodus uit te schakelen?
Als u ervoor kiest om EDR uit te schakelen in de blokmodus, kan het tot 30 minuten duren voordat het systeem deze mogelijkheid heeft uitgeschakeld.

## <a name="see-also"></a>Zie ook

- [Tech Community-blog: Introductie van EDR in de blokmodus: Aanvallen stoppen](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Gedrag blokkeren en insluiting](behavioral-blocking-containment.md)
- [Beter samen: Microsoft Defender Antivirus en Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

