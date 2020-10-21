---
title: DNS-records bij easyDNS maken voor Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op easyDNS voor Microsoft.
ms.openlocfilehash: 4909a02ec56fc9720a2636e822da0339e89bccf8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645549"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="8a788-103">DNS-records bij easyDNS maken voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a788-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="8a788-104">[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="8a788-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8a788-105">Voor het routeren van e-mail naar Microsoft moet u alle volgende DNS-records toevoegen op de website van uw bewaarder, uw domein gebruiken voor teams en Skype voor bedrijven, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="8a788-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="8a788-106">Opmerking: SRV-records zijn momenteel niet beschikbaar onder alle easyDNS-servicepakketten.</span><span class="sxs-lookup"><span data-stu-id="8a788-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="8a788-107">Mogelijk moet u upgraden naar een hoger serviceniveau met easyDNS om SRV-records toe te voegen die vereist zijn voor Skype voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="8a788-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="8a788-108">Controleren of u de eigenaar bent van het domein met een TXT-record</span><span class="sxs-lookup"><span data-stu-id="8a788-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="8a788-109">Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en meld u aan met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="8a788-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="8a788-110">Selecteer DNS onder de kop **all domains** **.**</span><span class="sxs-lookup"><span data-stu-id="8a788-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="8a788-111">Selecteer onder de kop **TXT-records** de knop bewerken (gereedschap pictogram).</span><span class="sxs-lookup"><span data-stu-id="8a788-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="8a788-112">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="8a788-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="8a788-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="8a788-113">**Host**</span></span>|<span data-ttu-id="8a788-114">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="8a788-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="8a788-115">MS = msXXXXXXXX (gebruik de waarde die u hebt opgegeven op de pagina domeinen in het Beheercentrum).</span><span class="sxs-lookup"><span data-stu-id="8a788-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="8a788-116">Selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="8a788-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="8a788-117">Controleer of de record klopt en selecteer vervolgens **bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="8a788-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="8a788-118">Wacht een paar minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden gedetecteerd en door Microsoft wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="8a788-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="8a788-119">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="8a788-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="8a788-120">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="8a788-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="8a788-121">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="8a788-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="8a788-122">Selecteer op de pagina **Setup** de optie **Setup starten.**</span><span class="sxs-lookup"><span data-stu-id="8a788-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="8a788-123">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="8a788-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="8a788-124">Een MX-record toevoegen om e-mail rond Microsoft te routeren</span><span class="sxs-lookup"><span data-stu-id="8a788-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="8a788-125">Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en meld u aan met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="8a788-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="8a788-126">Selecteer DNS onder de kop **all domains** **.**</span><span class="sxs-lookup"><span data-stu-id="8a788-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="8a788-127">Selecteer onder de kop **MX-records** de knop bewerken (gereedschap pictogram).</span><span class="sxs-lookup"><span data-stu-id="8a788-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="8a788-128">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="8a788-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="8a788-129">**E-MAIL VOOR ZONE**</span><span class="sxs-lookup"><span data-stu-id="8a788-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="8a788-130">**E-MAIL SERVER**</span><span class="sxs-lookup"><span data-stu-id="8a788-130">**MAIL SERVER**</span></span>|<span data-ttu-id="8a788-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="8a788-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8a788-132">\<domain-key\>. mail.protection.outlook.com (de \<domain-key\> waarde van de pagina Domains voor het Beheercentrum kopen)</span><span class="sxs-lookup"><span data-stu-id="8a788-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="8a788-133">0</span><span class="sxs-lookup"><span data-stu-id="8a788-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="8a788-134">Als u uw andere MX-records wilt opslaan voor reservekopieën, kopieert u deze naar een willekeurige plaats.</span><span class="sxs-lookup"><span data-stu-id="8a788-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="8a788-135">Verwijder alle andere MX-records hier voordat u verdergaat.</span><span class="sxs-lookup"><span data-stu-id="8a788-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="8a788-136">Selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="8a788-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="8a788-137">Controleer of de record klopt en selecteer vervolgens **bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="8a788-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="8a788-138">De vereiste CNAME-records toevoegen</span><span class="sxs-lookup"><span data-stu-id="8a788-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="8a788-139">Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en meld u aan met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="8a788-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="8a788-140">Selecteer DNS onder de kop **all domains** **.**</span><span class="sxs-lookup"><span data-stu-id="8a788-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="8a788-141">Selecteer onder de kop **CNAME/alias records** de knop bewerken (gereedschap pictogram).</span><span class="sxs-lookup"><span data-stu-id="8a788-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="8a788-142">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="8a788-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="8a788-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="8a788-143">**HOST**</span></span>|<span data-ttu-id="8a788-144">**Adres (moet eindigen op een '. ')**</span><span class="sxs-lookup"><span data-stu-id="8a788-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8a788-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8a788-145">autodiscover</span></span>  <br/> |<span data-ttu-id="8a788-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8a788-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="8a788-147">sip</span><span class="sxs-lookup"><span data-stu-id="8a788-147">sip</span></span>  <br/> |<span data-ttu-id="8a788-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8a788-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="8a788-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8a788-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8a788-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8a788-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="8a788-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8a788-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8a788-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="8a788-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="8a788-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8a788-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8a788-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8a788-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="8a788-155">Selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="8a788-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="8a788-156">Controleer of de record klopt en selecteer vervolgens **bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="8a788-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8a788-157">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="8a788-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="8a788-158">Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en meld u aan met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="8a788-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="8a788-159">Selecteer DNS onder de kop **all domains** **.**</span><span class="sxs-lookup"><span data-stu-id="8a788-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="8a788-160">Selecteer onder de kop **TXT-records** de knop bewerken (gereedschap pictogram).</span><span class="sxs-lookup"><span data-stu-id="8a788-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="8a788-161">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="8a788-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="8a788-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="8a788-162">**Host**</span></span>|<span data-ttu-id="8a788-163">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="8a788-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="8a788-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8a788-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="8a788-165">Selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="8a788-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="8a788-166">Controleer of de record klopt en selecteer vervolgens **bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="8a788-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8a788-167">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a788-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="8a788-168">Opmerking: SRV-records zijn momenteel niet beschikbaar onder easyDNS ' domein plus serviceniveau.</span><span class="sxs-lookup"><span data-stu-id="8a788-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="8a788-169">Mogelijk moet u een upgrade uitvoeren naar een hoger serviceniveau met easyDNS om SRV-records toe te voegen</span><span class="sxs-lookup"><span data-stu-id="8a788-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="8a788-170">Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en meld u aan met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="8a788-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="8a788-171">Selecteer DNS onder de kop **all domains** **.**</span><span class="sxs-lookup"><span data-stu-id="8a788-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="8a788-172">Selecteer onder de kop **SRV records** de knop bewerken (gereedschap pictogram).</span><span class="sxs-lookup"><span data-stu-id="8a788-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="8a788-173">Voer de volgende records in de tekstvelden in:</span><span class="sxs-lookup"><span data-stu-id="8a788-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="8a788-174">**SERVICE**</span><span class="sxs-lookup"><span data-stu-id="8a788-174">**SERVICE**</span></span>|<span data-ttu-id="8a788-175">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="8a788-175">**PROTO**</span></span>|<span data-ttu-id="8a788-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="8a788-176">**HOST**</span></span>|<span data-ttu-id="8a788-177">**PRIORITEIT**</span><span class="sxs-lookup"><span data-stu-id="8a788-177">**PRI**</span></span>|<span data-ttu-id="8a788-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="8a788-178">**WGT**</span></span>|<span data-ttu-id="8a788-179">**PORT**</span><span class="sxs-lookup"><span data-stu-id="8a788-179">**PORT**</span></span>|<span data-ttu-id="8a788-180">**DOEL (moet eindigen op '. ')**</span><span class="sxs-lookup"><span data-stu-id="8a788-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="8a788-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a788-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8a788-182">_sip</span><span class="sxs-lookup"><span data-stu-id="8a788-182">_sip</span></span>  <br/> |<span data-ttu-id="8a788-183">TLS</span><span class="sxs-lookup"><span data-stu-id="8a788-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="8a788-184">100</span><span class="sxs-lookup"><span data-stu-id="8a788-184">100</span></span>  <br/> |<span data-ttu-id="8a788-185">1</span><span class="sxs-lookup"><span data-stu-id="8a788-185">1</span></span>  <br/> |<span data-ttu-id="8a788-186">443</span><span class="sxs-lookup"><span data-stu-id="8a788-186">443</span></span>  <br/> |<span data-ttu-id="8a788-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8a788-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="8a788-188">1800</span><span class="sxs-lookup"><span data-stu-id="8a788-188">1800</span></span>  <br/> |
    |<span data-ttu-id="8a788-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8a788-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="8a788-190">TCP</span><span class="sxs-lookup"><span data-stu-id="8a788-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="8a788-191">100</span><span class="sxs-lookup"><span data-stu-id="8a788-191">100</span></span>  <br/> |<span data-ttu-id="8a788-192">1</span><span class="sxs-lookup"><span data-stu-id="8a788-192">1</span></span>  <br/> |<span data-ttu-id="8a788-193">5061</span><span class="sxs-lookup"><span data-stu-id="8a788-193">5061</span></span>  <br/> |<span data-ttu-id="8a788-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8a788-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="8a788-195">1800</span><span class="sxs-lookup"><span data-stu-id="8a788-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="8a788-196">Selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="8a788-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="8a788-197">Controleer of de record klopt en selecteer vervolgens **bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="8a788-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

