---
title: DNS-records maken op 1&1 IONOS voor Microsoft
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
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op 1&1 IONOS voor Microsoft.
ms.openlocfilehash: 9e6994b1906293cb249bf64101deaeb94a033c81
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629765"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="ff929-103">DNS-records maken op 1&1 IONOS voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="ff929-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="ff929-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="ff929-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="ff929-105">Houd er rekening mee dat 1&1 IONOS niet toestaat dat een domein zowel een MX-record als een Autodiscover CNAME-record op het hoogste niveau heeft.</span><span class="sxs-lookup"><span data-stu-id="ff929-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="ff929-106">Dit beperkt de manieren waarop u Exchange Online voor Microsoft configureren.</span><span class="sxs-lookup"><span data-stu-id="ff929-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="ff929-107">Er is een tijdelijke oplossing, maar we raden u aan deze **alleen** in te zetten als u al ervaring hebt met het maken van subdomeinen op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="ff929-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="ff929-108">> Als u er ondanks deze [servicebeperking](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) voor kiest om uw eigen Microsoft DNS-records op 1&1 IONOS te beheren, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="ff929-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="ff929-109">Nadat u deze records op 1&1 IONOS hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="ff929-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="ff929-110">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="ff929-110">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff929-111">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="ff929-111">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ff929-112">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="ff929-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ff929-113">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="ff929-113">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ff929-114">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="ff929-114">Add a TXT record for verification</span></span>

