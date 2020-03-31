---
title: DNS-records maken op MyDomain voor Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Lees hier hoe u uw domein en DNS-records voor e-mail, Skype voor Bedrijven Online en andere service kunt instellen via Mijn domein voor Office 365.
ms.openlocfilehash: c85c04d369add95d3aaa815229257fe90a24fb28
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42805373"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a><span data-ttu-id="fd04a-103">DNS-records maken op MyDomain voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fd04a-103">Create DNS records at MyDomain for Office 365</span></span>


  
 <span data-ttu-id="fd04a-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="fd04a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="fd04a-p101">De website MyDomain ondersteunt geen SRV-records. Dat betekent dat een aantal functies in Skype voor Bedrijven Online en Outlook Web App niet werkt. Als u uw DNS-records beheert via MyDomain, dan gelden er, ongeacht uw Office 365-abonnement, [aanzienlijke servicebeperkingen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx). U kunt overwegen over te schakelen naar een andere DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="fd04a-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="fd04a-107">Als u ondanks deze beperkingen uw eigen DNS-records voor Office 365 via MyDomain wilt beheren, volgt u de stappen in dit artikel om uw DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="fd04a-107">If you choose to manage your own Office 365 DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="fd04a-108">Nadat u deze records op MyDomain hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="fd04a-108">After you add these records at MyDomain, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="fd04a-109">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="fd04a-109">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd04a-p102">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fd04a-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fd04a-113">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="fd04a-113">Add a TXT record for verification</span></span>
