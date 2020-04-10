---
title: DNS-records maken bij GoDaddy voor Office 365
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij GoDaddy voor Office 365.
ms.custom: okr_smb
ms.openlocfilehash: eceab4659dfc01d6a731c4ed07f27bb29214e5fb
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211737"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="7ee9d-103">DNS-records maken bij GoDaddy voor Office 365</span><span class="sxs-lookup"><span data-stu-id="7ee9d-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="7ee9d-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="7ee9d-105">Als GoDaddy uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="7ee9d-106">Nadat u deze records bij GoDaddy hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="7ee9d-107">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="7ee9d-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7ee9d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7ee9d-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="7ee9d-111">Add a TXT record for verification</span></span>
<span data-ttu-id="7ee9d-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7ee9d-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7ee9d-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="7ee9d-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="7ee9d-117">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="7ee9d-117">Follow the steps below.</span></span>

1. <span data-ttu-id="7ee9d-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="7ee9d-121">Selecteer **onder Domeinen**de optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="7ee9d-123">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-123">Select **Add**.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="7ee9d-125">Kies **TXT (Text)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="7ee9d-126">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="7ee9d-127">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-127">**Record type**</span></span> |<span data-ttu-id="7ee9d-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-128">**Host**</span></span>|<span data-ttu-id="7ee9d-129">**TXT-waarde**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-129">**TXT Value**</span></span>|<span data-ttu-id="7ee9d-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7ee9d-131">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-131">TXT (Text)</span></span>|@|<span data-ttu-id="7ee9d-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7ee9d-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="7ee9d-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-133">**Note**: This is an example.</span></span> <span data-ttu-id="7ee9d-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="7ee9d-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="7ee9d-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="7ee9d-136">1 uur</span><span class="sxs-lookup"><span data-stu-id="7ee9d-136">1 hour</span></span>  <br><span data-ttu-id="7ee9d-137">(Selecteer een waarde in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-137">(Select a value from the drop-down list.)</span></span>|

      ![Afbeelding van het te maken](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="7ee9d-139">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-139">Select **Save**.</span></span>

6. <span data-ttu-id="7ee9d-140">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="7ee9d-141">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="7ee9d-142">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7ee9d-143">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7ee9d-144">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7ee9d-145">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="7ee9d-146">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="7ee9d-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7ee9d-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="7ee9d-150">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="7ee9d-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="7ee9d-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7ee9d-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="7ee9d-152">Voer de onderstaande stappen uit.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-152">Follow the steps below.</span></span>

1. <span data-ttu-id="7ee9d-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="7ee9d-156">Selecteer **onder Domeinen**de optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="7ee9d-158">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-158">Select **Add**.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="7ee9d-160">Kies **MX (Mail Exchanger)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![Afbeelding van het te maken](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="7ee9d-162">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="7ee9d-163">(Kies de **TTL-waarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="7ee9d-164">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-164">**Record type**</span></span>|<span data-ttu-id="7ee9d-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-165">**Host**</span></span>|<span data-ttu-id="7ee9d-166">**Verwijst naar**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-166">**Points to**</span></span>|<span data-ttu-id="7ee9d-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-167">**Priority**</span></span>|<span data-ttu-id="7ee9d-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7ee9d-169">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="7ee9d-170">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7ee9d-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="7ee9d-171">**Let op:** Haal uw \* \<domeinsleutel\> \* op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="7ee9d-172">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="7ee9d-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7ee9d-173">10</span><span class="sxs-lookup"><span data-stu-id="7ee9d-173">10</span></span>  <br/> <span data-ttu-id="7ee9d-174">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="7ee9d-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="7ee9d-175">1 uur</span><span class="sxs-lookup"><span data-stu-id="7ee9d-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="7ee9d-176">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="7ee9d-177">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="7ee9d-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="7ee9d-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7ee9d-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="7ee9d-179">Voer de onderstaande stappen uit.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-179">Follow the steps below.</span></span>

1. <span data-ttu-id="7ee9d-p110">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="7ee9d-183">Selecteer **onder Domeinen**de optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="7ee9d-185">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-185">Select **Add**.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="7ee9d-187">Kies **CNAME (Alias)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![Afbeelding van het te maken](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="7ee9d-189">Maak de eerste CNAME-record.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="7ee9d-190">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="7ee9d-191">(Kies de **TTL-waarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="7ee9d-192">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-192">**Record type**</span></span>|<span data-ttu-id="7ee9d-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-193">**Host**</span></span>|<span data-ttu-id="7ee9d-194">**Verwijst naar**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-194">**Points to**</span></span>|<span data-ttu-id="7ee9d-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7ee9d-196">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7ee9d-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7ee9d-197">autodiscover</span></span>  <br/> |<span data-ttu-id="7ee9d-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7ee9d-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="7ee9d-199">1 uur</span><span class="sxs-lookup"><span data-stu-id="7ee9d-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="7ee9d-200">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7ee9d-201">sip</span><span class="sxs-lookup"><span data-stu-id="7ee9d-201">sip</span></span>  <br/> |<span data-ttu-id="7ee9d-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7ee9d-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="7ee9d-203">1 uur</span><span class="sxs-lookup"><span data-stu-id="7ee9d-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="7ee9d-204">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7ee9d-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7ee9d-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7ee9d-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7ee9d-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="7ee9d-207">1 uur</span><span class="sxs-lookup"><span data-stu-id="7ee9d-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="7ee9d-208">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7ee9d-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7ee9d-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7ee9d-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="7ee9d-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="7ee9d-211">1 uur</span><span class="sxs-lookup"><span data-stu-id="7ee9d-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="7ee9d-212">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="7ee9d-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7ee9d-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7ee9d-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7ee9d-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="7ee9d-215">1 uur</span><span class="sxs-lookup"><span data-stu-id="7ee9d-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="7ee9d-216">Herhaal deze stappen om de volgende CNAME-record toe te voegen totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7ee9d-217">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="7ee9d-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7ee9d-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7ee9d-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ee9d-219">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7ee9d-220">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7ee9d-221">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="7ee9d-222">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="7ee9d-223">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="7ee9d-223">Follow the steps below.</span></span>

1. <span data-ttu-id="7ee9d-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="7ee9d-227">Selecteer **onder Domeinen**de optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="7ee9d-229">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-229">Select **Add**.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="7ee9d-231">Kies **TXT (Text)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![Afbeelding van het te maken](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="7ee9d-233">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="7ee9d-234">(Kies de **TTL-waarde** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="7ee9d-235">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-235">**Record type**</span></span>|<span data-ttu-id="7ee9d-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-236">**Host**</span></span>|<span data-ttu-id="7ee9d-237">**TXT-waarde**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-237">**TXT Value**</span></span>|<span data-ttu-id="7ee9d-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7ee9d-239">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="7ee9d-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7ee9d-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7ee9d-241">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="7ee9d-242">1 uur</span><span class="sxs-lookup"><span data-stu-id="7ee9d-242">1 hour</span></span>  <br/> |

    ![Afbeelding van het te maken](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="7ee9d-244">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="7ee9d-245">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="7ee9d-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="7ee9d-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7ee9d-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="7ee9d-247">Voer de onderstaande stappen uit.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-247">Follow the steps below.</span></span>

1. <span data-ttu-id="7ee9d-p113">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="7ee9d-251">Selecteer **onder Domeinen**de optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="7ee9d-253">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-253">Select **Add**.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="7ee9d-255">Kies **SRV (Service)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![Afbeelding van het te maken](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="7ee9d-257">Maak de eerste SRV-record.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-257">Create the first SRV record.</span></span>

    <span data-ttu-id="7ee9d-258">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="7ee9d-259">(Kies de waarden **Record en** **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="7ee9d-260">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-260">**Record type**</span></span>|<span data-ttu-id="7ee9d-261">**Naam**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-261">**Name**</span></span>|<span data-ttu-id="7ee9d-262">**Doel**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-262">**Target**</span></span>|<span data-ttu-id="7ee9d-263">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-263">**Protocol**</span></span>|<span data-ttu-id="7ee9d-264">**Service**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-264">**Service**</span></span>|<span data-ttu-id="7ee9d-265">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-265">**Priority**</span></span>|<span data-ttu-id="7ee9d-266">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-266">**Weight**</span></span>|<span data-ttu-id="7ee9d-267">**Poort**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-267">**Port**</span></span>|<span data-ttu-id="7ee9d-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7ee9d-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7ee9d-269">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="7ee9d-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7ee9d-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="7ee9d-271">_tls</span><span class="sxs-lookup"><span data-stu-id="7ee9d-271">_tls</span></span>  <br/> |<span data-ttu-id="7ee9d-272">_sip</span><span class="sxs-lookup"><span data-stu-id="7ee9d-272">_sip</span></span>  <br/> |<span data-ttu-id="7ee9d-273">100</span><span class="sxs-lookup"><span data-stu-id="7ee9d-273">100</span></span>  <br/> |<span data-ttu-id="7ee9d-274">1</span><span class="sxs-lookup"><span data-stu-id="7ee9d-274">1</span></span>  <br/> |<span data-ttu-id="7ee9d-275">443</span><span class="sxs-lookup"><span data-stu-id="7ee9d-275">443</span></span>  <br/> |<span data-ttu-id="7ee9d-276">1 uur</span><span class="sxs-lookup"><span data-stu-id="7ee9d-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="7ee9d-277">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="7ee9d-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="7ee9d-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7ee9d-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="7ee9d-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="7ee9d-279">_tcp</span></span>  <br/> |<span data-ttu-id="7ee9d-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7ee9d-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="7ee9d-281">100</span><span class="sxs-lookup"><span data-stu-id="7ee9d-281">100</span></span>  <br/> |<span data-ttu-id="7ee9d-282">1</span><span class="sxs-lookup"><span data-stu-id="7ee9d-282">1</span></span>  <br/> |<span data-ttu-id="7ee9d-283">5061</span><span class="sxs-lookup"><span data-stu-id="7ee9d-283">5061</span></span>  <br/> |<span data-ttu-id="7ee9d-284">1 uur</span><span class="sxs-lookup"><span data-stu-id="7ee9d-284">1 hour</span></span>  <br/> |

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="7ee9d-286">Herhaal **stap 5** om de andere SRV-record te maken.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="7ee9d-287">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7ee9d-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="7ee9d-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7ee9d-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
