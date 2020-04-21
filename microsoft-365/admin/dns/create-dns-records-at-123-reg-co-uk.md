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
ms.openlocfilehash: 887e7e6fc42fb55d4cc09ba66b68a2bb9702bbb9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629741"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="0648d-103">DNS-records maken op 123-reg.co.uk voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="0648d-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="0648d-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="0648d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0648d-105">Als 123-reg.co.uk uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0648d-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0648d-106">Nadat u deze records op 123-reg.co.uk hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="0648d-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="0648d-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="0648d-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0648d-108">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="0648d-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="0648d-109">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="0648d-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="0648d-110">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="0648d-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0648d-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="0648d-111">Add a TXT record for verification</span></span>
<span data-ttu-id="0648d-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0648d-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0648d-113">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="0648d-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="0648d-114">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="0648d-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0648d-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0648d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0648d-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0648d-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0648d-119">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0648d-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0648d-120">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0648d-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0648d-121">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="0648d-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0648d-122">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="0648d-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0648d-123">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="0648d-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="0648d-124">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0648d-124">**Hostname**</span></span> <br/> |<span data-ttu-id="0648d-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="0648d-125">**Type**</span></span> <br/> |<span data-ttu-id="0648d-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="0648d-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="0648d-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="0648d-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="0648d-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0648d-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0648d-129">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0648d-129">**Note:** This is an example.</span></span> <span data-ttu-id="0648d-130">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="0648d-130">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="0648d-131">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="0648d-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="0648d-132">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0648d-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="0648d-133">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="0648d-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0648d-134">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.</span><span class="sxs-lookup"><span data-stu-id="0648d-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="0648d-135">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="0648d-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0648d-136">Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="0648d-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0648d-137">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="0648d-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0648d-138">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="0648d-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0648d-139">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="0648d-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0648d-140">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="0648d-140">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="0648d-141">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="0648d-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="0648d-142">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="0648d-142">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0648d-143">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="0648d-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0648d-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0648d-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="0648d-p107">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0648d-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0648d-147">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0648d-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0648d-148">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0648d-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0648d-149">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="0648d-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0648d-150">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="0648d-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0648d-151">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="0648d-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0648d-152">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0648d-152">**Hostname**</span></span>|<span data-ttu-id="0648d-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="0648d-153">**Type**</span></span>|<span data-ttu-id="0648d-154">**Priority**</span><span class="sxs-lookup"><span data-stu-id="0648d-154">**Priority**</span></span>|<span data-ttu-id="0648d-155">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="0648d-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0648d-156">MX</span><span class="sxs-lookup"><span data-stu-id="0648d-156">MX</span></span>  <br/> |<span data-ttu-id="0648d-157">1</span><span class="sxs-lookup"><span data-stu-id="0648d-157">1</span></span>  <br/> <span data-ttu-id="0648d-158">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="0648d-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="0648d-159">*\<domein-sleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0648d-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="0648d-160">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0648d-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="0648d-161">**Let op:** Haal \<uw domeinsleutel\> uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="0648d-161">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="0648d-162">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="0648d-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Waarden uit de tabel kopiëren en plakken](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="0648d-164">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0648d-164">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="0648d-166">Als er andere MX-records zijn, verwijdert u deze door het pictogram **Verwijderen (Prullenbak)** voor die records te kiezen.</span><span class="sxs-lookup"><span data-stu-id="0648d-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Verwijderen selecteren (pictogram prullenbak)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0648d-168">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="0648d-168">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0648d-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0648d-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="0648d-p109">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0648d-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0648d-172">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0648d-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0648d-173">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0648d-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0648d-174">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="0648d-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0648d-175">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="0648d-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="0648d-176">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Advanced DNS** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0648d-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0648d-177">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="0648d-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0648d-178">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0648d-178">**Hostname**</span></span>|<span data-ttu-id="0648d-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="0648d-179">**Type**</span></span>|<span data-ttu-id="0648d-180">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="0648d-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0648d-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0648d-181">autodiscover</span></span>  <br/> |<span data-ttu-id="0648d-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="0648d-182">CNAME</span></span>  <br/> |<span data-ttu-id="0648d-183">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0648d-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="0648d-184">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0648d-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0648d-185">sip</span><span class="sxs-lookup"><span data-stu-id="0648d-185">sip</span></span>  <br/> |<span data-ttu-id="0648d-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="0648d-186">CNAME</span></span>  <br/> |<span data-ttu-id="0648d-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0648d-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0648d-188">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0648d-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0648d-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0648d-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0648d-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="0648d-190">CNAME</span></span>  <br/> |<span data-ttu-id="0648d-191">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0648d-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0648d-192">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0648d-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0648d-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0648d-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0648d-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="0648d-194">CNAME</span></span>  <br/> |<span data-ttu-id="0648d-195">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="0648d-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="0648d-196">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0648d-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0648d-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0648d-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0648d-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="0648d-198">CNAME</span></span>  <br/> |<span data-ttu-id="0648d-199">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0648d-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="0648d-200">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0648d-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="0648d-202">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0648d-202">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="0648d-204">Voeg de overige vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="0648d-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="0648d-205">Maak in de sectie **Geavanceerd DNS** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="0648d-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="0648d-206">Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0648d-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0648d-207">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="0648d-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0648d-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0648d-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0648d-209">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="0648d-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0648d-210">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="0648d-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0648d-211">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsfot.</span><span class="sxs-lookup"><span data-stu-id="0648d-211">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="0648d-212">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="0648d-212">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="0648d-213">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="0648d-213">Need examples?</span></span> <span data-ttu-id="0648d-214">Bekijk deze [externe domeinnaamsysteemrecords voor Microsoft.](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)</span><span class="sxs-lookup"><span data-stu-id="0648d-214">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="0648d-215">Voor het valideren van uw SPF-record kunt u een van deze [SPF-validatiehulpmiddelen](../setup/domains-faq.md) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0648d-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="0648d-p111">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0648d-p111">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0648d-218">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0648d-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0648d-219">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0648d-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0648d-220">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="0648d-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0648d-221">Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="0648d-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0648d-222">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="0648d-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0648d-223">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0648d-223">**Hostname**</span></span>|<span data-ttu-id="0648d-224">**Type**</span><span class="sxs-lookup"><span data-stu-id="0648d-224">**Type**</span></span>|<span data-ttu-id="0648d-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="0648d-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0648d-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="0648d-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="0648d-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0648d-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0648d-228">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="0648d-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Afbeelding van het te maken:Afbeelding van het te maken](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="0648d-230">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0648d-230">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0648d-232">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="0648d-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0648d-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0648d-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="0648d-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0648d-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0648d-236">Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0648d-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0648d-237">Kies in de vervolgkeuzelijst **Select action** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0648d-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0648d-238">Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.**</span><span class="sxs-lookup"><span data-stu-id="0648d-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0648d-239">Voeg als volgt de eerste van de twee SRV-records toe:</span><span class="sxs-lookup"><span data-stu-id="0648d-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="0648d-240">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Advanced DNS** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0648d-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0648d-241">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="0648d-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0648d-242">Hostname</span><span class="sxs-lookup"><span data-stu-id="0648d-242">Hostname</span></span>|<span data-ttu-id="0648d-243">Type</span><span class="sxs-lookup"><span data-stu-id="0648d-243">Type</span></span>|<span data-ttu-id="0648d-244">Priority</span><span class="sxs-lookup"><span data-stu-id="0648d-244">Priority</span></span>|<span data-ttu-id="0648d-245">TTL</span><span class="sxs-lookup"><span data-stu-id="0648d-245">TTL</span></span>|<span data-ttu-id="0648d-246">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="0648d-246">Destination SRV</span></span>|
    |<span data-ttu-id="0648d-247">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="0648d-247">_sip._tls</span></span>|<span data-ttu-id="0648d-248">SRV</span><span class="sxs-lookup"><span data-stu-id="0648d-248">SRV</span></span>|<span data-ttu-id="0648d-249">100</span><span class="sxs-lookup"><span data-stu-id="0648d-249">100</span></span>|<span data-ttu-id="0648d-250">3600</span><span class="sxs-lookup"><span data-stu-id="0648d-250">3600</span></span>|<span data-ttu-id="0648d-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0648d-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="0648d-252">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0648d-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="0648d-253">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="0648d-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="0648d-254">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="0648d-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="0648d-255">SRV</span><span class="sxs-lookup"><span data-stu-id="0648d-255">SRV</span></span>|<span data-ttu-id="0648d-256">100</span><span class="sxs-lookup"><span data-stu-id="0648d-256">100</span></span>|<span data-ttu-id="0648d-257">3600</span><span class="sxs-lookup"><span data-stu-id="0648d-257">3600</span></span>|<span data-ttu-id="0648d-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0648d-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="0648d-259">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0648d-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="0648d-260">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="0648d-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="0648d-262">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0648d-262">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="0648d-264">De andere SRV-record toevoegen:</span><span class="sxs-lookup"><span data-stu-id="0648d-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="0648d-265">Maak in de sectie **Geavanceerd DNS** een record met de waarden uit de tweede rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="0648d-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0648d-266">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="0648d-266">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="0648d-267">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="0648d-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="0648d-268">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="0648d-268">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
