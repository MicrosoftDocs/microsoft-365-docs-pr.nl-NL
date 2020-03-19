---
title: DNS-records bij Freenom maken voor Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Freenom voor Office 365.
ms.openlocfilehash: 16348eb03a6507e15d31d5c183bd91125d0236f6
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809959"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a><span data-ttu-id="266f5-103">DNS-records bij Freenom maken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="266f5-103">Create DNS records at Freenom for Office 365</span></span>

<span data-ttu-id="266f5-104">[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="266f5-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="266f5-p101">De website Freenom ondersteunt geen SRV-records, wat betekent dat verschillende functies in Skype voor Bedrijven Online en de webversie van Outlook niet werken. Ongeacht uw Office 365-abonnement, zijn de servicebeperkingen aanzienlijk. We adviseren dan ook om over te stappen op een andere DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="266f5-p101">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="266f5-107">Als u er ondanks de servicebeperkingen voor kiest om uw eigen DNS-records van Office 365 op Freenom te beheren, volgt u de stappen in dit artikel om uw domein te verifiëren en DNS-records in te stellen voor e-mail en andere services.</span><span class="sxs-lookup"><span data-stu-id="266f5-107">If despite the service limitations, you choose to manage your own Office 365 DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="266f5-108">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="266f5-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="266f5-p102">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="266f5-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="266f5-112">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="266f5-112">Add a TXT record for verification</span></span>
<span data-ttu-id="266f5-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="266f5-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="266f5-p103">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="266f5-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="266f5-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="266f5-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="266f5-118">Ga om te beginnen naar de pagina domeinen in Freenom via [deze link.](https://my.freenom.com/)</span><span class="sxs-lookup"><span data-stu-id="266f5-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="266f5-119">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="266f5-119">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="266f5-121">Selecteer **Services**en selecteer **Mijn domeinen**.</span><span class="sxs-lookup"><span data-stu-id="266f5-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="266f5-123">Selecteer **Domein beheren**voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="266f5-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="266f5-125">Selecteer **Freenom DNS beheren**.</span><span class="sxs-lookup"><span data-stu-id="266f5-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="266f5-127">Ga onder **Add Record** naar de kolom **Type** en kies **TXT** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="266f5-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="266f5-129">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="266f5-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="266f5-130">**Name**</span><span class="sxs-lookup"><span data-stu-id="266f5-130">**Name**</span></span>|<span data-ttu-id="266f5-131">**Type**</span><span class="sxs-lookup"><span data-stu-id="266f5-131">**Type**</span></span>|<span data-ttu-id="266f5-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="266f5-132">**TTL**</span></span>|<span data-ttu-id="266f5-133">**Doel**</span><span class="sxs-lookup"><span data-stu-id="266f5-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="266f5-134">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="266f5-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="266f5-135">TXT</span><span class="sxs-lookup"><span data-stu-id="266f5-135">TXT</span></span>  <br/> |<span data-ttu-id="266f5-136">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="266f5-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="266f5-137">MS=msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="266f5-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="266f5-p106">**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="266f5-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="266f5-142">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="266f5-142">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="266f5-144">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="266f5-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="266f5-145">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="266f5-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="266f5-146">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="266f5-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="266f5-147">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="266f5-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="266f5-148">Selecteer **op** de pagina Domeinen het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="266f5-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="266f5-149">Selecteer **op** de pagina Setup de optie **Installatie starten**.</span><span class="sxs-lookup"><span data-stu-id="266f5-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="266f5-150">Selecteer **op** de pagina Domein verifiëren de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="266f5-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="266f5-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="266f5-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="266f5-154">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="266f5-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="266f5-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="266f5-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="266f5-156">Ga om te beginnen naar de pagina domeinen in Freenom via [deze link.](https://my.freenom.com/)</span><span class="sxs-lookup"><span data-stu-id="266f5-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="266f5-157">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="266f5-157">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="266f5-159">Selecteer **Services**en selecteer **Mijn domeinen**.</span><span class="sxs-lookup"><span data-stu-id="266f5-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="266f5-161">Selecteer **Domein beheren**voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="266f5-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="266f5-163">Stel de naam dient voor uw domein op de standaard Freenom-naamservers.</span><span class="sxs-lookup"><span data-stu-id="266f5-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="266f5-164">Selecteer **Beheerhulpprogramma's**en selecteer **vervolgens Nameservers**.</span><span class="sxs-lookup"><span data-stu-id="266f5-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="266f5-166">Controleer of **Standaardnaamservers gebruiken** is geselecteerd en selecteer **Naamservers wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="266f5-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="266f5-168">Selecteer **Freenom DNS beheren**.</span><span class="sxs-lookup"><span data-stu-id="266f5-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selecteert Freenom DNS beheren](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="266f5-170">Ga onder **Add Record** naar de kolom **Type** en kies **MX** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="266f5-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="266f5-172">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="266f5-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="266f5-173">**Name**</span><span class="sxs-lookup"><span data-stu-id="266f5-173">**Name**</span></span>|<span data-ttu-id="266f5-174">**Type**</span><span class="sxs-lookup"><span data-stu-id="266f5-174">**Type**</span></span>|<span data-ttu-id="266f5-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="266f5-175">**TTL**</span></span>|<span data-ttu-id="266f5-176">**Doel**</span><span class="sxs-lookup"><span data-stu-id="266f5-176">**Target**</span></span>|<span data-ttu-id="266f5-177">**Priority**</span><span class="sxs-lookup"><span data-stu-id="266f5-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="266f5-178">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="266f5-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="266f5-179">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="266f5-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="266f5-180">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="266f5-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="266f5-181">\<domeinsleutel\>.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="266f5-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="266f5-182">**Let op:** Haal uw \* \<domeinsleutel\> \* op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="266f5-182">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="266f5-183">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="266f5-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="266f5-184">10</span><span class="sxs-lookup"><span data-stu-id="266f5-184">10</span></span>  <br/> <span data-ttu-id="266f5-185">Zie [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="266f5-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="266f5-187">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="266f5-187">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="266f5-189">Als er andere MX-records zijn, verwijdert u ze allemaal.</span><span class="sxs-lookup"><span data-stu-id="266f5-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="266f5-190">Selecteer Voor elke record **Delete**.</span><span class="sxs-lookup"><span data-stu-id="266f5-190">For each record, select **Delete**.</span></span> <span data-ttu-id="266f5-191">Wanneer het bericht Wilt u dit item echt **OK** **verwijderen?**</span><span class="sxs-lookup"><span data-stu-id="266f5-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="266f5-192">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="266f5-192">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="266f5-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="266f5-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="266f5-194">Ga om te beginnen naar de pagina domeinen in Freenom via [deze link.](https://my.freenom.com/)</span><span class="sxs-lookup"><span data-stu-id="266f5-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="266f5-195">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="266f5-195">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="266f5-197">Selecteer **Services**en selecteer **Mijn domeinen**.</span><span class="sxs-lookup"><span data-stu-id="266f5-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="266f5-199">Selecteer **Domein beheren**voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="266f5-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="266f5-201">Selecteer **Freenom DNS beheren**.</span><span class="sxs-lookup"><span data-stu-id="266f5-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selecteert Freenom DNS beheren](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="266f5-203">Ga onder **Add Record** naar de kolom **Type** en kies **CNAME** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="266f5-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="266f5-p113">Maak de eerste CNAME-record. Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="266f5-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="266f5-207">**Naam**</span><span class="sxs-lookup"><span data-stu-id="266f5-207">**Name**</span></span>|<span data-ttu-id="266f5-208">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="266f5-208">**Record type**</span></span>|<span data-ttu-id="266f5-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="266f5-209">**TTL**</span></span>|<span data-ttu-id="266f5-210">**Doel**</span><span class="sxs-lookup"><span data-stu-id="266f5-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="266f5-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="266f5-211">autodiscover</span></span>  <br/> |<span data-ttu-id="266f5-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="266f5-212">CNAME</span></span>  <br/> |<span data-ttu-id="266f5-213">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="266f5-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="266f5-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="266f5-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="266f5-215">sip</span><span class="sxs-lookup"><span data-stu-id="266f5-215">sip</span></span>  <br/> |<span data-ttu-id="266f5-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="266f5-216">CNAME</span></span>  <br/> |<span data-ttu-id="266f5-217">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="266f5-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="266f5-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="266f5-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="266f5-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="266f5-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="266f5-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="266f5-220">CNAME</span></span>  <br/> |<span data-ttu-id="266f5-221">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="266f5-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="266f5-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="266f5-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="266f5-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="266f5-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="266f5-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="266f5-224">CNAME</span></span>  <br/> |<span data-ttu-id="266f5-225">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="266f5-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="266f5-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="266f5-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="266f5-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="266f5-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="266f5-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="266f5-228">CNAME</span></span>  <br/> |<span data-ttu-id="266f5-229">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="266f5-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="266f5-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="266f5-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="266f5-232">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="266f5-232">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="266f5-234">Herhaal de vorige stappen om de vijf andere CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="266f5-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="266f5-235">Typ of kopieer en plak voor elke record de waarden uit de volgende rij van de bovenstaande tabel in de velden voor die record.</span><span class="sxs-lookup"><span data-stu-id="266f5-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="266f5-236">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="266f5-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="266f5-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="266f5-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="266f5-238">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="266f5-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="266f5-239">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="266f5-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="266f5-240">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="266f5-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="266f5-241">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="266f5-241">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="266f5-242">Ga om te beginnen naar de pagina domeinen in Freenom via [deze link.](https://my.freenom.com/)</span><span class="sxs-lookup"><span data-stu-id="266f5-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="266f5-243">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="266f5-243">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="266f5-245">Selecteer **Services**en selecteer **Mijn domeinen**.</span><span class="sxs-lookup"><span data-stu-id="266f5-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="266f5-247">Selecteer **Domein beheren**voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="266f5-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="266f5-249">Selecteer **Freenom DNS beheren**.</span><span class="sxs-lookup"><span data-stu-id="266f5-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom selecteert Freenom DNS beheren](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="266f5-251">Ga onder **Add Record** naar de kolom **Type** en kies **TXT** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="266f5-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="266f5-253">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="266f5-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="266f5-254">**Naam**</span><span class="sxs-lookup"><span data-stu-id="266f5-254">**Name**</span></span>|<span data-ttu-id="266f5-255">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="266f5-255">**Record type**</span></span>|<span data-ttu-id="266f5-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="266f5-256">**TTL**</span></span>|<span data-ttu-id="266f5-257">**Doel**</span><span class="sxs-lookup"><span data-stu-id="266f5-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="266f5-258">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="266f5-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="266f5-259">TXT</span><span class="sxs-lookup"><span data-stu-id="266f5-259">TXT</span></span>  <br/> |<span data-ttu-id="266f5-260">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="266f5-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="266f5-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="266f5-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="266f5-262">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="266f5-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="266f5-264">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="266f5-264">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

