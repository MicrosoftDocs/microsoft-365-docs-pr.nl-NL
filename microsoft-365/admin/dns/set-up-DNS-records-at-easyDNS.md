---
title: DNS-records maken bij easyDNS voor Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij easyDNS voor Microsoft.
ms.openlocfilehash: 24f477d240af936975141c53d382e114a24c0ac5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400230"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="eadf9-103">DNS-records maken bij easyDNS voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="eadf9-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="eadf9-104">[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="eadf9-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="eadf9-105">U moet alle volgende DNS-records op de website van uw registrar toevoegen om e-mail naar Microsoft te routeren, uw domein te gebruiken voor Teams en Skype voor Bedrijven, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="eadf9-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="eadf9-106">LET OP: SRV Records zijn momenteel NIET beschikbaar onder alle easyDNS-servicepakketten.</span><span class="sxs-lookup"><span data-stu-id="eadf9-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="eadf9-107">Mogelijk moet u upgraden naar een hoger serviceniveau met easyDNS om SRV-records toe te voegen die nodig zijn voor Skype voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="eadf9-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="eadf9-108">Controleren of u eigenaar bent van het domein met een TXT-record</span><span class="sxs-lookup"><span data-stu-id="eadf9-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="eadf9-109">Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en log in met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="eadf9-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="eadf9-110">Selecteer dns onder de kop **alle domeinen.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="eadf9-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="eadf9-111">Selecteer onder de kop **TXT-records** de bewerkingsknop (moersleutelpictogram).</span><span class="sxs-lookup"><span data-stu-id="eadf9-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="eadf9-112">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="eadf9-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="eadf9-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="eadf9-113">**Host**</span></span>|<span data-ttu-id="eadf9-114">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="eadf9-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="eadf9-115">MS=msXXXXXXXX (Gebruik de waarde die u wordt verstrekt op de pagina Domeinen van het beheercentrum)</span><span class="sxs-lookup"><span data-stu-id="eadf9-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="eadf9-116">Selecteer **VOLGENDE**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="eadf9-117">Controleer of de record correct is en selecteer **BEVESTIGEN**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="eadf9-118">Wacht een paar minuten voordat u verdergaat, zodat de record die u zojuist hebt gemaakt, zich over het internet kan verspreiden en door Microsoft kan worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="eadf9-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="eadf9-119">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="eadf9-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="eadf9-120">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="eadf9-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="eadf9-121">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="eadf9-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="eadf9-122">Selecteer **Op** de pagina Setup de optie **Installatie starten.**</span><span class="sxs-lookup"><span data-stu-id="eadf9-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="eadf9-123">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="eadf9-124">Een MX-record toevoegen om e-mail naar Microsoft te routeren</span><span class="sxs-lookup"><span data-stu-id="eadf9-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="eadf9-125">Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en log in met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="eadf9-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="eadf9-126">Selecteer dns onder de kop **alle domeinen.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="eadf9-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="eadf9-127">Selecteer onder de kop **MX-records** de knop bewerken (moersleutelpictogram).</span><span class="sxs-lookup"><span data-stu-id="eadf9-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="eadf9-128">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="eadf9-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="eadf9-129">**E-MAIL VOOR ZONE**</span><span class="sxs-lookup"><span data-stu-id="eadf9-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="eadf9-130">**MAILSERVER**</span><span class="sxs-lookup"><span data-stu-id="eadf9-130">**MAIL SERVER**</span></span>|<span data-ttu-id="eadf9-131">**PREF PREF**</span><span class="sxs-lookup"><span data-stu-id="eadf9-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="eadf9-132">\<domain-key\>.mail.protection.outlook.com (Uw \<domain-key\> waarde ophalen via de pagina Domeinen van het beheercentrum)</span><span class="sxs-lookup"><span data-stu-id="eadf9-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="eadf9-133">0</span><span class="sxs-lookup"><span data-stu-id="eadf9-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="eadf9-134">Als u uw andere MX-records wilt opslaan voor back-updoeleinden, kopieert u deze ergens naar beneden.</span><span class="sxs-lookup"><span data-stu-id="eadf9-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="eadf9-135">Verwijder alle andere MX-records voordat u verdergaat met het verwijderen van alle andere MX-records.</span><span class="sxs-lookup"><span data-stu-id="eadf9-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="eadf9-136">Selecteer **VOLGENDE**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="eadf9-137">Controleer of de record correct is en selecteer **BEVESTIGEN**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="eadf9-138">De vereiste CNAME-records toevoegen</span><span class="sxs-lookup"><span data-stu-id="eadf9-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="eadf9-139">Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en log in met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="eadf9-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="eadf9-140">Selecteer dns onder de kop **alle domeinen.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="eadf9-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="eadf9-141">Selecteer onder de kop **CNAME/Alias records** de knop bewerken (moersleutelpictogram).</span><span class="sxs-lookup"><span data-stu-id="eadf9-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="eadf9-142">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="eadf9-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="eadf9-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="eadf9-143">**HOST**</span></span>|<span data-ttu-id="eadf9-144">**Adres (Moet eindigen met een ".")**</span><span class="sxs-lookup"><span data-stu-id="eadf9-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="eadf9-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="eadf9-145">autodiscover</span></span>  <br/> |<span data-ttu-id="eadf9-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="eadf9-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="eadf9-147">sip</span><span class="sxs-lookup"><span data-stu-id="eadf9-147">sip</span></span>  <br/> |<span data-ttu-id="eadf9-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eadf9-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="eadf9-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="eadf9-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="eadf9-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eadf9-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="eadf9-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="eadf9-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="eadf9-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="eadf9-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="eadf9-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="eadf9-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="eadf9-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="eadf9-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="eadf9-155">Selecteer **VOLGENDE**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="eadf9-156">Controleer of de record correct is en selecteer **BEVESTIGEN**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="eadf9-157">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="eadf9-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="eadf9-158">Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en log in met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="eadf9-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="eadf9-159">Selecteer dns onder de kop **alle domeinen.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="eadf9-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="eadf9-160">Selecteer onder de kop **TXT-records** de bewerkingsknop (moersleutelpictogram).</span><span class="sxs-lookup"><span data-stu-id="eadf9-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="eadf9-161">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="eadf9-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="eadf9-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="eadf9-162">**Host**</span></span>|<span data-ttu-id="eadf9-163">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="eadf9-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="eadf9-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="eadf9-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="eadf9-165">Selecteer **VOLGENDE**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="eadf9-166">Controleer of de record correct is en selecteer **BEVESTIGEN**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="eadf9-167">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="eadf9-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="eadf9-168">LET OP: SRV Records zijn momenteel NIET beschikbaar onder het Domein Plus-serviceniveau van easyDNS.</span><span class="sxs-lookup"><span data-stu-id="eadf9-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="eadf9-169">Mogelijk moet u upgraden naar een hoger serviceniveau met easyDNS om SRV-records toe te voegen</span><span class="sxs-lookup"><span data-stu-id="eadf9-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="eadf9-170">Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en log in met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="eadf9-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="eadf9-171">Selecteer dns onder de kop **alle domeinen.** **dns.**</span><span class="sxs-lookup"><span data-stu-id="eadf9-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="eadf9-172">Selecteer onder de kop **SRV-records** de knop bewerken (moersleutelpictogram).</span><span class="sxs-lookup"><span data-stu-id="eadf9-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="eadf9-173">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="eadf9-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="eadf9-174">**SERVICE**</span><span class="sxs-lookup"><span data-stu-id="eadf9-174">**SERVICE**</span></span>|<span data-ttu-id="eadf9-175">**Proto**</span><span class="sxs-lookup"><span data-stu-id="eadf9-175">**PROTO**</span></span>|<span data-ttu-id="eadf9-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="eadf9-176">**HOST**</span></span>|<span data-ttu-id="eadf9-177">**Pri**</span><span class="sxs-lookup"><span data-stu-id="eadf9-177">**PRI**</span></span>|<span data-ttu-id="eadf9-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="eadf9-178">**WGT**</span></span>|<span data-ttu-id="eadf9-179">**PORT**</span><span class="sxs-lookup"><span data-stu-id="eadf9-179">**PORT**</span></span>|<span data-ttu-id="eadf9-180">**TARGET(Moet eindigen met een ".")**</span><span class="sxs-lookup"><span data-stu-id="eadf9-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="eadf9-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eadf9-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="eadf9-182">_sip</span><span class="sxs-lookup"><span data-stu-id="eadf9-182">_sip</span></span>  <br/> |<span data-ttu-id="eadf9-183">TLS</span><span class="sxs-lookup"><span data-stu-id="eadf9-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="eadf9-184">100</span><span class="sxs-lookup"><span data-stu-id="eadf9-184">100</span></span>  <br/> |<span data-ttu-id="eadf9-185">1</span><span class="sxs-lookup"><span data-stu-id="eadf9-185">1</span></span>  <br/> |<span data-ttu-id="eadf9-186">443</span><span class="sxs-lookup"><span data-stu-id="eadf9-186">443</span></span>  <br/> |<span data-ttu-id="eadf9-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eadf9-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="eadf9-188">1800</span><span class="sxs-lookup"><span data-stu-id="eadf9-188">1800</span></span>  <br/> |
    |<span data-ttu-id="eadf9-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="eadf9-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="eadf9-190">TCP</span><span class="sxs-lookup"><span data-stu-id="eadf9-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="eadf9-191">100</span><span class="sxs-lookup"><span data-stu-id="eadf9-191">100</span></span>  <br/> |<span data-ttu-id="eadf9-192">1</span><span class="sxs-lookup"><span data-stu-id="eadf9-192">1</span></span>  <br/> |<span data-ttu-id="eadf9-193">5061</span><span class="sxs-lookup"><span data-stu-id="eadf9-193">5061</span></span>  <br/> |<span data-ttu-id="eadf9-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eadf9-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="eadf9-195">1800</span><span class="sxs-lookup"><span data-stu-id="eadf9-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="eadf9-196">Selecteer **VOLGENDE**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="eadf9-197">Controleer of de record correct is en selecteer **BEVESTIGEN**.</span><span class="sxs-lookup"><span data-stu-id="eadf9-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

