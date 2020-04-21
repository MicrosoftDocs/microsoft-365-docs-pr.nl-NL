---
title: DNS-records maken op Names.co.uk voor Microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op Names.co.uk voor Microsoft.
ms.openlocfilehash: 2552017e06001c0b28605558b823fdb4c670ef8c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629321"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="ae7f3-103">DNS-records maken op Names.co.uk voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae7f3-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="ae7f3-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ae7f3-105">Als Names.co.uk uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="ae7f3-106">Nadat u deze records hebt toegevoegd aan Names.co.uk, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="ae7f3-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ae7f3-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ae7f3-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ae7f3-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="ae7f3-111">Add a TXT record for verification</span></span>
<span data-ttu-id="ae7f3-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ae7f3-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ae7f3-113">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="ae7f3-114">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae7f3-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ae7f3-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ae7f3-120">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ae7f3-121">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-121">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ae7f3-123">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A, CNAME, AAAA, TXT and NS records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ae7f3-124">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="ae7f3-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ae7f3-125">(Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ae7f3-126">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="ae7f3-127">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-127">**Host name**</span></span>|<span data-ttu-id="ae7f3-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-128">**Type**</span></span>|<span data-ttu-id="ae7f3-129">**Resultaat**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ae7f3-130">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ae7f3-131">TXT</span><span class="sxs-lookup"><span data-stu-id="ae7f3-131">TXT</span></span>  <br/> |<span data-ttu-id="ae7f3-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ae7f3-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ae7f3-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-133">**Note:** This is an example.</span></span> <span data-ttu-id="ae7f3-134">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="ae7f3-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="ae7f3-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![Afbeelding van het te maken van de afbeelding van de knop Verifiëren-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="ae7f3-137">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-137">Select **Save**.</span></span>
    
    <span data-ttu-id="ae7f3-138">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-138">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken van de afbeelding van de knop Verifiëren-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="ae7f3-140">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ae7f3-141">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ae7f3-142">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ae7f3-143">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ae7f3-144">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ae7f3-145">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ae7f3-146">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ae7f3-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ae7f3-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ae7f3-150">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="ae7f3-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ae7f3-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ae7f3-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="ae7f3-p107">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ae7f3-155">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ae7f3-156">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-156">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ae7f3-158">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **Mail Exchange records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ae7f3-159">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ae7f3-160">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-160">**Host name**</span></span>|<span data-ttu-id="ae7f3-161">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-161">**Priority**</span></span>|<span data-ttu-id="ae7f3-162">**Resultaat**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ae7f3-163">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ae7f3-164">1</span><span class="sxs-lookup"><span data-stu-id="ae7f3-164">1</span></span>  <br/> <span data-ttu-id="ae7f3-165">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="ae7f3-166">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ae7f3-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="ae7f3-167">> [!NOTE]> Uw \* \<domeinsleutel\> \* ophalen van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="ae7f3-168">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="ae7f3-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="ae7f3-170">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-170">Select **Save**.</span></span>
    
    <span data-ttu-id="ae7f3-171">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-171">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="ae7f3-173">Als er in de sectie **Mail Exchange records** andere MX-records worden vermeld, verwijdert u elke record door deze te selecteren en vervolgens op het toetsenbord op de toets **Delete** te drukken.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="ae7f3-175">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-175">Select **Save**.</span></span>
    
    <span data-ttu-id="ae7f3-176">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-176">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ae7f3-178">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae7f3-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ae7f3-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ae7f3-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="ae7f3-p109">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ae7f3-183">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ae7f3-184">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-184">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ae7f3-186">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A, CNAME, AAAA, TXT and NS records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ae7f3-187">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="ae7f3-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ae7f3-188">(Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ae7f3-189">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ae7f3-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-190">**Host Name**</span></span>|<span data-ttu-id="ae7f3-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-191">**Type**</span></span>|<span data-ttu-id="ae7f3-192">**Result**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ae7f3-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ae7f3-193">autodiscover</span></span>  <br/> |<span data-ttu-id="ae7f3-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="ae7f3-194">CNAME</span></span>  <br/> |<span data-ttu-id="ae7f3-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ae7f3-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="ae7f3-196">sip</span><span class="sxs-lookup"><span data-stu-id="ae7f3-196">sip</span></span>  <br/> |<span data-ttu-id="ae7f3-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="ae7f3-197">CNAME</span></span>  <br/> |<span data-ttu-id="ae7f3-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ae7f3-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ae7f3-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ae7f3-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ae7f3-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="ae7f3-200">CNAME</span></span>  <br/> |<span data-ttu-id="ae7f3-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ae7f3-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ae7f3-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ae7f3-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ae7f3-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="ae7f3-203">CNAME</span></span>  <br/> |<span data-ttu-id="ae7f3-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ae7f3-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="ae7f3-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ae7f3-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ae7f3-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="ae7f3-206">CNAME</span></span>  <br/> |<span data-ttu-id="ae7f3-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ae7f3-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Afbeelding van het te maken van afbeelding van het](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="ae7f3-209">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-209">Select **Save**.</span></span>
    
    ![Afbeelding van het te maken van afbeelding van het](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ae7f3-211">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="ae7f3-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ae7f3-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ae7f3-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae7f3-213">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ae7f3-214">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ae7f3-215">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-215">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ae7f3-216">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-216">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="ae7f3-p111">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ae7f3-220">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ae7f3-221">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-221">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ae7f3-223">Selecteer op de pagina **DNS-zones op account** in de kolom **Domeinnaam** de naam van het domein dat u bijwerkt.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![Afbeelding van het te maken van de afbeelding van het](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="ae7f3-225">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ae7f3-226">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="ae7f3-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="ae7f3-227">(Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="ae7f3-228">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ae7f3-229">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-229">**Host name**</span></span>|<span data-ttu-id="ae7f3-230">**Type**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-230">**Type**</span></span>|<span data-ttu-id="ae7f3-231">**Resultaat**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ae7f3-232">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ae7f3-233">TXT</span><span class="sxs-lookup"><span data-stu-id="ae7f3-233">TXT</span></span>  <br/> |<span data-ttu-id="ae7f3-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ae7f3-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ae7f3-235">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![Afbeelding van het te maken:Bp-afbeelding](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="ae7f3-237">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-237">Select **Save**.</span></span>
    
    <span data-ttu-id="ae7f3-238">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-238">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken:Bp-afbeelding](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ae7f3-240">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae7f3-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ae7f3-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ae7f3-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="ae7f3-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="ae7f3-245">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="ae7f3-246">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-246">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="ae7f3-248">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **Service records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ae7f3-249">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="ae7f3-250">**Name**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-250">**Name**</span></span>|<span data-ttu-id="ae7f3-251">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-251">**Priority**</span></span>|<span data-ttu-id="ae7f3-252">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-252">**Weight**</span></span>|<span data-ttu-id="ae7f3-253">**Poort**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-253">**Port**</span></span>|<span data-ttu-id="ae7f3-254">**Result**</span><span class="sxs-lookup"><span data-stu-id="ae7f3-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ae7f3-255">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="ae7f3-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="ae7f3-256">100</span><span class="sxs-lookup"><span data-stu-id="ae7f3-256">100</span></span>  <br/> |<span data-ttu-id="ae7f3-257">1</span><span class="sxs-lookup"><span data-stu-id="ae7f3-257">1</span></span>  <br/> |<span data-ttu-id="ae7f3-258">443</span><span class="sxs-lookup"><span data-stu-id="ae7f3-258">443</span></span>  <br/> |<span data-ttu-id="ae7f3-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ae7f3-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ae7f3-260">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="ae7f3-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="ae7f3-261">100</span><span class="sxs-lookup"><span data-stu-id="ae7f3-261">100</span></span>  <br/> |<span data-ttu-id="ae7f3-262">1</span><span class="sxs-lookup"><span data-stu-id="ae7f3-262">1</span></span>  <br/> |<span data-ttu-id="ae7f3-263">5061</span><span class="sxs-lookup"><span data-stu-id="ae7f3-263">5061</span></span>  <br/> |<span data-ttu-id="ae7f3-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ae7f3-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Afbeelding van het te maken:Bp-afbeelding](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="ae7f3-266">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ae7f3-266">Select **Save**.</span></span>
    
    <span data-ttu-id="ae7f3-267">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ae7f3-267">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken:Bp-afbeelding-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="ae7f3-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ae7f3-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
