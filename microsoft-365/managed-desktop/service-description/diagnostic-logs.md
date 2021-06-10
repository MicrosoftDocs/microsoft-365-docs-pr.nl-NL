---
title: Diagnostische logboeken
description: Logboeken die kunnen worden verzameld van apparaten tijdens het oplossen van problemen en hoe ze worden opgeslagen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272889"
---
# <a name="diagnostic-logs"></a><span data-ttu-id="5c472-104">Diagnostische logboeken</span><span class="sxs-lookup"><span data-stu-id="5c472-104">Diagnostic logs</span></span>

<span data-ttu-id="5c472-105">Wanneer we een probleem oplossen op een apparaat dat wordt beheerd door Microsoft Managed Desktop, of u nu een apparaat hebt gerapporteerd of een apparaat dat door onze service is geïdentificeerd, moeten we mogelijk bepaalde diagnostische logboeken van het apparaat verzamelen zonder tussenkomst van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="5c472-105">When we troubleshoot an issue on a device managed by Microsoft Managed Desktop, whether one you've reported or one identified by our service, we might have to collect certain diagnostic logs from the device without intervention from the user.</span></span> <span data-ttu-id="5c472-106">We verzamelen geen door de gebruiker gegenereerde inhoud of informatie uit gebruikers directories.</span><span class="sxs-lookup"><span data-stu-id="5c472-106">We don't collect any user-generated content or information from user directories.</span></span> <span data-ttu-id="5c472-107">We verzamelen alleen diagnostische en logboekgegevens die betrekking hebben op de status en status van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5c472-107">We only collect diagnostic and log data that concerns device health and status.</span></span>

<span data-ttu-id="5c472-108">We slaan verzamelde logboeken op voor 28 dagen en verwijderen ze vervolgens.</span><span class="sxs-lookup"><span data-stu-id="5c472-108">We store any collected logs for 28 days, and then delete them.</span></span> <span data-ttu-id="5c472-109">Alle logboeken die vanaf een apparaat worden verzameld, worden verwerkt volgens onze standaarden [voor gegevensafhandeling.](privacy-personal-data.md)</span><span class="sxs-lookup"><span data-stu-id="5c472-109">We process any logs collected from a device following our [data handling standards](privacy-personal-data.md).</span></span>

## <a name="data-collected"></a><span data-ttu-id="5c472-110">Verzamelde gegevens</span><span class="sxs-lookup"><span data-stu-id="5c472-110">Data collected</span></span>

<span data-ttu-id="5c472-111">Deze lijst bevat alle mappen, gebeurtenislogboeken, uitvoerbare bestanden of registerlocaties waaruit Microsoft Managed Desktop diagnostische logboeken kunnen verzamelen.</span><span class="sxs-lookup"><span data-stu-id="5c472-111">This list includes all the folders, event logs, executables, or registry locations that Microsoft Managed Desktop might collect diagnostic logs from.</span></span> <span data-ttu-id="5c472-112">De werkelijke verzamelde gegevens zijn een subset van deze lijst en zijn afhankelijk van het geïdentificeerde probleem.</span><span class="sxs-lookup"><span data-stu-id="5c472-112">The actual data collected will be a subset of this list and depends on the identified issue.</span></span>

### <a name="registry-keys"></a><span data-ttu-id="5c472-113">Registersleutels</span><span class="sxs-lookup"><span data-stu-id="5c472-113">Registry keys</span></span>

