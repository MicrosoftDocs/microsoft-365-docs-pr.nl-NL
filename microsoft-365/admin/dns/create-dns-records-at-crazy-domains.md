---
title: DNS-records maken bij Crazy Domains voor Microsoft
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Crazy Domains voor Microsoft.
ms.openlocfilehash: db8979d303e4749a2a04870d277b68e5aec2e52f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629693"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="7c10d-103">DNS-records maken bij Crazy Domains voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c10d-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="7c10d-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="7c10d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7c10d-105">Als Crazy Domains uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="7c10d-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7c10d-106">Nadat u deze records hebt toegevoegd bij Crazy Domains, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="7c10d-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="7c10d-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="7c10d-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c10d-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7c10d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7c10d-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="7c10d-111">Add a TXT record for verification</span></span>
<span data-ttu-id="7c10d-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7c10d-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7c10d-113">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="7c10d-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="7c10d-114">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="7c10d-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c10d-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7c10d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7c10d-p104">Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7c10d-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="7c10d-120">Selecteer **Domeinen**in de sectie **Mijn account** .</span><span class="sxs-lookup"><span data-stu-id="7c10d-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="7c10d-122">Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="7c10d-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="7c10d-124">Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram.</span><span class="sxs-lookup"><span data-stu-id="7c10d-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="7c10d-126">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-126">Select **Add Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="7c10d-128">Kies **TXT Record** in de vervolgkeuzelijst **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![Afbeelding van het lint](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="7c10d-130">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-130">Select **Add**.</span></span>
    
    ![Afbeelding van het lint](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="7c10d-132">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7c10d-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7c10d-133">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="7c10d-133">**Sub Domain**</span></span>|<span data-ttu-id="7c10d-134">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="7c10d-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7c10d-135">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="7c10d-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7c10d-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7c10d-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7c10d-137">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="7c10d-137">**Note:** This is an example.</span></span> <span data-ttu-id="7c10d-138">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="7c10d-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="7c10d-139">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="7c10d-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Afbeelding van het lint](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="7c10d-141">Selecteer **Bijwerken**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-141">Select **Update**.</span></span>
    
    ![Afbeelding van het lint](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="7c10d-143">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="7c10d-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7c10d-144">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="7c10d-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="7c10d-145">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="7c10d-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7c10d-146">Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="7c10d-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7c10d-147">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="7c10d-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7c10d-148">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7c10d-149">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7c10d-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7c10d-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7c10d-153">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="7c10d-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7c10d-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7c10d-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7c10d-p107">Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7c10d-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="7c10d-158">Selecteer **Domeinen**in de sectie **Mijn account** .</span><span class="sxs-lookup"><span data-stu-id="7c10d-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="7c10d-160">Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="7c10d-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="7c10d-162">Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram.</span><span class="sxs-lookup"><span data-stu-id="7c10d-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="7c10d-164">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-164">Select **Add Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="7c10d-166">Kies **TXT Record** uit de vervolgkeuzelijst **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Afbeelding van het lint](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="7c10d-168">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-168">Select **Add**.</span></span>
    
    ![Afbeelding van het lint](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="7c10d-170">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7c10d-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="7c10d-171">(Kies de **waarde Prioriteit** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="7c10d-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7c10d-172">**Mail For Zone**</span><span class="sxs-lookup"><span data-stu-id="7c10d-172">**Mail For Zone**</span></span>|<span data-ttu-id="7c10d-173">**Priority**</span><span class="sxs-lookup"><span data-stu-id="7c10d-173">**Priority**</span></span>|<span data-ttu-id="7c10d-174">**Assigned To Server**</span><span class="sxs-lookup"><span data-stu-id="7c10d-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="7c10d-175">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="7c10d-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7c10d-176">1</span><span class="sxs-lookup"><span data-stu-id="7c10d-176">1</span></span>  <br/> <span data-ttu-id="7c10d-177">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="7c10d-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="7c10d-178">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7c10d-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="7c10d-179">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="7c10d-179">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="7c10d-180">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="7c10d-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Afbeelding van het lint](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="7c10d-182">Selecteer **Bijwerken**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-182">Select **Update**.</span></span>
    
    ![Afbeelding van het lint](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="7c10d-184">Als er andere MX-records worden vermeld in de sectie **MX Record,** selecteert **u Wijzigen** voor een van deze records.</span><span class="sxs-lookup"><span data-stu-id="7c10d-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![Afbeelding van het lint](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="7c10d-186">Selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-186">Select **Delete**.</span></span>
    
    ![Afbeelding van het lint](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="7c10d-188">Selecteer **Bijwerken** om de verwijdering te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="7c10d-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![Afbeelding van het lint](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="7c10d-190">Verwijder op dezelfde manier alle andere MX-records in de lijst, met uitzondering van de MX-record die u eerder met deze procedure hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="7c10d-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7c10d-191">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c10d-191">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="7c10d-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7c10d-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="7c10d-p109">Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7c10d-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="7c10d-196">Selecteer **Domeinen**in de sectie **Mijn account** .</span><span class="sxs-lookup"><span data-stu-id="7c10d-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="7c10d-198">Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="7c10d-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="7c10d-200">Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram.</span><span class="sxs-lookup"><span data-stu-id="7c10d-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="7c10d-202">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-202">Select **Add Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="7c10d-204">Kies **CNAME Record** uit de vervolgkeuzelijst **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Afbeelding van het lint](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="7c10d-206">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-206">Select **Add**.</span></span>
    
    ![Afbeelding van het lint](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="7c10d-208">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="7c10d-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="7c10d-209">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7c10d-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="7c10d-210">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="7c10d-210">**Sub Domain**</span></span>|<span data-ttu-id="7c10d-211">**Alias for**</span><span class="sxs-lookup"><span data-stu-id="7c10d-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7c10d-212">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7c10d-212">autodiscover</span></span>  <br/> |<span data-ttu-id="7c10d-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7c10d-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="7c10d-214">sip</span><span class="sxs-lookup"><span data-stu-id="7c10d-214">sip</span></span>  <br/> |<span data-ttu-id="7c10d-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7c10d-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7c10d-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7c10d-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7c10d-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7c10d-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7c10d-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7c10d-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7c10d-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="7c10d-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="7c10d-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7c10d-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7c10d-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7c10d-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Afbeelding van het lint](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="7c10d-223">Selecteer **CNAME-record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-223">Select **Add CNAME Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="7c10d-225">Voeg de tweede CNAME-record toe:</span><span class="sxs-lookup"><span data-stu-id="7c10d-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="7c10d-226">Gebruik in de vakken voor de nieuwe record de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **CNAME Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="7c10d-227">Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7c10d-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="7c10d-228">Selecteer **Bijwerken** om uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="7c10d-228">Select **Update** to save your changes.</span></span> 
    
    ![Afbeelding van het lint](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7c10d-230">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="7c10d-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7c10d-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7c10d-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c10d-232">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="7c10d-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7c10d-233">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="7c10d-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7c10d-234">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7c10d-234">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7c10d-235">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="7c10d-235">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="7c10d-p111">Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7c10d-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="7c10d-239">Selecteer **Domeinen**in de sectie **Mijn account** .</span><span class="sxs-lookup"><span data-stu-id="7c10d-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="7c10d-241">Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="7c10d-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="7c10d-243">Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram.</span><span class="sxs-lookup"><span data-stu-id="7c10d-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="7c10d-245">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-245">Select **Add Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="7c10d-247">Kies **TXT Record** uit de vervolgkeuzelijst **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Afbeelding van het lint](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="7c10d-249">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-249">Select **Add**.</span></span>
    
    ![Afbeelding van het lint](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="7c10d-251">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7c10d-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7c10d-252">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="7c10d-252">**Sub Domain**</span></span>|<span data-ttu-id="7c10d-253">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="7c10d-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7c10d-254">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="7c10d-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7c10d-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7c10d-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7c10d-256">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="7c10d-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Afbeelding van het lint](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="7c10d-258">Selecteer **Bijwerken**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-258">Select **Update**.</span></span>
    
    ![Afbeelding van het lint](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7c10d-260">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c10d-260">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7c10d-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7c10d-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="7c10d-p112">Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7c10d-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="7c10d-265">Selecteer **Domeinen**in de sectie **Mijn account** .</span><span class="sxs-lookup"><span data-stu-id="7c10d-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="7c10d-267">Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="7c10d-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="7c10d-269">Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram.</span><span class="sxs-lookup"><span data-stu-id="7c10d-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="7c10d-271">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-271">Select **Add Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="7c10d-273">Kies **SRV Record** uit de vervolgkeuzelijst **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Afbeelding van het lint](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="7c10d-275">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-275">Select **Add**.</span></span>
    
    ![Afbeelding van het lint](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="7c10d-277">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="7c10d-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="7c10d-278">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7c10d-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="7c10d-279">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="7c10d-279">**Record Type**</span></span>|<span data-ttu-id="7c10d-280">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="7c10d-280">**Sub Domain**</span></span>|<span data-ttu-id="7c10d-281">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="7c10d-281">**Priority**</span></span>|<span data-ttu-id="7c10d-282">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="7c10d-282">**Weight**</span></span>|<span data-ttu-id="7c10d-283">**Poort**</span><span class="sxs-lookup"><span data-stu-id="7c10d-283">**Port**</span></span>|<span data-ttu-id="7c10d-284">**Target**</span><span class="sxs-lookup"><span data-stu-id="7c10d-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7c10d-285">SRV Record</span><span class="sxs-lookup"><span data-stu-id="7c10d-285">SRV Record</span></span>  <br/> |<span data-ttu-id="7c10d-286">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="7c10d-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="7c10d-287">100</span><span class="sxs-lookup"><span data-stu-id="7c10d-287">100</span></span>  <br/> |<span data-ttu-id="7c10d-288">1</span><span class="sxs-lookup"><span data-stu-id="7c10d-288">1</span></span>  <br/> |<span data-ttu-id="7c10d-289">443</span><span class="sxs-lookup"><span data-stu-id="7c10d-289">443</span></span>  <br/> |<span data-ttu-id="7c10d-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7c10d-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7c10d-291">SRV Record</span><span class="sxs-lookup"><span data-stu-id="7c10d-291">SRV Record</span></span>  <br/> |<span data-ttu-id="7c10d-292">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="7c10d-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="7c10d-293">100</span><span class="sxs-lookup"><span data-stu-id="7c10d-293">100</span></span>  <br/> |<span data-ttu-id="7c10d-294">1</span><span class="sxs-lookup"><span data-stu-id="7c10d-294">1</span></span>  <br/> |<span data-ttu-id="7c10d-295">5061</span><span class="sxs-lookup"><span data-stu-id="7c10d-295">5061</span></span>  <br/> |<span data-ttu-id="7c10d-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7c10d-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Afbeelding van het lint](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="7c10d-298">Selecteer **SRV-record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7c10d-298">Select **Add SRV Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="7c10d-300">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="7c10d-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="7c10d-301">Voeg in de vakken voor de nieuwe record de waarden uit de tweede rij in de tabel toe.</span><span class="sxs-lookup"><span data-stu-id="7c10d-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="7c10d-302">Selecteer **Bijwerken** om uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="7c10d-302">Select **Update** to save your changes.</span></span> 
    
    ![Afbeelding van het lint](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="7c10d-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7c10d-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
