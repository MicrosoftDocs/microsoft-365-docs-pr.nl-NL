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
ms.openlocfilehash: 008263bfb948d1a2c52031635d074aca323e6764
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256889"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c7db4-104">Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="c7db4-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c7db4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c7db4-105">**Applies to:**</span></span>
- [<span data-ttu-id="c7db4-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c7db4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c7db4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7db4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c7db4-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c7db4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c7db4-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="c7db4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c7db4-110">In dit onderwerp wordt beschreven hoe u Microsoft Defender voor Eindpunt op Linux kunt installeren, configureren, bijwerken en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c7db4-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="c7db4-111">Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Microsoft Defender voor Eindpunt op Linux kan waarschijnlijk leiden tot prestatieproblemen en onvoorspelbare bijwerkingen.</span><span class="sxs-lookup"><span data-stu-id="c7db4-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="c7db4-112">Als niet-Microsoft-eindpuntbeveiliging een absolute vereiste is in uw omgeving, kunt u nog steeds veilig profiteren van De functionaliteit van Defender voor Eindpunt op Linux EDR nadat u de antivirusfunctionaliteit hebt geconfigureerd voor gebruik in de passieve [modus.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="c7db4-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c7db4-113">Microsoft Defender voor Eindpunt installeren op Linux</span><span class="sxs-lookup"><span data-stu-id="c7db4-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="c7db4-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="c7db4-114">Prerequisites</span></span>

- <span data-ttu-id="c7db4-115">Toegang tot de Microsoft Defender-beveiligingscentrum portal</span><span class="sxs-lookup"><span data-stu-id="c7db4-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="c7db4-116">Linux-distributie met [de systemd](https://systemd.io/) system manager</span><span class="sxs-lookup"><span data-stu-id="c7db4-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="c7db4-117">Beginnerservaring in Linux- en BASH-scripting</span><span class="sxs-lookup"><span data-stu-id="c7db4-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="c7db4-118">Beheerdersbevoegdheden op het apparaat (in geval van handmatige implementatie)</span><span class="sxs-lookup"><span data-stu-id="c7db4-118">Administrative privileges on the device (in case of manual deployment)</span></span>

> [!NOTE]
>  <span data-ttu-id="c7db4-119">Microsoft Defender voor Endpoint op Linux-agent is onafhankelijk van [OMS-agent.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="c7db4-119">Microsoft Defender for Endpoint on Linux agent is independent from [OMS agent](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span></span> <span data-ttu-id="c7db4-120">Microsoft Defender voor Eindpunt is afhankelijk van een eigen onafhankelijke telemetriepijplijn.</span><span class="sxs-lookup"><span data-stu-id="c7db4-120">Microsoft Defender for Endpoint relies on its own independent telemetry pipeline.</span></span>
> 
> <span data-ttu-id="c7db4-121">Microsoft Defender voor Eindpunt op Linux is nog niet geïntegreerd in azure-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="c7db4-121">Microsoft Defender for Endpoint on Linux is not yet integrated into Azure Security Center.</span></span>



### <a name="installation-instructions"></a><span data-ttu-id="c7db4-122">Installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="c7db4-122">Installation instructions</span></span>

<span data-ttu-id="c7db4-123">Er zijn verschillende methoden en implementatiehulpmiddelen waarmee u Microsoft Defender voor Eindpunt op Linux kunt installeren en configureren.</span><span class="sxs-lookup"><span data-stu-id="c7db4-123">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="c7db4-124">Over het algemeen moet u de volgende stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="c7db4-124">In general you need to take the following steps:</span></span>

- <span data-ttu-id="c7db4-125">Zorg ervoor dat u een Microsoft Defender voor Eindpunt-abonnement hebt en dat u toegang hebt tot de [Microsoft Defender for Endpoint-portal.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="c7db4-125">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="c7db4-126">Microsoft Defender voor Eindpunt implementeren op Linux met behulp van een van de volgende implementatiemethoden:</span><span class="sxs-lookup"><span data-stu-id="c7db4-126">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="c7db4-127">Het opdrachtregelhulpmiddel:</span><span class="sxs-lookup"><span data-stu-id="c7db4-127">The command-line tool:</span></span>
    - [<span data-ttu-id="c7db4-128">Handmatige implementatie</span><span class="sxs-lookup"><span data-stu-id="c7db4-128">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="c7db4-129">Beheerhulpmiddelen van derden:</span><span class="sxs-lookup"><span data-stu-id="c7db4-129">Third-party management tools:</span></span>
    - [<span data-ttu-id="c7db4-130">Implementeren met behulp van Het configuratiebeheerprogramma van De pop-over</span><span class="sxs-lookup"><span data-stu-id="c7db4-130">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="c7db4-131">Implementeren met behulp van het hulpprogramma voor configuratiebeheer van Ansible</span><span class="sxs-lookup"><span data-stu-id="c7db4-131">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)
    - [<span data-ttu-id="c7db4-132">Implementeren met het configuratiebeheerprogramma van Chef</span><span class="sxs-lookup"><span data-stu-id="c7db4-132">Deploy using Chef configuration management tool</span></span>](linux-deploy-defender-for-endpoint-with-chef.md)
    
<span data-ttu-id="c7db4-133">Als er installatiefouten optreden, raadpleegt u [Installatiefouten oplossen in Microsoft Defender voor Eindpunt op Linux.](linux-support-install.md)</span><span class="sxs-lookup"><span data-stu-id="c7db4-133">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>



### <a name="system-requirements"></a><span data-ttu-id="c7db4-134">Systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="c7db4-134">System requirements</span></span>

- <span data-ttu-id="c7db4-135">Ondersteunde Linux-serverdistributies en x64-versies (AMD64/EM64T) :</span><span class="sxs-lookup"><span data-stu-id="c7db4-135">Supported Linux server distributions and x64 (AMD64/EM64T) versions:</span></span>

  - <span data-ttu-id="c7db4-136">Red Hat Enterprise Linux 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="c7db4-136">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="c7db4-137">CentOS 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="c7db4-137">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="c7db4-138">Ubuntu 16.04 LTS of hoger LTS</span><span class="sxs-lookup"><span data-stu-id="c7db4-138">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="c7db4-139">Debian 9 of hoger</span><span class="sxs-lookup"><span data-stu-id="c7db4-139">Debian 9 or higher</span></span>
  - <span data-ttu-id="c7db4-140">SUSE Linux Enterprise Server 12 of hoger</span><span class="sxs-lookup"><span data-stu-id="c7db4-140">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="c7db4-141">Oracle Linux 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="c7db4-141">Oracle Linux 7.2 or higher</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7db4-142">Distributies en versies die niet expliciet worden vermeld, worden niet ondersteund (zelfs als ze zijn afgeleid van de officieel ondersteunde distributies).</span><span class="sxs-lookup"><span data-stu-id="c7db4-142">Distributions and version that are not explicitly listed are unsupported (even if they are derived from the officially supported distributions).</span></span>


- <span data-ttu-id="c7db4-143">Minimum kernel versie 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="c7db4-143">Minimum kernel version 3.10.0-327</span></span>

- <span data-ttu-id="c7db4-144">De `fanotify` kerneloptie moet zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="c7db4-144">The `fanotify` kernel option must be enabled</span></span>

  > [!CAUTION]
  > <span data-ttu-id="c7db4-145">Het uitvoeren van Defender voor Eindpunt op Linux naast andere op basis van `fanotify` beveiligingsoplossingen wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="c7db4-145">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="c7db4-146">Dit kan leiden tot onvoorspelbare resultaten, waaronder het ophangen van het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="c7db4-146">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="c7db4-147">Schijfruimte: 1 GB</span><span class="sxs-lookup"><span data-stu-id="c7db4-147">Disk space: 1 GB</span></span>

- <span data-ttu-id="c7db4-148">/opt/microsoft/mdatp/sbin/wdavdaemon vereist uitvoerbare machtigingen.</span><span class="sxs-lookup"><span data-stu-id="c7db4-148">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="c7db4-149">Zie 'Controleer of de daemon uitvoerbare machtiging heeft' in Installatieproblemen oplossen voor Microsoft Defender voor Eindpunt op Linux voor meer [informatie.](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="c7db4-149">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>

- <span data-ttu-id="c7db4-150">Kernen: 2 minimum, 4 voorkeur</span><span class="sxs-lookup"><span data-stu-id="c7db4-150">Cores: 2 minimum, 4 preferred</span></span>

- <span data-ttu-id="c7db4-151">Geheugen: minimaal 1 GB, 4 voorkeur</span><span class="sxs-lookup"><span data-stu-id="c7db4-151">Memory: 1 GB minimum, 4 preferred</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7db4-152">Zorg ervoor dat u vrije schijfruimte hebt in /var.</span><span class="sxs-lookup"><span data-stu-id="c7db4-152">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="c7db4-153">De oplossing biedt momenteel realtime bescherming voor de volgende bestandssysteemtypen:</span><span class="sxs-lookup"><span data-stu-id="c7db4-153">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="c7db4-154">Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om uitgaande verbindingen tussen de service en uw eindpunten toe te staan.</span><span class="sxs-lookup"><span data-stu-id="c7db4-154">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="c7db4-155">Audit framework ( `auditd` ) moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c7db4-155">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c7db4-156">Systeemgebeurtenissen die zijn vastgelegd met regels die zijn toegevoegd, worden toegevoegd aan (s) en kunnen van invloed zijn op de controle van de `/etc/audit/rules.d/` `audit.log` host en de upstreamverzameling.</span><span class="sxs-lookup"><span data-stu-id="c7db4-156">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="c7db4-157">Gebeurtenissen die zijn toegevoegd door Microsoft Defender voor Endpoint op Linux, worden met de sleutel `mdatp` gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="c7db4-157">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="c7db4-158">Netwerkverbindingen</span><span class="sxs-lookup"><span data-stu-id="c7db4-158">Network connections</span></span>

<span data-ttu-id="c7db4-159">In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="c7db4-159">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="c7db4-160">U moet ervoor zorgen dat er geen firewall- of netwerkfilterregels zijn die de toegang tot deze URL's weigeren.</span><span class="sxs-lookup"><span data-stu-id="c7db4-160">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="c7db4-161">Als dat zo is, moet u mogelijk een *regel* voor toestaan speciaal voor hen maken.</span><span class="sxs-lookup"><span data-stu-id="c7db4-161">If there are, you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="c7db4-162">Spreadsheet met domeinenlijst</span><span class="sxs-lookup"><span data-stu-id="c7db4-162">Spreadsheet of domains list</span></span> | <span data-ttu-id="c7db4-163">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c7db4-163">Description</span></span> |
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="c7db4-165">Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="c7db4-165">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="c7db4-166">Download de spreadsheet hier.</span><span class="sxs-lookup"><span data-stu-id="c7db4-166">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="c7db4-167">Zie Proxy- en internetverbindingsinstellingen configureren voor een specifiekere [URL-lijst.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="c7db4-167">For a more specific URL list, see [Configure proxy and internet connectivity settings](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="c7db4-168">Defender voor Eindpunt kan een proxyserver ontdekken met behulp van de volgende detectiemethoden:</span><span class="sxs-lookup"><span data-stu-id="c7db4-168">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="c7db4-169">Transparante proxy</span><span class="sxs-lookup"><span data-stu-id="c7db4-169">Transparent proxy</span></span>
- <span data-ttu-id="c7db4-170">Handmatige statische proxyconfiguratie</span><span class="sxs-lookup"><span data-stu-id="c7db4-170">Manual static proxy configuration</span></span>

<span data-ttu-id="c7db4-171">Als een proxy of firewall anoniem verkeer blokkeert, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.</span><span class="sxs-lookup"><span data-stu-id="c7db4-171">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="c7db4-172">Voor doorzichtige proxies is er geen extra configuratie nodig voor Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="c7db4-172">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="c7db4-173">Voor statische proxy volgt u de stappen in [Handmatige statische proxyconfiguratie.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="c7db4-173">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="c7db4-174">PAC-, WPAD- en geverifieerde proxies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="c7db4-174">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="c7db4-175">Zorg ervoor dat alleen een statische proxy of transparante proxy wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c7db4-175">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="c7db4-176">SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen.</span><span class="sxs-lookup"><span data-stu-id="c7db4-176">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="c7db4-177">Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Defender for Endpoint op Linux rechtstreeks door te geven aan de relevante URL's zonder interceptie.</span><span class="sxs-lookup"><span data-stu-id="c7db4-177">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="c7db4-178">Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="c7db4-178">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="c7db4-179">Zie Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt op Linux voor meer informatie over het oplossen van problemen met [de cloud.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="c7db4-179">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c7db4-180">Microsoft Defender voor Eindpunt bijwerken op Linux</span><span class="sxs-lookup"><span data-stu-id="c7db4-180">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="c7db4-181">Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="c7db4-181">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="c7db4-182">Als u Microsoft Defender voor Eindpunt op Linux wilt bijwerken, raadpleegt u Updates implementeren voor [Microsoft Defender voor Eindpunt op Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="c7db4-182">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c7db4-183">Microsoft Defender configureren voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="c7db4-183">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="c7db4-184">Richtlijnen voor het configureren van het product in bedrijfsomgevingen zijn beschikbaar in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="c7db4-184">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="c7db4-185">Middelen</span><span class="sxs-lookup"><span data-stu-id="c7db4-185">Resources</span></span>

- <span data-ttu-id="c7db4-186">Zie Resources voor meer informatie over logboekregistratie, verwijderen of andere [onderwerpen.](linux-resources.md)</span><span class="sxs-lookup"><span data-stu-id="c7db4-186">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
