---
title: DNS-records maken op 1&1 IONOS voor Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services op 1&1 IONOS voor Microsoft.
ms.openlocfilehash: 123abd6d1d93f80eb73f187b7ff75ccd90d02980
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910556"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="53eec-103">DNS-records maken op 1&1 IONOS voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="53eec-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="53eec-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="53eec-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="53eec-105">Met 1&1 IONOS kan een domein niet zowel een MX-record als een CNAME-record op het hoogste niveau hebben.</span><span class="sxs-lookup"><span data-stu-id="53eec-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="53eec-106">Dit beperkt de manieren waarop u Exchange Online voor Microsoft kunt configureren.</span><span class="sxs-lookup"><span data-stu-id="53eec-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="53eec-107">Er is een tijdelijke oplossing, maar  we raden u aan deze alleen te gebruiken als u al ervaring hebt met het maken van subdomeinen op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="53eec-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="53eec-108">> Als u ondanks deze [servicebeperking](../setup/domains-faq.yml) ervoor kiest om uw eigen Microsoft DNS-records te beheren op 1&1 IONOS, volgt u de stappen in dit artikel om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, en ga zo maar door.</span><span class="sxs-lookup"><span data-stu-id="53eec-108">> If despite this [service limitation](../setup/domains-faq.yml) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="53eec-109">Nadat u deze records hebt&1 IONOS, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="53eec-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="53eec-p102">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="53eec-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="53eec-113">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="53eec-113">Add a TXT record for verification</span></span>

<span data-ttu-id="53eec-p103">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="53eec-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53eec-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="53eec-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="53eec-118">Volg onderstaande stappen of [bekijk de video (start op 0:42)]().</span><span class="sxs-lookup"><span data-stu-id="53eec-118">Follow the steps below or [watch the video (start at 0:42)]().</span></span>
  
