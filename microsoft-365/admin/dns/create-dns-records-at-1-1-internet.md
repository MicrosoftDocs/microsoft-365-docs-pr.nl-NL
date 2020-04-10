---
title: DNS-records maken op 1&1 IONOS voor Office 365
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op 1&1 IONOS voor Office 365.
ms.openlocfilehash: e31c9d9d08e29156ff6197c030de6b0f4169b5f4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211869"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a><span data-ttu-id="5d5ff-103">DNS-records maken op 1&1 IONOS voor Office 365</span><span class="sxs-lookup"><span data-stu-id="5d5ff-103">Create DNS records at 1&1 IONOS for Office 365</span></span>

 <span data-ttu-id="5d5ff-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="5d5ff-105">Houd er rekening mee dat 1&1 IONOS niet toestaat dat een domein zowel een MX-record als een Autodiscover CNAME-record op het hoogste niveau heeft.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="5d5ff-106">Dit beperkt de manieren waarop u Exchange Online kunt configureren voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-106">This limits the ways in which you can configure Exchange Online for Office 365.</span></span> <span data-ttu-id="5d5ff-107">Er is een tijdelijke oplossing, maar we raden u aan deze **alleen** in te zetten als u al ervaring hebt met het maken van subdomeinen op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="5d5ff-108">> Als u er ondanks deze [servicebeperking](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) voor kiest om uw eigen DNS-records van Office 365 op 1&1 IONOS te beheren, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Office 365 DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="5d5ff-109">Nadat u deze records hebt toegevoegd op 1&1 IONOS, wordt uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="5d5ff-110">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-110">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d5ff-p102">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5d5ff-114">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="5d5ff-114">Add a TXT record for verification</span></span>