- <span data-ttu-id="5c472-114">HKLM \\ SYSTEM \\ CurrentControlSet \\ Services</span><span class="sxs-lookup"><span data-stu-id="5c472-114">HKLM\\SYSTEM\\CurrentControlSet\\Services</span></span>
- <span data-ttu-id="5c472-115">HKLM \\ SOFTWARE \\ Microsoft \\ Surface</span><span class="sxs-lookup"><span data-stu-id="5c472-115">HKLM\\SOFTWARE\\Microsoft\\Surface</span></span>
- <span data-ttu-id="5c472-116">HKLM \\ SOFTWARE Policies Microsoft Windows \\ \\ \\ \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="5c472-116">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate</span></span>
- <span data-ttu-id="5c472-117">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages</span><span class="sxs-lookup"><span data-stu-id="5c472-117">HKLM\\SYSTEM\\CurrentControlSet\\Control\\MUI\\UILanguages</span></span>
- <span data-ttu-id="5c472-118">\\HKLM-softwarebeleid \\ \\ Microsoft \\ WindowsStore</span><span class="sxs-lookup"><span data-stu-id="5c472-118">HKLM\\Software\\Policies\\Microsoft\\WindowsStore</span></span>
- <span data-ttu-id="5c472-119">HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="5c472-119">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate</span></span>
- <span data-ttu-id="5c472-120">HKLM \\ SOFTWARE Microsoft Windows \\ \\ NT \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="5c472-120">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="5c472-121">HKLM \\ SOFTWARE Microsoft Windows \\ \\ NT \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="5c472-121">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="5c472-122">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ AppModel</span><span class="sxs-lookup"><span data-stu-id="5c472-122">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>
- <span data-ttu-id="5c472-123">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources</span><span class="sxs-lookup"><span data-stu-id="5c472-123">HKLM\\SYSTEM\\CurrentControlSet\\Control\\FirmwareResources</span></span>
- <span data-ttu-id="5c472-124">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost</span><span class="sxs-lookup"><span data-stu-id="5c472-124">HKLM\\SOFTWARE\\Microsoft\\WindowsSelfhost</span></span>
- <span data-ttu-id="5c472-125">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="5c472-125">HKLM\\SOFTWARE\\Microsoft\\WindowsUpdate</span></span>
- <span data-ttu-id="5c472-126">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Appx</span><span class="sxs-lookup"><span data-stu-id="5c472-126">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx</span></span>
- <span data-ttu-id="5c472-127">HKLM \\ SOFTWARE Microsoft Windows \\ \\ NT \\ CurrentVersion \\ Superfetch</span><span class="sxs-lookup"><span data-stu-id="5c472-127">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch</span></span>
- <span data-ttu-id="5c472-128">HKLM \\ SYSTEM \\ Setup</span><span class="sxs-lookup"><span data-stu-id="5c472-128">HKLM\\SYSTEM\\Setup</span></span>
- <span data-ttu-id="5c472-129">HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="5c472-129">HKLM\\Software\\Microsoft\\IntuneManagementExtension</span></span>
- <span data-ttu-id="5c472-130">HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot</span><span class="sxs-lookup"><span data-stu-id="5c472-130">HKLM\\SOFTWARE\\Microsoft\\SystemCertificates\\AuthRoot</span></span>
- <span data-ttu-id="5c472-131">HKLM \\ SOFTWARE Microsoft Windows Advanced Threat \\ \\ Protection</span><span class="sxs-lookup"><span data-stu-id="5c472-131">HKLM\\SOFTWARE\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="5c472-132">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Authentication \\ \\ LogonUI</span><span class="sxs-lookup"><span data-stu-id="5c472-132">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI</span></span>
- <span data-ttu-id="5c472-133">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Internet \\ Instellingen</span><span class="sxs-lookup"><span data-stu-id="5c472-133">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>
- <span data-ttu-id="5c472-134">HKLM \\ Software Microsoft Windows \\ \\ \\ CurrentVersion \\ Uninstall</span><span class="sxs-lookup"><span data-stu-id="5c472-134">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="5c472-135">\\HKLM-softwarebeleid \\</span><span class="sxs-lookup"><span data-stu-id="5c472-135">HKLM\\Software\\Policies</span></span>
- <span data-ttu-id="5c472-136">HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Cryptography \\ Configuration \\ SSL</span><span class="sxs-lookup"><span data-stu-id="5c472-136">HKLM\\SOFTWARE\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL</span></span>
- <span data-ttu-id="5c472-137">HKLM \\ SOFTWARE Policies Microsoft Windows Advanced Threat \\ \\ \\ Protection</span><span class="sxs-lookup"><span data-stu-id="5c472-137">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="5c472-138">HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Uninstall</span><span class="sxs-lookup"><span data-stu-id="5c472-138">HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="5c472-139">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL</span><span class="sxs-lookup"><span data-stu-id="5c472-139">HKLM\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL</span></span>

### <a name="commands"></a><span data-ttu-id="5c472-140">Opdrachten</span><span class="sxs-lookup"><span data-stu-id="5c472-140">Commands</span></span>

