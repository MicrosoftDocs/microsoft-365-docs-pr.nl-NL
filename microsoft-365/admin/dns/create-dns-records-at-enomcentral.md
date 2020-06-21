---
title: DNS-records maken bij eNomCentral voor Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij eNomCentral voor Microsoft.
ms.openlocfilehash: c964729c052f5c0b61441f14ce15a167caa06b72
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780395"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="fc5db-103">DNS-records maken bij eNomCentral voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fc5db-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="fc5db-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="fc5db-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fc5db-105">Als eNomCentral uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fc5db-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="fc5db-106">Nadat u deze records hebt toegevoegd bij eNomCentral, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="fc5db-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="fc5db-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="fc5db-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="fc5db-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="fc5db-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="fc5db-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fc5db-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fc5db-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="fc5db-110">Add a TXT record for verification</span></span>
<span data-ttu-id="fc5db-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="fc5db-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="fc5db-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="fc5db-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="fc5db-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="fc5db-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc5db-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="fc5db-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="fc5db-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="fc5db-115">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="fc5db-116">Volg onderstaande stappen of [bekijk de video (start op 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="fc5db-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="fc5db-117">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="fc5db-117">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="fc5db-118">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="fc5db-118">You'll be prompted to login.</span></span>
    
    ![Afbeelding van het knopen -1-1 van afbeelding](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="fc5db-120">Selecteer onder **mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fc5db-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="fc5db-122">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![afbeelding van het aandeel ENom-BP-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="fc5db-124">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="fc5db-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="fc5db-125">Kies de waarde **Recordtype** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fc5db-125">Choose the **Record Type** value from the drop-down list.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="fc5db-126">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="fc5db-126">**Host Name**</span></span> <br/> |<span data-ttu-id="fc5db-127">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="fc5db-127">**Record Type**</span></span> <br/> |<span data-ttu-id="fc5db-128">**Address**</span><span class="sxs-lookup"><span data-stu-id="fc5db-128">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="fc5db-129">TXT</span><span class="sxs-lookup"><span data-stu-id="fc5db-129">TXT</span></span>  <br/> |<span data-ttu-id="fc5db-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fc5db-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fc5db-131">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="fc5db-131">**Note:** This is an example.</span></span> <span data-ttu-id="fc5db-132">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="fc5db-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="fc5db-133">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="fc5db-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![afbeelding van het aandeel ENom-BP-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="fc5db-135">Selecteer **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-135">Select **save**.</span></span>
    
    ![afbeelding van het aandeel ENom-BP-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="fc5db-137">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="fc5db-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fc5db-138">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="fc5db-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="fc5db-139">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="fc5db-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fc5db-140">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="fc5db-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="fc5db-141">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="fc5db-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="fc5db-142">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="fc5db-143">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="fc5db-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="fc5db-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="fc5db-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="fc5db-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="fc5db-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fc5db-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="fc5db-147">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="fc5db-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="fc5db-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="fc5db-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="fc5db-149">Volg onderstaande stappen of [bekijk de video (start op 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="fc5db-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="fc5db-150">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="fc5db-150">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="fc5db-151">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="fc5db-151">You'll be prompted to login.</span></span>
    
    ![Afbeelding van het knopen -1-1 van afbeelding](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="fc5db-153">Selecteer onder **mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fc5db-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="fc5db-155">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Email Settings**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![Afbeelding van het knopen -1-3 afbeelding van het eNom-BP-bp-](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="fc5db-157">Kies in de vervolgkeuzelijst **Service Selection** de optie **User (MX)**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![Afbeelding van het knopen -1-4 afbeelding van het eNom-BP-](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="fc5db-159">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="fc5db-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="fc5db-160">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="fc5db-160">**Host Name**</span></span>|<span data-ttu-id="fc5db-161">**Address**</span><span class="sxs-lookup"><span data-stu-id="fc5db-161">**Address**</span></span>|<span data-ttu-id="fc5db-162">**Pref**</span><span class="sxs-lookup"><span data-stu-id="fc5db-162">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="fc5db-163">*\<domain-key\>* mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="fc5db-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="fc5db-164">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fc5db-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="fc5db-165">**Let op:** Haal je *\<domain-key\>* van je Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="fc5db-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="fc5db-166">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="fc5db-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="fc5db-167">10</span><span class="sxs-lookup"><span data-stu-id="fc5db-167">10</span></span>  <br/> <span data-ttu-id="fc5db-168">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="fc5db-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
       
   ![Afbeelding van het knopen -2-1 afbeelding van het eNom-BP-](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="fc5db-170">Selecteer **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-170">Select **save**.</span></span>
    
    ![Afbeelding van het knopen -2-2 voor afbeelding van het enom-BP-](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="fc5db-172">Als er andere MX-records zijn, schakelt u de selectievakjes voor deze records in om deze te selecteren.</span><span class="sxs-lookup"><span data-stu-id="fc5db-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![Afbeelding van het knopen -2-3 afbeelding van het eNom-BP-bp-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="fc5db-174">Selecteer **Verwijderen gecontroleerd**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-174">Select **delete checked**.</span></span>
    
    ![Afbeelding van het knopen -2-4 afbeelding van het eNom-BP-](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="fc5db-176">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fc5db-176">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="fc5db-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="fc5db-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="fc5db-178">Volg onderstaande stappen of [bekijk de video (start op 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="fc5db-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="fc5db-179">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="fc5db-179">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="fc5db-180">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="fc5db-180">You'll be prompted to login.</span></span>
    
    ![Afbeelding van het knopen -1-1 van afbeelding](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="fc5db-182">Selecteer onder **mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fc5db-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="fc5db-184">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van ENom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="fc5db-186">Selecteer **een nieuwe rij**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-186">Select **new row**.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="fc5db-188">Typ of kopieer en plak de volgende waarden in de vakken voor de zes nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="fc5db-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
<span data-ttu-id="fc5db-189">Kies de waarde **Recordtype** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fc5db-189">Choose the **Record Type** value from the drop-down list.</span></span>
        
    |<span data-ttu-id="fc5db-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="fc5db-190">**Host Name**</span></span>|<span data-ttu-id="fc5db-191">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="fc5db-191">**Record Type**</span></span>|<span data-ttu-id="fc5db-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="fc5db-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fc5db-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="fc5db-193">autodiscover</span></span>  <br/> |<span data-ttu-id="fc5db-194">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="fc5db-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="fc5db-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="fc5db-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="fc5db-196">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fc5db-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fc5db-197">sip</span><span class="sxs-lookup"><span data-stu-id="fc5db-197">sip</span></span>  <br/> |<span data-ttu-id="fc5db-198">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="fc5db-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="fc5db-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fc5db-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fc5db-200">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fc5db-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fc5db-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fc5db-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="fc5db-202">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="fc5db-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="fc5db-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fc5db-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fc5db-204">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fc5db-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fc5db-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="fc5db-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="fc5db-206">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="fc5db-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="fc5db-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="fc5db-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="fc5db-208">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fc5db-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fc5db-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="fc5db-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="fc5db-210">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="fc5db-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="fc5db-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fc5db-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="fc5db-212">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fc5db-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="fc5db-213">Selecteer **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-213">Select **save**.</span></span>
    
    ![Afbeelding van het knopen -3-3 van eNom-BP](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="fc5db-215">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="fc5db-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="fc5db-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="fc5db-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc5db-217">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="fc5db-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="fc5db-218">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="fc5db-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="fc5db-219">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fc5db-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="fc5db-220">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="fc5db-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="fc5db-221">Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="fc5db-221">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="fc5db-222">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="fc5db-222">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="fc5db-223">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="fc5db-223">You'll be prompted to login.</span></span>
    
    ![Afbeelding van het knopen -1-1 van afbeelding](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="fc5db-225">Selecteer onder **mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fc5db-225">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="fc5db-227">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van ENom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="fc5db-229">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="fc5db-229">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
<span data-ttu-id="fc5db-230">Kies de waarde **Recordtype** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="fc5db-230">Choose the **Record Type** value from the drop-down list.</span></span>
    
    |<span data-ttu-id="fc5db-231">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="fc5db-231">**Host Name**</span></span>|<span data-ttu-id="fc5db-232">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="fc5db-232">**Record Type**</span></span>|<span data-ttu-id="fc5db-233">**Address**</span><span class="sxs-lookup"><span data-stu-id="fc5db-233">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="fc5db-234">TXT</span><span class="sxs-lookup"><span data-stu-id="fc5db-234">TXT</span></span>  <br/> |<span data-ttu-id="fc5db-235">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="fc5db-235">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="fc5db-236">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="fc5db-236">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="fc5db-238">Selecteer **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-238">Select **save**.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="fc5db-240">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fc5db-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="fc5db-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="fc5db-241"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="fc5db-242">Volg onderstaande stappen of [bekijk de video (start op 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="fc5db-242">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="fc5db-243">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="fc5db-243">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="fc5db-244">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="fc5db-244">You'll be prompted to login.</span></span>
    
    ![Afbeelding van het knopen -1-1 van afbeelding](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="fc5db-246">Selecteer onder **mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fc5db-246">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="fc5db-248">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van ENom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="fc5db-250">Selecteer rechts van de **nieuwe rij** **SRV- of SPF-record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="fc5db-250">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="fc5db-252">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="fc5db-252">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="fc5db-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="fc5db-253">**Service**</span></span>|<span data-ttu-id="fc5db-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="fc5db-254">**Protocol**</span></span>|<span data-ttu-id="fc5db-255">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="fc5db-255">**Priority**</span></span>|<span data-ttu-id="fc5db-256">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="fc5db-256">**Weight**</span></span>|<span data-ttu-id="fc5db-257">**Poort**</span><span class="sxs-lookup"><span data-stu-id="fc5db-257">**Port**</span></span>|<span data-ttu-id="fc5db-258">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="fc5db-258">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fc5db-259">_sip</span><span class="sxs-lookup"><span data-stu-id="fc5db-259">_sip</span></span>  <br/> |<span data-ttu-id="fc5db-260">_tls</span><span class="sxs-lookup"><span data-stu-id="fc5db-260">_tls</span></span>  <br/> |<span data-ttu-id="fc5db-261">100</span><span class="sxs-lookup"><span data-stu-id="fc5db-261">100</span></span>  <br/> |<span data-ttu-id="fc5db-262">1</span><span class="sxs-lookup"><span data-stu-id="fc5db-262">1</span></span>  <br/> |<span data-ttu-id="fc5db-263">443</span><span class="sxs-lookup"><span data-stu-id="fc5db-263">443</span></span>  <br/> |<span data-ttu-id="fc5db-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fc5db-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="fc5db-265">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fc5db-265">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="fc5db-266">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="fc5db-266">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="fc5db-267">_tcp</span><span class="sxs-lookup"><span data-stu-id="fc5db-267">_tcp</span></span>  <br/> |<span data-ttu-id="fc5db-268">100</span><span class="sxs-lookup"><span data-stu-id="fc5db-268">100</span></span>  <br/> |<span data-ttu-id="fc5db-269">1</span><span class="sxs-lookup"><span data-stu-id="fc5db-269">1</span></span>  <br/> |<span data-ttu-id="fc5db-270">5061</span><span class="sxs-lookup"><span data-stu-id="fc5db-270">5061</span></span>  <br/> |<span data-ttu-id="fc5db-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="fc5db-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="fc5db-272">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fc5db-272">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="fc5db-274">Opslaan **selecteren**</span><span class="sxs-lookup"><span data-stu-id="fc5db-274">Select **save**</span></span>
    
    ![Afbeelding van het knopen -afbeeldingsman van ENom-BP-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="fc5db-276">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="fc5db-276">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="fc5db-277">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="fc5db-277">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="fc5db-278">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fc5db-278">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

