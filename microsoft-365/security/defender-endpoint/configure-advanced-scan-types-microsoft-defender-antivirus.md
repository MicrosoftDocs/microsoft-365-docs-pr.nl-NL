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
ms.topic: article
ms.openlocfilehash: 1efa72d5b8d204b6aec1cef05fe3c8afe1ca82f7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275300"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Microsoft Defender Antivirus-scanopties configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Scanopties Microsoft Intune gebruiken om scanopties te configureren

Zie [Instellingen voor apparaatbeperkingen configureren in Microsoft Intune](/intune/device-restrictions-configure) en Microsoft Defender Antivirus instellingen voor apparaatbeperkingen voor Windows 10 in [Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) voor meer informatie.

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Gebruik Microsoft Endpoint Manager om scanopties te configureren

Zie [Antimalware-beleid](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) maken en implementeren: Scaninstellingen voor meer informatie over het configureren van Microsoft Endpoint Manager (huidige vertakking).

## <a name="use-group-policy-to-configure-scanning-options"></a>Groepsbeleid gebruiken om scanopties te configureren

De instellingen voor groepsbeleid configureren die in de volgende tabel worden beschreven:

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**

3. Vouw de boom uit **Windows onderdelen > Microsoft Defender Antivirus** en  vervolgens de locatie die is opgegeven in de onderstaande tabel.

4. Dubbelklik op de **beleidsinstelling** zoals aangegeven in de onderstaande tabel en stel de optie in op de gewenste configuratie. Klik **op OK** en herhaal dit voor andere instellingen.

Omschrijving | Locatie en instelling | Standaardinstelling (indien niet geconfigureerd) | `Set-MpPreference`PowerShell-parameter of WMI-eigenschap voor `MSFT_MpPreference` klas
---|---|---|---
E-mail scannen Zie [Beperkingen voor het scannen van e-mail](#ref1)| Scannen > e-mail scannen in- | Uitgeschakeld | `-DisableEmailScanning`
[Reparse-punten scannen](/windows/win32/fileio/reparse-points) | Scannen > Het scannen van reparse-punten in- | Uitgeschakeld | Niet beschikbaar
Netwerkstations scannen | Scannen > Volledige scan uitvoeren op netwerkstations met kaart | Uitgeschakeld | `-DisableScanningMappedNetworkDrivesForFullScan`
 Archiefbestanden scannen (zoals .zip of .rar bestanden). De [uitsluitingslijst voor extensies](configure-extension-file-exclusions-microsoft-defender-antivirus.md) heeft voorrang op deze instelling. | Archiefbestanden > scannen | Ingeschakeld | `-DisableArchiveScanning`
Bestanden in het netwerk scannen | Netwerkbestanden > scannen | Uitgeschakeld | `-DisableScanningNetworkFiles`
Scanpakket uitvoerbare bestanden | Scan > scanpakket uitvoerbare bestanden | Ingeschakeld | Niet beschikbaar
Verwisselbare stations alleen scannen tijdens volledige scans | Scan > Verwisselbare stations scannen | Uitgeschakeld | `-DisableRemovableDriveScanning`
Het niveau opgeven van submappen in een archiefmap om te scannen | Scannen > De maximale diepte opgeven voor het scannen van archiefbestanden | 0 | Niet beschikbaar
 Geef de maximale CPU-belasting (als percentage) op tijdens een scan. Opmerking: Dit is geen harde limiet, maar een richtlijn voor de scan-engine om dit maximum gemiddeld niet te overschrijden. | Scan > Het maximale percentage cpu-gebruik opgeven tijdens een scan | 50 |  `-ScanAvgCPULoadFactor`
 Geef de maximale grootte (in kilobytes) op van archiefbestanden die moeten worden gescand. De **standaardwaarde, 0,** geldt geen limiet | Scannen > De maximale grootte opgeven van archiefbestanden die moeten worden gescand | Geen limiet | Niet beschikbaar
 Lage CPU-prioriteit configureren voor geplande scans | Scan > Lage CPU-prioriteit configureren voor geplande scans | Uitgeschakeld | Niet beschikbaar
 
> [!NOTE]
> Als realtimebeveiliging is ingeschakeld, worden bestanden gescand voordat ze worden toegankelijk en uitgevoerd. Het scanbereik bevat alle bestanden, inclusief bestanden op opgeslagen verwisselbare media, zoals USB-stations. Als het apparaat dat de scan voert realtimebeveiliging of on-access-beveiliging heeft ingeschakeld, bevat de scan ook netwerkaandelen.

## <a name="use-powershell-to-configure-scanning-options"></a>PowerShell gebruiken om scanopties te configureren

Zie [Beheer Microsoft Defender Antivirus met PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) en [Defender-cmdlets](/powershell/module/defender/) voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

## <a name="use-wmi-to-configure-scanning-options"></a>WMI gebruiken om scanopties te configureren

Zie voor het gebruik van WMI-klassen [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>Beperkingen voor het scannen van e-mail

Met e-mail scannen kunt u e-mailbestanden scannen die door Outlook en andere e-mail clients worden gebruikt tijdens scans op aanvraag en gepland. Ingesloten objecten in een e-mailbestand (zoals bijlagen en gearchiveerde bestanden) worden ook gescand. De volgende bestandsindelingstypen kunnen worden gescand en gesaneerd:

- DBX
- MBX
- MIME

PST-bestanden die worden gebruikt door Outlook 2003 of ouder (waarbij het archieftype is ingesteld op niet-unicode) worden ook gescand, maar Windows Defender kunnen geen bedreigingen herstellen die zijn gedetecteerd in PST-bestanden.

Als Microsoft Defender Antivirus een bedreiging in een e-mailbericht detecteert, worden de volgende gegevens aan u gegeven om u te helpen bij het identificeren van de gecompromitteerde e-mail, zodat u de bedreiging handmatig kunt herstellen:

- E-mail onderwerp
- Naam van bijlage

## <a name="related-topics"></a>Verwante onderwerpen

- [De resultaten van scans en herstel van Microsoft Defender Antivirus aanpassen, starten en controleren](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus-scans op aanvraag configureren en uitvoeren](run-scan-microsoft-defender-antivirus.md)
- [Geplande scans Microsoft Defender Antivirus configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)