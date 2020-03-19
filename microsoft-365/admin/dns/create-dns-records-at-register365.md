---
title: DNS-records bij Register365 maken voor Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij Register365 voor Office 365.
ms.openlocfilehash: 7f9398e14ea5280948829b263d4cd66d61fab682
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809245"
---
# <a name="create-dns-records-at-register365-for-office-365"></a><span data-ttu-id="b1c53-103">DNS-records bij Register365 maken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b1c53-103">Create DNS records at Register365 for Office 365</span></span>

 <span data-ttu-id="b1c53-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="b1c53-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b1c53-105">Als Register365 uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b1c53-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="b1c53-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="b1c53-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="b1c53-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="b1c53-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="b1c53-108">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="b1c53-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="b1c53-109">De zes CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="b1c53-109">Add the six CNAME records that are required for Office 365</span></span>](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="b1c53-110">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="b1c53-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="b1c53-111">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="b1c53-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="b1c53-112">Nadat u deze records bij Office 365 hebt toegevoegd, wordt uw domein ingesteld voor de Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="b1c53-112">After you add these records at Office 365, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="b1c53-113">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1c53-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b1c53-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b1c53-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b1c53-117">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="b1c53-117">Add a TXT record for verification</span></span>
<span data-ttu-id="b1c53-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b1c53-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b1c53-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="b1c53-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b1c53-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b1c53-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b1c53-p104">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="b1c53-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="b1c53-126">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="b1c53-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="b1c53-127">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-127">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="b1c53-129">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="b1c53-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b1c53-130">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="b1c53-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="b1c53-131">(Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS (+)** toevoegen .)</span><span class="sxs-lookup"><span data-stu-id="b1c53-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="b1c53-132">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="b1c53-133">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="b1c53-133">**Host name**</span></span>|<span data-ttu-id="b1c53-134">**Type**</span><span class="sxs-lookup"><span data-stu-id="b1c53-134">**Type**</span></span>|<span data-ttu-id="b1c53-135">**Resultaat**</span><span class="sxs-lookup"><span data-stu-id="b1c53-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b1c53-136">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b1c53-137">TXT</span><span class="sxs-lookup"><span data-stu-id="b1c53-137">TXT</span></span>  <br/> |<span data-ttu-id="b1c53-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b1c53-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b1c53-p105">**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="b1c53-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="b1c53-143">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b1c53-143">Select **Save**.</span></span>
    
    <span data-ttu-id="b1c53-144">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-144">(You may have to scroll down.)</span></span>
    
    ![Opslaan selecteren](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="b1c53-146">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="b1c53-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b1c53-147">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="b1c53-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b1c53-148">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="b1c53-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b1c53-149">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="b1c53-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b1c53-150">Selecteer op de pagina **Domeinen** het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="b1c53-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b1c53-151">Selecteer op de pagina **Setup** de optie **Startsetup**.</span><span class="sxs-lookup"><span data-stu-id="b1c53-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b1c53-152">Selecteer op de pagina **Domein verifiëren** de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="b1c53-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b1c53-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b1c53-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="b1c53-156">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="b1c53-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="b1c53-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b1c53-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b1c53-p107">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="b1c53-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="b1c53-161">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="b1c53-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="b1c53-162">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-162">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="b1c53-164">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **Mail Exchange records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="b1c53-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b1c53-165">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="b1c53-166">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="b1c53-166">**Host name**</span></span>|<span data-ttu-id="b1c53-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b1c53-167">**Priority**</span></span>|<span data-ttu-id="b1c53-168">**Resultaat**</span><span class="sxs-lookup"><span data-stu-id="b1c53-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b1c53-169">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b1c53-170">1</span><span class="sxs-lookup"><span data-stu-id="b1c53-170">1</span></span>  <br/> <span data-ttu-id="b1c53-171">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="b1c53-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="b1c53-172">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b1c53-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b1c53-173">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="b1c53-173">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="b1c53-174">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="b1c53-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="b1c53-176">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b1c53-176">Select **Save**.</span></span>
    
    <span data-ttu-id="b1c53-177">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-177">(You may have to scroll down.)</span></span>
    
    ![Opslaan selecteren](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="b1c53-179">Als er in de sectie **Mail exchange records** andere MX-records worden vermeld, verwijdert u elke record door deze te selecteren en vervolgens op het toetsenbord op de toets **Delete** te drukken.</span><span class="sxs-lookup"><span data-stu-id="b1c53-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="b1c53-181">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b1c53-181">Select **Save**.</span></span>
    
    <span data-ttu-id="b1c53-182">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-182">(You may have to scroll down.)</span></span>
    
    ![Opslaan selecteren](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="b1c53-184">De zes CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="b1c53-184">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="b1c53-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b1c53-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b1c53-p109">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="b1c53-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="b1c53-189">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="b1c53-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="b1c53-190">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-190">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="b1c53-192">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone** in de sectie **A-, CNAME, AAAA, TXT and NS Records** de waarden uit de volgende tabel in de vakken voor de nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="b1c53-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b1c53-193">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="b1c53-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="b1c53-194">(Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS (+)** toevoegen .)</span><span class="sxs-lookup"><span data-stu-id="b1c53-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="b1c53-195">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="b1c53-196">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b1c53-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="b1c53-197">\*\*\*\*Type\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b1c53-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="b1c53-198">\*\*\*\*Result\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b1c53-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b1c53-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b1c53-199">autodiscover</span></span>  <br/> |<span data-ttu-id="b1c53-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="b1c53-200">CNAME</span></span>  <br/> |<span data-ttu-id="b1c53-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b1c53-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="b1c53-202">sip</span><span class="sxs-lookup"><span data-stu-id="b1c53-202">sip</span></span>  <br/> |<span data-ttu-id="b1c53-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="b1c53-203">CNAME</span></span>  <br/> |<span data-ttu-id="b1c53-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b1c53-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b1c53-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b1c53-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b1c53-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="b1c53-206">CNAME</span></span>  <br/> |<span data-ttu-id="b1c53-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b1c53-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b1c53-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b1c53-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b1c53-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="b1c53-209">CNAME</span></span>  <br/> |<span data-ttu-id="b1c53-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b1c53-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="b1c53-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b1c53-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b1c53-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="b1c53-212">CNAME</span></span>  <br/> |<span data-ttu-id="b1c53-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b1c53-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="b1c53-215">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b1c53-215">Select **Save**.</span></span>
    
    ![Opslaan selecteren](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b1c53-217">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="b1c53-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b1c53-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b1c53-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1c53-219">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="b1c53-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b1c53-220">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="b1c53-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b1c53-221">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="b1c53-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="b1c53-222">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="b1c53-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="b1c53-p111">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="b1c53-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="b1c53-226">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="b1c53-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="b1c53-227">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-227">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="b1c53-229">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="b1c53-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b1c53-230">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="b1c53-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="b1c53-231">(Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS (+)** toevoegen .)</span><span class="sxs-lookup"><span data-stu-id="b1c53-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="b1c53-232">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="b1c53-233">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="b1c53-233">**Host name**</span></span>|<span data-ttu-id="b1c53-234">**Type**</span><span class="sxs-lookup"><span data-stu-id="b1c53-234">**Type**</span></span>|<span data-ttu-id="b1c53-235">**Resultaat**</span><span class="sxs-lookup"><span data-stu-id="b1c53-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b1c53-236">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b1c53-237">TXT</span><span class="sxs-lookup"><span data-stu-id="b1c53-237">TXT</span></span>  <br/> |<span data-ttu-id="b1c53-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b1c53-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="b1c53-239">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="b1c53-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="b1c53-241">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b1c53-241">Select **Save**.</span></span>
    
    <span data-ttu-id="b1c53-242">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-242">(You may have to scroll down.)</span></span>
    
    ![Opslaan selecteren](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="b1c53-244">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="b1c53-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="b1c53-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b1c53-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="b1c53-p112">U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="b1c53-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="b1c53-249">Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="b1c53-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="b1c53-250">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-250">(You may have to scroll down.)</span></span>
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="b1c53-252">Typ of kopieer en plak op de pagina **Add/Modify DNS Zone** in de sectie **Service records** de waarden uit de volgende tabel in de vakken voor de nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="b1c53-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b1c53-253">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="b1c53-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="b1c53-254">**Name**</span></span>|<span data-ttu-id="b1c53-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b1c53-255">**Priority**</span></span>|<span data-ttu-id="b1c53-256">**Weight**</span><span class="sxs-lookup"><span data-stu-id="b1c53-256">**Weight**</span></span>|<span data-ttu-id="b1c53-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="b1c53-257">**Port**</span></span>|<span data-ttu-id="b1c53-258">**Result**</span><span class="sxs-lookup"><span data-stu-id="b1c53-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b1c53-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="b1c53-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="b1c53-260">100</span><span class="sxs-lookup"><span data-stu-id="b1c53-260">100</span></span>  <br/> |<span data-ttu-id="b1c53-261">1</span><span class="sxs-lookup"><span data-stu-id="b1c53-261">1</span></span>  <br/> |<span data-ttu-id="b1c53-262">443</span><span class="sxs-lookup"><span data-stu-id="b1c53-262">443</span></span>  <br/> |<span data-ttu-id="b1c53-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b1c53-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b1c53-264">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="b1c53-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="b1c53-265">100</span><span class="sxs-lookup"><span data-stu-id="b1c53-265">100</span></span>  <br/> |<span data-ttu-id="b1c53-266">1</span><span class="sxs-lookup"><span data-stu-id="b1c53-266">1</span></span>  <br/> |<span data-ttu-id="b1c53-267">5061</span><span class="sxs-lookup"><span data-stu-id="b1c53-267">5061</span></span>  <br/> |<span data-ttu-id="b1c53-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b1c53-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Waarden invoeren in de sectie Servicerecords](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="b1c53-270">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b1c53-270">Select **Save**.</span></span>
    
    <span data-ttu-id="b1c53-271">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="b1c53-271">(You may have to scroll down.)</span></span>
    
    ![Opslaan selecteren](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="b1c53-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b1c53-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