- <span data-ttu-id="5c472-141">%programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles</span><span class="sxs-lookup"><span data-stu-id="5c472-141">%programfiles%\\windows defender\\mpcmdrun.exe -GetFiles</span></span>
- <span data-ttu-id="5c472-142">%windir% \\ system32 \\certutil.exe -store</span><span class="sxs-lookup"><span data-stu-id="5c472-142">%windir%\\system32\\certutil.exe -store</span></span>
- <span data-ttu-id="5c472-143">%windir% \\ system32 \\certutil.exe -store -user my</span><span class="sxs-lookup"><span data-stu-id="5c472-143">%windir%\\system32\\certutil.exe -store -user my</span></span>
- <span data-ttu-id="5c472-144">%windir% \\ system32 \\Dsregcmd.exe /status</span><span class="sxs-lookup"><span data-stu-id="5c472-144">%windir%\\system32\\Dsregcmd.exe /status</span></span>
- <span data-ttu-id="5c472-145">%windir% \\ system32 \\ipconfig.exe /all</span><span class="sxs-lookup"><span data-stu-id="5c472-145">%windir%\\system32\\ipconfig.exe /all</span></span>
- <span data-ttu-id="5c472-146">%windir% \\ system32 \\ipconfig.exe /displaydns</span><span class="sxs-lookup"><span data-stu-id="5c472-146">%windir%\\system32\\ipconfig.exe /displaydns</span></span>
- <span data-ttu-id="5c472-147">%windir% \\ system32 \\mdmdiagnosticstool.exe</span><span class="sxs-lookup"><span data-stu-id="5c472-147">%windir%\\system32\\mdmdiagnosticstool.exe</span></span>
- <span data-ttu-id="5c472-148">%windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log</span><span class="sxs-lookup"><span data-stu-id="5c472-148">%windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnostics\\msinfo32.log</span></span>
- <span data-ttu-id="5c472-149">%windir% \\ system32 \\netsh.exe advfirewall show allprofiles</span><span class="sxs-lookup"><span data-stu-id="5c472-149">%windir%\\system32\\netsh.exe advfirewall show allprofiles</span></span>
- <span data-ttu-id="5c472-150">%windir% \\ system32 \\netsh.exe advfirewall show global</span><span class="sxs-lookup"><span data-stu-id="5c472-150">%windir%\\system32\\netsh.exe advfirewall show global</span></span>
- <span data-ttu-id="5c472-151">%windir% \\ system32 \\netsh.exe lan show profiles</span><span class="sxs-lookup"><span data-stu-id="5c472-151">%windir%\\system32\\netsh.exe lan show profiles</span></span>
- <span data-ttu-id="5c472-152">%windir% \\ system32 \\netsh.exe winhttp show proxy</span><span class="sxs-lookup"><span data-stu-id="5c472-152">%windir%\\system32\\netsh.exe winhttp show proxy</span></span>
- <span data-ttu-id="5c472-153">%windir% \\ system32 \\netsh.exe wlan show profiles</span><span class="sxs-lookup"><span data-stu-id="5c472-153">%windir%\\system32\\netsh.exe wlan show profiles</span></span>
- <span data-ttu-id="5c472-154">%windir% \\ system32 \\netsh.exe wlan show wlanreport</span><span class="sxs-lookup"><span data-stu-id="5c472-154">%windir%\\system32\\netsh.exe wlan show wlanreport</span></span>
- <span data-ttu-id="5c472-155">%windir% \\ system32 \\ping.exe -n 50 localhost</span><span class="sxs-lookup"><span data-stu-id="5c472-155">%windir%\\system32\\ping.exe -n 50 localhost</span></span>
- <span data-ttu-id="5c472-156">%windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html</span><span class="sxs-lookup"><span data-stu-id="5c472-156">%windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnostics\\battery-report.html</span></span>
- <span data-ttu-id="5c472-157">%windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html</span><span class="sxs-lookup"><span data-stu-id="5c472-157">%windir%\\system32\\powercfg.exe /energy /output %temp%\\MDMDiagnostics\\energy-report.html</span></span>
- <span data-ttu-id="5c472-158">bitsadmin /list /allusers /verbose</span><span class="sxs-lookup"><span data-stu-id="5c472-158">bitsadmin /list /allusers /verbose</span></span>
- <span data-ttu-id="5c472-159">fltMC.exe</span><span class="sxs-lookup"><span data-stu-id="5c472-159">fltMC.exe</span></span>
- <span data-ttu-id="5c472-160">bcdedit /enum all /v</span><span class="sxs-lookup"><span data-stu-id="5c472-160">bcdedit /enum all /v</span></span>
- <span data-ttu-id="5c472-161">manage-bde -protectors -get</span><span class="sxs-lookup"><span data-stu-id="5c472-161">manage-bde -protectors -get</span></span>
- <span data-ttu-id="5c472-162">Windows PowerShell opdrachten:</span><span class="sxs-lookup"><span data-stu-id="5c472-162">Windows PowerShell commands:</span></span>
    - <span data-ttu-id="5c472-163">Get-appxpackage -allusers</span><span class="sxs-lookup"><span data-stu-id="5c472-163">Get-appxpackage -allusers</span></span>
    - <span data-ttu-id="5c472-164">Get-appxpackage -packagetype bundle</span><span class="sxs-lookup"><span data-stu-id="5c472-164">Get-appxpackage -packagetype bundle</span></span>
    - <span data-ttu-id="5c472-165">Get-Service wuauserv</span><span class="sxs-lookup"><span data-stu-id="5c472-165">Get-Service wuauserv</span></span>
    - <span data-ttu-id="5c472-166">Get-NetFirewallRule</span><span class="sxs-lookup"><span data-stu-id="5c472-166">Get-NetFirewallRule</span></span>
    - <span data-ttu-id="5c472-167">Get-WmiObject -Class \_ win32-product</span><span class="sxs-lookup"><span data-stu-id="5c472-167">Get-WmiObject -Class win32\_product</span></span>
    - <span data-ttu-id="5c472-168">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="5c472-168">Get-ComputerInfo</span></span>
    - <span data-ttu-id="5c472-169">Get-Service</span><span class="sxs-lookup"><span data-stu-id="5c472-169">Get-Service</span></span>
    - <span data-ttu-id="5c472-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="5c472-170">Get-Process</span></span>
    - <span data-ttu-id="5c472-171">Get-WmiObject Win32 \_ PnPSignedDriver</span><span class="sxs-lookup"><span data-stu-id="5c472-171">Get-WmiObject Win32\_PnPSignedDriver</span></span>

