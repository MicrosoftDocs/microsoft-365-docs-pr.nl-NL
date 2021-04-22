---
title: Een update van het Microsoft Defender for Endpoint (Linux) plannen
description: Lees hoe u een update van het Microsoft Defender for Endpoint (Linux) kunt plannen om de activa van uw organisatie beter te beschermen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, scans, antivirus, microsoft defender for endpoint (linux)
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 22ff42cb399b3d07c0ebd8ec4f947352eb6f44aa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934763"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Een update van Microsoft Defender voor Eindpunt (Linux) plannen

Zie Updates implementeren voor Microsoft Defender voor Endpoint op Linux als u een update wilt uitvoeren op Microsoft Defender [voor Endpoint op Linux.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates)

Linux (en Unix) hebben een hulpprogramma genaamd **crontab** (vergelijkbaar met Taakplanning) om geplande taken uit te voeren.

## <a name="pre-requisite"></a>Vereiste

> [!NOTE]
> Voer de volgende opdracht uit om een lijst met alle tijdzones te krijgen: `timedatectl list-timezones`<br>
> Voorbeelden voor tijdzones: <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>De cron-taak instellen
Gebruik de volgende opdrachten:

**Back-up maken van crontab-items**

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> Where 201118 == YYMMDD

> [!TIP]
> Doe dit voordat u deze bewerkt of verwijdert. <br>

Het kruisje bewerken en een nieuwe taak toevoegen als hoofdgebruiker: <br>
`sudo crontab -e`

> [!NOTE]
> De standaardeditor is VIM.

Mogelijk ziet u het volgende:

0****/etc/opt/microsoft/mdatp/logrorate.sh

En

02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log

Zie [Scans plannen met Microsoft Defender voor Eindpunt (Linux)](linux-schedule-scan-atp.md)

Druk op Invoegen

Voeg de volgende vermeldingen toe:

CRON_TZ=America/Los_Angeles

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL en varianten (CentOS en Oracle Linux)

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a>! SLES en varianten

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a>! Ubuntu- en Debian-systemen

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> In de bovenstaande voorbeelden stellen we het in op 00 minuten, 6:00(uur in 24 uursindeling), elke dag van de maand, elke maand, op zondag. [$(datum + d) -le 15] == Wordt niet uitgevoerd, tenzij deze gelijk is aan of kleiner is dan de \% 15e dag (3e week). Dit betekent dat het elke 3e zondag(7) van de maand om 6:00 uur wordt uitgevoerd. Pacific (UTC -8).

Druk op Esc

Typ ':wq' w/o de dubbele aanhalingstekens.

> [!NOTE]
> w == schrijven, q == stoppen

Als u uw cron-taken wilt weergeven, typt u `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="MDE linux bijwerken":::

Als u de cron-taak wilt controleren, gaat u als eerste te werk: `sudo grep mdatp /var/log/cron`

De mdatp_cron_job.log controleren `sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Voor degenen die Ansible, Chef of Puppet gebruiken

Gebruik de volgende opdrachten:
### <a name="to-set-cron-jobs-in-ansible"></a>Cron-taken instellen in Ansible

`cron – Manage cron.d and crontab entries`

Zie [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) voor meer informatie.

### <a name="to-set-crontabs-in-chef"></a>Crontabs instellen in Chef
`cron resource`

Zie [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) voor meer informatie.

### <a name="to-set-cron-jobs-in-puppet"></a>Cron-taken instellen in Poppop
Resourcetype: cron

Zie [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) voor meer informatie.

Automatiseren met Poppop: Cron-taken en geplande taken

Zie [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) voor meer informatie.

## <a name="additional-information"></a>Aanvullende informatie

**Hulp krijgen bij crontab**

`man crontab`

**Een lijst met crontabbestand van de huidige gebruiker downloaden**

`crontab -l`

**Een lijst met crontabbestand van een andere gebruiker downloaden**

`crontab -u username -l`

**Back-up maken van crontab-items**

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> Doe dit voordat u deze bewerkt of verwijdert. <br>

**Crontab-items herstellen**

`crontab /var/tmp/cron_backup.dat`

**Het crontab bewerken en een nieuwe taak als hoofdgebruiker toevoegen**

`sudo crontab -e`

**Het kruisje bewerken en een nieuwe taak toevoegen**

`crontab -e`

**De crontab-items van andere gebruikers bewerken**

`crontab -u username -e`

**Alle crontab-items verwijderen**

`crontab -r`

**De crontab-items van andere gebruikers verwijderen**

`crontab -u username -r`

**Uitleg**

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

