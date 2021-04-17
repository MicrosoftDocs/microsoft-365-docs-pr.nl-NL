---
title: Microsoft Defender Antivirus-uitsluitingen configureren op Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows Server bevat automatische uitsluitingen, op basis van de serverrol. U kunt ook aangepaste uitsluitingen toevoegen.
keywords: uitsluitingen, server, automatische uitsluitingen, automatisch, aangepast, scans, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.openlocfilehash: 507edb980f671b2f39403cc41e540150f5e82891
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764339"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>Microsoft Defender Antivirus-uitsluitingen configureren op Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus op Windows Server 2016 en Windows Server 2019 registreren u automatisch in bepaalde uitsluitingen, zoals gedefinieerd door uw opgegeven serverrol. Deze uitsluitingen worden niet weergegeven in de standaarduitsluitingslijsten die worden weergegeven in de [Windows Security-app.](microsoft-defender-security-center-antivirus.md)

> [!NOTE]
> Automatische uitsluitingen zijn alleen van toepassing op RTP-scannen (Real-time protection). Automatische uitsluitingen worden niet nagekomen tijdens een volledige/snelle of on-demand scan.

Naast door de server gedefinieerde automatische uitsluitingen, kunt u aangepaste uitsluitingen toevoegen of verwijderen. Raadpleeg de volgende artikelen om dit te doen:
- [Uitsluitingen configureren en valideren op basis van bestandsnaam, extensie en maplocatie](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Uitsluitingen configureren en valideren voor bestanden die zijn geopend door processen](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>Een paar punten om rekening mee te houden

Houd rekening met de volgende belangrijke punten:

- Aangepaste uitsluitingen hebben voorrang op automatische uitsluitingen.
- Automatische uitsluitingen zijn alleen van toepassing op RTP-scannen (Real-time protection). Automatische uitsluitingen worden niet nagekomen tijdens een volledige/snelle of on-demand scan.
- Aangepaste en dubbele uitsluitingen komen niet in conflict met automatische uitsluitingen.
- Microsoft Defender Antivirus gebruikt de hulpprogramma's Voor het onderhouden en beheren van implementatieafbeeldingen (DISM) om te bepalen welke rollen op uw computer zijn geïnstalleerd.

## <a name="opt-out-of-automatic-exclusions"></a>Automatische uitsluitingen uitsluiten

In Windows Server 2016 en Windows Server 2019 sluiten de vooraf gedefinieerde uitsluitingen die worden geleverd door beveiligingsinformatieupdates alleen de standaardpaden voor een rol of functie uit. Als u een rol of functie in een aangepast pad hebt geïnstalleerd of als u de set uitsluitingen handmatig wilt controleren, moet u zich afkeert van de automatische uitsluitingen die worden geleverd in beveiligingsinformatie-updates. Houd er echter rekening mee dat de uitsluitingen die automatisch worden geleverd, zijn geoptimaliseerd voor Windows Server 2016- en 2019-rollen. Zie Aanbevelingen voor het definiëren van uitsluitingen voordat u uw [uitsluitingslijsten](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) definieert.

> [!WARNING]
> Het uitsluiten van automatische uitsluitingen kan negatieve gevolgen hebben voor de prestaties of leiden tot gegevenscorruptie. De uitsluitingen die automatisch worden geleverd, zijn geoptimaliseerd voor windows server 2016- en Windows Server 2019-rollen.

Omdat vooraf gedefinieerde uitsluitingen alleen standaardpaden uitsluiten **,** moet u uitsluitingen handmatig toevoegen als u NTDS en SYSVOL [](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) verplaatst naar een ander station of pad dat verschilt van het oorspronkelijke pad *.*

U kunt de automatische uitsluitingslijsten uitschakelen met groepsbeleid, PowerShell-cmdlets en WMI.

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Groepsbeleid gebruiken om de lijst met automatische uitsluitingen uit te schakelen op Windows Server 2016 en Windows Server 2019

1. Open op uw computer voor groepsbeleidsbeheer de [console Groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)). Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik vervolgens op **Bewerken.**
2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en klik vervolgens op **Beheersjablonen.**
3. Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus**  >  **Exclusions**.
4. Dubbelklik op **Automatische uitsluitingen uitschakelen** en stel de optie in op **Ingeschakeld.** Klik daarna op **OK**. 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a>PowerShell-cmdlets gebruiken om de lijst met automatische uitsluitingen uit te schakelen op Windows Server 2016 en 2019

Gebruik de volgende cmdlets:

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

Zie de volgende bronnen voor meer informatie:

- [Gebruik PowerShell-cmdlets om Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)te configureren en uit te voeren.
- [PowerShell gebruiken met Microsoft Defender Antivirus](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Windows Management Instruction (WMI) gebruiken om de lijst met automatische uitsluitingen uit te schakelen op Windows Server 2016 en Windows Server 2019

Gebruik de **methode Set** van de [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) voor de volgende eigenschappen:

```WMI
DisableAutoExclusions
```

Zie het volgende voor meer informatie en toegestane parameters:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a>Lijst met automatische uitsluitingen

De volgende secties bevatten de uitsluitingen die worden geleverd met automatische uitsluitingen van bestandspaden en bestandstypen.

### <a name="default-exclusions-for-all-roles"></a>Standaarduitsluitingen voor alle rollen

In deze sectie vindt u de standaarduitsluitingen voor alle rollen van Windows Server 2016 en 2019.

> [!NOTE]
> De standaardlocaties kunnen verschillen van wat in dit artikel wordt vermeld.

#### <a name="windows-tempedb-files"></a>Windows-bestanden met 'temp.edb'

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a>Windows Update-bestanden of Bestanden automatisch bijwerken

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a>Windows-beveiligingsbestanden

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a>Groepsbeleidsbestanden

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a>WINS-bestanden

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a>Uitsluitingen van bestandsreplicatieservice (FRS)

- Bestanden in de werkmap Bestandsreplicatieservice (FRS). De werkmap FRS wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- FRS-databaselogboekbestanden. De bestandsmap FRS-databaselogboek wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- De map FRS-staging. De map met tijdelijke bestanden wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- De map FRS vooraf installeren. Deze map wordt opgegeven door de map `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- De DFSR-database (Distributed File System Replication) en werkmappen. Deze mappen worden opgegeven met de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > Zie Automatische uitsluitingen uitsluiten voor aangepaste [locaties.](#opt-out-of-automatic-exclusions)

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a>Uitsluitingen verwerken

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a>Hyper-V-uitsluitingen

De volgende tabel bevat de uitsluitingen van het bestandstype, mapuitsluitingen en procesuitsluitingen die automatisch worden geleverd wanneer u de Hyper-V-rol installeert.

|Uitsluitingen van bestandstype |Mapuitsluitingen  | Uitsluitingen verwerken |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a>SYSVOL-bestanden

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a>Active Directory-uitsluitingen

In deze sectie worden de uitsluitingen vermeld die automatisch worden geleverd wanneer u Active Directory Domain Services installeert.

#### <a name="ntds-database-files"></a>NTDS-databasebestanden

De databasebestanden worden opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a>De AD DS-transactielogboekbestanden

De transactielogboekbestanden worden opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a>De werkmap NTDS

Deze map wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>Procesuitsluitingen voor AD DS- en AD DS-gerelateerde ondersteuningsbestanden

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a>DHCP Server-uitsluitingen

In deze sectie worden de uitsluitingen vermeld die automatisch worden geleverd wanneer u de functie DHCP Server installeert. De locaties van het DHCP Server-bestand worden opgegeven door de *parameters DatabasePath,* *DhcpLogFilePath* en *BackupDatabasePath* in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a>DNS Server-uitsluitingen

In deze sectie vindt u de uitsluitingen van bestanden en mappen en de procesuitsluitingen die automatisch worden geleverd wanneer u de dns-serverrol installeert.

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>Bestands- en mapuitsluitingen voor de rol DNS Server

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a>Uitsluitingen van processen voor de dns-serverrol

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a>Uitsluitingen van bestands- en opslagservices

In deze sectie worden de bestands- en mapuitsluitingen vermeld die automatisch worden geleverd wanneer u de rol Bestands- en opslagservices installeert. De uitsluitingen hieronder bevatten geen uitsluitingen voor de rol Clustering.

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a>Uitsluitingen van afdrukservers

In deze sectie vindt u de uitsluitingen van het bestandstype, mapuitsluitingen en de procesuitsluitingen die automatisch worden geleverd wanneer u de rol Afdrukserver installeert.

#### <a name="file-type-exclusions"></a>Uitsluitingen van bestandstype

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a>Mapuitsluitingen

Deze map wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a>Uitsluitingen verwerken

- `spoolsv.exe`

### <a name="web-server-exclusions"></a>Uitsluitingen van webservers

In deze sectie worden de mapuitsluitingen en de procesuitsluitingen vermeld die automatisch worden geleverd wanneer u de webserverrol installeert.

#### <a name="folder-exclusions"></a>Mapuitsluitingen

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a>Uitsluitingen verwerken

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Het scannen van bestanden in de map Sysvol\Sysvol of de map SYSVOL_DFSR\Sysvol uitschakelen

De huidige locatie van de map of map en alle submappen is het bestandssysteem dat het doel van de wortel van de `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` replicaset reparseert. In `Sysvol\Sysvol` de mappen worden standaard de volgende locaties `SYSVOL_DFSR\Sysvol` gebruikt:

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

Het pad naar het huidige actieve wordt verwezen door de NETLOGON-share en kan worden bepaald door de `SYSVOL` waardenaam SysVol in de volgende subsleutel: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

Sluit de volgende bestanden uit deze map en alle submappen:

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a>Uitsluitingen van Windows Server Update Services

In deze sectie worden de mapuitsluitingen vermeld die automatisch worden geleverd wanneer u de rol Windows Server Update Services (WSUS) installeert. De map WSUS wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a>Zie ook

- [Uitsluitingen configureren en valideren voor Antivirusscans van Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)
- [Uitsluitingen configureren en valideren op basis van bestandsnaam, extensie en maplocatie](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Uitsluitingen configureren en valideren voor bestanden die zijn geopend door processen](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [De resultaten van Microsoft Defender Antivirus scans en herstel aanpassen, starten en controleren](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)