### <a name="event-logs"></a><span data-ttu-id="5c472-172">Gebeurtenislogboeken</span><span class="sxs-lookup"><span data-stu-id="5c472-172">Event logs</span></span>

- <span data-ttu-id="5c472-173">Toepassing</span><span class="sxs-lookup"><span data-stu-id="5c472-173">Application</span></span>
- <span data-ttu-id="5c472-174">Microsoft-Windows-AppLocker/EXE en DLL</span><span class="sxs-lookup"><span data-stu-id="5c472-174">Microsoft-Windows-AppLocker/EXE and DLL</span></span>
- <span data-ttu-id="5c472-175">Microsoft-Windows-AppLocker/MSI en Script</span><span class="sxs-lookup"><span data-stu-id="5c472-175">Microsoft-Windows-AppLocker/MSI and Script</span></span>
- <span data-ttu-id="5c472-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span><span class="sxs-lookup"><span data-stu-id="5c472-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span></span>
- <span data-ttu-id="5c472-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span><span class="sxs-lookup"><span data-stu-id="5c472-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span></span>
- <span data-ttu-id="5c472-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span><span class="sxs-lookup"><span data-stu-id="5c472-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span></span>
- <span data-ttu-id="5c472-179">Microsoft-Windows-SENSE/Operational</span><span class="sxs-lookup"><span data-stu-id="5c472-179">Microsoft-Windows-SENSE/Operational</span></span>
- <span data-ttu-id="5c472-180">Microsoft-Windows-SenseIR/Operational</span><span class="sxs-lookup"><span data-stu-id="5c472-180">Microsoft-Windows-SenseIR/Operational</span></span>
- <span data-ttu-id="5c472-181">Configuratie</span><span class="sxs-lookup"><span data-stu-id="5c472-181">Setup</span></span>
- <span data-ttu-id="5c472-182">Systeem</span><span class="sxs-lookup"><span data-stu-id="5c472-182">System</span></span>

### <a name="files"></a><span data-ttu-id="5c472-183">Bestanden</span><span class="sxs-lookup"><span data-stu-id="5c472-183">Files</span></span>

