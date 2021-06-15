---
title: Uitsluitingen Microsoft Defender Antivirus configureren op Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows Server bevat automatische uitsluitingen, op basis van serverrol. U kunt ook aangepaste uitsluitingen toevoegen.
keywords: uitsluitingen, server, automatische uitsluitingen, automatisch, aangepast, scans, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/10/2021
ms.openlocfilehash: 31d5c22d11a28c9604b2be3145ebd46715a6e5b3
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925513"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="3b31b-105">Uitsluitingen Microsoft Defender Antivirus configureren op Windows Server</span><span class="sxs-lookup"><span data-stu-id="3b31b-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>


<span data-ttu-id="3b31b-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3b31b-106">**Applies to:**</span></span>

- [<span data-ttu-id="3b31b-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3b31b-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3b31b-108">Microsoft Defender Antivirus op Windows Server 2016 en Windows Server 2019 wordt u automatisch ingeschreven voor bepaalde uitsluitingen, zoals gedefinieerd door uw opgegeven serverrol.</span><span class="sxs-lookup"><span data-stu-id="3b31b-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="3b31b-109">Deze uitsluitingen worden niet weergegeven in de standaarduitsluitingslijsten die worden weergegeven in de [Windows-beveiliging app](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="3b31b-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3b31b-110">Automatische uitsluitingen zijn alleen van toepassing op RTP-scannen (Real-time protection).</span><span class="sxs-lookup"><span data-stu-id="3b31b-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="3b31b-111">Automatische uitsluitingen worden niet nagekomen tijdens een volledige/snelle of on-demand scan.</span><span class="sxs-lookup"><span data-stu-id="3b31b-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="3b31b-112">Naast door de server gedefinieerde automatische uitsluitingen, kunt u aangepaste uitsluitingen toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3b31b-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="3b31b-113">Raadpleeg de volgende artikelen om dit te doen:</span><span class="sxs-lookup"><span data-stu-id="3b31b-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="3b31b-114">Uitsluitingen configureren en valideren op basis van bestandsnaam, extensie en maplocatie</span><span class="sxs-lookup"><span data-stu-id="3b31b-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3b31b-115">Uitsluitingen configureren en valideren voor bestanden die zijn geopend door processen</span><span class="sxs-lookup"><span data-stu-id="3b31b-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="3b31b-116">Een paar punten om rekening mee te houden</span><span class="sxs-lookup"><span data-stu-id="3b31b-116">A few points to keep in mind</span></span>

<span data-ttu-id="3b31b-117">Houd rekening met de volgende belangrijke punten:</span><span class="sxs-lookup"><span data-stu-id="3b31b-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="3b31b-118">Aangepaste uitsluitingen hebben voorrang op automatische uitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="3b31b-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="3b31b-119">Automatische uitsluitingen zijn alleen van toepassing op RTP-scannen (Real-time protection).</span><span class="sxs-lookup"><span data-stu-id="3b31b-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="3b31b-120">Automatische uitsluitingen worden niet nagekomen tijdens een volledige/snelle of on-demand scan.</span><span class="sxs-lookup"><span data-stu-id="3b31b-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="3b31b-121">Aangepaste en dubbele uitsluitingen komen niet in conflict met automatische uitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="3b31b-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="3b31b-122">Microsoft Defender Antivirus de hulpprogramma's Voor het onderhouden en beheren van implementatieafbeeldingen (DISM) gebruikt om te bepalen welke rollen op uw computer zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="3b31b-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="3b31b-123">Automatische uitsluitingen uitsluiten</span><span class="sxs-lookup"><span data-stu-id="3b31b-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="3b31b-124">In Windows Server 2016 en Windows Server 2019 sluiten de vooraf gedefinieerde uitsluitingen die worden geleverd door beveiligingsinformatieupdates alleen de standaardpaden voor een rol of functie uit.</span><span class="sxs-lookup"><span data-stu-id="3b31b-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="3b31b-125">Als u een rol of functie in een aangepast pad hebt geïnstalleerd of als u de set uitsluitingen handmatig wilt controleren, moet u zich afkeert van de automatische uitsluitingen die worden geleverd in beveiligingsinformatie-updates.</span><span class="sxs-lookup"><span data-stu-id="3b31b-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="3b31b-126">Houd er echter rekening mee dat de uitsluitingen die automatisch worden geleverd, zijn geoptimaliseerd voor Windows Server 2016 en 2019-rollen.</span><span class="sxs-lookup"><span data-stu-id="3b31b-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="3b31b-127">Zie Aanbevelingen voor het definiëren van uitsluitingen voordat u uw [uitsluitingslijsten](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) definieert.</span><span class="sxs-lookup"><span data-stu-id="3b31b-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="3b31b-128">Het uitsluiten van automatische uitsluitingen kan negatieve gevolgen hebben voor de prestaties of leiden tot gegevenscorruptie.</span><span class="sxs-lookup"><span data-stu-id="3b31b-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="3b31b-129">De uitsluitingen die automatisch worden geleverd, worden geoptimaliseerd voor Windows Server 2016 en Windows Server 2019-rollen.</span><span class="sxs-lookup"><span data-stu-id="3b31b-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="3b31b-130">Omdat vooraf gedefinieerde uitsluitingen alleen standaardpaden uitsluiten **,** moet u uitsluitingen handmatig toevoegen als u NTDS en SYSVOL [](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) verplaatst naar een ander station of pad dat verschilt van het oorspronkelijke pad *.*</span><span class="sxs-lookup"><span data-stu-id="3b31b-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="3b31b-131">U kunt de automatische uitsluitingslijsten uitschakelen met groepsbeleid, PowerShell-cmdlets en WMI.</span><span class="sxs-lookup"><span data-stu-id="3b31b-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="3b31b-132">Groepsbeleid gebruiken om de lijst met automatische uitsluitingen op Windows Server 2016 en Windows Server 2019 uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="3b31b-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="3b31b-133">Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="3b31b-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="3b31b-134">Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik vervolgens op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="3b31b-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="3b31b-135">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en klik vervolgens op **Beheersjablonen.**</span><span class="sxs-lookup"><span data-stu-id="3b31b-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="3b31b-136">Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Uitsluitingen.**</span><span class="sxs-lookup"><span data-stu-id="3b31b-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="3b31b-137">Dubbelklik op **Automatische uitsluitingen uitschakelen** en stel de optie in op **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="3b31b-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="3b31b-138">Klik daarna op **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b31b-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="3b31b-139">PowerShell-cmdlets gebruiken om de lijst met automatische uitsluitingen op Windows Server 2016 en 2019 uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="3b31b-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="3b31b-140">Gebruik de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="3b31b-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="3b31b-141">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="3b31b-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="3b31b-142">[Gebruik PowerShell-cmdlets om deze te configureren](use-powershell-cmdlets-microsoft-defender-antivirus.md)en Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="3b31b-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="3b31b-143">[PowerShell gebruiken met Microsoft Defender Antivirus.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="3b31b-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="3b31b-144">Gebruik Windows Management Instruction (WMI) om de lijst met automatische uitsluitingen op Windows Server 2016 en Windows Server 2019 uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="3b31b-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="3b31b-145">Gebruik de **methode Set** van de [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) voor de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="3b31b-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="3b31b-146">Zie het volgende voor meer informatie en toegestane parameters:</span><span class="sxs-lookup"><span data-stu-id="3b31b-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="3b31b-147">Windows Defender WMIv2-API's</span><span class="sxs-lookup"><span data-stu-id="3b31b-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="3b31b-148">Lijst met automatische uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3b31b-148">List of automatic exclusions</span></span>

<span data-ttu-id="3b31b-149">De volgende secties bevatten de uitsluitingen die worden geleverd met automatische uitsluitingen van bestandspaden en bestandstypen.</span><span class="sxs-lookup"><span data-stu-id="3b31b-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="3b31b-150">Standaarduitsluitingen voor alle rollen</span><span class="sxs-lookup"><span data-stu-id="3b31b-150">Default exclusions for all roles</span></span>

<span data-ttu-id="3b31b-151">In deze sectie worden de standaarduitsluitingen voor alle Windows Server 2016 en 2019 weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3b31b-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="3b31b-152">De standaardlocaties kunnen verschillen van wat in dit artikel wordt vermeld.</span><span class="sxs-lookup"><span data-stu-id="3b31b-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="3b31b-153">Windows 'temp.edb'-bestanden</span><span class="sxs-lookup"><span data-stu-id="3b31b-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="3b31b-154">Windows Bestanden bijwerken of Bestanden automatisch bijwerken</span><span class="sxs-lookup"><span data-stu-id="3b31b-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="3b31b-155">Windows-beveiliging bestanden</span><span class="sxs-lookup"><span data-stu-id="3b31b-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="3b31b-156">Groepsbeleidsbestanden</span><span class="sxs-lookup"><span data-stu-id="3b31b-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="3b31b-157">WINS-bestanden</span><span class="sxs-lookup"><span data-stu-id="3b31b-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="3b31b-158">Uitsluitingen van bestandsreplicatieservice (FRS)</span><span class="sxs-lookup"><span data-stu-id="3b31b-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="3b31b-159">Bestanden in de werkmap Bestandsreplicatieservice (FRS).</span><span class="sxs-lookup"><span data-stu-id="3b31b-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="3b31b-160">De werkmap FRS wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="3b31b-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="3b31b-161">FRS-databaselogboekbestanden.</span><span class="sxs-lookup"><span data-stu-id="3b31b-161">FRS Database log files.</span></span> <span data-ttu-id="3b31b-162">De bestandsmap FRS-databaselogboek wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="3b31b-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="3b31b-163">De map FRS-staging.</span><span class="sxs-lookup"><span data-stu-id="3b31b-163">The FRS staging folder.</span></span> <span data-ttu-id="3b31b-164">De map met tijdelijke bestanden wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="3b31b-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="3b31b-165">De map FRS vooraf installeren.</span><span class="sxs-lookup"><span data-stu-id="3b31b-165">The FRS preinstall folder.</span></span> <span data-ttu-id="3b31b-166">Deze map wordt opgegeven door de map `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="3b31b-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="3b31b-167">De DFSR-database (Distributed File System Replication) en werkmappen.</span><span class="sxs-lookup"><span data-stu-id="3b31b-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="3b31b-168">Deze mappen worden opgegeven met de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="3b31b-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="3b31b-169">Zie Automatische uitsluitingen uitsluiten voor aangepaste [locaties.](#opt-out-of-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="3b31b-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

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

#### <a name="process-exclusions"></a><span data-ttu-id="3b31b-170">Uitsluitingen verwerken</span><span class="sxs-lookup"><span data-stu-id="3b31b-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="3b31b-171">Hyper-V-uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3b31b-171">Hyper-V exclusions</span></span>

<span data-ttu-id="3b31b-172">De volgende tabel bevat de uitsluitingen van het bestandstype, mapuitsluitingen en procesuitsluitingen die automatisch worden geleverd wanneer u de Hyper-V-rol installeert.</span><span class="sxs-lookup"><span data-stu-id="3b31b-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="3b31b-173">Uitsluitingen van bestandstype</span><span class="sxs-lookup"><span data-stu-id="3b31b-173">File type exclusions</span></span> |<span data-ttu-id="3b31b-174">Mapuitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3b31b-174">Folder exclusions</span></span>  | <span data-ttu-id="3b31b-175">Uitsluitingen verwerken</span><span class="sxs-lookup"><span data-stu-id="3b31b-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="3b31b-176">SYSVOL-bestanden</span><span class="sxs-lookup"><span data-stu-id="3b31b-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="3b31b-177">Active Directory-uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3b31b-177">Active Directory exclusions</span></span>

<span data-ttu-id="3b31b-178">In deze sectie worden de uitsluitingen vermeld die automatisch worden geleverd wanneer u Active Directory Domain Services installeert.</span><span class="sxs-lookup"><span data-stu-id="3b31b-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="3b31b-179">NTDS-databasebestanden</span><span class="sxs-lookup"><span data-stu-id="3b31b-179">NTDS database files</span></span>

<span data-ttu-id="3b31b-180">De databasebestanden worden opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="3b31b-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="3b31b-181">De AD DS-transactielogboekbestanden</span><span class="sxs-lookup"><span data-stu-id="3b31b-181">The AD DS transaction log files</span></span>

<span data-ttu-id="3b31b-182">De transactielogboekbestanden worden opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="3b31b-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="3b31b-183">De werkmap NTDS</span><span class="sxs-lookup"><span data-stu-id="3b31b-183">The NTDS working folder</span></span>

<span data-ttu-id="3b31b-184">Deze map wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="3b31b-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="3b31b-185">Procesuitsluitingen voor AD DS- en AD DS-gerelateerde ondersteuningsbestanden</span><span class="sxs-lookup"><span data-stu-id="3b31b-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="3b31b-186">DHCP Server-uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3b31b-186">DHCP Server exclusions</span></span>

<span data-ttu-id="3b31b-187">In deze sectie worden de uitsluitingen vermeld die automatisch worden geleverd wanneer u de functie DHCP Server installeert.</span><span class="sxs-lookup"><span data-stu-id="3b31b-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="3b31b-188">De locaties van het DHCP Server-bestand worden opgegeven door de *parameters DatabasePath,* *DhcpLogFilePath* en *BackupDatabasePath* in de registersleutel `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="3b31b-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="3b31b-189">DNS Server-uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3b31b-189">DNS Server exclusions</span></span>

<span data-ttu-id="3b31b-190">In deze sectie vindt u de uitsluitingen van bestanden en mappen en de procesuitsluitingen die automatisch worden geleverd wanneer u de dns-serverrol installeert.</span><span class="sxs-lookup"><span data-stu-id="3b31b-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="3b31b-191">Bestands- en mapuitsluitingen voor de rol DNS Server</span><span class="sxs-lookup"><span data-stu-id="3b31b-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="3b31b-192">Uitsluitingen van processen voor de dns-serverrol</span><span class="sxs-lookup"><span data-stu-id="3b31b-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="3b31b-193">Uitsluitingen van Storage services</span><span class="sxs-lookup"><span data-stu-id="3b31b-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="3b31b-194">In deze sectie worden de bestands- en mapuitsluitingen vermeld die automatisch worden bezorgd wanneer u de rol Bestand en Storage Services installeert.</span><span class="sxs-lookup"><span data-stu-id="3b31b-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="3b31b-195">De uitsluitingen hieronder bevatten geen uitsluitingen voor de rol Clustering.</span><span class="sxs-lookup"><span data-stu-id="3b31b-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="3b31b-196">Uitsluitingen van afdrukservers</span><span class="sxs-lookup"><span data-stu-id="3b31b-196">Print Server exclusions</span></span>

<span data-ttu-id="3b31b-197">In deze sectie vindt u de uitsluitingen van het bestandstype, mapuitsluitingen en de procesuitsluitingen die automatisch worden geleverd wanneer u de rol Afdrukserver installeert.</span><span class="sxs-lookup"><span data-stu-id="3b31b-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="3b31b-198">Uitsluitingen van bestandstype</span><span class="sxs-lookup"><span data-stu-id="3b31b-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="3b31b-199">Mapuitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3b31b-199">Folder exclusions</span></span>

<span data-ttu-id="3b31b-200">Deze map wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="3b31b-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="3b31b-201">Uitsluitingen verwerken</span><span class="sxs-lookup"><span data-stu-id="3b31b-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="3b31b-202">Uitsluitingen van webservers</span><span class="sxs-lookup"><span data-stu-id="3b31b-202">Web Server exclusions</span></span>

<span data-ttu-id="3b31b-203">In deze sectie worden de mapuitsluitingen en de procesuitsluitingen vermeld die automatisch worden geleverd wanneer u de webserverrol installeert.</span><span class="sxs-lookup"><span data-stu-id="3b31b-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="3b31b-204">Mapuitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3b31b-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="3b31b-205">Uitsluitingen verwerken</span><span class="sxs-lookup"><span data-stu-id="3b31b-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="3b31b-206">Het scannen van bestanden in de map Sysvol\Sysvol of de map SYSVOL_DFSR\Sysvol uitschakelen</span><span class="sxs-lookup"><span data-stu-id="3b31b-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="3b31b-207">De huidige locatie van de map of map en alle submappen is het bestandssysteem dat het doel van de wortel van de `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` replicaset reparseert.</span><span class="sxs-lookup"><span data-stu-id="3b31b-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="3b31b-208">In `Sysvol\Sysvol` de mappen worden standaard de volgende locaties `SYSVOL_DFSR\Sysvol` gebruikt:</span><span class="sxs-lookup"><span data-stu-id="3b31b-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="3b31b-209">Het pad naar het huidige actieve wordt verwezen door de NETLOGON-share en kan worden bepaald door de `SYSVOL` waardenaam SysVol in de volgende subsleutel: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="3b31b-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="3b31b-210">Sluit de volgende bestanden uit deze map en alle submappen:</span><span class="sxs-lookup"><span data-stu-id="3b31b-210">Exclude the following files from this folder and all its subfolders:</span></span>

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

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="3b31b-211">Windows Server Update Services uitsluitingen</span><span class="sxs-lookup"><span data-stu-id="3b31b-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="3b31b-212">In deze sectie worden de mapuitsluitingen vermeld die automatisch worden geleverd wanneer u de Windows Server Update Services (WSUS) installeert.</span><span class="sxs-lookup"><span data-stu-id="3b31b-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="3b31b-213">De map WSUS wordt opgegeven in de registersleutel `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="3b31b-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="3b31b-214">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3b31b-214">See also</span></span>

- [<span data-ttu-id="3b31b-215">Uitsluitingen configureren en valideren voor Microsoft Defender Antivirus scans</span><span class="sxs-lookup"><span data-stu-id="3b31b-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3b31b-216">Uitsluitingen configureren en valideren op basis van bestandsnaam, extensie en maplocatie</span><span class="sxs-lookup"><span data-stu-id="3b31b-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3b31b-217">Uitsluitingen configureren en valideren voor bestanden die zijn geopend door processen</span><span class="sxs-lookup"><span data-stu-id="3b31b-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3b31b-218">Veelvoorkomende fouten bij het definiëren van uitsluitingen voorkomen</span><span class="sxs-lookup"><span data-stu-id="3b31b-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3b31b-219">De resultaten van scans en herstel van Microsoft Defender Antivirus aanpassen, starten en controleren</span><span class="sxs-lookup"><span data-stu-id="3b31b-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3b31b-220">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="3b31b-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
