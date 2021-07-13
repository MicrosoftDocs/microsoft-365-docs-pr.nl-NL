---
title: Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Lees hoe u problemen kunt oplossen bij het instellen van een aangepast domein door ervoor te zorgen dat de DNS-records correct zijn ingesteld.
ms.openlocfilehash: 1dcc52be68fca11245e1a2437d9fe5a3f23ed694
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393893"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="cae05-103">Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd</span><span class="sxs-lookup"><span data-stu-id="cae05-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="cae05-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="cae05-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cae05-105">Het kan lastig zijn om uw domein zo in te stellen Microsoft 365 te werken.</span><span class="sxs-lookup"><span data-stu-id="cae05-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="cae05-106">Bij het werken met het DNS-systeem is het belangrijk dat alle waarden correct worden ingevoerd, want de DNS-instellingen voor uw domein zijn van invloed op belangrijke zakelijke activiteiten, zoals e-mail.</span><span class="sxs-lookup"><span data-stu-id="cae05-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="cae05-107">U kunt controleren op problemen met uw domein door de status ervan te controleren.</span><span class="sxs-lookup"><span data-stu-id="cae05-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="cae05-108">Ga naar **Domeinen**  >  **instellen** en bekijk de meldingen in de **kolom Status.**</span><span class="sxs-lookup"><span data-stu-id="cae05-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="cae05-109">Als u een probleem ziet, selecteert u de drie puntjes (meer acties) en kiest u **vervolgens Status controleren.**</span><span class="sxs-lookup"><span data-stu-id="cae05-109">If you see an issue, select the three dots (more actions), and then choose **Check health**.</span></span> <span data-ttu-id="cae05-110">In het deelvenster dat wordt geopend, worden eventuele problemen met uw domein beschreven.</span><span class="sxs-lookup"><span data-stu-id="cae05-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="cae05-111">Wat gebeurt er?</span><span class="sxs-lookup"><span data-stu-id="cae05-111">What's going on?</span></span>

