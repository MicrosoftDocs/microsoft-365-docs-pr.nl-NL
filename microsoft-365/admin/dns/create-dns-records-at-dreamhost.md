---
title: DNS-records bij Dreamhost maken voor Microsoft
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Dreamhost voor Microsoft.
ms.openlocfilehash: 8ab617fd5d63b292a85289d2d51a0ae0fd3b26be
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646197"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="8a460-103">DNS-records bij Dreamhost maken voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a460-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="8a460-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="8a460-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8a460-105">Als DreamHost uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Lync enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="8a460-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="8a460-106">Nadat u deze records bij DreamHost hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="8a460-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="8a460-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8a460-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8a460-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="8a460-110">Add a TXT record for verification</span></span>
<span data-ttu-id="8a460-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8a460-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8a460-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="8a460-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a460-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8a460-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8a460-p104">Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8a460-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="8a460-119">Selecteer op de pagina **Dashboard** de optie **Domains**en vervolgens **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="8a460-119">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="8a460-121">Selecteer op de pagina **domeinen beheren** in de sectie **Domain** de optie **DNS** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="8a460-121">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="8a460-123">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8a460-123">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8a460-124">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="8a460-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8a460-125">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="8a460-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8a460-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="8a460-126">**Name**</span></span>|<span data-ttu-id="8a460-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="8a460-127">**Type**</span></span>|<span data-ttu-id="8a460-128">**Value**</span><span class="sxs-lookup"><span data-stu-id="8a460-128">**Value**</span></span>|<span data-ttu-id="8a460-129">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="8a460-129">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8a460-130">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="8a460-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8a460-131">TXT</span><span class="sxs-lookup"><span data-stu-id="8a460-131">TXT</span></span>  <br/> |<span data-ttu-id="8a460-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8a460-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8a460-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8a460-133">**Note:** This is an example.</span></span> <span data-ttu-id="8a460-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="8a460-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="8a460-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="8a460-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8a460-136">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="8a460-136">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost voor 1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="8a460-138">Selecteer **record nu toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8a460-138">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="8a460-140">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8a460-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8a460-141">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="8a460-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8a460-142">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="8a460-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8a460-143">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="8a460-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8a460-144">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="8a460-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8a460-145">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="8a460-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8a460-146">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="8a460-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8a460-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8a460-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8a460-150">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="8a460-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8a460-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8a460-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="8a460-152">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="8a460-152">Follow the steps below.</span></span>
  
1. <span data-ttu-id="8a460-p107">Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8a460-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="8a460-156">Selecteer op de pagina **Dashboard** de optie **mail**en vervolgens **Custom MX**.</span><span class="sxs-lookup"><span data-stu-id="8a460-156">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="8a460-158">Selecteer in de sectie **e-mail bezorgen beheren** , in de kolom **acties** , de optie **bewerken** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="8a460-158">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="8a460-160">Typ of kopieer en plak de volgende waarden uit de volgende tabel in het gebied **Custom MX Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8a460-160">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="8a460-161">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="8a460-161">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8a460-162">(Als er andere bestaande MX-records zijn, markeert u deze records om te worden verwijderd.)</span><span class="sxs-lookup"><span data-stu-id="8a460-162">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="8a460-163">**MX-record (vereist)**</span><span class="sxs-lookup"><span data-stu-id="8a460-163">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="8a460-164">0  *\<domain-key\>*  . mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8a460-164">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="8a460-165">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="8a460-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="8a460-p108">De 0 is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  </span><span class="sxs-lookup"><span data-stu-id="8a460-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="8a460-168">**Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="8a460-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="8a460-169">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="8a460-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost voor 2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="8a460-171">Selecteer **dit domein wijzigen om nu aangepaste MX-records te gebruiken!**</span><span class="sxs-lookup"><span data-stu-id="8a460-171">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="8a460-173">Als er andere bestaande MX-records zijn, verwijdert u elke record door deze te selecteren en vervolgens op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="8a460-173">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="8a460-175">Als u records hebt verwijderd, selecteert u **uw aangepaste MX-records nu bijwerken.**</span><span class="sxs-lookup"><span data-stu-id="8a460-175">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8a460-177">De zes CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a460-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8a460-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8a460-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="8a460-179">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="8a460-179">Follow the steps below.</span></span>
  
