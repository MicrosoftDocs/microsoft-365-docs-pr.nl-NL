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
ms.date: 05/05/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: d7ab8afd1d643933dc71a5bef1385b9ab95b553f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245802"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Endpoint detection and response (EDR) in block mode

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Wat is EDR in de blokmodus?

[Eindpuntdetectie en -respons](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) in de blokmodus biedt bescherming tegen schadelijke artefacten, zelfs wanneer Microsoft Defender Antivirus actief is in de passieve modus. Wanneer deze functie is ingeschakeld, EDR in de blokmodus schadelijke artefacten of gedragingen die op een apparaat worden gedetecteerd, geblokkeerd. EDR in de blokmodus werkt achter de schermen om schadelijke artefacten te corrigeren die na een inbreuk worden gedetecteerd. 

EDR in de blokmodus is ook geïntegreerd met [bedreigingen & vulnerability management.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) Het beveiligingsteam van uw [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) organisatie krijgt een beveiligingsaanbeveling om de EDR in de blokmodus in te schakelen als dit nog niet is ingeschakeld. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="aanbeveling om de EDR in te schakelen in de blokmodus":::

> [!NOTE]
> Als u de beste beveiliging wilt, moet u Microsoft Defender voor eindpunten **[implementeren.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>Wat gebeurt er wanneer er iets wordt gedetecteerd?

Wanneer EDR in de blokmodus is ingeschakeld en er een schadelijk artefact wordt gedetecteerd, blokkeert en herstelt Microsoft Defender voor eindpunten dat artefact. U ziet de detectiestatus als **Geblokkeerd** of Voorkomen **als** voltooide acties in het [Actiecentrum.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)

In de volgende afbeelding ziet u een exemplaar van ongewenste software die is gedetecteerd en geblokkeerd via EDR in de blokmodus:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR in de blokmodus iets gedetecteerd":::


## <a name="enable-edr-in-block-mode"></a>De EDR in de blokmodus inschakelen

> [!IMPORTANT]
> Zorg ervoor dat [aan de vereisten](#requirements-for-edr-in-block-mode) wordt voldaan voordat u EDR in de blokmodus.

1. Ga naar het Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) en meld u aan. 

2. Kies **Instellingen**  >  **Geavanceerde functies.**

3. Schakel de **EDR in de blokmodus in.**

> [!NOTE]
> EDR in de blokmodus kan alleen in de Microsoft Defender-beveiligingscentrum. U kunt registersleutels, Intune- of groepsbeleid niet gebruiken om de EDR in of uit te schakelen in de blokmodus.

## <a name="requirements-for-edr-in-block-mode"></a>Vereisten voor EDR in blokmodus

|Vereiste  |Details  |
|---------|---------|
|Machtigingen |Globale beheerder of beveiligingsbeheerder die is toegewezen in [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) Zie [Basismachtigingen.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions) |
|Besturingssysteem     |Een van de volgende versies: <br/>- Windows 10 (alle releases) <br/>- Windows Server, versie 1803 of hoger <br/>- Windows Server 2019  <p>**OPMERKING:** EDR in de blokmodus wordt niet ondersteund op Windows Server 2016.       |
|Windows E5-inschrijving     |Windows E5 is opgenomen in de volgende abonnementen: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 samen met het aanbod voor identiteits- & bedreigingsbeveiliging <br/><br/>Zie [Onderdelen](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) en [functies en mogelijkheden voor elk abonnement.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Microsoft Defender Antivirus  |Microsoft Defender Antivirus moet zijn geïnstalleerd en uitgevoerd in de actieve of passieve modus. (U kunt Microsoft Defender Antivirus naast een niet-Microsoft-antivirusoplossing gebruiken.) [Bevestig Microsoft Defender Antivirus actief of passief is.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Cloudbeveiliging |Zorg ervoor dat Microsoft Defender Antivirus zodanig is geconfigureerd dat beveiliging in de [cloud is ingeschakeld.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) |
|Microsoft Defender Antivirus antimalwareclient |Zorg ervoor dat uw client up-to-date is. Voer met PowerShell de [cmdlet Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) uit als beheerder. In de **REGEL AMProductVersion** ziet u **4.18.2001.10** of hoger. |
|Microsoft Defender Antivirus engine |Zorg ervoor dat uw motor up-to-date is. Voer met PowerShell de [cmdlet Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) uit als beheerder. In de **REGEL AMEngineVersion** ziet u **1.1.16700.2** of hoger. |

> [!IMPORTANT]
> Als u de beste [beschermingswaarde](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)wilt krijgen, moet u ervoor zorgen dat uw antivirusoplossing is geconfigureerd voor regelmatige updates en essentiële functies en dat uw uitsluitingen zijn geconfigureerd. EDR in de blokmodus respecteert uitsluitingen die zijn gedefinieerd voor Microsoft Defender Antivirus.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Moet ik de EDR in de blokmodus inschakelen, zelfs wanneer ik Microsoft Defender Antivirus apparaten heb uitgevoerd?

Het is raadzaam de EDR in de blokmodus aan te houden, ongeacht Microsoft Defender Antivirus actief is in de passieve modus of in de actieve modus. EDR in de blokmodus biedt een andere verdedigingslaag met Microsoft Defender voor Eindpunt. Hiermee kan Defender voor Eindpunt acties uitvoeren op basis van gedragsproblemen na inbreuk EDR detecties. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Is EDR in de blokmodus van invloed op de antivirusbeveiliging van een gebruiker? 

EDR in de blokmodus heeft geen invloed op antivirusbeveiliging van derden die wordt uitgevoerd op apparaten van gebruikers. EDR in de blokmodus werkt als de primaire antivirusoplossing iets mist of als er een detectie na inbreuk is. EDR in de blokmodus werkt net als Microsoft Defender Antivirus [in](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)passieve modus, behalve dat schadelijke artefacten of gedragingen die worden gedetecteerd, ook worden geblokkeerd en gesaneerd. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Waarom moet ik mijn Microsoft Defender Antivirus up-to-date houden? 

Omdat Microsoft Defender Antivirus schadelijke items detecteert en herstelt, is het belangrijk om deze up-to-date te houden. Om EDR in de blokmodus effectief te maken, worden de nieuwste leermodellen, gedragsdetecties en heuristische toepassingen gebruikt. De [stapel mogelijkheden van Defender](https://docs.microsoft.com/windows/security/threat-protection) voor eindpunten werkt op een geïntegreerde manier. Als u de beste beschermingswaarde wilt, moet u Microsoft Defender Antivirus up-to-date houden.  

### <a name="why-do-we-need-cloud-protection-on"></a>Waarom hebben we cloudbeveiliging nodig? 

Cloudbeveiliging is nodig om de functie op het apparaat in te zetten. Met cloudbeveiliging kan [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) de nieuwste en beste beveiliging bieden op basis van onze uitgebreide en uitgebreide beveiligingsinformatie, samen met modellen voor het leren van gedrag en apparaten.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Hoe stel ik de Microsoft Defender Antivirus in op passieve modus?

Zie [Microsoft Defender Antivirus inschakelen en bevestigen dat deze in de passieve modus staat.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Hoe bevestig ik dat Microsoft Defender Antivirus actief of passief is?

U Microsoft Defender Antivirus kunt opdrachtprompt of PowerShell gebruiken op een apparaat met Windows.

#### <a name="use-powershell"></a>PowerShell gebruiken

1. Selecteer het menu Start, begin te `PowerShell` typen en open Windows PowerShell in de resultaten.

2. Type `Get-MpComputerStatus`.

3. Zoek in de lijst met resultaten in de **rij AMRunningMode** naar een van de volgende waarden:   
   - `Normal`
   - `Passive Mode`  
   - `SxS Passive Mode`

Zie [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)voor meer informatie.

#### <a name="use-command-prompt"></a>Opdrachtprompt gebruiken

1. Selecteer het menu Start, begin te `Command Prompt` typen en open Windows opdrachtprompt in de resultaten.

2. Type `sc query windefend`.

3. Controleer in de lijst met resultaten in de **rij STATE** of de service wordt uitgevoerd.

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Hoeveel tijd duurt het om de EDR in de blokmodus uit te schakelen?

Als u ervoor kiest om de EDR in de blokmodus uit te schakelen, kan het tot 30 minuten duren voordat het systeem deze mogelijkheid heeft uitgeschakeld.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Wordt EDR in de blokmodus ondersteund op Windows Server 2016?

Nee. EDR in de blokmodus wordt ondersteund van de volgende versies van Windows:

- Windows 10 (alle releases)
- Windows Server, versie 1803 of hoger 
- Windows Server 2019 

## <a name="see-also"></a>Zie ook

- [Tech Community-blog: Introductie van EDR in de blokmodus: Aanvallen stoppen](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Gedragsblokkering en -insluiting](behavioral-blocking-containment.md)
- [Samen beter: Microsoft Defender Antivirus en Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

