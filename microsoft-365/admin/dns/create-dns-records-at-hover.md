---
title: DNS-records maken op Hover voor Office 365
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Hover voor Office 365.
ms.openlocfilehash: 7884038dcd1ebc7b13bbed44d98f0d5172015cc1
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211701"
---
# <a name="create-dns-records-at-hover-for-office-365"></a><span data-ttu-id="6fb33-103">DNS-records maken op Hover voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6fb33-103">Create DNS records at Hover for Office 365</span></span>

 <span data-ttu-id="6fb33-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="6fb33-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6fb33-105">Als Hover uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="6fb33-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="6fb33-106">Nadat u deze records bij Hover hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="6fb33-106">After you add these records at Hover, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="6fb33-107">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fb33-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="6fb33-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6fb33-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6fb33-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="6fb33-111">Add a TXT record for verification</span></span>
<span data-ttu-id="6fb33-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6fb33-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6fb33-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="6fb33-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6fb33-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="6fb33-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="6fb33-117">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6fb33-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6fb33-p104">Als u wilt beginnen, gaat u [via deze koppeling](https://www.hover.com/domains) naar uw pagina met domeinen bij Hover. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6fb33-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="6fb33-121">Selecteer **onder Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6fb33-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="6fb33-123">Selecteer het **tabblad DNS.**</span><span class="sxs-lookup"><span data-stu-id="6fb33-123">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="6fb33-125">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-125">Select **Add New**.</span></span>
    
    ![Nieuw toevoegen selecteren](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="6fb33-127">Selecteer in de vakken voor de nieuwe record de optie **TXT** voor het **recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="6fb33-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="6fb33-128">Hostname</span><span class="sxs-lookup"><span data-stu-id="6fb33-128">Hostname</span></span>  <br/> |<span data-ttu-id="6fb33-129">Recordtype</span><span class="sxs-lookup"><span data-stu-id="6fb33-129">Record Type</span></span>  <br/> |<span data-ttu-id="6fb33-130">Value</span><span class="sxs-lookup"><span data-stu-id="6fb33-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="6fb33-131">TXT</span><span class="sxs-lookup"><span data-stu-id="6fb33-131">TXT</span></span>  <br/> |<span data-ttu-id="6fb33-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6fb33-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6fb33-p105">**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="6fb33-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="6fb33-137">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-137">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="6fb33-139">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="6fb33-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6fb33-140">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="6fb33-140">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="6fb33-141">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="6fb33-141">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6fb33-142">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="6fb33-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6fb33-143">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="6fb33-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6fb33-144">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6fb33-145">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6fb33-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6fb33-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="6fb33-149">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="6fb33-149">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="6fb33-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6fb33-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="6fb33-151">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6fb33-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6fb33-p107">Als u wilt beginnen, gaat u [via deze koppeling](https://www.hover.com/domains) naar uw pagina met domeinen bij Hover. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6fb33-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="6fb33-155">Selecteer **onder Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6fb33-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="6fb33-157">Selecteer het **tabblad DNS.**</span><span class="sxs-lookup"><span data-stu-id="6fb33-157">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="6fb33-159">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-159">Select **Add New**.</span></span>
    
    ![Nieuw toevoegen selecteren](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="6fb33-161">Selecteer in de vakken voor de nieuwe record de optie **MX** voor het **recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="6fb33-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6fb33-162">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="6fb33-162">**Hostname**</span></span>|<span data-ttu-id="6fb33-163">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="6fb33-163">**Record Type**</span></span>|<span data-ttu-id="6fb33-164">**Priority**</span><span class="sxs-lookup"><span data-stu-id="6fb33-164">**Priority**</span></span>|<span data-ttu-id="6fb33-165">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="6fb33-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="6fb33-166">MX</span><span class="sxs-lookup"><span data-stu-id="6fb33-166">MX</span></span>  <br/> |<span data-ttu-id="6fb33-167">0</span><span class="sxs-lookup"><span data-stu-id="6fb33-167">0</span></span>  <br/> <span data-ttu-id="6fb33-168">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="6fb33-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="6fb33-169">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6fb33-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6fb33-170">**Let op:** Haal uw \* \<domeinsleutel\> \* op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="6fb33-170">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="6fb33-171">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="6fb33-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="6fb33-173">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-173">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="6fb33-175">Als er andere MX-records zijn, verwijdert u deze met behulp van de volgende tweestapsprocedure:</span><span class="sxs-lookup"><span data-stu-id="6fb33-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="6fb33-176">Selecteer eerst het mousing over een record die u wilt verwijderen **.**</span><span class="sxs-lookup"><span data-stu-id="6fb33-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Muis over en selecteer Verwijderen](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="6fb33-178">Ten tweede selecteert u **Ja** om elke verwijdering te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="6fb33-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Selecteer Ja om verwijdering te bevestigen](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="6fb33-180">Herhaal dit proces tot u alle MX-records hebt verwijderd, behalve die welke u eerder in deze procedure hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="6fb33-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="6fb33-181">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="6fb33-181">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="6fb33-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6fb33-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="6fb33-183">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6fb33-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6fb33-p109">Als u wilt beginnen, gaat u [via deze koppeling](https://www.hover.com/domains) naar uw pagina met domeinen bij Hover. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6fb33-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="6fb33-187">Selecteer **onder Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6fb33-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="6fb33-189">Selecteer het **tabblad DNS.**</span><span class="sxs-lookup"><span data-stu-id="6fb33-189">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="6fb33-191">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="6fb33-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="6fb33-192">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-192">Select **Add New**.</span></span>
    
    ![Nieuw toevoegen selecteren](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="6fb33-194">Selecteer in de lege vakken voor de nieuwe record de optie **CNAME** voor het **recordtype** en typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="6fb33-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="6fb33-195">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="6fb33-195">**Hostname**</span></span>|<span data-ttu-id="6fb33-196">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="6fb33-196">**Record Type**</span></span>|<span data-ttu-id="6fb33-197">**Doelhost**</span><span class="sxs-lookup"><span data-stu-id="6fb33-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="6fb33-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6fb33-198">autodiscover</span></span>  <br/> |<span data-ttu-id="6fb33-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="6fb33-199">CNAME</span></span>  <br/> |<span data-ttu-id="6fb33-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6fb33-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="6fb33-201">sip</span><span class="sxs-lookup"><span data-stu-id="6fb33-201">sip</span></span>  <br/> |<span data-ttu-id="6fb33-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="6fb33-202">CNAME</span></span>  <br/> |<span data-ttu-id="6fb33-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6fb33-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6fb33-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6fb33-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6fb33-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="6fb33-205">CNAME</span></span>  <br/> |<span data-ttu-id="6fb33-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6fb33-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6fb33-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6fb33-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6fb33-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="6fb33-208">CNAME</span></span>  <br/> |<span data-ttu-id="6fb33-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6fb33-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="6fb33-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6fb33-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6fb33-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="6fb33-211">CNAME</span></span>  <br/> |<span data-ttu-id="6fb33-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6fb33-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="6fb33-214">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-214">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="6fb33-216">Met de voorgaande drie stappen en de waarden uit de andere vijf rijen in de tabel voegt u de andere vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="6fb33-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6fb33-217">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="6fb33-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6fb33-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6fb33-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fb33-219">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="6fb33-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6fb33-220">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="6fb33-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6fb33-221">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="6fb33-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="6fb33-222">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="6fb33-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="6fb33-223">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6fb33-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6fb33-p111">Als u wilt beginnen, gaat u [via deze koppeling](https://www.hover.com/domains) naar uw pagina met domeinen bij Hover. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6fb33-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="6fb33-227">Selecteer **onder Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6fb33-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="6fb33-229">Selecteer het **tabblad DNS.**</span><span class="sxs-lookup"><span data-stu-id="6fb33-229">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="6fb33-231">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-231">Select **Add New**.</span></span>
    
    ![Nieuw toevoegen selecteren](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="6fb33-233">Selecteer in de vakken voor de nieuwe record de optie **TXT** voor het **Recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="6fb33-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6fb33-234">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="6fb33-234">**Hostname**</span></span>|<span data-ttu-id="6fb33-235">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="6fb33-235">**Record Type**</span></span>|<span data-ttu-id="6fb33-236">**Value**</span><span class="sxs-lookup"><span data-stu-id="6fb33-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="6fb33-237">TXT</span><span class="sxs-lookup"><span data-stu-id="6fb33-237">TXT</span></span>  <br/> |<span data-ttu-id="6fb33-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6fb33-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="6fb33-239">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="6fb33-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="6fb33-241">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-241">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="6fb33-243">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="6fb33-243">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="6fb33-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6fb33-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="6fb33-245">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6fb33-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6fb33-p112">Als u wilt beginnen, gaat u [via deze koppeling](https://www.hover.com/domains) naar uw pagina met domeinen bij Hover. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6fb33-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="6fb33-249">Selecteer **onder Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6fb33-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="6fb33-251">Selecteer het **tabblad DNS.**</span><span class="sxs-lookup"><span data-stu-id="6fb33-251">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="6fb33-253">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="6fb33-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="6fb33-254">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-254">Select **Add New**.</span></span>
    
    ![Nieuw toevoegen selecteren](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="6fb33-256">Selecteer in de lege vakken voor de nieuwe record de optie **SRV** voor het **recordtype** en typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="6fb33-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="6fb33-257">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="6fb33-257">**Hostname**</span></span>|<span data-ttu-id="6fb33-258">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="6fb33-258">**Record Type**</span></span>|<span data-ttu-id="6fb33-259">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="6fb33-259">**Priority**</span></span>|<span data-ttu-id="6fb33-260">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="6fb33-260">**Weight**</span></span>|<span data-ttu-id="6fb33-261">**Poort**</span><span class="sxs-lookup"><span data-stu-id="6fb33-261">**Port**</span></span>|<span data-ttu-id="6fb33-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="6fb33-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6fb33-263">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="6fb33-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="6fb33-264">SRV</span><span class="sxs-lookup"><span data-stu-id="6fb33-264">SRV</span></span>  <br/> |<span data-ttu-id="6fb33-265">100</span><span class="sxs-lookup"><span data-stu-id="6fb33-265">100</span></span>  <br/> |<span data-ttu-id="6fb33-266">1</span><span class="sxs-lookup"><span data-stu-id="6fb33-266">1</span></span>  <br/> |<span data-ttu-id="6fb33-267">443</span><span class="sxs-lookup"><span data-stu-id="6fb33-267">443</span></span>  <br/> |<span data-ttu-id="6fb33-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6fb33-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6fb33-269">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="6fb33-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="6fb33-270">SRV</span><span class="sxs-lookup"><span data-stu-id="6fb33-270">SRV</span></span>  <br/> |<span data-ttu-id="6fb33-271">100</span><span class="sxs-lookup"><span data-stu-id="6fb33-271">100</span></span>  <br/> |<span data-ttu-id="6fb33-272">1</span><span class="sxs-lookup"><span data-stu-id="6fb33-272">1</span></span>  <br/> |<span data-ttu-id="6fb33-273">5061</span><span class="sxs-lookup"><span data-stu-id="6fb33-273">5061</span></span>  <br/> |<span data-ttu-id="6fb33-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6fb33-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="6fb33-276">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6fb33-276">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="6fb33-278">Met de drie voorgaande stappen en de waarden uit de tweede rij in de tabel voegt u de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="6fb33-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6fb33-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6fb33-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