<span data-ttu-id="5d5ff-p103">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d5ff-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="5d5ff-119">Volg onderstaande stappen of [bekijk de video (start op 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="5d5ff-120">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="5d5ff-121">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="5d5ff-122">Selecteer **Domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="5d5ff-123">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Paneel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="5d5ff-124">Selecteer **DNS-instellingen bewerken**in het gebied **Domeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="5d5ff-125">Selecteer **Record toevoegen**in de sectie **TXT- en SRV-records** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="5d5ff-126">Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d5ff-127">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="5d5ff-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-128">**Type**</span></span> <br/> |<span data-ttu-id="5d5ff-129">**Voorvoegsel**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-129">**Prefix**</span></span> <br/> |<span data-ttu-id="5d5ff-130">**Naamwaarde**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="5d5ff-131">TXT</span><span class="sxs-lookup"><span data-stu-id="5d5ff-131">TXT</span></span>  <br/> |<span data-ttu-id="5d5ff-132">(Laat dit veld leeg staan)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="5d5ff-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5d5ff-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5d5ff-134">LET OP: Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-134">NOTE: This is an example.</span></span> <span data-ttu-id="5d5ff-135">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="5d5ff-136">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="5d5ff-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="5d5ff-137">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="5d5ff-138">Selecteer Opnieuw **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="5d5ff-139">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="5d5ff-140">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5d5ff-141">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5d5ff-142">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5d5ff-143">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5d5ff-144">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5d5ff-145">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5d5ff-146">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5d5ff-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5d5ff-150">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="5d5ff-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5d5ff-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5d5ff-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="5d5ff-152">Volg onderstaande stappen of [bekijk de video (start op 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d5ff-153">Als je je hebt geregistreerd bij 1und1.de, [log dan hier in.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="5d5ff-154">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="5d5ff-155">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="5d5ff-156">Selecteer **Domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="5d5ff-157">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Paneel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="5d5ff-158">Selecteer **DNS-instellingen bewerken**in het gebied **Domeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="5d5ff-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="5d5ff-160">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="5d5ff-161">![Afbeelding&amp;van het te maken:1-BP-afbeelding](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="5d5ff-162">Als er al MX-records worden vermeld, verwijdert u deze door de records te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="5d5ff-163">(Als er nog geen MX-records worden vermeld, gaat u verder met de volgende stap.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="5d5ff-164">![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="5d5ff-165">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de **MX 1**-record.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="5d5ff-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-166">**MX 1**</span></span>|<span data-ttu-id="5d5ff-167">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="5d5ff-168">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5d5ff-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="5d5ff-169">OPMERKING: haal \<uw\> domeinsleutel op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-169">NOTE: Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="5d5ff-170">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="5d5ff-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5d5ff-171">10</span><span class="sxs-lookup"><span data-stu-id="5d5ff-171">10</span></span>  <br/> <span data-ttu-id="5d5ff-172">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="5d5ff-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 en 1 - configureren 2 en 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="5d5ff-174">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-174">Select **Save**.</span></span><br/><span data-ttu-id="5d5ff-175">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="5d5ff-176">![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="5d5ff-177">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="5d5ff-178">![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5d5ff-179">De zes CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="5d5ff-179">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5d5ff-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5d5ff-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="5d5ff-181">1&1 IONOS vereist een tijdelijke oplossing, zodat u een MX-record gebruiken samen met de CNAME-records die vereist zijn voor E-mailservices van Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Office 365 email services.</span></span> <span data-ttu-id="5d5ff-182">Voor deze tijdelijke oplossing moet u een set subdomeinen maken op 1&1 IONOS en deze toewijzen aan CNAME-records.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5d5ff-183">Zorg dat u ten minste twee beschikbare subdomeinen hebt voordat u deze procedure begint.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="5d5ff-184">We raden deze oplossing alleen aan als je al ervaring hebt met het maken van subdomeinen op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="5d5ff-185">Basis-CNAME-records</span><span class="sxs-lookup"><span data-stu-id="5d5ff-185">Basic CNAME records</span></span>

<span data-ttu-id="5d5ff-186">Volg onderstaande stappen of [bekijk de video (start op 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d5ff-187">Als je je hebt geregistreerd bij 1und1.de, [log dan hier in.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="5d5ff-188">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="5d5ff-189">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="5d5ff-190">Selecteer **Domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="5d5ff-191">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer **Subdomeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="5d5ff-192">![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="5d5ff-193">Nu maakt u twee subdomeinen en stelt u voor elk subdomein een **Alias**-waarde in.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="5d5ff-194">(Dit is vereist omdat 1&1 IONOS slechts één CNAME-record op het hoogste niveau ondersteunt, maar voor Office 365 zijn meerdere CNAME-records vereist.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Office 365 requires several CNAME records.)</span></span><br/><span data-ttu-id="5d5ff-195">Eerst maakt u het autodiscover-subdomein.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="5d5ff-196">Selecteer **Subdomein maken**in de sectie **Subdomeinoverzicht** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="5d5ff-p113">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="5d5ff-200">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-200">**Create Subdomain**</span></span>|<span data-ttu-id="5d5ff-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5d5ff-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5d5ff-202">autodiscover</span></span>  <br/> |<span data-ttu-id="5d5ff-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5d5ff-203">autodiscover.outlook.com</span></span>   | 

    ![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="5d5ff-205">Selecteer **Subdomein maken**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="5d5ff-206">![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="5d5ff-207">Zoek in de sectie **Subdomeinoverzicht** het **subdomein automatisch ontdekken** dat u zojuist hebt gemaakt en selecteer vervolgens het **besturingselement Paneel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="5d5ff-208">![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="5d5ff-209">Selecteer **DNS-instellingen bewerken**in het gebied **Subdomeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="5d5ff-210">![Afbeelding&amp;van het te maken:1 BP-afbeelding-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="5d5ff-211">Selecteer in de sectie **A/AAAA Records (IP-adressen)** in het gedeelte **IP-adres (A Record)** de optie **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="5d5ff-212">![Afbeelding&amp;van het te maken:1-BP-afbeelding](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="5d5ff-213">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="5d5ff-214">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-214">**Create Subdomain**</span></span>|<span data-ttu-id="5d5ff-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5d5ff-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5d5ff-216">autodiscover</span></span>  <br/> |<span data-ttu-id="5d5ff-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5d5ff-217">autodiscover.outlook.com</span></span>   |

    ![Afbeelding&amp;van het te maken:1 BP-afbeelding-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="5d5ff-219">Schakel het selectievakje in voor de vrijwaring **I am aware**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="5d5ff-220">![Afbeelding&amp;van het te maken:1-BP-afbeelding](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="5d5ff-221">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-221">Select **Save**.</span></span><br/><span data-ttu-id="5d5ff-222">![Afbeelding&amp;van het te maken:1 BP afbeelding van het aantal](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="5d5ff-223">Extra CNAME-records</span><span class="sxs-lookup"><span data-stu-id="5d5ff-223">Additional CNAME records</span></span>

<span data-ttu-id="5d5ff-p114">Met de extra CNAME-records die in de volgende procedure worden gemaakt, worden Skype voor Bedrijven Online-services ingeschakeld. U gebruikt dezelfde stappen die u eerder hebt gebruikt om de twee CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="5d5ff-226">Maak het derde subdomein (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="5d5ff-227">Selecteer **Subdomein maken**in de sectie **Subdomeinoverzicht** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="5d5ff-p115">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="5d5ff-230">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-230">**Create Subdomain**</span></span>|<span data-ttu-id="5d5ff-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5d5ff-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5d5ff-232">lyncdiscover</span></span>   |<span data-ttu-id="5d5ff-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5d5ff-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="5d5ff-234">Selecteer **Subdomein maken**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="5d5ff-235">Selecteer **Subdomeinen beheren**op de pagina **Domain Center** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="5d5ff-236">Zoek in de sectie **Subdomeinoverzicht** het subdomein **lyncdiscover** dat u zojuist hebt gemaakt en selecteer vervolgens het **besturingselement Paneel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="5d5ff-237">Selecteer **DNS-instellingen bewerken**in het gebied **Subdomeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="5d5ff-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="5d5ff-239">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="5d5ff-240">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-240">**Create Subdomain**</span></span>|<span data-ttu-id="5d5ff-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5d5ff-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5d5ff-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5d5ff-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5d5ff-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="5d5ff-244">Schakel het selectievakje in voor de disclaimer **Ik ben me bewust** en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="5d5ff-245">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="5d5ff-246">Maak als volgt het vierde subdomein (SIP):</span><span class="sxs-lookup"><span data-stu-id="5d5ff-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="5d5ff-247">Selecteer **Subdomein maken**in de sectie **Subdomeinoverzicht** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="5d5ff-p116">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="5d5ff-250">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-250">**Create Subdomain**</span></span>|<span data-ttu-id="5d5ff-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5d5ff-252">sip</span><span class="sxs-lookup"><span data-stu-id="5d5ff-252">sip</span></span>  <br/> |<span data-ttu-id="5d5ff-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5d5ff-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="5d5ff-254">Selecteer **Subdomein maken**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="5d5ff-255">Selecteer **Subdomeinen beheren**op de pagina **Domain Center** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="5d5ff-256">Zoek in de sectie **Subdomeinoverzicht** het **sip-subdomein** dat u zojuist hebt gemaakt en selecteer vervolgens het **besturingselement Paneel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="5d5ff-257">Selecteer **DNS-instellingen bewerken**in het gebied **Subdomeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="5d5ff-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="5d5ff-259">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="5d5ff-260">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-260">**Create Subdomain**</span></span>|<span data-ttu-id="5d5ff-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5d5ff-262">sip</span><span class="sxs-lookup"><span data-stu-id="5d5ff-262">sip</span></span>  <br/> |<span data-ttu-id="5d5ff-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5d5ff-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="5d5ff-264">Schakel het selectievakje in voor de disclaimer **Ik ben me bewust** en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="5d5ff-265">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="5d5ff-266">CNAME-records die nodig zijn voor MDM</span><span class="sxs-lookup"><span data-stu-id="5d5ff-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d5ff-267">Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="5d5ff-268">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-268">**Create Subdomain**</span></span>|<span data-ttu-id="5d5ff-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5d5ff-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5d5ff-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5d5ff-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5d5ff-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="5d5ff-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5d5ff-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5d5ff-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5d5ff-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5d5ff-274">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="5d5ff-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d5ff-275">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5d5ff-276">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5d5ff-277">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5d5ff-278">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="5d5ff-279">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="5d5ff-279">Need examples?</span></span> <span data-ttu-id="5d5ff-280">Bekijk deze [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-280">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="5d5ff-281">Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="5d5ff-282">Volg onderstaande stappen of [bekijk de video (start op 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d5ff-283">Als je je hebt geregistreerd bij 1und1.de, [log dan hier in.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="5d5ff-284">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="5d5ff-285">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="5d5ff-286">Selecteer **Domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="5d5ff-287">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Paneel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="5d5ff-288">Selecteer **DNS-instellingen bewerken**in het gebied **Domeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="5d5ff-289">Selecteer **Record toevoegen**in de sectie **TXT- en SRV-records** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="5d5ff-290">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="5d5ff-291">Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="5d5ff-292">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="5d5ff-293">**Type**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-293">**Type**</span></span>|<span data-ttu-id="5d5ff-294">**Voorvoegsel**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-294">**Prefix**</span></span>|<span data-ttu-id="5d5ff-295">**Naamwaarde**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5d5ff-296">TXT</span><span class="sxs-lookup"><span data-stu-id="5d5ff-296">TXT</span></span>  <br/> |<span data-ttu-id="5d5ff-297">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5d5ff-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5d5ff-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5d5ff-299">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT-record](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="5d5ff-301">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-301">Select **Save**.</span></span><br/><span data-ttu-id="5d5ff-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="5d5ff-303">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-303">Select **Save**.</span></span><br/><span data-ttu-id="5d5ff-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="5d5ff-305">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="5d5ff-306">![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5d5ff-307">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="5d5ff-307">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="5d5ff-308">Volg onderstaande stappen of [bekijk de video (start op 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d5ff-309">Als je je hebt geregistreerd bij 1und1.de, [log dan hier in.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="5d5ff-310">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="5d5ff-311">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="5d5ff-312">Selecteer **Domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="5d5ff-313">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Paneel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="5d5ff-314">Selecteer **DNS-instellingen bewerken**in het gebied **Domeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="5d5ff-315">Selecteer **Record toevoegen**in de sectie **TXT- en SRV-records** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="5d5ff-316">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="5d5ff-317">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="5d5ff-318">(Kies de waarden **Type** en **TTL** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5d5ff-319">**Type**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-319">**Type**</span></span>|<span data-ttu-id="5d5ff-320">**Service**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-320">**Service**</span></span>|<span data-ttu-id="5d5ff-321">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-321">**Protocol**</span></span>|<span data-ttu-id="5d5ff-322">**Naam**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-322">**Name**</span></span>|<span data-ttu-id="5d5ff-323">**Host**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-323">**Host**</span></span>|<span data-ttu-id="5d5ff-324">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-324">**Priority**</span></span>|<span data-ttu-id="5d5ff-325">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-325">**Weight**</span></span>|<span data-ttu-id="5d5ff-326">**Poort**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-326">**Port**</span></span>|<span data-ttu-id="5d5ff-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5d5ff-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5d5ff-328">SRV</span><span class="sxs-lookup"><span data-stu-id="5d5ff-328">SRV</span></span>  <br/> |<span data-ttu-id="5d5ff-329">sip</span><span class="sxs-lookup"><span data-stu-id="5d5ff-329">sip</span></span>  <br/> |<span data-ttu-id="5d5ff-330">tls</span><span class="sxs-lookup"><span data-stu-id="5d5ff-330">tls</span></span>  <br/> |<span data-ttu-id="5d5ff-331">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5d5ff-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5d5ff-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="5d5ff-333">100</span><span class="sxs-lookup"><span data-stu-id="5d5ff-333">100</span></span>  <br/> |<span data-ttu-id="5d5ff-334">1</span><span class="sxs-lookup"><span data-stu-id="5d5ff-334">1</span></span>  <br/> |<span data-ttu-id="5d5ff-335">443</span><span class="sxs-lookup"><span data-stu-id="5d5ff-335">443</span></span>  <br/> |<span data-ttu-id="5d5ff-336">3600 (1 uur)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="5d5ff-337">SRV</span><span class="sxs-lookup"><span data-stu-id="5d5ff-337">SRV</span></span>  <br/> |<span data-ttu-id="5d5ff-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="5d5ff-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="5d5ff-339">tcp</span><span class="sxs-lookup"><span data-stu-id="5d5ff-339">tcp</span></span>  <br/> |<span data-ttu-id="5d5ff-340">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5d5ff-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5d5ff-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="5d5ff-342">100</span><span class="sxs-lookup"><span data-stu-id="5d5ff-342">100</span></span>  <br/> |<span data-ttu-id="5d5ff-343">1</span><span class="sxs-lookup"><span data-stu-id="5d5ff-343">1</span></span>  <br/> |<span data-ttu-id="5d5ff-344">5061</span><span class="sxs-lookup"><span data-stu-id="5d5ff-344">5061</span></span>  <br/> |<span data-ttu-id="5d5ff-345">3600 (1 uur)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-345">3600 (1 h)</span></span>  <br/> |  
    
    ![Afbeelding&amp;van het te maken:1-BP-afbeelding](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="5d5ff-347">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-347">Select **Save**.</span></span> <br/><span data-ttu-id="5d5ff-348">![Afbeelding&amp;van het te maken:1 BP-knopafbeelding -5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="5d5ff-349">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-349">Select **Save**.</span></span> <br/><span data-ttu-id="5d5ff-350">![Afbeelding&amp;van het te maken:1 BP-knopafbeelding -5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="5d5ff-351">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="5d5ff-352">![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="5d5ff-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="5d5ff-353">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="5d5ff-354">Selecteer **Record toevoegen**in de sectie **TXT- en SRV-records** .</span><span class="sxs-lookup"><span data-stu-id="5d5ff-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="5d5ff-355">Maak in het gebied **Record toevoegen** een record met de waarden uit de andere rij in de tabel en selecteer vervolgens opnieuw **Toevoegen,** **Opslaan**en **Ja** om de record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="5d5ff-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="5d5ff-p120">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5d5ff-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
