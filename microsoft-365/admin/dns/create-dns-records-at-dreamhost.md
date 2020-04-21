---
title: DNS-records maken bij Dreamhost voor Microsoft
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Dreamhost voor Microsoft.
ms.openlocfilehash: 2187cc155bc15e8482960d933d9136401ea29beb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629801"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a><span data-ttu-id="6820c-103">DNS-records maken bij Dreamhost voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="6820c-103">Create DNS records at Dreamhost for Microsoft</span></span>

 <span data-ttu-id="6820c-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="6820c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6820c-105">Als DreamHost uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Lync enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="6820c-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="6820c-106">Nadat u deze records bij DreamHost hebt toegevoegd, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="6820c-106">After you add these records at DreamHost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="6820c-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)</span><span class="sxs-lookup"><span data-stu-id="6820c-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6820c-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6820c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6820c-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="6820c-111">Add a TXT record for verification</span></span>
<span data-ttu-id="6820c-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6820c-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6820c-113">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="6820c-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="6820c-114">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="6820c-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6820c-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="6820c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6820c-p104">Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6820c-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="6820c-120">Selecteer op de pagina **Dashboard** **domeinen**en **beheer domeinen**.</span><span class="sxs-lookup"><span data-stu-id="6820c-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="6820c-122">Selecteer op de pagina **Domeinen beheren** in de sectie **Domein** de optie **DNS** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6820c-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="6820c-124">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="6820c-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6820c-125">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="6820c-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6820c-126">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="6820c-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6820c-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="6820c-127">**Name**</span></span>|<span data-ttu-id="6820c-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="6820c-128">**Type**</span></span>|<span data-ttu-id="6820c-129">**Value**</span><span class="sxs-lookup"><span data-stu-id="6820c-129">**Value**</span></span>|<span data-ttu-id="6820c-130">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="6820c-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6820c-131">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="6820c-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6820c-132">TXT</span><span class="sxs-lookup"><span data-stu-id="6820c-132">TXT</span></span>  <br/> |<span data-ttu-id="6820c-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6820c-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6820c-134">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="6820c-134">**Note:** This is an example.</span></span> <span data-ttu-id="6820c-135">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="6820c-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="6820c-136">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="6820c-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6820c-137">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="6820c-137">(This field is optional.)</span></span>  <br/> |
   
   ![Afbeelding van het te maken](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="6820c-139">Selecteer **Nu record toevoegen!**</span><span class="sxs-lookup"><span data-stu-id="6820c-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="6820c-141">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="6820c-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6820c-142">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="6820c-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="6820c-143">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="6820c-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6820c-144">Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="6820c-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6820c-145">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="6820c-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6820c-146">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="6820c-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6820c-147">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="6820c-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6820c-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6820c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6820c-151">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="6820c-151">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6820c-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6820c-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="6820c-153">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="6820c-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="6820c-p107">Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6820c-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="6820c-157">Selecteer op **de** dashboardpagina **E-mail**en vervolgens **Aangepast MX**.</span><span class="sxs-lookup"><span data-stu-id="6820c-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="6820c-159">Selecteer **bewerken** voor het domein dat u wilt bewerken in de sectie **E-mailbezorging** beheren in de kolom **Acties.**</span><span class="sxs-lookup"><span data-stu-id="6820c-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="6820c-161">Typ of kopieer en plak de volgende waarden uit de volgende tabel in het gebied **Custom MX Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="6820c-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="6820c-162">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="6820c-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6820c-163">(Als er andere bestaande MX-records zijn, markeert u deze records om te worden verwijderd.)</span><span class="sxs-lookup"><span data-stu-id="6820c-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="6820c-164">**MX-record (vereist)**</span><span class="sxs-lookup"><span data-stu-id="6820c-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="6820c-165">0  *\<domeinsleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6820c-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="6820c-166">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6820c-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="6820c-p108">De 0 is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  </span><span class="sxs-lookup"><span data-stu-id="6820c-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="6820c-169">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="6820c-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="6820c-170">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="6820c-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Afbeelding van het te maken dat u afbeelding van het huis hebt](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="6820c-172">Selecteer **Dit domein wijzigen om nu aangepaste MX-records te gebruiken!**</span><span class="sxs-lookup"><span data-stu-id="6820c-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="6820c-174">Als er andere bestaande MX-records zijn, verwijdert u elke record door deze te selecteren en vervolgens op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="6820c-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="6820c-176">Als u records hebt verwijderd, selecteert u **Nu uw aangepaste MX-records bijwerken!**</span><span class="sxs-lookup"><span data-stu-id="6820c-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6820c-178">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="6820c-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6820c-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6820c-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="6820c-180">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="6820c-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="6820c-p110">Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6820c-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="6820c-184">Selecteer op de pagina **Dashboard** **domeinen**en **beheer domeinen**.</span><span class="sxs-lookup"><span data-stu-id="6820c-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="6820c-186">Selecteer op de pagina **Domeinen beheren** in de sectie **Domein** de optie **DNS** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6820c-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="6820c-188">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="6820c-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="6820c-189">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="6820c-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6820c-190">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="6820c-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6820c-191">**Name**</span><span class="sxs-lookup"><span data-stu-id="6820c-191">**Name**</span></span>|<span data-ttu-id="6820c-192">**Type**</span><span class="sxs-lookup"><span data-stu-id="6820c-192">**Type**</span></span>|<span data-ttu-id="6820c-193">**Value**</span><span class="sxs-lookup"><span data-stu-id="6820c-193">**Value**</span></span>|<span data-ttu-id="6820c-194">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="6820c-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6820c-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6820c-195">autodiscover</span></span>  <br/> |<span data-ttu-id="6820c-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="6820c-196">CNAME</span></span>  <br/> |<span data-ttu-id="6820c-197">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6820c-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="6820c-198">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6820c-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6820c-199">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="6820c-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="6820c-200">sip</span><span class="sxs-lookup"><span data-stu-id="6820c-200">sip</span></span>  <br/> |<span data-ttu-id="6820c-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="6820c-201">CNAME</span></span>  <br/> |<span data-ttu-id="6820c-202">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6820c-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6820c-203">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6820c-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6820c-204">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="6820c-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="6820c-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6820c-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6820c-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="6820c-206">CNAME</span></span>  <br/> |<span data-ttu-id="6820c-207">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6820c-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6820c-208">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6820c-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6820c-209">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="6820c-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="6820c-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6820c-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6820c-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="6820c-211">CNAME</span></span>  <br/> |<span data-ttu-id="6820c-212">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="6820c-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="6820c-213">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6820c-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6820c-214">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="6820c-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="6820c-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6820c-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6820c-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="6820c-216">CNAME</span></span>  <br/> |<span data-ttu-id="6820c-217">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6820c-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="6820c-218">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6820c-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6820c-219">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="6820c-219">(This field is optional.)</span></span>  <br/> |
   
    ![Afbeelding van het te maken:Afbeelding van het te maken](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="6820c-221">Selecteer **Nu record toevoegen!**</span><span class="sxs-lookup"><span data-stu-id="6820c-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="6820c-223">Voeg met de voorgaande twee stappen en de waarden van de andere vijf rijen in de tabel elk van de andere vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="6820c-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6820c-224">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="6820c-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6820c-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6820c-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6820c-226">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="6820c-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6820c-227">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="6820c-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6820c-228">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6820c-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6820c-229">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="6820c-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="6820c-230">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="6820c-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="6820c-p112">Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6820c-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="6820c-234">Selecteer op de pagina **Dashboard** **domeinen**en **beheer domeinen**.</span><span class="sxs-lookup"><span data-stu-id="6820c-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="6820c-236">Selecteer op de pagina **Domeinen beheren** in de sectie **Domein** de optie **DNS** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6820c-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="6820c-238">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="6820c-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="6820c-239">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="6820c-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6820c-240">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="6820c-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6820c-241">**Name**</span><span class="sxs-lookup"><span data-stu-id="6820c-241">**Name**</span></span>|<span data-ttu-id="6820c-242">**Type**</span><span class="sxs-lookup"><span data-stu-id="6820c-242">**Type**</span></span>|<span data-ttu-id="6820c-243">**Value**</span><span class="sxs-lookup"><span data-stu-id="6820c-243">**Value**</span></span>|<span data-ttu-id="6820c-244">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="6820c-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6820c-245">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="6820c-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6820c-246">TXT</span><span class="sxs-lookup"><span data-stu-id="6820c-246">TXT</span></span>  <br/> |<span data-ttu-id="6820c-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6820c-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6820c-248">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="6820c-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="6820c-249">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="6820c-249">(This field is optional.)</span></span>  <br/> |
   
   ![Afbeelding van het te maken](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="6820c-251">Selecteer **Nu record toevoegen!**</span><span class="sxs-lookup"><span data-stu-id="6820c-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="6820c-253">Met de twee voorgaande stappen en de waarden uit de tweede rij in de tabel, moet u de andere SRV-record toevoegen.</span><span class="sxs-lookup"><span data-stu-id="6820c-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6820c-254">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="6820c-254">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="6820c-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6820c-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="6820c-256">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="6820c-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="6820c-p113">Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6820c-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="6820c-260">Selecteer op de pagina **Dashboard** **domeinen**en **beheer domeinen**.</span><span class="sxs-lookup"><span data-stu-id="6820c-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="6820c-262">Selecteer op de pagina **Domeinen beheren** in de sectie **Domein** de optie **DNS** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6820c-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="6820c-264">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="6820c-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="6820c-265">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="6820c-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="6820c-266">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="6820c-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6820c-267">**Name**</span><span class="sxs-lookup"><span data-stu-id="6820c-267">**Name**</span></span>|<span data-ttu-id="6820c-268">**Type**</span><span class="sxs-lookup"><span data-stu-id="6820c-268">**Type**</span></span>|<span data-ttu-id="6820c-269">**Value**</span><span class="sxs-lookup"><span data-stu-id="6820c-269">**Value**</span></span>|<span data-ttu-id="6820c-270">**Opmerking**</span><span class="sxs-lookup"><span data-stu-id="6820c-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6820c-271">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="6820c-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="6820c-272">SRV</span><span class="sxs-lookup"><span data-stu-id="6820c-272">SRV</span></span>  <br/> |<span data-ttu-id="6820c-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="6820c-273">100 1 443</span></span>  <br/> <span data-ttu-id="6820c-274">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6820c-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6820c-275">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6820c-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6820c-276">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="6820c-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="6820c-277">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="6820c-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="6820c-278">SRV</span><span class="sxs-lookup"><span data-stu-id="6820c-278">SRV</span></span>  <br/> |<span data-ttu-id="6820c-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="6820c-279">100 1 5061</span></span>  <br/> <span data-ttu-id="6820c-280">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6820c-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="6820c-281">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6820c-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="6820c-282">(Dit veld is optioneel.)</span><span class="sxs-lookup"><span data-stu-id="6820c-282">(This field is optional.)</span></span>  <br/> |
   
    ![Afbeelding van het te maken:Afbeelding van het te maken](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="6820c-284">Selecteer **Nu record toevoegen!**.</span><span class="sxs-lookup"><span data-stu-id="6820c-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="6820c-286">Met de twee voorgaande stappen en de waarden uit de tweede rij in de tabel, moet u de andere SRV-record toevoegen.</span><span class="sxs-lookup"><span data-stu-id="6820c-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="6820c-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6820c-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
