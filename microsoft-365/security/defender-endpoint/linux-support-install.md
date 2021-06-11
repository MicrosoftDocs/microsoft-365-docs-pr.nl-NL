---
title: Installatieproblemen oplossen voor Microsoft Defender voor Eindpunt op Linux
ms.reviewer: ''
description: Installatieproblemen oplossen voor Microsoft Defender voor Eindpunt op Linux
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installatie
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
ms.openlocfilehash: dc1e8707dc0810c0986698674a64e969792b5fb8
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311230"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="a8a30-104">Installatieproblemen oplossen voor Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="a8a30-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a8a30-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a8a30-105">**Applies to:**</span></span>
- [<span data-ttu-id="a8a30-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a8a30-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a8a30-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8a30-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a8a30-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a8a30-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a8a30-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a8a30-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="a8a30-110">Controleren of de installatie is geslaagd</span><span class="sxs-lookup"><span data-stu-id="a8a30-110">Verify if installation succeeded</span></span>

<span data-ttu-id="a8a30-111">Een fout in de installatie kan al dan niet leiden tot een duidelijke foutmelding door de package manager.</span><span class="sxs-lookup"><span data-stu-id="a8a30-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="a8a30-112">Als u wilt controleren of de installatie is gelukt, kunt u de installatielogboeken verkrijgen en controleren met behulp van:</span><span class="sxs-lookup"><span data-stu-id="a8a30-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

```bash
 sudo journalctl --no-pager | grep 'microsoft-mdatp' > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
```

<span data-ttu-id="a8a30-113">Een uitvoer van de vorige opdracht met de juiste datum en tijd van de installatie duidt op succes.</span><span class="sxs-lookup"><span data-stu-id="a8a30-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="a8a30-114">Controleer ook de [clientconfiguratie om](linux-install-manually.md#client-configuration) de status van het product te controleren en het TEKSTBESTAND VAN EICAR te detecteren.</span><span class="sxs-lookup"><span data-stu-id="a8a30-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="a8a30-115">Zorg ervoor dat u het juiste pakket hebt</span><span class="sxs-lookup"><span data-stu-id="a8a30-115">Make sure you have the correct package</span></span>

<span data-ttu-id="a8a30-116">Houd er rekening mee dat het pakket dat u installeert overeenkomt met de hostdistributie en -versie.</span><span class="sxs-lookup"><span data-stu-id="a8a30-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="a8a30-117">pakket</span><span class="sxs-lookup"><span data-stu-id="a8a30-117">package</span></span>                       | <span data-ttu-id="a8a30-118">distributie</span><span class="sxs-lookup"><span data-stu-id="a8a30-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="a8a30-119">mdatp-rhel8. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="a8a30-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="a8a30-120">Oracle, RHEL en CentOS 8.x</span><span class="sxs-lookup"><span data-stu-id="a8a30-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="a8a30-121">mdatp-sles12. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="a8a30-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="a8a30-122">SuSE Linux Enterprise Server 12.x</span><span class="sxs-lookup"><span data-stu-id="a8a30-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="a8a30-123">mdatp-sles15. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="a8a30-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="a8a30-124">SuSE Linux Enterprise Server 15.x</span><span class="sxs-lookup"><span data-stu-id="a8a30-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="a8a30-125">mdatp. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="a8a30-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="a8a30-126">Oracle, RHEL en CentOS 7.x</span><span class="sxs-lookup"><span data-stu-id="a8a30-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="a8a30-127">mdatp. Linux.x86_64.deb</span><span class="sxs-lookup"><span data-stu-id="a8a30-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="a8a30-128">Debian en Ubuntu 16.04, 18.04 en 20.04</span><span class="sxs-lookup"><span data-stu-id="a8a30-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="a8a30-129">Voor [handmatige implementatie](linux-install-manually.md)moet u ervoor zorgen dat de juiste distributie en versie zijn gekozen.</span><span class="sxs-lookup"><span data-stu-id="a8a30-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="a8a30-130">Installatie mislukt</span><span class="sxs-lookup"><span data-stu-id="a8a30-130">Installation failed</span></span>

<span data-ttu-id="a8a30-131">Controleer of de mdatp-service wordt uitgevoerd:</span><span class="sxs-lookup"><span data-stu-id="a8a30-131">Check if the mdatp service is running:</span></span>

```bash
systemctl status mdatp
```

```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="a8a30-132">Stappen om problemen op te lossen als de mdatp-service niet wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="a8a30-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="a8a30-133">Controleer of 'mdatp'-gebruiker bestaat:</span><span class="sxs-lookup"><span data-stu-id="a8a30-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="a8a30-134">Als er geen uitvoer is, voer dan</span><span class="sxs-lookup"><span data-stu-id="a8a30-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="a8a30-135">Probeer de service in te stellen en opnieuw te starten met behulp van:</span><span class="sxs-lookup"><span data-stu-id="a8a30-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="a8a30-136">Als mdatp.service niet wordt gevonden bij het uitvoeren van de vorige opdracht, voer dan het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="a8a30-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="a8a30-137">waar `<systemd_path>` is `/lib/systemd/system` voor Ubuntu- en Debian-distributies en `/usr/lib/systemd/system` voor Rhel, CentOS, Oracle en SLES.</span><span class="sxs-lookup"><span data-stu-id="a8a30-137">where `<systemd_path>` is `/lib/systemd/system` for Ubuntu and Debian distributions and `/usr/lib/systemd/system` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="a8a30-138">Vervolgens stap 2 opnieuw.</span><span class="sxs-lookup"><span data-stu-id="a8a30-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="a8a30-139">Als de bovenstaande stappen niet werken, controleert u of SELinux is geïnstalleerd en in de afdwingmodus.</span><span class="sxs-lookup"><span data-stu-id="a8a30-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="a8a30-140">Als dat het het beste is, kunt u de modus instellen op een permissieve (bij voorkeur) of uitgeschakelde modus.</span><span class="sxs-lookup"><span data-stu-id="a8a30-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="a8a30-141">U kunt dit doen door de parameter in te stellen op `SELINUX` 'permissief' of 'uitgeschakeld' in het `/etc/selinux/config` bestand, gevolgd door opnieuw opstarten.</span><span class="sxs-lookup"><span data-stu-id="a8a30-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="a8a30-142">Controleer de man-pagina van selinux voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a8a30-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="a8a30-143">Start nu de mdatp-service opnieuw met stap 2.</span><span class="sxs-lookup"><span data-stu-id="a8a30-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="a8a30-144">U kunt de configuratiewijziging echter direct herstellen om beveiligingsredenen nadat u deze hebt geprobeerd en opnieuw hebt opgestart.</span><span class="sxs-lookup"><span data-stu-id="a8a30-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="a8a30-145">Als `/opt` adreslijst een symbolische koppeling is, maakt u een koppelingskoppeling voor `/opt/microsoft` .</span><span class="sxs-lookup"><span data-stu-id="a8a30-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="a8a30-146">Controleer of de daemon uitvoerbare machtiging heeft.</span><span class="sxs-lookup"><span data-stu-id="a8a30-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="a8a30-147">Als de daemon geen uitvoerbare machtigingen heeft, kunt u deze uitvoerbaar maken met behulp van:</span><span class="sxs-lookup"><span data-stu-id="a8a30-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="a8a30-148">en u kunt stap 2 opnieuw uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="a8a30-148">and retry running step 2.</span></span>

7. <span data-ttu-id="a8a30-149">Zorg ervoor dat het bestandssysteem met wdavdaemon niet is bevestigd met 'noexec'.</span><span class="sxs-lookup"><span data-stu-id="a8a30-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="a8a30-150">Als de mdatp-service wordt uitgevoerd, maar de detectie van EICAR-tekstbestand niet werkt</span><span class="sxs-lookup"><span data-stu-id="a8a30-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="a8a30-151">Controleer het bestandssysteemtype met behulp van:</span><span class="sxs-lookup"><span data-stu-id="a8a30-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="a8a30-152">Momenteel ondersteunde bestandssystemen voor on-access-activiteiten worden hier [weergegeven.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="a8a30-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="a8a30-153">Bestanden buiten deze bestandssystemen worden niet gescand.</span><span class="sxs-lookup"><span data-stu-id="a8a30-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="a8a30-154">Opdrachtregelhulpmiddel 'mdatp' werkt niet</span><span class="sxs-lookup"><span data-stu-id="a8a30-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="a8a30-155">Als het uitvoeren van het opdrachtregelhulpmiddel `mdatp` een fout `command not found` geeft, voer dan de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="a8a30-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="a8a30-156">en probeer het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="a8a30-156">and try again.</span></span>

    <span data-ttu-id="a8a30-157">Als geen van de bovenstaande stappen helpt, verzamelt u de diagnostische logboeken:</span><span class="sxs-lookup"><span data-stu-id="a8a30-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="a8a30-158">Pad naar een zip-bestand dat de logboeken bevat, wordt weergegeven als uitvoer.</span><span class="sxs-lookup"><span data-stu-id="a8a30-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="a8a30-159">Contact op met onze klantenondersteuning met deze logboeken.</span><span class="sxs-lookup"><span data-stu-id="a8a30-159">Reach out to our customer support with these logs.</span></span>
