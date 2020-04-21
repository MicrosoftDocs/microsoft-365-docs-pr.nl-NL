---
title: DNS-records maken bij OVH voor Microsoft
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij OVH voor Microsoft.
ms.openlocfilehash: 01c455f54a7ee2efc6114dba1c01170b97ea5f71
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629285"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="b36f8-103">DNS-records maken bij OVH voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="b36f8-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="b36f8-104">[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="b36f8-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b36f8-105">Als OVH uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b36f8-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b36f8-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="b36f8-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="b36f8-107">DNS-records maken bij OVH voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="b36f8-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="b36f8-108">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="b36f8-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="b36f8-109">De CNAME-records toevoegen die voor Microsoft vereist zijn</span><span class="sxs-lookup"><span data-stu-id="b36f8-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="b36f8-110">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="b36f8-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="b36f8-111">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="b36f8-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="b36f8-112">Nadat u deze records bij OVH hebt toegevoegd, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="b36f8-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="b36f8-113">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)</span><span class="sxs-lookup"><span data-stu-id="b36f8-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b36f8-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b36f8-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b36f8-117">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="b36f8-117">Add a TXT record for verification</span></span>
<span data-ttu-id="b36f8-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="b36f8-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="b36f8-119">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="b36f8-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="b36f8-120">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="b36f8-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b36f8-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b36f8-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b36f8-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="b36f8-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="b36f8-126">Selecteer **onder Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="b36f8-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="b36f8-128">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="b36f8-130">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-130">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="b36f8-132">**TXT selecteren**</span><span class="sxs-lookup"><span data-stu-id="b36f8-132">Select **TXT**</span></span>
    
    ![OVH selecteert TXT-vermelding](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="b36f8-134">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="b36f8-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="b36f8-135">Als u een TTL-waarde wilt toewijzen, kiest **u Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="b36f8-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="b36f8-136">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="b36f8-136">**Record type**</span></span>|<span data-ttu-id="b36f8-137">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="b36f8-137">**Sub-domain**</span></span>|<span data-ttu-id="b36f8-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b36f8-138">**TTL**</span></span>|<span data-ttu-id="b36f8-139">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="b36f8-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b36f8-140">TXT</span><span class="sxs-lookup"><span data-stu-id="b36f8-140">TXT</span></span>  <br/> |<span data-ttu-id="b36f8-141">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="b36f8-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="b36f8-142">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="b36f8-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b36f8-143">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="b36f8-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="b36f8-144">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="b36f8-144">**Note:** This is an example.</span></span> <span data-ttu-id="b36f8-145">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="b36f8-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="b36f8-146">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="b36f8-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="b36f8-147">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-147">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="b36f8-149">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="b36f8-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b36f8-150">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="b36f8-150">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b36f8-151">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="b36f8-151">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b36f8-152">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="b36f8-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b36f8-153">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="b36f8-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b36f8-154">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b36f8-155">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b36f8-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b36f8-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b36f8-159">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="b36f8-159">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b36f8-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="b36f8-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="b36f8-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="b36f8-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="b36f8-164">Selecteer **onder Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="b36f8-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="b36f8-166">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="b36f8-168">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-168">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="b36f8-170">Selecteer **MX**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-170">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="b36f8-172">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="b36f8-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="b36f8-173">Als u een TTL-waarde wilt toewijzen, kiest **u Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="b36f8-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b36f8-174">OvH gebruikt standaard relatieve notatie voor het doel, dat de domeinnaam toevoegt aan het einde van de doelrecord.</span><span class="sxs-lookup"><span data-stu-id="b36f8-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="b36f8-175">Als u in plaats daarvan absolute notatie wilt gebruiken, voegt u een punt toe aan de doelrecord zoals in de onderstaande tabel.</span><span class="sxs-lookup"><span data-stu-id="b36f8-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="b36f8-176">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="b36f8-176">**Record type**</span></span>|<span data-ttu-id="b36f8-177">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="b36f8-177">**Sub-domain**</span></span>|<span data-ttu-id="b36f8-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b36f8-178">**TTL**</span></span>|<span data-ttu-id="b36f8-179">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="b36f8-179">**Priority**</span></span>|<span data-ttu-id="b36f8-180">**Doel**</span><span class="sxs-lookup"><span data-stu-id="b36f8-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b36f8-181">MX</span><span class="sxs-lookup"><span data-stu-id="b36f8-181">MX</span></span>  <br/> |<span data-ttu-id="b36f8-182">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="b36f8-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="b36f8-183">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="b36f8-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b36f8-184">10</span><span class="sxs-lookup"><span data-stu-id="b36f8-184">10</span></span>  <br/> <span data-ttu-id="b36f8-185">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="b36f8-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="b36f8-186">\<domain-key\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b36f8-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="b36f8-187">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="b36f8-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="b36f8-188">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="b36f8-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH MX record voor e-mail](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="b36f8-190">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-190">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="b36f8-192">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-192">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="b36f8-194">Als er andere MX-records zijn, verwijdert u deze in op de pagina **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="b36f8-195">Selecteer elke record en selecteer vervolgens in de kolom **Acties** het pictogram **Verwijderen** van prullenbak.</span><span class="sxs-lookup"><span data-stu-id="b36f8-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="b36f8-197">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b36f8-198">De CNAME-records toevoegen die voor Microsoft vereist zijn</span><span class="sxs-lookup"><span data-stu-id="b36f8-198">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b36f8-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="b36f8-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="b36f8-p113">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="b36f8-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="b36f8-203">Selecteer **onder Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="b36f8-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="b36f8-205">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="b36f8-207">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-207">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="b36f8-209">Selecteer **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-209">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="b36f8-211">Maak de eerste CNAME-record.</span><span class="sxs-lookup"><span data-stu-id="b36f8-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="b36f8-212">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="b36f8-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="b36f8-213">Als u een TTL-waarde wilt toewijzen, kiest **u Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="b36f8-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="b36f8-214">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="b36f8-214">**Record type**</span></span>|<span data-ttu-id="b36f8-215">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="b36f8-215">**Sub-domain**</span></span>|<span data-ttu-id="b36f8-216">**Doel**</span><span class="sxs-lookup"><span data-stu-id="b36f8-216">**Target**</span></span>|<span data-ttu-id="b36f8-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b36f8-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b36f8-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="b36f8-218">CNAME</span></span>  <br/> |<span data-ttu-id="b36f8-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b36f8-219">autodiscover</span></span>  <br/> |<span data-ttu-id="b36f8-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b36f8-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="b36f8-221">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="b36f8-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="b36f8-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="b36f8-222">CNAME</span></span>  <br/> |<span data-ttu-id="b36f8-223">sip</span><span class="sxs-lookup"><span data-stu-id="b36f8-223">sip</span></span>  <br/> |<span data-ttu-id="b36f8-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b36f8-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="b36f8-225">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="b36f8-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="b36f8-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="b36f8-226">CNAME</span></span>  <br/> |<span data-ttu-id="b36f8-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b36f8-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b36f8-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b36f8-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="b36f8-229">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="b36f8-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="b36f8-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="b36f8-230">CNAME</span></span>  <br/> |<span data-ttu-id="b36f8-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b36f8-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b36f8-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="b36f8-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="b36f8-233">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="b36f8-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="b36f8-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="b36f8-234">CNAME</span></span>  <br/> |<span data-ttu-id="b36f8-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b36f8-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b36f8-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b36f8-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="b36f8-237">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="b36f8-237">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME record](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="b36f8-239">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-239">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="b36f8-241">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="b36f8-242">Herhaal de vorige stappen om de vijf andere CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="b36f8-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="b36f8-243">Typ of kopieer en plak voor elke record de waarden uit de volgende rij van de bovenstaande tabel in de velden voor die record.</span><span class="sxs-lookup"><span data-stu-id="b36f8-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b36f8-244">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="b36f8-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b36f8-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="b36f8-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b36f8-246">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="b36f8-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b36f8-247">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="b36f8-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b36f8-248">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b36f8-248">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b36f8-249">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="b36f8-249">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="b36f8-p116">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="b36f8-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="b36f8-253">Selecteer **onder Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="b36f8-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="b36f8-255">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="b36f8-257">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-257">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="b36f8-259">Selecteer **TXT**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="b36f8-260">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="b36f8-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="b36f8-261">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="b36f8-261">**Record type**</span></span>|<span data-ttu-id="b36f8-262">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="b36f8-262">**Sub-domain**</span></span>|<span data-ttu-id="b36f8-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b36f8-263">**TTL**</span></span>|<span data-ttu-id="b36f8-264">**TXT-waarde**</span><span class="sxs-lookup"><span data-stu-id="b36f8-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b36f8-265">TXT</span><span class="sxs-lookup"><span data-stu-id="b36f8-265">TXT</span></span>  <br/> |<span data-ttu-id="b36f8-266">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="b36f8-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="b36f8-267">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="b36f8-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b36f8-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b36f8-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b36f8-269">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="b36f8-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH Voeg TXT-record voor SPF toe](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="b36f8-271">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-271">Select **Next**.</span></span>
    
    ![OVH Voeg TXT-record voor SPF toe en selecteer Volgende](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="b36f8-273">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-273">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b36f8-275">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="b36f8-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b36f8-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="b36f8-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="b36f8-p117">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="b36f8-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="b36f8-280">Selecteer **onder Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="b36f8-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="b36f8-282">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="b36f8-284">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-284">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="b36f8-286">Selecteer **SRV**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-286">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="b36f8-288">Maak de eerste SRV-record.</span><span class="sxs-lookup"><span data-stu-id="b36f8-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="b36f8-289">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="b36f8-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="b36f8-290">Als u een TTL-waarde wilt toewijzen, kiest **u Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="b36f8-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="b36f8-291">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="b36f8-291">**Record type**</span></span>|<span data-ttu-id="b36f8-292">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="b36f8-292">**Sub-domain**</span></span>|<span data-ttu-id="b36f8-293">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="b36f8-293">**Priority**</span></span>|<span data-ttu-id="b36f8-294">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="b36f8-294">**Weight**</span></span>|<span data-ttu-id="b36f8-295">**Poort**</span><span class="sxs-lookup"><span data-stu-id="b36f8-295">**Port**</span></span>|<span data-ttu-id="b36f8-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b36f8-296">**TTL**</span></span>|<span data-ttu-id="b36f8-297">**Doel**</span><span class="sxs-lookup"><span data-stu-id="b36f8-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b36f8-298">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="b36f8-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="b36f8-299">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="b36f8-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="b36f8-300">100</span><span class="sxs-lookup"><span data-stu-id="b36f8-300">100</span></span>  <br/> |<span data-ttu-id="b36f8-301">1</span><span class="sxs-lookup"><span data-stu-id="b36f8-301">1</span></span>  <br/> |<span data-ttu-id="b36f8-302">443</span><span class="sxs-lookup"><span data-stu-id="b36f8-302">443</span></span>  <br/> |<span data-ttu-id="b36f8-303">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="b36f8-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b36f8-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b36f8-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="b36f8-305">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="b36f8-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="b36f8-306">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="b36f8-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="b36f8-307">100</span><span class="sxs-lookup"><span data-stu-id="b36f8-307">100</span></span>  <br/> |<span data-ttu-id="b36f8-308">1</span><span class="sxs-lookup"><span data-stu-id="b36f8-308">1</span></span>  <br/> |<span data-ttu-id="b36f8-309">5061</span><span class="sxs-lookup"><span data-stu-id="b36f8-309">5061</span></span>  <br/> |<span data-ttu-id="b36f8-310">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="b36f8-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b36f8-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b36f8-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV record](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="b36f8-313">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-313">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="b36f8-315">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="b36f8-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="b36f8-p119">Herhaal de vorige stappen om de andere SRV-record te maken. Typ of kopieer en plak de waarden uit de tweede rij van de bovenstaande tabel in de vakken voor de tweede record.</span><span class="sxs-lookup"><span data-stu-id="b36f8-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="b36f8-p120">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b36f8-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
