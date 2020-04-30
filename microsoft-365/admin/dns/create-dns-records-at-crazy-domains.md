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
ms.openlocfilehash: 5a5a0f4c92e14bdfd6c54249cd66c9e88abee075
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939329"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="8d0fc-103">DNS-records maken bij Crazy Domains voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d0fc-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="8d0fc-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8d0fc-105">Als Crazy Domains uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8d0fc-106">Nadat u deze records hebt toegevoegd bij Crazy Domains, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="8d0fc-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8d0fc-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8d0fc-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="8d0fc-110">Add a TXT record for verification</span></span>
<span data-ttu-id="8d0fc-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0fc-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8d0fc-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d0fc-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8d0fc-p104">Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="8d0fc-119">Selecteer **Domeinen**in de sectie **Mijn account** .</span><span class="sxs-lookup"><span data-stu-id="8d0fc-119">In the **My Account** section, select **Domains**.</span></span>
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="8d0fc-121">Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-121">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="8d0fc-123">Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-123">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="8d0fc-125">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-125">Select **Add Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="8d0fc-127">Kies **TXT Record** in de vervolgkeuzelijst **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-127">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![Afbeelding van het lint](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="8d0fc-129">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-129">Select **Add**.</span></span>
    
    ![Afbeelding van het lint](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="8d0fc-131">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8d0fc-132">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-132">**Sub Domain**</span></span>|<span data-ttu-id="8d0fc-133">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-133">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8d0fc-134">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="8d0fc-134">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8d0fc-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8d0fc-135">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8d0fc-136">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-136">**Note:** This is an example.</span></span> <span data-ttu-id="8d0fc-137">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-137">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="8d0fc-138">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="8d0fc-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Afbeelding van het lint](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="8d0fc-140">Selecteer **Bijwerken**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-140">Select **Update**.</span></span>
    
    ![Afbeelding van het lint](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="8d0fc-142">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8d0fc-143">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8d0fc-144">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8d0fc-145">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8d0fc-146">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8d0fc-147">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-147">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8d0fc-148">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-148">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8d0fc-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8d0fc-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8d0fc-152">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="8d0fc-152">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8d0fc-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0fc-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="8d0fc-p107">Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="8d0fc-157">Selecteer **Domeinen**in de sectie **Mijn account** .</span><span class="sxs-lookup"><span data-stu-id="8d0fc-157">In the **My Account** section, select **Domains**.</span></span>
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="8d0fc-159">Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-159">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="8d0fc-161">Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-161">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="8d0fc-163">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-163">Select **Add Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="8d0fc-165">Kies **TXT Record** uit de vervolgkeuzelijst **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-165">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Afbeelding van het lint](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="8d0fc-167">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-167">Select **Add**.</span></span>
    
    ![Afbeelding van het lint](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="8d0fc-169">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-169">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="8d0fc-170">(Kies de **waarde Prioriteit** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="8d0fc-170">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8d0fc-171">**Mail For Zone**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-171">**Mail For Zone**</span></span>|<span data-ttu-id="8d0fc-172">**Priority**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-172">**Priority**</span></span>|<span data-ttu-id="8d0fc-173">**Assigned To Server**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-173">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8d0fc-174">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="8d0fc-174">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8d0fc-175">1</span><span class="sxs-lookup"><span data-stu-id="8d0fc-175">1</span></span>  <br/> <span data-ttu-id="8d0fc-176">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-176">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="8d0fc-177">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8d0fc-177">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="8d0fc-178">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-178">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="8d0fc-179">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="8d0fc-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Afbeelding van het lint](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="8d0fc-181">Selecteer **Bijwerken**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-181">Select **Update**.</span></span>
    
    ![Afbeelding van het lint](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="8d0fc-183">Als er andere MX-records worden vermeld in de sectie **MX Record,** selecteert **u Wijzigen** voor een van deze records.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-183">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![Afbeelding van het lint](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="8d0fc-185">Selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-185">Select **Delete**.</span></span>
    
    ![Afbeelding van het lint](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="8d0fc-187">Selecteer **Bijwerken** om de verwijdering te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-187">Select **Update** to confirm the deletion.</span></span> 
    
    ![Afbeelding van het lint](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="8d0fc-189">Verwijder op dezelfde manier alle andere MX-records in de lijst, met uitzondering van de MX-record die u eerder met deze procedure hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-189">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8d0fc-190">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d0fc-190">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8d0fc-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0fc-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="8d0fc-p109">Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="8d0fc-195">Selecteer **Domeinen**in de sectie **Mijn account** .</span><span class="sxs-lookup"><span data-stu-id="8d0fc-195">In the **My Account** section, select **Domains**.</span></span>
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="8d0fc-197">Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-197">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="8d0fc-199">Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-199">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="8d0fc-201">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-201">Select **Add Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="8d0fc-203">Kies **CNAME Record** uit de vervolgkeuzelijst **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Afbeelding van het lint](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="8d0fc-205">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-205">Select **Add**.</span></span>
    
    ![Afbeelding van het lint](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="8d0fc-207">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-207">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="8d0fc-208">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-208">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="8d0fc-209">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-209">**Sub Domain**</span></span>|<span data-ttu-id="8d0fc-210">**Alias for**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-210">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8d0fc-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8d0fc-211">autodiscover</span></span>  <br/> |<span data-ttu-id="8d0fc-212">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8d0fc-212">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="8d0fc-213">sip</span><span class="sxs-lookup"><span data-stu-id="8d0fc-213">sip</span></span>  <br/> |<span data-ttu-id="8d0fc-214">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d0fc-214">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8d0fc-215">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8d0fc-215">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8d0fc-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d0fc-216">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8d0fc-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8d0fc-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8d0fc-218">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8d0fc-218">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="8d0fc-219">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8d0fc-219">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8d0fc-220">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8d0fc-220">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Afbeelding van het lint](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="8d0fc-222">Selecteer **CNAME-record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-222">Select **Add CNAME Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="8d0fc-224">Voeg de tweede CNAME-record toe:</span><span class="sxs-lookup"><span data-stu-id="8d0fc-224">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="8d0fc-225">Gebruik in de vakken voor de nieuwe record de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **CNAME Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-225">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="8d0fc-226">Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-226">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="8d0fc-227">Selecteer **Bijwerken** om uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-227">Select **Update** to save your changes.</span></span> 
    
    ![Afbeelding van het lint](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8d0fc-229">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="8d0fc-229">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8d0fc-230"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0fc-230"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d0fc-231">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-231">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8d0fc-232">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-232">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8d0fc-233">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-233">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8d0fc-234">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-234">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="8d0fc-p111">Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="8d0fc-238">Selecteer **Domeinen**in de sectie **Mijn account** .</span><span class="sxs-lookup"><span data-stu-id="8d0fc-238">In the **My Account** section, select **Domains**.</span></span>
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="8d0fc-240">Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-240">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="8d0fc-242">Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-242">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="8d0fc-244">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-244">Select **Add Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="8d0fc-246">Kies **TXT Record** uit de vervolgkeuzelijst **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-246">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Afbeelding van het lint](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="8d0fc-248">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-248">Select **Add**.</span></span>
    
    ![Afbeelding van het lint](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="8d0fc-250">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-250">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8d0fc-251">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-251">**Sub Domain**</span></span>|<span data-ttu-id="8d0fc-252">**Text Record**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-252">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8d0fc-253">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="8d0fc-253">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8d0fc-254">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8d0fc-254">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8d0fc-255">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-255">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Afbeelding van het lint](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="8d0fc-257">Selecteer **Bijwerken**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-257">Select **Update**.</span></span>
    
    ![Afbeelding van het lint](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8d0fc-259">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d0fc-259">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8d0fc-260"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8d0fc-260"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="8d0fc-p112">Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="8d0fc-264">Selecteer **Domeinen**in de sectie **Mijn account** .</span><span class="sxs-lookup"><span data-stu-id="8d0fc-264">In the **My Account** section, select **Domains**.</span></span>
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="8d0fc-266">Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-266">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="8d0fc-268">Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-268">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="8d0fc-270">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-270">Select **Add Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="8d0fc-272">Kies **SRV Record** uit de vervolgkeuzelijst **Add Record**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-272">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![Afbeelding van het lint](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="8d0fc-274">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-274">Select **Add**.</span></span>
    
    ![Afbeelding van het lint](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="8d0fc-276">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-276">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="8d0fc-277">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-277">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="8d0fc-278">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-278">**Record Type**</span></span>|<span data-ttu-id="8d0fc-279">**Sub Domain**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-279">**Sub Domain**</span></span>|<span data-ttu-id="8d0fc-280">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-280">**Priority**</span></span>|<span data-ttu-id="8d0fc-281">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-281">**Weight**</span></span>|<span data-ttu-id="8d0fc-282">**Poort**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-282">**Port**</span></span>|<span data-ttu-id="8d0fc-283">**Target**</span><span class="sxs-lookup"><span data-stu-id="8d0fc-283">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8d0fc-284">SRV Record</span><span class="sxs-lookup"><span data-stu-id="8d0fc-284">SRV Record</span></span>  <br/> |<span data-ttu-id="8d0fc-285">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="8d0fc-285">_sip._tls</span></span>  <br/> |<span data-ttu-id="8d0fc-286">100</span><span class="sxs-lookup"><span data-stu-id="8d0fc-286">100</span></span>  <br/> |<span data-ttu-id="8d0fc-287">1</span><span class="sxs-lookup"><span data-stu-id="8d0fc-287">1</span></span>  <br/> |<span data-ttu-id="8d0fc-288">443</span><span class="sxs-lookup"><span data-stu-id="8d0fc-288">443</span></span>  <br/> |<span data-ttu-id="8d0fc-289">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d0fc-289">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8d0fc-290">SRV Record</span><span class="sxs-lookup"><span data-stu-id="8d0fc-290">SRV Record</span></span>  <br/> |<span data-ttu-id="8d0fc-291">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="8d0fc-291">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="8d0fc-292">100</span><span class="sxs-lookup"><span data-stu-id="8d0fc-292">100</span></span>  <br/> |<span data-ttu-id="8d0fc-293">1</span><span class="sxs-lookup"><span data-stu-id="8d0fc-293">1</span></span>  <br/> |<span data-ttu-id="8d0fc-294">5061</span><span class="sxs-lookup"><span data-stu-id="8d0fc-294">5061</span></span>  <br/> |<span data-ttu-id="8d0fc-295">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d0fc-295">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Afbeelding van het lint](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="8d0fc-297">Selecteer **SRV-record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-297">Select **Add SRV Record**.</span></span>
    
    ![Afbeelding van het lint](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="8d0fc-299">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-299">Add the other SRV record.</span></span>
    
    <span data-ttu-id="8d0fc-300">Voeg in de vakken voor de nieuwe record de waarden uit de tweede rij in de tabel toe.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-300">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="8d0fc-301">Selecteer **Bijwerken** om uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="8d0fc-301">Select **Update** to save your changes.</span></span> 
    
    ![Afbeelding van het lint](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="8d0fc-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8d0fc-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
