---
title: DNS-records maken op MyDomain voor Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Lees hier hoe u uw domein en DNS-records voor e-mail, Skype voor Bedrijven Online en andere service kunt instellen via Mijn domein voor Microsoft.
ms.openlocfilehash: 13660b4f3fd899d4d055a2c18aaff90cb3ba19c3
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645957"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="d4e02-103">DNS-records maken op MyDomain voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4e02-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="d4e02-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="d4e02-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="d4e02-p101">De website MyDomain ondersteunt geen SRV-records. Dit betekent dat een aantal functies in Skype voor Bedrijven Online en Outlook Web App niet werkt. Als u uw DNS-records beheert via MyDomain, dan gelden er, ongeacht uw Microsoft-abonnement, [aanzienlijke servicebeperkingen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). U kunt overwegen over te schakelen naar een andere DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="d4e02-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="d4e02-107">Als u ondanks deze beperkingen uw eigen DNS-records voor Microsoft via MyDomain wilt beheren, volgt u de stappen in dit artikel om uw DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="d4e02-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="d4e02-108">Nadat u deze records op MyDomain hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="d4e02-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="d4e02-p102">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d4e02-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d4e02-112">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="d4e02-112">Add a TXT record for verification</span></span>
<span data-ttu-id="d4e02-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d4e02-113"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d4e02-p103">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="d4e02-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4e02-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d4e02-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d4e02-p105">Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="d4e02-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d4e02-120">Kies in de sectie **Mijn favorieten** de optie **Domain Central**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-120">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="d4e02-121">Kies onder **Domein** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="d4e02-121">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="d4e02-122">Kies in de rij **Overzicht** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-122">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="d4e02-123">Kies in de vervolgkeuzelijst **Wijzigen** de optie **TXT/SPF-record**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-123">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="d4e02-124">Typ of kopieer en plak de waarden uit de volgende tabel in het vak voor de nieuwe record onder **Content**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-124">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="d4e02-125">**Content**</span><span class="sxs-lookup"><span data-stu-id="d4e02-125">**Content**</span></span> <br/> |
    |<span data-ttu-id="d4e02-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d4e02-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d4e02-127">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d4e02-127">**Note:** This is an example.</span></span> <span data-ttu-id="d4e02-128">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="d4e02-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="d4e02-129">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="d4e02-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="d4e02-130">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-130">Select **Add**.</span></span>
    
