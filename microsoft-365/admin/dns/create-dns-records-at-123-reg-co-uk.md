---
title: DNS-records maken op 123-reg.co.uk voor Office 365
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Lees uw domein verifiëren en STEL DNS-records in voor e-mail, Skype voor Bedrijven Online en andere services op 123-reg.co.uk voor Office 365.
ms.openlocfilehash: 521426f039ac02e8c4566f5901fee49679de4e70
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211857"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a><span data-ttu-id="15f63-103">DNS-records maken op 123-reg.co.uk voor Office 365</span><span class="sxs-lookup"><span data-stu-id="15f63-103">Create DNS records at 123-reg.co.uk for Office 365</span></span>

 <span data-ttu-id="15f63-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="15f63-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="15f63-105">Als 123-reg.co.uk uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="15f63-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="15f63-106">Nadat u deze records bij 123-reg.co.uk hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="15f63-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="15f63-107">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="15f63-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="15f63-p101">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="15f63-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="15f63-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="15f63-111">Add a TXT record for verification</span></span>
<span data-ttu-id="15f63-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="15f63-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="15f63-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="15f63-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15f63-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="15f63-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="15f63-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="15f63-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="15f63-119">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="15f63-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="15f63-120">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="15f63-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="15f63-121">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="15f63-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="15f63-122">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="15f63-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="15f63-123">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="15f63-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="15f63-124">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="15f63-124">**Hostname**</span></span> <br/> |<span data-ttu-id="15f63-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="15f63-125">**Type**</span></span> <br/> |<span data-ttu-id="15f63-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="15f63-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="15f63-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="15f63-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="15f63-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="15f63-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="15f63-129">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="15f63-129">**Note:** This is an example.</span></span> <span data-ttu-id="15f63-130">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="15f63-130">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="15f63-131">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="15f63-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="15f63-132">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="15f63-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="15f63-133">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="15f63-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="15f63-134">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="15f63-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="15f63-135">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="15f63-135">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="15f63-136">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="15f63-136">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="15f63-137">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="15f63-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="15f63-138">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="15f63-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="15f63-139">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="15f63-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="15f63-p106">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="15f63-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="15f63-143">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="15f63-143">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="15f63-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="15f63-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="15f63-p107">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="15f63-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="15f63-147">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="15f63-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="15f63-148">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="15f63-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="15f63-149">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="15f63-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="15f63-150">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="15f63-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="15f63-151">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="15f63-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="15f63-152">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="15f63-152">**Hostname**</span></span>|<span data-ttu-id="15f63-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="15f63-153">**Type**</span></span>|<span data-ttu-id="15f63-154">**Priority**</span><span class="sxs-lookup"><span data-stu-id="15f63-154">**Priority**</span></span>|<span data-ttu-id="15f63-155">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="15f63-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="15f63-156">MX</span><span class="sxs-lookup"><span data-stu-id="15f63-156">MX</span></span>  <br/> |<span data-ttu-id="15f63-157">1</span><span class="sxs-lookup"><span data-stu-id="15f63-157">1</span></span>  <br/> <span data-ttu-id="15f63-158">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="15f63-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="15f63-159">*\<domein-sleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="15f63-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="15f63-160">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="15f63-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="15f63-161">**Opmerking**: Uw \<domeinsleutel\> kunt u ophalen uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="15f63-161">**Note:** Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="15f63-162">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="15f63-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Waarden uit de tabel kopiëren en plakken](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="15f63-164">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="15f63-164">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="15f63-166">Als er andere MX-records zijn, verwijdert u deze door het pictogram **Verwijderen (Prullenbak)** voor die records te kiezen.</span><span class="sxs-lookup"><span data-stu-id="15f63-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Verwijderen selecteren (pictogram prullenbak)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="15f63-168">De zes CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="15f63-168">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="15f63-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="15f63-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="15f63-p109">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="15f63-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="15f63-172">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="15f63-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="15f63-173">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="15f63-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="15f63-174">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="15f63-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="15f63-175">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="15f63-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="15f63-176">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="15f63-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="15f63-177">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="15f63-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="15f63-178">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="15f63-178">**Hostname**</span></span>|<span data-ttu-id="15f63-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="15f63-179">**Type**</span></span>|<span data-ttu-id="15f63-180">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="15f63-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="15f63-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="15f63-181">autodiscover</span></span>  <br/> |<span data-ttu-id="15f63-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="15f63-182">CNAME</span></span>  <br/> |<span data-ttu-id="15f63-183">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="15f63-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="15f63-184">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="15f63-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="15f63-185">sip</span><span class="sxs-lookup"><span data-stu-id="15f63-185">sip</span></span>  <br/> |<span data-ttu-id="15f63-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="15f63-186">CNAME</span></span>  <br/> |<span data-ttu-id="15f63-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="15f63-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="15f63-188">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="15f63-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="15f63-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="15f63-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="15f63-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="15f63-190">CNAME</span></span>  <br/> |<span data-ttu-id="15f63-191">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="15f63-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="15f63-192">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="15f63-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="15f63-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="15f63-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="15f63-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="15f63-194">CNAME</span></span>  <br/> |<span data-ttu-id="15f63-195">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="15f63-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="15f63-196">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="15f63-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="15f63-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="15f63-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="15f63-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="15f63-198">CNAME</span></span>  <br/> |<span data-ttu-id="15f63-199">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="15f63-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="15f63-200">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="15f63-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="15f63-202">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="15f63-202">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="15f63-204">Voeg de overige vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="15f63-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="15f63-205">Maak in de sectie **Geavanceerd DNS** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="15f63-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="15f63-206">Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="15f63-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="15f63-207">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="15f63-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="15f63-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="15f63-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="15f63-p110">U kunt maximaal één TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals bezorgings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen. Hebt u voorbeelden nodig? Bekijk deze [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). Voor het valideren van uw SPF-record kunt u een van deze [SPF-validatiehulpmiddelen](../setup/domains-faq.md) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="15f63-p110">You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="15f63-p111">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="15f63-p111">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="15f63-218">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="15f63-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="15f63-219">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="15f63-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="15f63-220">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="15f63-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="15f63-221">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="15f63-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="15f63-222">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="15f63-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="15f63-223">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="15f63-223">**Hostname**</span></span>|<span data-ttu-id="15f63-224">**Type**</span><span class="sxs-lookup"><span data-stu-id="15f63-224">**Type**</span></span>|<span data-ttu-id="15f63-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="15f63-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="15f63-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="15f63-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="15f63-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="15f63-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="15f63-228">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="15f63-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Afbeelding van het te maken:Afbeelding van het te maken](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="15f63-230">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="15f63-230">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="15f63-232">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="15f63-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="15f63-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="15f63-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="15f63-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="15f63-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="15f63-236">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="15f63-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="15f63-237">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="15f63-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="15f63-238">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="15f63-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="15f63-239">Voeg als volgt de eerste van de twee SRV-records toe:</span><span class="sxs-lookup"><span data-stu-id="15f63-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="15f63-240">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Advanced DNS** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="15f63-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="15f63-241">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="15f63-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="15f63-242">Hostname</span><span class="sxs-lookup"><span data-stu-id="15f63-242">Hostname</span></span>|<span data-ttu-id="15f63-243">Type</span><span class="sxs-lookup"><span data-stu-id="15f63-243">Type</span></span>|<span data-ttu-id="15f63-244">Priority</span><span class="sxs-lookup"><span data-stu-id="15f63-244">Priority</span></span>|<span data-ttu-id="15f63-245">TTL</span><span class="sxs-lookup"><span data-stu-id="15f63-245">TTL</span></span>|<span data-ttu-id="15f63-246">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="15f63-246">Destination SRV</span></span>|
    |<span data-ttu-id="15f63-247">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="15f63-247">_sip._tls</span></span>|<span data-ttu-id="15f63-248">SRV</span><span class="sxs-lookup"><span data-stu-id="15f63-248">SRV</span></span>|<span data-ttu-id="15f63-249">100</span><span class="sxs-lookup"><span data-stu-id="15f63-249">100</span></span>|<span data-ttu-id="15f63-250">3600</span><span class="sxs-lookup"><span data-stu-id="15f63-250">3600</span></span>|<span data-ttu-id="15f63-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="15f63-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="15f63-252">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="15f63-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="15f63-253">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="15f63-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="15f63-254">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="15f63-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="15f63-255">SRV</span><span class="sxs-lookup"><span data-stu-id="15f63-255">SRV</span></span>|<span data-ttu-id="15f63-256">100</span><span class="sxs-lookup"><span data-stu-id="15f63-256">100</span></span>|<span data-ttu-id="15f63-257">3600</span><span class="sxs-lookup"><span data-stu-id="15f63-257">3600</span></span>|<span data-ttu-id="15f63-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="15f63-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="15f63-259">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="15f63-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="15f63-260">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="15f63-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="15f63-262">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="15f63-262">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="15f63-264">De andere SRV-record toevoegen:</span><span class="sxs-lookup"><span data-stu-id="15f63-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="15f63-265">Maak in de sectie **Geavanceerd DNS** een record met de waarden uit de tweede rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="15f63-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="15f63-p115">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="15f63-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
