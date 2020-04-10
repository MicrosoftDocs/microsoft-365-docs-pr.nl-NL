---
title: DNS-records maken op eNomCentral voor Office 365
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
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op eNomCentral voor Office 365.
ms.openlocfilehash: fb10c5bc10e9e4bb231e90148dd5d5c742ff169d
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211761"
---
# <a name="create-dns-records-at-enomcentral-for-office-365"></a><span data-ttu-id="0cd4c-103">DNS-records maken op eNomCentral voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0cd4c-103">Create DNS records at eNomCentral for Office 365</span></span>

 <span data-ttu-id="0cd4c-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0cd4c-105">Als eNomCentral uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0cd4c-106">Nadat u deze records bij eNomCentral hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-106">After you add these records at eNomCentral, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="0cd4c-107">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="0cd4c-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0cd4c-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="0cd4c-111">Add a TXT record for verification</span></span>
<span data-ttu-id="0cd4c-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0cd4c-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0cd4c-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0cd4c-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="0cd4c-117">Volg onderstaande stappen of [bekijk de video (start op 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0cd4c-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0cd4c-p104">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="0cd4c-121">Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="0cd4c-123">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het te maken](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="0cd4c-125">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="0cd4c-126">(Kies in de vervolgkeuzelijst de waarde **Record Type**.)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="0cd4c-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-127">**Host Name**</span></span> <br/> |<span data-ttu-id="0cd4c-128">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-128">**Record Type**</span></span> <br/> |<span data-ttu-id="0cd4c-129">**Address**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="0cd4c-130">TXT</span><span class="sxs-lookup"><span data-stu-id="0cd4c-130">TXT</span></span>  <br/> |<span data-ttu-id="0cd4c-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0cd4c-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0cd4c-p105">**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![Afbeelding van het te maken](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="0cd4c-136">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-136">Select **save**.</span></span>
    
    ![Afbeelding van het te maken](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="0cd4c-138">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0cd4c-139">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="0cd4c-140">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0cd4c-141">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0cd4c-142">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="0cd4c-143">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="0cd4c-144">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="0cd4c-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="0cd4c-148">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="0cd4c-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="0cd4c-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0cd4c-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="0cd4c-150">Volg onderstaande stappen of [bekijk de video (start op 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0cd4c-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0cd4c-p107">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="0cd4c-154">Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="0cd4c-156">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Email Settings**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![Afbeelding van het te maken](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="0cd4c-158">Kies in de vervolgkeuzelijst **Service Selection** de optie **User (MX)**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![Afbeelding van het te maken](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="0cd4c-160">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="0cd4c-161">**Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-161">**Host Name**</span></span>|<span data-ttu-id="0cd4c-162">**Address**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-162">**Address**</span></span>|<span data-ttu-id="0cd4c-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="0cd4c-164">*\<domeinsleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="0cd4c-165">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="0cd4c-166">**Let op:** Haal uw \* \<domeinsleutel\> \* op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-166">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="0cd4c-167">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="0cd4c-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0cd4c-168">10</span><span class="sxs-lookup"><span data-stu-id="0cd4c-168">10</span></span>  <br/> <span data-ttu-id="0cd4c-169">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="0cd4c-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![Afbeelding van het te maken](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="0cd4c-171">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-171">Select **save**.</span></span>
    
    ![Afbeelding van het te maken](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="0cd4c-173">Als er andere MX-records zijn, schakelt u de selectievakjes voor deze records in om deze te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![Afbeelding van het te maken](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="0cd4c-175">Selecteer **aangevinkt verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-175">Select **delete checked**.</span></span>
    
    ![Afbeelding van het te maken](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="0cd4c-177">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="0cd4c-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="0cd4c-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0cd4c-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="0cd4c-179">Volg onderstaande stappen of [bekijk de video (start op 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0cd4c-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0cd4c-p109">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="0cd4c-183">Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="0cd4c-185">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het te maken](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="0cd4c-187">Selecteer **nieuwe rij**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-187">Select **new row**.</span></span>
    
    ![Afbeelding van het te maken](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="0cd4c-189">Typ of kopieer en plak de volgende waarden in de vakken voor de zes nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="0cd4c-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-190">**Host Name**</span></span>|<span data-ttu-id="0cd4c-191">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-191">**Record Type**</span></span>|<span data-ttu-id="0cd4c-192">**Address**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0cd4c-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0cd4c-193">autodiscover</span></span>  <br/> |<span data-ttu-id="0cd4c-194">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="0cd4c-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="0cd4c-196">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0cd4c-197">sip</span><span class="sxs-lookup"><span data-stu-id="0cd4c-197">sip</span></span>  <br/> |<span data-ttu-id="0cd4c-198">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="0cd4c-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0cd4c-200">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0cd4c-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0cd4c-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0cd4c-202">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="0cd4c-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0cd4c-204">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0cd4c-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0cd4c-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0cd4c-206">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="0cd4c-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="0cd4c-208">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0cd4c-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0cd4c-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0cd4c-210">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="0cd4c-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="0cd4c-212">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Afbeelding van het te maken](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="0cd4c-214">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-214">Select **save**.</span></span>
    
    ![Afbeelding van het te maken](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0cd4c-216">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="0cd4c-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0cd4c-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0cd4c-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0cd4c-218">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0cd4c-219">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0cd4c-220">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="0cd4c-221">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-221">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="0cd4c-222">Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0cd4c-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0cd4c-p111">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="0cd4c-226">Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="0cd4c-228">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het te maken](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="0cd4c-230">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="0cd4c-231">(Kies in de vervolgkeuzelijst de waarde **Record Type**.)</span><span class="sxs-lookup"><span data-stu-id="0cd4c-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0cd4c-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-232">**Host Name**</span></span>|<span data-ttu-id="0cd4c-233">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-233">**Record Type**</span></span>|<span data-ttu-id="0cd4c-234">**Address**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0cd4c-235">TXT</span><span class="sxs-lookup"><span data-stu-id="0cd4c-235">TXT</span></span>  <br/> |<span data-ttu-id="0cd4c-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0cd4c-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="0cd4c-237">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Afbeelding van het te maken](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="0cd4c-239">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-239">Select **save**.</span></span>
    
    ![Afbeelding van het te maken](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="0cd4c-241">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="0cd4c-241">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="0cd4c-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0cd4c-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="0cd4c-243">Volg onderstaande stappen of [bekijk de video (start op 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0cd4c-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0cd4c-p112">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="0cd4c-247">Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="0cd4c-249">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![Afbeelding van het te maken](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="0cd4c-251">Selecteer Rechts van **de nieuwe rij**De optie **SRV- of SPF-record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![Afbeelding van het te maken](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="0cd4c-253">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="0cd4c-254">**Service**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-254">**Service**</span></span>|<span data-ttu-id="0cd4c-255">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-255">**Protocol**</span></span>|<span data-ttu-id="0cd4c-256">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-256">**Priority**</span></span>|<span data-ttu-id="0cd4c-257">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-257">**Weight**</span></span>|<span data-ttu-id="0cd4c-258">**Poort**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-258">**Port**</span></span>|<span data-ttu-id="0cd4c-259">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0cd4c-260">_sip</span><span class="sxs-lookup"><span data-stu-id="0cd4c-260">_sip</span></span>  <br/> |<span data-ttu-id="0cd4c-261">_tls</span><span class="sxs-lookup"><span data-stu-id="0cd4c-261">_tls</span></span>  <br/> |<span data-ttu-id="0cd4c-262">100</span><span class="sxs-lookup"><span data-stu-id="0cd4c-262">100</span></span>  <br/> |<span data-ttu-id="0cd4c-263">1</span><span class="sxs-lookup"><span data-stu-id="0cd4c-263">1</span></span>  <br/> |<span data-ttu-id="0cd4c-264">443</span><span class="sxs-lookup"><span data-stu-id="0cd4c-264">443</span></span>  <br/> |<span data-ttu-id="0cd4c-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0cd4c-266">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0cd4c-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0cd4c-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="0cd4c-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="0cd4c-268">_tcp</span></span>  <br/> |<span data-ttu-id="0cd4c-269">100</span><span class="sxs-lookup"><span data-stu-id="0cd4c-269">100</span></span>  <br/> |<span data-ttu-id="0cd4c-270">1</span><span class="sxs-lookup"><span data-stu-id="0cd4c-270">1</span></span>  <br/> |<span data-ttu-id="0cd4c-271">5061</span><span class="sxs-lookup"><span data-stu-id="0cd4c-271">5061</span></span>  <br/> |<span data-ttu-id="0cd4c-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0cd4c-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="0cd4c-273">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Afbeelding van het te maken](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="0cd4c-275">Selecteer **opslaan**</span><span class="sxs-lookup"><span data-stu-id="0cd4c-275">Select **save**</span></span>
    
    ![Afbeelding van het te maken](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="0cd4c-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0cd4c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

