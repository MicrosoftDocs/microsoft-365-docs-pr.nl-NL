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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Lees hoe u problemen kunt oplossen bij het instellen van een aangepast domein door ervoor te zorgen dat de DNS-records correct zijn ingesteld.
ms.openlocfilehash: 786df75f3f8a514e9b3c2a7666d715c9abd082bd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926388"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="9b4c1-103">Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd</span><span class="sxs-lookup"><span data-stu-id="9b4c1-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="9b4c1-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9b4c1-105">Het kan lastig zijn om uw domein in te stellen voor gebruik met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="9b4c1-106">Bij het werken met het DNS-systeem is het belangrijk dat alle waarden correct worden ingevoerd, want de DNS-instellingen voor uw domein zijn van invloed op belangrijke zakelijke activiteiten, zoals e-mail.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="9b4c1-107">U kunt controleren op problemen met uw domein door de status ervan te controleren.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="9b4c1-108">Ga naar **Domeinen**  >  **instellen en** bekijk de meldingen in de kolom **Status.**</span><span class="sxs-lookup"><span data-stu-id="9b4c1-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="9b4c1-109">Als u een probleem ziet, selecteert u Meer acties (drie puntjes) en kiest u **Status controleren.**</span><span class="sxs-lookup"><span data-stu-id="9b4c1-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="9b4c1-110">In het deelvenster dat wordt geopend, worden eventuele problemen met uw domein beschreven.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="9b4c1-111">Wat gebeurt er?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-111">What's going on?</span></span>

