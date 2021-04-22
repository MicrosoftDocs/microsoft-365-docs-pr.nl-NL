---
title: Scans plannen met Microsoft Defender voor Eindpunt (Linux)
description: Lees hoe u een automatische scantijd voor Microsoft Defender voor Eindpunt (Linux) kunt plannen om de activa van uw organisatie beter te beveiligen.
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
ms.openlocfilehash: f868570fccf9b30cde5f16aa8e71292fb8b09497
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933131"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Scans plannen met Microsoft Defender voor Eindpunt (Linux)

Zie Ondersteunde opdrachten om een scan voor Linux [uit te voeren.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)

Linux (en Unix) hebben een hulpprogramma genaamd **crontab** (vergelijkbaar met Taakplanning) om geplande taken uit te voeren.

## <a name="pre-requisite"></a>Vereiste

> [!NOTE]
> Voer de volgende opdracht uit om een lijst met alle tijdzones te krijgen: `timedatectl list-timezones`<br>
> Voorbeelden voor tijdzones:
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>De cron-taak instellen
Gebruik de volgende opdrachten:

**Back-up maken van crontab-items**

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> Where 200919 == YRMMDD

> [!TIP]
> Doe dit voordat u deze bewerkt of verwijdert. <br>

Het kruisje bewerken en een nieuwe taak toevoegen als hoofdgebruiker: <br>
`sudo crontab -e`

> [!NOTE]
> De standaardeditor is VIM.

Mogelijk ziet u het volgende:

0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh

Druk op Invoegen

Voeg de volgende vermeldingen toe:

CRON_TZ=America/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log

> [!NOTE]
>In dit voorbeeld hebben we deze ingesteld op 00 minuten, 02:00 uur. (uur in 24 uursindeling), elke dag van de maand, elke maand, op zaterdag. Dit betekent dat de zaterdag om 02:00 uur wordt uitgevoerd. Pacific (UTC –8).

Druk op Esc

Typ ':wq' zonder dubbele aanhalingstekens.

> [!NOTE]
> w == schrijven, q == stoppen

Als u uw cron-taken wilt weergeven, typt u `sudo crontab -l`

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

**Cron-taak uitgevoerd controleren**

`sudo grep mdatp /var/log/cron`

**De mdatp_cron_job.log controleren**

`sudo nano mdatp_cron_job.log`

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

+—————- minuut (waarden: 0 – 59) (speciale tekens: , – * /)  <br>
| +————- uur (waarden: 0 – 23) (speciale tekens: , – * /) <br>
| | +———- dag van de maand (waarden: 1 – 31) (speciale tekens: , – * / L W C)  <br>
| | | +——- maand (waarden: 1 – 12) (speciale tekens: ,- * / )  <br>
| | | | +—- dag van de week (waarden: 0 – 6) (zondag=0 of 7) (speciale tekens: , – * / L W C) <br>
| | | | |*****-opdracht die moet worden uitgevoerd


