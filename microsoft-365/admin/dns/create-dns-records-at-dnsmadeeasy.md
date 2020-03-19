---
title: DNS-records bij DNSMadeEasy maken voor Office 365
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij DNSMadeEasy voor Office 365.
ms.openlocfilehash: 82244d216652b1957aefc3b81acd881ea4b32393
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42811746"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a><span data-ttu-id="5bdf1-103">DNS-records bij DNSMadeEasy maken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="5bdf1-103">Create DNS records at DNSMadeEasy for Office 365</span></span>

 <span data-ttu-id="5bdf1-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5bdf1-105">Als DNSMadeEasy uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5bdf1-106">Nadat u deze records bij DNSMadeEasy hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="5bdf1-107">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5bdf1-p101">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5bdf1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5bdf1-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="5bdf1-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5bdf1-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5bdf1-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5bdf1-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5bdf1-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5bdf1-117">Voor DNSMadeEasy-accounts is het domein dat u hebt toegevoegd, gekocht bij een afzonderlijke domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="5bdf1-118">DNSMadeEasy biedt geen domeinregistratieservices aan.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="5bdf1-119">Uw vermogen om in te loggen bij DNSMadeEasy en de DNS-record te maken is voldoende bewijs van eigendom.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="5bdf1-120">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="5bdf1-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="5bdf1-121">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5bdf1-122">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5bdf1-123">Selecteer op de pagina **Beheerde DNS** in het **+** gebied **TXT Records** het besturingselement ( Toevoegen van **nieuw).**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="5bdf1-124">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5bdf1-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="5bdf1-125">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add TXT Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="5bdf1-126">**Naam**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-126">**Name**</span></span> <br/> |<span data-ttu-id="5bdf1-127">**Value**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-127">**Value**</span></span> <br/> |<span data-ttu-id="5bdf1-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="5bdf1-129">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="5bdf1-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5bdf1-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5bdf1-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5bdf1-131">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-131">**Note:** This is an example.</span></span> <span data-ttu-id="5bdf1-132">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="5bdf1-133">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="5bdf1-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5bdf1-134">1800</span><span class="sxs-lookup"><span data-stu-id="5bdf1-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="5bdf1-135">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="5bdf1-136">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5bdf1-137">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5bdf1-138">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-138">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5bdf1-139">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5bdf1-140">Selecteer op de pagina **Domeinen** het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5bdf1-141">Selecteer op de pagina **Setup** de optie **Startsetup**.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5bdf1-142">Selecteer op de pagina **Domein verifiëren** de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5bdf1-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5bdf1-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5bdf1-146">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="5bdf1-146">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5bdf1-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5bdf1-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5bdf1-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5bdf1-150">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="5bdf1-151">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET AFBEELDING VAN DNSMadeEasy-BP-configureren-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="5bdf1-153">Selecteer op de pagina **Beheerde DNS** in het gebied **MX Records** het besturingselement **(+) (Nieuw** **toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5bdf1-154">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5bdf1-154">(You may have to scroll down.)</span></span>
    
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET TWEE](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="5bdf1-156">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add MX Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5bdf1-157">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5bdf1-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5bdf1-158">**Naam**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-158">**Name**</span></span>|<span data-ttu-id="5bdf1-159">**Server**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-159">**Server**</span></span>|<span data-ttu-id="5bdf1-160">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-160">**MX Level**</span></span>|<span data-ttu-id="5bdf1-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5bdf1-162">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="5bdf1-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="5bdf1-163">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5bdf1-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5bdf1-164">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="5bdf1-165">**Let op:** Haal \<uw domeinsleutel\> uit uw Office 365-account. *domain-key*</span><span class="sxs-lookup"><span data-stu-id="5bdf1-165">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="5bdf1-166">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="5bdf1-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5bdf1-167">10</span><span class="sxs-lookup"><span data-stu-id="5bdf1-167">10</span></span>  <br/> <span data-ttu-id="5bdf1-168">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="5bdf1-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="5bdf1-169">1800</span><span class="sxs-lookup"><span data-stu-id="5bdf1-169">1800</span></span>  <br/> |
   
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET TWEE](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="5bdf1-171">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-171">Select **Submit**.</span></span>
    
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET TWEE-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="5bdf1-173">Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u deze door elk record te selecteren.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![AFBEELDING VAN HET-AFBEELDING VAN AFBEELDING 2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="5bdf1-175">Wanneer alle records zijn geselecteerd, selecteert u **Verwijderen geselecteerd**.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET TWEE-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="5bdf1-177">Selecteer in het dialoogvenster **MX-records verwijderen** de optie **Verwijderen** om uw wijzigingen te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET TWEE](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5bdf1-179">De vijf CNAME-records toevoegen die nodig zijn voor Office 365</span><span class="sxs-lookup"><span data-stu-id="5bdf1-179">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5bdf1-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5bdf1-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5bdf1-p110">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5bdf1-183">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5bdf1-184">Selecteer op de pagina **Beheerde DNS** in het gebied **CNAME Records** het besturingselement **(+) (Nieuw** **toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5bdf1-185">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5bdf1-185">(You may have to scroll down.)</span></span>
    
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET AFBEELDING VAN DNS-Knop](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="5bdf1-187">Voeg de eerste van de vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="5bdf1-188">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add CNAME Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="5bdf1-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-189">**Name**</span></span>|<span data-ttu-id="5bdf1-190">**Alias to**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-190">**Alias to**</span></span>|<span data-ttu-id="5bdf1-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5bdf1-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5bdf1-192">autodiscover</span></span>  <br/> |<span data-ttu-id="5bdf1-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="5bdf1-194">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5bdf1-195">1800</span><span class="sxs-lookup"><span data-stu-id="5bdf1-195">1800</span></span>  <br/> |
    |<span data-ttu-id="5bdf1-196">sip</span><span class="sxs-lookup"><span data-stu-id="5bdf1-196">sip</span></span>  <br/> |<span data-ttu-id="5bdf1-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5bdf1-198">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5bdf1-199">1800</span><span class="sxs-lookup"><span data-stu-id="5bdf1-199">1800</span></span>  <br/> |
    |<span data-ttu-id="5bdf1-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5bdf1-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5bdf1-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5bdf1-202">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5bdf1-203">1800</span><span class="sxs-lookup"><span data-stu-id="5bdf1-203">1800</span></span>  <br/> |
    |<span data-ttu-id="5bdf1-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5bdf1-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5bdf1-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="5bdf1-206">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5bdf1-207">1800</span><span class="sxs-lookup"><span data-stu-id="5bdf1-207">1800</span></span>  <br/> |
    |<span data-ttu-id="5bdf1-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5bdf1-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5bdf1-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="5bdf1-210">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5bdf1-211">1800</span><span class="sxs-lookup"><span data-stu-id="5bdf1-211">1800</span></span>  <br/> |
   
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET AFBEELDING VAN DNSMadeEasy-BP-configureren-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="5bdf1-213">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-213">Select **Submit**.</span></span>
    
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET AFBEELDING VAN DNS-Knop](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="5bdf1-215">Voeg elk van de andere vier CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="5bdf1-216">Selecteer in de sectie **CNAME Records** het besturingselement **(+)** toevoegen ( **Nieuw toevoegen),** maak een record met behulp van de waarden uit de volgende rij in de tabel en selecteer Vervolgens Opnieuw **Verzenden** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="5bdf1-217">Herhaal dit proces totdat u alle vijf CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5bdf1-218">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="5bdf1-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5bdf1-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5bdf1-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5bdf1-220">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5bdf1-221">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5bdf1-222">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5bdf1-223">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-223">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="5bdf1-224">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="5bdf1-224">Need examples?</span></span> <span data-ttu-id="5bdf1-225">Bekijk deze [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="5bdf1-225">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="5bdf1-226">Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="5bdf1-227">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="5bdf1-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="5bdf1-228">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5bdf1-229">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5bdf1-230">Selecteer op de pagina **Beheerde DNS** in het gebied **TXT Records** het besturingselement **(+) (Nieuw** **toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5bdf1-231">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5bdf1-231">(You may have to scroll down.)</span></span>
    
    ![AFBEELDING VAN HET](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="5bdf1-233">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add TXT Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="5bdf1-234">**Naam**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-234">**Name**</span></span>|<span data-ttu-id="5bdf1-235">**Value**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-235">**Value**</span></span>|<span data-ttu-id="5bdf1-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5bdf1-237">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="5bdf1-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5bdf1-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5bdf1-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5bdf1-239">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="5bdf1-240">1800</span><span class="sxs-lookup"><span data-stu-id="5bdf1-240">1800</span></span>  <br/> |
   
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET AFBEELDING VAN DNSMadeEasy-BP-configureren-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="5bdf1-242">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-242">Select **Submit**.</span></span>
    
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET AFBEELDING VAN DNSMadeEasy-BP-configureren-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5bdf1-244">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5bdf1-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5bdf1-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5bdf1-p113">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5bdf1-248">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5bdf1-249">Selecteer op de pagina **Beheerde DNS** in het gebied **SRV Records** het besturingselement **(+) (Nieuw** **toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5bdf1-250">(Mogelijk moet u omlaag schuiven)</span><span class="sxs-lookup"><span data-stu-id="5bdf1-250">(You may have to scroll down)</span></span>
    
    ![AFBEELDING VAN HET](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="5bdf1-252">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="5bdf1-253">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add SRV Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="5bdf1-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-254">**Name**</span></span>|<span data-ttu-id="5bdf1-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-255">**Priority**</span></span>|<span data-ttu-id="5bdf1-256">**Weight**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-256">**Weight**</span></span>|<span data-ttu-id="5bdf1-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-257">**Port**</span></span>|<span data-ttu-id="5bdf1-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-258">**Host**</span></span>|<span data-ttu-id="5bdf1-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5bdf1-260">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="5bdf1-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="5bdf1-261">100</span><span class="sxs-lookup"><span data-stu-id="5bdf1-261">100</span></span>  <br/> |<span data-ttu-id="5bdf1-262">1</span><span class="sxs-lookup"><span data-stu-id="5bdf1-262">1</span></span>  <br/> |<span data-ttu-id="5bdf1-263">443</span><span class="sxs-lookup"><span data-stu-id="5bdf1-263">443</span></span>  <br/> |<span data-ttu-id="5bdf1-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5bdf1-265">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5bdf1-266">1800</span><span class="sxs-lookup"><span data-stu-id="5bdf1-266">1800</span></span>  <br/> |
    |<span data-ttu-id="5bdf1-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="5bdf1-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5bdf1-268">100</span><span class="sxs-lookup"><span data-stu-id="5bdf1-268">100</span></span>  <br/> |<span data-ttu-id="5bdf1-269">1</span><span class="sxs-lookup"><span data-stu-id="5bdf1-269">1</span></span>  <br/> |<span data-ttu-id="5bdf1-270">5061</span><span class="sxs-lookup"><span data-stu-id="5bdf1-270">5061</span></span>  <br/> |<span data-ttu-id="5bdf1-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="5bdf1-272">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5bdf1-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5bdf1-273">1800</span><span class="sxs-lookup"><span data-stu-id="5bdf1-273">1800</span></span>  <br/> |
   
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET AFBEELDING VAN DNSMadeEasy-BP-configureren-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="5bdf1-275">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-275">Select **Submit**.</span></span>
    
    ![AFBEELDING VAN HET BASIS-PROGRAMMA MET AFBEELDING VAN DNSMadeEasy-BP-configureren-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="5bdf1-277">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="5bdf1-278">Selecteer in de sectie **SRV-records** het besturingselement **(+)** toevoegen ( **Nieuw toevoegen),** maak een record met behulp van de waarden uit de volgende rij in de tabel en selecteer Vervolgens Opnieuw **Verzenden** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="5bdf1-p114">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5bdf1-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