- [<span data-ttu-id="9b4c1-112">Kunt u uw domein niet verifiëren?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="9b4c1-113">Werkt Outlook niet?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="9b4c1-114">Zijn alle e-mailberichten overgeschakeld naar Microsoft 365 en wilt u alleen uw e-mail laten overstappen?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="9b4c1-115">Kunt u de status van het non-profit- of schoolaccount niet bevestigen?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="9b4c1-116">Werken services niet met uw domein?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="9b4c1-117">Werkt toegang tot uw website niet?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="9b4c1-118">U kunt uw domein niet verifiëren?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-118">Can't verify your domain?</span></span>
<span data-ttu-id="9b4c1-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4c1-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9b4c1-120">Er zijn enkele veelvoorkomende redenen waarom de verificatie van een domein niet werkt zoals het zou moeten:</span><span class="sxs-lookup"><span data-stu-id="9b4c1-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="9b4c1-p103">**De waarde van de verificatierecord is niet helemaal juist.** Controleer goed of u de exacte waarde naar de TXT-record voor verificatie bij uw DNS-host hebt gekopieerd en geplakt. Een veelvoorkomende fout is dat het gedeelte 'MS=' van de record niet mee is gekopieerd. Maar dat hebben we ook nodig!</span><span class="sxs-lookup"><span data-stu-id="9b4c1-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="9b4c1-125">**De record is niet opgeslagen.**</span><span class="sxs-lookup"><span data-stu-id="9b4c1-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="9b4c1-126">Bij sommige DNS-hosts moet u een extra stap nemen om het zonebestand (waarin de DNS-record wordt opgeslagen) op te slaan zodat dit overal op internet wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="9b4c1-127">Zorg ervoor dat u uw wijzigingen hebt opgeslagen, zodat Microsoft 365 de record kan zien en controleren.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="9b4c1-128">**De record is nog niet overal op internet bijgewerkt.**</span><span class="sxs-lookup"><span data-stu-id="9b4c1-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="9b4c1-129">Het duurt meestal slechts een paar minuten voordat we de nieuwe record kunnen zien, maar soms duurt het wel een paar uur.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="9b4c1-130">Outlook werkt niet?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-130">Outlook isn't working?</span></span>
<span data-ttu-id="9b4c1-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4c1-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="9b4c1-132">Als u uw MX-record en andere DNS-records correct hebt ingesteld voor uw domein, maar e-mail niet werkt, kunnen wij u helpen [uw Outlook-problemen op te lossen](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="9b4c1-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="9b4c1-133">Zijn alle e-mailberichten overgeschakeld naar Microsoft 365 en wilt u alleen uw e-mail laten overstappen?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="9b4c1-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4c1-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="9b4c1-135">Wanneer u uw domein toevoegt aan Microsoft 365, wordt de MX-record van uw domein meestal bijgewerkt (door u of Microsoft 365) zodat deze naar Microsoft 365 wijst. ALLE e-mail die naar dat domein wordt verzonden, wordt nu verzonden naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="9b4c1-136">Zorg ervoor dat u in Microsoft 365 postvakken hebt gemaakt voor iedereen die een e-mailaccount in uw domein heeft, VOORDAT u de MX-record wijzigt.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="9b4c1-137">Wat moet u doen als u niet voor iedereen in uw domein e-mail wilt verplaatsen naar Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="9b4c1-138">In plaats daarvan kunt u stappen ondernemen [om Microsoft 365 met slechts een paar e-mailadressen te piloten.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="9b4c1-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="9b4c1-139">Kunt u de status van het non-profit- of schoolaccount niet bevestigen?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="9b4c1-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4c1-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="9b4c1-141">Er zijn een paar scenario's waarin u het domein van uw organisatie hoeft te verifiëren en geen services hoeft in te stellen.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="9b4c1-142">Bijvoorbeeld om te bewijzen voor Microsoft 365 dat uw organisatie in aanmerking komt voor een schoolabonnement.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="9b4c1-143">Raadpleeg de richtlijnen in [Uw Microsoft 365-domein](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) verifiëren om te bewijzen dat u de eigenaar bent, de status van een non-profitorganisatie of onderwijsorganisatie, of om Yammer te activeren om te controleren of u alle vereiste stappen hebt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="9b4c1-144">Het verschilt per situatie.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="9b4c1-145">Zijn er services die niet werken met uw domein?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-145">Services not working with your domain?</span></span>
<span data-ttu-id="9b4c1-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4c1-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="9b4c1-147">We kunnen u helpen bij het oplossen van problemen met de DNS-instellingen van uw domein.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="9b4c1-148">De probleemoplosser voor domeinen in Microsoft 365 toont alle records die moeten worden opgelost en precies op welke records moet worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="9b4c1-149">Hebt u uw DNS-correct ingesteld, maar werkt e-mail niet in Outlook op uw desktopcomputer?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="9b4c1-150">Bekijk de verschillende scenario's voor e-mailstroom die u kunt hebben met [Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) om er zeker van te zijn dat u alles correct hebt ingesteld voor uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-150">Check out the [different mail flow scenarios you can have with Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="9b4c1-151">Meer hulp bij het oplossen van problemen met e-mail vindt u hier: [Problemen met Outlook oplossen](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="9b4c1-151">Or get more troubleshooting help with email here: [Fix Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="9b4c1-152">U krijgt geen toegang tot uw website?</span><span class="sxs-lookup"><span data-stu-id="9b4c1-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="9b4c1-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="9b4c1-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="9b4c1-154">Als u DNS-problemen hebt opgelost en nog steeds problemen ondervindt, probeer dan een van de volgende opties.</span><span class="sxs-lookup"><span data-stu-id="9b4c1-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="9b4c1-155">Personen kunnen uw website op www.mijndomein.com niet bereiken: [Websiteproblemen opsporen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="9b4c1-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span></span>
    
- <span data-ttu-id="9b4c1-156">U kunt uw A-record of CNAME-record niet bijwerken zodat deze naar uw website wijzen: Aangepaste [DNS-records bijwerken in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="9b4c1-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="9b4c1-157">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9b4c1-157">Related content</span></span>

[<span data-ttu-id="9b4c1-158">Problemen oplossen: Gegevens voor gecontroleerde domeinwijziging controleren</span><span class="sxs-lookup"><span data-stu-id="9b4c1-158">Troubleshoot: Audit data on verified domain change</span></span>](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
