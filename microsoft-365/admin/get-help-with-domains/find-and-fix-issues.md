---
title: Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Leer eventuele problemen op te sporen die u tegenkomt tijdens het instellen van een aangepast domein door ervoor te zorgen dat de DNS-records correct zijn ingesteld.
ms.openlocfilehash: 13d867559684d80ee5c0e1f7005d1dcaf3b4d611
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628468"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="65686-103">Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd</span><span class="sxs-lookup"><span data-stu-id="65686-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="65686-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="65686-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="65686-105">Het kan een uitdaging zijn om uw domein in te stellen om met Microsoft 365 te werken.</span><span class="sxs-lookup"><span data-stu-id="65686-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="65686-106">Bij het werken met het DNS-systeem is het belangrijk dat alle waarden correct worden ingevoerd, want de DNS-instellingen voor uw domein zijn van invloed op belangrijke zakelijke activiteiten, zoals e-mail.</span><span class="sxs-lookup"><span data-stu-id="65686-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="65686-107">U controleren op problemen met uw domein door de status ervan te controleren.</span><span class="sxs-lookup"><span data-stu-id="65686-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="65686-108">Ga naar **Domeinen** > **instellen** en bekijk de meldingen in de kolom **Status.**</span><span class="sxs-lookup"><span data-stu-id="65686-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="65686-109">Als u een probleem ziet, selecteert u Meer acties (drie puntjes) en kiest u **De status controleren**.</span><span class="sxs-lookup"><span data-stu-id="65686-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="65686-110">In het deelvenster dat wordt geopend, worden eventuele problemen met uw domein beschreven.</span><span class="sxs-lookup"><span data-stu-id="65686-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="65686-111">Wat gebeurt er?</span><span class="sxs-lookup"><span data-stu-id="65686-111">What's going on?</span></span>

