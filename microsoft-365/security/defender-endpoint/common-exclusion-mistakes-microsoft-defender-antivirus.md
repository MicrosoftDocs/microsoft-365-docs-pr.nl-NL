---
title: Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen
description: Vermijd veelvoorkomende fouten bij het definiëren van uitsluitingen voor Microsoft Defender Antivirus-scans.
keywords: uitsluitingen, bestanden, extensie, bestandstype, mapnaam, bestandsnaam, scans
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: eb3ac89eb05b39ff3337aa8e9c5ead1c308fbefb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764913"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

U kunt een uitsluitingslijst definiëren voor items die u niet wilt dat Microsoft Defender Antivirus wordt gescand. Dergelijke uitgesloten items kunnen bedreigingen bevatten die uw apparaat kwetsbaar maken. 

In dit artikel wordt een veelvoorkomende fout beschreven die u moet vermijden bij het definiëren van uitsluitingen. 

Zie Aanbevelingen voor het definiëren van uitsluitingslijsten voordat u [uitsluitingslijsten definieert.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)

## <a name="excluding-certain-trusted-items"></a>Bepaalde vertrouwde items uitsluiten

Bepaalde bestanden, bestandstypen, mappen of processen mogen niet worden uitgesloten van scannen, ook al vertrouwt u erop dat ze niet schadelijk zijn. 

Geen uitsluitingen definiëren voor de maplocaties, bestandsextensies en processen die in de volgende tabel worden vermeld:

| Maplocaties | Bestandsextensies | Processen |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`[1] <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`[2] <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> U kunt ervoor kiezen om bestandstypen uit te sluiten, zoals , of als uw omgeving een `.gif` `.jpg` `.jpeg` moderne, up-to-date software heeft met een strikt updatebeleid om eventuele beveiligingslekken `.png` te behandelen.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Alleen de bestandsnaam in de uitsluitingslijst gebruiken

Een malware kan dezelfde naam hebben als het bestand dat u vertrouwt en wilt uitsluiten van scannen. Gebruik daarom een volledig gekwalificeerd pad naar het bestand dat u wilt uitsluiten in plaats van alleen de bestandsnaam te gebruiken om te voorkomen dat een potentiële malware wordt gescand. Als u bijvoorbeeld het scannen wilt uitsluiten, gebruikt u het volledige pad naar `Filename.exe` het bestand, zoals `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Eén uitsluitingslijst gebruiken voor meerdere serverwerkbelastingen

Gebruik geen enkele uitsluitingslijst om uitsluitingen voor meerdere serverbelastingen te definiëren. Splits de uitsluitingen voor verschillende toepassings- of servicewerkbelastingen in meerdere uitsluitingslijsten. De uitsluitingslijst voor uw IIS Server-werkbelasting moet bijvoorbeeld verschillen van de uitsluitingslijst voor uw SQL Server-werkbelasting.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Onjuiste omgevingsvariabelen gebruiken als jokertekens in de lijsten met bestandsnaam en mappad of extensieuitsluiting

Microsoft Defender Antivirus Service wordt uitgevoerd in systeemcontext met behulp van het LocalSystem-account, wat betekent dat deze informatie krijgt van de variabele systeemomgeving en niet van de variabele voor de gebruikersomgeving. Het gebruik van omgevingsvariabelen als jokerteken in uitsluitingslijsten is beperkt tot systeemvariabelen en die van toepassing op processen die als NT AUTHORITY\SYSTEM-account worden uitgevoerd. Gebruik daarom geen variabelen in de gebruikersomgeving als jokertekens bij het toevoegen van Microsoft Defender Antivirus-map en procesuitsluitingen. Zie de tabel onder [Systeemomgevingvariabelen](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) voor een volledige lijst met systeemomgevingvariabelen.

Zie [Jokertekens gebruiken in de](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) lijst met uitsluitingslijsten voor bestandsnaam en mappen of extensies voor informatie over het gebruik van jokertekens in uitsluitingslijsten.

## <a name="related-articles"></a>Verwante artikelen

- [Uitsluitingen configureren en valideren in Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md)
- [Uitsluitingen configureren en valideren op basis van bestandsextensie en maplocatie](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Uitsluitingen configureren en valideren voor bestanden die zijn geopend door processen](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus-uitsluitingen configureren op Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
