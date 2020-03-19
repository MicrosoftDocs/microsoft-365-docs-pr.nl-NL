---
title: DNS-records maken bij GoDaddy voor Office 365
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij GoDaddy voor Office 365.
ms.custom: okr_smb
ms.openlocfilehash: e037e989a51a95b16077d1edfcdff4b341ee3b80
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42806899"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="890d7-103">DNS-records maken bij GoDaddy voor Office 365</span><span class="sxs-lookup"><span data-stu-id="890d7-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="890d7-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="890d7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="890d7-105">Als GoDaddy uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="890d7-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="890d7-106">Nadat u deze records bij GoDaddy hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="890d7-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="890d7-107">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="890d7-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="890d7-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="890d7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="890d7-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="890d7-111">Add a TXT record for verification</span></span>
<span data-ttu-id="890d7-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="890d7-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="890d7-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="890d7-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="890d7-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="890d7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="890d7-117">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="890d7-117">Follow the steps below.</span></span>

1. <span data-ttu-id="890d7-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="890d7-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="890d7-121">Selecteer onder **Domeinen**DE optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="890d7-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="890d7-123">Selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="890d7-123">Select **Add**.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="890d7-125">Kies **TXT (Text)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="890d7-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="890d7-126">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="890d7-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="890d7-127">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="890d7-127">**Record type**</span></span> |<span data-ttu-id="890d7-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="890d7-128">**Host**</span></span>|<span data-ttu-id="890d7-129">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="890d7-129">**TXT Value**</span></span>|<span data-ttu-id="890d7-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="890d7-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="890d7-131">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="890d7-131">TXT (Text)</span></span>|@|<span data-ttu-id="890d7-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="890d7-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="890d7-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="890d7-133">**Note**: This is an example.</span></span> <span data-ttu-id="890d7-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="890d7-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="890d7-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="890d7-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="890d7-136">1 uur</span><span class="sxs-lookup"><span data-stu-id="890d7-136">1 hour</span></span>  <br><span data-ttu-id="890d7-137">(Selecteer een waarde uit de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="890d7-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="890d7-139">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="890d7-139">Select **Save**.</span></span>

6. <span data-ttu-id="890d7-140">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="890d7-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="890d7-141">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="890d7-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="890d7-142">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="890d7-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="890d7-143">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="890d7-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="890d7-144">Selecteer op de pagina **Domeinen** het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="890d7-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="890d7-145">Selecteer op de pagina **Setup** de optie **Startsetup**.</span><span class="sxs-lookup"><span data-stu-id="890d7-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="890d7-146">Selecteer op de pagina **Domein verifiëren** de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="890d7-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="890d7-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="890d7-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="890d7-150">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="890d7-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="890d7-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="890d7-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="890d7-152">Voer de onderstaande stappen uit.</span><span class="sxs-lookup"><span data-stu-id="890d7-152">Follow the steps below.</span></span>

1. <span data-ttu-id="890d7-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="890d7-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="890d7-156">Selecteer onder **Domeinen**DE optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="890d7-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="890d7-158">Selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="890d7-158">Select **Add**.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="890d7-160">Kies **MX (Mail Exchanger)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="890d7-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-afbeelding 2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="890d7-162">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="890d7-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="890d7-163">(Kies de **TTL-waarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="890d7-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="890d7-164">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="890d7-164">**Record type**</span></span>|<span data-ttu-id="890d7-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="890d7-165">**Host**</span></span>|<span data-ttu-id="890d7-166">**Points to**</span><span class="sxs-lookup"><span data-stu-id="890d7-166">**Points to**</span></span>|<span data-ttu-id="890d7-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="890d7-167">**Priority**</span></span>|<span data-ttu-id="890d7-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="890d7-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="890d7-169">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="890d7-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="890d7-170">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="890d7-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="890d7-171">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="890d7-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="890d7-172">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="890d7-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="890d7-173">10</span><span class="sxs-lookup"><span data-stu-id="890d7-173">10</span></span>  <br/> <span data-ttu-id="890d7-174">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="890d7-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="890d7-175">1 uur</span><span class="sxs-lookup"><span data-stu-id="890d7-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="890d7-176">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="890d7-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="890d7-177">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="890d7-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="890d7-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="890d7-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="890d7-179">Voer de onderstaande stappen uit.</span><span class="sxs-lookup"><span data-stu-id="890d7-179">Follow the steps below.</span></span>

