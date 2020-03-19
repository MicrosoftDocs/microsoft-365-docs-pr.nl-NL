---
title: DNS-records maken bij easyDNS voor Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services op easyDNS voor Office 365.
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807420"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a><span data-ttu-id="aabbe-103">DNS-records maken bij easyDNS voor Office 365</span><span class="sxs-lookup"><span data-stu-id="aabbe-103">Create DNS records at easyDNS for Office 365</span></span>

<span data-ttu-id="aabbe-104">[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="aabbe-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="aabbe-105">U moet alle volgende DNS-records toevoegen op de website van uw registrar om e-mail naar Office 365 te routeren, uw domein te gebruiken voor Teams en Skype voor Bedrijven, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="aabbe-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Office 365, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="aabbe-106">OPMERKING: SRV Records zijn momenteel niet beschikbaar onder alle easyDNS-servicepakketten.</span><span class="sxs-lookup"><span data-stu-id="aabbe-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="aabbe-107">Mogelijk moet u upgraden naar een hoger serviceniveau met easyDNS om SRV-records toe te voegen die vereist zijn voor Office 365 Skype voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="aabbe-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Office 365 Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="aabbe-108">Controleren of u eigenaar bent van het domein met een TXT-record</span><span class="sxs-lookup"><span data-stu-id="aabbe-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="aabbe-109">Ga [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) naar en log in met je referenties.</span><span class="sxs-lookup"><span data-stu-id="aabbe-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="aabbe-110">Selecteer onder de kop **alle domeinen** **dns.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="aabbe-111">Selecteer onder de kop **TXT-records** de knop Bewerken (sleutelpictogram).</span><span class="sxs-lookup"><span data-stu-id="aabbe-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="aabbe-112">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="aabbe-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="aabbe-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="aabbe-113">**Host**</span></span>|<span data-ttu-id="aabbe-114">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="aabbe-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="aabbe-115">MS=msXXXXXXXX (Gebruik de waarde die u wordt verstrekt op de pagina Domeinen van het beheercentrum)</span><span class="sxs-lookup"><span data-stu-id="aabbe-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="aabbe-116">Selecteer **VOLGENDE**.</span><span class="sxs-lookup"><span data-stu-id="aabbe-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="aabbe-117">Controleer of de record correct is en selecteer **BEVESTIGEN.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="aabbe-118">Wacht een paar minuten voordat u verdergaat, zodat de record die u zojuist hebt gemaakt, kan worden doorgegeven via internet en kan worden gedetecteerd door Office 365.</span><span class="sxs-lookup"><span data-stu-id="aabbe-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Office 365.</span></span>
    
8. <span data-ttu-id="aabbe-119">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="aabbe-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
    
9. <span data-ttu-id="aabbe-120">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="aabbe-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="aabbe-121">Selecteer op de pagina **Domeinen** het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="aabbe-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="aabbe-122">Selecteer op de pagina **Setup** **de optie Startinstelling.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="aabbe-123">Selecteer op de pagina **Domein verifiëren** de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="aabbe-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a><span data-ttu-id="aabbe-124">Een MX-record toevoegen om e-mail naar Office 365 te routeren</span><span class="sxs-lookup"><span data-stu-id="aabbe-124">Add an MX record to route email to Office 365</span></span>

1. <span data-ttu-id="aabbe-125">Ga [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) naar en log in met je referenties.</span><span class="sxs-lookup"><span data-stu-id="aabbe-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="aabbe-126">Selecteer onder de kop **alle domeinen** **dns.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="aabbe-127">Selecteer onder de kop **MX-records** de knop Bewerken (sleutelpictogram).</span><span class="sxs-lookup"><span data-stu-id="aabbe-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="aabbe-128">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="aabbe-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="aabbe-129">**POST VOOR ZONE**</span><span class="sxs-lookup"><span data-stu-id="aabbe-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="aabbe-130">**MAILSERVER**</span><span class="sxs-lookup"><span data-stu-id="aabbe-130">**MAIL SERVER**</span></span>|<span data-ttu-id="aabbe-131">**PREF PREF**</span><span class="sxs-lookup"><span data-stu-id="aabbe-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="aabbe-132">\<domeintoets\>.mail.protection.outlook.com (Haal \<de\> waarde van uw domeinsleutel op vanaf de pagina Domeinen van het beheercentrum)</span><span class="sxs-lookup"><span data-stu-id="aabbe-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="aabbe-133">0</span><span class="sxs-lookup"><span data-stu-id="aabbe-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="aabbe-134">Als u uw andere MX-records wilt opslaan voor back-updoeleinden, kopieert u ze ergens.</span><span class="sxs-lookup"><span data-stu-id="aabbe-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="aabbe-135">Voordat u verder gaat, verwijdert u hier alle andere MX-records.</span><span class="sxs-lookup"><span data-stu-id="aabbe-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="aabbe-136">Selecteer **VOLGENDE**.</span><span class="sxs-lookup"><span data-stu-id="aabbe-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="aabbe-137">Controleer of de record correct is en selecteer **BEVESTIGEN.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="aabbe-138">De vereiste CNAME-records toevoegen</span><span class="sxs-lookup"><span data-stu-id="aabbe-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="aabbe-139">Ga [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) naar en log in met je referenties.</span><span class="sxs-lookup"><span data-stu-id="aabbe-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="aabbe-140">Selecteer onder de kop **alle domeinen** **dns.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="aabbe-141">Selecteer onder de kop **CNAME/Alias-records** de knop Bewerken (sleutelpictogram).</span><span class="sxs-lookup"><span data-stu-id="aabbe-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="aabbe-142">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="aabbe-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="aabbe-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="aabbe-143">**HOST**</span></span>|<span data-ttu-id="aabbe-144">**Adres (Moet eindigen met een ".")**</span><span class="sxs-lookup"><span data-stu-id="aabbe-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="aabbe-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="aabbe-145">autodiscover</span></span>  <br/> |<span data-ttu-id="aabbe-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="aabbe-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="aabbe-147">sip</span><span class="sxs-lookup"><span data-stu-id="aabbe-147">sip</span></span>  <br/> |<span data-ttu-id="aabbe-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aabbe-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="aabbe-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="aabbe-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="aabbe-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aabbe-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="aabbe-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="aabbe-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="aabbe-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="aabbe-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="aabbe-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="aabbe-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="aabbe-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="aabbe-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="aabbe-155">Selecteer **VOLGENDE**.</span><span class="sxs-lookup"><span data-stu-id="aabbe-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="aabbe-156">Controleer of de record correct is en selecteer **BEVESTIGEN.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="aabbe-157">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="aabbe-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="aabbe-158">Ga [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) naar en log in met je referenties.</span><span class="sxs-lookup"><span data-stu-id="aabbe-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="aabbe-159">Selecteer onder de kop **alle domeinen** **dns.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="aabbe-160">Selecteer onder de kop **TXT-records** de knop Bewerken (sleutelpictogram).</span><span class="sxs-lookup"><span data-stu-id="aabbe-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="aabbe-161">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="aabbe-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="aabbe-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="aabbe-162">**Host**</span></span>|<span data-ttu-id="aabbe-163">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="aabbe-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="aabbe-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="aabbe-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="aabbe-165">Selecteer **VOLGENDE**.</span><span class="sxs-lookup"><span data-stu-id="aabbe-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="aabbe-166">Controleer of de record correct is en selecteer **BEVESTIGEN.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="aabbe-167">De twee SRV-records toevoegen die nodig zijn voor Office 365</span><span class="sxs-lookup"><span data-stu-id="aabbe-167">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="aabbe-168">OPMERKING: SRV Records zijn momenteel NIET beschikbaar onder het domein plus-serviceniveau van easyDNS.</span><span class="sxs-lookup"><span data-stu-id="aabbe-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="aabbe-169">Mogelijk moet u upgraden naar een hoger serviceniveau met easyDNS om SRV-records toe te voegen</span><span class="sxs-lookup"><span data-stu-id="aabbe-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="aabbe-170">Ga [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) naar en log in met je referenties.</span><span class="sxs-lookup"><span data-stu-id="aabbe-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="aabbe-171">Selecteer onder de kop **alle domeinen** **dns.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="aabbe-172">Selecteer onder de kop **SRV-records** de knop Bewerken (sleutelpictogram).</span><span class="sxs-lookup"><span data-stu-id="aabbe-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="aabbe-173">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="aabbe-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="aabbe-174">**SERVICE**</span><span class="sxs-lookup"><span data-stu-id="aabbe-174">**SERVICE**</span></span>|<span data-ttu-id="aabbe-175">**Proto**</span><span class="sxs-lookup"><span data-stu-id="aabbe-175">**PROTO**</span></span>|<span data-ttu-id="aabbe-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="aabbe-176">**HOST**</span></span>|<span data-ttu-id="aabbe-177">**Pri**</span><span class="sxs-lookup"><span data-stu-id="aabbe-177">**PRI**</span></span>|<span data-ttu-id="aabbe-178">**WGT (WGT)**</span><span class="sxs-lookup"><span data-stu-id="aabbe-178">**WGT**</span></span>|<span data-ttu-id="aabbe-179">**PORT**</span><span class="sxs-lookup"><span data-stu-id="aabbe-179">**PORT**</span></span>|<span data-ttu-id="aabbe-180">**TARGET(Moet eindigen met een ".")**</span><span class="sxs-lookup"><span data-stu-id="aabbe-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="aabbe-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="aabbe-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="aabbe-182">_sip</span><span class="sxs-lookup"><span data-stu-id="aabbe-182">_sip</span></span>  <br/> |<span data-ttu-id="aabbe-183">TLS</span><span class="sxs-lookup"><span data-stu-id="aabbe-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="aabbe-184">100</span><span class="sxs-lookup"><span data-stu-id="aabbe-184">100</span></span>  <br/> |<span data-ttu-id="aabbe-185">1</span><span class="sxs-lookup"><span data-stu-id="aabbe-185">1</span></span>  <br/> |<span data-ttu-id="aabbe-186">443</span><span class="sxs-lookup"><span data-stu-id="aabbe-186">443</span></span>  <br/> |<span data-ttu-id="aabbe-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aabbe-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="aabbe-188">1800</span><span class="sxs-lookup"><span data-stu-id="aabbe-188">1800</span></span>  <br/> |
    |<span data-ttu-id="aabbe-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="aabbe-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="aabbe-190">TCP</span><span class="sxs-lookup"><span data-stu-id="aabbe-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="aabbe-191">100</span><span class="sxs-lookup"><span data-stu-id="aabbe-191">100</span></span>  <br/> |<span data-ttu-id="aabbe-192">1</span><span class="sxs-lookup"><span data-stu-id="aabbe-192">1</span></span>  <br/> |<span data-ttu-id="aabbe-193">5061</span><span class="sxs-lookup"><span data-stu-id="aabbe-193">5061</span></span>  <br/> |<span data-ttu-id="aabbe-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="aabbe-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="aabbe-195">1800</span><span class="sxs-lookup"><span data-stu-id="aabbe-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="aabbe-196">Selecteer **VOLGENDE**.</span><span class="sxs-lookup"><span data-stu-id="aabbe-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="aabbe-197">Controleer of de record correct is en selecteer **BEVESTIGEN.**</span><span class="sxs-lookup"><span data-stu-id="aabbe-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

