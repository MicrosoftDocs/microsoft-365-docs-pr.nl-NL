---
title: DNS-records maken bij OVH voor Office 365
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij OVH voor Office 365.
ms.openlocfilehash: 4857addd7dfd096c1ddd6e59f1f17ace76b75a9e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42805372"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="e101f-103">DNS-records maken bij OVH voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e101f-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="e101f-104">[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="e101f-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e101f-105">Als OVH uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="e101f-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e101f-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="e101f-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="e101f-107">DNS-records maken bij OVH voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e101f-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="e101f-108">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="e101f-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="e101f-109">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="e101f-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="e101f-110">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="e101f-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="e101f-111">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="e101f-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="e101f-112">Nadat u deze records bij OVH hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="e101f-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="e101f-113">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="e101f-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e101f-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e101f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e101f-117">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="e101f-117">Add a TXT record for verification</span></span>
<span data-ttu-id="e101f-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="e101f-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="e101f-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="e101f-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e101f-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e101f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e101f-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e101f-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e101f-126">Selecteer onder **Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="e101f-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e101f-128">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="e101f-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e101f-130">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-130">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e101f-132">Selecteer **TXT**</span><span class="sxs-lookup"><span data-stu-id="e101f-132">Select **TXT**</span></span>
    
    ![OVH selecteert TXT-vermelding](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="e101f-134">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="e101f-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="e101f-135">Als u een TTL-waarde wilt toewijzen, kiest u **Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="e101f-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="e101f-136">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="e101f-136">**Record type**</span></span>|<span data-ttu-id="e101f-137">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="e101f-137">**Sub-domain**</span></span>|<span data-ttu-id="e101f-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e101f-138">**TTL**</span></span>|<span data-ttu-id="e101f-139">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="e101f-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e101f-140">TXT</span><span class="sxs-lookup"><span data-stu-id="e101f-140">TXT</span></span>  <br/> |<span data-ttu-id="e101f-141">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="e101f-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="e101f-142">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="e101f-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e101f-143">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="e101f-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="e101f-p106">**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="e101f-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
7. <span data-ttu-id="e101f-147">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-147">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="e101f-149">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e101f-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e101f-150">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="e101f-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="e101f-151">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="e101f-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e101f-152">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="e101f-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e101f-153">Selecteer op de pagina **Domeinen** het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="e101f-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e101f-154">Selecteer op de pagina **Setup** de optie **Startsetup**.</span><span class="sxs-lookup"><span data-stu-id="e101f-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e101f-155">Selecteer op de pagina **Domein verifiëren** de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="e101f-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e101f-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e101f-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="e101f-159">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="e101f-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="e101f-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="e101f-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="e101f-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e101f-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e101f-164">Selecteer onder **Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="e101f-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e101f-166">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="e101f-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e101f-168">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-168">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e101f-170">Selecteer **MX**.</span><span class="sxs-lookup"><span data-stu-id="e101f-170">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="e101f-172">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="e101f-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="e101f-173">Als u een TTL-waarde wilt toewijzen, kiest u **Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="e101f-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e101f-174">OvH gebruikt standaard relatieve notatie voor het doel, waardoor de domeinnaam wordt toegevoegd aan het einde van het doelrecord.</span><span class="sxs-lookup"><span data-stu-id="e101f-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="e101f-175">Als u in plaats daarvan absolute notatie wilt gebruiken, voegt u een stip toe aan de doelrecord zoals in de onderstaande tabel wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e101f-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="e101f-176">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="e101f-176">**Record type**</span></span>|<span data-ttu-id="e101f-177">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="e101f-177">**Sub-domain**</span></span>|<span data-ttu-id="e101f-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e101f-178">**TTL**</span></span>|<span data-ttu-id="e101f-179">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="e101f-179">**Priority**</span></span>|<span data-ttu-id="e101f-180">**Target**</span><span class="sxs-lookup"><span data-stu-id="e101f-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e101f-181">MX</span><span class="sxs-lookup"><span data-stu-id="e101f-181">MX</span></span>  <br/> |<span data-ttu-id="e101f-182">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="e101f-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="e101f-183">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="e101f-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e101f-184">10</span><span class="sxs-lookup"><span data-stu-id="e101f-184">10</span></span>  <br/> <span data-ttu-id="e101f-185">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="e101f-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="e101f-186">\<domain-key\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e101f-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e101f-187">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="e101f-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="e101f-188">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="e101f-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH MX record voor mail](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="e101f-190">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e101f-190">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="e101f-192">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-192">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="e101f-194">Als er andere MX-records zijn, verwijdert u deze in op de pagina **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="e101f-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="e101f-195">Selecteer elke record en selecteer vervolgens in de kolom **Acties** het pictogram Prullenbak **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="e101f-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="e101f-197">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="e101f-198">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="e101f-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="e101f-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="e101f-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="e101f-p113">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e101f-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e101f-203">Selecteer onder **Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="e101f-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e101f-205">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="e101f-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e101f-207">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-207">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e101f-209">Selecteer **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="e101f-209">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="e101f-211">Maak de eerste CNAME-record.</span><span class="sxs-lookup"><span data-stu-id="e101f-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="e101f-212">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="e101f-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="e101f-213">Als u een TTL-waarde wilt toewijzen, kiest u **Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="e101f-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="e101f-214">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="e101f-214">**Record type**</span></span>|<span data-ttu-id="e101f-215">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="e101f-215">**Sub-domain**</span></span>|<span data-ttu-id="e101f-216">**Doel**</span><span class="sxs-lookup"><span data-stu-id="e101f-216">**Target**</span></span>|<span data-ttu-id="e101f-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e101f-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e101f-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="e101f-218">CNAME</span></span>  <br/> |<span data-ttu-id="e101f-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e101f-219">autodiscover</span></span>  <br/> |<span data-ttu-id="e101f-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e101f-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="e101f-221">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="e101f-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e101f-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="e101f-222">CNAME</span></span>  <br/> |<span data-ttu-id="e101f-223">sip</span><span class="sxs-lookup"><span data-stu-id="e101f-223">sip</span></span>  <br/> |<span data-ttu-id="e101f-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e101f-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="e101f-225">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="e101f-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e101f-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="e101f-226">CNAME</span></span>  <br/> |<span data-ttu-id="e101f-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e101f-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e101f-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e101f-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="e101f-229">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="e101f-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e101f-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="e101f-230">CNAME</span></span>  <br/> |<span data-ttu-id="e101f-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e101f-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e101f-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e101f-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="e101f-233">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="e101f-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="e101f-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="e101f-234">CNAME</span></span>  <br/> |<span data-ttu-id="e101f-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e101f-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e101f-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e101f-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="e101f-237">3600 seconden</span><span class="sxs-lookup"><span data-stu-id="e101f-237">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME record](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="e101f-239">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e101f-239">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="e101f-241">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="e101f-242">Herhaal de vorige stappen om de vijf andere CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="e101f-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="e101f-243">Typ of kopieer en plak voor elke record de waarden uit de volgende rij van de bovenstaande tabel in de velden voor die record.</span><span class="sxs-lookup"><span data-stu-id="e101f-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e101f-244">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="e101f-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e101f-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="e101f-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e101f-246">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="e101f-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e101f-247">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="e101f-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e101f-248">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="e101f-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="e101f-249">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="e101f-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="e101f-p116">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e101f-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e101f-253">Selecteer onder **Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="e101f-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e101f-255">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="e101f-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e101f-257">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-257">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e101f-259">Selecteer **TXT**.</span><span class="sxs-lookup"><span data-stu-id="e101f-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="e101f-260">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="e101f-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="e101f-261">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="e101f-261">**Record type**</span></span>|<span data-ttu-id="e101f-262">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="e101f-262">**Sub-domain**</span></span>|<span data-ttu-id="e101f-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e101f-263">**TTL**</span></span>|<span data-ttu-id="e101f-264">**TXT-waarde**</span><span class="sxs-lookup"><span data-stu-id="e101f-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e101f-265">TXT</span><span class="sxs-lookup"><span data-stu-id="e101f-265">TXT</span></span>  <br/> |<span data-ttu-id="e101f-266">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="e101f-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="e101f-267">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="e101f-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e101f-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e101f-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e101f-269">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="e101f-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH Add TXT record voor SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="e101f-271">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e101f-271">Select **Next**.</span></span>
    
    ![OVH Add TXT-record voor SPF en selecteer Volgende](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="e101f-273">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-273">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="e101f-275">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="e101f-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="e101f-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="e101f-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="e101f-p117">Als u wilt beginnen, gaat u naar uw domeinenpagina in OVH via [deze koppeling](https://www.ovh.com/manager/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e101f-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="e101f-280">Selecteer onder **Domeinen**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="e101f-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="e101f-282">Selecteer **DNS-zone**.</span><span class="sxs-lookup"><span data-stu-id="e101f-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="e101f-284">Selecteer **Een item toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-284">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="e101f-286">Selecteer **SRV**.</span><span class="sxs-lookup"><span data-stu-id="e101f-286">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="e101f-288">Maak de eerste SRV-record.</span><span class="sxs-lookup"><span data-stu-id="e101f-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="e101f-289">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="e101f-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="e101f-290">Als u een TTL-waarde wilt toewijzen, kiest u **Gepersonaliseerd** in de vervolgkeuzelijst en typt u de waarde in het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="e101f-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="e101f-291">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="e101f-291">**Record type**</span></span>|<span data-ttu-id="e101f-292">**Subdomein**</span><span class="sxs-lookup"><span data-stu-id="e101f-292">**Sub-domain**</span></span>|<span data-ttu-id="e101f-293">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="e101f-293">**Priority**</span></span>|<span data-ttu-id="e101f-294">**Weight**</span><span class="sxs-lookup"><span data-stu-id="e101f-294">**Weight**</span></span>|<span data-ttu-id="e101f-295">**Port**</span><span class="sxs-lookup"><span data-stu-id="e101f-295">**Port**</span></span>|<span data-ttu-id="e101f-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e101f-296">**TTL**</span></span>|<span data-ttu-id="e101f-297">**Doel**</span><span class="sxs-lookup"><span data-stu-id="e101f-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e101f-298">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="e101f-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="e101f-299">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="e101f-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="e101f-300">100</span><span class="sxs-lookup"><span data-stu-id="e101f-300">100</span></span>  <br/> |<span data-ttu-id="e101f-301">1</span><span class="sxs-lookup"><span data-stu-id="e101f-301">1</span></span>  <br/> |<span data-ttu-id="e101f-302">443</span><span class="sxs-lookup"><span data-stu-id="e101f-302">443</span></span>  <br/> |<span data-ttu-id="e101f-303">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="e101f-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e101f-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e101f-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="e101f-305">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="e101f-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="e101f-306">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e101f-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="e101f-307">100</span><span class="sxs-lookup"><span data-stu-id="e101f-307">100</span></span>  <br/> |<span data-ttu-id="e101f-308">1</span><span class="sxs-lookup"><span data-stu-id="e101f-308">1</span></span>  <br/> |<span data-ttu-id="e101f-309">5061</span><span class="sxs-lookup"><span data-stu-id="e101f-309">5061</span></span>  <br/> |<span data-ttu-id="e101f-310">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="e101f-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e101f-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e101f-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV record](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="e101f-313">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e101f-313">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="e101f-315">Selecteer **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="e101f-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="e101f-p119">Herhaal de vorige stappen om de andere SRV-record te maken. Typ of kopieer en plak de waarden uit de tweede rij van de bovenstaande tabel in de vakken voor de tweede record.</span><span class="sxs-lookup"><span data-stu-id="e101f-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="e101f-p120">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e101f-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