1. <span data-ttu-id="890d7-p110">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="890d7-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="890d7-183">Selecteer onder **Domeinen**DE optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="890d7-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="890d7-185">Selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="890d7-185">Select **Add**.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="890d7-187">Kies **CNAME (Alias)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="890d7-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="890d7-189">Maak de eerste CNAME-record.</span><span class="sxs-lookup"><span data-stu-id="890d7-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="890d7-190">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="890d7-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="890d7-191">(Kies de **TTL-waarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="890d7-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="890d7-192">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="890d7-192">**Record type**</span></span>|<span data-ttu-id="890d7-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="890d7-193">**Host**</span></span>|<span data-ttu-id="890d7-194">**Points to**</span><span class="sxs-lookup"><span data-stu-id="890d7-194">**Points to**</span></span>|<span data-ttu-id="890d7-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="890d7-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="890d7-196">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="890d7-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="890d7-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="890d7-197">autodiscover</span></span>  <br/> |<span data-ttu-id="890d7-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="890d7-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="890d7-199">1 uur</span><span class="sxs-lookup"><span data-stu-id="890d7-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="890d7-200">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="890d7-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="890d7-201">sip</span><span class="sxs-lookup"><span data-stu-id="890d7-201">sip</span></span>  <br/> |<span data-ttu-id="890d7-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="890d7-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="890d7-203">1 uur</span><span class="sxs-lookup"><span data-stu-id="890d7-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="890d7-204">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="890d7-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="890d7-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="890d7-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="890d7-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="890d7-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="890d7-207">1 uur</span><span class="sxs-lookup"><span data-stu-id="890d7-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="890d7-208">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="890d7-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="890d7-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="890d7-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="890d7-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="890d7-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="890d7-211">1 uur</span><span class="sxs-lookup"><span data-stu-id="890d7-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="890d7-212">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="890d7-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="890d7-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="890d7-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="890d7-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="890d7-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="890d7-215">1 uur</span><span class="sxs-lookup"><span data-stu-id="890d7-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="890d7-216">Herhaal deze stappen om de volgende CNAME-record toe te voegen totdat u alle zes de CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="890d7-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="890d7-217">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="890d7-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="890d7-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="890d7-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="890d7-219">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="890d7-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="890d7-220">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="890d7-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="890d7-221">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="890d7-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="890d7-222">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="890d7-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="890d7-223">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="890d7-223">Follow the steps below.</span></span>