- [<span data-ttu-id="65686-112">u uw domein niet verifiëren?</span><span class="sxs-lookup"><span data-stu-id="65686-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="65686-113">Werkt Outlook niet?</span><span class="sxs-lookup"><span data-stu-id="65686-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="65686-114">Ieders e-mail werd overgeschakeld naar Microsoft 365 en je wilde alleen je e-mail om over te schakelen?</span><span class="sxs-lookup"><span data-stu-id="65686-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="65686-115">u de status van non-profit- of schoolaccount niet bevestigen?</span><span class="sxs-lookup"><span data-stu-id="65686-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="65686-116">Services die niet met uw domein werken?</span><span class="sxs-lookup"><span data-stu-id="65686-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="65686-117">Toegang tot uw website werkt niet?</span><span class="sxs-lookup"><span data-stu-id="65686-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="65686-118">U kunt uw domein niet verifiëren?</span><span class="sxs-lookup"><span data-stu-id="65686-118">Can't verify your domain?</span></span>
<span data-ttu-id="65686-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="65686-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="65686-120">Er zijn enkele veelvoorkomende redenen waarom de verificatie van een domein niet werkt zoals het zou moeten:</span><span class="sxs-lookup"><span data-stu-id="65686-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="65686-p103">**De waarde van de verificatierecord is niet helemaal juist.** Controleer goed of u de exacte waarde naar de TXT-record voor verificatie bij uw DNS-host hebt gekopieerd en geplakt. Een veelvoorkomende fout is dat het gedeelte 'MS=' van de record niet mee is gekopieerd. Maar dat hebben we ook nodig!</span><span class="sxs-lookup"><span data-stu-id="65686-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="65686-125">**De record is niet opgeslagen.**</span><span class="sxs-lookup"><span data-stu-id="65686-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="65686-126">Bij sommige DNS-hosts moet u een extra stap nemen om het zonebestand (waarin de DNS-record wordt opgeslagen) op te slaan zodat dit overal op internet wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="65686-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="65686-127">Zorg ervoor dat u de wijzigingen hebt opgeslagen, zodat Microsoft 365 de record kan zien en verifiëren.</span><span class="sxs-lookup"><span data-stu-id="65686-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="65686-128">**De record is niet bijgewerkt op het internet.**</span><span class="sxs-lookup"><span data-stu-id="65686-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="65686-129">Het duurt meestal slechts een paar minuten voor ons in staat zijn om de nieuwe record te zien, maar af en toe kan het zo lang duren als een paar uur.</span><span class="sxs-lookup"><span data-stu-id="65686-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="65686-130">Outlook werkt niet?</span><span class="sxs-lookup"><span data-stu-id="65686-130">Outlook isn't working?</span></span>
<span data-ttu-id="65686-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="65686-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="65686-132">Als u uw MX-record en andere DNS-records correct hebt ingesteld voor uw domein, maar e-mail niet werkt, kunnen wij u helpen [uw Outlook-problemen op te lossen](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span><span class="sxs-lookup"><span data-stu-id="65686-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="65686-133">Ieders e-mail werd overgeschakeld naar Microsoft 365 en je wilde alleen je e-mail om over te schakelen?</span><span class="sxs-lookup"><span data-stu-id="65686-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="65686-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="65686-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="65686-135">Wanneer u uw domein toevoegt aan Microsoft 365, wordt de MX-record van uw domein meestal bijgewerkt (door u of Microsoft 365) om naar Microsoft 365 te wijzen en alle e-mails die naar dat domein worden verzonden, worden naar Microsoft 365 verzonden.</span><span class="sxs-lookup"><span data-stu-id="65686-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="65686-136">Zorg ervoor dat u postvakken hebt gemaakt in Microsoft 365 voor iedereen die e-mail op uw domein heeft voordat u de MX-record wijzigt.</span><span class="sxs-lookup"><span data-stu-id="65686-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="65686-137">Wat moet u doen als u e-mail niet voor iedereen in uw domein wilt verplaatsen naar Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="65686-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="65686-138">U stappen ondernemen om [Microsoft 365 te besturen met slechts een paar e-mailadressen in plaats daarvan.](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx)</span><span class="sxs-lookup"><span data-stu-id="65686-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="65686-139">u de status van non-profit- of schoolaccount niet bevestigen?</span><span class="sxs-lookup"><span data-stu-id="65686-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="65686-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="65686-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="65686-141">Er zijn een paar scenario's waarin u alleen het domein van uw organisatie hoeft te verifiëren en geen services hoeft in te stellen.</span><span class="sxs-lookup"><span data-stu-id="65686-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="65686-142">Bijvoorbeeld om aan Microsoft 365 te bewijzen dat uw organisatie in aanmerking komt voor een schoolabonnement.</span><span class="sxs-lookup"><span data-stu-id="65686-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="65686-143">Bekijk de richtlijnen in [Uw Microsoft 365-domein verifiëren om de eigendoms-, non-profit- of onderwijsstatus te bewijzen of Yammer te activeren](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) om ervoor te zorgen dat u alle vereiste stappen hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="65686-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="65686-144">Het is een beetje anders voor elke situatie.</span><span class="sxs-lookup"><span data-stu-id="65686-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="65686-145">Zijn er services die niet werken met uw domein?</span><span class="sxs-lookup"><span data-stu-id="65686-145">Services not working with your domain?</span></span>
<span data-ttu-id="65686-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="65686-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="65686-147">We kunnen u helpen bij het opsporen van problemen met de DNS-installatie van uw domein.</span><span class="sxs-lookup"><span data-stu-id="65686-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="65686-148">De probleemoplosser voor domeinen in Microsoft 365 toont u alle records die moeten worden hersteld en waar de records precies op moeten worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="65686-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="65686-149">Hebt u uw DNS-correct ingesteld, maar werkt e-mail niet in Outlook op uw desktopcomputer?</span><span class="sxs-lookup"><span data-stu-id="65686-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="65686-150">Bekijk de [verschillende scenario's voor e-mailstroom die u hebben met Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=787530) om ervoor te zorgen dat u dingen correct hebt ingesteld voor uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="65686-150">Check out the [different mail flow scenarios you can have with Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=787530) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="65686-151">Meer hulp bij het oplossen van problemen met e-mail vindt u hier: [Problemen met Outlook oplossen](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span><span class="sxs-lookup"><span data-stu-id="65686-151">Or get more troubleshooting help with email here: [Fix Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="65686-152">U krijgt geen toegang tot uw website?</span><span class="sxs-lookup"><span data-stu-id="65686-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="65686-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="65686-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="65686-154">Als u DNS-problemen hebt opgelost en nog steeds problemen ondervindt, probeer dan een van de volgende opties.</span><span class="sxs-lookup"><span data-stu-id="65686-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="65686-155">Personen kunnen uw website op www.mijndomein.com niet bereiken: [Websiteproblemen opsporen](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span><span class="sxs-lookup"><span data-stu-id="65686-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span></span>
    
- <span data-ttu-id="65686-156">U uw A-record of CNAME-record niet bijwerken om naar uw website te wijzen: [Aangepaste DNS-records bijwerken in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="65686-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span></span>
    
