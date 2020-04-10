---
title: DNS-records bij name.com maken voor Office 365
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
description: Lees uw domein en stel DNS-records in voor e-mail, Skype voor Bedrijven Online en andere services op name.com voor Office 365.
ms.openlocfilehash: f39cf9f241851e555ea23ca7b63453796a5f471b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211653"
---
# <a name="create-dns-records-at-namecom-for-office-365"></a><span data-ttu-id="9cdb1-103">DNS-records bij name.com maken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="9cdb1-103">Create DNS records at name.com for Office 365</span></span>

 <span data-ttu-id="9cdb1-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9cdb1-105">Als name.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9cdb1-106">Nadat u deze records bij name.com hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-106">After you add these records at name.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="9cdb1-107">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9cdb1-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9cdb1-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="9cdb1-111">Add a TXT record for verification</span></span>
<span data-ttu-id="9cdb1-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9cdb1-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9cdb1-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9cdb1-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9cdb1-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="9cdb1-120">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="9cdb1-122">Selecteer in de kolom **Details** de optie \*\* DNS Records \*\*.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="9cdb1-124">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="9cdb1-125">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9cdb1-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-126">**Type**</span></span> <br/> |<span data-ttu-id="9cdb1-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-127">**Host**</span></span> <br/> |<span data-ttu-id="9cdb1-128">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-128">**Answer**</span></span> <br/> |<span data-ttu-id="9cdb1-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="9cdb1-130">TXT</span><span class="sxs-lookup"><span data-stu-id="9cdb1-130">TXT</span></span>  <br/> |<span data-ttu-id="9cdb1-131">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="9cdb1-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9cdb1-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9cdb1-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9cdb1-p105">**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="9cdb1-136">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-136">Use the default value (300).</span></span>  <br/> |
   
    ![Afbeelding van het te geven/geeft aan de knop Verifiëren-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="9cdb1-138">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="9cdb1-140">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9cdb1-141">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="9cdb1-142">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9cdb1-143">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9cdb1-144">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9cdb1-145">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9cdb1-146">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="9cdb1-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="9cdb1-150">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="9cdb1-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="9cdb1-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9cdb1-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9cdb1-p107">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="9cdb1-155">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="9cdb1-157">Selecteer **DNS-records**in de kolom **Details** .</span><span class="sxs-lookup"><span data-stu-id="9cdb1-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="9cdb1-159">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="9cdb1-160">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9cdb1-161">**Type**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-161">**Type**</span></span>|<span data-ttu-id="9cdb1-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-162">**Host**</span></span>|<span data-ttu-id="9cdb1-163">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-163">**Answer**</span></span>|<span data-ttu-id="9cdb1-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-164">**TTL**</span></span>|<span data-ttu-id="9cdb1-165">**Prio**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9cdb1-166">MX</span><span class="sxs-lookup"><span data-stu-id="9cdb1-166">MX</span></span>  <br/> |<span data-ttu-id="9cdb1-167">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="9cdb1-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="9cdb1-168">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9cdb1-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9cdb1-169">**Let op:** Haal uw \* \<domeinsleutel\> \* op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="9cdb1-170">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="9cdb1-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="9cdb1-171">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="9cdb1-172">0</span><span class="sxs-lookup"><span data-stu-id="9cdb1-172">0</span></span>  <br/> <span data-ttu-id="9cdb1-173">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Afbeelding van het te maken](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="9cdb1-175">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="9cdb1-177">Als er andere MX-records zijn, verwijdert u deze met behulp van de volgende tweestapsprocedure:</span><span class="sxs-lookup"><span data-stu-id="9cdb1-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="9cdb1-178">Selecteer **Verwijderen** voor elkaars MX-record in de kolom **Acties.**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="9cdb1-180">Als u elke verwijdering wilt bevestigen, selecteert u **Opnieuw verwijderen** in de kolom **Acties.**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="9cdb1-182">Herhaal deze tweestapsprocedure tot u alle overige MX-records hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="9cdb1-183">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="9cdb1-183">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="9cdb1-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9cdb1-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9cdb1-p109">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="9cdb1-188">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="9cdb1-190">Selecteer **DNS-records**in de kolom **Details** .</span><span class="sxs-lookup"><span data-stu-id="9cdb1-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="9cdb1-192">Voeg de eerste CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="9cdb1-193">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="9cdb1-194">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9cdb1-195">**Type**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-195">**Type**</span></span>|<span data-ttu-id="9cdb1-196">**Host**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-196">**Host**</span></span>|<span data-ttu-id="9cdb1-197">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-197">**Answer**</span></span>|<span data-ttu-id="9cdb1-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9cdb1-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cdb1-199">CNAME</span></span>  <br/> |<span data-ttu-id="9cdb1-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9cdb1-200">autodiscover</span></span>  <br/> |<span data-ttu-id="9cdb1-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9cdb1-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="9cdb1-202">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="9cdb1-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cdb1-203">CNAME</span></span>  <br/> |<span data-ttu-id="9cdb1-204">sip</span><span class="sxs-lookup"><span data-stu-id="9cdb1-204">sip</span></span>  <br/> |<span data-ttu-id="9cdb1-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9cdb1-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9cdb1-206">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="9cdb1-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cdb1-207">CNAME</span></span>  <br/> |<span data-ttu-id="9cdb1-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9cdb1-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9cdb1-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9cdb1-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9cdb1-210">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="9cdb1-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cdb1-211">CNAME</span></span>  <br/> |<span data-ttu-id="9cdb1-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9cdb1-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9cdb1-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9cdb1-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="9cdb1-214">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="9cdb1-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cdb1-215">CNAME</span></span>  <br/> |<span data-ttu-id="9cdb1-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9cdb1-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9cdb1-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9cdb1-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="9cdb1-218">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-218">Use the default value (300).</span></span>  <br/> |
   
   ![Afbeelding van het te maken](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="9cdb1-220">Selecteer **Record toevoegen** om de eerste record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="9cdb1-222">Voeg de tweede CNAME-record toe:</span><span class="sxs-lookup"><span data-stu-id="9cdb1-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="9cdb1-223">Gebruik de waarden uit de tweede rij van de bovenstaande tabel en selecteer **Record toevoegen** om de tweede record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="9cdb1-224">Voeg de resterende records op dezelfde manier toe met behulp van de waarden uit de derde, vierde, vijfde en zesde rij van de tabel.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9cdb1-225">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="9cdb1-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9cdb1-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9cdb1-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cdb1-227">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9cdb1-228">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9cdb1-229">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="9cdb1-230">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9cdb1-p111">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="9cdb1-234">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="9cdb1-236">Selecteer **DNS-records**in de kolom **Details** .</span><span class="sxs-lookup"><span data-stu-id="9cdb1-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="9cdb1-238">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="9cdb1-239">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9cdb1-240">**Type**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-240">**Type**</span></span>|<span data-ttu-id="9cdb1-241">**Host**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-241">**Host**</span></span>|<span data-ttu-id="9cdb1-242">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-242">**Answer**</span></span>|<span data-ttu-id="9cdb1-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9cdb1-244">TXT</span><span class="sxs-lookup"><span data-stu-id="9cdb1-244">TXT</span></span>  <br/> |<span data-ttu-id="9cdb1-245">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="9cdb1-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9cdb1-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9cdb1-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9cdb1-247">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="9cdb1-248">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-248">Use the default value (300).</span></span>  <br/> |
   
   ![Afbeelding van het te maken](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="9cdb1-250">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="9cdb1-252">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="9cdb1-252">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="9cdb1-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9cdb1-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="9cdb1-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="9cdb1-257">Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="9cdb1-259">Selecteer **DNS Records+** in de kolom **Details.**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="9cdb1-261">Voeg de eerste SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="9cdb1-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="9cdb1-262">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="9cdb1-263">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9cdb1-264">**Type**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-264">**Type**</span></span>|<span data-ttu-id="9cdb1-265">**Service**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-265">**Service**</span></span>|<span data-ttu-id="9cdb1-266">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-266">**Weight**</span></span>|<span data-ttu-id="9cdb1-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-267">**TTL**</span></span>|<span data-ttu-id="9cdb1-268">**Prio**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-268">**Prio**</span></span>|<span data-ttu-id="9cdb1-269">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-269">**Protocol**</span></span>|<span data-ttu-id="9cdb1-270">**Poort**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-270">**Port**</span></span>|<span data-ttu-id="9cdb1-271">**Doel**</span><span class="sxs-lookup"><span data-stu-id="9cdb1-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9cdb1-272">SRV</span><span class="sxs-lookup"><span data-stu-id="9cdb1-272">SRV</span></span>|<span data-ttu-id="9cdb1-273">sip</span><span class="sxs-lookup"><span data-stu-id="9cdb1-273">sip</span></span>|<span data-ttu-id="9cdb1-274">1</span><span class="sxs-lookup"><span data-stu-id="9cdb1-274">1</span></span>|<span data-ttu-id="9cdb1-275">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-275">Use the default value (300).</span></span>|<span data-ttu-id="9cdb1-276">100</span><span class="sxs-lookup"><span data-stu-id="9cdb1-276">100</span></span>|<span data-ttu-id="9cdb1-277">tls</span><span class="sxs-lookup"><span data-stu-id="9cdb1-277">tls</span></span>|<span data-ttu-id="9cdb1-278">443</span><span class="sxs-lookup"><span data-stu-id="9cdb1-278">443</span></span>|<span data-ttu-id="9cdb1-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9cdb1-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="9cdb1-280">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="9cdb1-281">SRV</span><span class="sxs-lookup"><span data-stu-id="9cdb1-281">SRV</span></span>|<span data-ttu-id="9cdb1-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9cdb1-282">sipfederationtls</span></span>|<span data-ttu-id="9cdb1-283">1</span><span class="sxs-lookup"><span data-stu-id="9cdb1-283">1</span></span>|<span data-ttu-id="9cdb1-284">Gebruik de standaardwaarde (300).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-284">Use the default value (300).</span></span>|<span data-ttu-id="9cdb1-285">100</span><span class="sxs-lookup"><span data-stu-id="9cdb1-285">100</span></span>|<span data-ttu-id="9cdb1-286">tcp</span><span class="sxs-lookup"><span data-stu-id="9cdb1-286">tcp</span></span>|<span data-ttu-id="9cdb1-287">5061</span><span class="sxs-lookup"><span data-stu-id="9cdb1-287">5061</span></span>|<span data-ttu-id="9cdb1-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9cdb1-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="9cdb1-289">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Afbeelding van het te maken](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="9cdb1-291">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="9cdb1-293">Voeg als volgt de tweede SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="9cdb1-293">Add the second SRV record:</span></span>

<span data-ttu-id="9cdb1-294">Gebruik de waarden uit de volgende rij van de bovenstaande tabel en selecteer **Record toevoegen** om de tweede record toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="9cdb1-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="9cdb1-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9cdb1-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