- [<span data-ttu-id="cae05-112">Kunt u uw domein niet verifiëren?</span><span class="sxs-lookup"><span data-stu-id="cae05-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="cae05-113">Outlook werkt het niet?</span><span class="sxs-lookup"><span data-stu-id="cae05-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="cae05-114">Iedereens e-mail is overgeschakeld naar Microsoft 365 en u wilde alleen dat uw e-mail werd overgeschakeld?</span><span class="sxs-lookup"><span data-stu-id="cae05-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="cae05-115">Kunt u de status van het non-profit- of schoolaccount niet bevestigen?</span><span class="sxs-lookup"><span data-stu-id="cae05-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="cae05-116">Werken services niet met uw domein?</span><span class="sxs-lookup"><span data-stu-id="cae05-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="cae05-117">Werkt toegang tot uw website niet?</span><span class="sxs-lookup"><span data-stu-id="cae05-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="cae05-118">U kunt uw domein niet verifiëren?</span><span class="sxs-lookup"><span data-stu-id="cae05-118">Can't verify your domain?</span></span>
<span data-ttu-id="cae05-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cae05-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cae05-120">Er zijn enkele veelvoorkomende redenen waarom de verificatie van een domein niet werkt zoals het zou moeten:</span><span class="sxs-lookup"><span data-stu-id="cae05-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="cae05-p103">**De waarde van de verificatierecord is niet helemaal juist.** Controleer goed of u de exacte waarde naar de TXT-record voor verificatie bij uw DNS-host hebt gekopieerd en geplakt. Een veelvoorkomende fout is dat het gedeelte 'MS=' van de record niet mee is gekopieerd. Maar dat hebben we ook nodig!</span><span class="sxs-lookup"><span data-stu-id="cae05-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="cae05-125">**De record is niet opgeslagen.**</span><span class="sxs-lookup"><span data-stu-id="cae05-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="cae05-126">Bij sommige DNS-hosts moet u een extra stap nemen om het zonebestand (waarin de DNS-record wordt opgeslagen) op te slaan zodat dit overal op internet wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="cae05-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="cae05-127">Zorg ervoor dat u de wijzigingen hebt opgeslagen, zodat Microsoft 365 de record kan zien en controleren.</span><span class="sxs-lookup"><span data-stu-id="cae05-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="cae05-128">**De record is niet bijgewerkt op internet.**</span><span class="sxs-lookup"><span data-stu-id="cae05-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="cae05-129">Meestal duurt het slechts enkele minuten voordat we de nieuwe record kunnen zien, maar af en toe kan het enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="cae05-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="cae05-130">Outlook werkt niet?</span><span class="sxs-lookup"><span data-stu-id="cae05-130">Outlook isn't working?</span></span>
<span data-ttu-id="cae05-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="cae05-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="cae05-132">Als u uw MX-record en andere DNS-records correct hebt ingesteld voor uw domein, maar e-mail niet werkt, kunnen wij u helpen [uw Outlook-problemen op te lossen](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="cae05-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="cae05-133">Iedereens e-mail is overgeschakeld naar Microsoft 365 en u wilde alleen dat uw e-mail werd overgeschakeld?</span><span class="sxs-lookup"><span data-stu-id="cae05-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="cae05-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="cae05-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="cae05-135">Wanneer u uw domein toevoegt aan Microsoft 365, wordt de MX-record van uw domein meestal bijgewerkt (door u of Microsoft 365) om naar Microsoft 365 te wijzen en alle e-mail die naar dat domein wordt verzonden, wordt Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cae05-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="cae05-136">Zorg ervoor dat u postvakken hebt gemaakt in Microsoft 365 voor iedereen die e-mail in uw domein heeft voordat u de MX-record wijzigt.</span><span class="sxs-lookup"><span data-stu-id="cae05-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="cae05-137">Wat gebeurt er als u e-mail voor iedereen in uw domein niet wilt verplaatsen naar Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="cae05-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="cae05-138">In plaats daarvan kunt u stappen Microsoft 365 [met slechts een paar e-mailadressen.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="cae05-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](../setup/domains-faq.yml).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="cae05-139">Kunt u de status van het non-profit- of schoolaccount niet bevestigen?</span><span class="sxs-lookup"><span data-stu-id="cae05-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="cae05-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="cae05-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="cae05-141">Er zijn een paar scenario's waarin u alleen het domein van uw organisatie hoeft te verifiëren en geen services hoeft in te stellen.</span><span class="sxs-lookup"><span data-stu-id="cae05-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="cae05-142">Bijvoorbeeld om aan te tonen Microsoft 365 dat uw organisatie in aanmerking komt voor een schoolabonnement.</span><span class="sxs-lookup"><span data-stu-id="cae05-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="cae05-143">Bekijk de richtlijnen in Uw Microsoft 365 domein [controleren](../setup/domains-faq.yml) om de eigendomsstatus, non-profitstatus of onderwijsstatus te bewijzen of om Yammer te activeren om ervoor te zorgen dat u alle vereiste stappen hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="cae05-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](../setup/domains-faq.yml) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="cae05-144">Het is een beetje anders voor elke situatie.</span><span class="sxs-lookup"><span data-stu-id="cae05-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="cae05-145">Zijn er services die niet werken met uw domein?</span><span class="sxs-lookup"><span data-stu-id="cae05-145">Services not working with your domain?</span></span>
<span data-ttu-id="cae05-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="cae05-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="cae05-147">We kunnen u helpen bij het vinden van problemen met de DNS-instelling van uw domein.</span><span class="sxs-lookup"><span data-stu-id="cae05-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="cae05-148">De probleemoplosser voor domeinen in Microsoft 365 toont u alle records die moeten worden opgelost en precies waar de records op moeten worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="cae05-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="cae05-149">Hebt u uw DNS-correct ingesteld, maar werkt e-mail niet in Outlook op uw desktopcomputer?</span><span class="sxs-lookup"><span data-stu-id="cae05-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="cae05-150">Bekijk de [verschillende scenario's](/exchange/mail-flow-best-practices/mail-flow-best-practices) voor e-mailstroom die u kunt hebben met Microsoft 365 om ervoor te zorgen dat u de zaken correct hebt ingesteld voor uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="cae05-150">Check out the [different mail flow scenarios you can have with Microsoft 365](/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="cae05-151">Meer hulp bij het oplossen van problemen met e-mail vindt u hier: [Problemen met Outlook oplossen](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="cae05-151">Or get more troubleshooting help with email here: [Fix Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="cae05-152">U krijgt geen toegang tot uw website?</span><span class="sxs-lookup"><span data-stu-id="cae05-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="cae05-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="cae05-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="cae05-154">Als u DNS-problemen hebt opgelost en nog steeds problemen ondervindt, probeer dan een van de volgende opties.</span><span class="sxs-lookup"><span data-stu-id="cae05-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="cae05-155">Personen kunnen uw website op www.mijndomein.com niet bereiken: [Websiteproblemen opsporen](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="cae05-155">People can't get to your website at www.mydomain.com: [Track down website issues](../setup/add-domain.md)</span></span>
    
- <span data-ttu-id="cae05-156">U kunt uw A-record of CNAME-record niet bijwerken om naar uw website te wijzen: [Aangepaste DNS-records bijwerken in Microsoft 365](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="cae05-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../setup/add-domain.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="cae05-157">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="cae05-157">Related content</span></span>

<span data-ttu-id="cae05-158">[Probleem oplossen: Controlegegevens over geverifieerde domeinwijziging](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (artikel)</span><span class="sxs-lookup"><span data-stu-id="cae05-158">[Troubleshoot: Audit data on verified domain change](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (article)</span></span>\
<span data-ttu-id="cae05-159">[Veelgestelde vragen over domeinen](../setup/domains-faq.yml) (artikel)</span><span class="sxs-lookup"><span data-stu-id="cae05-159">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

