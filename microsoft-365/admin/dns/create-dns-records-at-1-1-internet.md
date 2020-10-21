---
title: DNS-records bij 1&1 IONOS voor Microsoft maken
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
description: Leer hoe u uw domein verifieert en DNS-records voor e-mail, Skype voor bedrijven online en andere services voor e-mail, Skype voor bedrijven online en andere services voor 1&1 IONOS voor Microsoft hebt ingesteld.
ms.openlocfilehash: b88fa4f14104f60f22857bb9cfdc9e6366d2c303
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646389"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="1dd0a-103">DNS-records bij 1&1 IONOS voor Microsoft maken</span><span class="sxs-lookup"><span data-stu-id="1dd0a-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="1dd0a-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="1dd0a-105">Met 1&1 IONOS kan een domein niet zowel een MX-record als een Autodiscover-record van het hoogste niveau bevatten.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="1dd0a-106">Dit beperkt de manieren waarop u Exchange Online voor Microsoft kunt configureren.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="1dd0a-107">Er is een tijdelijke oplossing, maar u kunt deze **alleen** gebruiken als u al ervaring hebt met het maken van subdomeinen voor 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="1dd0a-108">> als deze [servicebeperking](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) u kiest voor het beheren van uw eigen Microsoft DNS-records bij 1&1 IONOS, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor E-mail, Skype voor bedrijven online.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-108">> If despite this [service limitation](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="1dd0a-109">Nadat u deze records bij 1&1 IONOS hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="1dd0a-p102">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1dd0a-113">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="1dd0a-113">Add a TXT record for verification</span></span>

<span data-ttu-id="1dd0a-p103">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dd0a-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="1dd0a-118">Volg onderstaande stappen of [bekijk de video (start op 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-118">Follow the steps below or [watch the video (start at 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
1. <span data-ttu-id="1dd0a-119">Als u wilt beginnen, gaat u naar uw domeinen pagina op 1&1 IONOS met behulp van [deze koppeling](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1dd0a-120">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1dd0a-121">Selecteer **domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1dd0a-122">Zoek op de pagina **Domain Center** naar het domein dat u wilt bijwerken en selecteer het besturingselement **panel** ( **v**) voor het domein.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1dd0a-123">Selecteer in het gebied **Domain Settings** de optie **Edit DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1dd0a-124">Selecteer in de sectie **txt and SRV records** de optie **add record**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="1dd0a-125">Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1dd0a-126">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="1dd0a-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-127">**Type**</span></span> <br/> |<span data-ttu-id="1dd0a-128">**Voorvoegsel**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-128">**Prefix**</span></span> <br/> |<span data-ttu-id="1dd0a-129">**Naamwaarde**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="1dd0a-130">TXT</span><span class="sxs-lookup"><span data-stu-id="1dd0a-130">TXT</span></span>  <br/> |<span data-ttu-id="1dd0a-131">(Laat dit veld leeg)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="1dd0a-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1dd0a-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1dd0a-133">Opmerking: dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-133">NOTE: This is an example.</span></span> <span data-ttu-id="1dd0a-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="1dd0a-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="1dd0a-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="1dd0a-136">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="1dd0a-137">Selecteer opnieuw **Opslaan** .</span><span class="sxs-lookup"><span data-stu-id="1dd0a-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="1dd0a-138">Selecteer in het dialoogvenster **Edit DNS Settings** de optie **Yes**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="1dd0a-139">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1dd0a-140">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="1dd0a-141">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1dd0a-142">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1dd0a-143">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="1dd0a-144">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="1dd0a-145">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1dd0a-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1dd0a-149">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="1dd0a-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1dd0a-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd0a-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="1dd0a-151">Volg onderstaande stappen of [bekijk de video (start op 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-151">Follow the steps below or [watch the video (start at 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dd0a-152">Als u zich hebt geregistreerd bij 1und1.de, [meldt u zich hier](https://go.microsoft.com/fwlink/?linkid=859152)aan.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1dd0a-153">Als u wilt beginnen, gaat u naar uw domeinen pagina op 1&1 IONOS met behulp van [deze koppeling](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1dd0a-154">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1dd0a-155">Selecteer **domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1dd0a-156">Zoek op de pagina **Domain Center** naar het domein dat u wilt bijwerken en selecteer het besturingselement **panel** ( **v**) voor het domein.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1dd0a-157">Selecteer in het gebied **Domain Settings** de optie **Edit DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1dd0a-158">Selecteer in de sectie **MX records** in het gebied **Mail Exchanger (MX record)** de optie **other mailserver**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="1dd0a-159">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="1dd0a-160">![afbeelding van 1 &amp; 2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="1dd0a-161">Als er al MX-records worden vermeld, verwijdert u deze door de records te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="1dd0a-162">(Als er nog geen MX-records worden vermeld, gaat u verder met de volgende stap.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="1dd0a-163">![afbeelding van 1 &amp; 2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="1dd0a-164">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de **MX 1**-record.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="1dd0a-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-165">**MX 1**</span></span>|<span data-ttu-id="1dd0a-166">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="1dd0a-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1dd0a-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="1dd0a-168">Opmerking: u ontvangt uw \<domain-key\> van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="1dd0a-169">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="1dd0a-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1dd0a-170">10</span><span class="sxs-lookup"><span data-stu-id="1dd0a-170">10</span></span>  <br/> <span data-ttu-id="1dd0a-171">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="1dd0a-171">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | 
    
    ![1 en 1-Configureer 2 en 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="1dd0a-173">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-173">Select **Save**.</span></span><br/><span data-ttu-id="1dd0a-174">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="1dd0a-175">![afbeelding van 1 &amp; 2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="1dd0a-176">Selecteer in het dialoogvenster **Edit DNS Settings** de optie **Yes**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="1dd0a-177">![Ja selecteren in het dialoogvenster Edit DNS Settings](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1dd0a-178">De zes CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="1dd0a-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1dd0a-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd0a-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="1dd0a-180">1&1 IONOS vereist een tijdelijke oplossing zodat u een MX-record kunt gebruiken in combinatie met de CNAME-records die zijn vereist voor Microsoft-e-mailservices.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="1dd0a-181">Voor deze tijdelijke oplossing dient u een verzameling subdomeinen te maken voor 1&1 IONOS en deze toe te wijzen aan CNAME-records.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1dd0a-182">Zorg dat u ten minste twee beschikbare subdomeinen hebt voordat u deze procedure begint.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="1dd0a-183">U wordt aangeraden deze oplossing uitsluitend te maken als u al met ervaring subdomeinen hebt voor 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="1dd0a-184">Basis-CNAME-records</span><span class="sxs-lookup"><span data-stu-id="1dd0a-184">Basic CNAME records</span></span>

<span data-ttu-id="1dd0a-185">Volg onderstaande stappen of [bekijk de video (start op 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-185">Follow the steps below or [watch the video (start at 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dd0a-186">Als u zich hebt geregistreerd bij 1und1.de, [meldt u zich hier](https://go.microsoft.com/fwlink/?linkid=859152)aan.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1dd0a-187">Als u wilt beginnen, gaat u naar uw domeinen pagina op 1&1 IONOS met behulp van [deze koppeling](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1dd0a-188">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1dd0a-189">Selecteer **domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1dd0a-190">Zoek op de pagina **Domain Center** naar het domein dat u wilt bijwerken en selecteer **Manage subdomains**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="1dd0a-191">![afbeelding van 1 &amp; 3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="1dd0a-192">Nu maakt u twee subdomeinen en stelt u voor elk subdomein een **Alias**-waarde in.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="1dd0a-193">(Dit is nodig omdat 1&1 IONOS ondersteuning biedt voor één CNAME-record op het hoogste niveau, maar Microsoft heeft meerdere CNAME-records nodig.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="1dd0a-194">Eerst maakt u het autodiscover-subdomein.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="1dd0a-195">Selecteer in de sectie **subdomain Overview** de optie **Create Subdomain**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="1dd0a-p113">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="1dd0a-199">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-199">**Create Subdomain**</span></span>|<span data-ttu-id="1dd0a-200">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1dd0a-201">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1dd0a-201">autodiscover</span></span>  <br/> |<span data-ttu-id="1dd0a-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1dd0a-202">autodiscover.outlook.com</span></span>   | 

    ![afbeelding van 1 &amp; 3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="1dd0a-204">Selecteer **subdomein maken**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="1dd0a-205">![afbeelding van 1 &amp; 3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="1dd0a-206">Zoek in de sectie **subdomain Overview** het **Autodiscover** -subdomein dat u zojuist hebt gemaakt, en selecteer het besturingselement **panel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="1dd0a-207">![afbeelding van 1 &amp; 3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="1dd0a-208">Selecteer in het gebied **subdomain Settings** de optie **Edit DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="1dd0a-209">![afbeelding van 1 &amp; 3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="1dd0a-210">Selecteer **CNAME**in het gebied **IP Address (a record)** van de sectie **A/AAAA records (IP** addresses).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="1dd0a-211">![afbeelding van 1 &amp; 3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="1dd0a-212">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="1dd0a-213">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-213">**Create Subdomain**</span></span>|<span data-ttu-id="1dd0a-214">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1dd0a-215">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1dd0a-215">autodiscover</span></span>  <br/> |<span data-ttu-id="1dd0a-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1dd0a-216">autodiscover.outlook.com</span></span>   |

    ![afbeelding van 1 &amp; 3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="1dd0a-218">Schakel het selectievakje in voor de vrijwaring **I am aware**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="1dd0a-219">![afbeelding van 1 &amp; 3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="1dd0a-220">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-220">Select **Save**.</span></span><br/><span data-ttu-id="1dd0a-221">![afbeelding van 1 &amp; 3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="1dd0a-222">Extra CNAME-records</span><span class="sxs-lookup"><span data-stu-id="1dd0a-222">Additional CNAME records</span></span>

<span data-ttu-id="1dd0a-p114">Met de extra CNAME-records die in de volgende procedure worden gemaakt, worden Skype voor Bedrijven Online-services ingeschakeld. U gebruikt dezelfde stappen die u eerder hebt gebruikt om de twee CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="1dd0a-225">Maak het derde subdomein (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="1dd0a-226">Selecteer in de sectie **subdomain Overview** de optie **Create Subdomain**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="1dd0a-p115">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="1dd0a-229">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-229">**Create Subdomain**</span></span>|<span data-ttu-id="1dd0a-230">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1dd0a-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1dd0a-231">lyncdiscover</span></span>   |<span data-ttu-id="1dd0a-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dd0a-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="1dd0a-233">Selecteer **subdomein maken**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="1dd0a-234">Selecteer op de pagina **Domain Center** de optie **Manage subdomains**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="1dd0a-235">Zoek in de sectie **subdomain Overview** het **lyncdiscover** -subdomein dat u zojuist hebt gemaakt, en selecteer het besturingselement **panel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="1dd0a-236">Selecteer in het gebied **subdomain Settings** de optie **Edit DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="1dd0a-237">Selecteer **CNAME**in het gebied **IP Address (a record)** van de sectie **A/AAAA records (IP** addresses).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="1dd0a-238">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="1dd0a-239">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-239">**Create Subdomain**</span></span>|<span data-ttu-id="1dd0a-240">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1dd0a-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1dd0a-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1dd0a-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dd0a-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="1dd0a-243">Schakel het selectievakje in voor de vrijwaring **I am aware** en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="1dd0a-244">Selecteer in het dialoogvenster **Edit DNS Settings** de optie **Yes**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="1dd0a-245">Maak als volgt het vierde subdomein (SIP):</span><span class="sxs-lookup"><span data-stu-id="1dd0a-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="1dd0a-246">Selecteer in de sectie **subdomain Overview** de optie **Create Subdomain**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="1dd0a-p116">Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="1dd0a-249">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-249">**Create Subdomain**</span></span>|<span data-ttu-id="1dd0a-250">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1dd0a-251">sip</span><span class="sxs-lookup"><span data-stu-id="1dd0a-251">sip</span></span>  <br/> |<span data-ttu-id="1dd0a-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dd0a-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="1dd0a-253">Selecteer **subdomein maken**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="1dd0a-254">Selecteer op de pagina **Domain Center** de optie **Manage subdomains**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="1dd0a-255">Zoek in de sectie **subdomain Overview** het **SIP** -subdomein dat u zojuist hebt gemaakt, en selecteer het besturingselement **panel (v)** voor dat subdomein.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="1dd0a-256">Selecteer in het gebied **subdomain Settings** de optie **Edit DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="1dd0a-257">Selecteer **CNAME**in het gebied **IP Address (a record)** van de sectie **A/AAAA records (IP** addresses).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="1dd0a-258">Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="1dd0a-259">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-259">**Create Subdomain**</span></span>|<span data-ttu-id="1dd0a-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1dd0a-261">sip</span><span class="sxs-lookup"><span data-stu-id="1dd0a-261">sip</span></span>  <br/> |<span data-ttu-id="1dd0a-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dd0a-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="1dd0a-263">Schakel het selectievakje in voor de vrijwaring **I am aware** en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="1dd0a-264">Selecteer in het dialoogvenster **Edit DNS Settings** de optie **Yes**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="1dd0a-265">CNAME-records die nodig zijn voor MDM</span><span class="sxs-lookup"><span data-stu-id="1dd0a-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1dd0a-266">Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="1dd0a-267">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-267">**Create Subdomain**</span></span>|<span data-ttu-id="1dd0a-268">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1dd0a-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1dd0a-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1dd0a-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1dd0a-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="1dd0a-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1dd0a-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1dd0a-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1dd0a-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1dd0a-273">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="1dd0a-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1dd0a-274">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1dd0a-275">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1dd0a-276">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1dd0a-277">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="1dd0a-278">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="1dd0a-278">Need examples?</span></span> <span data-ttu-id="1dd0a-279">Bekijk deze [Externe Domain Name System-records voor Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-279">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="1dd0a-280">Voor het valideren van uw SPF-record gebruikt u een van deze[SPF-validatie hulpmiddelen](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="1dd0a-281">Volg onderstaande stappen of [bekijk de video (start op 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-281">Follow the steps below or [watch the video (start at 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dd0a-282">Als u zich hebt geregistreerd bij 1und1.de, [meldt u zich hier](https://go.microsoft.com/fwlink/?linkid=859152)aan.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1dd0a-283">Als u wilt beginnen, gaat u naar uw domeinen pagina op 1&1 IONOS met behulp van [deze koppeling](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1dd0a-284">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1dd0a-285">Selecteer **domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1dd0a-286">Zoek op de pagina **Domain Center** naar het domein dat u wilt bijwerken en selecteer het besturingselement **panel** (**v**) voor het domein.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1dd0a-287">Selecteer in het gebied **Domain Settings** de optie **Edit DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1dd0a-288">Selecteer in de sectie **txt and SRV records** de optie **add record**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="1dd0a-289">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="1dd0a-290">Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="1dd0a-291">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="1dd0a-292">**Type**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-292">**Type**</span></span>|<span data-ttu-id="1dd0a-293">**Voorvoegsel**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-293">**Prefix**</span></span>|<span data-ttu-id="1dd0a-294">**Naamwaarde**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1dd0a-295">TXT</span><span class="sxs-lookup"><span data-stu-id="1dd0a-295">TXT</span></span>  <br/> |<span data-ttu-id="1dd0a-296">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1dd0a-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1dd0a-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1dd0a-298">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT-record](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="1dd0a-300">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-300">Select **Save**.</span></span><br/><span data-ttu-id="1dd0a-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="1dd0a-302">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-302">Select **Save**.</span></span><br/><span data-ttu-id="1dd0a-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="1dd0a-304">Selecteer in het dialoogvenster **Edit DNS Settings** de optie **Yes**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="1dd0a-305">![Ja selecteren in het dialoogvenster Edit DNS Settings](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1dd0a-306">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="1dd0a-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="1dd0a-307">Volg onderstaande stappen of [bekijk de video (start op 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-307">Follow the steps below or [watch the video (start at 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dd0a-308">Als u zich hebt geregistreerd bij 1und1.de, [meldt u zich hier](https://go.microsoft.com/fwlink/?linkid=859152)aan.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1dd0a-309">Als u wilt beginnen, gaat u naar uw domeinen pagina op 1&1 IONOS met behulp van [deze koppeling](https://my.1and1.com/).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1dd0a-310">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1dd0a-311">Selecteer **domeinen beheren**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1dd0a-312">Zoek op de pagina **Domain Center** naar het domein dat u wilt bijwerken en selecteer het besturingselement **panel** ( **v**) voor het domein.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1dd0a-313">Selecteer in het gebied **Domain Settings** de optie **Edit DNS Settings**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1dd0a-314">Selecteer in de sectie **txt and SRV records** de optie **add record**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="1dd0a-315">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="1dd0a-316">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="1dd0a-317">(Kies in de vervolgkeuzelijst de waarden **type** en **TTL** .)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1dd0a-318">**Type**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-318">**Type**</span></span>|<span data-ttu-id="1dd0a-319">**Service**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-319">**Service**</span></span>|<span data-ttu-id="1dd0a-320">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-320">**Protocol**</span></span>|<span data-ttu-id="1dd0a-321">**Naam**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-321">**Name**</span></span>|<span data-ttu-id="1dd0a-322">**Host**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-322">**Host**</span></span>|<span data-ttu-id="1dd0a-323">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-323">**Priority**</span></span>|<span data-ttu-id="1dd0a-324">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-324">**Weight**</span></span>|<span data-ttu-id="1dd0a-325">**Poort**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-325">**Port**</span></span>|<span data-ttu-id="1dd0a-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1dd0a-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1dd0a-327">SRV</span><span class="sxs-lookup"><span data-stu-id="1dd0a-327">SRV</span></span>  <br/> |<span data-ttu-id="1dd0a-328">sip</span><span class="sxs-lookup"><span data-stu-id="1dd0a-328">sip</span></span>  <br/> |<span data-ttu-id="1dd0a-329">tls</span><span class="sxs-lookup"><span data-stu-id="1dd0a-329">tls</span></span>  <br/> |<span data-ttu-id="1dd0a-330">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1dd0a-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dd0a-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1dd0a-332">100</span><span class="sxs-lookup"><span data-stu-id="1dd0a-332">100</span></span>  <br/> |<span data-ttu-id="1dd0a-333">1</span><span class="sxs-lookup"><span data-stu-id="1dd0a-333">1</span></span>  <br/> |<span data-ttu-id="1dd0a-334">443</span><span class="sxs-lookup"><span data-stu-id="1dd0a-334">443</span></span>  <br/> |<span data-ttu-id="1dd0a-335">3600 (1 uur)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="1dd0a-336">SRV</span><span class="sxs-lookup"><span data-stu-id="1dd0a-336">SRV</span></span>  <br/> |<span data-ttu-id="1dd0a-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="1dd0a-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="1dd0a-338">tcp</span><span class="sxs-lookup"><span data-stu-id="1dd0a-338">tcp</span></span>  <br/> |<span data-ttu-id="1dd0a-339">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1dd0a-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dd0a-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="1dd0a-341">100</span><span class="sxs-lookup"><span data-stu-id="1dd0a-341">100</span></span>  <br/> |<span data-ttu-id="1dd0a-342">1</span><span class="sxs-lookup"><span data-stu-id="1dd0a-342">1</span></span>  <br/> |<span data-ttu-id="1dd0a-343">5061</span><span class="sxs-lookup"><span data-stu-id="1dd0a-343">5061</span></span>  <br/> |<span data-ttu-id="1dd0a-344">3600 (1 uur)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-344">3600 (1 h)</span></span>  <br/> |  
    
    ![afbeelding van 1 &amp; 5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="1dd0a-346">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-346">Select **Save**.</span></span> <br/><span data-ttu-id="1dd0a-347">![afbeelding van 1 &amp; 5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="1dd0a-348">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-348">Select **Save**.</span></span> <br/><span data-ttu-id="1dd0a-349">![afbeelding van 1 &amp; 5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="1dd0a-350">Selecteer in het dialoogvenster **Edit DNS Settings** de optie **Yes**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="1dd0a-351">![Ja selecteren in het dialoogvenster Edit DNS Settings](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="1dd0a-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="1dd0a-352">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="1dd0a-353">Selecteer in de sectie **txt and SRV records** de optie **add record**.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="1dd0a-354">Maak in het gebied **add record** een record met behulp van de waarden uit de andere rij in de tabel en selecteer vervolgens opnieuw **add**, **Save**en **Yes** om de record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="1dd0a-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1dd0a-p120">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1dd0a-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
