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
ms.openlocfilehash: 13bcbc74fcb9c540c45a6eec7e7e506b6943986a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841788"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Microsoft Defender voor eindpunt implementeren op Linux met Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In dit artikel wordt beschreven hoe u Defender voor Eindpunt op Linux implementeert met Ansible. Voor een geslaagde implementatie moeten alle volgende taken zijn voltooid:

- [Het onboarding-pakket downloaden](#download-the-onboarding-package)
- [Ansible YAML-bestanden maken](#create-ansible-yaml-files)
- [Implementatie](#deployment)
- [Verwijzingen](#references)

## <a name="prerequisites-and-system-requirements"></a>Vereisten en systeemvereisten

Voordat u aan de slag gaat, bekijkt u de [hoofdpagina](microsoft-defender-endpoint-linux.md) van Defender voor Eindpunt op Linux voor een beschrijving van vereisten en systeemvereisten voor de huidige softwareversie.

Bovendien moet u voor Ansible-implementatie bekend zijn met Ansible-beheertaken, Ansible configureren en weten hoe u playbooks en taken implementeert. Ansible heeft veel manieren om dezelfde taak uit te voeren. In deze instructies wordt ervan uitgenomen dat ondersteunde Ansible-modules beschikbaar zijn, zoals *apt* en *unarchive om* het pakket te implementeren. Uw organisatie kan een andere werkstroom gebruiken. Raadpleeg de [Ansible-documentatie](https://docs.ansible.com/) voor meer informatie.

- Ansible moet op ten minste één computer zijn geïnstalleerd (Ansible noemt dit het besturingselement knooppunt).
- SSH moet zijn geconfigureerd voor een beheerdersaccount tussen het knooppunt van het besturingselement en alle beheerde knooppunten (apparaten waar Defender voor Eindpunt op is geïnstalleerd) en het wordt aanbevolen om te worden geconfigureerd met verificatie met openbare sleutel.
- De volgende software moet zijn geïnstalleerd op alle beheerde knooppunten:
  - krul
  - python-apt

- Alle beheerde knooppunten moeten worden weergegeven in de volgende indeling in het `/etc/ansible/hosts` of relevante bestand:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Pingtest:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Het onboarding-pakket downloaden

Download het onboarding-pakket van Microsoft Defender-beveiligingscentrum:

1. Ga Microsoft Defender-beveiligingscentrum naar Instellingen > **Device Management > Onboarding.**
2. Selecteer in de eerste vervolgkeuzelijst **Linux Server** als besturingssysteem. Selecteer in de tweede vervolgkeuzelijst **Uw voorkeursprogramma** voor configuratiebeheer voor Linux als implementatiemethode.
3. Selecteer **Onboarding-pakket downloaden.** Sla het bestand op als WindowsDefenderATPOnboardingPackage.zip.

    ![Microsoft Defender-beveiligingscentrum schermafbeelding](images/atp-portal-onboarding-linux-2.png)

4. Controleer in een opdrachtprompt of u het bestand hebt. Haal de inhoud van het archief op:

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

## <a name="create-ansible-yaml-files"></a>Ansible YAML-bestanden maken

Maak een subtaak of rolbestanden die bijdragen aan een speelboek of taak.

- Maak de onboarding-taak: `onboarding_setup.yml`

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

- Voeg de defender voor eindpuntopslagplaats en de sleutel `add_apt_repo.yml` toe:

    Defender for Endpoint on Linux kan worden geïmplementeerd vanuit een van de volgende kanalen (hieronder aangeduid als *[kanaal]*): *insiders-fast*, *insiders-slow*, of *prod*. Elk van deze kanalen komt overeen met een Linux-softwareopslagplaats.

    De keuze van het kanaal bepaalt het type en de frequentie van de updates die op uw apparaat worden aangeboden. Apparaten in *insiders-fast* zijn de eersten die updates en nieuwe functies ontvangen, later gevolgd door *insiders-slow* en ten laatste *door prod*.

    Als u een voorbeeld van nieuwe functies wilt bekijken en vroegtijdig feedback wilt geven, wordt u aangeraden sommige apparaten in uw bedrijf te configureren om *insiders-fast* of *insiders-slow te gebruiken.*

    > [!WARNING]
    > Als u het kanaal na de eerste installatie overschakelt, moet het product opnieuw worden geïnstalleerd. Als u het productkanaal wilt wijzigen: verwijder het bestaande pakket, configureer het apparaat opnieuw om het nieuwe kanaal te gebruiken en volg de stappen in dit document om het pakket vanaf de nieuwe locatie te installeren.

    Noteer uw distributie en versie en identificeer de dichtstbijzijnde vermelding voor de versie onder `https://packages.microsoft.com/config/` .

    Vervang *[distro]* en *[versie]* in de volgende opdrachten door de gegevens die u hebt geïdentificeerd.

    > [!NOTE]
    > In het geval van Oracle Linux vervangt *u [distro] door* "rhel".

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      url: https://packages.microsoft.com/keys/microsoft.asc
      state: present
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel]
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

- Maak de Ansible-installatie en verwijder YAML-bestanden.

    - Voor apt-gebaseerde distributies gebruikt u het volgende YAML-bestand:

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

    - Voor dnf-gebaseerde distributies gebruikt u het volgende YAML-bestand:

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

## <a name="deployment"></a>Implementatie

Voer nu de takenbestanden uit onder `/etc/ansible/playbooks/` of relevante adreslijst.

- Installatie:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> Wanneer het product voor het eerst wordt gestart, worden de meest recente antimalwaredefinities gedownload. Afhankelijk van uw internetverbinding kan dit enkele minuten duren.

- Validatie/configuratie:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- Verwijderen:

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>Problemen met de installatie van logboeken

Zie [Installatieproblemen in logboeken](linux-resources.md#log-installation-issues) voor meer informatie over het vinden van het automatisch gegenereerde logboek dat door het installatieprogramma wordt gemaakt wanneer er een fout optreedt.

## <a name="operating-system-upgrades"></a>Upgrades van besturingssysteem

Wanneer u uw besturingssysteem upgradet naar een nieuwe hoofdversie, moet u Eerst Defender voor Eindpunt op Linux verwijderen, de upgrade installeren en defender voor eindpunt opnieuw configureren op Linux op uw apparaat.

## <a name="references"></a>Verwijzingen

- [YUM-opslagplaatsen toevoegen of verwijderen](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Pakketten beheren met de dnf package manager](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [APT-opslagplaatsen toevoegen en verwijderen](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Apt-pakketten beheren](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>Zie ook
- [Statusproblemen van agent onderzoeken](health-status.md)
