---
title: DNS-records maken bij Hover voor Microsoft
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
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Hover voor Microsoft.
ms.openlocfilehash: 328020dffe5d6549f7a0418a01d99b18ef9c5035
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629513"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="8d68a-103">DNS-records maken bij Hover voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d68a-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="8d68a-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="8d68a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8d68a-105">Als Hover uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="8d68a-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="8d68a-106">Nadat u deze records bij Hover hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="8d68a-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="8d68a-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="8d68a-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="8d68a-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8d68a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8d68a-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="8d68a-111">Add a TXT record for verification</span></span>
<span data-ttu-id="8d68a-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8d68a-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8d68a-113">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="8d68a-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="8d68a-114">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="8d68a-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d68a-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8d68a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="8d68a-117">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8d68a-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8d68a-p104">Als u wilt beginnen, gaat u [via deze koppeling](https://www.hover.com/domains) naar uw pagina met domeinen bij Hover. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8d68a-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="8d68a-121">Selecteer **onder Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="8d68a-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="8d68a-123">Selecteer het **tabblad DNS.**</span><span class="sxs-lookup"><span data-stu-id="8d68a-123">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="8d68a-125">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-125">Select **Add New**.</span></span>
    
    ![Nieuw toevoegen selecteren](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="8d68a-127">Selecteer in de vakken voor de nieuwe record de optie **TXT** voor het **recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="8d68a-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="8d68a-128">Hostname</span><span class="sxs-lookup"><span data-stu-id="8d68a-128">Hostname</span></span>  <br/> |<span data-ttu-id="8d68a-129">Recordtype</span><span class="sxs-lookup"><span data-stu-id="8d68a-129">Record Type</span></span>  <br/> |<span data-ttu-id="8d68a-130">Value</span><span class="sxs-lookup"><span data-stu-id="8d68a-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="8d68a-131">TXT</span><span class="sxs-lookup"><span data-stu-id="8d68a-131">TXT</span></span>  <br/> |<span data-ttu-id="8d68a-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8d68a-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8d68a-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8d68a-133">**Note:** This is an example.</span></span> <span data-ttu-id="8d68a-134">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="8d68a-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="8d68a-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="8d68a-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="8d68a-137">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-137">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="8d68a-139">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8d68a-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8d68a-140">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft 365 en vraagt u Microsoft 365 om de record te zoeken.</span><span class="sxs-lookup"><span data-stu-id="8d68a-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="8d68a-141">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="8d68a-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8d68a-142">Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="8d68a-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8d68a-143">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="8d68a-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8d68a-144">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8d68a-145">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8d68a-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8d68a-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8d68a-149">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="8d68a-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8d68a-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8d68a-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="8d68a-151">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8d68a-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8d68a-p107">Als u wilt beginnen, gaat u [via deze koppeling](https://www.hover.com/domains) naar uw pagina met domeinen bij Hover. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8d68a-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="8d68a-155">Selecteer **onder Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="8d68a-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="8d68a-157">Selecteer het **tabblad DNS.**</span><span class="sxs-lookup"><span data-stu-id="8d68a-157">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="8d68a-159">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-159">Select **Add New**.</span></span>
    
    ![Nieuw toevoegen selecteren](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="8d68a-161">Selecteer in de vakken voor de nieuwe record de optie **MX** voor het **recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="8d68a-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8d68a-162">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="8d68a-162">**Hostname**</span></span>|<span data-ttu-id="8d68a-163">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="8d68a-163">**Record Type**</span></span>|<span data-ttu-id="8d68a-164">**Priority**</span><span class="sxs-lookup"><span data-stu-id="8d68a-164">**Priority**</span></span>|<span data-ttu-id="8d68a-165">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="8d68a-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8d68a-166">MX</span><span class="sxs-lookup"><span data-stu-id="8d68a-166">MX</span></span>  <br/> |<span data-ttu-id="8d68a-167">0</span><span class="sxs-lookup"><span data-stu-id="8d68a-167">0</span></span>  <br/> <span data-ttu-id="8d68a-168">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="8d68a-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="8d68a-169">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8d68a-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="8d68a-170">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="8d68a-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="8d68a-171">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="8d68a-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="8d68a-173">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-173">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="8d68a-175">Als er andere MX-records zijn, verwijdert u deze met behulp van de volgende tweestapsprocedure:</span><span class="sxs-lookup"><span data-stu-id="8d68a-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="8d68a-176">Selecteer eerst het mousing over een record die u wilt verwijderen **.**</span><span class="sxs-lookup"><span data-stu-id="8d68a-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Muis over en selecteer Verwijderen](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="8d68a-178">Ten tweede selecteert u **Ja** om elke verwijdering te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="8d68a-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Selecteer Ja om verwijdering te bevestigen](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="8d68a-180">Herhaal dit proces tot u alle MX-records hebt verwijderd, behalve die welke u eerder in deze procedure hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="8d68a-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8d68a-181">De CNAME-records toevoegen die voor Microsoft vereist zijn</span><span class="sxs-lookup"><span data-stu-id="8d68a-181">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8d68a-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8d68a-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="8d68a-183">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8d68a-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8d68a-p109">Als u wilt beginnen, gaat u [via deze koppeling](https://www.hover.com/domains) naar uw pagina met domeinen bij Hover. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8d68a-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="8d68a-187">Selecteer **onder Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="8d68a-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="8d68a-189">Selecteer het **tabblad DNS.**</span><span class="sxs-lookup"><span data-stu-id="8d68a-189">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="8d68a-191">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="8d68a-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="8d68a-192">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-192">Select **Add New**.</span></span>
    
    ![Nieuw toevoegen selecteren](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="8d68a-194">Selecteer in de lege vakken voor de nieuwe record de optie **CNAME** voor het **recordtype** en typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="8d68a-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="8d68a-195">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="8d68a-195">**Hostname**</span></span>|<span data-ttu-id="8d68a-196">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="8d68a-196">**Record Type**</span></span>|<span data-ttu-id="8d68a-197">**Doelhost**</span><span class="sxs-lookup"><span data-stu-id="8d68a-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8d68a-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8d68a-198">autodiscover</span></span>  <br/> |<span data-ttu-id="8d68a-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d68a-199">CNAME</span></span>  <br/> |<span data-ttu-id="8d68a-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8d68a-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="8d68a-201">sip</span><span class="sxs-lookup"><span data-stu-id="8d68a-201">sip</span></span>  <br/> |<span data-ttu-id="8d68a-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d68a-202">CNAME</span></span>  <br/> |<span data-ttu-id="8d68a-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d68a-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8d68a-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8d68a-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8d68a-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d68a-205">CNAME</span></span>  <br/> |<span data-ttu-id="8d68a-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d68a-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8d68a-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8d68a-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8d68a-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d68a-208">CNAME</span></span>  <br/> |<span data-ttu-id="8d68a-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8d68a-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="8d68a-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8d68a-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8d68a-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="8d68a-211">CNAME</span></span>  <br/> |<span data-ttu-id="8d68a-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8d68a-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="8d68a-214">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-214">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="8d68a-216">Met de voorgaande drie stappen en de waarden uit de andere vijf rijen in de tabel voegt u de andere vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="8d68a-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8d68a-217">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="8d68a-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8d68a-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8d68a-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d68a-219">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="8d68a-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8d68a-220">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="8d68a-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8d68a-221">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d68a-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8d68a-222">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="8d68a-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="8d68a-223">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8d68a-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8d68a-p111">Als u wilt beginnen, gaat u [via deze koppeling](https://www.hover.com/domains) naar uw pagina met domeinen bij Hover. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8d68a-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="8d68a-227">Selecteer **onder Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="8d68a-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="8d68a-229">Selecteer het **tabblad DNS.**</span><span class="sxs-lookup"><span data-stu-id="8d68a-229">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="8d68a-231">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-231">Select **Add New**.</span></span>
    
    ![Nieuw toevoegen selecteren](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="8d68a-233">Selecteer in de vakken voor de nieuwe record de optie **TXT** voor het **Recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="8d68a-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8d68a-234">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="8d68a-234">**Hostname**</span></span>|<span data-ttu-id="8d68a-235">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="8d68a-235">**Record Type**</span></span>|<span data-ttu-id="8d68a-236">**Value**</span><span class="sxs-lookup"><span data-stu-id="8d68a-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8d68a-237">TXT</span><span class="sxs-lookup"><span data-stu-id="8d68a-237">TXT</span></span>  <br/> |<span data-ttu-id="8d68a-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8d68a-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="8d68a-239">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="8d68a-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="8d68a-241">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-241">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8d68a-243">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d68a-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8d68a-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8d68a-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="8d68a-245">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="8d68a-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8d68a-p112">Als u wilt beginnen, gaat u [via deze koppeling](https://www.hover.com/domains) naar uw pagina met domeinen bij Hover. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="8d68a-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="8d68a-249">Selecteer **onder Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="8d68a-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="8d68a-251">Selecteer het **tabblad DNS.**</span><span class="sxs-lookup"><span data-stu-id="8d68a-251">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="8d68a-253">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="8d68a-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="8d68a-254">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-254">Select **Add New**.</span></span>
    
    ![Nieuw toevoegen selecteren](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="8d68a-256">Selecteer in de lege vakken voor de nieuwe record de optie **SRV** voor het **recordtype** en typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="8d68a-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="8d68a-257">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="8d68a-257">**Hostname**</span></span>|<span data-ttu-id="8d68a-258">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="8d68a-258">**Record Type**</span></span>|<span data-ttu-id="8d68a-259">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="8d68a-259">**Priority**</span></span>|<span data-ttu-id="8d68a-260">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="8d68a-260">**Weight**</span></span>|<span data-ttu-id="8d68a-261">**Poort**</span><span class="sxs-lookup"><span data-stu-id="8d68a-261">**Port**</span></span>|<span data-ttu-id="8d68a-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="8d68a-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8d68a-263">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="8d68a-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="8d68a-264">SRV</span><span class="sxs-lookup"><span data-stu-id="8d68a-264">SRV</span></span>  <br/> |<span data-ttu-id="8d68a-265">100</span><span class="sxs-lookup"><span data-stu-id="8d68a-265">100</span></span>  <br/> |<span data-ttu-id="8d68a-266">1</span><span class="sxs-lookup"><span data-stu-id="8d68a-266">1</span></span>  <br/> |<span data-ttu-id="8d68a-267">443</span><span class="sxs-lookup"><span data-stu-id="8d68a-267">443</span></span>  <br/> |<span data-ttu-id="8d68a-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d68a-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8d68a-269">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="8d68a-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="8d68a-270">SRV</span><span class="sxs-lookup"><span data-stu-id="8d68a-270">SRV</span></span>  <br/> |<span data-ttu-id="8d68a-271">100</span><span class="sxs-lookup"><span data-stu-id="8d68a-271">100</span></span>  <br/> |<span data-ttu-id="8d68a-272">1</span><span class="sxs-lookup"><span data-stu-id="8d68a-272">1</span></span>  <br/> |<span data-ttu-id="8d68a-273">5061</span><span class="sxs-lookup"><span data-stu-id="8d68a-273">5061</span></span>  <br/> |<span data-ttu-id="8d68a-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8d68a-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="8d68a-276">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8d68a-276">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="8d68a-278">Met de drie voorgaande stappen en de waarden uit de tweede rij in de tabel voegt u de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="8d68a-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8d68a-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8d68a-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