<span data-ttu-id="fd04a-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="fd04a-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="fd04a-p103">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="fd04a-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd04a-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fd04a-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="fd04a-119">Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="fd04a-119">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="fd04a-120">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fd04a-120">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="fd04a-121">Kies in de sectie **Mijn favorieten** de optie **Domain Central**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="fd04a-122">Kies onder **Domein** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fd04a-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="fd04a-123">Kies in de rij **Overzicht** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="fd04a-124">Kies in de vervolgkeuzelijst **Wijzigen** de optie **TXT/SPF-record**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="fd04a-125">Typ of kopieer en plak de waarden uit de volgende tabel in het vak voor de nieuwe record onder **Content**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="fd04a-126">**Content**</span><span class="sxs-lookup"><span data-stu-id="fd04a-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="fd04a-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fd04a-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fd04a-128">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="fd04a-128">**Note:** This is an example.</span></span> <span data-ttu-id="fd04a-129">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fd04a-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="fd04a-130">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="fd04a-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="fd04a-131">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="fd04a-132">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="fd04a-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fd04a-133">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="fd04a-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="fd04a-134">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="fd04a-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fd04a-135">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="fd04a-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="fd04a-136">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="fd04a-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="fd04a-137">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="fd04a-138">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fd04a-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fd04a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="fd04a-142">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="fd04a-142">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="fd04a-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="fd04a-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="fd04a-p108">Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fd04a-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="fd04a-146">Kies in de sectie **Mijn favorieten** de optie **Domain Central**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="fd04a-147">Kies onder **Domein** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fd04a-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="fd04a-148">Kies in de rij **Overzicht** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="fd04a-149">Kies in de vervolgkeuzelijst **Modify** de optie **MX Record**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="fd04a-151">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="fd04a-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="fd04a-152">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="fd04a-152">**Priority**</span></span>|<span data-ttu-id="fd04a-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="fd04a-153">**Host**</span></span>|<span data-ttu-id="fd04a-154">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="fd04a-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fd04a-155">0</span><span class="sxs-lookup"><span data-stu-id="fd04a-155">0</span></span>  <br/> <span data-ttu-id="fd04a-156">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="fd04a-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="fd04a-157">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fd04a-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="fd04a-158">**Opmerking**: Uw \<*domeinsleutel*\> kunt u ophalen uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="fd04a-158">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span><span data-ttu-id="fd04a-159"> > [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="fd04a-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="fd04a-161">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="fd04a-163">Als er andere MX-records aanwezig zijn, selecteert u **Remove** in de kolom **Action** voor elke te verwijderen record.</span><span class="sxs-lookup"><span data-stu-id="fd04a-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="fd04a-165">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="fd04a-167">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="fd04a-167">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="fd04a-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="fd04a-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="fd04a-p110">Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fd04a-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="fd04a-171">Kies in de sectie **Mijn favorieten** de optie **Domain Central**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="fd04a-172">Kies onder **Domein** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fd04a-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="fd04a-173">Kies in de rij **Overzicht** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="fd04a-174">Kies in de vervolgkeuzelijst **Modify** de optie **CNAME Alias**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="fd04a-176">Voeg de eerste CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="fd04a-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="fd04a-177">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="fd04a-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="fd04a-178">**Host**</span><span class="sxs-lookup"><span data-stu-id="fd04a-178">**Host**</span></span>|<span data-ttu-id="fd04a-179">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="fd04a-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="fd04a-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="fd04a-180">autodiscover</span></span>  <br/> |<span data-ttu-id="fd04a-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fd04a-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="fd04a-182">sip</span><span class="sxs-lookup"><span data-stu-id="fd04a-182">sip</span></span>  <br/> |<span data-ttu-id="fd04a-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fd04a-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fd04a-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fd04a-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="fd04a-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fd04a-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fd04a-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="fd04a-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="fd04a-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="fd04a-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="fd04a-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="fd04a-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="fd04a-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fd04a-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="fd04a-191">Kies **Toevoegen** om een eerste record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="fd04a-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="fd04a-193">Voeg de tweede CNAME-record toe:</span><span class="sxs-lookup"><span data-stu-id="fd04a-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="fd04a-194">Gebruik de waarden uit de tweede rij van de bovenstaande tabel en kies vervolgens **Toevoegen** om de tweede record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="fd04a-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="fd04a-195">Voeg de resterende records op dezelfde manier toe met behulp van de waarden uit de derde, vierde, vijfde en zesde rij van de tabel.</span><span class="sxs-lookup"><span data-stu-id="fd04a-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="fd04a-196">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="fd04a-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="fd04a-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="fd04a-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd04a-198">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="fd04a-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="fd04a-199">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="fd04a-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="fd04a-200">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="fd04a-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="fd04a-201">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over één SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="fd04a-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="fd04a-202">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="fd04a-202">Need examples?</span></span> <span data-ttu-id="fd04a-203">Bekijk deze [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="fd04a-203">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="fd04a-204">Voor het valideren van uw SPF-record, kunt u een van deze [SPF-validatiehulpmiddelen](../setup/domains-faq.md) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fd04a-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="fd04a-205">Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="fd04a-205">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="fd04a-206">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fd04a-206">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="fd04a-207">Kies in de sectie **Mijn favorieten** de optie **Domain Central**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="fd04a-208">Kies onder **Domein** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fd04a-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="fd04a-209">Kies in de rij **Overzicht** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="fd04a-210">Kies in de vervolgkeuzelijst **Modify** de optie **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="fd04a-212">Typ of kopieer en plak de waarden uit de volgende tabel in het vak voor de nieuwe record onder **Content**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="fd04a-213">**Content**</span><span class="sxs-lookup"><span data-stu-id="fd04a-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="fd04a-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="fd04a-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="fd04a-215">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="fd04a-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="fd04a-217">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="fd04a-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="fd04a-219">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="fd04a-219">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="fd04a-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="fd04a-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="fd04a-p113">De website MyDomain ondersteunt geen SRV-records. Dat betekent dat een aantal functies in Skype voor Bedrijven Online en Outlook Web App niet werkt. Als u uw DNS-records beheert via MyDomain, dan gelden er, ongeacht uw Office 365-abonnement, [aanzienlijke servicebeperkingen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx). U kunt overwegen over te schakelen naar een andere DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="fd04a-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fd04a-p114">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fd04a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
