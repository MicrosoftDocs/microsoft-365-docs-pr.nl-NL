---
title: Microsoft Defender voor Eindpunt op Linux
ms.reviewer: ''
description: Hier wordt beschreven hoe u Microsoft Defender voor Eindpunt op Linux installeert en gebruikt.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, pop, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bd9d42ed85e9a489107a72ccbe841537a7e524d4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843516"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="83a4d-104">Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="83a4d-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="83a4d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="83a4d-105">**Applies to:**</span></span>
- [<span data-ttu-id="83a4d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="83a4d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="83a4d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83a4d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="83a4d-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="83a4d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="83a4d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="83a4d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="83a4d-110">In dit onderwerp wordt beschreven hoe u Microsoft Defender voor Eindpunt op Linux kunt installeren, configureren, bijwerken en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="83a4d-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="83a4d-111">Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Microsoft Defender voor Eindpunt op Linux kan waarschijnlijk leiden tot prestatieproblemen en onvoorspelbare bijwerkingen.</span><span class="sxs-lookup"><span data-stu-id="83a4d-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="83a4d-112">Als niet-Microsoft-eindpuntbeveiliging een absolute vereiste is in uw omgeving, kunt u nog steeds veilig profiteren van De functionaliteit van Defender voor Eindpunt op Linux EDR nadat u de antivirusfunctionaliteit hebt geconfigureerd voor gebruik in de passieve [modus.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="83a4d-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="83a4d-113">Microsoft Defender voor Eindpunt installeren op Linux</span><span class="sxs-lookup"><span data-stu-id="83a4d-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="83a4d-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="83a4d-114">Prerequisites</span></span>

- <span data-ttu-id="83a4d-115">Toegang tot de Microsoft Defender-beveiligingscentrum portal</span><span class="sxs-lookup"><span data-stu-id="83a4d-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="83a4d-116">Linux-distributie met [de systemd](https://systemd.io/) system manager</span><span class="sxs-lookup"><span data-stu-id="83a4d-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="83a4d-117">Beginnerservaring in Linux- en BASH-scripting</span><span class="sxs-lookup"><span data-stu-id="83a4d-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="83a4d-118">Beheerdersbevoegdheden op het apparaat (in geval van handmatige implementatie)</span><span class="sxs-lookup"><span data-stu-id="83a4d-118">Administrative privileges on the device (in case of manual deployment)</span></span>

> [!NOTE]
>  <span data-ttu-id="83a4d-119">Microsoft Defender voor Endpoint op Linux-agent is onafhankelijk van [OMS-agent.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="83a4d-119">Microsoft Defender for Endpoint on Linux agent is independent from [OMS agent](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span></span> <span data-ttu-id="83a4d-120">Microsoft Defender voor Eindpunt is afhankelijk van een eigen onafhankelijke telemetriepijplijn.</span><span class="sxs-lookup"><span data-stu-id="83a4d-120">Microsoft Defender for Endpoint relies on its own independent telemetry pipeline.</span></span>
> 
> <span data-ttu-id="83a4d-121">Microsoft Defender voor Eindpunt op Linux is nog niet geïntegreerd in azure-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="83a4d-121">Microsoft Defender for Endpoint on Linux is not yet integrated into Azure Security Center.</span></span>



### <a name="installation-instructions"></a><span data-ttu-id="83a4d-122">Installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="83a4d-122">Installation instructions</span></span>

<span data-ttu-id="83a4d-123">Er zijn verschillende methoden en implementatiehulpmiddelen waarmee u Microsoft Defender voor Eindpunt op Linux kunt installeren en configureren.</span><span class="sxs-lookup"><span data-stu-id="83a4d-123">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="83a4d-124">Over het algemeen moet u de volgende stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="83a4d-124">In general you need to take the following steps:</span></span>

- <span data-ttu-id="83a4d-125">Zorg ervoor dat u een Microsoft Defender voor Eindpunt-abonnement hebt en dat u toegang hebt tot de [Microsoft Defender for Endpoint-portal.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="83a4d-125">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="83a4d-126">Microsoft Defender voor Eindpunt implementeren op Linux met behulp van een van de volgende implementatiemethoden:</span><span class="sxs-lookup"><span data-stu-id="83a4d-126">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="83a4d-127">Het opdrachtregelhulpmiddel:</span><span class="sxs-lookup"><span data-stu-id="83a4d-127">The command-line tool:</span></span>
    - [<span data-ttu-id="83a4d-128">Handmatige implementatie</span><span class="sxs-lookup"><span data-stu-id="83a4d-128">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="83a4d-129">Beheerhulpmiddelen van derden:</span><span class="sxs-lookup"><span data-stu-id="83a4d-129">Third-party management tools:</span></span>
    - [<span data-ttu-id="83a4d-130">Implementeren met behulp van Het configuratiebeheerprogramma van De pop-over</span><span class="sxs-lookup"><span data-stu-id="83a4d-130">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="83a4d-131">Implementeren met behulp van het hulpprogramma voor configuratiebeheer van Ansible</span><span class="sxs-lookup"><span data-stu-id="83a4d-131">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="83a4d-132">Als er installatiefouten optreden, raadpleegt u [Installatiefouten oplossen in Microsoft Defender voor Eindpunt op Linux.](linux-support-install.md)</span><span class="sxs-lookup"><span data-stu-id="83a4d-132">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>



### <a name="system-requirements"></a><span data-ttu-id="83a4d-133">Systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="83a4d-133">System requirements</span></span>

- <span data-ttu-id="83a4d-134">Ondersteunde Linux-serverdistributies en x64-versies (AMD64/EM64T) :</span><span class="sxs-lookup"><span data-stu-id="83a4d-134">Supported Linux server distributions and x64 (AMD64/EM64T) versions:</span></span>

  - <span data-ttu-id="83a4d-135">Red Hat Enterprise Linux 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="83a4d-135">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="83a4d-136">CentOS 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="83a4d-136">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="83a4d-137">Ubuntu 16.04 LTS of hoger LTS</span><span class="sxs-lookup"><span data-stu-id="83a4d-137">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="83a4d-138">Debian 9 of hoger</span><span class="sxs-lookup"><span data-stu-id="83a4d-138">Debian 9 or higher</span></span>
  - <span data-ttu-id="83a4d-139">SUSE Linux Enterprise Server 12 of hoger</span><span class="sxs-lookup"><span data-stu-id="83a4d-139">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="83a4d-140">Oracle Linux 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="83a4d-140">Oracle Linux 7.2 or higher</span></span>

    > [!NOTE]
    > <span data-ttu-id="83a4d-141">Distributies en versies die niet expliciet worden vermeld, worden niet ondersteund (zelfs als ze zijn afgeleid van de officieel ondersteunde distributies).</span><span class="sxs-lookup"><span data-stu-id="83a4d-141">Distributions and version that are not explicitly listed are unsupported (even if they are derived from the officially supported distributions).</span></span>


- <span data-ttu-id="83a4d-142">Minimum kernel versie 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="83a4d-142">Minimum kernel version 3.10.0-327</span></span>

- <span data-ttu-id="83a4d-143">De `fanotify` kerneloptie moet zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="83a4d-143">The `fanotify` kernel option must be enabled</span></span>

  > [!CAUTION]
  > <span data-ttu-id="83a4d-144">Het uitvoeren van Defender voor Eindpunt op Linux naast andere op basis van `fanotify` beveiligingsoplossingen wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="83a4d-144">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="83a4d-145">Dit kan leiden tot onvoorspelbare resultaten, waaronder het ophangen van het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="83a4d-145">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="83a4d-146">Schijfruimte: 1 GB</span><span class="sxs-lookup"><span data-stu-id="83a4d-146">Disk space: 1 GB</span></span>

- <span data-ttu-id="83a4d-147">/opt/microsoft/mdatp/sbin/wdavdaemon vereist uitvoerbare machtigingen.</span><span class="sxs-lookup"><span data-stu-id="83a4d-147">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="83a4d-148">Zie 'Controleer of de daemon uitvoerbare machtiging heeft' in Installatieproblemen oplossen voor Microsoft Defender voor Eindpunt op Linux voor meer [informatie.](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="83a4d-148">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>

- <span data-ttu-id="83a4d-149">Geheugen: 1 GB</span><span class="sxs-lookup"><span data-stu-id="83a4d-149">Memory: 1 GB</span></span>

    > [!NOTE]
    > <span data-ttu-id="83a4d-150">Zorg ervoor dat u vrije schijfruimte hebt in /var.</span><span class="sxs-lookup"><span data-stu-id="83a4d-150">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="83a4d-151">De oplossing biedt momenteel realtime bescherming voor de volgende bestandssysteemtypen:</span><span class="sxs-lookup"><span data-stu-id="83a4d-151">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="83a4d-152">Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om uitgaande verbindingen tussen de service en uw eindpunten toe te staan.</span><span class="sxs-lookup"><span data-stu-id="83a4d-152">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="83a4d-153">Audit framework ( `auditd` ) moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="83a4d-153">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="83a4d-154">Systeemgebeurtenissen die zijn vastgelegd met regels die zijn toegevoegd, worden toegevoegd aan (s) en kunnen van invloed zijn op de controle van de `/etc/audit/rules.d/` `audit.log` host en de upstreamverzameling.</span><span class="sxs-lookup"><span data-stu-id="83a4d-154">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="83a4d-155">Gebeurtenissen die zijn toegevoegd door Microsoft Defender voor Endpoint op Linux, worden met de sleutel `mdatp` gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="83a4d-155">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="83a4d-156">Netwerkverbindingen</span><span class="sxs-lookup"><span data-stu-id="83a4d-156">Network connections</span></span>

<span data-ttu-id="83a4d-157">In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="83a4d-157">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="83a4d-158">U moet ervoor zorgen dat er geen firewall- of netwerkfilterregels zijn die de toegang tot deze URL's weigeren.</span><span class="sxs-lookup"><span data-stu-id="83a4d-158">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="83a4d-159">Als dat zo is, moet u mogelijk een *regel* voor toestaan speciaal voor hen maken.</span><span class="sxs-lookup"><span data-stu-id="83a4d-159">If there are, you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="83a4d-160">Spreadsheet met domeinenlijst</span><span class="sxs-lookup"><span data-stu-id="83a4d-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="83a4d-161">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="83a4d-161">Description</span></span> |
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="83a4d-163">Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="83a4d-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="83a4d-164">Download de spreadsheet hier.</span><span class="sxs-lookup"><span data-stu-id="83a4d-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="83a4d-165">Zie Proxy- en internetverbindingsinstellingen configureren voor een specifiekere [URL-lijst.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="83a4d-165">For a more specific URL list, see [Configure proxy and internet connectivity settings](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="83a4d-166">Defender voor Eindpunt kan een proxyserver ontdekken met behulp van de volgende detectiemethoden:</span><span class="sxs-lookup"><span data-stu-id="83a4d-166">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="83a4d-167">Transparante proxy</span><span class="sxs-lookup"><span data-stu-id="83a4d-167">Transparent proxy</span></span>
- <span data-ttu-id="83a4d-168">Handmatige statische proxyconfiguratie</span><span class="sxs-lookup"><span data-stu-id="83a4d-168">Manual static proxy configuration</span></span>

<span data-ttu-id="83a4d-169">Als een proxy of firewall anoniem verkeer blokkeert, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.</span><span class="sxs-lookup"><span data-stu-id="83a4d-169">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="83a4d-170">Voor doorzichtige proxies is er geen extra configuratie nodig voor Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="83a4d-170">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="83a4d-171">Voor statische proxy volgt u de stappen in [Handmatige statische proxyconfiguratie.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="83a4d-171">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="83a4d-172">PAC-, WPAD- en geverifieerde proxies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="83a4d-172">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="83a4d-173">Zorg ervoor dat alleen een statische proxy of transparante proxy wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="83a4d-173">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="83a4d-174">SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen.</span><span class="sxs-lookup"><span data-stu-id="83a4d-174">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="83a4d-175">Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Defender for Endpoint op Linux rechtstreeks door te geven aan de relevante URL's zonder interceptie.</span><span class="sxs-lookup"><span data-stu-id="83a4d-175">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="83a4d-176">Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="83a4d-176">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="83a4d-177">Zie Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt op Linux voor meer informatie over het oplossen van problemen met [de cloud.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="83a4d-177">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="83a4d-178">Microsoft Defender voor Eindpunt bijwerken op Linux</span><span class="sxs-lookup"><span data-stu-id="83a4d-178">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="83a4d-179">Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="83a4d-179">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="83a4d-180">Als u Microsoft Defender voor Eindpunt op Linux wilt bijwerken, raadpleegt u Updates implementeren voor [Microsoft Defender voor Eindpunt op Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="83a4d-180">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="83a4d-181">Microsoft Defender configureren voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="83a4d-181">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="83a4d-182">Richtlijnen voor het configureren van het product in bedrijfsomgevingen zijn beschikbaar in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="83a4d-182">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="83a4d-183">Resources</span><span class="sxs-lookup"><span data-stu-id="83a4d-183">Resources</span></span>

- <span data-ttu-id="83a4d-184">Zie Resources voor meer informatie over logboekregistratie, verwijderen of andere [onderwerpen.](linux-resources.md)</span><span class="sxs-lookup"><span data-stu-id="83a4d-184">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