8. <span data-ttu-id="d4e02-131">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="d4e02-131">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d4e02-132">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="d4e02-132">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d4e02-133">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="d4e02-133">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d4e02-134">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="d4e02-134">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d4e02-135">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="d4e02-135">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d4e02-136">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-136">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d4e02-137">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-137">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d4e02-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d4e02-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d4e02-141">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="d4e02-141">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d4e02-142"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d4e02-142"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d4e02-p108">Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="d4e02-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d4e02-145">Kies in de sectie **Mijn favorieten** de optie **Domain Central**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-145">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="d4e02-146">Kies onder **Domein** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="d4e02-146">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="d4e02-147">Kies in de rij **Overzicht** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-147">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="d4e02-148">Kies in de vervolgkeuzelijst **Modify** de optie **MX Record**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-148">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="d4e02-150">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="d4e02-150">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="d4e02-151">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="d4e02-151">**Priority**</span></span>|<span data-ttu-id="d4e02-152">**Host**</span><span class="sxs-lookup"><span data-stu-id="d4e02-152">**Host**</span></span>|<span data-ttu-id="d4e02-153">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="d4e02-153">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d4e02-154">0</span><span class="sxs-lookup"><span data-stu-id="d4e02-154">0</span></span>  <br/> <span data-ttu-id="d4e02-155">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="d4e02-155">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |@  <br/> | <span data-ttu-id="d4e02-156">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d4e02-156">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d4e02-157">**Opmerking:** Haal uw \<*domain-key*\> uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="d4e02-157">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="d4e02-158"> > [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="d4e02-158"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="d4e02-160">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-160">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="d4e02-162">Als er andere MX-records aanwezig zijn, selecteert u **Remove** in de kolom **Action** voor elke te verwijderen record.</span><span class="sxs-lookup"><span data-stu-id="d4e02-162">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="d4e02-164">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-164">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d4e02-166">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4e02-166">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d4e02-167"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d4e02-167"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d4e02-p110">Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="d4e02-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d4e02-170">Kies in de sectie **Mijn favorieten** de optie **Domain Central**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-170">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="d4e02-171">Kies onder **Domein** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="d4e02-171">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="d4e02-172">Kies in de rij **Overzicht** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-172">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="d4e02-173">Kies in de vervolgkeuzelijst **Modify** de optie **CNAME Alias**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-173">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="d4e02-175">Voeg de eerste CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="d4e02-175">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="d4e02-176">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="d4e02-176">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="d4e02-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="d4e02-177">**Host**</span></span>|<span data-ttu-id="d4e02-178">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="d4e02-178">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d4e02-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d4e02-179">autodiscover</span></span>  <br/> |<span data-ttu-id="d4e02-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d4e02-180">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d4e02-181">sip</span><span class="sxs-lookup"><span data-stu-id="d4e02-181">sip</span></span>  <br/> |<span data-ttu-id="d4e02-182">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d4e02-182">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d4e02-183">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d4e02-183">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d4e02-184">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d4e02-184">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d4e02-185">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d4e02-185">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d4e02-186">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d4e02-186">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d4e02-187">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d4e02-187">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d4e02-188">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d4e02-188">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="d4e02-190">Kies **Toevoegen** om een eerste record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="d4e02-190">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="d4e02-192">Voeg de tweede CNAME-record toe:</span><span class="sxs-lookup"><span data-stu-id="d4e02-192">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="d4e02-193">Gebruik de waarden uit de tweede rij van de bovenstaande tabel en kies vervolgens **Toevoegen** om de tweede record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="d4e02-193">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="d4e02-194">Voeg de resterende records op dezelfde manier toe met behulp van de waarden uit de derde, vierde, vijfde en zesde rij van de tabel.</span><span class="sxs-lookup"><span data-stu-id="d4e02-194">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d4e02-195">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="d4e02-195">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d4e02-196"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d4e02-196"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4e02-197">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="d4e02-197">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d4e02-198">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="d4e02-198">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d4e02-199">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4e02-199">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d4e02-200">In plaats hiervan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u beschikt over één SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="d4e02-200">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="d4e02-201">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="d4e02-201">Need examples?</span></span> <span data-ttu-id="d4e02-202">Bekijk deze [Externe Domain Name System-records voor Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="d4e02-202">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="d4e02-203">Voor het valideren van uw SPF-record, kunt u een van deze [SPF-validatiehulpmiddelen](../setup/domains-faq.md) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d4e02-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="d4e02-p112">Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="d4e02-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d4e02-206">Kies in de sectie **Mijn favorieten** de optie **Domain Central**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-206">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="d4e02-207">Kies onder **Domein** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="d4e02-207">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="d4e02-208">Kies in de rij **Overzicht** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-208">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="d4e02-209">Kies in de vervolgkeuzelijst **Modify** de optie **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-209">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="d4e02-211">Typ of kopieer en plak de waarden uit de volgende tabel in het vak voor de nieuwe record onder **Content**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-211">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="d4e02-212">**Content**</span><span class="sxs-lookup"><span data-stu-id="d4e02-212">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="d4e02-213">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d4e02-213">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d4e02-214">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="d4e02-214">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="d4e02-216">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d4e02-216">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d4e02-218">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="d4e02-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d4e02-219"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d4e02-219"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="d4e02-p113">De website MyDomain ondersteunt geen SRV-records. Dit betekent dat een aantal functies in Skype voor Bedrijven Online en Outlook Web App niet werkt. Als u uw DNS-records beheert via MyDomain, dan gelden er, ongeacht uw Microsoft-abonnement, [aanzienlijke servicebeperkingen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). U kunt overwegen over te schakelen naar een andere DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="d4e02-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d4e02-p114">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d4e02-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