<span data-ttu-id="ff929-115">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="ff929-115">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="ff929-116">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="ff929-116">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff929-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ff929-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="ff929-119">Volg onderstaande stappen of [bekijk de video (start op 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ff929-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="ff929-120">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="ff929-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ff929-121">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ff929-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ff929-122">Selecteer **Domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="ff929-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ff929-123">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Paneel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="ff929-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ff929-124">Selecteer **DNS-instellingen bewerken**in het gebied **Domeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="ff929-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ff929-125">Selecteer **Record toevoegen**in de sectie **TXT- en SRV-records** .</span><span class="sxs-lookup"><span data-stu-id="ff929-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="ff929-126">Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="ff929-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ff929-127">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="ff929-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="ff929-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="ff929-128">**Type**</span></span> <br/> |<span data-ttu-id="ff929-129">**Voorvoegsel**</span><span class="sxs-lookup"><span data-stu-id="ff929-129">**Prefix**</span></span> <br/> |<span data-ttu-id="ff929-130">**Naamwaarde**</span><span class="sxs-lookup"><span data-stu-id="ff929-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="ff929-131">TXT</span><span class="sxs-lookup"><span data-stu-id="ff929-131">TXT</span></span>  <br/> |<span data-ttu-id="ff929-132">(Laat dit veld leeg staan)</span><span class="sxs-lookup"><span data-stu-id="ff929-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="ff929-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ff929-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ff929-134">LET OP: Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="ff929-134">NOTE: This is an example.</span></span> <span data-ttu-id="ff929-135">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="ff929-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="ff929-136">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="ff929-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="ff929-137">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff929-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="ff929-138">Selecteer Opnieuw **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="ff929-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="ff929-139">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="ff929-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="ff929-140">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="ff929-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ff929-141">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft 365 en vraagt u Microsoft 365 om de record te zoeken.</span><span class="sxs-lookup"><span data-stu-id="ff929-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="ff929-142">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="ff929-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ff929-143">Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="ff929-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ff929-144">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="ff929-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ff929-145">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="ff929-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ff929-146">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="ff929-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ff929-147">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="ff929-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ff929-148">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="ff929-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ff929-149">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="ff929-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ff929-150">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="ff929-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ff929-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ff929-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="ff929-152">Volg onderstaande stappen of [bekijk de video (start op 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ff929-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff929-153">Als je je hebt geregistreerd bij 1und1.de, [log dan hier in.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="ff929-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ff929-154">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="ff929-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ff929-155">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ff929-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ff929-156">Selecteer **Domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="ff929-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ff929-157">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Paneel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="ff929-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ff929-158">Selecteer **DNS-instellingen bewerken**in het gebied **Domeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="ff929-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ff929-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span><span class="sxs-lookup"><span data-stu-id="ff929-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="ff929-160">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ff929-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="ff929-161">![Afbeelding&amp;van het te maken:1-BP-afbeelding](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="ff929-162">Als er al MX-records worden vermeld, verwijdert u deze door de records te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="ff929-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="ff929-163">(Als er nog geen MX-records worden vermeld, gaat u verder met de volgende stap.)</span><span class="sxs-lookup"><span data-stu-id="ff929-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="ff929-164">![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="ff929-165">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de **MX 1**-record.</span><span class="sxs-lookup"><span data-stu-id="ff929-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="ff929-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="ff929-166">**MX 1**</span></span>|<span data-ttu-id="ff929-167">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="ff929-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="ff929-168">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ff929-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="ff929-169">OPMERKING: haal \<uw\> domeinsleutel uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="ff929-169">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="ff929-170">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="ff929-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ff929-171">10</span><span class="sxs-lookup"><span data-stu-id="ff929-171">10</span></span>  <br/> <span data-ttu-id="ff929-172">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="ff929-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1 en 1 - configureren 2 en 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="ff929-174">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff929-174">Select **Save**.</span></span><br/><span data-ttu-id="ff929-175">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ff929-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="ff929-176">![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="ff929-177">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="ff929-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="ff929-178">![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ff929-179">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="ff929-179">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ff929-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ff929-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="ff929-181">1&1 IONOS vereist een tijdelijke oplossing, zodat u een MX-record gebruiken samen met de CNAME-records die vereist zijn voor microsoft-e-mailservices.</span><span class="sxs-lookup"><span data-stu-id="ff929-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="ff929-182">Voor deze tijdelijke oplossing moet u een set subdomeinen maken op 1&1 IONOS en deze toewijzen aan CNAME-records.</span><span class="sxs-lookup"><span data-stu-id="ff929-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ff929-183">Zorg dat u ten minste twee beschikbare subdomeinen hebt voordat u deze procedure begint.</span><span class="sxs-lookup"><span data-stu-id="ff929-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="ff929-184">We raden deze oplossing alleen aan als je al ervaring hebt met het maken van subdomeinen op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="ff929-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="ff929-185">Basis-CNAME-records</span><span class="sxs-lookup"><span data-stu-id="ff929-185">Basic CNAME records</span></span>

<span data-ttu-id="ff929-186">Volg onderstaande stappen of [bekijk de video (start op 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ff929-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff929-187">Als je je hebt geregistreerd bij 1und1.de, [log dan hier in.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="ff929-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ff929-188">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="ff929-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ff929-189">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ff929-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ff929-190">Selecteer **Domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="ff929-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ff929-191">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer **Subdomeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="ff929-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="ff929-192">![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="ff929-193">Nu maakt u twee subdomeinen en stelt u voor elk subdomein een **Alias**-waarde in.</span><span class="sxs-lookup"><span data-stu-id="ff929-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="ff929-194">(Dit is vereist omdat 1&1 IONOS slechts één CNAME-record op het hoogste niveau ondersteunt, maar Microsoft vereist meerdere CNAME-records.)</span><span class="sxs-lookup"><span data-stu-id="ff929-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="ff929-195">Eerst maakt u het autodiscover-subdomein.</span><span class="sxs-lookup"><span data-stu-id="ff929-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="ff929-196">Selecteer **Subdomein maken**in de sectie **Subdomeinoverzicht** .</span><span class="sxs-lookup"><span data-stu-id="ff929-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="ff929-p113">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="ff929-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="ff929-200">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="ff929-200">**Create Subdomain**</span></span>|<span data-ttu-id="ff929-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ff929-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ff929-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ff929-202">autodiscover</span></span>  <br/> |<span data-ttu-id="ff929-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ff929-203">autodiscover.outlook.com</span></span>   | 

    ![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="ff929-205">Selecteer **Subdomein maken**.</span><span class="sxs-lookup"><span data-stu-id="ff929-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="ff929-206">![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="ff929-207">Zoek in de sectie **Subdomeinoverzicht** het **subdomein automatisch ontdekken** dat u zojuist hebt gemaakt en selecteer vervolgens het **besturingselement Paneel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="ff929-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="ff929-208">![Afbeelding&amp;van het te maken:1 BP-afbeelding](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="ff929-209">Selecteer **DNS-instellingen bewerken**in het gebied **Subdomeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="ff929-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="ff929-210">![Afbeelding&amp;van het te maken:1 BP-afbeelding-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="ff929-211">Selecteer in de sectie **A/AAAA Records (IP-adressen)** in het gedeelte **IP-adres (A Record)** de optie **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ff929-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="ff929-212">![Afbeelding&amp;van het te maken:1-BP-afbeelding](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="ff929-213">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="ff929-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="ff929-214">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="ff929-214">**Create Subdomain**</span></span>|<span data-ttu-id="ff929-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ff929-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ff929-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ff929-216">autodiscover</span></span>  <br/> |<span data-ttu-id="ff929-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ff929-217">autodiscover.outlook.com</span></span>   |

    ![Afbeelding&amp;van het te maken:1 BP-afbeelding-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="ff929-219">Schakel het selectievakje in voor de vrijwaring **I am aware**.</span><span class="sxs-lookup"><span data-stu-id="ff929-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="ff929-220">![Afbeelding&amp;van het te maken:1-BP-afbeelding](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="ff929-221">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff929-221">Select **Save**.</span></span><br/><span data-ttu-id="ff929-222">![Afbeelding&amp;van het te maken:1 BP afbeelding van het aantal](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="ff929-223">Extra CNAME-records</span><span class="sxs-lookup"><span data-stu-id="ff929-223">Additional CNAME records</span></span>

<span data-ttu-id="ff929-p114">Met de extra CNAME-records die in de volgende procedure worden gemaakt, worden Skype voor Bedrijven Online-services ingeschakeld. U gebruikt dezelfde stappen die u eerder hebt gebruikt om de twee CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="ff929-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="ff929-226">Maak het derde subdomein (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="ff929-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="ff929-227">Selecteer **Subdomein maken**in de sectie **Subdomeinoverzicht** .</span><span class="sxs-lookup"><span data-stu-id="ff929-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="ff929-p115">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="ff929-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="ff929-230">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="ff929-230">**Create Subdomain**</span></span>|<span data-ttu-id="ff929-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ff929-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ff929-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ff929-232">lyncdiscover</span></span>   |<span data-ttu-id="ff929-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff929-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="ff929-234">Selecteer **Subdomein maken**.</span><span class="sxs-lookup"><span data-stu-id="ff929-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="ff929-235">Selecteer **Subdomeinen beheren**op de pagina **Domain Center** .</span><span class="sxs-lookup"><span data-stu-id="ff929-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="ff929-236">Zoek in de sectie **Subdomeinoverzicht** het subdomein **lyncdiscover** dat u zojuist hebt gemaakt en selecteer vervolgens het **besturingselement Paneel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="ff929-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="ff929-237">Selecteer **DNS-instellingen bewerken**in het gebied **Subdomeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="ff929-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="ff929-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ff929-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="ff929-239">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="ff929-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="ff929-240">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="ff929-240">**Create Subdomain**</span></span>|<span data-ttu-id="ff929-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ff929-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ff929-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ff929-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ff929-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff929-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="ff929-244">Schakel het selectievakje in voor de disclaimer **Ik ben me bewust** en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff929-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="ff929-245">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="ff929-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="ff929-246">Maak als volgt het vierde subdomein (SIP):</span><span class="sxs-lookup"><span data-stu-id="ff929-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="ff929-247">Selecteer **Subdomein maken**in de sectie **Subdomeinoverzicht** .</span><span class="sxs-lookup"><span data-stu-id="ff929-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="ff929-p116">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="ff929-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="ff929-250">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="ff929-250">**Create Subdomain**</span></span>|<span data-ttu-id="ff929-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ff929-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ff929-252">sip</span><span class="sxs-lookup"><span data-stu-id="ff929-252">sip</span></span>  <br/> |<span data-ttu-id="ff929-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff929-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="ff929-254">Selecteer **Subdomein maken**.</span><span class="sxs-lookup"><span data-stu-id="ff929-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="ff929-255">Selecteer **Subdomeinen beheren**op de pagina **Domain Center** .</span><span class="sxs-lookup"><span data-stu-id="ff929-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="ff929-256">Zoek in de sectie **Subdomeinoverzicht** het **sip-subdomein** dat u zojuist hebt gemaakt en selecteer vervolgens het **besturingselement Paneel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="ff929-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="ff929-257">Selecteer **DNS-instellingen bewerken**in het gebied **Subdomeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="ff929-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="ff929-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="ff929-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="ff929-259">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="ff929-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="ff929-260">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="ff929-260">**Create Subdomain**</span></span>|<span data-ttu-id="ff929-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ff929-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ff929-262">sip</span><span class="sxs-lookup"><span data-stu-id="ff929-262">sip</span></span>  <br/> |<span data-ttu-id="ff929-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff929-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="ff929-264">Schakel het selectievakje in voor de disclaimer **Ik ben me bewust** en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff929-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="ff929-265">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="ff929-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="ff929-266">CNAME-records die nodig zijn voor MDM</span><span class="sxs-lookup"><span data-stu-id="ff929-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff929-267">Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="ff929-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="ff929-268">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="ff929-268">**Create Subdomain**</span></span>|<span data-ttu-id="ff929-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ff929-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff929-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ff929-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ff929-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ff929-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="ff929-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ff929-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ff929-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ff929-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ff929-274">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="ff929-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff929-275">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="ff929-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ff929-276">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="ff929-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ff929-277">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ff929-277">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ff929-278">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="ff929-278">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="ff929-279">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="ff929-279">Need examples?</span></span> <span data-ttu-id="ff929-280">Bekijk deze [externe domeinnaamsysteemrecords voor Microsoft.](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)</span><span class="sxs-lookup"><span data-stu-id="ff929-280">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="ff929-281">Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ff929-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="ff929-282">Volg onderstaande stappen of [bekijk de video (start op 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ff929-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff929-283">Als je je hebt geregistreerd bij 1und1.de, [log dan hier in.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="ff929-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ff929-284">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="ff929-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ff929-285">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ff929-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ff929-286">Selecteer **Domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="ff929-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ff929-287">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Paneel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="ff929-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ff929-288">Selecteer **DNS-instellingen bewerken**in het gebied **Domeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="ff929-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ff929-289">Selecteer **Record toevoegen**in de sectie **TXT- en SRV-records** .</span><span class="sxs-lookup"><span data-stu-id="ff929-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="ff929-290">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="ff929-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="ff929-291">Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="ff929-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="ff929-292">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="ff929-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="ff929-293">**Type**</span><span class="sxs-lookup"><span data-stu-id="ff929-293">**Type**</span></span>|<span data-ttu-id="ff929-294">**Voorvoegsel**</span><span class="sxs-lookup"><span data-stu-id="ff929-294">**Prefix**</span></span>|<span data-ttu-id="ff929-295">**Naamwaarde**</span><span class="sxs-lookup"><span data-stu-id="ff929-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ff929-296">TXT</span><span class="sxs-lookup"><span data-stu-id="ff929-296">TXT</span></span>  <br/> |<span data-ttu-id="ff929-297">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="ff929-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ff929-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ff929-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ff929-299">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="ff929-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT-record](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="ff929-301">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff929-301">Select **Save**.</span></span><br/><span data-ttu-id="ff929-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="ff929-303">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff929-303">Select **Save**.</span></span><br/><span data-ttu-id="ff929-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="ff929-305">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="ff929-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="ff929-306">![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ff929-307">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="ff929-307">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="ff929-308">Volg onderstaande stappen of [bekijk de video (start op 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="ff929-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff929-309">Als je je hebt geregistreerd bij 1und1.de, [log dan hier in.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="ff929-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="ff929-310">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="ff929-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="ff929-311">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ff929-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="ff929-312">Selecteer **Domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="ff929-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="ff929-313">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Paneel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="ff929-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="ff929-314">Selecteer **DNS-instellingen bewerken**in het gebied **Domeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="ff929-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="ff929-315">Selecteer **Record toevoegen**in de sectie **TXT- en SRV-records** .</span><span class="sxs-lookup"><span data-stu-id="ff929-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="ff929-316">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="ff929-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="ff929-317">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="ff929-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="ff929-318">(Kies de waarden **Type** en **TTL** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="ff929-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ff929-319">**Type**</span><span class="sxs-lookup"><span data-stu-id="ff929-319">**Type**</span></span>|<span data-ttu-id="ff929-320">**Service**</span><span class="sxs-lookup"><span data-stu-id="ff929-320">**Service**</span></span>|<span data-ttu-id="ff929-321">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="ff929-321">**Protocol**</span></span>|<span data-ttu-id="ff929-322">**Naam**</span><span class="sxs-lookup"><span data-stu-id="ff929-322">**Name**</span></span>|<span data-ttu-id="ff929-323">**Host**</span><span class="sxs-lookup"><span data-stu-id="ff929-323">**Host**</span></span>|<span data-ttu-id="ff929-324">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="ff929-324">**Priority**</span></span>|<span data-ttu-id="ff929-325">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="ff929-325">**Weight**</span></span>|<span data-ttu-id="ff929-326">**Poort**</span><span class="sxs-lookup"><span data-stu-id="ff929-326">**Port**</span></span>|<span data-ttu-id="ff929-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ff929-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ff929-328">SRV</span><span class="sxs-lookup"><span data-stu-id="ff929-328">SRV</span></span>  <br/> |<span data-ttu-id="ff929-329">sip</span><span class="sxs-lookup"><span data-stu-id="ff929-329">sip</span></span>  <br/> |<span data-ttu-id="ff929-330">tls</span><span class="sxs-lookup"><span data-stu-id="ff929-330">tls</span></span>  <br/> |<span data-ttu-id="ff929-331">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="ff929-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ff929-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff929-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="ff929-333">100</span><span class="sxs-lookup"><span data-stu-id="ff929-333">100</span></span>  <br/> |<span data-ttu-id="ff929-334">1</span><span class="sxs-lookup"><span data-stu-id="ff929-334">1</span></span>  <br/> |<span data-ttu-id="ff929-335">443</span><span class="sxs-lookup"><span data-stu-id="ff929-335">443</span></span>  <br/> |<span data-ttu-id="ff929-336">3600 (1 uur)</span><span class="sxs-lookup"><span data-stu-id="ff929-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="ff929-337">SRV</span><span class="sxs-lookup"><span data-stu-id="ff929-337">SRV</span></span>  <br/> |<span data-ttu-id="ff929-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ff929-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="ff929-339">tcp</span><span class="sxs-lookup"><span data-stu-id="ff929-339">tcp</span></span>  <br/> |<span data-ttu-id="ff929-340">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="ff929-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ff929-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff929-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="ff929-342">100</span><span class="sxs-lookup"><span data-stu-id="ff929-342">100</span></span>  <br/> |<span data-ttu-id="ff929-343">1</span><span class="sxs-lookup"><span data-stu-id="ff929-343">1</span></span>  <br/> |<span data-ttu-id="ff929-344">5061</span><span class="sxs-lookup"><span data-stu-id="ff929-344">5061</span></span>  <br/> |<span data-ttu-id="ff929-345">3600 (1 uur)</span><span class="sxs-lookup"><span data-stu-id="ff929-345">3600 (1 h)</span></span>  <br/> |  
    
    ![Afbeelding&amp;van het te maken:1-BP-afbeelding](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="ff929-347">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff929-347">Select **Save**.</span></span> <br/><span data-ttu-id="ff929-348">![Afbeelding&amp;van het te maken:1 BP-knopafbeelding -5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="ff929-349">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff929-349">Select **Save**.</span></span> <br/><span data-ttu-id="ff929-350">![Afbeelding&amp;van het te maken:1 BP-knopafbeelding -5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="ff929-351">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="ff929-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="ff929-352">![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="ff929-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="ff929-353">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="ff929-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="ff929-354">Selecteer **Record toevoegen**in de sectie **TXT- en SRV-records** .</span><span class="sxs-lookup"><span data-stu-id="ff929-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="ff929-355">Maak in het gebied **Record toevoegen** een record met de waarden uit de andere rij in de tabel en selecteer vervolgens opnieuw **Toevoegen,** **Opslaan**en **Ja** om de record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="ff929-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="ff929-356">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="ff929-356">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ff929-357">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="ff929-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ff929-358">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="ff929-358">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