1. <span data-ttu-id="890d7-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="890d7-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="890d7-227">Selecteer onder **Domeinen**DE optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="890d7-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="890d7-229">Selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="890d7-229">Select **Add**.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="890d7-231">Kies **TXT (Text)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="890d7-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-afbeelding 4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="890d7-233">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="890d7-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="890d7-234">(Kies de **TTL-waarde** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="890d7-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="890d7-235">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="890d7-235">**Record type**</span></span>|<span data-ttu-id="890d7-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="890d7-236">**Host**</span></span>|<span data-ttu-id="890d7-237">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="890d7-237">**TXT Value**</span></span>|<span data-ttu-id="890d7-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="890d7-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="890d7-239">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="890d7-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="890d7-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="890d7-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="890d7-241">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="890d7-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="890d7-242">1 uur</span><span class="sxs-lookup"><span data-stu-id="890d7-242">1 hour</span></span>  <br/> |

    ![Afbeelding van het bureaublad van Afbeelding van het bureaublad van GoDaddy-BP](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="890d7-244">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="890d7-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="890d7-245">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="890d7-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="890d7-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="890d7-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="890d7-247">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="890d7-247">Follow the steps below.</span></span>

1. <span data-ttu-id="890d7-p113">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="890d7-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="890d7-251">Selecteer onder **Domeinen**DE optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="890d7-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="890d7-253">Selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="890d7-253">Select **Add**.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-configureren-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="890d7-255">Kies **SRV (Service)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="890d7-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![Afbeelding van het bureaublad van GoDaddy-BP-afbeelding 5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="890d7-257">Maak de eerste SRV-record.</span><span class="sxs-lookup"><span data-stu-id="890d7-257">Create the first SRV record.</span></span>

    <span data-ttu-id="890d7-258">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="890d7-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="890d7-259">(Kies het **recordtype** en **ttl-waarden** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="890d7-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="890d7-260">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="890d7-260">**Record type**</span></span>|<span data-ttu-id="890d7-261">**Naam**</span><span class="sxs-lookup"><span data-stu-id="890d7-261">**Name**</span></span>|<span data-ttu-id="890d7-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="890d7-262">**Target**</span></span>|<span data-ttu-id="890d7-263">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="890d7-263">**Protocol**</span></span>|<span data-ttu-id="890d7-264">**Service**</span><span class="sxs-lookup"><span data-stu-id="890d7-264">**Service**</span></span>|<span data-ttu-id="890d7-265">**Priority**</span><span class="sxs-lookup"><span data-stu-id="890d7-265">**Priority**</span></span>|<span data-ttu-id="890d7-266">**Weight**</span><span class="sxs-lookup"><span data-stu-id="890d7-266">**Weight**</span></span>|<span data-ttu-id="890d7-267">**Port**</span><span class="sxs-lookup"><span data-stu-id="890d7-267">**Port**</span></span>|<span data-ttu-id="890d7-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="890d7-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="890d7-269">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="890d7-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="890d7-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="890d7-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="890d7-271">_tls</span><span class="sxs-lookup"><span data-stu-id="890d7-271">_tls</span></span>  <br/> |<span data-ttu-id="890d7-272">_sip</span><span class="sxs-lookup"><span data-stu-id="890d7-272">_sip</span></span>  <br/> |<span data-ttu-id="890d7-273">100</span><span class="sxs-lookup"><span data-stu-id="890d7-273">100</span></span>  <br/> |<span data-ttu-id="890d7-274">1</span><span class="sxs-lookup"><span data-stu-id="890d7-274">1</span></span>  <br/> |<span data-ttu-id="890d7-275">443</span><span class="sxs-lookup"><span data-stu-id="890d7-275">443</span></span>  <br/> |<span data-ttu-id="890d7-276">1 uur</span><span class="sxs-lookup"><span data-stu-id="890d7-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="890d7-277">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="890d7-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="890d7-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="890d7-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="890d7-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="890d7-279">_tcp</span></span>  <br/> |<span data-ttu-id="890d7-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="890d7-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="890d7-281">100</span><span class="sxs-lookup"><span data-stu-id="890d7-281">100</span></span>  <br/> |<span data-ttu-id="890d7-282">1</span><span class="sxs-lookup"><span data-stu-id="890d7-282">1</span></span>  <br/> |<span data-ttu-id="890d7-283">5061</span><span class="sxs-lookup"><span data-stu-id="890d7-283">5061</span></span>  <br/> |<span data-ttu-id="890d7-284">1 uur</span><span class="sxs-lookup"><span data-stu-id="890d7-284">1 hour</span></span>  <br/> |

    ![Afbeelding van het bureaublad van GoDaddy-BP-afbeelding 5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="890d7-286">Herhaal **stap 5** om de andere SRV-record te maken.</span><span class="sxs-lookup"><span data-stu-id="890d7-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="890d7-287">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="890d7-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="890d7-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="890d7-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
