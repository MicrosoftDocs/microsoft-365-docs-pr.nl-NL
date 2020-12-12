---
title: DNS-records bij Freenom maken voor Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Freenom voor Microsoft.
ms.openlocfilehash: b958a69d1dad9a0b56cf954d12cd42e40d6d4fea
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657873"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="1dd4a-103">DNS-records bij Freenom maken voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="1dd4a-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="1dd4a-104">[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml) als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-104">[Check the Domains FAQ ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="1dd4a-105">De Freenom-website biedt geen ondersteuning voor SRV-records, wat betekent dat meerdere functies van Skype voor bedrijven online en Outlook Web app niet werken.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="1dd4a-106">Ongeacht welke Microsoft-abonnement u gebruikt, er zijn belangrijke Servicebeperkingen en u kunt ook overschakelen naar een andere DNS-hosting provider.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="1dd4a-107">Als u ondanks de Servicebeperkingen besluit uw eigen DNS-records voor Microsoft te beheren bij Freenom, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail en andere services in te stellen.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="1dd4a-p102">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1dd4a-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1dd4a-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="1dd4a-111">Add a TXT record for verification</span></span>
<span data-ttu-id="1dd4a-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd4a-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="1dd4a-p103">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dd4a-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1dd4a-117">Als u wilt beginnen, gaat u naar uw domeinen pagina in Freenom met behulp van [deze koppeling](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="1dd4a-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="1dd4a-118">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-118">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="1dd4a-120">Selecteer **Services** en selecteer vervolgens **My Domains**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="1dd4a-122">Selecteer **Manage Domain** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="1dd4a-124">Selecteer **Manage FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="1dd4a-126">Ga onder **Add Record** naar de kolom **Type** en kies **TXT** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="1dd4a-128">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="1dd4a-129">**Naam**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-129">**Name**</span></span>|<span data-ttu-id="1dd4a-130">**Type**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-130">**Type**</span></span>|<span data-ttu-id="1dd4a-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-131">**TTL**</span></span>|<span data-ttu-id="1dd4a-132">**Doel**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1dd4a-133">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="1dd4a-134">TXT</span><span class="sxs-lookup"><span data-stu-id="1dd4a-134">TXT</span></span>  <br/> |<span data-ttu-id="1dd4a-135">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1dd4a-136">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="1dd4a-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="1dd4a-137">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-137">**Note:** This is an example.</span></span> <span data-ttu-id="1dd4a-138">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="1dd4a-139">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="1dd4a-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="1dd4a-141">Selecteer **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-141">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="1dd4a-143">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1dd4a-144">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="1dd4a-145">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1dd4a-146">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1dd4a-147">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1dd4a-148">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1dd4a-149">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1dd4a-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1dd4a-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1dd4a-153">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="1dd4a-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1dd4a-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd4a-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="1dd4a-155">Als u wilt beginnen, gaat u naar uw domeinen pagina in Freenom met behulp van [deze koppeling](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="1dd4a-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="1dd4a-156">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-156">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="1dd4a-158">Selecteer **Services** en selecteer vervolgens **My Domains**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="1dd4a-160">Selecteer **Manage Domain** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="1dd4a-162">Stel de naam in voor uw domein in de standaard Freenom-naamservers.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="1dd4a-163">Selecteer **beheerprogramma's** en selecteer vervolgens **Naamservers**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="1dd4a-165">Controleer of **use default naamservers** is geselecteerd en selecteer vervolgens **Change naamservers**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="1dd4a-167">Selecteer **Manage FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-167">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Selecteer Manage Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="1dd4a-169">Ga onder **Add Record** naar de kolom **Type** en kies **MX** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="1dd4a-171">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="1dd4a-172">**Naam**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-172">**Name**</span></span>|<span data-ttu-id="1dd4a-173">**Type**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-173">**Type**</span></span>|<span data-ttu-id="1dd4a-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-174">**TTL**</span></span>|<span data-ttu-id="1dd4a-175">**Doel**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-175">**Target**</span></span>|<span data-ttu-id="1dd4a-176">**Priority**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1dd4a-177">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="1dd4a-178">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="1dd4a-179">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1dd4a-180">\<domain-key\>. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1dd4a-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1dd4a-181">**Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="1dd4a-182">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="1dd4a-182">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1dd4a-183">10</span><span class="sxs-lookup"><span data-stu-id="1dd4a-183">10</span></span>  <br/> <span data-ttu-id="1dd4a-184">Zie [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="1dd4a-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="1dd4a-186">Selecteer **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-186">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="1dd4a-188">Als er andere MX-records zijn, verwijdert u deze allemaal.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="1dd4a-189">Selecteer **verwijderen** voor elke record.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-189">For each record, select **Delete**.</span></span> <span data-ttu-id="1dd4a-190">Als u wilt dat het bericht **u echt wilt verwijderen?** wordt weergegeven, selecteert u **OK**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1dd4a-191">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="1dd4a-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1dd4a-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd4a-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="1dd4a-193">Als u wilt beginnen, gaat u naar uw domeinen pagina in Freenom met behulp van [deze koppeling](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="1dd4a-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="1dd4a-194">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-194">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="1dd4a-196">Selecteer **Services** en selecteer vervolgens **My Domains**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="1dd4a-198">Selecteer **Manage Domain** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="1dd4a-200">Selecteer **Manage FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-200">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Selecteer Manage Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="1dd4a-202">Ga onder **Add Record** naar de kolom **Type** en kies **CNAME** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="1dd4a-p113">Maak de eerste CNAME-record. Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="1dd4a-206">**Naam**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-206">**Name**</span></span>|<span data-ttu-id="1dd4a-207">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-207">**Record type**</span></span>|<span data-ttu-id="1dd4a-208">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-208">**TTL**</span></span>|<span data-ttu-id="1dd4a-209">**Doel**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1dd4a-210">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1dd4a-210">autodiscover</span></span>  <br/> |<span data-ttu-id="1dd4a-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="1dd4a-211">CNAME</span></span>  <br/> |<span data-ttu-id="1dd4a-212">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1dd4a-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1dd4a-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="1dd4a-214">sip</span><span class="sxs-lookup"><span data-stu-id="1dd4a-214">sip</span></span>  <br/> |<span data-ttu-id="1dd4a-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="1dd4a-215">CNAME</span></span>  <br/> |<span data-ttu-id="1dd4a-216">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1dd4a-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dd4a-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1dd4a-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1dd4a-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1dd4a-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="1dd4a-219">CNAME</span></span>  <br/> |<span data-ttu-id="1dd4a-220">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1dd4a-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dd4a-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1dd4a-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1dd4a-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1dd4a-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="1dd4a-223">CNAME</span></span>  <br/> |<span data-ttu-id="1dd4a-224">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1dd4a-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1dd4a-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="1dd4a-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1dd4a-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1dd4a-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="1dd4a-227">CNAME</span></span>  <br/> |<span data-ttu-id="1dd4a-228">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1dd4a-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1dd4a-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="1dd4a-231">Selecteer **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="1dd4a-233">Herhaal de vorige stappen om de vijf andere CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="1dd4a-234">Typ of kopieer en plak voor elke record de waarden uit de volgende rij van de bovenstaande tabel in de velden voor die record.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1dd4a-235">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="1dd4a-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1dd4a-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd4a-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1dd4a-237">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1dd4a-238">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1dd4a-239">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1dd4a-240">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="1dd4a-241">Als u wilt beginnen, gaat u naar uw domeinen pagina in Freenom met behulp van [deze koppeling](https://my.freenom.com/).</span><span class="sxs-lookup"><span data-stu-id="1dd4a-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="1dd4a-242">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-242">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="1dd4a-244">Selecteer **Services** en selecteer vervolgens **My Domains**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="1dd4a-246">Selecteer **Manage Domain** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="1dd4a-248">Selecteer **Manage FREENOM DNS**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-248">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Selecteer Manage Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="1dd4a-250">Ga onder **Add Record** naar de kolom **Type** en kies **TXT** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="1dd4a-252">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="1dd4a-253">**Naam**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-253">**Name**</span></span>|<span data-ttu-id="1dd4a-254">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-254">**Record type**</span></span>|<span data-ttu-id="1dd4a-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-255">**TTL**</span></span>|<span data-ttu-id="1dd4a-256">**Doel**</span><span class="sxs-lookup"><span data-stu-id="1dd4a-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1dd4a-257">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="1dd4a-258">TXT</span><span class="sxs-lookup"><span data-stu-id="1dd4a-258">TXT</span></span>  <br/> |<span data-ttu-id="1dd4a-259">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="1dd4a-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1dd4a-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1dd4a-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="1dd4a-261">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="1dd4a-263">Selecteer **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="1dd4a-263">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

