---
title: Microsoft Defender voor Eindpunt handmatig implementeren op Linux
ms.reviewer: ''
description: Hier wordt beschreven hoe u Microsoft Defender voor Eindpunt handmatig op Linux implementeert vanaf de opdrachtregel.
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3ed033f137d3329dc208183fe8fad1f300ffd4c9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841787"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a><span data-ttu-id="02ec8-104">Microsoft Defender voor Eindpunt handmatig implementeren op Linux</span><span class="sxs-lookup"><span data-stu-id="02ec8-104">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="02ec8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="02ec8-105">**Applies to:**</span></span>
- [<span data-ttu-id="02ec8-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="02ec8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="02ec8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02ec8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="02ec8-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="02ec8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="02ec8-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="02ec8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="02ec8-110">In dit artikel wordt beschreven hoe u Microsoft Defender voor Eindpunt handmatig op Linux implementeert.</span><span class="sxs-lookup"><span data-stu-id="02ec8-110">This article describes how to deploy Microsoft Defender for Endpoint on Linux manually.</span></span> <span data-ttu-id="02ec8-111">Voor een geslaagde implementatie moeten alle volgende taken zijn voltooid:</span><span class="sxs-lookup"><span data-stu-id="02ec8-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="02ec8-112">Microsoft Defender voor Eindpunt handmatig implementeren op Linux</span><span class="sxs-lookup"><span data-stu-id="02ec8-112">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [<span data-ttu-id="02ec8-113">Vereisten en systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="02ec8-113">Prerequisites and system requirements</span></span>](#prerequisites-and-system-requirements)
  - [<span data-ttu-id="02ec8-114">De Linux-softwareopslagplaats configureren</span><span class="sxs-lookup"><span data-stu-id="02ec8-114">Configure the Linux software repository</span></span>](#configure-the-linux-software-repository)
    - [<span data-ttu-id="02ec8-115">RHEL en varianten (CentOS en Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="02ec8-115">RHEL and variants (CentOS and Oracle Linux)</span></span>](#rhel-and-variants-centos-and-oracle-linux)
    - [<span data-ttu-id="02ec8-116">SLES en varianten</span><span class="sxs-lookup"><span data-stu-id="02ec8-116">SLES and variants</span></span>](#sles-and-variants)
    - [<span data-ttu-id="02ec8-117">Ubuntu- en Debian-systemen</span><span class="sxs-lookup"><span data-stu-id="02ec8-117">Ubuntu and Debian systems</span></span>](#ubuntu-and-debian-systems)
  - [<span data-ttu-id="02ec8-118">Toepassingsinstallatie</span><span class="sxs-lookup"><span data-stu-id="02ec8-118">Application installation</span></span>](#application-installation)
  - [<span data-ttu-id="02ec8-119">Het onboarding-pakket downloaden</span><span class="sxs-lookup"><span data-stu-id="02ec8-119">Download the onboarding package</span></span>](#download-the-onboarding-package)
  - [<span data-ttu-id="02ec8-120">Clientconfiguratie</span><span class="sxs-lookup"><span data-stu-id="02ec8-120">Client configuration</span></span>](#client-configuration)
  - [<span data-ttu-id="02ec8-121">Installatiescript</span><span class="sxs-lookup"><span data-stu-id="02ec8-121">Installer script</span></span>](#installer-script)
  - [<span data-ttu-id="02ec8-122">Problemen met de installatie van logboeken</span><span class="sxs-lookup"><span data-stu-id="02ec8-122">Log installation issues</span></span>](#log-installation-issues)
  - [<span data-ttu-id="02ec8-123">Upgrades van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="02ec8-123">Operating system upgrades</span></span>](#operating-system-upgrades)
  - [<span data-ttu-id="02ec8-124">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="02ec8-124">Uninstallation</span></span>](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="02ec8-125">Vereisten en systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="02ec8-125">Prerequisites and system requirements</span></span>

<span data-ttu-id="02ec8-126">Zie Microsoft Defender voor Eindpunt op [Linux](microsoft-defender-endpoint-linux.md) voordat u aan de slag gaat voor een beschrijving van vereisten en systeemvereisten voor de huidige softwareversie.</span><span class="sxs-lookup"><span data-stu-id="02ec8-126">Before you get started, see [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="configure-the-linux-software-repository"></a><span data-ttu-id="02ec8-127">De Linux-softwareopslagplaats configureren</span><span class="sxs-lookup"><span data-stu-id="02ec8-127">Configure the Linux software repository</span></span>

<span data-ttu-id="02ec8-128">Defender for Endpoint on Linux kan worden geïmplementeerd vanuit een van de volgende kanalen (hieronder aangeduid als *[kanaal]*): *insiders-fast*, *insiders-slow*, of *prod*. Elk van deze kanalen komt overeen met een Linux-softwareopslagplaats.</span><span class="sxs-lookup"><span data-stu-id="02ec8-128">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span> <span data-ttu-id="02ec8-129">Instructies voor het configureren van uw apparaat voor het gebruik van een van deze opslagplaatsen vindt u hieronder.</span><span class="sxs-lookup"><span data-stu-id="02ec8-129">Instructions for configuring your device to use one of these repositories are provided below.</span></span>

<span data-ttu-id="02ec8-130">De keuze van het kanaal bepaalt het type en de frequentie van de updates die op uw apparaat worden aangeboden.</span><span class="sxs-lookup"><span data-stu-id="02ec8-130">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="02ec8-131">Apparaten in *insiders-fast* zijn de eersten die updates en nieuwe functies ontvangen, later gevolgd door *insiders-slow* en ten laatste *door prod*.</span><span class="sxs-lookup"><span data-stu-id="02ec8-131">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="02ec8-132">Als u een voorbeeld van nieuwe functies wilt bekijken en vroegtijdig feedback wilt geven, wordt u aangeraden sommige apparaten in uw bedrijf te configureren om *insiders-fast* of *insiders-slow te gebruiken.*</span><span class="sxs-lookup"><span data-stu-id="02ec8-132">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="02ec8-133">Als u het kanaal na de eerste installatie overschakelt, moet het product opnieuw worden geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="02ec8-133">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="02ec8-134">Als u het productkanaal wilt wijzigen: verwijder het bestaande pakket, configureer het apparaat opnieuw om het nieuwe kanaal te gebruiken en volg de stappen in dit document om het pakket vanaf de nieuwe locatie te installeren.</span><span class="sxs-lookup"><span data-stu-id="02ec8-134">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

### <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="02ec8-135">RHEL en varianten (CentOS en Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="02ec8-135">RHEL and variants (CentOS and Oracle Linux)</span></span>

- <span data-ttu-id="02ec8-136">Installeren `yum-utils` als deze nog niet is geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="02ec8-136">Install `yum-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo yum install yum-utils
    ```

- <span data-ttu-id="02ec8-137">Noteer uw distributie en versie en identificeer de dichtstbijzijnde vermelding (per hoofd- en vervolgens secundaire vermelding) onder `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="02ec8-137">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span> <span data-ttu-id="02ec8-138">RHEL 7.9 is bijvoorbeeld dichter bij 7,4 dan bij 8.</span><span class="sxs-lookup"><span data-stu-id="02ec8-138">For instance, RHEL 7.9 is closer to 7.4 than to 8.</span></span>

    <span data-ttu-id="02ec8-139">Vervang *[distro]* en *[versie]* in de onderstaande opdrachten door de gegevens die u hebt geïdentificeerd:</span><span class="sxs-lookup"><span data-stu-id="02ec8-139">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    > [!NOTE]
    > <span data-ttu-id="02ec8-140">In het geval van Oracle Linux vervangt *u [distro] door* "rhel".</span><span class="sxs-lookup"><span data-stu-id="02ec8-140">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="02ec8-141">Als u bijvoorbeeld CentOS 7 gebruikt en Defender voor Eindpunt op Linux wilt implementeren via het *prod-kanaal:*</span><span class="sxs-lookup"><span data-stu-id="02ec8-141">For example, if you are running CentOS 7 and want to deploy Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    <span data-ttu-id="02ec8-142">Of als u nieuwe functies op geselecteerde apparaten wilt verkennen, kunt u MDE voor Linux implementeren voor *insiders-fast-kanaal:*</span><span class="sxs-lookup"><span data-stu-id="02ec8-142">Or if you wish to explore new features on selected devices, you might want to deploy MDE for Linux to *insiders-fast* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- <span data-ttu-id="02ec8-143">Installeer de openbare Microsoft GPG-sleutel:</span><span class="sxs-lookup"><span data-stu-id="02ec8-143">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- <span data-ttu-id="02ec8-144">Download en gebruik alle metagegevens voor de momenteel ingeschakelde yum-opslagplaatsen:</span><span class="sxs-lookup"><span data-stu-id="02ec8-144">Download and make usable all the metadata for the currently enabled yum repositories:</span></span>

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a><span data-ttu-id="02ec8-145">SLES en varianten</span><span class="sxs-lookup"><span data-stu-id="02ec8-145">SLES and variants</span></span>

- <span data-ttu-id="02ec8-146">Noteer uw distributie en versie en identificeer de dichtstbijzijnde vermelding(per hoofd- en vervolgens secundaire) voor deze vermelding onder `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="02ec8-146">Note your distribution and version, and identify the closest entry(by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="02ec8-147">Vervang *[distro]* en *[versie]* in de volgende opdrachten door de gegevens die u hebt geïdentificeerd:</span><span class="sxs-lookup"><span data-stu-id="02ec8-147">In the following commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="02ec8-148">Als u bijvoorbeeld SLES 12 gebruikt en MDE voor Linux wilt implementeren vanuit het *prod-kanaal:*</span><span class="sxs-lookup"><span data-stu-id="02ec8-148">For example, if you are running SLES 12 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- <span data-ttu-id="02ec8-149">Installeer de openbare Microsoft GPG-sleutel:</span><span class="sxs-lookup"><span data-stu-id="02ec8-149">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="02ec8-150">Ubuntu- en Debian-systemen</span><span class="sxs-lookup"><span data-stu-id="02ec8-150">Ubuntu and Debian systems</span></span>

- <span data-ttu-id="02ec8-151">Installeren `curl` als deze nog niet is geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="02ec8-151">Install `curl` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install curl
    ```

- <span data-ttu-id="02ec8-152">Installeren `libplist-utils` als deze nog niet is geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="02ec8-152">Install `libplist-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install libplist-utils
    ```

- <span data-ttu-id="02ec8-153">Noteer uw distributie en versie en identificeer de dichtstbijzijnde vermelding (per hoofd- en vervolgens secundaire vermelding) onder `https://packages.microsoft.com/config` .</span><span class="sxs-lookup"><span data-stu-id="02ec8-153">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config`.</span></span>

    <span data-ttu-id="02ec8-154">Vervang *[distro]* en *[versie]* in de onderstaande opdracht door de gegevens die u hebt geïdentificeerd:</span><span class="sxs-lookup"><span data-stu-id="02ec8-154">In the below command, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    <span data-ttu-id="02ec8-155">Als u bijvoorbeeld Ubuntu 18.04 gebruikt en MDE voor Linux wilt implementeren vanuit het *prod-kanaal:*</span><span class="sxs-lookup"><span data-stu-id="02ec8-155">For example, if you are running Ubuntu 18.04 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- <span data-ttu-id="02ec8-156">Installeer de configuratie van de opslagplaats:</span><span class="sxs-lookup"><span data-stu-id="02ec8-156">Install the repository configuration:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    <span data-ttu-id="02ec8-157">Als u bijvoorbeeld *prod-kanaal kiest:*</span><span class="sxs-lookup"><span data-stu-id="02ec8-157">For example, if you chose *prod* channel:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- <span data-ttu-id="02ec8-158">Installeer het `gpg` pakket als het nog niet is geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="02ec8-158">Install the `gpg` package if not already installed:</span></span>

    ```bash
    sudo apt-get install gpg
    ```

  <span data-ttu-id="02ec8-159">Als `gpg` deze niet beschikbaar is, installeert u `gnupg` .</span><span class="sxs-lookup"><span data-stu-id="02ec8-159">If `gpg` is not available, then install `gnupg`.</span></span>

- <span data-ttu-id="02ec8-160">Installeer de openbare Microsoft GPG-sleutel:</span><span class="sxs-lookup"><span data-stu-id="02ec8-160">Install the Microsoft GPG public key:</span></span>

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- <span data-ttu-id="02ec8-161">Installeer het https-stuurprogramma als dit nog niet aanwezig is:</span><span class="sxs-lookup"><span data-stu-id="02ec8-161">Install the https driver if it's not already present:</span></span>

    ```bash
    sudo apt-get install apt-transport-https
    ```

- <span data-ttu-id="02ec8-162">De metagegevens van de opslagplaats bijwerken:</span><span class="sxs-lookup"><span data-stu-id="02ec8-162">Update the repository metadata:</span></span>

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a><span data-ttu-id="02ec8-163">Toepassingsinstallatie</span><span class="sxs-lookup"><span data-stu-id="02ec8-163">Application installation</span></span>

- <span data-ttu-id="02ec8-164">RHEL en varianten (CentOS en Oracle Linux):</span><span class="sxs-lookup"><span data-stu-id="02ec8-164">RHEL and variants (CentOS and Oracle Linux):</span></span>

    ```bash
    sudo yum install mdatp
    ```

    <span data-ttu-id="02ec8-165">Als u meerdere Microsoft-opslagplaatsen hebt geconfigureerd op uw apparaat, kunt u specifiek zijn over welke opslagplaats u het pakket wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="02ec8-165">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="02ec8-166">In het volgende voorbeeld ziet u hoe u het pakket installeert vanuit het kanaal als u ook het `production` `insiders-fast` archiefkanaal hebt geconfigureerd op dit apparaat.</span><span class="sxs-lookup"><span data-stu-id="02ec8-166">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="02ec8-167">Deze situatie kan zich voor doen als u meerdere Microsoft-producten op uw apparaat gebruikt.</span><span class="sxs-lookup"><span data-stu-id="02ec8-167">This situation can happen if you are using multiple Microsoft products on your device.</span></span> <span data-ttu-id="02ec8-168">Afhankelijk van de distributie en de versie van uw server, kan de alias van de opslagplaats anders zijn dan de alias in het volgende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="02ec8-168">Depending on the distribution and the version of your server, the repository alias might be different than the one in the following example.</span></span>

    ```bash
    # list all repositories
    yum repolist
    ```
    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```
    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- <span data-ttu-id="02ec8-169">SLES en varianten:</span><span class="sxs-lookup"><span data-stu-id="02ec8-169">SLES and variants:</span></span>

    ```bash
    sudo zypper install mdatp
    ```

    <span data-ttu-id="02ec8-170">Als u meerdere Microsoft-opslagplaatsen hebt geconfigureerd op uw apparaat, kunt u specifiek zijn over welke opslagplaats u het pakket wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="02ec8-170">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="02ec8-171">In het volgende voorbeeld ziet u hoe u het pakket installeert vanuit het kanaal als u ook het `production` `insiders-fast` archiefkanaal hebt geconfigureerd op dit apparaat.</span><span class="sxs-lookup"><span data-stu-id="02ec8-171">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="02ec8-172">Deze situatie kan zich voor doen als u meerdere Microsoft-producten op uw apparaat gebruikt.</span><span class="sxs-lookup"><span data-stu-id="02ec8-172">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...
    ```
    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- <span data-ttu-id="02ec8-173">Ubuntu- en Debian-systeem:</span><span class="sxs-lookup"><span data-stu-id="02ec8-173">Ubuntu and Debian system:</span></span>

    ```bash
    sudo apt-get install mdatp
    ```

    <span data-ttu-id="02ec8-174">Als u meerdere Microsoft-opslagplaatsen hebt geconfigureerd op uw apparaat, kunt u specifiek zijn over welke opslagplaats u het pakket wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="02ec8-174">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="02ec8-175">In het volgende voorbeeld ziet u hoe u het pakket installeert vanuit het kanaal als u ook het `production` `insiders-fast` archiefkanaal hebt geconfigureerd op dit apparaat.</span><span class="sxs-lookup"><span data-stu-id="02ec8-175">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="02ec8-176">Deze situatie kan zich voor doen als u meerdere Microsoft-producten op uw apparaat gebruikt.</span><span class="sxs-lookup"><span data-stu-id="02ec8-176">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    cat /etc/apt/sources.list.d/*
    ```
    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```
    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="02ec8-177">Het onboarding-pakket downloaden</span><span class="sxs-lookup"><span data-stu-id="02ec8-177">Download the onboarding package</span></span>

<span data-ttu-id="02ec8-178">Download het onboarding-pakket van Microsoft Defender-beveiligingscentrum:</span><span class="sxs-lookup"><span data-stu-id="02ec8-178">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="02ec8-179">Ga Microsoft Defender-beveiligingscentrum naar Instellingen > **Device Management > Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="02ec8-179">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="02ec8-180">Selecteer in de eerste vervolgkeuzelijst **Linux Server** als besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="02ec8-180">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="02ec8-181">Selecteer in de tweede vervolgkeuzelijst Lokaal script (voor maximaal **10 apparaten)** als implementatiemethode.</span><span class="sxs-lookup"><span data-stu-id="02ec8-181">In the second drop-down menu, select **Local Script (for up to 10 devices)** as the deployment method.</span></span>
3. <span data-ttu-id="02ec8-182">Selecteer **Onboarding-pakket downloaden.**</span><span class="sxs-lookup"><span data-stu-id="02ec8-182">Select **Download onboarding package**.</span></span> <span data-ttu-id="02ec8-183">Sla het bestand op als WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="02ec8-183">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender-beveiligingscentrum schermafbeelding](images/atp-portal-onboarding-linux.png)

4. <span data-ttu-id="02ec8-185">Controleer in een opdrachtprompt of u het bestand hebt.</span><span class="sxs-lookup"><span data-stu-id="02ec8-185">From a command prompt, verify that you have the file.</span></span>
    <span data-ttu-id="02ec8-186">Haal de inhoud van het archief op:</span><span class="sxs-lookup"><span data-stu-id="02ec8-186">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```


## <a name="client-configuration"></a><span data-ttu-id="02ec8-187">Clientconfiguratie</span><span class="sxs-lookup"><span data-stu-id="02ec8-187">Client configuration</span></span>

1. <span data-ttu-id="02ec8-188">Kopieer MicrosoftDefenderATPOnboardingLinuxServer.py naar het doelapparaat.</span><span class="sxs-lookup"><span data-stu-id="02ec8-188">Copy MicrosoftDefenderATPOnboardingLinuxServer.py to the target device.</span></span>

    <span data-ttu-id="02ec8-189">In eerste instantie is het clientapparaat niet gekoppeld aan een organisatie.</span><span class="sxs-lookup"><span data-stu-id="02ec8-189">Initially the client device is not associated with an organization.</span></span> <span data-ttu-id="02ec8-190">Houd er rekening mee *dat het orgId-kenmerk* leeg is:</span><span class="sxs-lookup"><span data-stu-id="02ec8-190">Note that the *orgId* attribute is blank:</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="02ec8-191">Voer MicrosoftDefenderATPOnboardingLinuxServer.py uit en houd er rekening mee dat u deze opdracht moet hebben geïnstalleerd `python` op het apparaat:</span><span class="sxs-lookup"><span data-stu-id="02ec8-191">Run MicrosoftDefenderATPOnboardingLinuxServer.py, and note that, in order to run this command, you must have `python` installed on the device:</span></span>

    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. <span data-ttu-id="02ec8-192">Controleer of het apparaat nu is gekoppeld aan uw organisatie en rapporteer een geldige organisatie-id:</span><span class="sxs-lookup"><span data-stu-id="02ec8-192">Verify that the device is now associated with your organization and reports a valid organization identifier:</span></span>

    ```bash
    mdatp health --field org_id
    ```

4. <span data-ttu-id="02ec8-193">Enkele minuten nadat u de installatie hebt voltooid, kunt u de status zien door de volgende opdracht uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="02ec8-193">A few minutes after you complete the installation, you can see the status by running the following command.</span></span> <span data-ttu-id="02ec8-194">Een retourwaarde van `1` geeft aan dat het product werkt zoals verwacht:</span><span class="sxs-lookup"><span data-stu-id="02ec8-194">A return value of `1` denotes that the product is functioning as expected:</span></span>

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="02ec8-195">Wanneer het product voor het eerst wordt gestart, worden de meest recente antimalwaredefinities gedownload.</span><span class="sxs-lookup"><span data-stu-id="02ec8-195">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="02ec8-196">Afhankelijk van uw internetverbinding kan dit enkele minuten duren.</span><span class="sxs-lookup"><span data-stu-id="02ec8-196">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="02ec8-197">Gedurende deze periode retourneert de bovenstaande opdracht een waarde van `false` .</span><span class="sxs-lookup"><span data-stu-id="02ec8-197">During this time the above command returns a value of `false`.</span></span> <span data-ttu-id="02ec8-198">U kunt de status van de definitie-update controleren met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="02ec8-198">You can check the status of the definition update using the following command:</span></span>
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > <span data-ttu-id="02ec8-199">Houd er rekening mee dat u mogelijk ook een proxy moet configureren na het voltooien van de eerste installatie.</span><span class="sxs-lookup"><span data-stu-id="02ec8-199">Please note that you may also need to configure a proxy after completing the initial installation.</span></span> <span data-ttu-id="02ec8-200">Zie [Defender voor eindpunt configureren op Linux voor statische proxydetectie: Configuratie na installatie](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span><span class="sxs-lookup"><span data-stu-id="02ec8-200">See [Configure Defender for Endpoint on Linux for static proxy discovery: Post-installation configuration](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span></span>

5. <span data-ttu-id="02ec8-201">Voer een detectietest uit om te controleren of het apparaat goed is onboarded en rapporteert aan de service.</span><span class="sxs-lookup"><span data-stu-id="02ec8-201">Run a detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="02ec8-202">Voer de volgende stappen uit op het nieuwe onboarded-apparaat:</span><span class="sxs-lookup"><span data-stu-id="02ec8-202">Perform the following steps on the newly onboarded device:</span></span>

    - <span data-ttu-id="02ec8-203">Zorg ervoor dat realtimebeveiliging is ingeschakeld (aangegeven door een resultaat van het uitvoeren van `1` de volgende opdracht):</span><span class="sxs-lookup"><span data-stu-id="02ec8-203">Ensure that real-time protection is enabled (denoted by a result of `1` from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - <span data-ttu-id="02ec8-204">Open een terminalvenster.</span><span class="sxs-lookup"><span data-stu-id="02ec8-204">Open a Terminal window.</span></span> <span data-ttu-id="02ec8-205">Kopieer en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="02ec8-205">Copy and execute the following command:</span></span>

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - <span data-ttu-id="02ec8-206">Het bestand had in quarantaine moeten zijn geplaatst door Defender voor Eindpunt op Linux.</span><span class="sxs-lookup"><span data-stu-id="02ec8-206">The file should have been quarantined by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="02ec8-207">Gebruik de volgende opdracht om alle gedetecteerde bedreigingen op te geven:</span><span class="sxs-lookup"><span data-stu-id="02ec8-207">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

## <a name="installer-script"></a><span data-ttu-id="02ec8-208">Installatiescript</span><span class="sxs-lookup"><span data-stu-id="02ec8-208">Installer script</span></span>

<span data-ttu-id="02ec8-209">U kunt ook een geautomatiseerd installatieprogramma [bash-script gebruiken](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) dat beschikbaar is in onze [openbare GitHub repository.](https://github.com/microsoft/mdatp-xplat/)</span><span class="sxs-lookup"><span data-stu-id="02ec8-209">Alternatively, you can use an automated [installer bash script](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) provided in our [public GitHub repository](https://github.com/microsoft/mdatp-xplat/).</span></span>
<span data-ttu-id="02ec8-210">Het script identificeert de distributie en versie en stelt het apparaat in om het nieuwste pakket op te halen en te installeren.</span><span class="sxs-lookup"><span data-stu-id="02ec8-210">The script identifies the distribution and version, and sets up the device to pull the latest package and install it.</span></span>
<span data-ttu-id="02ec8-211">U kunt ook aan boord gaan met een meegeleverd script.</span><span class="sxs-lookup"><span data-stu-id="02ec8-211">You can also onboard with a provided script.</span></span>

```bash
❯ ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

<span data-ttu-id="02ec8-212">Lees hier [meer.](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation)</span><span class="sxs-lookup"><span data-stu-id="02ec8-212">Read more [here](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="02ec8-213">Problemen met de installatie van logboeken</span><span class="sxs-lookup"><span data-stu-id="02ec8-213">Log installation issues</span></span>

<span data-ttu-id="02ec8-214">Zie [Installatieproblemen in logboeken](linux-resources.md#log-installation-issues) voor meer informatie over het vinden van het automatisch gegenereerde logboek dat door het installatieprogramma wordt gemaakt wanneer er een fout optreedt.</span><span class="sxs-lookup"><span data-stu-id="02ec8-214">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="02ec8-215">Upgrades van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="02ec8-215">Operating system upgrades</span></span>

<span data-ttu-id="02ec8-216">Wanneer u uw besturingssysteem upgradet naar een nieuwe hoofdversie, moet u Eerst Defender voor Eindpunt op Linux verwijderen, de upgrade installeren en defender voor eindpunt opnieuw configureren op Linux op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="02ec8-216">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a><span data-ttu-id="02ec8-217">Migreren van Insiders-Fast naar productiekanaal</span><span class="sxs-lookup"><span data-stu-id="02ec8-217">How to migrate from Insiders-Fast to Production channel</span></span>

1. <span data-ttu-id="02ec8-218">Verwijder de versie 'Insiders-Fast-kanaal' van MDE voor Linux.</span><span class="sxs-lookup"><span data-stu-id="02ec8-218">Uninstall the “Insiders-Fast channel” version of MDE for Linux.</span></span>

    ``
    sudo yum remove mdatp
    ``

1. <span data-ttu-id="02ec8-219">De MDE voor Linux-Insiders-Fast uitschakelen  ``
    sudo yum repolist
    ``</span><span class="sxs-lookup"><span data-stu-id="02ec8-219">Disable the MDE for Linux Insiders-Fast repo  ``
    sudo yum repolist
 ``</span></span>

    > [!NOTE]
    > <span data-ttu-id="02ec8-220">De uitvoer moet 'packages-microsoft-com-fast-prod' laten zien.</span><span class="sxs-lookup"><span data-stu-id="02ec8-220">The output should show “packages-microsoft-com-fast-prod”.</span></span>

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. <span data-ttu-id="02ec8-221">Herdeploy MDE voor Linux met behulp van het 'Productiekanaal'.</span><span class="sxs-lookup"><span data-stu-id="02ec8-221">Redeploy MDE for Linux using the “Production channel”.</span></span>


## <a name="uninstallation"></a><span data-ttu-id="02ec8-222">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="02ec8-222">Uninstallation</span></span>

<span data-ttu-id="02ec8-223">Zie [Verwijderen voor](linux-resources.md#uninstall) meer informatie over het verwijderen van Defender voor Eindpunt op Linux van clientapparaten.</span><span class="sxs-lookup"><span data-stu-id="02ec8-223">See [Uninstall](linux-resources.md#uninstall) for details on how to remove Defender for Endpoint on Linux from client devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="02ec8-224">Zie ook</span><span class="sxs-lookup"><span data-stu-id="02ec8-224">See also</span></span>
- [<span data-ttu-id="02ec8-225">Statusproblemen van agent onderzoeken</span><span class="sxs-lookup"><span data-stu-id="02ec8-225">Investigate agent health issues</span></span>](health-status.md)
