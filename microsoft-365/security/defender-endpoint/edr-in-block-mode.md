---
title: Eindpuntdetectie en -reactie in de blokmodus
description: Meer informatie over eindpuntdetectie en -antwoorden in de blokmodus
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
ms.date: 05/06/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 78201fd20d689a6774eb5395aa787a2b15147972
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274482"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Endpoint detection and response (EDR) in block mode

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Wat is EDR in de blokmodus?

[Endpoint detection and response](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) in block mode biedt bescherming tegen schadelijke artefacten, zelfs wanneer Microsoft Defender Antivirus wordt uitgevoerd in de passieve modus. Wanneer EDR is ingeschakeld, blokkeert EDR in de blokmodus schadelijke artefacten of gedragingen die worden gedetecteerd op een apparaat. EDR in de blokmodus werkt achter de schermen om schadelijke artefacten te corrigeren die worden gedetecteerd na een inbreuk. 

EDR in de blokmodus is ook geïntegreerd met [& beveiligingsprobleembeheer.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) Het beveiligingsteam van uw [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) organisatie krijgt een beveiligingsaanbeveling om EDR in de blokmodus in te schakelen als dit nog niet is ingeschakeld. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="aanbeveling om EDR in te schakelen in de blokmodus":::

> [!NOTE]
> Als u de beste beveiliging wilt, moet u Microsoft Defender voor eindpunten **[implementeren.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>Wat gebeurt er wanneer er iets wordt gedetecteerd?

Wanneer EDR in de blokmodus is ingeschakeld en er een schadelijk artefact wordt gedetecteerd, blokkeert en herstelt Microsoft Defender voor Eindpunten dat artefact. Uw beveiligingsbewerkingsteam ziet de detectiestatus **als** Geblokkeerd of Voorkomen **in** het [Actiecentrum,](respond-machine-alerts.md#check-activity-details-in-action-center)weergegeven als voltooide acties.

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
|Besturingssysteem     |Een van de volgende versies: <br/>- Windows 10 (alle releases) <br/>- Windows Server, versie 1803 of hoger <br/>- Windows Server 2019 <br/>- Windows Server 2016 (alleen als Microsoft Defender Antivirus actief is)     |
|Windows E5-inschrijving     |Windows E5 is opgenomen in de volgende abonnementen: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 samen met de identity & Threat Protection-aanbieding <br/><br/>Zie [Onderdelen](/microsoft-365/enterprise/microsoft-365-overview#components) en [functies en mogelijkheden voor elk abonnement.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Microsoft Defender Antivirus  |Microsoft Defender Antivirus moet zijn geïnstalleerd en uitgevoerd in de actieve of passieve modus. (U kunt Microsoft Defender Antivirus naast een niet-Microsoft-antivirusoplossing gebruiken.) [Bevestig dat Microsoft Defender Antivirus actief of passief is.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Cloudbeveiliging |Zorg ervoor dat Microsoft Defender Antivirus zodanig is geconfigureerd dat beveiliging in de [cloud is ingeschakeld.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Microsoft Defender Antivirus antimalware-client |Zorg ervoor dat uw client up-to-date is. Voer met PowerShell de [cmdlet Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) uit als beheerder. In de **REGEL AMProductVersion** ziet u **4.18.2001.10** of hoger. |
|Microsoft Defender Antivirus-engine |Zorg ervoor dat uw motor up-to-date is. Voer met PowerShell de [cmdlet Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) uit als beheerder. In de **REGEL AMEngineVersion** ziet u **1.1.16700.2** of hoger. |

> [!IMPORTANT]
> Als u de beste [beschermingswaarde](configure-exclusions-microsoft-defender-antivirus.md)wilt krijgen, moet u ervoor zorgen dat uw antivirusoplossing is geconfigureerd voor regelmatige updates en essentiële functies en dat uw uitsluitingen zijn geconfigureerd. EDR in de blokmodus respecteert uitsluitingen die zijn gedefinieerd voor Microsoft Defender Antivirus.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Moet ik EDR in de blokmodus inschakelen, zelfs als Microsoft Defender Antivirus op apparaten wordt uitgevoerd?

Het is raadzaam om EDR in de blokmodus aan te houden, ongeacht of Microsoft Defender Antivirus actief is in de passieve modus of in de actieve modus. EDR in de blokmodus biedt een andere verdedigingslaag met Microsoft Defender voor eindpunt. Hiermee kan Defender voor Eindpunt acties uitvoeren op basis van gedrags-EDR-detecties na inbreuk. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Heeft EDR in de blokmodus invloed op de antivirusbeveiliging van een gebruiker? 

EDR in de blokmodus heeft geen invloed op antivirusbeveiliging van derden die wordt uitgevoerd op apparaten van gebruikers. EDR in de blokmodus werkt als de primaire antivirusoplossing iets mist of als er een detectie na inbreuk is. EDR in de blokmodus werkt net als Microsoft Defender Antivirus in passieve [modus,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)maar blokkeert en herstelt ook schadelijke artefacten of gedragingen die worden gedetecteerd. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Waarom moet ik Microsoft Defender Antivirus up-to-date houden? 

Omdat Microsoft Defender Antivirus schadelijke items detecteert en herstelt, is het belangrijk om deze up-to-date te houden. Om EDR in de blokmodus effectief te laten zijn, worden de nieuwste leermodellen, gedragsdetecties en heuristische toepassingen gebruikt. De [stapel mogelijkheden van Defender](microsoft-defender-endpoint.md) voor eindpunten werkt op een geïntegreerde manier. Om de beste beschermingswaarde te krijgen, moet u Microsoft Defender Antivirus up-to-date houden. Zie [Microsoft Defender Antivirus-updates beheren en basislijnen toepassen.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-on"></a>Waarom hebben we cloudbeveiliging nodig? 

Cloudbeveiliging is nodig om de functie op het apparaat in te zetten. Met cloudbeveiliging kan [Defender for Endpoint](microsoft-defender-endpoint.md) de nieuwste en beste beveiliging bieden op basis van onze uitgebreide en uitgebreide beveiligingsinformatie, samen met modellen voor het leren van gedrag en apparaten.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Hoe stel ik Microsoft Defender Antivirus in op passieve modus?

Afhankelijk van besturingssystemen kan Microsoft Defender Antivirus automatisch in de passieve modus gaan wanneer apparaten met een niet-Microsoft-antivirus-/antimalware-oplossing zijn onboarded bij Defender for Endpoint. Zie Antivirus en [Microsoft Defender voor Eindpunt voor meer informatie.](microsoft-defender-antivirus-compatibility.md#antivirus-and-microsoft-defender-for-endpoint) 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Hoe kan ik bevestigen dat Microsoft Defender Antivirus actief of passief is?

Als u wilt controleren of Microsoft Defender Antivirus actief of passief is, kunt u Opdrachtprompt of PowerShell gebruiken op een apparaat met Windows.


|Methode  |Procedure  |
|---------|---------|
| PowerShell     | 1. Selecteer het menu Start, begin te `PowerShell` typen en open Vervolgens Windows PowerShell in de resultaten. <p>2. Typ `Get-MpComputerStatus` . <p>3. Zoek in de lijst met resultaten in de rij **AMRunningMode** naar een van de volgende waarden: <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Zie [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)voor meer informatie.        |
|Opdrachtprompt     | 1. Selecteer het menu Start, begin te `Command Prompt` typen en open vervolgens De opdrachtprompt van Windows in de resultaten. <p>2. Typ `sc query windefend` . <p>3. Bevestig in de lijst met resultaten in de rij **STATE** dat de service wordt uitgevoerd.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Hoeveel tijd duurt het om EDR in de blokmodus uit te schakelen?

Als u ervoor kiest om EDR uit te schakelen in de blokmodus, kan het tot 30 minuten duren voordat het systeem deze mogelijkheid heeft uitgeschakeld.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Wordt EDR in de blokmodus ondersteund op Windows Server 2016?

Als Microsoft Defender Antivirus wordt uitgevoerd in de actieve modus of passieve modus, wordt EDR in de blokmodus ondersteund van de volgende versies van Windows:

- Windows 10 (alle releases)
- Windows Server, versie 1803 of hoger 
- Windows Server 2019 

Als In Windows Server 2016 Microsoft Defender Antivirus wordt uitgevoerd in de actieve modus en het eindpunt is onboarded bij Defender voor Eindpunt, wordt EDR in de blokmodus ondersteund. EDR in de blokmodus is echter bedoeld als extra beveiliging wanneer Microsoft Defender Antivirus niet de primaire antivirusoplossing op een eindpunt is. 

## <a name="see-also"></a>Zie ook

- [Tech Community-blog: Introductie van EDR in de blokmodus: Aanvallen stoppen](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Gedragsblokkering en -insluiting](behavioral-blocking-containment.md)
- [Samen beter: Microsoft Defender Antivirus en Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

