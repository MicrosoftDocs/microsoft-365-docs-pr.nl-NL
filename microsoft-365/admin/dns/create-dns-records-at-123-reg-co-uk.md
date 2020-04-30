---
title: DNS-records maken op 123-reg.co.uk voor Microsoft
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
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op 123-reg.co.uk voor Microsoft.
ms.openlocfilehash: af03f4994868c34ebd76537c21af9e4f3755dd6a
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939365"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="5cc8a-103">DNS-records maken op 123-reg.co.uk voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="5cc8a-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="5cc8a-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5cc8a-105">Als 123-reg.co.uk uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5cc8a-106">Nadat u deze records op 123-reg.co.uk hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="5cc8a-p101">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5cc8a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5cc8a-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="5cc8a-110">Add a TXT record for verification</span></span>
<span data-ttu-id="5cc8a-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5cc8a-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5cc8a-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5cc8a-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5cc8a-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5cc8a-118">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5cc8a-119">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="5cc8a-120">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="5cc8a-121">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5cc8a-122">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="5cc8a-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="5cc8a-123">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-123">**Hostname**</span></span> <br/> |<span data-ttu-id="5cc8a-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-124">**Type**</span></span> <br/> |<span data-ttu-id="5cc8a-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="5cc8a-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="5cc8a-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="5cc8a-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5cc8a-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5cc8a-128">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-128">**Note:** This is an example.</span></span> <span data-ttu-id="5cc8a-129">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="5cc8a-130">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="5cc8a-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="5cc8a-131">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="5cc8a-132">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5cc8a-133">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="5cc8a-134">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5cc8a-135">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5cc8a-136">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5cc8a-137">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5cc8a-138">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5cc8a-p106">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5cc8a-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5cc8a-142">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="5cc8a-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5cc8a-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5cc8a-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5cc8a-p107">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5cc8a-146">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5cc8a-147">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="5cc8a-148">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="5cc8a-149">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5cc8a-150">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="5cc8a-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5cc8a-151">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-151">**Hostname**</span></span>|<span data-ttu-id="5cc8a-152">**Type**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-152">**Type**</span></span>|<span data-ttu-id="5cc8a-153">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-153">**Priority**</span></span>|<span data-ttu-id="5cc8a-154">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5cc8a-155">MX</span><span class="sxs-lookup"><span data-stu-id="5cc8a-155">MX</span></span>  <br/> |<span data-ttu-id="5cc8a-156">1</span><span class="sxs-lookup"><span data-stu-id="5cc8a-156">1</span></span>  <br/> <span data-ttu-id="5cc8a-157">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="5cc8a-157">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="5cc8a-158">*\<domein-sleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="5cc8a-159">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="5cc8a-160">**Opmerking**: Uw \<domeinsleutel\> kunt u ophalen uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="5cc8a-161">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="5cc8a-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Waarden uit de tabel kopiëren en plakken](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="5cc8a-163">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-163">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="5cc8a-165">Als er andere MX-records zijn, verwijdert u deze door het pictogram **Verwijderen (Prullenbak)** voor die records te kiezen.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Verwijderen selecteren (pictogram prullenbak)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5cc8a-167">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="5cc8a-167">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5cc8a-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5cc8a-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5cc8a-p109">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5cc8a-171">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5cc8a-172">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="5cc8a-173">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="5cc8a-174">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-174">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="5cc8a-175">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5cc8a-176">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="5cc8a-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5cc8a-177">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-177">**Hostname**</span></span>|<span data-ttu-id="5cc8a-178">**Type**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-178">**Type**</span></span>|<span data-ttu-id="5cc8a-179">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5cc8a-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5cc8a-180">autodiscover</span></span>  <br/> |<span data-ttu-id="5cc8a-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="5cc8a-181">CNAME</span></span>  <br/> |<span data-ttu-id="5cc8a-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="5cc8a-183">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5cc8a-184">sip</span><span class="sxs-lookup"><span data-stu-id="5cc8a-184">sip</span></span>  <br/> |<span data-ttu-id="5cc8a-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="5cc8a-185">CNAME</span></span>  <br/> |<span data-ttu-id="5cc8a-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5cc8a-187">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5cc8a-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5cc8a-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5cc8a-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="5cc8a-189">CNAME</span></span>  <br/> |<span data-ttu-id="5cc8a-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5cc8a-191">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5cc8a-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5cc8a-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5cc8a-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="5cc8a-193">CNAME</span></span>  <br/> |<span data-ttu-id="5cc8a-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="5cc8a-195">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="5cc8a-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5cc8a-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5cc8a-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="5cc8a-197">CNAME</span></span>  <br/> |<span data-ttu-id="5cc8a-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="5cc8a-199">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="5cc8a-201">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-201">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="5cc8a-203">Voeg de overige vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-203">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="5cc8a-204">Maak in de sectie **Geavanceerd DNS** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="5cc8a-205">Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-205">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5cc8a-206">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="5cc8a-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5cc8a-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5cc8a-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5cc8a-208">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5cc8a-209">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5cc8a-210">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsfot.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="5cc8a-211">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="5cc8a-212">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="5cc8a-212">Need examples?</span></span> <span data-ttu-id="5cc8a-213">Bekijk deze [Externe Domain Name System-records voor Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="5cc8a-213">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="5cc8a-214">Voor het valideren van uw SPF-record, kunt u een van deze [SPF-validatiehulpmiddelen](../setup/domains-faq.md) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="5cc8a-p111">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-p111">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5cc8a-217">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5cc8a-218">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="5cc8a-219">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="5cc8a-220">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5cc8a-221">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="5cc8a-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5cc8a-222">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-222">**Hostname**</span></span>|<span data-ttu-id="5cc8a-223">**Type**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-223">**Type**</span></span>|<span data-ttu-id="5cc8a-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="5cc8a-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="5cc8a-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="5cc8a-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5cc8a-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5cc8a-227">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Afbeelding van het te maken:Afbeelding van het te maken](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="5cc8a-229">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-229">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5cc8a-231">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="5cc8a-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5cc8a-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5cc8a-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5cc8a-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="5cc8a-235">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="5cc8a-236">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="5cc8a-237">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="5cc8a-238">Voeg als volgt de eerste van de twee SRV-records toe:</span><span class="sxs-lookup"><span data-stu-id="5cc8a-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="5cc8a-239">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Advanced DNS** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5cc8a-240">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="5cc8a-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5cc8a-241">Hostname</span><span class="sxs-lookup"><span data-stu-id="5cc8a-241">Hostname</span></span>|<span data-ttu-id="5cc8a-242">Type</span><span class="sxs-lookup"><span data-stu-id="5cc8a-242">Type</span></span>|<span data-ttu-id="5cc8a-243">Priority</span><span class="sxs-lookup"><span data-stu-id="5cc8a-243">Priority</span></span>|<span data-ttu-id="5cc8a-244">TTL</span><span class="sxs-lookup"><span data-stu-id="5cc8a-244">TTL</span></span>|<span data-ttu-id="5cc8a-245">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="5cc8a-245">Destination SRV</span></span>|
    |<span data-ttu-id="5cc8a-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="5cc8a-246">_sip._tls</span></span>|<span data-ttu-id="5cc8a-247">SRV</span><span class="sxs-lookup"><span data-stu-id="5cc8a-247">SRV</span></span>|<span data-ttu-id="5cc8a-248">100</span><span class="sxs-lookup"><span data-stu-id="5cc8a-248">100</span></span>|<span data-ttu-id="5cc8a-249">3600</span><span class="sxs-lookup"><span data-stu-id="5cc8a-249">3600</span></span>|<span data-ttu-id="5cc8a-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="5cc8a-251">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="5cc8a-252">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="5cc8a-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="5cc8a-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="5cc8a-254">SRV</span><span class="sxs-lookup"><span data-stu-id="5cc8a-254">SRV</span></span>|<span data-ttu-id="5cc8a-255">100</span><span class="sxs-lookup"><span data-stu-id="5cc8a-255">100</span></span>|<span data-ttu-id="5cc8a-256">3600</span><span class="sxs-lookup"><span data-stu-id="5cc8a-256">3600</span></span>|<span data-ttu-id="5cc8a-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="5cc8a-258">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5cc8a-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="5cc8a-259">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="5cc8a-261">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-261">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="5cc8a-263">De andere SRV-record toevoegen:</span><span class="sxs-lookup"><span data-stu-id="5cc8a-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="5cc8a-264">Maak in de sectie **Geavanceerd DNS** een record met de waarden uit de tweede rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="5cc8a-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="5cc8a-p115">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5cc8a-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
