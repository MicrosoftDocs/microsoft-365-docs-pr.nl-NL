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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op eNomCentral voor Microsoft.
ms.openlocfilehash: 33231896b69c0883bc9af3153fa57533096a1a0f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629573"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="de684-103">DNS-records maken bij eNomCentral voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="de684-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="de684-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="de684-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="de684-105">Als eNomCentral uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="de684-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="de684-106">Nadat u deze records hebt toegevoegd bij eNomCentral, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="de684-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="de684-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="de684-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="de684-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="de684-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="de684-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="de684-111">Add a TXT record for verification</span></span>
<span data-ttu-id="de684-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="de684-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="de684-113">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="de684-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="de684-114">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="de684-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="de684-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="de684-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="de684-117">Volg onderstaande stappen of [bekijk de video (start op 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="de684-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="de684-p104">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="de684-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="de684-121">Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="de684-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="de684-123">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="de684-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het te maken](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="de684-125">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="de684-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="de684-126">(Kies in de vervolgkeuzelijst de waarde **Record Type**.)</span><span class="sxs-lookup"><span data-stu-id="de684-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="de684-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="de684-127">**Host Name**</span></span> <br/> |<span data-ttu-id="de684-128">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="de684-128">**Record Type**</span></span> <br/> |<span data-ttu-id="de684-129">**Address**</span><span class="sxs-lookup"><span data-stu-id="de684-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="de684-130">TXT</span><span class="sxs-lookup"><span data-stu-id="de684-130">TXT</span></span>  <br/> |<span data-ttu-id="de684-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="de684-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="de684-132">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="de684-132">**Note:** This is an example.</span></span> <span data-ttu-id="de684-133">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="de684-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="de684-134">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="de684-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Afbeelding van het te maken](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="de684-136">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="de684-136">Select **save**.</span></span>
    
    ![Afbeelding van het te maken](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="de684-138">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="de684-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="de684-139">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft 365 en vraagt u Microsoft 365 om de record te zoeken.</span><span class="sxs-lookup"><span data-stu-id="de684-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="de684-140">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="de684-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="de684-141">Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="de684-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="de684-142">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="de684-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="de684-143">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="de684-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="de684-144">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="de684-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="de684-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="de684-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="de684-148">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="de684-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="de684-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="de684-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="de684-150">Volg onderstaande stappen of [bekijk de video (start op 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="de684-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="de684-p107">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="de684-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="de684-154">Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="de684-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="de684-156">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Email Settings**.</span><span class="sxs-lookup"><span data-stu-id="de684-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![Afbeelding van het te maken](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="de684-158">Kies in de vervolgkeuzelijst **Service Selection** de optie **User (MX)**.</span><span class="sxs-lookup"><span data-stu-id="de684-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![Afbeelding van het te maken](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="de684-160">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="de684-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="de684-161">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="de684-161">**Host Name**</span></span>|<span data-ttu-id="de684-162">**Address**</span><span class="sxs-lookup"><span data-stu-id="de684-162">**Address**</span></span>|<span data-ttu-id="de684-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="de684-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="de684-164">*\<domeinsleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="de684-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="de684-165">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="de684-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="de684-166">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="de684-166">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="de684-167">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="de684-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="de684-168">10</span><span class="sxs-lookup"><span data-stu-id="de684-168">10</span></span>  <br/> <span data-ttu-id="de684-169">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="de684-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![Afbeelding van het te maken](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="de684-171">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="de684-171">Select **save**.</span></span>
    
    ![Afbeelding van het te maken](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="de684-173">Als er andere MX-records zijn, schakelt u de selectievakjes voor deze records in om deze te selecteren.</span><span class="sxs-lookup"><span data-stu-id="de684-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![Afbeelding van het te maken](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="de684-175">Selecteer **aangevinkt verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="de684-175">Select **delete checked**.</span></span>
    
    ![Afbeelding van het te maken](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="de684-177">De CNAME-records toevoegen die voor Microsoft vereist zijn</span><span class="sxs-lookup"><span data-stu-id="de684-177">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="de684-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="de684-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="de684-179">Volg onderstaande stappen of [bekijk de video (start op 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="de684-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="de684-p109">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="de684-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="de684-183">Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="de684-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="de684-185">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="de684-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het te maken](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="de684-187">Selecteer **nieuwe rij**.</span><span class="sxs-lookup"><span data-stu-id="de684-187">Select **new row**.</span></span>
    
    ![Afbeelding van het te maken](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="de684-189">Typ of kopieer en plak de volgende waarden in de vakken voor de zes nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="de684-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="de684-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="de684-190">**Host Name**</span></span>|<span data-ttu-id="de684-191">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="de684-191">**Record Type**</span></span>|<span data-ttu-id="de684-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="de684-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="de684-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="de684-193">autodiscover</span></span>  <br/> |<span data-ttu-id="de684-194">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="de684-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="de684-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="de684-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="de684-196">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="de684-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="de684-197">sip</span><span class="sxs-lookup"><span data-stu-id="de684-197">sip</span></span>  <br/> |<span data-ttu-id="de684-198">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="de684-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="de684-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="de684-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="de684-200">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="de684-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="de684-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="de684-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="de684-202">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="de684-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="de684-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="de684-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="de684-204">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="de684-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="de684-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="de684-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="de684-206">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="de684-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="de684-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="de684-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="de684-208">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="de684-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="de684-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="de684-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="de684-210">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="de684-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="de684-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="de684-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="de684-212">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="de684-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Afbeelding van het te maken](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="de684-214">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="de684-214">Select **save**.</span></span>
    
    ![Afbeelding van het te maken](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="de684-216">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="de684-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="de684-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="de684-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de684-218">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="de684-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="de684-219">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="de684-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="de684-220">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="de684-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="de684-221">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="de684-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="de684-222">Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="de684-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="de684-p111">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="de684-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="de684-226">Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="de684-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="de684-228">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="de684-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het te maken](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="de684-230">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="de684-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="de684-231">(Kies in de vervolgkeuzelijst de waarde **Record Type**.)</span><span class="sxs-lookup"><span data-stu-id="de684-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="de684-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="de684-232">**Host Name**</span></span>|<span data-ttu-id="de684-233">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="de684-233">**Record Type**</span></span>|<span data-ttu-id="de684-234">**Address**</span><span class="sxs-lookup"><span data-stu-id="de684-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="de684-235">TXT</span><span class="sxs-lookup"><span data-stu-id="de684-235">TXT</span></span>  <br/> |<span data-ttu-id="de684-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="de684-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="de684-237">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="de684-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Afbeelding van het te maken](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="de684-239">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="de684-239">Select **save**.</span></span>
    
    ![Afbeelding van het te maken](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="de684-241">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="de684-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="de684-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="de684-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="de684-243">Volg onderstaande stappen of [bekijk de video (start op 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="de684-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="de684-p112">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="de684-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="de684-247">Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="de684-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="de684-249">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="de684-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het te maken](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="de684-251">Selecteer Rechts van **de nieuwe rij**De optie **SRV- of SPF-record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="de684-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![Afbeelding van het te maken](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="de684-253">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="de684-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="de684-254">**Service**</span><span class="sxs-lookup"><span data-stu-id="de684-254">**Service**</span></span>|<span data-ttu-id="de684-255">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="de684-255">**Protocol**</span></span>|<span data-ttu-id="de684-256">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="de684-256">**Priority**</span></span>|<span data-ttu-id="de684-257">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="de684-257">**Weight**</span></span>|<span data-ttu-id="de684-258">**Poort**</span><span class="sxs-lookup"><span data-stu-id="de684-258">**Port**</span></span>|<span data-ttu-id="de684-259">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="de684-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de684-260">_sip</span><span class="sxs-lookup"><span data-stu-id="de684-260">_sip</span></span>  <br/> |<span data-ttu-id="de684-261">_tls</span><span class="sxs-lookup"><span data-stu-id="de684-261">_tls</span></span>  <br/> |<span data-ttu-id="de684-262">100</span><span class="sxs-lookup"><span data-stu-id="de684-262">100</span></span>  <br/> |<span data-ttu-id="de684-263">1</span><span class="sxs-lookup"><span data-stu-id="de684-263">1</span></span>  <br/> |<span data-ttu-id="de684-264">443</span><span class="sxs-lookup"><span data-stu-id="de684-264">443</span></span>  <br/> |<span data-ttu-id="de684-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="de684-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="de684-266">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="de684-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="de684-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="de684-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="de684-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="de684-268">_tcp</span></span>  <br/> |<span data-ttu-id="de684-269">100</span><span class="sxs-lookup"><span data-stu-id="de684-269">100</span></span>  <br/> |<span data-ttu-id="de684-270">1</span><span class="sxs-lookup"><span data-stu-id="de684-270">1</span></span>  <br/> |<span data-ttu-id="de684-271">5061</span><span class="sxs-lookup"><span data-stu-id="de684-271">5061</span></span>  <br/> |<span data-ttu-id="de684-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="de684-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="de684-273">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="de684-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Afbeelding van het te maken](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="de684-275">Selecteer **opslaan**</span><span class="sxs-lookup"><span data-stu-id="de684-275">Select **save**</span></span>
    
    ![Afbeelding van het te maken](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="de684-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="de684-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

