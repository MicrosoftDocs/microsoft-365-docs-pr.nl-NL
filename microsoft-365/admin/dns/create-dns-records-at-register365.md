---
title: DNS-records maken bij Register365 voor Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Register365 voor Microsoft.
ms.openlocfilehash: 08db53df7510de76c6c5c33d2047cba4203324d8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629261"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="381ea-103">DNS-records maken bij Register365 voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="381ea-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="381ea-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="381ea-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="381ea-105">Als Register365 uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="381ea-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="381ea-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="381ea-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="381ea-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="381ea-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="381ea-108">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="381ea-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="381ea-109">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="381ea-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="381ea-110">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="381ea-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="381ea-111">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="381ea-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="381ea-112">Nadat u deze records bij Microsoft hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="381ea-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="381ea-113">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="381ea-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="381ea-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="381ea-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="381ea-117">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="381ea-117">Add a TXT record for verification</span></span>
<span data-ttu-id="381ea-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="381ea-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="381ea-119">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="381ea-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="381ea-120">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="381ea-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="381ea-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="381ea-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="381ea-p104">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="381ea-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="381ea-126">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="381ea-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="381ea-127">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-127">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="381ea-129">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="381ea-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="381ea-130">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="381ea-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="381ea-131">(Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)</span><span class="sxs-lookup"><span data-stu-id="381ea-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="381ea-132">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="381ea-133">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="381ea-133">**Host name**</span></span>|<span data-ttu-id="381ea-134">**Type**</span><span class="sxs-lookup"><span data-stu-id="381ea-134">**Type**</span></span>|<span data-ttu-id="381ea-135">**Resultaat**</span><span class="sxs-lookup"><span data-stu-id="381ea-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="381ea-136">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="381ea-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="381ea-137">TXT</span><span class="sxs-lookup"><span data-stu-id="381ea-137">TXT</span></span>  <br/> |<span data-ttu-id="381ea-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="381ea-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="381ea-139">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="381ea-139">**Note:** This is an example.</span></span> <span data-ttu-id="381ea-140">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="381ea-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="381ea-141">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="381ea-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="381ea-143">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="381ea-143">Select **Save**.</span></span>
    
    <span data-ttu-id="381ea-144">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-144">(You may have to scroll down.)</span></span>
    
    ![Selecteer Opslaan](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="381ea-146">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="381ea-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="381ea-147">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="381ea-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="381ea-148">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="381ea-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="381ea-149">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="381ea-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="381ea-150">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="381ea-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="381ea-151">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="381ea-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="381ea-152">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="381ea-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="381ea-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="381ea-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="381ea-156">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="381ea-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="381ea-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="381ea-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="381ea-p107">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="381ea-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="381ea-161">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="381ea-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="381ea-162">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-162">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="381ea-164">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **Mail Exchange records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="381ea-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="381ea-165">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="381ea-166">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="381ea-166">**Host name**</span></span>|<span data-ttu-id="381ea-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="381ea-167">**Priority**</span></span>|<span data-ttu-id="381ea-168">**Resultaat**</span><span class="sxs-lookup"><span data-stu-id="381ea-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="381ea-169">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="381ea-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="381ea-170">1</span><span class="sxs-lookup"><span data-stu-id="381ea-170">1</span></span>  <br/> <span data-ttu-id="381ea-171">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="381ea-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="381ea-172">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="381ea-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="381ea-173">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="381ea-173">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="381ea-174">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="381ea-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="381ea-176">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="381ea-176">Select **Save**.</span></span>
    
    <span data-ttu-id="381ea-177">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-177">(You may have to scroll down.)</span></span>
    
    ![Selecteer Opslaan](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="381ea-179">Als er in de sectie **Mail exchange records** andere MX-records worden vermeld, verwijdert u elke record door deze te selecteren en vervolgens op het toetsenbord op de toets **Delete** te drukken.</span><span class="sxs-lookup"><span data-stu-id="381ea-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="381ea-181">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="381ea-181">Select **Save**.</span></span>
    
    <span data-ttu-id="381ea-182">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-182">(You may have to scroll down.)</span></span>
    
    ![Selecteer Opslaan](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="381ea-184">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="381ea-184">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="381ea-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="381ea-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="381ea-p109">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="381ea-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="381ea-189">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="381ea-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="381ea-190">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-190">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="381ea-192">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone** in de sectie **A-, CNAME, AAAA, TXT and NS Records** de waarden uit de volgende tabel in de vakken voor de nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="381ea-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="381ea-193">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="381ea-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="381ea-194">(Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)</span><span class="sxs-lookup"><span data-stu-id="381ea-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="381ea-195">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="381ea-196">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="381ea-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="381ea-197">\*\*\*\*Type\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="381ea-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="381ea-198">\*\*\*\*Result\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="381ea-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="381ea-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="381ea-199">autodiscover</span></span>  <br/> |<span data-ttu-id="381ea-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="381ea-200">CNAME</span></span>  <br/> |<span data-ttu-id="381ea-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="381ea-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="381ea-202">sip</span><span class="sxs-lookup"><span data-stu-id="381ea-202">sip</span></span>  <br/> |<span data-ttu-id="381ea-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="381ea-203">CNAME</span></span>  <br/> |<span data-ttu-id="381ea-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="381ea-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="381ea-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="381ea-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="381ea-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="381ea-206">CNAME</span></span>  <br/> |<span data-ttu-id="381ea-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="381ea-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="381ea-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="381ea-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="381ea-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="381ea-209">CNAME</span></span>  <br/> |<span data-ttu-id="381ea-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="381ea-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="381ea-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="381ea-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="381ea-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="381ea-212">CNAME</span></span>  <br/> |<span data-ttu-id="381ea-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="381ea-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="381ea-215">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="381ea-215">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="381ea-217">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="381ea-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="381ea-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="381ea-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="381ea-219">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="381ea-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="381ea-220">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="381ea-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="381ea-221">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="381ea-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="381ea-222">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="381ea-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="381ea-p111">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="381ea-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="381ea-226">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="381ea-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="381ea-227">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-227">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="381ea-229">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="381ea-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="381ea-230">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="381ea-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="381ea-231">(Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)</span><span class="sxs-lookup"><span data-stu-id="381ea-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="381ea-232">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="381ea-233">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="381ea-233">**Host name**</span></span>|<span data-ttu-id="381ea-234">**Type**</span><span class="sxs-lookup"><span data-stu-id="381ea-234">**Type**</span></span>|<span data-ttu-id="381ea-235">**Resultaat**</span><span class="sxs-lookup"><span data-stu-id="381ea-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="381ea-236">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="381ea-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="381ea-237">TXT</span><span class="sxs-lookup"><span data-stu-id="381ea-237">TXT</span></span>  <br/> |<span data-ttu-id="381ea-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="381ea-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="381ea-239">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="381ea-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="381ea-241">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="381ea-241">Select **Save**.</span></span>
    
    <span data-ttu-id="381ea-242">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-242">(You may have to scroll down.)</span></span>
    
    ![Selecteer Opslaan](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="381ea-244">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="381ea-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="381ea-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="381ea-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="381ea-p112">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="381ea-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="381ea-249">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="381ea-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="381ea-250">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-250">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="381ea-252">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone** in de sectie **Service records** de waarden uit de volgende tabel in de vakken voor de nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="381ea-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="381ea-253">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="381ea-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="381ea-254">**Name**</span></span>|<span data-ttu-id="381ea-255">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="381ea-255">**Priority**</span></span>|<span data-ttu-id="381ea-256">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="381ea-256">**Weight**</span></span>|<span data-ttu-id="381ea-257">**Poort**</span><span class="sxs-lookup"><span data-stu-id="381ea-257">**Port**</span></span>|<span data-ttu-id="381ea-258">**Result**</span><span class="sxs-lookup"><span data-stu-id="381ea-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="381ea-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="381ea-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="381ea-260">100</span><span class="sxs-lookup"><span data-stu-id="381ea-260">100</span></span>  <br/> |<span data-ttu-id="381ea-261">1</span><span class="sxs-lookup"><span data-stu-id="381ea-261">1</span></span>  <br/> |<span data-ttu-id="381ea-262">443</span><span class="sxs-lookup"><span data-stu-id="381ea-262">443</span></span>  <br/> |<span data-ttu-id="381ea-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="381ea-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="381ea-264">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="381ea-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="381ea-265">100</span><span class="sxs-lookup"><span data-stu-id="381ea-265">100</span></span>  <br/> |<span data-ttu-id="381ea-266">1</span><span class="sxs-lookup"><span data-stu-id="381ea-266">1</span></span>  <br/> |<span data-ttu-id="381ea-267">5061</span><span class="sxs-lookup"><span data-stu-id="381ea-267">5061</span></span>  <br/> |<span data-ttu-id="381ea-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="381ea-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Waarden invoeren in de sectie Servicerecords](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="381ea-270">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="381ea-270">Select **Save**.</span></span>
    
    <span data-ttu-id="381ea-271">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="381ea-271">(You may have to scroll down.)</span></span>
    
    ![Selecteer Opslaan](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="381ea-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="381ea-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
