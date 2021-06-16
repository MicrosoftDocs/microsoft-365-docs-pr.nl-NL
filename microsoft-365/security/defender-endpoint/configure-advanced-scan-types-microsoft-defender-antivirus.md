---
title: Scanopties configureren voor Microsoft Defender Antivirus
description: U kunt Microsoft Defender AV configureren voor het scannen van e-mailopslagbestanden, back-up- of herstelpunten, netwerkbestanden en gearchiveerde bestanden (zoals .zip bestanden).
keywords: geavanceerde scans, scannen, e-mail, archief, zip, rar, archief, herparseren scannen
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 96e4dab96f8ceb149916c908991079bb2dfa866f
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964895"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Microsoft Defender Antivirus-scanopties configureren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Scanopties Microsoft Intune gebruiken om scanopties te configureren

Zie Instellingen voor apparaatbeperkingen configureren [in](/intune/device-restrictions-configure) Microsoft Intune en Microsoft Defender Antivirus instellingen voor apparaatbeperkingen voor Windows 10 [in Intune voor meer informatie.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Gebruik Microsoft Endpoint Manager om scanopties te configureren

Zie [Antimalware-beleid](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)maken en implementeren voor meer informatie over het configureren Microsoft Endpoint Manager (huidige vertakking).

## <a name="use-group-policy-to-configure-scanning-options"></a>Groepsbeleid gebruiken om scanopties te configureren

1. Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**

3. Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**

4. Vouw de boom uit **Windows onderdelen Microsoft Defender Antivirus** en selecteer vervolgens een locatie (zie Instellingen  >  en [locaties](#settings-and-locations) in dit artikel).


5. Bewerk het beleidsobject. 

6. Klik **op OK** en herhaal dit voor andere instellingen.

### <a name="settings-and-locations"></a>Instellingen en locaties

| Beleidsitem en locatie | Standaardinstelling (indien niet geconfigureerd) | `Set-MpPreference`PowerShell-parameter of WMI-eigenschap voor `MSFT_MpPreference` klas |
|---|---|---|
| E-mail scannen <p> **Scannen**  >  **E-mail scannen in-/uit-**<p>Zie [Beperkingen voor het scannen van e-mail](#email-scanning-limitations) (in dit artikel) | Uitgeschakeld | `-DisableEmailScanning` |
|[Reparse-punten scannen](/windows/win32/fileio/reparse-points) <p> **Scannen**  >  **Reparse point scanning in-** | Uitgeschakeld | Niet beschikbaar <p>Zie [Punten reparseren](/windows/win32/fileio/reparse-points)  |
| Netwerkstations scannen <p> **Scannen**  >  **Volledige scan uitvoeren op netwerkstations** met kaart | Uitgeschakeld | `-DisableScanningMappedNetworkDrivesForFullScan`|
| Archiefbestanden scannen (zoals .zip of .rar bestanden).  <p> **Scannen**  >  **Archiefbestanden scannen** | Ingeschakeld | `-DisableArchiveScanning` <p>De [uitsluitingslijst voor extensies](configure-extension-file-exclusions-microsoft-defender-antivirus.md) heeft voorrang op deze instelling.|
| Bestanden in het netwerk scannen <p> **Scannen**  >  **Netwerkbestanden scannen** | Uitgeschakeld | `-DisableScanningNetworkFiles` |
| Scanpakket uitvoerbare bestanden <p> **Scannen**  >  **Scanpakket uitvoerbare bestanden** | Ingeschakeld | Niet beschikbaar |
| Verwisselbare stations alleen scannen tijdens volledige scans <p> **Scannen**  >  **Verwisselbare stations scannen** | Uitgeschakeld | `-DisableRemovableDriveScanning` |
| Het niveau opgeven van submappen in een archiefmap om te scannen <p>**Scannen**  >  **De maximale diepte opgeven voor het scannen van archiefbestanden** | 0 | Niet beschikbaar |
| Geef de maximale CPU-belasting (als percentage) op tijdens een scan. <p> **Scannen**  >  **Het maximale percentage cpu-gebruik opgeven tijdens een scan** | 50 |  `-ScanAvgCPULoadFactor` <p>**OPMERKING:** De maximale CPU-belasting is geen harde limiet, maar is wel een richtlijn voor de scan-engine om het maximum niet te overschrijden. Handmatig scans uitvoeren negeert deze instelling en wordt uitgevoerd zonder CPU-limieten. |
| Geef de maximale grootte (in kilobytes) op van archiefbestanden die moeten worden gescand. <p> **Scannen**  >  **De maximale grootte opgeven van archiefbestanden die moeten worden gescand** | Geen limiet | Niet beschikbaar <p>De standaardwaarde van 0 geldt geen limiet |
| Lage CPU-prioriteit configureren voor geplande scans <p> **Scannen**  >  **Lage CPU-prioriteit configureren voor geplande scans** | Uitgeschakeld | Niet beschikbaar |

 
> [!NOTE]
> Als realtimebeveiliging is ingeschakeld, worden bestanden gescand voordat ze worden toegankelijk en uitgevoerd. Het scanbereik bevat alle bestanden, inclusief bestanden op opgeslagen verwisselbare media, zoals USB-stations. Als het apparaat dat de scan voert realtimebeveiliging of on-access-beveiliging heeft ingeschakeld, bevat de scan ook netwerkaandelen.

## <a name="use-powershell-to-configure-scanning-options"></a>PowerShell gebruiken om scanopties te configureren


Zie voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus

- [Beheer Microsoft Defender Antivirus met PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender-cmdlets](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>WMI gebruiken om scanopties te configureren

Zie [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="email-scanning-limitations"></a>Beperkingen voor het scannen van e-mail

Met e-mail scannen kunt u e-mailbestanden scannen die door Outlook en andere e-mail clients worden gebruikt tijdens scans op aanvraag en gepland. Ingesloten objecten in e-mail (zoals bijlagen en gearchiveerde bestanden) worden ook gescand. De volgende bestandsindelingstypen kunnen worden gescand en gesaneerd:

- DBX
- MBX
- MIME

PST-bestanden die worden gebruikt door Outlook 2003 of ouder (waarbij het archieftype is ingesteld op niet-unicode) worden ook gescand, maar Microsoft Defender Antivirus kunnen geen bedreigingen herstellen die worden gedetecteerd in PST-bestanden.

Als Microsoft Defender Antivirus een bedreiging in een e-mailbericht detecteert, worden de volgende gegevens weergegeven om u te helpen bij het identificeren van de gecompromitteerde e-mail, zodat u de bedreiging handmatig kunt herstellen:

- E-mail onderwerp
- Naam van bijlage


## <a name="scanning-mapped-network-drives"></a>Netwerkstations scannen

Op elk besturingssysteem worden alleen de netwerkstations gescand die op systeemniveau zijn in kaart gebracht. Netwerkstations op gebruikersniveau worden niet gescand. Netwerkstations op gebruikersniveau zijn netwerken die een gebruiker handmatig in zijn of haar sessie toewijst en zijn eigen referenties gebruikt.

## <a name="see-also"></a>Zie ook


- [De resultaten van scans en herstel van Microsoft Defender Antivirus aanpassen, starten en controleren](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus-scans op aanvraag configureren en uitvoeren](run-scan-microsoft-defender-antivirus.md)
- [Geplande scans Microsoft Defender Antivirus configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
