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
ms.openlocfilehash: 34274e260da2e8acc8088fcff6d324b6b31fc2ef
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935939"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c25f5-104">Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="c25f5-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c25f5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c25f5-105">**Applies to:**</span></span>
- [<span data-ttu-id="c25f5-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c25f5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c25f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c25f5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c25f5-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c25f5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c25f5-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="c25f5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c25f5-110">In dit onderwerp wordt beschreven hoe u Microsoft Defender voor Eindpunt op Linux kunt installeren, configureren, bijwerken en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c25f5-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="c25f5-111">Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Microsoft Defender voor Eindpunt op Linux kan waarschijnlijk leiden tot prestatieproblemen en onvoorspelbare bijwerkingen.</span><span class="sxs-lookup"><span data-stu-id="c25f5-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="c25f5-112">Als niet-Microsoft-eindpuntbeveiliging een absolute vereiste is in uw omgeving, kunt u na het configureren van de antivirusfunctionaliteit [](linux-preferences.md#enable--disable-passive-mode)in de passieve modus nog steeds veilig gebruik maken van Defender for Endpoint op Linux EDR-functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="c25f5-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c25f5-113">Microsoft Defender voor Eindpunt installeren op Linux</span><span class="sxs-lookup"><span data-stu-id="c25f5-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="c25f5-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="c25f5-114">Prerequisites</span></span>

- <span data-ttu-id="c25f5-115">Toegang tot de microsoft Defender-beveiligingscentrumportal</span><span class="sxs-lookup"><span data-stu-id="c25f5-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="c25f5-116">Linux-distributie met [de systemd](https://systemd.io/) system manager</span><span class="sxs-lookup"><span data-stu-id="c25f5-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="c25f5-117">Beginnerservaring in Linux- en BASH-scripting</span><span class="sxs-lookup"><span data-stu-id="c25f5-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="c25f5-118">Beheerdersbevoegdheden op het apparaat (in geval van handmatige implementatie)</span><span class="sxs-lookup"><span data-stu-id="c25f5-118">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="c25f5-119">Installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="c25f5-119">Installation instructions</span></span>

<span data-ttu-id="c25f5-120">Er zijn verschillende methoden en implementatiehulpmiddelen waarmee u Microsoft Defender voor Eindpunt op Linux kunt installeren en configureren.</span><span class="sxs-lookup"><span data-stu-id="c25f5-120">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="c25f5-121">Over het algemeen moet u de volgende stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="c25f5-121">In general you need to take the following steps:</span></span>

- <span data-ttu-id="c25f5-122">Zorg ervoor dat u een Microsoft Defender voor Eindpunt-abonnement hebt en dat u toegang hebt tot de [Microsoft Defender for Endpoint-portal.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="c25f5-122">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="c25f5-123">Microsoft Defender voor Eindpunt implementeren op Linux met behulp van een van de volgende implementatiemethoden:</span><span class="sxs-lookup"><span data-stu-id="c25f5-123">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="c25f5-124">Het opdrachtregelhulpmiddel:</span><span class="sxs-lookup"><span data-stu-id="c25f5-124">The command-line tool:</span></span>
    - [<span data-ttu-id="c25f5-125">Handmatige implementatie</span><span class="sxs-lookup"><span data-stu-id="c25f5-125">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="c25f5-126">Beheerhulpmiddelen van derden:</span><span class="sxs-lookup"><span data-stu-id="c25f5-126">Third-party management tools:</span></span>
    - [<span data-ttu-id="c25f5-127">Implementeren met behulp van Het configuratiebeheerprogramma van De pop-over</span><span class="sxs-lookup"><span data-stu-id="c25f5-127">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="c25f5-128">Implementeren met behulp van het hulpprogramma voor configuratiebeheer van Ansible</span><span class="sxs-lookup"><span data-stu-id="c25f5-128">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="c25f5-129">Als er installatiefouten optreden, raadpleegt u [Installatiefouten oplossen in Microsoft Defender voor Eindpunt op Linux.](linux-support-install.md)</span><span class="sxs-lookup"><span data-stu-id="c25f5-129">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="c25f5-130">Systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="c25f5-130">System requirements</span></span>

- <span data-ttu-id="c25f5-131">Ondersteunde Linux-serverdistributies en -versies:</span><span class="sxs-lookup"><span data-stu-id="c25f5-131">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="c25f5-132">Red Hat Enterprise Linux 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="c25f5-132">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="c25f5-133">CentOS 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="c25f5-133">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="c25f5-134">Ubuntu 16.04 LTS of hoger LTS</span><span class="sxs-lookup"><span data-stu-id="c25f5-134">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="c25f5-135">Debian 9 of hoger</span><span class="sxs-lookup"><span data-stu-id="c25f5-135">Debian 9 or higher</span></span>
  - <span data-ttu-id="c25f5-136">SUSE Linux Enterprise Server 12 of hoger</span><span class="sxs-lookup"><span data-stu-id="c25f5-136">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="c25f5-137">Oracle Linux 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="c25f5-137">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="c25f5-138">Minimum kernel versie 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="c25f5-138">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="c25f5-139">De `fanotify` kerneloptie moet zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="c25f5-139">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="c25f5-140">Het uitvoeren van Defender voor Eindpunt op Linux naast andere op basis van `fanotify` beveiligingsoplossingen wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="c25f5-140">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="c25f5-141">Dit kan leiden tot onvoorspelbare resultaten, waaronder het ophangen van het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="c25f5-141">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="c25f5-142">Schijfruimte: 1 GB</span><span class="sxs-lookup"><span data-stu-id="c25f5-142">Disk space: 1GB</span></span>
- <span data-ttu-id="c25f5-143">/opt/microsoft/mdatp/sbin/wdavdaemon vereist uitvoerbare machtigingen.</span><span class="sxs-lookup"><span data-stu-id="c25f5-143">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="c25f5-144">Zie 'Controleer of de daemon uitvoerbare machtiging heeft' in Installatieproblemen oplossen voor Microsoft Defender voor Eindpunt op Linux voor meer [informatie.](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="c25f5-144">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="c25f5-145">Geheugen: 1 GB</span><span class="sxs-lookup"><span data-stu-id="c25f5-145">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="c25f5-146">Zorg ervoor dat u vrije schijfruimte hebt in /var.</span><span class="sxs-lookup"><span data-stu-id="c25f5-146">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="c25f5-147">De oplossing biedt momenteel realtime bescherming voor de volgende bestandssysteemtypen:</span><span class="sxs-lookup"><span data-stu-id="c25f5-147">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="c25f5-148">Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om uitgaande verbindingen tussen de service en uw eindpunten toe te staan.</span><span class="sxs-lookup"><span data-stu-id="c25f5-148">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="c25f5-149">Audit framework ( `auditd` ) moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c25f5-149">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c25f5-150">Systeemgebeurtenissen die zijn vastgelegd met regels die zijn toegevoegd, worden toegevoegd aan (s) en kunnen van invloed zijn op de controle van de `/etc/audit/rules.d/` `audit.log` host en de upstreamverzameling.</span><span class="sxs-lookup"><span data-stu-id="c25f5-150">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="c25f5-151">Gebeurtenissen die zijn toegevoegd door Microsoft Defender voor Endpoint op Linux, worden met de sleutel `mdatp` gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="c25f5-151">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="c25f5-152">Netwerkverbindingen</span><span class="sxs-lookup"><span data-stu-id="c25f5-152">Network connections</span></span>

<span data-ttu-id="c25f5-153">In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="c25f5-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="c25f5-154">U moet ervoor zorgen dat er geen firewall- of netwerkfilterregels zijn die de toegang tot deze URL's weigeren.</span><span class="sxs-lookup"><span data-stu-id="c25f5-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="c25f5-155">Als dat zo is, moet u mogelijk een *regel* voor toestaan speciaal voor hen maken.</span><span class="sxs-lookup"><span data-stu-id="c25f5-155">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="c25f5-156">**Spreadsheet met domeinenlijst**</span><span class="sxs-lookup"><span data-stu-id="c25f5-156">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="c25f5-157">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="c25f5-157">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="c25f5-159">Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="c25f5-159">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="c25f5-160">Download de spreadsheet hier.</span><span class="sxs-lookup"><span data-stu-id="c25f5-160">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="c25f5-161">Zie Proxy- en internetverbindingsinstellingen configureren voor een specifiekere [URL-lijst.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="c25f5-161">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="c25f5-162">Defender voor Eindpunt kan een proxyserver ontdekken met behulp van de volgende detectiemethoden:</span><span class="sxs-lookup"><span data-stu-id="c25f5-162">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="c25f5-163">Transparante proxy</span><span class="sxs-lookup"><span data-stu-id="c25f5-163">Transparent proxy</span></span>
- <span data-ttu-id="c25f5-164">Handmatige statische proxyconfiguratie</span><span class="sxs-lookup"><span data-stu-id="c25f5-164">Manual static proxy configuration</span></span>

<span data-ttu-id="c25f5-165">Als een proxy of firewall anoniem verkeer blokkeert, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.</span><span class="sxs-lookup"><span data-stu-id="c25f5-165">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="c25f5-166">Voor doorzichtige proxies is er geen extra configuratie nodig voor Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="c25f5-166">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="c25f5-167">Voor statische proxy volgt u de stappen in [Handmatige statische proxyconfiguratie.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="c25f5-167">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="c25f5-168">PAC-, WPAD- en geverifieerde proxies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="c25f5-168">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="c25f5-169">Zorg ervoor dat alleen een statische proxy of transparante proxy wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c25f5-169">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="c25f5-170">SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen.</span><span class="sxs-lookup"><span data-stu-id="c25f5-170">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="c25f5-171">Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Defender for Endpoint op Linux rechtstreeks door te geven aan de relevante URL's zonder interceptie.</span><span class="sxs-lookup"><span data-stu-id="c25f5-171">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="c25f5-172">Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="c25f5-172">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="c25f5-173">Zie Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt op Linux voor meer informatie over het oplossen van problemen met [de cloud.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="c25f5-173">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c25f5-174">Microsoft Defender voor Eindpunt bijwerken op Linux</span><span class="sxs-lookup"><span data-stu-id="c25f5-174">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="c25f5-175">Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="c25f5-175">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="c25f5-176">Als u Microsoft Defender voor Eindpunt op Linux wilt bijwerken, raadpleegt u Updates implementeren voor [Microsoft Defender voor Eindpunt op Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="c25f5-176">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c25f5-177">Microsoft Defender configureren voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="c25f5-177">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="c25f5-178">Richtlijnen voor het configureren van het product in bedrijfsomgevingen zijn beschikbaar in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="c25f5-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="c25f5-179">Resources</span><span class="sxs-lookup"><span data-stu-id="c25f5-179">Resources</span></span>

- <span data-ttu-id="c25f5-180">Zie Resources voor meer informatie over logboekregistratie, verwijderen of andere [onderwerpen.](linux-resources.md)</span><span class="sxs-lookup"><span data-stu-id="c25f5-180">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
