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
ms.openlocfilehash: 5a4beaefb2fcc12d46cf61c22644217dce1807a6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845364"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="ded93-104">Scans plannen met Microsoft Defender voor Eindpunt (Linux)</span><span class="sxs-lookup"><span data-stu-id="ded93-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="ded93-105">Zie Ondersteunde opdrachten om een scan voor Linux [uit te voeren.](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)</span><span class="sxs-lookup"><span data-stu-id="ded93-105">To run a scan for Linux, see [Supported Commands](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="ded93-106">Linux (en Unix) hebben een hulpprogramma genaamd **crontab** (vergelijkbaar met Taakplanning) om geplande taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ded93-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="ded93-107">Vereiste</span><span class="sxs-lookup"><span data-stu-id="ded93-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="ded93-108">Voer de volgende opdracht uit om een lijst met alle tijdzones te krijgen: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="ded93-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="ded93-109">Voorbeelden voor tijdzones:</span><span class="sxs-lookup"><span data-stu-id="ded93-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="ded93-110">De cron-taak instellen</span><span class="sxs-lookup"><span data-stu-id="ded93-110">To set the Cron job</span></span>
<span data-ttu-id="ded93-111">Gebruik de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="ded93-111">Use the following commands:</span></span>

<span data-ttu-id="ded93-112">**Back-up maken van crontab-items**</span><span class="sxs-lookup"><span data-stu-id="ded93-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="ded93-113">Where 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="ded93-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="ded93-114">Doe dit voordat u deze bewerkt of verwijdert.</span><span class="sxs-lookup"><span data-stu-id="ded93-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="ded93-115">Het kruisje bewerken en een nieuwe taak toevoegen als hoofdgebruiker:</span><span class="sxs-lookup"><span data-stu-id="ded93-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="ded93-116">De standaardeditor is VIM.</span><span class="sxs-lookup"><span data-stu-id="ded93-116">The default editor is VIM.</span></span>

<span data-ttu-id="ded93-117">Mogelijk ziet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="ded93-117">You might see:</span></span>

<span data-ttu-id="ded93-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="ded93-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="ded93-119">Druk op Invoegen</span><span class="sxs-lookup"><span data-stu-id="ded93-119">Press “Insert”</span></span>

<span data-ttu-id="ded93-120">Voeg de volgende vermeldingen toe:</span><span class="sxs-lookup"><span data-stu-id="ded93-120">Add the following entries:</span></span>

<span data-ttu-id="ded93-121">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="ded93-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="ded93-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="ded93-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="ded93-123">In dit voorbeeld hebben we deze ingesteld op 00 minuten, 02:00 uur.</span><span class="sxs-lookup"><span data-stu-id="ded93-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="ded93-124">(uur in 24 uursindeling), elke dag van de maand, elke maand, op zaterdag.</span><span class="sxs-lookup"><span data-stu-id="ded93-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="ded93-125">Dit betekent dat de zaterdag om 02:00 uur wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ded93-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="ded93-126">Pacific (UTC –8).</span><span class="sxs-lookup"><span data-stu-id="ded93-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="ded93-127">Druk op Esc</span><span class="sxs-lookup"><span data-stu-id="ded93-127">Press “Esc”</span></span>

<span data-ttu-id="ded93-128">Typ ':wq' zonder dubbele aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="ded93-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="ded93-129">w == schrijven, q == stoppen</span><span class="sxs-lookup"><span data-stu-id="ded93-129">w == write, q == quit</span></span>

<span data-ttu-id="ded93-130">Als u uw cron-taken wilt weergeven, typt u `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="ded93-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="ded93-132">**Cron-taak uitgevoerd controleren**</span><span class="sxs-lookup"><span data-stu-id="ded93-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="ded93-133">**De mdatp_cron_job.log controleren**</span><span class="sxs-lookup"><span data-stu-id="ded93-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="ded93-134">Voor degenen die Ansible, Chef of Puppet gebruiken</span><span class="sxs-lookup"><span data-stu-id="ded93-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="ded93-135">Gebruik de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="ded93-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="ded93-136">Cron-taken instellen in Ansible</span><span class="sxs-lookup"><span data-stu-id="ded93-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="ded93-137">Zie [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ded93-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="ded93-138">Crontabs instellen in Chef</span><span class="sxs-lookup"><span data-stu-id="ded93-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="ded93-139">Zie [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ded93-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="ded93-140">Cron-taken instellen in Poppop</span><span class="sxs-lookup"><span data-stu-id="ded93-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="ded93-141">Resourcetype: cron</span><span class="sxs-lookup"><span data-stu-id="ded93-141">Resource Type: cron</span></span>

<span data-ttu-id="ded93-142">Zie [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ded93-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="ded93-143">Automatiseren met Poppop: Cron-taken en geplande taken</span><span class="sxs-lookup"><span data-stu-id="ded93-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="ded93-144">Zie [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ded93-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="ded93-145">Aanvullende informatie</span><span class="sxs-lookup"><span data-stu-id="ded93-145">Additional information</span></span>

<span data-ttu-id="ded93-146">**Hulp krijgen bij crontab**</span><span class="sxs-lookup"><span data-stu-id="ded93-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="ded93-147">**Een lijst met crontabbestand van de huidige gebruiker downloaden**</span><span class="sxs-lookup"><span data-stu-id="ded93-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="ded93-148">**Een lijst met crontabbestand van een andere gebruiker downloaden**</span><span class="sxs-lookup"><span data-stu-id="ded93-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="ded93-149">**Back-up maken van crontab-items**</span><span class="sxs-lookup"><span data-stu-id="ded93-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="ded93-150">Doe dit voordat u deze bewerkt of verwijdert.</span><span class="sxs-lookup"><span data-stu-id="ded93-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="ded93-151">**Crontab-items herstellen**</span><span class="sxs-lookup"><span data-stu-id="ded93-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="ded93-152">**Het crontab bewerken en een nieuwe taak als hoofdgebruiker toevoegen**</span><span class="sxs-lookup"><span data-stu-id="ded93-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="ded93-153">**Het kruisje bewerken en een nieuwe taak toevoegen**</span><span class="sxs-lookup"><span data-stu-id="ded93-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="ded93-154">**De crontab-items van andere gebruikers bewerken**</span><span class="sxs-lookup"><span data-stu-id="ded93-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="ded93-155">**Alle crontab-items verwijderen**</span><span class="sxs-lookup"><span data-stu-id="ded93-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="ded93-156">**De crontab-items van andere gebruikers verwijderen**</span><span class="sxs-lookup"><span data-stu-id="ded93-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="ded93-157">**Uitleg**</span><span class="sxs-lookup"><span data-stu-id="ded93-157">**Explanation**</span></span>

<span data-ttu-id="ded93-158">+—————- minuut (waarden: 0 – 59) (speciale tekens: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="ded93-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="ded93-159">| +————- uur (waarden: 0 – 23) (speciale tekens: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="ded93-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="ded93-160">| | +———- dag van de maand (waarden: 1 – 31) (speciale tekens: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="ded93-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="ded93-161">| | | +——- maand (waarden: 1 – 12) (speciale tekens: ,- \* / )</span><span class="sxs-lookup"><span data-stu-id="ded93-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="ded93-162">| | | | +—- dag van de week (waarden: 0 – 6) (zondag=0 of 7) (speciale tekens: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="ded93-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="ded93-163">| | | | |\*\*\*\*\*-opdracht die moet worden uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="ded93-163">| | | | |\*\*\*\*\*command to be executed</span></span>