- <span data-ttu-id="5c472-184">%ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ \\ \* Collectoren .etl</span><span class="sxs-lookup"><span data-stu-id="5c472-184">%ProgramData%\\Microsoft\\DiagnosticLogCSP\\Collectors\\\*.etl</span></span>
- <span data-ttu-id="5c472-185">%ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ Logs \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="5c472-185">%ProgramData%\\Microsoft\\IntuneManagementExtension\\Logs\\\*.\*</span></span>
- <span data-ttu-id="5c472-186">%ProgramData% \\ Microsoft Windows Defender Ondersteuning \\ \\ \\MpSupportFiles.cab</span><span class="sxs-lookup"><span data-stu-id="5c472-186">%ProgramData%\\Microsoft\\Windows Defender\\Support\\MpSupportFiles.cab</span></span>
- <span data-ttu-id="5c472-187">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="5c472-187">%ProgramData%\\Microsoft\\Windows\\WlanReport\\wlan-report-latest.html</span></span>
- <span data-ttu-id="5c472-188">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="5c472-188">%ProgramData%\\Microsoft\\Windows\\WlanReport -SourceFileName wlan-report-latest.html</span></span>
- <span data-ttu-id="5c472-189">%windir% \\ ccm \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="5c472-189">%windir%\\ccm\\logs\*.log</span></span>
- <span data-ttu-id="5c472-190">%windir% \\ ccmsetup \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="5c472-190">%windir%\\ccmsetup\\logs\*.log</span></span>
- <span data-ttu-id="5c472-191">%windir% \\ logs \\ CBS \\ cbs.log</span><span class="sxs-lookup"><span data-stu-id="5c472-191">%windir%\\logs\\CBS\\cbs.log</span></span>
- <span data-ttu-id="5c472-192">%windir% \\ logs \\ measuredboot \* .\*</span><span class="sxs-lookup"><span data-stu-id="5c472-192">%windir%\\logs\\measuredboot\*.\*</span></span>
- <span data-ttu-id="5c472-193">%windir% \\ Logs \\ WindowsUpdate \* .etl</span><span class="sxs-lookup"><span data-stu-id="5c472-193">%windir%\\Logs\\WindowsUpdate\*.etl</span></span>
- <span data-ttu-id="5c472-194">%windir% \\ inf \\ \* .log</span><span class="sxs-lookup"><span data-stu-id="5c472-194">%windir%\\inf\\\*.log</span></span>
- <span data-ttu-id="5c472-195">%windir% \\ \\ servicesessies \\ActionList.xml</span><span class="sxs-lookup"><span data-stu-id="5c472-195">%windir%\\servicing\\sessions\\ActionList.xml</span></span>
- <span data-ttu-id="5c472-196">%windir% \\ \\ servicesessies \\Sessions.xml</span><span class="sxs-lookup"><span data-stu-id="5c472-196">%windir%\\servicing\\sessions\\Sessions.xml</span></span>
- <span data-ttu-id="5c472-197">%windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log</span><span class="sxs-lookup"><span data-stu-id="5c472-197">%windir%\\SoftwareDistribution\\DataStore\\Logs\\edb.log</span></span>
- <span data-ttu-id="5c472-198">%windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb</span><span class="sxs-lookup"><span data-stu-id="5c472-198">%windir%\\SoftwareDistribution\\DataStore\\DataStore.edb</span></span>
- <span data-ttu-id="5c472-199">%windir% \\ \\ logt dism \\ dism.log</span><span class="sxs-lookup"><span data-stu-id="5c472-199">%windir%\\logs\\dism\\dism.log</span></span>
- <span data-ttu-id="5c472-200">%SystemRoot% \\ System32 \\ Winevt \\ Logs</span><span class="sxs-lookup"><span data-stu-id="5c472-200">%SystemRoot%\\System32\\Winevt\\Logs</span></span>\\
- <span data-ttu-id="5c472-201">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="5c472-201">%appdata%\\Microsoft\\Teams\\media-stack\\\*.blog</span></span>
- <span data-ttu-id="5c472-202">%appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="5c472-202">%appdata%\\Microsoft\\Teams\\skylib\\\*.blog</span></span>
- <span data-ttu-id="5c472-203">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="5c472-203">%appdata%\\Microsoft\\Teams\\media-stack\\\*.etl</span></span>
- <span data-ttu-id="5c472-204">%appdata% \\ Microsoft \\ Teams \\logs.txt</span><span class="sxs-lookup"><span data-stu-id="5c472-204">%appdata%\\Microsoft\\Teams\\logs.txt</span></span>
- <span data-ttu-id="5c472-205">%windir% \\ Windows \\ System32 \\ winevt \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="5c472-205">%windir%\\Windows\\System32\\winevt\\\*.\*</span></span>