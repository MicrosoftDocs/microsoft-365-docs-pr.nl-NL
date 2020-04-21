---
title: DNS-records maken op name.com voor Microsoft
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op name.com voor Microsoft.
ms.openlocfilehash: 8b23ab4d324b5e6d023f10f8f1d11d95d3c579ba
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629345"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="54c42-103">DNS-records maken op name.com voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="54c42-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="54c42-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="54c42-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="54c42-105">Als name.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="54c42-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="54c42-106">Nadat u deze records bij name.com hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="54c42-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="54c42-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="54c42-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="54c42-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="54c42-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="54c42-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="54c42-111">Add a TXT record for verification</span></span>
<span data-ttu-id="54c42-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="54c42-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="54c42-113">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="54c42-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="54c42-114">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="54c42-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="54c42-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="54c42-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="54c42-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="54c42-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="54c42-120">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="54c42-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="54c42-122">Selecteer in de kolom **Details** de optie \*\* DNS Records \*\*.</span><span class="sxs-lookup"><span data-stu-id="54c42-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="54c42-124">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="54c42-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="54c42-125">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="54c42-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="54c42-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="54c42-126">**Type**</span></span> <br/> |<span data-ttu-id="54c42-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="54c42-127">**Host**</span></span> <br/> |<span data-ttu-id="54c42-128">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="54c42-128">**Answer**</span></span> <br/> |<span data-ttu-id="54c42-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54c42-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="54c42-130">TXT</span><span class="sxs-lookup"><span data-stu-id="54c42-130">TXT</span></span>  <br/> |<span data-ttu-id="54c42-131">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="54c42-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="54c42-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="54c42-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="54c42-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="54c42-133">**Note:** This is an example.</span></span> <span data-ttu-id="54c42-134">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="54c42-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="54c42-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="54c42-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="54c42-136">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="54c42-136">Use the default value (300).</span></span>  <br/> |
   
    ![Afbeelding van het te geven/geeft aan de knop Verifiëren-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="54c42-138">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="54c42-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="54c42-140">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="54c42-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="54c42-141">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="54c42-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="54c42-142">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="54c42-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="54c42-143">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="54c42-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="54c42-144">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="54c42-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="54c42-145">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="54c42-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="54c42-146">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="54c42-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="54c42-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="54c42-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="54c42-150">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="54c42-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="54c42-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="54c42-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="54c42-p107">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="54c42-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="54c42-155">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="54c42-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="54c42-157">Selecteer **DNS-records**in de kolom **Details** .</span><span class="sxs-lookup"><span data-stu-id="54c42-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="54c42-159">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="54c42-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="54c42-160">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="54c42-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="54c42-161">**Type**</span><span class="sxs-lookup"><span data-stu-id="54c42-161">**Type**</span></span>|<span data-ttu-id="54c42-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="54c42-162">**Host**</span></span>|<span data-ttu-id="54c42-163">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="54c42-163">**Answer**</span></span>|<span data-ttu-id="54c42-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54c42-164">**TTL**</span></span>|<span data-ttu-id="54c42-165">**Prio**</span><span class="sxs-lookup"><span data-stu-id="54c42-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="54c42-166">MX</span><span class="sxs-lookup"><span data-stu-id="54c42-166">MX</span></span>  <br/> |<span data-ttu-id="54c42-167">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="54c42-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="54c42-168">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="54c42-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="54c42-169">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="54c42-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="54c42-170">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="54c42-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="54c42-171">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="54c42-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="54c42-172">0</span><span class="sxs-lookup"><span data-stu-id="54c42-172">0</span></span>  <br/> <span data-ttu-id="54c42-173">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="54c42-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Afbeelding van het te maken](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="54c42-175">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="54c42-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="54c42-177">Als er andere MX-records zijn, verwijdert u deze met behulp van de volgende tweestapsprocedure:</span><span class="sxs-lookup"><span data-stu-id="54c42-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="54c42-178">Selecteer **Verwijderen** voor elkaars MX-record in de kolom **Acties.**</span><span class="sxs-lookup"><span data-stu-id="54c42-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="54c42-180">Als u elke verwijdering wilt bevestigen, selecteert u **Opnieuw verwijderen** in de kolom **Acties.**</span><span class="sxs-lookup"><span data-stu-id="54c42-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="54c42-182">Herhaal deze tweestapsprocedure tot u alle overige MX-records hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="54c42-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="54c42-183">De CNAME-records toevoegen die voor Microsoft vereist zijn</span><span class="sxs-lookup"><span data-stu-id="54c42-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="54c42-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="54c42-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="54c42-p109">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="54c42-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="54c42-188">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="54c42-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="54c42-190">Selecteer **DNS-records**in de kolom **Details** .</span><span class="sxs-lookup"><span data-stu-id="54c42-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="54c42-192">Voeg de eerste CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="54c42-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="54c42-193">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="54c42-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="54c42-194">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="54c42-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="54c42-195">**Type**</span><span class="sxs-lookup"><span data-stu-id="54c42-195">**Type**</span></span>|<span data-ttu-id="54c42-196">**Host**</span><span class="sxs-lookup"><span data-stu-id="54c42-196">**Host**</span></span>|<span data-ttu-id="54c42-197">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="54c42-197">**Answer**</span></span>|<span data-ttu-id="54c42-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54c42-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="54c42-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="54c42-199">CNAME</span></span>  <br/> |<span data-ttu-id="54c42-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="54c42-200">autodiscover</span></span>  <br/> |<span data-ttu-id="54c42-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="54c42-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="54c42-202">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="54c42-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="54c42-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="54c42-203">CNAME</span></span>  <br/> |<span data-ttu-id="54c42-204">sip</span><span class="sxs-lookup"><span data-stu-id="54c42-204">sip</span></span>  <br/> |<span data-ttu-id="54c42-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="54c42-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="54c42-206">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="54c42-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="54c42-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="54c42-207">CNAME</span></span>  <br/> |<span data-ttu-id="54c42-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="54c42-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="54c42-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="54c42-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="54c42-210">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="54c42-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="54c42-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="54c42-211">CNAME</span></span>  <br/> |<span data-ttu-id="54c42-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="54c42-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="54c42-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="54c42-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="54c42-214">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="54c42-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="54c42-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="54c42-215">CNAME</span></span>  <br/> |<span data-ttu-id="54c42-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="54c42-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="54c42-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="54c42-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="54c42-218">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="54c42-218">Use the default value (300).</span></span>  <br/> |
   
   ![Afbeelding van het te maken](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="54c42-220">Selecteer **Record toevoegen** om de eerste record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="54c42-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="54c42-222">Voeg de tweede CNAME-record toe:</span><span class="sxs-lookup"><span data-stu-id="54c42-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="54c42-223">Gebruik de waarden uit de tweede rij van de bovenstaande tabel en selecteer **Record toevoegen** om de tweede record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="54c42-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="54c42-224">Voeg de resterende records op dezelfde manier toe met behulp van de waarden uit de derde, vierde, vijfde en zesde rij van de tabel.</span><span class="sxs-lookup"><span data-stu-id="54c42-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="54c42-225">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="54c42-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="54c42-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="54c42-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="54c42-227">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="54c42-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="54c42-228">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="54c42-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="54c42-229">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54c42-229">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="54c42-230">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="54c42-230">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="54c42-p111">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="54c42-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="54c42-234">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="54c42-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="54c42-236">Selecteer **DNS-records**in de kolom **Details** .</span><span class="sxs-lookup"><span data-stu-id="54c42-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="54c42-238">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="54c42-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="54c42-239">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="54c42-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="54c42-240">**Type**</span><span class="sxs-lookup"><span data-stu-id="54c42-240">**Type**</span></span>|<span data-ttu-id="54c42-241">**Host**</span><span class="sxs-lookup"><span data-stu-id="54c42-241">**Host**</span></span>|<span data-ttu-id="54c42-242">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="54c42-242">**Answer**</span></span>|<span data-ttu-id="54c42-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54c42-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="54c42-244">TXT</span><span class="sxs-lookup"><span data-stu-id="54c42-244">TXT</span></span>  <br/> |<span data-ttu-id="54c42-245">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="54c42-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="54c42-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="54c42-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="54c42-247">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="54c42-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="54c42-248">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="54c42-248">Use the default value (300).</span></span>  <br/> |
   
   ![Afbeelding van het te maken](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="54c42-250">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="54c42-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="54c42-252">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="54c42-252">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="54c42-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="54c42-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="54c42-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="54c42-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="54c42-257">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="54c42-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="54c42-259">Selecteer **DNS Records+** in de kolom **Details.**</span><span class="sxs-lookup"><span data-stu-id="54c42-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="54c42-261">Voeg de eerste SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="54c42-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="54c42-262">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="54c42-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="54c42-263">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="54c42-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="54c42-264">**Type**</span><span class="sxs-lookup"><span data-stu-id="54c42-264">**Type**</span></span>|<span data-ttu-id="54c42-265">**Service**</span><span class="sxs-lookup"><span data-stu-id="54c42-265">**Service**</span></span>|<span data-ttu-id="54c42-266">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="54c42-266">**Weight**</span></span>|<span data-ttu-id="54c42-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54c42-267">**TTL**</span></span>|<span data-ttu-id="54c42-268">**Prio**</span><span class="sxs-lookup"><span data-stu-id="54c42-268">**Prio**</span></span>|<span data-ttu-id="54c42-269">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="54c42-269">**Protocol**</span></span>|<span data-ttu-id="54c42-270">**Poort**</span><span class="sxs-lookup"><span data-stu-id="54c42-270">**Port**</span></span>|<span data-ttu-id="54c42-271">**Doel**</span><span class="sxs-lookup"><span data-stu-id="54c42-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="54c42-272">SRV</span><span class="sxs-lookup"><span data-stu-id="54c42-272">SRV</span></span>|<span data-ttu-id="54c42-273">sip</span><span class="sxs-lookup"><span data-stu-id="54c42-273">sip</span></span>|<span data-ttu-id="54c42-274">1</span><span class="sxs-lookup"><span data-stu-id="54c42-274">1</span></span>|<span data-ttu-id="54c42-275">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="54c42-275">Use the default value (300).</span></span>|<span data-ttu-id="54c42-276">100</span><span class="sxs-lookup"><span data-stu-id="54c42-276">100</span></span>|<span data-ttu-id="54c42-277">tls</span><span class="sxs-lookup"><span data-stu-id="54c42-277">tls</span></span>|<span data-ttu-id="54c42-278">443</span><span class="sxs-lookup"><span data-stu-id="54c42-278">443</span></span>|<span data-ttu-id="54c42-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="54c42-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="54c42-280">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="54c42-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="54c42-281">SRV</span><span class="sxs-lookup"><span data-stu-id="54c42-281">SRV</span></span>|<span data-ttu-id="54c42-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="54c42-282">sipfederationtls</span></span>|<span data-ttu-id="54c42-283">1</span><span class="sxs-lookup"><span data-stu-id="54c42-283">1</span></span>|<span data-ttu-id="54c42-284">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="54c42-284">Use the default value (300).</span></span>|<span data-ttu-id="54c42-285">100</span><span class="sxs-lookup"><span data-stu-id="54c42-285">100</span></span>|<span data-ttu-id="54c42-286">tcp</span><span class="sxs-lookup"><span data-stu-id="54c42-286">tcp</span></span>|<span data-ttu-id="54c42-287">5061</span><span class="sxs-lookup"><span data-stu-id="54c42-287">5061</span></span>|<span data-ttu-id="54c42-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="54c42-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="54c42-289">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="54c42-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Afbeelding van het te maken](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="54c42-291">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="54c42-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="54c42-293">Voeg als volgt de tweede SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="54c42-293">Add the second SRV record:</span></span>

<span data-ttu-id="54c42-294">Gebruik de waarden uit de volgende rij van de bovenstaande tabel en selecteer **Record toevoegen** om de tweede record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="54c42-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="54c42-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="54c42-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