1. <span data-ttu-id="8a460-p110">Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8a460-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="8a460-183">Selecteer op de pagina **Dashboard** de optie **Domains**en vervolgens **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="8a460-183">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="8a460-185">Selecteer op de pagina **domeinen beheren** in de sectie **Domain** de optie **DNS** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="8a460-185">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="8a460-187">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8a460-187">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="8a460-188">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="8a460-188">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8a460-189">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="8a460-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8a460-190">**Name**</span><span class="sxs-lookup"><span data-stu-id="8a460-190">**Name**</span></span>|<span data-ttu-id="8a460-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="8a460-191">**Type**</span></span>|<span data-ttu-id="8a460-192">**Value**</span><span class="sxs-lookup"><span data-stu-id="8a460-192">**Value**</span></span>|<span data-ttu-id="8a460-193">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="8a460-193">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8a460-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8a460-194">autodiscover</span></span>  <br/> |<span data-ttu-id="8a460-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="8a460-195">CNAME</span></span>  <br/> |<span data-ttu-id="8a460-196">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="8a460-196">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="8a460-197">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="8a460-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a460-198">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="8a460-198">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="8a460-199">sip</span><span class="sxs-lookup"><span data-stu-id="8a460-199">sip</span></span>  <br/> |<span data-ttu-id="8a460-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="8a460-200">CNAME</span></span>  <br/> |<span data-ttu-id="8a460-201">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8a460-201">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8a460-202">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="8a460-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a460-203">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="8a460-203">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="8a460-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8a460-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8a460-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="8a460-205">CNAME</span></span>  <br/> |<span data-ttu-id="8a460-206">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8a460-206">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8a460-207">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="8a460-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a460-208">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="8a460-208">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="8a460-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8a460-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8a460-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="8a460-210">CNAME</span></span>  <br/> |<span data-ttu-id="8a460-211">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="8a460-211">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="8a460-212">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="8a460-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a460-213">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="8a460-213">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="8a460-214">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8a460-214">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8a460-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="8a460-215">CNAME</span></span>  <br/> |<span data-ttu-id="8a460-216">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8a460-216">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="8a460-217">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="8a460-217">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a460-218">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="8a460-218">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost voor 3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="8a460-220">Selecteer **record nu toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8a460-220">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="8a460-222">Met de twee voorgaande stappen en de waarden uit de andere vijf rijen in de tabel voegt u de andere vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="8a460-222">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8a460-223">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="8a460-223">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8a460-224"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8a460-224"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a460-225">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="8a460-225">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8a460-226">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="8a460-226">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8a460-227">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8a460-227">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8a460-228">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="8a460-228">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="8a460-229">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="8a460-229">Follow the steps below.</span></span>
  
1. <span data-ttu-id="8a460-p112">Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8a460-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="8a460-233">Selecteer op de pagina **Dashboard** de optie **Domains**en vervolgens **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="8a460-233">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="8a460-235">Selecteer op de pagina **domeinen beheren** in de sectie **Domain** de optie **DNS** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="8a460-235">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="8a460-237">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8a460-237">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="8a460-238">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="8a460-238">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8a460-239">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="8a460-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8a460-240">**Name**</span><span class="sxs-lookup"><span data-stu-id="8a460-240">**Name**</span></span>|<span data-ttu-id="8a460-241">**Type**</span><span class="sxs-lookup"><span data-stu-id="8a460-241">**Type**</span></span>|<span data-ttu-id="8a460-242">**Value**</span><span class="sxs-lookup"><span data-stu-id="8a460-242">**Value**</span></span>|<span data-ttu-id="8a460-243">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="8a460-243">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8a460-244">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="8a460-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="8a460-245">TXT</span><span class="sxs-lookup"><span data-stu-id="8a460-245">TXT</span></span>  <br/> |<span data-ttu-id="8a460-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8a460-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8a460-247">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="8a460-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="8a460-248">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="8a460-248">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost voor 4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="8a460-250">Selecteer **record nu toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8a460-250">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="8a460-252">Met de twee voorgaande stappen en de waarden uit de tweede rij in de tabel, moet u de andere SRV-record toevoegen.</span><span class="sxs-lookup"><span data-stu-id="8a460-252">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8a460-253">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a460-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8a460-254"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8a460-254"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="8a460-255">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="8a460-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="8a460-p113">Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8a460-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="8a460-259">Selecteer op de pagina **Dashboard** de optie **Domains**en vervolgens **Manage Domains**.</span><span class="sxs-lookup"><span data-stu-id="8a460-259">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="8a460-261">Selecteer op de pagina **domeinen beheren** in de sectie **Domain** de optie **DNS** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="8a460-261">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="8a460-263">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8a460-263">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="8a460-264">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="8a460-264">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8a460-265">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="8a460-265">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8a460-266">**Name**</span><span class="sxs-lookup"><span data-stu-id="8a460-266">**Name**</span></span>|<span data-ttu-id="8a460-267">**Type**</span><span class="sxs-lookup"><span data-stu-id="8a460-267">**Type**</span></span>|<span data-ttu-id="8a460-268">**Value**</span><span class="sxs-lookup"><span data-stu-id="8a460-268">**Value**</span></span>|<span data-ttu-id="8a460-269">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="8a460-269">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8a460-270">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="8a460-270">_sip._tls</span></span>  <br/> |<span data-ttu-id="8a460-271">SRV</span><span class="sxs-lookup"><span data-stu-id="8a460-271">SRV</span></span>  <br/> |<span data-ttu-id="8a460-272">100 1 443</span><span class="sxs-lookup"><span data-stu-id="8a460-272">100 1 443</span></span>  <br/> <span data-ttu-id="8a460-273">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8a460-273">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="8a460-274">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="8a460-274">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a460-275">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="8a460-275">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="8a460-276">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="8a460-276">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="8a460-277">SRV</span><span class="sxs-lookup"><span data-stu-id="8a460-277">SRV</span></span>  <br/> |<span data-ttu-id="8a460-278">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="8a460-278">100 1 5061</span></span>  <br/> <span data-ttu-id="8a460-279">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8a460-279">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="8a460-280">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="8a460-280">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="8a460-281">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="8a460-281">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost voor 5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="8a460-283">Selecteer **Add Record Now!**.</span><span class="sxs-lookup"><span data-stu-id="8a460-283">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="8a460-285">Met de twee voorgaande stappen en de waarden uit de tweede rij in de tabel, moet u de andere SRV-record toevoegen.</span><span class="sxs-lookup"><span data-stu-id="8a460-285">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="8a460-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8a460-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
