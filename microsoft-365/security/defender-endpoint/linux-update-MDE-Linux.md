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
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="c6663-104">Een update van Microsoft Defender voor Eindpunt (Linux) plannen</span><span class="sxs-lookup"><span data-stu-id="c6663-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="c6663-105">Zie Updates implementeren voor Microsoft Defender voor Endpoint op Linux als u een update wilt uitvoeren op Microsoft Defender [voor Endpoint op Linux.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates)</span><span class="sxs-lookup"><span data-stu-id="c6663-105">To run an update on Microsoft Defender for Endpoint on Linux, see [Deploy updates for Microsoft Defender for Endpoint on Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="c6663-106">Linux (en Unix) hebben een hulpprogramma genaamd **crontab** (vergelijkbaar met Taakplanning) om geplande taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="c6663-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="c6663-107">Vereiste</span><span class="sxs-lookup"><span data-stu-id="c6663-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="c6663-108">Voer de volgende opdracht uit om een lijst met alle tijdzones te krijgen: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="c6663-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="c6663-109">Voorbeelden voor tijdzones:</span><span class="sxs-lookup"><span data-stu-id="c6663-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="c6663-110">De cron-taak instellen</span><span class="sxs-lookup"><span data-stu-id="c6663-110">To set the Cron job</span></span>
<span data-ttu-id="c6663-111">Gebruik de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="c6663-111">Use the following commands:</span></span>

<span data-ttu-id="c6663-112">**Back-up maken van crontab-items**</span><span class="sxs-lookup"><span data-stu-id="c6663-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="c6663-113">Where 201118 == YYMMDD</span><span class="sxs-lookup"><span data-stu-id="c6663-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="c6663-114">Doe dit voordat u deze bewerkt of verwijdert.</span><span class="sxs-lookup"><span data-stu-id="c6663-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="c6663-115">Het kruisje bewerken en een nieuwe taak toevoegen als hoofdgebruiker:</span><span class="sxs-lookup"><span data-stu-id="c6663-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="c6663-116">De standaardeditor is VIM.</span><span class="sxs-lookup"><span data-stu-id="c6663-116">The default editor is VIM.</span></span>

<span data-ttu-id="c6663-117">Mogelijk ziet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="c6663-117">You might see:</span></span>

<span data-ttu-id="c6663-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="c6663-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="c6663-119">En</span><span class="sxs-lookup"><span data-stu-id="c6663-119">And</span></span>

<span data-ttu-id="c6663-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="c6663-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="c6663-121">Zie [Scans plannen met Microsoft Defender voor Eindpunt (Linux)](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="c6663-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="c6663-122">Druk op Invoegen</span><span class="sxs-lookup"><span data-stu-id="c6663-122">Press “Insert”</span></span>

<span data-ttu-id="c6663-123">Voeg de volgende vermeldingen toe:</span><span class="sxs-lookup"><span data-stu-id="c6663-123">Add the following entries:</span></span>

<span data-ttu-id="c6663-124">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="c6663-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="c6663-125">! RHEL en varianten (CentOS en Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="c6663-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="c6663-126">! SLES en varianten</span><span class="sxs-lookup"><span data-stu-id="c6663-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="c6663-127">! Ubuntu- en Debian-systemen</span><span class="sxs-lookup"><span data-stu-id="c6663-127">!Ubuntu and Debian systems</span></span>

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="c6663-128">In de bovenstaande voorbeelden stellen we het in op 00 minuten, 6:00(uur in 24 uursindeling), elke dag van de maand, elke maand, op zondag. [$(datum + d) -le 15] == Wordt niet uitgevoerd, tenzij deze gelijk is aan of kleiner is dan de \% 15e dag (3e week).</span><span class="sxs-lookup"><span data-stu-id="c6663-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="c6663-129">Dit betekent dat het elke 3e zondag(7) van de maand om 6:00 uur wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c6663-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="c6663-130">Pacific (UTC -8).</span><span class="sxs-lookup"><span data-stu-id="c6663-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="c6663-131">Druk op Esc</span><span class="sxs-lookup"><span data-stu-id="c6663-131">Press “Esc”</span></span>

<span data-ttu-id="c6663-132">Typ ':wq' w/o de dubbele aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="c6663-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="c6663-133">w == schrijven, q == stoppen</span><span class="sxs-lookup"><span data-stu-id="c6663-133">w == write, q == quit</span></span>

<span data-ttu-id="c6663-134">Als u uw cron-taken wilt weergeven, typt u `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="c6663-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="MDE linux bijwerken":::

<span data-ttu-id="c6663-136">Als u de cron-taak wilt controleren, gaat u als eerste te werk: `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="c6663-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="c6663-137">De mdatp_cron_job.log controleren `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="c6663-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="c6663-138">Voor degenen die Ansible, Chef of Puppet gebruiken</span><span class="sxs-lookup"><span data-stu-id="c6663-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="c6663-139">Gebruik de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="c6663-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="c6663-140">Cron-taken instellen in Ansible</span><span class="sxs-lookup"><span data-stu-id="c6663-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="c6663-141">Zie [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c6663-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="c6663-142">Crontabs instellen in Chef</span><span class="sxs-lookup"><span data-stu-id="c6663-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="c6663-143">Zie [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c6663-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="c6663-144">Cron-taken instellen in Poppop</span><span class="sxs-lookup"><span data-stu-id="c6663-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="c6663-145">Resourcetype: cron</span><span class="sxs-lookup"><span data-stu-id="c6663-145">Resource Type: cron</span></span>

<span data-ttu-id="c6663-146">Zie [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c6663-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="c6663-147">Automatiseren met Poppop: Cron-taken en geplande taken</span><span class="sxs-lookup"><span data-stu-id="c6663-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="c6663-148">Zie [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c6663-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="c6663-149">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="c6663-149">Additional information</span></span>

<span data-ttu-id="c6663-150">**Hulp krijgen bij crontab**</span><span class="sxs-lookup"><span data-stu-id="c6663-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="c6663-151">**Een lijst met crontabbestand van de huidige gebruiker downloaden**</span><span class="sxs-lookup"><span data-stu-id="c6663-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="c6663-152">**Een lijst met crontabbestand van een andere gebruiker downloaden**</span><span class="sxs-lookup"><span data-stu-id="c6663-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="c6663-153">**Back-up maken van crontab-items**</span><span class="sxs-lookup"><span data-stu-id="c6663-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="c6663-154">Doe dit voordat u deze bewerkt of verwijdert.</span><span class="sxs-lookup"><span data-stu-id="c6663-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="c6663-155">**Crontab-items herstellen**</span><span class="sxs-lookup"><span data-stu-id="c6663-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="c6663-156">**Het crontab bewerken en een nieuwe taak als hoofdgebruiker toevoegen**</span><span class="sxs-lookup"><span data-stu-id="c6663-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="c6663-157">**Het kruisje bewerken en een nieuwe taak toevoegen**</span><span class="sxs-lookup"><span data-stu-id="c6663-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="c6663-158">**De crontab-items van andere gebruikers bewerken**</span><span class="sxs-lookup"><span data-stu-id="c6663-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="c6663-159">**Alle crontab-items verwijderen**</span><span class="sxs-lookup"><span data-stu-id="c6663-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="c6663-160">**De crontab-items van andere gebruikers verwijderen**</span><span class="sxs-lookup"><span data-stu-id="c6663-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="c6663-161">**Uitleg**</span><span class="sxs-lookup"><span data-stu-id="c6663-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

