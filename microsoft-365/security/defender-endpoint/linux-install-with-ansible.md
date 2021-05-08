---
title: Microsoft Defender voor eindpunt implementeren op Linux met Ansible
ms.reviewer: ''
description: Hier wordt beschreven hoe u Microsoft Defender voor Eindpunt op Linux implementeert met Ansible.
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
ms.openlocfilehash: 9cd544ca3d714ea46c74e10f8aba5e46dc0e1b35
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280991"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a><span data-ttu-id="34f09-104">Microsoft Defender voor eindpunt implementeren op Linux met Ansible</span><span class="sxs-lookup"><span data-stu-id="34f09-104">Deploy Microsoft Defender for Endpoint on Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="34f09-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="34f09-105">**Applies to:**</span></span>
- [<span data-ttu-id="34f09-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="34f09-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="34f09-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34f09-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="34f09-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="34f09-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="34f09-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="34f09-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="34f09-110">In dit artikel wordt beschreven hoe u Defender voor Eindpunt op Linux implementeert met Ansible.</span><span class="sxs-lookup"><span data-stu-id="34f09-110">This article describes how to deploy Defender for Endpoint on Linux using Ansible.</span></span> <span data-ttu-id="34f09-111">Voor een geslaagde implementatie moeten alle volgende taken zijn voltooid:</span><span class="sxs-lookup"><span data-stu-id="34f09-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="34f09-112">Het onboarding-pakket downloaden</span><span class="sxs-lookup"><span data-stu-id="34f09-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="34f09-113">Ansible YAML-bestanden maken</span><span class="sxs-lookup"><span data-stu-id="34f09-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="34f09-114">Implementatie</span><span class="sxs-lookup"><span data-stu-id="34f09-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="34f09-115">Verwijzingen</span><span class="sxs-lookup"><span data-stu-id="34f09-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="34f09-116">Vereisten en systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="34f09-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="34f09-117">Voordat u aan de slag gaat, bekijkt u de [hoofdpagina](microsoft-defender-endpoint-linux.md) van Defender voor Eindpunt op Linux voor een beschrijving van vereisten en systeemvereisten voor de huidige softwareversie.</span><span class="sxs-lookup"><span data-stu-id="34f09-117">Before you get started, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="34f09-118">Bovendien moet u voor Ansible-implementatie bekend zijn met Ansible-beheertaken, Ansible configureren en weten hoe u playbooks en taken implementeert.</span><span class="sxs-lookup"><span data-stu-id="34f09-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="34f09-119">Ansible heeft veel manieren om dezelfde taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="34f09-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="34f09-120">In deze instructies wordt ervan uitgenomen dat ondersteunde Ansible-modules beschikbaar zijn, zoals *apt* en *unarchive om* het pakket te implementeren.</span><span class="sxs-lookup"><span data-stu-id="34f09-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="34f09-121">Uw organisatie kan een andere werkstroom gebruiken.</span><span class="sxs-lookup"><span data-stu-id="34f09-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="34f09-122">Raadpleeg de [Ansible-documentatie](https://docs.ansible.com/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="34f09-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="34f09-123">Ansible moet op ten minste één computer zijn geïnstalleerd (Ansible noemt dit het besturingselement knooppunt).</span><span class="sxs-lookup"><span data-stu-id="34f09-123">Ansible needs to be installed on at least one computer (Ansible calls this the control node).</span></span>
- <span data-ttu-id="34f09-124">SSH moet zijn geconfigureerd voor een beheerdersaccount tussen het knooppunt van het besturingselement en alle beheerde knooppunten (apparaten waar Defender voor Eindpunt op is geïnstalleerd) en het wordt aanbevolen om te worden geconfigureerd met verificatie met openbare sleutel.</span><span class="sxs-lookup"><span data-stu-id="34f09-124">SSH must be configured for an administrator account between the control node and all managed nodes (devices that will have Defender for Endpoint installed on them), and it is recommended to be configured with public key authentication.</span></span>
- <span data-ttu-id="34f09-125">De volgende software moet zijn geïnstalleerd op alle beheerde knooppunten:</span><span class="sxs-lookup"><span data-stu-id="34f09-125">The following software must be installed on all managed nodes:</span></span>
  - <span data-ttu-id="34f09-126">krul</span><span class="sxs-lookup"><span data-stu-id="34f09-126">curl</span></span>
  - <span data-ttu-id="34f09-127">python-apt</span><span class="sxs-lookup"><span data-stu-id="34f09-127">python-apt</span></span>

- <span data-ttu-id="34f09-128">Alle beheerde knooppunten moeten worden weergegeven in de volgende indeling in het `/etc/ansible/hosts` of relevante bestand:</span><span class="sxs-lookup"><span data-stu-id="34f09-128">All managed nodes must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="34f09-129">Pingtest:</span><span class="sxs-lookup"><span data-stu-id="34f09-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="34f09-130">Het onboarding-pakket downloaden</span><span class="sxs-lookup"><span data-stu-id="34f09-130">Download the onboarding package</span></span>

<span data-ttu-id="34f09-131">Download het onboarding-pakket van Microsoft Defender-beveiligingscentrum:</span><span class="sxs-lookup"><span data-stu-id="34f09-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="34f09-132">Ga Microsoft Defender-beveiligingscentrum naar Instellingen > **Device Management > Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="34f09-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="34f09-133">Selecteer in de eerste vervolgkeuzelijst **Linux Server** als besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="34f09-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="34f09-134">Selecteer in de tweede vervolgkeuzelijst **Uw voorkeursprogramma** voor configuratiebeheer voor Linux als implementatiemethode.</span><span class="sxs-lookup"><span data-stu-id="34f09-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="34f09-135">Selecteer **Onboarding-pakket downloaden.**</span><span class="sxs-lookup"><span data-stu-id="34f09-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="34f09-136">Sla het bestand op als WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="34f09-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender-beveiligingscentrum schermafbeelding](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="34f09-138">Controleer in een opdrachtprompt of u het bestand hebt.</span><span class="sxs-lookup"><span data-stu-id="34f09-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="34f09-139">Haal de inhoud van het archief op:</span><span class="sxs-lookup"><span data-stu-id="34f09-139">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="34f09-140">Ansible YAML-bestanden maken</span><span class="sxs-lookup"><span data-stu-id="34f09-140">Create Ansible YAML files</span></span>

<span data-ttu-id="34f09-141">Maak een subtaak of rolbestanden die bijdragen aan een speelboek of taak.</span><span class="sxs-lookup"><span data-stu-id="34f09-141">Create a subtask or role files that contribute to a playbook or task.</span></span>

- <span data-ttu-id="34f09-142">Maak de onboarding-taak: `onboarding_setup.yml`</span><span class="sxs-lookup"><span data-stu-id="34f09-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- <span data-ttu-id="34f09-143">Voeg de defender voor eindpuntopslagplaats en de sleutel toe.</span><span class="sxs-lookup"><span data-stu-id="34f09-143">Add the Defender for Endpoint repository and key.</span></span>

    <span data-ttu-id="34f09-144">Defender for Endpoint on Linux kan worden geïmplementeerd vanuit een van de volgende kanalen (hieronder aangeduid als *[kanaal]*): *insiders-fast*, *insiders-slow*, of *prod*. Elk van deze kanalen komt overeen met een Linux-softwareopslagplaats.</span><span class="sxs-lookup"><span data-stu-id="34f09-144">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="34f09-145">De keuze van het kanaal bepaalt het type en de frequentie van de updates die op uw apparaat worden aangeboden.</span><span class="sxs-lookup"><span data-stu-id="34f09-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="34f09-146">Apparaten in *insiders-fast* zijn de eersten die updates en nieuwe functies ontvangen, later gevolgd door *insiders-slow* en ten laatste *door prod*.</span><span class="sxs-lookup"><span data-stu-id="34f09-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="34f09-147">Als u een voorbeeld van nieuwe functies wilt bekijken en vroegtijdig feedback wilt geven, wordt u aangeraden sommige apparaten in uw bedrijf te configureren om *insiders-fast* of *insiders-slow te gebruiken.*</span><span class="sxs-lookup"><span data-stu-id="34f09-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="34f09-148">Als u het kanaal na de eerste installatie overschakelt, moet het product opnieuw worden geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="34f09-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="34f09-149">Als u het productkanaal wilt wijzigen: verwijder het bestaande pakket, configureer het apparaat opnieuw om het nieuwe kanaal te gebruiken en volg de stappen in dit document om het pakket vanaf de nieuwe locatie te installeren.</span><span class="sxs-lookup"><span data-stu-id="34f09-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="34f09-150">Noteer uw distributie en versie en identificeer de dichtstbijzijnde vermelding voor de versie onder `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="34f09-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="34f09-151">Vervang *[distro]* en *[versie]* in de volgende opdrachten door de gegevens die u hebt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="34f09-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="34f09-152">In het geval van Oracle Linux vervangt *u [distro] door* "rhel".</span><span class="sxs-lookup"><span data-stu-id="34f09-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- <span data-ttu-id="34f09-153">Maak de Ansible-installatie en verwijder YAML-bestanden.</span><span class="sxs-lookup"><span data-stu-id="34f09-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="34f09-154">Voor apt-gebaseerde distributies gebruikt u het volgende YAML-bestand:</span><span class="sxs-lookup"><span data-stu-id="34f09-154">For apt-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - <span data-ttu-id="34f09-155">Voor dnf-gebaseerde distributies gebruikt u het volgende YAML-bestand:</span><span class="sxs-lookup"><span data-stu-id="34f09-155">For dnf-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a><span data-ttu-id="34f09-156">Implementatie</span><span class="sxs-lookup"><span data-stu-id="34f09-156">Deployment</span></span>

<span data-ttu-id="34f09-157">Voer nu de takenbestanden uit onder `/etc/ansible/playbooks/` of relevante adreslijst.</span><span class="sxs-lookup"><span data-stu-id="34f09-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="34f09-158">Installatie:</span><span class="sxs-lookup"><span data-stu-id="34f09-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="34f09-159">Wanneer het product voor het eerst wordt gestart, worden de meest recente antimalwaredefinities gedownload.</span><span class="sxs-lookup"><span data-stu-id="34f09-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="34f09-160">Afhankelijk van uw internetverbinding kan dit enkele minuten duren.</span><span class="sxs-lookup"><span data-stu-id="34f09-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="34f09-161">Validatie/configuratie:</span><span class="sxs-lookup"><span data-stu-id="34f09-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="34f09-162">Verwijderen:</span><span class="sxs-lookup"><span data-stu-id="34f09-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="34f09-163">Problemen met de installatie van logboeken</span><span class="sxs-lookup"><span data-stu-id="34f09-163">Log installation issues</span></span>

<span data-ttu-id="34f09-164">Zie [Installatieproblemen in logboeken](linux-resources.md#log-installation-issues) voor meer informatie over het vinden van het automatisch gegenereerde logboek dat door het installatieprogramma wordt gemaakt wanneer er een fout optreedt.</span><span class="sxs-lookup"><span data-stu-id="34f09-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="34f09-165">Upgrades van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="34f09-165">Operating system upgrades</span></span>

<span data-ttu-id="34f09-166">Wanneer u uw besturingssysteem upgradet naar een nieuwe hoofdversie, moet u Eerst Defender voor Eindpunt op Linux verwijderen, de upgrade installeren en defender voor eindpunt opnieuw configureren op Linux op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="34f09-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="34f09-167">Verwijzingen</span><span class="sxs-lookup"><span data-stu-id="34f09-167">References</span></span>

- [<span data-ttu-id="34f09-168">YUM-opslagplaatsen toevoegen of verwijderen</span><span class="sxs-lookup"><span data-stu-id="34f09-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [<span data-ttu-id="34f09-169">Pakketten beheren met de dnf package manager</span><span class="sxs-lookup"><span data-stu-id="34f09-169">Manage packages with the dnf package manager</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [<span data-ttu-id="34f09-170">APT-opslagplaatsen toevoegen en verwijderen</span><span class="sxs-lookup"><span data-stu-id="34f09-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [<span data-ttu-id="34f09-171">Apt-pakketten beheren</span><span class="sxs-lookup"><span data-stu-id="34f09-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a><span data-ttu-id="34f09-172">Zie ook</span><span class="sxs-lookup"><span data-stu-id="34f09-172">See also</span></span>
- [<span data-ttu-id="34f09-173">Problemen met de status van agent onderzoeken</span><span class="sxs-lookup"><span data-stu-id="34f09-173">Investigate agent health issues</span></span>](health-status.md)