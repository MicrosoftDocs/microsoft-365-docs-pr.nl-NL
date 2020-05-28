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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij OVH voor Microsoft.
ms.openlocfilehash: b462979a3ab1bcf769c78d15d9fd3ad03f307ef0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400338"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="0d242-103">DNS-records maken bij OVH voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d242-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="0d242-104">[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="0d242-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0d242-105">Als OVH uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0d242-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0d242-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="0d242-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="0d242-107">DNS-records maken bij OVH voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d242-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="0d242-108">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="0d242-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="0d242-109">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d242-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="0d242-110">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="0d242-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="0d242-111">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d242-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="0d242-112">Nadat u deze records bij OVH hebt toegevoegd, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="0d242-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="0d242-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0d242-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0d242-116">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="0d242-116">Add a TXT record for verification</span></span>
<span data-ttu-id="0d242-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="0d242-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="0d242-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="0d242-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0d242-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0d242-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0d242-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0d242-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="0d242-125">Selecteer **onder Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0d242-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="0d242-127">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="0d242-127">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="0d242-129">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-129">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="0d242-131">**TXT selecteren**</span><span class="sxs-lookup"><span data-stu-id="0d242-131">Select **TXT**</span></span>
    
    ![OVH selecteert TXT-vermelding](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="0d242-133">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0d242-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="0d242-134">Als u een TTL-waarde wilt toewijzen, kiest **u Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="0d242-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="0d242-135">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="0d242-135">**Record type**</span></span>|<span data-ttu-id="0d242-136">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="0d242-136">**Sub-domain**</span></span>|<span data-ttu-id="0d242-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0d242-137">**TTL**</span></span>|<span data-ttu-id="0d242-138">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="0d242-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0d242-139">TXT</span><span class="sxs-lookup"><span data-stu-id="0d242-139">TXT</span></span>  <br/> |<span data-ttu-id="0d242-140">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="0d242-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="0d242-141">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="0d242-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0d242-142">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="0d242-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="0d242-143">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0d242-143">**Note:** This is an example.</span></span> <span data-ttu-id="0d242-144">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="0d242-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="0d242-145">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="0d242-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="0d242-146">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-146">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="0d242-148">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="0d242-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0d242-149">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="0d242-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="0d242-150">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="0d242-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0d242-151">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="0d242-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="0d242-152">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="0d242-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="0d242-153">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="0d242-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="0d242-154">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="0d242-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="0d242-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0d242-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0d242-158">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="0d242-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0d242-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="0d242-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="0d242-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0d242-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="0d242-163">Selecteer **onder Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0d242-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="0d242-165">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="0d242-165">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="0d242-167">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-167">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="0d242-169">Selecteer **MX**.</span><span class="sxs-lookup"><span data-stu-id="0d242-169">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="0d242-171">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0d242-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="0d242-172">Als u een TTL-waarde wilt toewijzen, kiest **u Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="0d242-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0d242-173">OvH gebruikt standaard relatieve notatie voor het doel, dat de domeinnaam toevoegt aan het einde van de doelrecord.</span><span class="sxs-lookup"><span data-stu-id="0d242-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="0d242-174">Als u in plaats daarvan absolute notatie wilt gebruiken, voegt u een punt toe aan de doelrecord zoals in de onderstaande tabel.</span><span class="sxs-lookup"><span data-stu-id="0d242-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="0d242-175">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="0d242-175">**Record type**</span></span>|<span data-ttu-id="0d242-176">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="0d242-176">**Sub-domain**</span></span>|<span data-ttu-id="0d242-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0d242-177">**TTL**</span></span>|<span data-ttu-id="0d242-178">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="0d242-178">**Priority**</span></span>|<span data-ttu-id="0d242-179">**Doel**</span><span class="sxs-lookup"><span data-stu-id="0d242-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0d242-180">MX</span><span class="sxs-lookup"><span data-stu-id="0d242-180">MX</span></span>  <br/> |<span data-ttu-id="0d242-181">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="0d242-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="0d242-182">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="0d242-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0d242-183">10</span><span class="sxs-lookup"><span data-stu-id="0d242-183">10</span></span>  <br/> <span data-ttu-id="0d242-184">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="0d242-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="0d242-185">\<domain-key\>mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0d242-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="0d242-186">**Let op:** Haal uw *\<domain-key\>* van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="0d242-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="0d242-187">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="0d242-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH MX record voor e-mail](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="0d242-189">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0d242-189">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="0d242-191">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-191">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="0d242-193">Als er andere MX-records zijn, verwijdert u deze in op de pagina **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="0d242-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="0d242-194">Selecteer elke record en selecteer vervolgens in de kolom **Acties** het pictogram **Verwijderen** van prullenbak.</span><span class="sxs-lookup"><span data-stu-id="0d242-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="0d242-196">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0d242-197">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d242-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0d242-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="0d242-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="0d242-p113">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0d242-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="0d242-202">Selecteer **onder Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0d242-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="0d242-204">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="0d242-204">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="0d242-206">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-206">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="0d242-208">Selecteer **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="0d242-208">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="0d242-210">Maak de eerste CNAME-record.</span><span class="sxs-lookup"><span data-stu-id="0d242-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="0d242-211">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0d242-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="0d242-212">Als u een TTL-waarde wilt toewijzen, kiest **u Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="0d242-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="0d242-213">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="0d242-213">**Record type**</span></span>|<span data-ttu-id="0d242-214">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="0d242-214">**Sub-domain**</span></span>|<span data-ttu-id="0d242-215">**Doel**</span><span class="sxs-lookup"><span data-stu-id="0d242-215">**Target**</span></span>|<span data-ttu-id="0d242-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0d242-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0d242-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="0d242-217">CNAME</span></span>  <br/> |<span data-ttu-id="0d242-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0d242-218">autodiscover</span></span>  <br/> |<span data-ttu-id="0d242-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0d242-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="0d242-220">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="0d242-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="0d242-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="0d242-221">CNAME</span></span>  <br/> |<span data-ttu-id="0d242-222">sip</span><span class="sxs-lookup"><span data-stu-id="0d242-222">sip</span></span>  <br/> |<span data-ttu-id="0d242-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0d242-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="0d242-224">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="0d242-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="0d242-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="0d242-225">CNAME</span></span>  <br/> |<span data-ttu-id="0d242-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0d242-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0d242-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0d242-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="0d242-228">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="0d242-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="0d242-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="0d242-229">CNAME</span></span>  <br/> |<span data-ttu-id="0d242-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0d242-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0d242-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="0d242-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="0d242-232">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="0d242-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="0d242-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="0d242-233">CNAME</span></span>  <br/> |<span data-ttu-id="0d242-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0d242-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0d242-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0d242-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="0d242-236">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="0d242-236">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME record](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="0d242-238">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0d242-238">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="0d242-240">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="0d242-241">Herhaal de vorige stappen om de vijf andere CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="0d242-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="0d242-242">Typ of kopieer en plak voor elke record de waarden uit de volgende rij van de bovenstaande tabel in de velden voor die record.</span><span class="sxs-lookup"><span data-stu-id="0d242-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0d242-243">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="0d242-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0d242-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="0d242-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d242-245">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="0d242-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0d242-246">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="0d242-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0d242-247">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0d242-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0d242-248">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="0d242-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="0d242-p116">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0d242-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="0d242-252">Selecteer **onder Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0d242-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="0d242-254">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="0d242-254">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="0d242-256">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-256">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="0d242-258">Selecteer **TXT**.</span><span class="sxs-lookup"><span data-stu-id="0d242-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="0d242-259">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0d242-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="0d242-260">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="0d242-260">**Record type**</span></span>|<span data-ttu-id="0d242-261">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="0d242-261">**Sub-domain**</span></span>|<span data-ttu-id="0d242-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0d242-262">**TTL**</span></span>|<span data-ttu-id="0d242-263">**TXT-waarde**</span><span class="sxs-lookup"><span data-stu-id="0d242-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0d242-264">TXT</span><span class="sxs-lookup"><span data-stu-id="0d242-264">TXT</span></span>  <br/> |<span data-ttu-id="0d242-265">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="0d242-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="0d242-266">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="0d242-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0d242-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0d242-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0d242-268">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="0d242-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH Voeg TXT-record voor SPF toe](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="0d242-270">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0d242-270">Select **Next**.</span></span>
    
    ![OVH Voeg TXT-record voor SPF toe en selecteer Volgende](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="0d242-272">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-272">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0d242-274">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d242-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0d242-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="0d242-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="0d242-p117">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0d242-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="0d242-279">Selecteer **onder Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="0d242-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="0d242-281">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="0d242-281">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="0d242-283">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-283">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="0d242-285">Selecteer **SRV**.</span><span class="sxs-lookup"><span data-stu-id="0d242-285">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="0d242-287">Maak de eerste SRV-record.</span><span class="sxs-lookup"><span data-stu-id="0d242-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="0d242-288">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0d242-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="0d242-289">Als u een TTL-waarde wilt toewijzen, kiest **u Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="0d242-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="0d242-290">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="0d242-290">**Record type**</span></span>|<span data-ttu-id="0d242-291">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="0d242-291">**Sub-domain**</span></span>|<span data-ttu-id="0d242-292">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="0d242-292">**Priority**</span></span>|<span data-ttu-id="0d242-293">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="0d242-293">**Weight**</span></span>|<span data-ttu-id="0d242-294">**Poort**</span><span class="sxs-lookup"><span data-stu-id="0d242-294">**Port**</span></span>|<span data-ttu-id="0d242-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0d242-295">**TTL**</span></span>|<span data-ttu-id="0d242-296">**Doel**</span><span class="sxs-lookup"><span data-stu-id="0d242-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0d242-297">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="0d242-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="0d242-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="0d242-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="0d242-299">100</span><span class="sxs-lookup"><span data-stu-id="0d242-299">100</span></span>  <br/> |<span data-ttu-id="0d242-300">1</span><span class="sxs-lookup"><span data-stu-id="0d242-300">1</span></span>  <br/> |<span data-ttu-id="0d242-301">443</span><span class="sxs-lookup"><span data-stu-id="0d242-301">443</span></span>  <br/> |<span data-ttu-id="0d242-302">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="0d242-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0d242-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0d242-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="0d242-304">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="0d242-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="0d242-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="0d242-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="0d242-306">100</span><span class="sxs-lookup"><span data-stu-id="0d242-306">100</span></span>  <br/> |<span data-ttu-id="0d242-307">1</span><span class="sxs-lookup"><span data-stu-id="0d242-307">1</span></span>  <br/> |<span data-ttu-id="0d242-308">5061</span><span class="sxs-lookup"><span data-stu-id="0d242-308">5061</span></span>  <br/> |<span data-ttu-id="0d242-309">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="0d242-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="0d242-310">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0d242-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV record](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="0d242-312">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0d242-312">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="0d242-314">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="0d242-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="0d242-p119">Herhaal de vorige stappen om de andere SRV-record te maken. Typ of kopieer en plak de waarden uit de tweede rij van de bovenstaande tabel in de vakken voor de tweede record.</span><span class="sxs-lookup"><span data-stu-id="0d242-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="0d242-p120">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0d242-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
