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
ms.openlocfilehash: 12f648ce476f6e29cbb6b038cc42f2e744d77104
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933299"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Installatieproblemen oplossen voor Microsoft Defender voor Eindpunt op Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a>Controleren of de installatie is geslaagd

Een fout in de installatie kan al dan niet leiden tot een duidelijke foutmelding door de package manager. Als u wilt controleren of de installatie is gelukt, kunt u de installatielogboeken verkrijgen en controleren met behulp van:

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

Een uitvoer van de vorige opdracht met de juiste datum en tijd van de installatie duidt op succes.

Controleer ook de [clientconfiguratie om](linux-install-manually.md#client-configuration) de status van het product te controleren en het TEKSTBESTAND VAN EICAR te detecteren.

## <a name="make-sure-you-have-the-correct-package"></a>Zorg ervoor dat u het juiste pakket hebt

Houd er rekening mee dat het pakket dat u installeert overeenkomt met de hostdistributie en -versie.

| pakket                       | distributie                             |
|-------------------------------|------------------------------------------|
| mdatp-rhel8. Linux.x86_64.rpm  | Oracle, RHEL en CentOS 8.x              |
| mdatp-sles12. Linux.x86_64.rpm | SuSE Linux Enterprise Server 12.x        |
| mdatp-sles15. Linux.x86_64.rpm | SuSE Linux Enterprise Server 15.x        |
| mdatp. Linux.x86_64.rpm        | Oracle, RHEL en CentOS 7.x              |
| mdatp. Linux.x86_64.deb        | Debian en Ubuntu 16.04, 18.04 en 20.04 |

Voor [handmatige implementatie](linux-install-manually.md)moet u ervoor zorgen dat de juiste distributie en versie zijn gekozen.

## <a name="installation-failed"></a>Installatie mislukt

Controleer of de mdatp-service wordt uitgevoerd:

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

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a>Stappen om problemen op te lossen als de mdatp-service niet wordt uitgevoerd

1. Controleer of 'mdatp'-gebruiker bestaat:

    ```bash
    id "mdatp"
    ```

    Als er geen uitvoer is, voer dan

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. Probeer de service in te stellen en opnieuw te starten met behulp van:

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. Als mdatp.service niet wordt gevonden bij het uitvoeren van de vorige opdracht, voer dan het volgende uit:

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    waar ```<systemd_path>``` is ```/lib/systemd/system``` voor Ubuntu- en Debian-distributies en ```/usr/lib/systemd/system``` voor Rhel, CentOS, Oracle en SLES.
   Vervolgens stap 2 opnieuw.

4. Als de bovenstaande stappen niet werken, controleert u of SELinux is geïnstalleerd en in de afdwingmodus. Als dat het het beste is, kunt u de modus instellen op een permissieve (bij voorkeur) of uitgeschakelde modus. U kunt dit doen door de parameter in te stellen op `SELINUX` 'permissief' of 'uitgeschakeld' in het `/etc/selinux/config` bestand, gevolgd door opnieuw opstarten. Controleer de man-pagina van selinux voor meer informatie.
Start nu de mdatp-service opnieuw met stap 2. U kunt de configuratiewijziging echter direct herstellen om beveiligingsredenen nadat u deze hebt geprobeerd en opnieuw hebt opgestart.

5. Als `/opt` adreslijst een symbolische koppeling is, maakt u een koppelingskoppeling voor `/opt/microsoft` .

6. Controleer of de daemon uitvoerbare machtiging heeft.

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    Als de daemon geen uitvoerbare machtigingen heeft, kunt u deze uitvoerbaar maken met behulp van:

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    en u kunt stap 2 opnieuw uitvoeren.

7. Zorg ervoor dat het bestandssysteem met wdavdaemon niet is bevestigd met 'noexec'.

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a>Als de mdatp-service wordt uitgevoerd, maar de detectie van EICAR-tekstbestand niet werkt

1. Controleer het bestandssysteemtype met behulp van:

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    Momenteel ondersteunde bestandssystemen voor on-access-activiteiten worden hier [weergegeven.](microsoft-defender-endpoint-linux.md#system-requirements) Bestanden buiten deze bestandssystemen worden niet gescand.

## <a name="command-line-tool-mdatp-isnt-working"></a>Opdrachtregelhulpmiddel 'mdatp' werkt niet

1. Als het uitvoeren van het opdrachtregelhulpmiddel `mdatp` een fout `command not found` geeft, voer dan de volgende opdracht uit:

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    en probeer het opnieuw.

    Als geen van de bovenstaande stappen helpt, verzamelt u de diagnostische logboeken:

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    Pad naar een zip-bestand dat de logboeken bevat, wordt weergegeven als uitvoer. Contact op met onze klantenondersteuning met deze logboeken.
