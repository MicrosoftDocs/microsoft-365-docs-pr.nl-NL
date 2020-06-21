---
title: DNS-records maken bij Hover for Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij Hover voor Microsoft.
ms.openlocfilehash: e51cb77831f4e29ac3a51602a1bb19f8b0c9e0e3
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780347"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="4b057-103">DNS-records maken bij Hover for Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b057-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="4b057-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="4b057-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4b057-105">Als Hover uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="4b057-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="4b057-106">Nadat u deze records hebt toegevoegd bij Hover, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="4b057-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="4b057-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="4b057-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4b057-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="4b057-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4b057-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4b057-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4b057-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="4b057-110">Add a TXT record for verification</span></span>
<span data-ttu-id="4b057-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4b057-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4b057-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="4b057-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="4b057-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="4b057-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b057-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="4b057-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="4b057-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="4b057-115">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="4b057-116">Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="4b057-116">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="4b057-117">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="4b057-117">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="4b057-118">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="4b057-118">You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="4b057-120">Selecteer onder **Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="4b057-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="4b057-122">Selecteer het tabblad **DNS.**</span><span class="sxs-lookup"><span data-stu-id="4b057-122">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="4b057-124">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4b057-124">Select **Add New**.</span></span>
    
    ![Selecteer Nieuw toevoegen](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="4b057-126">Selecteer in de vakken voor de nieuwe record de optie **TXT** voor het **recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="4b057-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="4b057-127">Hostname</span><span class="sxs-lookup"><span data-stu-id="4b057-127">Hostname</span></span>  <br/> |<span data-ttu-id="4b057-128">Recordtype</span><span class="sxs-lookup"><span data-stu-id="4b057-128">Record Type</span></span>  <br/> |<span data-ttu-id="4b057-129">Value</span><span class="sxs-lookup"><span data-stu-id="4b057-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="4b057-130">TXT</span><span class="sxs-lookup"><span data-stu-id="4b057-130">TXT</span></span>  <br/> |<span data-ttu-id="4b057-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4b057-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4b057-132">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="4b057-132">**Note:** This is an example.</span></span> <span data-ttu-id="4b057-133">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="4b057-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="4b057-134">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="4b057-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="4b057-136">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4b057-136">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="4b057-138">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="4b057-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4b057-139">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="4b057-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="4b057-140">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="4b057-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4b057-141">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="4b057-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="4b057-142">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="4b057-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4b057-143">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="4b057-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4b057-144">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="4b057-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="4b057-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="4b057-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4b057-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="4b057-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4b057-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4b057-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4b057-148">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="4b057-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4b057-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4b057-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="4b057-150">Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="4b057-150">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="4b057-151">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="4b057-151">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="4b057-152">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="4b057-152">You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="4b057-154">Selecteer onder **Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="4b057-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="4b057-156">Selecteer het tabblad **DNS.**</span><span class="sxs-lookup"><span data-stu-id="4b057-156">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="4b057-158">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4b057-158">Select **Add New**.</span></span>
    
    ![Selecteer Nieuw toevoegen](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="4b057-160">Selecteer in de vakken voor de nieuwe record de optie **MX** voor het **recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="4b057-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="4b057-161">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="4b057-161">**Hostname**</span></span>|<span data-ttu-id="4b057-162">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="4b057-162">**Record Type**</span></span>|<span data-ttu-id="4b057-163">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4b057-163">**Priority**</span></span>|<span data-ttu-id="4b057-164">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="4b057-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="4b057-165">MX</span><span class="sxs-lookup"><span data-stu-id="4b057-165">MX</span></span>  <br/> |<span data-ttu-id="4b057-166">0</span><span class="sxs-lookup"><span data-stu-id="4b057-166">0</span></span>  <br/> <span data-ttu-id="4b057-167">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="4b057-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="4b057-168">*\<domain-key\>*,,Mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4b057-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4b057-169">**Let op:** Haal je *\<domain-key\>* van je Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="4b057-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="4b057-170">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="4b057-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="4b057-172">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4b057-172">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="4b057-174">Als er andere MX-records zijn, verwijdert u deze met behulp van de volgende tweestapsprocedure:</span><span class="sxs-lookup"><span data-stu-id="4b057-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="4b057-175">Selecteer eerst verwijderen door een record te **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="4b057-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Muis over en selecteer Verwijderen](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="4b057-177">Selecteer ten tweede **Ja** om elke verwijdering te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="4b057-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Selecteer Ja om verwijdering te bevestigen](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="4b057-179">Herhaal dit proces tot u alle MX-records hebt verwijderd, behalve die welke u eerder in deze procedure hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="4b057-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4b057-180">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b057-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="4b057-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4b057-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="4b057-182">Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="4b057-182">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="4b057-183">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="4b057-183">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="4b057-184">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="4b057-184">You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="4b057-186">Selecteer onder **Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="4b057-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="4b057-188">Selecteer het tabblad **DNS.**</span><span class="sxs-lookup"><span data-stu-id="4b057-188">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="4b057-190">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="4b057-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="4b057-191">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4b057-191">Select **Add New**.</span></span>
    
    ![Selecteer Nieuw toevoegen](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="4b057-193">Selecteer in de lege vakken voor de nieuwe record de optie **CNAME** voor het **recordtype** en typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="4b057-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="4b057-194">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="4b057-194">**Hostname**</span></span>|<span data-ttu-id="4b057-195">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="4b057-195">**Record Type**</span></span>|<span data-ttu-id="4b057-196">**Doelhost**</span><span class="sxs-lookup"><span data-stu-id="4b057-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4b057-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4b057-197">autodiscover</span></span>  <br/> |<span data-ttu-id="4b057-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b057-198">CNAME</span></span>  <br/> |<span data-ttu-id="4b057-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4b057-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="4b057-200">sip</span><span class="sxs-lookup"><span data-stu-id="4b057-200">sip</span></span>  <br/> |<span data-ttu-id="4b057-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b057-201">CNAME</span></span>  <br/> |<span data-ttu-id="4b057-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b057-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4b057-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4b057-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4b057-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b057-204">CNAME</span></span>  <br/> |<span data-ttu-id="4b057-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b057-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4b057-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4b057-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4b057-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b057-207">CNAME</span></span>  <br/> |<span data-ttu-id="4b057-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4b057-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="4b057-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4b057-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4b057-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b057-210">CNAME</span></span>  <br/> |<span data-ttu-id="4b057-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4b057-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="4b057-213">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4b057-213">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="4b057-215">Met de voorgaande drie stappen en de waarden uit de andere vijf rijen in de tabel voegt u de andere vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="4b057-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4b057-216">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="4b057-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4b057-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4b057-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b057-218">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="4b057-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4b057-219">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="4b057-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4b057-220">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b057-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="4b057-221">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="4b057-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="4b057-222">Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="4b057-222">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="4b057-223">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="4b057-223">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="4b057-224">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="4b057-224">You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="4b057-226">Selecteer onder **Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="4b057-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="4b057-228">Selecteer het tabblad **DNS.**</span><span class="sxs-lookup"><span data-stu-id="4b057-228">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="4b057-230">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4b057-230">Select **Add New**.</span></span>
    
    ![Selecteer Nieuw toevoegen](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="4b057-232">Selecteer in de vakken voor de nieuwe record de optie **TXT** voor het **Recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="4b057-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="4b057-233">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="4b057-233">**Hostname**</span></span>|<span data-ttu-id="4b057-234">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="4b057-234">**Record Type**</span></span>|<span data-ttu-id="4b057-235">**Value**</span><span class="sxs-lookup"><span data-stu-id="4b057-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="4b057-236">TXT</span><span class="sxs-lookup"><span data-stu-id="4b057-236">TXT</span></span>  <br/> |<span data-ttu-id="4b057-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4b057-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="4b057-238">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="4b057-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="4b057-240">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4b057-240">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4b057-242">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b057-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4b057-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4b057-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="4b057-244">Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="4b057-244">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="4b057-245">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="4b057-245">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="4b057-246">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="4b057-246">You'll be prompted to sign in.</span></span>
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="4b057-248">Selecteer onder **Uw domeinen beheren**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="4b057-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="4b057-250">Selecteer het tabblad **DNS.**</span><span class="sxs-lookup"><span data-stu-id="4b057-250">Select the **DNS** tab.</span></span> 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="4b057-252">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="4b057-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="4b057-253">Selecteer **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4b057-253">Select **Add New**.</span></span>
    
    ![Selecteer Nieuw toevoegen](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="4b057-255">Selecteer in de lege vakken voor de nieuwe record de optie **SRV** voor het **recordtype** en typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="4b057-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="4b057-256">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="4b057-256">**Hostname**</span></span>|<span data-ttu-id="4b057-257">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="4b057-257">**Record Type**</span></span>|<span data-ttu-id="4b057-258">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="4b057-258">**Priority**</span></span>|<span data-ttu-id="4b057-259">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="4b057-259">**Weight**</span></span>|<span data-ttu-id="4b057-260">**Poort**</span><span class="sxs-lookup"><span data-stu-id="4b057-260">**Port**</span></span>|<span data-ttu-id="4b057-261">**Target**</span><span class="sxs-lookup"><span data-stu-id="4b057-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b057-262">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="4b057-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="4b057-263">SRV</span><span class="sxs-lookup"><span data-stu-id="4b057-263">SRV</span></span>  <br/> |<span data-ttu-id="4b057-264">100</span><span class="sxs-lookup"><span data-stu-id="4b057-264">100</span></span>  <br/> |<span data-ttu-id="4b057-265">1</span><span class="sxs-lookup"><span data-stu-id="4b057-265">1</span></span>  <br/> |<span data-ttu-id="4b057-266">443</span><span class="sxs-lookup"><span data-stu-id="4b057-266">443</span></span>  <br/> |<span data-ttu-id="4b057-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b057-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4b057-268">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="4b057-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="4b057-269">SRV</span><span class="sxs-lookup"><span data-stu-id="4b057-269">SRV</span></span>  <br/> |<span data-ttu-id="4b057-270">100</span><span class="sxs-lookup"><span data-stu-id="4b057-270">100</span></span>  <br/> |<span data-ttu-id="4b057-271">1</span><span class="sxs-lookup"><span data-stu-id="4b057-271">1</span></span>  <br/> |<span data-ttu-id="4b057-272">5061</span><span class="sxs-lookup"><span data-stu-id="4b057-272">5061</span></span>  <br/> |<span data-ttu-id="4b057-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b057-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="4b057-275">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4b057-275">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="4b057-277">Met de drie voorgaande stappen en de waarden uit de tweede rij in de tabel voegt u de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="4b057-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4b057-278">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="4b057-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="4b057-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="4b057-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="4b057-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4b057-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
