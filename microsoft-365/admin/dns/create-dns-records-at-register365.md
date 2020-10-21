---
title: DNS-records bij Register365 maken voor Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Register365 voor Microsoft.
ms.openlocfilehash: a4c66a4c16960332150a51779207defb00df3044
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645765"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="fb935-103">DNS-records bij Register365 maken voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb935-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="fb935-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="fb935-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fb935-105">Als Register365 uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fb935-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="fb935-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="fb935-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="fb935-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="fb935-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="fb935-108">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="fb935-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="fb935-109">De zes CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb935-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="fb935-110">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="fb935-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="fb935-111">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb935-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="fb935-112">Nadat u deze records bij Microsoft hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="fb935-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="fb935-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fb935-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fb935-116">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="fb935-116">Add a TXT record for verification</span></span>
<span data-ttu-id="fb935-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="fb935-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="fb935-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="fb935-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb935-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fb935-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="fb935-p104">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fb935-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="fb935-125">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fb935-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="fb935-126">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-126">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="fb935-128">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="fb935-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="fb935-129">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="fb935-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="fb935-130">(Als u een rij wilt toevoegen, selecteert u **add a/CNAME-records (+)**.)</span><span class="sxs-lookup"><span data-stu-id="fb935-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="fb935-131">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="fb935-132">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="fb935-132">**Host name**</span></span>|<span data-ttu-id="fb935-133">**Type**</span><span class="sxs-lookup"><span data-stu-id="fb935-133">**Type**</span></span>|<span data-ttu-id="fb935-134">**Result**</span><span class="sxs-lookup"><span data-stu-id="fb935-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fb935-135">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="fb935-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="fb935-136">TXT</span><span class="sxs-lookup"><span data-stu-id="fb935-136">TXT</span></span>  <br/> |<span data-ttu-id="fb935-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fb935-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fb935-138">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="fb935-138">**Note:** This is an example.</span></span> <span data-ttu-id="fb935-139">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="fb935-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="fb935-140">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="fb935-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="fb935-142">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fb935-142">Select **Save**.</span></span>
    
    <span data-ttu-id="fb935-143">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-143">(You may have to scroll down.)</span></span>
    
    ![Selecteer opslaan.](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="fb935-145">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="fb935-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fb935-146">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="fb935-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="fb935-147">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="fb935-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fb935-148">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="fb935-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="fb935-149">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="fb935-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="fb935-150">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="fb935-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="fb935-151">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="fb935-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="fb935-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fb935-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="fb935-155">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="fb935-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="fb935-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="fb935-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="fb935-p107">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fb935-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="fb935-160">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fb935-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="fb935-161">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-161">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="fb935-163">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **Mail Exchange records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="fb935-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="fb935-164">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="fb935-165">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="fb935-165">**Host name**</span></span>|<span data-ttu-id="fb935-166">**Priority**</span><span class="sxs-lookup"><span data-stu-id="fb935-166">**Priority**</span></span>|<span data-ttu-id="fb935-167">**Result**</span><span class="sxs-lookup"><span data-stu-id="fb935-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fb935-168">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="fb935-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="fb935-169">1</span><span class="sxs-lookup"><span data-stu-id="fb935-169">1</span></span>  <br/> <span data-ttu-id="fb935-170">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="fb935-170">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="fb935-171">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fb935-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="fb935-172">**Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="fb935-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="fb935-173">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="fb935-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="fb935-175">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fb935-175">Select **Save**.</span></span>
    
    <span data-ttu-id="fb935-176">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-176">(You may have to scroll down.)</span></span>
    
    ![Selecteer opslaan.](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="fb935-178">Als er in de sectie **Mail exchange records** andere MX-records worden vermeld, verwijdert u elke record door deze te selecteren en vervolgens op het toetsenbord op de toets **Delete** te drukken.</span><span class="sxs-lookup"><span data-stu-id="fb935-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="fb935-180">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fb935-180">Select **Save**.</span></span>
    
    <span data-ttu-id="fb935-181">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-181">(You may have to scroll down.)</span></span>
    
    ![Selecteer opslaan.](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="fb935-183">De zes CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb935-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="fb935-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="fb935-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="fb935-p109">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fb935-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="fb935-188">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fb935-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="fb935-189">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-189">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="fb935-191">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone** in de sectie **A-, CNAME, AAAA, TXT and NS Records** de waarden uit de volgende tabel in de vakken voor de nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="fb935-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="fb935-192">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="fb935-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="fb935-193">(Als u een rij wilt toevoegen, selecteert u **add a/CNAME-records (+)**.)</span><span class="sxs-lookup"><span data-stu-id="fb935-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="fb935-194">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="fb935-195">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fb935-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="fb935-196">\*\*\*\*Type\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fb935-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="fb935-197">\*\*\*\*Result\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fb935-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fb935-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="fb935-198">autodiscover</span></span>  <br/> |<span data-ttu-id="fb935-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="fb935-199">CNAME</span></span>  <br/> |<span data-ttu-id="fb935-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fb935-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="fb935-201">sip</span><span class="sxs-lookup"><span data-stu-id="fb935-201">sip</span></span>  <br/> |<span data-ttu-id="fb935-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="fb935-202">CNAME</span></span>  <br/> |<span data-ttu-id="fb935-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fb935-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fb935-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fb935-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="fb935-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="fb935-205">CNAME</span></span>  <br/> |<span data-ttu-id="fb935-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fb935-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fb935-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="fb935-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="fb935-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="fb935-208">CNAME</span></span>  <br/> |<span data-ttu-id="fb935-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="fb935-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="fb935-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="fb935-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="fb935-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="fb935-211">CNAME</span></span>  <br/> |<span data-ttu-id="fb935-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fb935-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="fb935-214">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fb935-214">Select **Save**.</span></span>
    
    ![Selecteer opslaan.](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="fb935-216">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="fb935-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="fb935-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="fb935-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb935-218">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="fb935-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="fb935-219">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="fb935-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="fb935-220">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fb935-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="fb935-221">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="fb935-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="fb935-p111">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fb935-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="fb935-225">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fb935-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="fb935-226">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-226">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="fb935-228">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="fb935-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="fb935-229">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="fb935-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="fb935-230">(Als u een rij wilt toevoegen, selecteert u **add a/CNAME-records (+)**.)</span><span class="sxs-lookup"><span data-stu-id="fb935-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="fb935-231">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="fb935-232">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="fb935-232">**Host name**</span></span>|<span data-ttu-id="fb935-233">**Type**</span><span class="sxs-lookup"><span data-stu-id="fb935-233">**Type**</span></span>|<span data-ttu-id="fb935-234">**Result**</span><span class="sxs-lookup"><span data-stu-id="fb935-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fb935-235">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="fb935-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="fb935-236">TXT</span><span class="sxs-lookup"><span data-stu-id="fb935-236">TXT</span></span>  <br/> |<span data-ttu-id="fb935-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="fb935-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="fb935-238">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="fb935-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="fb935-240">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fb935-240">Select **Save**.</span></span>
    
    <span data-ttu-id="fb935-241">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-241">(You may have to scroll down.)</span></span>
    
    ![Selecteer opslaan.](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="fb935-243">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb935-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="fb935-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="fb935-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="fb935-p112">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fb935-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="fb935-248">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fb935-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="fb935-249">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-249">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="fb935-251">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone** in de sectie **Service records** de waarden uit de volgende tabel in de vakken voor de nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="fb935-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="fb935-252">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="fb935-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="fb935-253">**Name**</span></span>|<span data-ttu-id="fb935-254">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="fb935-254">**Priority**</span></span>|<span data-ttu-id="fb935-255">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="fb935-255">**Weight**</span></span>|<span data-ttu-id="fb935-256">**Poort**</span><span class="sxs-lookup"><span data-stu-id="fb935-256">**Port**</span></span>|<span data-ttu-id="fb935-257">**Result**</span><span class="sxs-lookup"><span data-stu-id="fb935-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fb935-258">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="fb935-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="fb935-259">100</span><span class="sxs-lookup"><span data-stu-id="fb935-259">100</span></span>  <br/> |<span data-ttu-id="fb935-260">1</span><span class="sxs-lookup"><span data-stu-id="fb935-260">1</span></span>  <br/> |<span data-ttu-id="fb935-261">443</span><span class="sxs-lookup"><span data-stu-id="fb935-261">443</span></span>  <br/> |<span data-ttu-id="fb935-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fb935-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fb935-263">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="fb935-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="fb935-264">100</span><span class="sxs-lookup"><span data-stu-id="fb935-264">100</span></span>  <br/> |<span data-ttu-id="fb935-265">1</span><span class="sxs-lookup"><span data-stu-id="fb935-265">1</span></span>  <br/> |<span data-ttu-id="fb935-266">5061</span><span class="sxs-lookup"><span data-stu-id="fb935-266">5061</span></span>  <br/> |<span data-ttu-id="fb935-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fb935-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Waarden opgeven in de sectie service records](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="fb935-269">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fb935-269">Select **Save**.</span></span>
    
    <span data-ttu-id="fb935-270">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="fb935-270">(You may have to scroll down.)</span></span>
    
    ![Selecteer opslaan.](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="fb935-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fb935-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
