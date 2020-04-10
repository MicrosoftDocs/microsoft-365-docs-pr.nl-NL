---
title: DNS-records bij Namecheap maken voor Office 365
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Namecheap voor Office 365.
ms.openlocfilehash: 29b1130b75af592594e2a963dbb6fa8d3f08ab30
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211677"
---
# <a name="create-dns-records-at-namecheap-for-office-365"></a><span data-ttu-id="f9752-103">DNS-records bij Namecheap maken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f9752-103">Create DNS records at Namecheap for Office 365</span></span>

 <span data-ttu-id="f9752-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="f9752-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f9752-105">Als Namecheap uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="f9752-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f9752-106">Nadat u deze records bij Namecheap hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="f9752-106">After you add these records at Namecheap, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9752-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f9752-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f9752-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="f9752-110">Add a TXT record for verification</span></span>
<span data-ttu-id="f9752-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f9752-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f9752-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="f9752-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9752-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f9752-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="f9752-116">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="f9752-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="f9752-p104">Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden en verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="f9752-p104">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="f9752-120">Kies op de **bestemmingspagina** onder **Account**de optie **Lijst met domeinen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="f9752-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="f9752-122">Zoek op de pagina **Domeinlijst** de naam van het domein dat u wilt bewerken en selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="f9752-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="f9752-124">Selecteer **Geavanceerde DNS**.</span><span class="sxs-lookup"><span data-stu-id="f9752-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="f9752-126">Selecteer IN de sectie **HOST RECORDS** de optie NIEUWE **RECORD TOEVOEGEN**.</span><span class="sxs-lookup"><span data-stu-id="f9752-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="f9752-128">Selecteer in de vervolgkeuzelijst **Type** de optie **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="f9752-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9752-129">De vervolgkeuzelijst **Type** wordt automatisch weergegeven wanneer u **NIEUWE RECORD TOEVOEGEN selecteert.**</span><span class="sxs-lookup"><span data-stu-id="f9752-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="f9752-131">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f9752-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="f9752-132">(Kies de **TTL-waarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="f9752-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f9752-133">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9752-133">**Type**</span></span>|<span data-ttu-id="f9752-134">**Host**</span><span class="sxs-lookup"><span data-stu-id="f9752-134">**Host**</span></span>|<span data-ttu-id="f9752-135">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="f9752-135">**Value**</span></span>|<span data-ttu-id="f9752-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f9752-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9752-137">TXT</span><span class="sxs-lookup"><span data-stu-id="f9752-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="f9752-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f9752-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="f9752-139">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="f9752-139">**Note:** This is an example.</span></span> <span data-ttu-id="f9752-140">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9752-140">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="f9752-141">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="f9752-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f9752-142">30 min</span><span class="sxs-lookup"><span data-stu-id="f9752-142">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="f9752-144">Selecteer het besturingselement **Wijzigingen opslaan** (vinkje).</span><span class="sxs-lookup"><span data-stu-id="f9752-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="f9752-146">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f9752-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f9752-147">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="f9752-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f9752-148">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="f9752-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f9752-149">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="f9752-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="f9752-150">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="f9752-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f9752-151">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="f9752-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f9752-152">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="f9752-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="f9752-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f9752-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f9752-156">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="f9752-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f9752-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f9752-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="f9752-158">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="f9752-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="f9752-p107">Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden en verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="f9752-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="f9752-162">Kies op de **bestemmingspagina** onder **Account**de optie **Lijst met domeinen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="f9752-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="f9752-164">Zoek op de pagina **Domeinlijst** de naam van het domein dat u wilt bewerken en selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="f9752-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="f9752-166">Selecteer **Geavanceerde DNS**.</span><span class="sxs-lookup"><span data-stu-id="f9752-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="f9752-168">In de sectie **MAIL SETTINGS** selecteert u **Custom MX** in de vervolgkeuzelijst **Email Forwarding**.</span><span class="sxs-lookup"><span data-stu-id="f9752-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="f9752-169">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f9752-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="f9752-171">Selecteer **Nieuwe record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f9752-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-Configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="f9752-173">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f9752-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="f9752-174">(Het vak **Priority** is het naamloze vak rechts van het vak **Value**.</span><span class="sxs-lookup"><span data-stu-id="f9752-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="f9752-175">Kies de **TTL-waarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="f9752-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f9752-176">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9752-176">**Type**</span></span>|<span data-ttu-id="f9752-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="f9752-177">**Host**</span></span>|<span data-ttu-id="f9752-178">**Value**</span><span class="sxs-lookup"><span data-stu-id="f9752-178">**Value**</span></span>|<span data-ttu-id="f9752-179">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f9752-179">**Priority**</span></span>|<span data-ttu-id="f9752-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f9752-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9752-181">MX Record</span><span class="sxs-lookup"><span data-stu-id="f9752-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="f9752-182">\<*domeinsleutel*\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f9752-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="f9752-183">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f9752-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="f9752-184">**Let op:** Haal uw \* \<domeinsleutel\> \* op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="f9752-184">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="f9752-185">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="f9752-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f9752-186">0</span><span class="sxs-lookup"><span data-stu-id="f9752-186">0</span></span>  <br/> <span data-ttu-id="f9752-187">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="f9752-187">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="f9752-188">30 min</span><span class="sxs-lookup"><span data-stu-id="f9752-188">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="f9752-190">Selecteer het besturingselement **Wijzigingen opslaan** (vinkje).</span><span class="sxs-lookup"><span data-stu-id="f9752-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="f9752-192">Als er andere MX-records zijn, verwijdert u deze met behulp van de volgende tweestapsprocedure:</span><span class="sxs-lookup"><span data-stu-id="f9752-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="f9752-193">Selecteer eerst het **pictogram Verwijderen** (prullenbak) voor de record die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f9752-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="f9752-195">Ten tweede selecteert u **Ja** om de verwijdering te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="f9752-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="f9752-197">Verwijder alle MX-records, behalve die welke u eerder in deze procedure hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="f9752-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f9752-198">De zes CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="f9752-198">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f9752-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f9752-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="f9752-200">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="f9752-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="f9752-p110">Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden en verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="f9752-p110">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="f9752-204">Kies op de **bestemmingspagina** onder **Account**de optie **Lijst met domeinen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="f9752-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="f9752-206">Zoek op de pagina **Domeinlijst** de naam van het domein dat u wilt bewerken en selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="f9752-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="f9752-208">Selecteer **Geavanceerde DNS**.</span><span class="sxs-lookup"><span data-stu-id="f9752-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="f9752-210">Selecteer IN de sectie **HOST RECORDS** de optie NIEUWE **RECORD TOEVOEGEN**.</span><span class="sxs-lookup"><span data-stu-id="f9752-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="f9752-212">Selecteer in de vervolgkeuzelijst **Type** de optie **CNAME Record**.</span><span class="sxs-lookup"><span data-stu-id="f9752-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9752-213">De vervolgkeuzelijst **Type** wordt automatisch weergegeven wanneer u **NIEUWE RECORD TOEVOEGEN selecteert.**</span><span class="sxs-lookup"><span data-stu-id="f9752-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="f9752-215">Selecteer in de lege vakken voor de nieuwe record de optie **CNAME** voor het **recordtype** en typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="f9752-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="f9752-216">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9752-216">**Type**</span></span>|<span data-ttu-id="f9752-217">**Host**</span><span class="sxs-lookup"><span data-stu-id="f9752-217">**Host**</span></span>|<span data-ttu-id="f9752-218">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="f9752-218">**Value**</span></span>|<span data-ttu-id="f9752-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f9752-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9752-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="f9752-220">CNAME</span></span>  <br/> |<span data-ttu-id="f9752-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f9752-221">autodiscover</span></span>  <br/> |<span data-ttu-id="f9752-222">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f9752-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="f9752-223">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f9752-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f9752-224">3600</span><span class="sxs-lookup"><span data-stu-id="f9752-224">3600</span></span>  <br/> |
    |<span data-ttu-id="f9752-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="f9752-225">CNAME</span></span>  <br/> |<span data-ttu-id="f9752-226">sip</span><span class="sxs-lookup"><span data-stu-id="f9752-226">sip</span></span>  <br/> |<span data-ttu-id="f9752-227">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f9752-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f9752-228">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f9752-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f9752-229">3600</span><span class="sxs-lookup"><span data-stu-id="f9752-229">3600</span></span>  <br/> |
    |<span data-ttu-id="f9752-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="f9752-230">CNAME</span></span>  <br/> |<span data-ttu-id="f9752-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f9752-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f9752-232">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f9752-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f9752-233">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f9752-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f9752-234">3600</span><span class="sxs-lookup"><span data-stu-id="f9752-234">3600</span></span>  <br/> |
    |<span data-ttu-id="f9752-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="f9752-235">CNAME</span></span>  <br/> |<span data-ttu-id="f9752-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f9752-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f9752-237">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="f9752-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="f9752-238">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f9752-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f9752-239">3600</span><span class="sxs-lookup"><span data-stu-id="f9752-239">3600</span></span>  <br/> |
    |<span data-ttu-id="f9752-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="f9752-240">CNAME</span></span>  <br/> |<span data-ttu-id="f9752-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f9752-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f9752-242">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f9752-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="f9752-243">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f9752-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f9752-244">3600</span><span class="sxs-lookup"><span data-stu-id="f9752-244">3600</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="f9752-246">Selecteer het besturingselement **Wijzigingen opslaan** (vinkje).</span><span class="sxs-lookup"><span data-stu-id="f9752-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="f9752-248">Voeg met de voorgaande vier stappen en de waarden van de andere vijf rijen in de tabel elk van de andere vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="f9752-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f9752-249">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="f9752-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f9752-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f9752-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9752-251">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="f9752-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f9752-252">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="f9752-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f9752-253">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="f9752-253">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f9752-254">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="f9752-254">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="f9752-255">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="f9752-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="f9752-p112">Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden en verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="f9752-p112">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="f9752-258">Kies op de **bestemmingspagina** onder **Account**de optie **Lijst met domeinen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="f9752-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="f9752-260">Zoek op de pagina **Domeinlijst** de naam van het domein dat u wilt bewerken en selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="f9752-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="f9752-262">Selecteer **Geavanceerde DNS**.</span><span class="sxs-lookup"><span data-stu-id="f9752-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="f9752-264">Selecteer IN de sectie **HOST RECORDS** de optie NIEUWE **RECORD TOEVOEGEN**.</span><span class="sxs-lookup"><span data-stu-id="f9752-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="f9752-266">Selecteer in de vervolgkeuzelijst **Type** de optie **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="f9752-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9752-267">De vervolgkeuzelijst **Type** wordt automatisch weergegeven wanneer u **NIEUWE RECORD TOEVOEGEN selecteert.**</span><span class="sxs-lookup"><span data-stu-id="f9752-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="f9752-269">Typ of kopieer en plak de volgende waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f9752-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="f9752-270">(Kies de **TTL-waarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="f9752-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f9752-271">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9752-271">**Type**</span></span>|<span data-ttu-id="f9752-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="f9752-272">**Host**</span></span>|<span data-ttu-id="f9752-273">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="f9752-273">**Value**</span></span>|<span data-ttu-id="f9752-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f9752-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9752-275">TXT</span><span class="sxs-lookup"><span data-stu-id="f9752-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="f9752-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f9752-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f9752-277">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="f9752-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="f9752-278">30 min</span><span class="sxs-lookup"><span data-stu-id="f9752-278">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="f9752-280">Selecteer het besturingselement **Wijzigingen opslaan** (vinkje).</span><span class="sxs-lookup"><span data-stu-id="f9752-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f9752-282">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="f9752-282">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f9752-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f9752-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="f9752-p113">Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="f9752-p113">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="f9752-287">Kies op de **bestemmingspagina** onder **Account**de optie **Lijst met domeinen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="f9752-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="f9752-289">Zoek op de pagina **Domeinlijst** de naam van het domein dat u wilt bewerken en selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="f9752-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="f9752-291">Selecteer **Geavanceerde DNS**.</span><span class="sxs-lookup"><span data-stu-id="f9752-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="f9752-293">Selecteer IN de sectie **HOST RECORDS** de optie NIEUWE **RECORD TOEVOEGEN**.</span><span class="sxs-lookup"><span data-stu-id="f9752-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="f9752-295">Selecteer in de vervolgkeuzelijst **Type** de optie **SRV Record**.</span><span class="sxs-lookup"><span data-stu-id="f9752-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9752-296">De vervolgkeuzelijst **Type** wordt automatisch weergegeven wanneer u **NIEUWE RECORD TOEVOEGEN selecteert.**</span><span class="sxs-lookup"><span data-stu-id="f9752-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="f9752-298">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de lege vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f9752-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="f9752-299">**Service**</span><span class="sxs-lookup"><span data-stu-id="f9752-299">**Service**</span></span>|<span data-ttu-id="f9752-300">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="f9752-300">**Protocol**</span></span>|<span data-ttu-id="f9752-301">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="f9752-301">**Priority**</span></span>|<span data-ttu-id="f9752-302">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="f9752-302">**Weight**</span></span>|<span data-ttu-id="f9752-303">**Poort**</span><span class="sxs-lookup"><span data-stu-id="f9752-303">**Port**</span></span>|<span data-ttu-id="f9752-304">**Target**</span><span class="sxs-lookup"><span data-stu-id="f9752-304">**Target**</span></span>|<span data-ttu-id="f9752-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f9752-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f9752-306">_sip</span><span class="sxs-lookup"><span data-stu-id="f9752-306">_sip</span></span>  <br/> |<span data-ttu-id="f9752-307">_tls</span><span class="sxs-lookup"><span data-stu-id="f9752-307">_tls</span></span>  <br/> |<span data-ttu-id="f9752-308">100</span><span class="sxs-lookup"><span data-stu-id="f9752-308">100</span></span>  <br/> |<span data-ttu-id="f9752-309">1</span><span class="sxs-lookup"><span data-stu-id="f9752-309">1</span></span>  <br/> |<span data-ttu-id="f9752-310">443</span><span class="sxs-lookup"><span data-stu-id="f9752-310">443</span></span>  <br/> |<span data-ttu-id="f9752-311">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f9752-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f9752-312">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f9752-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f9752-313">30 min</span><span class="sxs-lookup"><span data-stu-id="f9752-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="f9752-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f9752-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="f9752-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="f9752-315">_tcp</span></span>  <br/> |<span data-ttu-id="f9752-316">100</span><span class="sxs-lookup"><span data-stu-id="f9752-316">100</span></span>  <br/> |<span data-ttu-id="f9752-317">1</span><span class="sxs-lookup"><span data-stu-id="f9752-317">1</span></span>  <br/> |<span data-ttu-id="f9752-318">5061</span><span class="sxs-lookup"><span data-stu-id="f9752-318">5061</span></span>  <br/> |<span data-ttu-id="f9752-319">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f9752-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="f9752-320">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f9752-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="f9752-321">30 min</span><span class="sxs-lookup"><span data-stu-id="f9752-321">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="f9752-323">Selecteer het besturingselement **Wijzigingen opslaan** (vinkje).</span><span class="sxs-lookup"><span data-stu-id="f9752-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="f9752-325">Met de vier voorgaande stappen en de waarden uit de tweede rij in de tabel, moet u de andere SRV-record toevoegen.</span><span class="sxs-lookup"><span data-stu-id="f9752-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f9752-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f9752-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