1. <span data-ttu-id="53eec-119">Als u wilt beginnen, gaat u via deze [koppeling](https://my.1and1.com/)naar uw domeinenpagina op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="53eec-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="53eec-120">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="53eec-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="53eec-121">Selecteer **Domeinen beheren.**</span><span class="sxs-lookup"><span data-stu-id="53eec-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="53eec-122">Zoek op **de pagina Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Panel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="53eec-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="53eec-123">Selecteer **dns-instellingen** bewerken in het gebied **Domeininstellingen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="53eec-124">Selecteer in **de sectie TXT- en SRV-records** de optie **Record toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="53eec-125">Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="53eec-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="53eec-126">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="53eec-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="53eec-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="53eec-127">**Type**</span></span> <br/> |<span data-ttu-id="53eec-128">**Voorvoegsel**</span><span class="sxs-lookup"><span data-stu-id="53eec-128">**Prefix**</span></span> <br/> |<span data-ttu-id="53eec-129">**Naamwaarde**</span><span class="sxs-lookup"><span data-stu-id="53eec-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="53eec-130">TXT</span><span class="sxs-lookup"><span data-stu-id="53eec-130">TXT</span></span>  <br/> |<span data-ttu-id="53eec-131">(Laat dit veld leeg)</span><span class="sxs-lookup"><span data-stu-id="53eec-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="53eec-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="53eec-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="53eec-133">OPMERKING: Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="53eec-133">NOTE: This is an example.</span></span> <span data-ttu-id="53eec-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="53eec-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="53eec-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="53eec-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="53eec-136">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="53eec-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="53eec-137">Selecteer **Opnieuw** opslaan.</span><span class="sxs-lookup"><span data-stu-id="53eec-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="53eec-138">Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="53eec-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="53eec-139">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="53eec-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="53eec-140">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="53eec-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="53eec-141">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="53eec-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="53eec-142">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="53eec-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="53eec-143">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="53eec-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="53eec-144">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="53eec-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="53eec-145">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="53eec-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="53eec-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="53eec-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="53eec-149">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="53eec-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="53eec-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="53eec-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="53eec-151">Volg onderstaande stappen of [bekijk de video (start op 3:22)]().</span><span class="sxs-lookup"><span data-stu-id="53eec-151">Follow the steps below or [watch the video (start at 3:22)]().</span></span>
  
> [!NOTE]
> <span data-ttu-id="53eec-152">Als u zich hebt geregistreerd bij 1und1.de, [meld u dan hier aan.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="53eec-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="53eec-153">Als u wilt beginnen, gaat u via deze [koppeling](https://my.1and1.com/)naar uw domeinenpagina op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="53eec-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="53eec-154">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="53eec-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="53eec-155">Selecteer **Domeinen beheren.**</span><span class="sxs-lookup"><span data-stu-id="53eec-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="53eec-156">Zoek op **de pagina Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Panel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="53eec-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="53eec-157">Selecteer **dns-instellingen** bewerken in het gebied **Domeininstellingen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="53eec-158">Selecteer in **de sectie MX Records** in het gebied Mail **Exchanger (MX Record)** de optie **Andere e-mailserver**.</span><span class="sxs-lookup"><span data-stu-id="53eec-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="53eec-159">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="53eec-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="53eec-160">![1 &amp; 1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="53eec-161">Als er al MX-records worden vermeld, verwijdert u deze door de records te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="53eec-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="53eec-162">(Als er nog geen MX-records worden vermeld, gaat u verder met de volgende stap.)</span><span class="sxs-lookup"><span data-stu-id="53eec-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="53eec-163">![1 &amp; 1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="53eec-164">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de **MX 1**-record.</span><span class="sxs-lookup"><span data-stu-id="53eec-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="53eec-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="53eec-165">**MX 1**</span></span>|<span data-ttu-id="53eec-166">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="53eec-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="53eec-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="53eec-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="53eec-168">OPMERKING: Haal uw \<domain-key\> uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="53eec-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="53eec-169">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="53eec-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="53eec-170">10</span><span class="sxs-lookup"><span data-stu-id="53eec-170">10</span></span>  <br/> <span data-ttu-id="53eec-171">Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="53eec-171">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | 
    
    ![1 en 1 - 2 en 3 configureren](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="53eec-173">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="53eec-173">Select **Save**.</span></span><br/><span data-ttu-id="53eec-174">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="53eec-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="53eec-175">![1 &amp; 1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="53eec-176">Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="53eec-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="53eec-177">![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="53eec-178">Voeg de zes CNAME-records toe die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="53eec-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="53eec-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="53eec-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="53eec-180">1&1 IONOS vereist een tijdelijke oplossing, zodat u een MX-record kunt gebruiken samen met de CNAME-records die zijn vereist voor e-mailservices van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53eec-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="53eec-181">Voor deze tijdelijke oplossing moet u een set subdomeinen maken op 1&1 IONOS en deze toewijzen aan CNAME-records.</span><span class="sxs-lookup"><span data-stu-id="53eec-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="53eec-182">Zorg dat u ten minste twee beschikbare subdomeinen hebt voordat u deze procedure begint.</span><span class="sxs-lookup"><span data-stu-id="53eec-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="53eec-183">We raden deze oplossing alleen aan als u al ervaring hebt met het maken van subdomeinen op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="53eec-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="53eec-184">Basis-CNAME-records</span><span class="sxs-lookup"><span data-stu-id="53eec-184">Basic CNAME records</span></span>

<span data-ttu-id="53eec-185">Volg onderstaande stappen of [bekijk de video (start op 3:57)]().</span><span class="sxs-lookup"><span data-stu-id="53eec-185">Follow the steps below or [watch the video (start at 3:57)]().</span></span>
  
> [!NOTE]
> <span data-ttu-id="53eec-186">Als u zich hebt geregistreerd bij 1und1.de, [meld u dan hier aan.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="53eec-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="53eec-187">Als u wilt beginnen, gaat u via deze [koppeling](https://my.1and1.com/)naar uw domeinenpagina op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="53eec-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="53eec-188">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="53eec-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="53eec-189">Selecteer **Domeinen beheren.**</span><span class="sxs-lookup"><span data-stu-id="53eec-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="53eec-190">Zoek op **de pagina Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens **Subdomeinen beheren.**</span><span class="sxs-lookup"><span data-stu-id="53eec-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="53eec-191">![1 &amp; 1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="53eec-192">Nu maakt u twee subdomeinen en stelt u voor elk subdomein een **Alias**-waarde in.</span><span class="sxs-lookup"><span data-stu-id="53eec-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="53eec-193">(Dit is vereist omdat 1&1 IONOS slechts één CNAME-record op het hoogste niveau ondersteunt, maar Microsoft meerdere CNAME-records nodig heeft.)</span><span class="sxs-lookup"><span data-stu-id="53eec-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="53eec-194">Eerst maakt u het autodiscover-subdomein.</span><span class="sxs-lookup"><span data-stu-id="53eec-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="53eec-195">Selecteer **subdomein maken** in de sectie **Subdomeinoverzicht.**</span><span class="sxs-lookup"><span data-stu-id="53eec-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="53eec-p113">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="53eec-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="53eec-199">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="53eec-199">**Create Subdomain**</span></span>|<span data-ttu-id="53eec-200">**Alias**</span><span class="sxs-lookup"><span data-stu-id="53eec-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="53eec-201">autodiscover</span><span class="sxs-lookup"><span data-stu-id="53eec-201">autodiscover</span></span>  <br/> |<span data-ttu-id="53eec-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="53eec-202">autodiscover.outlook.com</span></span>   | 

    ![1 &amp; 1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="53eec-204">Selecteer **Subdomein maken.**</span><span class="sxs-lookup"><span data-stu-id="53eec-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="53eec-205">![1 &amp; 1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="53eec-206">Zoek in **de sectie Subdomeinoverzicht** het **autodiscover-subdomein** dat u zojuist hebt gemaakt en selecteer vervolgens het besturingselement **Panel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="53eec-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="53eec-207">![1 &amp; 1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="53eec-208">Selecteer **dns-instellingen** bewerken in het gebied **Subdomeininstellingen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="53eec-209">![1 &amp; 1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="53eec-210">Selecteer CNAME in de sectie **A/AAAA Records (IP-adressen)** in het **gebied IP-adres (A** **Record).**</span><span class="sxs-lookup"><span data-stu-id="53eec-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="53eec-211">![1 &amp; 1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="53eec-212">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="53eec-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="53eec-213">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="53eec-213">**Create Subdomain**</span></span>|<span data-ttu-id="53eec-214">**Alias**</span><span class="sxs-lookup"><span data-stu-id="53eec-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="53eec-215">autodiscover</span><span class="sxs-lookup"><span data-stu-id="53eec-215">autodiscover</span></span>  <br/> |<span data-ttu-id="53eec-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="53eec-216">autodiscover.outlook.com</span></span>   |

    ![1 &amp; 1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="53eec-218">Schakel het selectievakje in voor de vrijwaring **I am aware**.</span><span class="sxs-lookup"><span data-stu-id="53eec-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="53eec-219">![1 &amp; 1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="53eec-220">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="53eec-220">Select **Save**.</span></span><br/><span data-ttu-id="53eec-221">![1 &amp; 1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="53eec-222">Extra CNAME-records</span><span class="sxs-lookup"><span data-stu-id="53eec-222">Additional CNAME records</span></span>

<span data-ttu-id="53eec-p114">Met de extra CNAME-records die in de volgende procedure worden gemaakt, worden Skype voor Bedrijven Online-services ingeschakeld. U gebruikt dezelfde stappen die u eerder hebt gebruikt om de twee CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="53eec-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="53eec-225">Maak het derde subdomein (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="53eec-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="53eec-226">Selecteer **subdomein maken** in de sectie **Subdomeinoverzicht.**</span><span class="sxs-lookup"><span data-stu-id="53eec-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="53eec-p115">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="53eec-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="53eec-229">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="53eec-229">**Create Subdomain**</span></span>|<span data-ttu-id="53eec-230">**Alias**</span><span class="sxs-lookup"><span data-stu-id="53eec-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="53eec-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="53eec-231">lyncdiscover</span></span>   |<span data-ttu-id="53eec-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="53eec-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="53eec-233">Selecteer **Subdomein maken.**</span><span class="sxs-lookup"><span data-stu-id="53eec-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="53eec-234">Selecteer op **de pagina Domeincentrum** **de optie Subdomeinen beheren.**</span><span class="sxs-lookup"><span data-stu-id="53eec-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="53eec-235">Zoek in **de sectie Subdomeinoverzicht** het **lyncdiscover-subdomein** dat u zojuist hebt gemaakt en selecteer vervolgens het besturingselement **Panel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="53eec-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="53eec-236">Selecteer **dns-instellingen** bewerken in het gebied **Subdomeininstellingen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="53eec-237">Selecteer CNAME in de sectie **A/AAAA Records (IP-adressen)** in het **gebied IP-adres (A** **Record).**</span><span class="sxs-lookup"><span data-stu-id="53eec-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="53eec-238">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="53eec-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="53eec-239">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="53eec-239">**Create Subdomain**</span></span>|<span data-ttu-id="53eec-240">**Alias**</span><span class="sxs-lookup"><span data-stu-id="53eec-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="53eec-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="53eec-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="53eec-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="53eec-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="53eec-243">Schakel het selectievakje in voor de vrijwaring **ik ben op de** hoogte en selecteer opslaan. </span><span class="sxs-lookup"><span data-stu-id="53eec-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="53eec-244">Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="53eec-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="53eec-245">Maak als volgt het vierde subdomein (SIP):</span><span class="sxs-lookup"><span data-stu-id="53eec-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="53eec-246">Selecteer **subdomein maken** in de sectie **Subdomeinoverzicht.**</span><span class="sxs-lookup"><span data-stu-id="53eec-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="53eec-p116">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="53eec-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="53eec-249">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="53eec-249">**Create Subdomain**</span></span>|<span data-ttu-id="53eec-250">**Alias**</span><span class="sxs-lookup"><span data-stu-id="53eec-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="53eec-251">sip</span><span class="sxs-lookup"><span data-stu-id="53eec-251">sip</span></span>  <br/> |<span data-ttu-id="53eec-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="53eec-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="53eec-253">Selecteer **Subdomein maken.**</span><span class="sxs-lookup"><span data-stu-id="53eec-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="53eec-254">Selecteer op **de pagina Domeincentrum** **de optie Subdomeinen beheren.**</span><span class="sxs-lookup"><span data-stu-id="53eec-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="53eec-255">Zoek in **de sectie Subdomeinoverzicht** het **sip-subdomein** dat u zojuist hebt gemaakt en selecteer vervolgens het besturingselement Panel **(v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="53eec-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="53eec-256">Selecteer **dns-instellingen** bewerken in het gebied **Subdomeininstellingen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="53eec-257">Selecteer CNAME in de sectie **A/AAAA Records (IP-adressen)** in het **gebied IP-adres (A** **Record).**</span><span class="sxs-lookup"><span data-stu-id="53eec-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="53eec-258">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="53eec-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="53eec-259">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="53eec-259">**Create Subdomain**</span></span>|<span data-ttu-id="53eec-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="53eec-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="53eec-261">sip</span><span class="sxs-lookup"><span data-stu-id="53eec-261">sip</span></span>  <br/> |<span data-ttu-id="53eec-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="53eec-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="53eec-263">Schakel het selectievakje in voor de vrijwaring **ik ben op de** hoogte en selecteer opslaan. </span><span class="sxs-lookup"><span data-stu-id="53eec-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="53eec-264">Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="53eec-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="53eec-265">CNAME-records die nodig zijn voor MDM</span><span class="sxs-lookup"><span data-stu-id="53eec-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53eec-266">Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="53eec-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="53eec-267">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="53eec-267">**Create Subdomain**</span></span>|<span data-ttu-id="53eec-268">**Alias**</span><span class="sxs-lookup"><span data-stu-id="53eec-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="53eec-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="53eec-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="53eec-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="53eec-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="53eec-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="53eec-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="53eec-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="53eec-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="53eec-273">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="53eec-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53eec-274">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="53eec-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="53eec-275">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="53eec-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="53eec-276">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53eec-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="53eec-277">Voeg in plaats daarvan de vereiste Microsoft-waarden  toe aan de huidige record, zodat u één SPF-record hebt met beide sets waarden.</span><span class="sxs-lookup"><span data-stu-id="53eec-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="53eec-278">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="53eec-278">Need examples?</span></span> <span data-ttu-id="53eec-279">Bekijk deze [Externe Domain Name System-records voor Microsoft](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="53eec-279">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="53eec-280">Als u uw SPF-record wilt valideren, kunt u een van deze[SPF-validatiehulpmiddelen gebruiken.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="53eec-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
<span data-ttu-id="53eec-281">Volg onderstaande stappen of [bekijk de video (start op 5:09)]().</span><span class="sxs-lookup"><span data-stu-id="53eec-281">Follow the steps below or [watch the video (start at 5:09)]().</span></span>
  
> [!NOTE]
> <span data-ttu-id="53eec-282">Als u zich hebt geregistreerd bij 1und1.de, [meld u dan hier aan.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="53eec-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="53eec-283">Als u wilt beginnen, gaat u via deze [koppeling](https://my.1and1.com/)naar uw domeinenpagina op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="53eec-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="53eec-284">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="53eec-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="53eec-285">Selecteer **Domeinen beheren.**</span><span class="sxs-lookup"><span data-stu-id="53eec-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="53eec-286">Zoek op **de pagina Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Panel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="53eec-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="53eec-287">Selecteer **dns-instellingen** bewerken in het gebied **Domeininstellingen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="53eec-288">Selecteer in **de sectie TXT- en SRV-records** de optie **Record toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="53eec-289">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="53eec-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="53eec-290">Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="53eec-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="53eec-291">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="53eec-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="53eec-292">**Type**</span><span class="sxs-lookup"><span data-stu-id="53eec-292">**Type**</span></span>|<span data-ttu-id="53eec-293">**Voorvoegsel**</span><span class="sxs-lookup"><span data-stu-id="53eec-293">**Prefix**</span></span>|<span data-ttu-id="53eec-294">**Naamwaarde**</span><span class="sxs-lookup"><span data-stu-id="53eec-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="53eec-295">TXT</span><span class="sxs-lookup"><span data-stu-id="53eec-295">TXT</span></span>  <br/> |<span data-ttu-id="53eec-296">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="53eec-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="53eec-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="53eec-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="53eec-298">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="53eec-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT-record](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="53eec-300">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="53eec-300">Select **Save**.</span></span><br/><span data-ttu-id="53eec-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="53eec-302">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="53eec-302">Select **Save**.</span></span><br/><span data-ttu-id="53eec-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="53eec-304">Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="53eec-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="53eec-305">![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="53eec-306">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="53eec-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="53eec-307">Volg onderstaande stappen of [bekijk de video (start op 5:51)]().</span><span class="sxs-lookup"><span data-stu-id="53eec-307">Follow the steps below or [watch the video (start at 5:51)]().</span></span>
  
> [!NOTE]
> <span data-ttu-id="53eec-308">Als u zich hebt geregistreerd bij 1und1.de, [meld u dan hier aan.](https://go.microsoft.com/fwlink/?linkid=859152)</span><span class="sxs-lookup"><span data-stu-id="53eec-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="53eec-309">Als u wilt beginnen, gaat u via deze [koppeling](https://my.1and1.com/)naar uw domeinenpagina op 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="53eec-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="53eec-310">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="53eec-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="53eec-311">Selecteer **Domeinen beheren.**</span><span class="sxs-lookup"><span data-stu-id="53eec-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="53eec-312">Zoek op **de pagina Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Panel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="53eec-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="53eec-313">Selecteer **dns-instellingen** bewerken in het gebied **Domeininstellingen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="53eec-314">Selecteer in **de sectie TXT- en SRV-records** de optie **Record toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="53eec-315">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="53eec-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="53eec-316">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="53eec-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="53eec-317">(Kies de **waarden Type** en **TTL** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="53eec-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="53eec-318">**Type**</span><span class="sxs-lookup"><span data-stu-id="53eec-318">**Type**</span></span>|<span data-ttu-id="53eec-319">**Service**</span><span class="sxs-lookup"><span data-stu-id="53eec-319">**Service**</span></span>|<span data-ttu-id="53eec-320">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="53eec-320">**Protocol**</span></span>|<span data-ttu-id="53eec-321">**Naam**</span><span class="sxs-lookup"><span data-stu-id="53eec-321">**Name**</span></span>|<span data-ttu-id="53eec-322">**Host**</span><span class="sxs-lookup"><span data-stu-id="53eec-322">**Host**</span></span>|<span data-ttu-id="53eec-323">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="53eec-323">**Priority**</span></span>|<span data-ttu-id="53eec-324">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="53eec-324">**Weight**</span></span>|<span data-ttu-id="53eec-325">**Poort**</span><span class="sxs-lookup"><span data-stu-id="53eec-325">**Port**</span></span>|<span data-ttu-id="53eec-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="53eec-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="53eec-327">SRV</span><span class="sxs-lookup"><span data-stu-id="53eec-327">SRV</span></span>  <br/> |<span data-ttu-id="53eec-328">sip</span><span class="sxs-lookup"><span data-stu-id="53eec-328">sip</span></span>  <br/> |<span data-ttu-id="53eec-329">tls</span><span class="sxs-lookup"><span data-stu-id="53eec-329">tls</span></span>  <br/> |<span data-ttu-id="53eec-330">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="53eec-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="53eec-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="53eec-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="53eec-332">100</span><span class="sxs-lookup"><span data-stu-id="53eec-332">100</span></span>  <br/> |<span data-ttu-id="53eec-333">1</span><span class="sxs-lookup"><span data-stu-id="53eec-333">1</span></span>  <br/> |<span data-ttu-id="53eec-334">443</span><span class="sxs-lookup"><span data-stu-id="53eec-334">443</span></span>  <br/> |<span data-ttu-id="53eec-335">3600 (1 uur)</span><span class="sxs-lookup"><span data-stu-id="53eec-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="53eec-336">SRV</span><span class="sxs-lookup"><span data-stu-id="53eec-336">SRV</span></span>  <br/> |<span data-ttu-id="53eec-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="53eec-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="53eec-338">tcp</span><span class="sxs-lookup"><span data-stu-id="53eec-338">tcp</span></span>  <br/> |<span data-ttu-id="53eec-339">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="53eec-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="53eec-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="53eec-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="53eec-341">100</span><span class="sxs-lookup"><span data-stu-id="53eec-341">100</span></span>  <br/> |<span data-ttu-id="53eec-342">1</span><span class="sxs-lookup"><span data-stu-id="53eec-342">1</span></span>  <br/> |<span data-ttu-id="53eec-343">5061</span><span class="sxs-lookup"><span data-stu-id="53eec-343">5061</span></span>  <br/> |<span data-ttu-id="53eec-344">3600 (1 uur)</span><span class="sxs-lookup"><span data-stu-id="53eec-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1 &amp; 1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="53eec-346">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="53eec-346">Select **Save**.</span></span> <br/><span data-ttu-id="53eec-347">![1 &amp; 1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="53eec-348">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="53eec-348">Select **Save**.</span></span> <br/><span data-ttu-id="53eec-349">![1 &amp; 1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="53eec-350">Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="53eec-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="53eec-351">![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="53eec-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="53eec-352">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="53eec-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="53eec-353">Selecteer in **de sectie TXT- en SRV-records** de optie **Record toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="53eec-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="53eec-354">Maak in **het gebied Record** toevoegen een record met de waarden uit de andere rij in de tabel en selecteer vervolgens opnieuw **Toevoegen,** Opslaan **en** **Ja** om de record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="53eec-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="53eec-p120">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="53eec-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
