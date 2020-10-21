---
title: DNS-records bij Names.co.uk maken voor Microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Names.co.uk voor Microsoft.
ms.openlocfilehash: d3a3e68558efc3857d343b3298c3c01f0e8d8802
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645861"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="20870-103">DNS-records bij Names.co.uk maken voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="20870-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="20870-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="20870-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="20870-105">Als Names.co.uk uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="20870-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="20870-106">Nadat u deze records bij Names.co.uk hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="20870-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="20870-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="20870-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="20870-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="20870-110">Add a TXT record for verification</span></span>
<span data-ttu-id="20870-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="20870-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="20870-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="20870-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20870-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="20870-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="20870-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="20870-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Gebeurtenis ondblclick voor 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="20870-119">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="20870-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="20870-120">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-120">(You may have to scroll down.)</span></span>
    
    ![Gebeurtenis ondblclick voor 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="20870-122">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="20870-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="20870-123">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="20870-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="20870-124">(Als u een rij wilt toevoegen, selecteert u **add a/CNAME-records (+)**.)</span><span class="sxs-lookup"><span data-stu-id="20870-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="20870-125">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="20870-126">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="20870-126">**Host name**</span></span>|<span data-ttu-id="20870-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="20870-127">**Type**</span></span>|<span data-ttu-id="20870-128">**Result**</span><span class="sxs-lookup"><span data-stu-id="20870-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="20870-129">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="20870-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="20870-130">TXT</span><span class="sxs-lookup"><span data-stu-id="20870-130">TXT</span></span>  <br/> |<span data-ttu-id="20870-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="20870-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="20870-132">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="20870-132">**Note:** This is an example.</span></span> <span data-ttu-id="20870-133">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="20870-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="20870-134">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="20870-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![Gebeurtenis ondblclick voor 1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="20870-136">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="20870-136">Select **Save**.</span></span>
    
    <span data-ttu-id="20870-137">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-137">(You may have to scroll down.)</span></span>
    
    ![Gebeurtenis ondblclick voor 1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="20870-139">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="20870-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="20870-140">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="20870-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="20870-141">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="20870-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="20870-142">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="20870-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="20870-143">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="20870-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="20870-144">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="20870-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="20870-145">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="20870-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="20870-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="20870-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="20870-149">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="20870-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="20870-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="20870-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="20870-p107">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="20870-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Gebeurtenis ondblclick voor 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="20870-154">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="20870-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="20870-155">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-155">(You may have to scroll down.)</span></span>
    
    ![Gebeurtenis ondblclick voor 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="20870-157">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **Mail Exchange records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="20870-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="20870-158">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="20870-159">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="20870-159">**Host name**</span></span>|<span data-ttu-id="20870-160">**Priority**</span><span class="sxs-lookup"><span data-stu-id="20870-160">**Priority**</span></span>|<span data-ttu-id="20870-161">**Result**</span><span class="sxs-lookup"><span data-stu-id="20870-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="20870-162">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="20870-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="20870-163">1</span><span class="sxs-lookup"><span data-stu-id="20870-163">1</span></span>  <br/> <span data-ttu-id="20870-164">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="20870-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="20870-165">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="20870-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="20870-166">> [!NOTE]> uw  *\<domain-key\>*  van uw Microsoft-account achterhalen.</span><span class="sxs-lookup"><span data-stu-id="20870-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="20870-167">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="20870-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Gebeurtenis ondblclick voor 2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="20870-169">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="20870-169">Select **Save**.</span></span>
    
    <span data-ttu-id="20870-170">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-170">(You may have to scroll down.)</span></span>
    
    ![Gebeurtenis ondblclick voor 2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="20870-172">Als er in de sectie **Mail Exchange records** andere MX-records worden vermeld, verwijdert u elke record door deze te selecteren en vervolgens op het toetsenbord op de toets **Delete** te drukken.</span><span class="sxs-lookup"><span data-stu-id="20870-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Gebeurtenis ondblclick voor 2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="20870-174">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="20870-174">Select **Save**.</span></span>
    
    <span data-ttu-id="20870-175">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-175">(You may have to scroll down.)</span></span>
    
    ![Gebeurtenis ondblclick voor 2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="20870-177">De zes CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="20870-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="20870-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="20870-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="20870-p109">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="20870-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Gebeurtenis ondblclick voor 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="20870-182">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="20870-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="20870-183">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-183">(You may have to scroll down.)</span></span>
    
    ![Gebeurtenis ondblclick voor 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="20870-185">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="20870-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="20870-186">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="20870-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="20870-187">(Als u een rij wilt toevoegen, selecteert u **add a/CNAME-records (+)**.)</span><span class="sxs-lookup"><span data-stu-id="20870-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="20870-188">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="20870-189">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="20870-189">**Host Name**</span></span>|<span data-ttu-id="20870-190">**Type**</span><span class="sxs-lookup"><span data-stu-id="20870-190">**Type**</span></span>|<span data-ttu-id="20870-191">**Result**</span><span class="sxs-lookup"><span data-stu-id="20870-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="20870-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="20870-192">autodiscover</span></span>  <br/> |<span data-ttu-id="20870-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="20870-193">CNAME</span></span>  <br/> |<span data-ttu-id="20870-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="20870-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="20870-195">sip</span><span class="sxs-lookup"><span data-stu-id="20870-195">sip</span></span>  <br/> |<span data-ttu-id="20870-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="20870-196">CNAME</span></span>  <br/> |<span data-ttu-id="20870-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20870-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="20870-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="20870-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="20870-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="20870-199">CNAME</span></span>  <br/> |<span data-ttu-id="20870-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20870-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="20870-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="20870-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="20870-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="20870-202">CNAME</span></span>  <br/> |<span data-ttu-id="20870-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="20870-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="20870-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="20870-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="20870-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="20870-205">CNAME</span></span>  <br/> |<span data-ttu-id="20870-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20870-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Gebeurtenis ondblclick voor 3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="20870-208">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="20870-208">Select **Save**.</span></span>
    
    ![Gebeurtenis ondblclick voor 3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="20870-210">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="20870-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="20870-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="20870-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="20870-212">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="20870-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="20870-213">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="20870-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="20870-214">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="20870-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="20870-215">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="20870-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="20870-p111">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="20870-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Gebeurtenis ondblclick voor 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="20870-219">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="20870-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="20870-220">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-220">(You may have to scroll down.)</span></span>
    
    ![Gebeurtenis ondblclick voor 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="20870-222">Selecteer op de pagina **DNS zones on account** in de kolom **domain name** de naam van het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="20870-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![Gebeurtenis ondblclick voor 1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="20870-224">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="20870-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="20870-225">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="20870-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="20870-226">(Als u een rij wilt toevoegen, selecteert u **add a/CNAME-records (+)**.)</span><span class="sxs-lookup"><span data-stu-id="20870-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="20870-227">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="20870-228">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="20870-228">**Host name**</span></span>|<span data-ttu-id="20870-229">**Type**</span><span class="sxs-lookup"><span data-stu-id="20870-229">**Type**</span></span>|<span data-ttu-id="20870-230">**Result**</span><span class="sxs-lookup"><span data-stu-id="20870-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="20870-231">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="20870-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="20870-232">TXT</span><span class="sxs-lookup"><span data-stu-id="20870-232">TXT</span></span>  <br/> |<span data-ttu-id="20870-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="20870-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="20870-234">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="20870-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![Gebeurtenis ondblclick voor 4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="20870-236">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="20870-236">Select **Save**.</span></span>
    
    <span data-ttu-id="20870-237">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-237">(You may have to scroll down.)</span></span>
    
    ![Gebeurtenis ondblclick voor 4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="20870-239">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="20870-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="20870-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="20870-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="20870-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="20870-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Gebeurtenis ondblclick voor 1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="20870-244">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="20870-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="20870-245">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-245">(You may have to scroll down.)</span></span>
    
    ![Gebeurtenis ondblclick voor 1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="20870-247">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **Service records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="20870-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="20870-248">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="20870-249">**Name**</span><span class="sxs-lookup"><span data-stu-id="20870-249">**Name**</span></span>|<span data-ttu-id="20870-250">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="20870-250">**Priority**</span></span>|<span data-ttu-id="20870-251">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="20870-251">**Weight**</span></span>|<span data-ttu-id="20870-252">**Poort**</span><span class="sxs-lookup"><span data-stu-id="20870-252">**Port**</span></span>|<span data-ttu-id="20870-253">**Result**</span><span class="sxs-lookup"><span data-stu-id="20870-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="20870-254">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="20870-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="20870-255">100</span><span class="sxs-lookup"><span data-stu-id="20870-255">100</span></span>  <br/> |<span data-ttu-id="20870-256">1</span><span class="sxs-lookup"><span data-stu-id="20870-256">1</span></span>  <br/> |<span data-ttu-id="20870-257">443</span><span class="sxs-lookup"><span data-stu-id="20870-257">443</span></span>  <br/> |<span data-ttu-id="20870-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20870-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="20870-259">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="20870-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="20870-260">100</span><span class="sxs-lookup"><span data-stu-id="20870-260">100</span></span>  <br/> |<span data-ttu-id="20870-261">1</span><span class="sxs-lookup"><span data-stu-id="20870-261">1</span></span>  <br/> |<span data-ttu-id="20870-262">5061</span><span class="sxs-lookup"><span data-stu-id="20870-262">5061</span></span>  <br/> |<span data-ttu-id="20870-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="20870-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Gebeurtenis ondblclick voor 5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="20870-265">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="20870-265">Select **Save**.</span></span>
    
    <span data-ttu-id="20870-266">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="20870-266">(You may have to scroll down.)</span></span>
    
    ![Gebeurtenis ondblclick voor 5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="20870-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="20870-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
