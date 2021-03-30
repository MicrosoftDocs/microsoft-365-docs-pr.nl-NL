---
title: Microsoft Defender ATP voor Linux
ms.reviewer: ''
description: Hier wordt beschreven hoe u Microsoft Defender ATP voor Linux installeert en gebruikt.
keywords: microsoft, defender, atp, linux, installatie, implementeren, verwijderen, pop, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 08bb4c73cb9df429c4b07194f1c7615f44d745d8
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408335"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="f0deb-104">Microsoft Defender voor Eindpunt voor Linux</span><span class="sxs-lookup"><span data-stu-id="f0deb-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f0deb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f0deb-105">**Applies to:**</span></span>
- [<span data-ttu-id="f0deb-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f0deb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f0deb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0deb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f0deb-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f0deb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f0deb-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f0deb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f0deb-110">In dit onderwerp wordt beschreven hoe u Microsoft Defender voor Eindpunt voor Linux kunt installeren, configureren, bijwerken en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f0deb-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="f0deb-111">Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Microsoft Defender voor Eindpunt voor Linux kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="f0deb-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="f0deb-112">Microsoft Defender voor Eindpunt voor Linux installeren</span><span class="sxs-lookup"><span data-stu-id="f0deb-112">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="f0deb-113">Vereisten</span><span class="sxs-lookup"><span data-stu-id="f0deb-113">Prerequisites</span></span>

- <span data-ttu-id="f0deb-114">Toegang tot de microsoft Defender-beveiligingscentrumportal</span><span class="sxs-lookup"><span data-stu-id="f0deb-114">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="f0deb-115">Linux-distributie met [de systemd](https://systemd.io/) system manager</span><span class="sxs-lookup"><span data-stu-id="f0deb-115">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="f0deb-116">Beginnerservaring in Linux- en BASH-scripting</span><span class="sxs-lookup"><span data-stu-id="f0deb-116">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="f0deb-117">Beheerdersbevoegdheden op het apparaat (in geval van handmatige implementatie)</span><span class="sxs-lookup"><span data-stu-id="f0deb-117">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="f0deb-118">Installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="f0deb-118">Installation instructions</span></span>

<span data-ttu-id="f0deb-119">Er zijn verschillende methoden en implementatiehulpmiddelen waarmee u Microsoft Defender voor Eindpunt voor Linux kunt installeren en configureren.</span><span class="sxs-lookup"><span data-stu-id="f0deb-119">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="f0deb-120">Over het algemeen moet u de volgende stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="f0deb-120">In general you need to take the following steps:</span></span>

- <span data-ttu-id="f0deb-121">Zorg ervoor dat u een Microsoft Defender voor Eindpunt-abonnement hebt en dat u toegang hebt tot de [Microsoft Defender for Endpoint-portal.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="f0deb-121">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="f0deb-122">Microsoft Defender voor Eindpunt voor Linux implementeren met behulp van een van de volgende implementatiemethoden:</span><span class="sxs-lookup"><span data-stu-id="f0deb-122">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="f0deb-123">Het opdrachtregelhulpmiddel:</span><span class="sxs-lookup"><span data-stu-id="f0deb-123">The command-line tool:</span></span>
    - [<span data-ttu-id="f0deb-124">Handmatige implementatie</span><span class="sxs-lookup"><span data-stu-id="f0deb-124">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="f0deb-125">Beheerhulpmiddelen van derden:</span><span class="sxs-lookup"><span data-stu-id="f0deb-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="f0deb-126">Implementeren met behulp van Het configuratiebeheerprogramma van De pop-over</span><span class="sxs-lookup"><span data-stu-id="f0deb-126">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="f0deb-127">Implementeren met behulp van het hulpprogramma voor configuratiebeheer van Ansible</span><span class="sxs-lookup"><span data-stu-id="f0deb-127">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="f0deb-128">Als er installatiefouten optreden, raadpleegt u [Installatiefouten oplossen in Microsoft Defender voor Eindpunt voor Linux.](linux-support-install.md)</span><span class="sxs-lookup"><span data-stu-id="f0deb-128">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="f0deb-129">Systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="f0deb-129">System requirements</span></span>

- <span data-ttu-id="f0deb-130">Ondersteunde Linux-serverdistributies en -versies:</span><span class="sxs-lookup"><span data-stu-id="f0deb-130">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="f0deb-131">Red Hat Enterprise Linux 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="f0deb-131">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="f0deb-132">CentOS 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="f0deb-132">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="f0deb-133">Ubuntu 16.04 LTS of hoger LTS</span><span class="sxs-lookup"><span data-stu-id="f0deb-133">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="f0deb-134">Debian 9 of hoger</span><span class="sxs-lookup"><span data-stu-id="f0deb-134">Debian 9 or higher</span></span>
  - <span data-ttu-id="f0deb-135">SUSE Linux Enterprise Server 12 of hoger</span><span class="sxs-lookup"><span data-stu-id="f0deb-135">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="f0deb-136">Oracle Linux 7.2 of hoger</span><span class="sxs-lookup"><span data-stu-id="f0deb-136">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="f0deb-137">Minimum kernel versie 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="f0deb-137">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="f0deb-138">De `fanotify` kerneloptie moet zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="f0deb-138">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="f0deb-139">Het uitvoeren van Defender voor Eindpunt voor Linux naast andere op basis van `fanotify` beveiligingsoplossingen wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="f0deb-139">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="f0deb-140">Dit kan leiden tot onvoorspelbare resultaten, waaronder het ophangen van het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="f0deb-140">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="f0deb-141">Schijfruimte: 1 GB</span><span class="sxs-lookup"><span data-stu-id="f0deb-141">Disk space: 1GB</span></span>
- <span data-ttu-id="f0deb-142">/opt/microsoft/mdatp/sbin/wdavdaemon vereist uitvoerbare machtigingen.</span><span class="sxs-lookup"><span data-stu-id="f0deb-142">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="f0deb-143">Zie 'Controleer of de daemon uitvoerbare machtiging heeft' in Installatieproblemen oplossen voor [Microsoft Defender ATP voor Linux voor](/microsoft-365/security/defender-endpoint/linux-support-install)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f0deb-143">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="f0deb-144">Geheugen: 1 GB</span><span class="sxs-lookup"><span data-stu-id="f0deb-144">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="f0deb-145">Zorg ervoor dat u vrije schijfruimte hebt in /var.</span><span class="sxs-lookup"><span data-stu-id="f0deb-145">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="f0deb-146">De oplossing biedt momenteel realtime bescherming voor de volgende bestandssysteemtypen:</span><span class="sxs-lookup"><span data-stu-id="f0deb-146">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="f0deb-147">Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om uitgaande verbindingen tussen de service en uw eindpunten toe te staan.</span><span class="sxs-lookup"><span data-stu-id="f0deb-147">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="f0deb-148">Audit framework ( `auditd` ) moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f0deb-148">Audit framework (`auditd`) must be enabled.</span></span>
  >[!NOTE]
  > <span data-ttu-id="f0deb-149">Systeemgebeurtenissen die zijn vastgelegd met regels die zijn toegevoegd, worden toegevoegd aan auditlogboeken en kunnen van invloed zijn op de controle van de `audit.logs` host en de upstreamverzameling.</span><span class="sxs-lookup"><span data-stu-id="f0deb-149">System events captured by rules added to `audit.logs` will add to audit logs and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="f0deb-150">Gebeurtenissen die zijn toegevoegd door Microsoft Defender voor Endopoint voor Linux, worden met de sleutel `mdatp` gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="f0deb-150">Events added by Microsoft Defender for Endopoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="f0deb-151">Netwerkverbindingen</span><span class="sxs-lookup"><span data-stu-id="f0deb-151">Network connections</span></span>

<span data-ttu-id="f0deb-152">In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="f0deb-152">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="f0deb-153">U moet ervoor zorgen dat er geen firewall- of netwerkfilterregels zijn die de toegang tot deze URL's weigeren.</span><span class="sxs-lookup"><span data-stu-id="f0deb-153">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="f0deb-154">Als dat zo is, moet u mogelijk een *regel* voor toestaan speciaal voor hen maken.</span><span class="sxs-lookup"><span data-stu-id="f0deb-154">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="f0deb-155">**Spreadsheet met domeinenlijst**</span><span class="sxs-lookup"><span data-stu-id="f0deb-155">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="f0deb-156">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="f0deb-156">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="f0deb-158">Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="f0deb-158">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="f0deb-159">Download de spreadsheet hier.</span><span class="sxs-lookup"><span data-stu-id="f0deb-159">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="f0deb-160">Zie Proxy- en internetverbindingsinstellingen configureren voor een specifiekere [URL-lijst.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="f0deb-160">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="f0deb-161">Defender voor Eindpunt kan een proxyserver ontdekken met behulp van de volgende detectiemethoden:</span><span class="sxs-lookup"><span data-stu-id="f0deb-161">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="f0deb-162">Transparante proxy</span><span class="sxs-lookup"><span data-stu-id="f0deb-162">Transparent proxy</span></span>
- <span data-ttu-id="f0deb-163">Handmatige statische proxyconfiguratie</span><span class="sxs-lookup"><span data-stu-id="f0deb-163">Manual static proxy configuration</span></span>

<span data-ttu-id="f0deb-164">Als een proxy of firewall anoniem verkeer blokkeert, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.</span><span class="sxs-lookup"><span data-stu-id="f0deb-164">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="f0deb-165">Voor doorzichtige proxies is er geen extra configuratie nodig voor Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="f0deb-165">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="f0deb-166">Voor statische proxy volgt u de stappen in [Handmatige statische proxyconfiguratie.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="f0deb-166">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="f0deb-167">PAC-, WPAD- en geverifieerde proxies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="f0deb-167">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="f0deb-168">Zorg ervoor dat alleen een statische proxy of transparante proxy wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f0deb-168">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="f0deb-169">SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen.</span><span class="sxs-lookup"><span data-stu-id="f0deb-169">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="f0deb-170">Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Defender voor Endpoint voor Linux rechtstreeks door te geven aan de relevante URL's zonder interceptie.</span><span class="sxs-lookup"><span data-stu-id="f0deb-170">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="f0deb-171">Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="f0deb-171">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="f0deb-172">Zie Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt voor Linux voor meer informatie over het oplossen van problemen met [de cloud.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="f0deb-172">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="f0deb-173">Microsoft Defender voor Eindpunt voor Linux bijwerken</span><span class="sxs-lookup"><span data-stu-id="f0deb-173">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="f0deb-174">Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="f0deb-174">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="f0deb-175">Als u Microsoft Defender voor Eindpunt voor Linux wilt bijwerken, raadpleegt u Updates implementeren voor [Microsoft Defender voor Eindpunt voor Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="f0deb-175">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="f0deb-176">Microsoft Defender configureren voor Eindpunt voor Linux</span><span class="sxs-lookup"><span data-stu-id="f0deb-176">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="f0deb-177">Richtlijnen voor het configureren van het product in bedrijfsomgevingen zijn beschikbaar in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="f0deb-177">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="f0deb-178">Resources</span><span class="sxs-lookup"><span data-stu-id="f0deb-178">Resources</span></span>

- <span data-ttu-id="f0deb-179">Zie Resources voor meer informatie over logboekregistratie, verwijderen of andere [onderwerpen.](linux-resources.md)</span><span class="sxs-lookup"><span data-stu-id="f0deb-179">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
