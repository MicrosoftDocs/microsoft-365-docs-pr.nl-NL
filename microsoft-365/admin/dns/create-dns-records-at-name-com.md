---
title: DNS-records maken op name.com voor Microsoft
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
- BCS160
- MET150
- MOE150
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services op name.com voor Microsoft.
ms.openlocfilehash: 97cc83fe060f8fbfe78decff584bded3102b09b5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910172"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="c5600-103">DNS-records maken op name.com voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="c5600-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="c5600-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="c5600-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c5600-105">Als name.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="c5600-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c5600-106">Nadat u deze records hebt name.com, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="c5600-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="c5600-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c5600-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c5600-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="c5600-110">Add a TXT record for verification</span></span>
<span data-ttu-id="c5600-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c5600-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c5600-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="c5600-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c5600-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c5600-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c5600-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="c5600-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="c5600-119">Selecteer **onder Mijn domeinen** de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c5600-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="c5600-121">Selecteer dns-records in **de** kolom **Details.**</span><span class="sxs-lookup"><span data-stu-id="c5600-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="c5600-123">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="c5600-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="c5600-124">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="c5600-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5600-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="c5600-125">**Type**</span></span> <br/> |<span data-ttu-id="c5600-126">**Host**</span><span class="sxs-lookup"><span data-stu-id="c5600-126">**Host**</span></span> <br/> |<span data-ttu-id="c5600-127">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="c5600-127">**Answer**</span></span> <br/> |<span data-ttu-id="c5600-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5600-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="c5600-129">TXT</span><span class="sxs-lookup"><span data-stu-id="c5600-129">TXT</span></span>  <br/> |<span data-ttu-id="c5600-130">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="c5600-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="c5600-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c5600-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c5600-132">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="c5600-132">**Note:** This is an example.</span></span> <span data-ttu-id="c5600-133">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="c5600-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="c5600-134">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="c5600-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c5600-135">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="c5600-135">Use the default value (300).</span></span>  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="c5600-137">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c5600-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="c5600-139">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="c5600-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c5600-140">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="c5600-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c5600-141">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="c5600-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c5600-142">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="c5600-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c5600-143">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="c5600-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="c5600-144">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="c5600-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="c5600-145">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="c5600-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="c5600-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c5600-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c5600-149">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="c5600-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c5600-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c5600-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="c5600-p107">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="c5600-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="c5600-154">Selecteer **onder Mijn domeinen** de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c5600-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="c5600-156">Selecteer dns-records in **de** kolom **Details.**</span><span class="sxs-lookup"><span data-stu-id="c5600-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="c5600-158">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="c5600-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="c5600-159">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="c5600-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c5600-160">**Type**</span><span class="sxs-lookup"><span data-stu-id="c5600-160">**Type**</span></span>|<span data-ttu-id="c5600-161">**Host**</span><span class="sxs-lookup"><span data-stu-id="c5600-161">**Host**</span></span>|<span data-ttu-id="c5600-162">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="c5600-162">**Answer**</span></span>|<span data-ttu-id="c5600-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5600-163">**TTL**</span></span>|<span data-ttu-id="c5600-164">**Prio**</span><span class="sxs-lookup"><span data-stu-id="c5600-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5600-165">MX</span><span class="sxs-lookup"><span data-stu-id="c5600-165">MX</span></span>  <br/> |<span data-ttu-id="c5600-166">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="c5600-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="c5600-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c5600-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c5600-168">**Opmerking:** Haal uw  *\<domain-key\>*  uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="c5600-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="c5600-169">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="c5600-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c5600-170">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="c5600-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="c5600-171">0</span><span class="sxs-lookup"><span data-stu-id="c5600-171">0</span></span>  <br/> <span data-ttu-id="c5600-172">Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="c5600-172">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="c5600-174">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c5600-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="c5600-176">Als er andere MX-records zijn, verwijdert u deze met behulp van de volgende tweestapsprocedure:</span><span class="sxs-lookup"><span data-stu-id="c5600-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="c5600-177">Selecteer Verwijderen in de  kolom **Acties** voor elke andere MX-record.</span><span class="sxs-lookup"><span data-stu-id="c5600-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="c5600-179">Als u elke verwijdering wilt bevestigen, **selecteert u Opnieuw** Verwijderen in **de** kolom Acties.</span><span class="sxs-lookup"><span data-stu-id="c5600-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="c5600-181">Herhaal deze tweestapsprocedure tot u alle overige MX-records hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c5600-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c5600-182">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="c5600-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c5600-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c5600-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="c5600-p109">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="c5600-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="c5600-187">Selecteer **onder Mijn domeinen** de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c5600-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="c5600-189">Selecteer dns-records in **de** kolom **Details.**</span><span class="sxs-lookup"><span data-stu-id="c5600-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="c5600-191">Voeg de eerste CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="c5600-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="c5600-192">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="c5600-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="c5600-193">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="c5600-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c5600-194">**Type**</span><span class="sxs-lookup"><span data-stu-id="c5600-194">**Type**</span></span>|<span data-ttu-id="c5600-195">**Host**</span><span class="sxs-lookup"><span data-stu-id="c5600-195">**Host**</span></span>|<span data-ttu-id="c5600-196">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="c5600-196">**Answer**</span></span>|<span data-ttu-id="c5600-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5600-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5600-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="c5600-198">CNAME</span></span>  <br/> |<span data-ttu-id="c5600-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c5600-199">autodiscover</span></span>  <br/> |<span data-ttu-id="c5600-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c5600-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="c5600-201">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="c5600-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="c5600-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="c5600-202">CNAME</span></span>  <br/> |<span data-ttu-id="c5600-203">sip</span><span class="sxs-lookup"><span data-stu-id="c5600-203">sip</span></span>  <br/> |<span data-ttu-id="c5600-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c5600-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c5600-205">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="c5600-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="c5600-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="c5600-206">CNAME</span></span>  <br/> |<span data-ttu-id="c5600-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c5600-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c5600-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c5600-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c5600-209">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="c5600-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="c5600-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="c5600-210">CNAME</span></span>  <br/> |<span data-ttu-id="c5600-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c5600-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c5600-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c5600-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="c5600-213">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="c5600-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="c5600-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="c5600-214">CNAME</span></span>  <br/> |<span data-ttu-id="c5600-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c5600-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c5600-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c5600-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="c5600-217">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="c5600-217">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="c5600-219">Selecteer **Record toevoegen om** de eerste record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="c5600-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="c5600-221">Voeg de tweede CNAME-record toe:</span><span class="sxs-lookup"><span data-stu-id="c5600-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="c5600-222">Gebruik de waarden uit de tweede rij van de bovenstaande tabel en selecteer **Vervolgens Record toevoegen** om de tweede record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="c5600-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="c5600-223">Voeg de resterende records op dezelfde manier toe met behulp van de waarden uit de derde, vierde, vijfde en zesde rij van de tabel.</span><span class="sxs-lookup"><span data-stu-id="c5600-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c5600-224">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="c5600-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c5600-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c5600-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5600-226">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="c5600-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c5600-227">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="c5600-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c5600-228">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5600-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c5600-229">Voeg in plaats daarvan de vereiste Microsoft-waarden  toe aan de huidige record, zodat u één SPF-record hebt met beide sets waarden.</span><span class="sxs-lookup"><span data-stu-id="c5600-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="c5600-p111">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="c5600-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="c5600-233">Selecteer **onder Mijn domeinen** de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c5600-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="c5600-235">Selecteer dns-records in **de** kolom **Details.**</span><span class="sxs-lookup"><span data-stu-id="c5600-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="c5600-237">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="c5600-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="c5600-238">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="c5600-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c5600-239">**Type**</span><span class="sxs-lookup"><span data-stu-id="c5600-239">**Type**</span></span>|<span data-ttu-id="c5600-240">**Host**</span><span class="sxs-lookup"><span data-stu-id="c5600-240">**Host**</span></span>|<span data-ttu-id="c5600-241">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="c5600-241">**Answer**</span></span>|<span data-ttu-id="c5600-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5600-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5600-243">TXT</span><span class="sxs-lookup"><span data-stu-id="c5600-243">TXT</span></span>  <br/> |<span data-ttu-id="c5600-244">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="c5600-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="c5600-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c5600-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c5600-246">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="c5600-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="c5600-247">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="c5600-247">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="c5600-249">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c5600-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c5600-251">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="c5600-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c5600-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c5600-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="c5600-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="c5600-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="c5600-256">Selecteer **onder Mijn domeinen** de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c5600-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="c5600-258">Selecteer in **de kolom** Details de optie **DNS Records+**.</span><span class="sxs-lookup"><span data-stu-id="c5600-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="c5600-260">Voeg de eerste SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="c5600-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="c5600-261">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="c5600-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="c5600-262">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="c5600-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c5600-263">**Type**</span><span class="sxs-lookup"><span data-stu-id="c5600-263">**Type**</span></span>|<span data-ttu-id="c5600-264">**Service**</span><span class="sxs-lookup"><span data-stu-id="c5600-264">**Service**</span></span>|<span data-ttu-id="c5600-265">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="c5600-265">**Weight**</span></span>|<span data-ttu-id="c5600-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c5600-266">**TTL**</span></span>|<span data-ttu-id="c5600-267">**Prio**</span><span class="sxs-lookup"><span data-stu-id="c5600-267">**Prio**</span></span>|<span data-ttu-id="c5600-268">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="c5600-268">**Protocol**</span></span>|<span data-ttu-id="c5600-269">**Poort**</span><span class="sxs-lookup"><span data-stu-id="c5600-269">**Port**</span></span>|<span data-ttu-id="c5600-270">**Doel**</span><span class="sxs-lookup"><span data-stu-id="c5600-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c5600-271">SRV</span><span class="sxs-lookup"><span data-stu-id="c5600-271">SRV</span></span>|<span data-ttu-id="c5600-272">sip</span><span class="sxs-lookup"><span data-stu-id="c5600-272">sip</span></span>|<span data-ttu-id="c5600-273">1</span><span class="sxs-lookup"><span data-stu-id="c5600-273">1</span></span>|<span data-ttu-id="c5600-274">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="c5600-274">Use the default value (300).</span></span>|<span data-ttu-id="c5600-275">100</span><span class="sxs-lookup"><span data-stu-id="c5600-275">100</span></span>|<span data-ttu-id="c5600-276">tls</span><span class="sxs-lookup"><span data-stu-id="c5600-276">tls</span></span>|<span data-ttu-id="c5600-277">443</span><span class="sxs-lookup"><span data-stu-id="c5600-277">443</span></span>|<span data-ttu-id="c5600-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c5600-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="c5600-279">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="c5600-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="c5600-280">SRV</span><span class="sxs-lookup"><span data-stu-id="c5600-280">SRV</span></span>|<span data-ttu-id="c5600-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c5600-281">sipfederationtls</span></span>|<span data-ttu-id="c5600-282">1</span><span class="sxs-lookup"><span data-stu-id="c5600-282">1</span></span>|<span data-ttu-id="c5600-283">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="c5600-283">Use the default value (300).</span></span>|<span data-ttu-id="c5600-284">100</span><span class="sxs-lookup"><span data-stu-id="c5600-284">100</span></span>|<span data-ttu-id="c5600-285">tcp</span><span class="sxs-lookup"><span data-stu-id="c5600-285">tcp</span></span>|<span data-ttu-id="c5600-286">5061</span><span class="sxs-lookup"><span data-stu-id="c5600-286">5061</span></span>|<span data-ttu-id="c5600-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c5600-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="c5600-288">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="c5600-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="c5600-290">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c5600-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="c5600-292">Voeg als volgt de tweede SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="c5600-292">Add the second SRV record:</span></span>

<span data-ttu-id="c5600-293">Gebruik de waarden uit de volgende rij van de bovenstaande tabel en selecteer **Vervolgens Record toevoegen** om de tweede record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="c5600-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="c5600-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c5600-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>