---
title: Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen
description: Vermijd veelvoorkomende fouten bij het definiëren van uitsluitingen voor Microsoft Defender Antivirus scans.
keywords: uitsluitingen, bestanden, extensie, bestandstype, mapnaam, bestandsnaam, scans
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 05/17/2021
ms.openlocfilehash: d10343538c995534878196cc57092c37fd2dcf7b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538061"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

U kunt een uitsluitingslijst definiëren voor items die u niet wilt Microsoft Defender Antivirus scannen. Dergelijke uitgesloten items kunnen bedreigingen bevatten die uw apparaat kwetsbaar maken. 

In dit artikel wordt een veelvoorkomende fout beschreven die u moet vermijden bij het definiëren van uitsluitingen. 

Voordat u uw uitsluitingslijsten definieert, [Aanbevelingen voor het definiëren van uitsluitingen.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)

## <a name="excluding-certain-trusted-items"></a>Bepaalde vertrouwde items uitsluiten

Bepaalde bestanden, bestandstypen, mappen of processen mogen niet worden uitgesloten van scannen, ook al vertrouwt u erop dat ze niet schadelijk zijn. 

Definieer geen uitsluitingen voor de maplocaties, bestandsextensies en processen die in de volgende secties worden vermeld:
- Maplocaties
- Bestandsextensies
- Processen

### <a name="folder-locations"></a>Maplocaties

Definieer over het algemeen geen uitsluitingen voor de volgende maplocaties:

`%systemdrive%` 

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java` 

`%ProgramFiles%\Contoso\` 

`C:\Program Files\Contoso\` 

`%ProgramFiles(x86)%\Contoso\` 

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Let op de volgende uitzondering voor SharePoint**: Sluit dit uit wanneer u antivirusbeveiliging op bestandsniveau gebruikt in `C:\Users\ServiceAccount\AppData\Local\Temp` [SharePoint.](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Let op de volgende uitzondering voor SharePoint**: Sluit dit uit wanneer u antivirusbeveiliging op bestandsniveau gebruikt in `C:\Users\Default\AppData\Local\Temp` [SharePoint.](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

### <a name="file-extensions"></a>Bestandsextensies

Definieer over het algemeen geen uitsluitingen voor de volgende bestandsextensies:

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com` 

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a>Processen 

Definieer over het algemeen geen uitsluitingen voor de volgende processen:

`AcroRd32.exe`  

`bitsadmin.exe`  

`excel.exe`  

`iexplore.exe`  

`java.exe`  

`outlook.exe`  

`psexec.exe`  

`powerpnt.exe`  

`powershell.exe`  

`schtasks.exe`

`svchost.exe` 

`wmic.exe`  

`winword.exe`  

`wuauclt.exe`  

`addinprocess.exe`  

`addinprocess32.exe`  

`addinutil.exe`  

`bash.exe`  

`bginfo.exe` 

`cdb.exe`  

`csi.exe`  

`dbghost.exe`  

`dbgsvc.exe`  

`dnx.exe`  

`fsi.exe`  

`fsiAnyCpu.exe`  

`kd.exe`  

`ntkd.exe`  

`lxssmanager.dll`  

`msbuild.exe` 

`mshta.exe`  

`ntsd.exe`  

`rcsi.exe`  

`system.management.automation.dll`  

`windbg.exe`

> [!NOTE]
> U kunt ervoor kiezen om bestandstypen uit te sluiten, zoals , of als uw omgeving een `.gif` `.jpg` `.jpeg` moderne, up-to-date software heeft met een strikt updatebeleid om eventuele beveiligingslekken `.png` te behandelen.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Alleen de bestandsnaam in de uitsluitingslijst gebruiken

Een malware kan dezelfde naam hebben als het bestand dat u vertrouwt en wilt uitsluiten van scannen. Gebruik daarom een volledig gekwalificeerd pad naar het bestand dat u wilt uitsluiten in plaats van alleen de bestandsnaam te gebruiken om te voorkomen dat een potentiële malware wordt gescand. Als u bijvoorbeeld het scannen wilt uitsluiten, gebruikt u het volledige pad naar `Filename.exe` het bestand, zoals `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Eén uitsluitingslijst gebruiken voor meerdere serverwerkbelastingen

Gebruik geen enkele uitsluitingslijst om uitsluitingen voor meerdere serverbelastingen te definiëren. Splits de uitsluitingen voor verschillende toepassings- of servicewerkbelastingen in meerdere uitsluitingslijsten. De uitsluitingslijst voor uw IIS Server-werkbelasting moet bijvoorbeeld verschillen van de uitsluitingslijst voor uw SQL Server werkbelasting.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Onjuiste omgevingsvariabelen gebruiken als jokertekens in de lijsten met bestandsnaam en mappad of extensieuitsluiting

Microsoft Defender Antivirus Service wordt uitgevoerd in systeemcontext met behulp van het LocalSystem-account, wat betekent dat de service informatie krijgt van de systeemomgevingsvariabele en niet van de variabele voor de gebruikersomgeving. Het gebruik van omgevingsvariabelen als jokerteken in uitsluitingslijsten is beperkt tot systeemvariabelen en die van toepassing op processen die als NT AUTHORITY\SYSTEM-account worden uitgevoerd. Gebruik daarom geen variabelen in de gebruikersomgeving als jokertekens bij het toevoegen van Microsoft Defender Antivirus map en procesuitsluitingen. Zie de tabel onder [Systeemomgevingvariabelen](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) voor een volledige lijst met systeemomgevingvariabelen.

Zie [Jokertekens gebruiken in de](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) lijst met uitsluitingslijsten voor bestandsnaam en mappen of extensies voor informatie over het gebruik van jokertekens in uitsluitingslijsten.

## <a name="related-articles"></a>Aanverwante artikelen

- [Uitsluitingen configureren en valideren in Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md)
- [Uitsluitingen configureren en valideren op basis van bestandsextensie en maplocatie](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Uitsluitingen configureren en valideren voor bestanden die zijn geopend door processen](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Uitsluitingen Microsoft Defender Antivirus configureren op Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
