---
title: DNS-records maken op name.com voor Microsoft
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op name.com voor Microsoft.
ms.openlocfilehash: 8518ca2570b3be1cb3abcd5c57b8309e989481cb
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938658"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="19515-103">DNS-records maken op name.com voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="19515-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="19515-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="19515-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="19515-105">Als name.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="19515-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="19515-106">Nadat u deze records bij name.com hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="19515-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="19515-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="19515-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="19515-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="19515-110">Add a TXT record for verification</span></span>
<span data-ttu-id="19515-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="19515-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="19515-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="19515-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19515-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="19515-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="19515-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="19515-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="19515-119">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="19515-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="19515-121">Selecteer **DNS-records**in de kolom **Details** .</span><span class="sxs-lookup"><span data-stu-id="19515-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="19515-123">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="19515-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="19515-124">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="19515-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="19515-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="19515-125">**Type**</span></span> <br/> |<span data-ttu-id="19515-126">**Host**</span><span class="sxs-lookup"><span data-stu-id="19515-126">**Host**</span></span> <br/> |<span data-ttu-id="19515-127">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="19515-127">**Answer**</span></span> <br/> |<span data-ttu-id="19515-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="19515-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="19515-129">TXT</span><span class="sxs-lookup"><span data-stu-id="19515-129">TXT</span></span>  <br/> |<span data-ttu-id="19515-130">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="19515-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="19515-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="19515-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="19515-132">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="19515-132">**Note:** This is an example.</span></span> <span data-ttu-id="19515-133">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="19515-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="19515-134">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="19515-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="19515-135">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="19515-135">Use the default value (300).</span></span>  <br/> |
   
    ![Afbeelding van het te geven/geeft aan de knop Verifiëren-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="19515-137">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="19515-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="19515-139">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="19515-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="19515-140">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="19515-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="19515-141">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="19515-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="19515-142">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="19515-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="19515-143">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="19515-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="19515-144">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="19515-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="19515-145">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="19515-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="19515-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="19515-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="19515-149">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="19515-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="19515-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="19515-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="19515-p107">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="19515-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="19515-154">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="19515-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="19515-156">Selecteer **DNS-records**in de kolom **Details** .</span><span class="sxs-lookup"><span data-stu-id="19515-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="19515-158">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="19515-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="19515-159">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="19515-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="19515-160">**Type**</span><span class="sxs-lookup"><span data-stu-id="19515-160">**Type**</span></span>|<span data-ttu-id="19515-161">**Host**</span><span class="sxs-lookup"><span data-stu-id="19515-161">**Host**</span></span>|<span data-ttu-id="19515-162">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="19515-162">**Answer**</span></span>|<span data-ttu-id="19515-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="19515-163">**TTL**</span></span>|<span data-ttu-id="19515-164">**Prio**</span><span class="sxs-lookup"><span data-stu-id="19515-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="19515-165">MX</span><span class="sxs-lookup"><span data-stu-id="19515-165">MX</span></span>  <br/> |<span data-ttu-id="19515-166">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="19515-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="19515-167">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="19515-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="19515-168">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="19515-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="19515-169">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="19515-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="19515-170">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="19515-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="19515-171">0</span><span class="sxs-lookup"><span data-stu-id="19515-171">0</span></span>  <br/> <span data-ttu-id="19515-172">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="19515-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Afbeelding van het te maken](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="19515-174">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="19515-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="19515-176">Als er andere MX-records zijn, verwijdert u deze met behulp van de volgende tweestapsprocedure:</span><span class="sxs-lookup"><span data-stu-id="19515-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="19515-177">Selecteer **Verwijderen** voor elkaars MX-record in de kolom **Acties.**</span><span class="sxs-lookup"><span data-stu-id="19515-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="19515-179">Als u elke verwijdering wilt bevestigen, selecteert u **Opnieuw verwijderen** in de kolom **Acties.**</span><span class="sxs-lookup"><span data-stu-id="19515-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="19515-181">Herhaal deze tweestapsprocedure tot u alle overige MX-records hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="19515-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="19515-182">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="19515-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="19515-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="19515-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="19515-p109">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="19515-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="19515-187">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="19515-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="19515-189">Selecteer **DNS-records**in de kolom **Details** .</span><span class="sxs-lookup"><span data-stu-id="19515-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="19515-191">Voeg de eerste CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="19515-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="19515-192">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="19515-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="19515-193">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="19515-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="19515-194">**Type**</span><span class="sxs-lookup"><span data-stu-id="19515-194">**Type**</span></span>|<span data-ttu-id="19515-195">**Host**</span><span class="sxs-lookup"><span data-stu-id="19515-195">**Host**</span></span>|<span data-ttu-id="19515-196">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="19515-196">**Answer**</span></span>|<span data-ttu-id="19515-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="19515-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="19515-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="19515-198">CNAME</span></span>  <br/> |<span data-ttu-id="19515-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="19515-199">autodiscover</span></span>  <br/> |<span data-ttu-id="19515-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="19515-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="19515-201">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="19515-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="19515-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="19515-202">CNAME</span></span>  <br/> |<span data-ttu-id="19515-203">sip</span><span class="sxs-lookup"><span data-stu-id="19515-203">sip</span></span>  <br/> |<span data-ttu-id="19515-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="19515-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="19515-205">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="19515-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="19515-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="19515-206">CNAME</span></span>  <br/> |<span data-ttu-id="19515-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="19515-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="19515-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="19515-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="19515-209">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="19515-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="19515-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="19515-210">CNAME</span></span>  <br/> |<span data-ttu-id="19515-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="19515-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="19515-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="19515-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="19515-213">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="19515-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="19515-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="19515-214">CNAME</span></span>  <br/> |<span data-ttu-id="19515-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="19515-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="19515-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="19515-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="19515-217">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="19515-217">Use the default value (300).</span></span>  <br/> |
   
   ![Afbeelding van het te maken](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="19515-219">Selecteer **Record toevoegen** om de eerste record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="19515-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="19515-221">Voeg de tweede CNAME-record toe:</span><span class="sxs-lookup"><span data-stu-id="19515-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="19515-222">Gebruik de waarden uit de tweede rij van de bovenstaande tabel en selecteer **Record toevoegen** om de tweede record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="19515-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="19515-223">Voeg de resterende records op dezelfde manier toe met behulp van de waarden uit de derde, vierde, vijfde en zesde rij van de tabel.</span><span class="sxs-lookup"><span data-stu-id="19515-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="19515-224">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="19515-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="19515-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="19515-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="19515-226">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="19515-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="19515-227">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="19515-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="19515-228">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19515-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="19515-229">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="19515-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="19515-p111">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="19515-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="19515-233">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="19515-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="19515-235">Selecteer **DNS-records**in de kolom **Details** .</span><span class="sxs-lookup"><span data-stu-id="19515-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="19515-237">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="19515-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="19515-238">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="19515-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="19515-239">**Type**</span><span class="sxs-lookup"><span data-stu-id="19515-239">**Type**</span></span>|<span data-ttu-id="19515-240">**Host**</span><span class="sxs-lookup"><span data-stu-id="19515-240">**Host**</span></span>|<span data-ttu-id="19515-241">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="19515-241">**Answer**</span></span>|<span data-ttu-id="19515-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="19515-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="19515-243">TXT</span><span class="sxs-lookup"><span data-stu-id="19515-243">TXT</span></span>  <br/> |<span data-ttu-id="19515-244">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="19515-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="19515-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="19515-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="19515-246">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="19515-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="19515-247">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="19515-247">Use the default value (300).</span></span>  <br/> |
   
   ![Afbeelding van het te maken](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="19515-249">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="19515-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="19515-251">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="19515-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="19515-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="19515-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="19515-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="19515-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="19515-256">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="19515-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="19515-258">Selecteer **DNS Records+** in de kolom **Details.**</span><span class="sxs-lookup"><span data-stu-id="19515-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="19515-260">Voeg de eerste SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="19515-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="19515-261">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="19515-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="19515-262">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="19515-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="19515-263">**Type**</span><span class="sxs-lookup"><span data-stu-id="19515-263">**Type**</span></span>|<span data-ttu-id="19515-264">**Service**</span><span class="sxs-lookup"><span data-stu-id="19515-264">**Service**</span></span>|<span data-ttu-id="19515-265">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="19515-265">**Weight**</span></span>|<span data-ttu-id="19515-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="19515-266">**TTL**</span></span>|<span data-ttu-id="19515-267">**Prio**</span><span class="sxs-lookup"><span data-stu-id="19515-267">**Prio**</span></span>|<span data-ttu-id="19515-268">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="19515-268">**Protocol**</span></span>|<span data-ttu-id="19515-269">**Poort**</span><span class="sxs-lookup"><span data-stu-id="19515-269">**Port**</span></span>|<span data-ttu-id="19515-270">**Doel**</span><span class="sxs-lookup"><span data-stu-id="19515-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="19515-271">SRV</span><span class="sxs-lookup"><span data-stu-id="19515-271">SRV</span></span>|<span data-ttu-id="19515-272">sip</span><span class="sxs-lookup"><span data-stu-id="19515-272">sip</span></span>|<span data-ttu-id="19515-273">1</span><span class="sxs-lookup"><span data-stu-id="19515-273">1</span></span>|<span data-ttu-id="19515-274">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="19515-274">Use the default value (300).</span></span>|<span data-ttu-id="19515-275">100</span><span class="sxs-lookup"><span data-stu-id="19515-275">100</span></span>|<span data-ttu-id="19515-276">tls</span><span class="sxs-lookup"><span data-stu-id="19515-276">tls</span></span>|<span data-ttu-id="19515-277">443</span><span class="sxs-lookup"><span data-stu-id="19515-277">443</span></span>|<span data-ttu-id="19515-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="19515-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="19515-279">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="19515-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="19515-280">SRV</span><span class="sxs-lookup"><span data-stu-id="19515-280">SRV</span></span>|<span data-ttu-id="19515-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="19515-281">sipfederationtls</span></span>|<span data-ttu-id="19515-282">1</span><span class="sxs-lookup"><span data-stu-id="19515-282">1</span></span>|<span data-ttu-id="19515-283">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="19515-283">Use the default value (300).</span></span>|<span data-ttu-id="19515-284">100</span><span class="sxs-lookup"><span data-stu-id="19515-284">100</span></span>|<span data-ttu-id="19515-285">tcp</span><span class="sxs-lookup"><span data-stu-id="19515-285">tcp</span></span>|<span data-ttu-id="19515-286">5061</span><span class="sxs-lookup"><span data-stu-id="19515-286">5061</span></span>|<span data-ttu-id="19515-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="19515-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="19515-288">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="19515-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Afbeelding van het te maken](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="19515-290">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="19515-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="19515-292">Voeg als volgt de tweede SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="19515-292">Add the second SRV record:</span></span>

<span data-ttu-id="19515-293">Gebruik de waarden uit de volgende rij van de bovenstaande tabel en selecteer **Record toevoegen** om de tweede record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="19515-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="19515-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="19515-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
