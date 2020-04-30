---
title: DNS-records maken bij GoDaddy voor Microsoft
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
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij GoDaddy voor Microsoft.
ms.custom: okr_smb
ms.openlocfilehash: 0f71eb512b83451db8fee41b535ecc0c60d8d6bc
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939213"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="35597-103">DNS-records maken bij GoDaddy voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="35597-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="35597-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="35597-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="35597-105">Als GoDaddy uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="35597-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="35597-106">Nadat u deze records bij GoDaddy hebt toegevoegd, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="35597-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="35597-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="35597-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="35597-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="35597-110">Add a TXT record for verification</span></span>
<span data-ttu-id="35597-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="35597-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="35597-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="35597-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="35597-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="35597-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="35597-116">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="35597-116">Follow the steps below.</span></span>

1. <span data-ttu-id="35597-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="35597-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="35597-120">Selecteer **onder Domeinen**de optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="35597-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="35597-122">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="35597-122">Select **Add**.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="35597-124">Kies **TXT (Text)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="35597-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="35597-125">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="35597-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="35597-126">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="35597-126">**Record type**</span></span> |<span data-ttu-id="35597-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="35597-127">**Host**</span></span>|<span data-ttu-id="35597-128">**TXT-waarde**</span><span class="sxs-lookup"><span data-stu-id="35597-128">**TXT Value**</span></span>|<span data-ttu-id="35597-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="35597-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="35597-130">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="35597-130">TXT (Text)</span></span>|@|<span data-ttu-id="35597-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="35597-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="35597-132">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="35597-132">**Note**: This is an example.</span></span> <span data-ttu-id="35597-133">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="35597-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="35597-134">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="35597-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="35597-135">1 uur</span><span class="sxs-lookup"><span data-stu-id="35597-135">1 hour</span></span>  <br><span data-ttu-id="35597-136">(Selecteer een waarde in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="35597-136">(Select a value from the drop-down list.)</span></span>|

      ![Afbeelding van het te maken](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="35597-138">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="35597-138">Select **Save**.</span></span>

6. <span data-ttu-id="35597-139">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="35597-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="35597-140">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="35597-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="35597-141">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="35597-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="35597-142">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="35597-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="35597-143">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="35597-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="35597-144">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="35597-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="35597-145">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="35597-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="35597-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="35597-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="35597-149">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="35597-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="35597-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="35597-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="35597-151">Voer de onderstaande stappen uit.</span><span class="sxs-lookup"><span data-stu-id="35597-151">Follow the steps below.</span></span>

1. <span data-ttu-id="35597-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="35597-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="35597-155">Selecteer **onder Domeinen**de optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="35597-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="35597-157">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="35597-157">Select **Add**.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="35597-159">Kies **MX (Mail Exchanger)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="35597-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![Afbeelding van het te maken](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="35597-161">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="35597-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="35597-162">(Kies de **TTL-waarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="35597-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="35597-163">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="35597-163">**Record type**</span></span>|<span data-ttu-id="35597-164">**Host**</span><span class="sxs-lookup"><span data-stu-id="35597-164">**Host**</span></span>|<span data-ttu-id="35597-165">**Verwijst naar**</span><span class="sxs-lookup"><span data-stu-id="35597-165">**Points to**</span></span>|<span data-ttu-id="35597-166">**Priority**</span><span class="sxs-lookup"><span data-stu-id="35597-166">**Priority**</span></span>|<span data-ttu-id="35597-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="35597-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="35597-168">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="35597-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="35597-169">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="35597-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="35597-170">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="35597-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="35597-171">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="35597-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="35597-172">10</span><span class="sxs-lookup"><span data-stu-id="35597-172">10</span></span>  <br/> <span data-ttu-id="35597-173">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="35597-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="35597-174">1 uur</span><span class="sxs-lookup"><span data-stu-id="35597-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="35597-175">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="35597-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="35597-176">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="35597-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="35597-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="35597-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="35597-178">Voer de onderstaande stappen uit.</span><span class="sxs-lookup"><span data-stu-id="35597-178">Follow the steps below.</span></span>

1. <span data-ttu-id="35597-p110">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="35597-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="35597-182">Selecteer **onder Domeinen**de optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="35597-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="35597-184">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="35597-184">Select **Add**.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="35597-186">Kies **CNAME (Alias)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="35597-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![Afbeelding van het te maken](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="35597-188">Maak de eerste CNAME-record.</span><span class="sxs-lookup"><span data-stu-id="35597-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="35597-189">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="35597-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="35597-190">(Kies de **TTL-waarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="35597-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="35597-191">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="35597-191">**Record type**</span></span>|<span data-ttu-id="35597-192">**Host**</span><span class="sxs-lookup"><span data-stu-id="35597-192">**Host**</span></span>|<span data-ttu-id="35597-193">**Verwijst naar**</span><span class="sxs-lookup"><span data-stu-id="35597-193">**Points to**</span></span>|<span data-ttu-id="35597-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="35597-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="35597-195">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="35597-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="35597-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="35597-196">autodiscover</span></span>  <br/> |<span data-ttu-id="35597-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="35597-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="35597-198">1 uur</span><span class="sxs-lookup"><span data-stu-id="35597-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="35597-199">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="35597-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="35597-200">sip</span><span class="sxs-lookup"><span data-stu-id="35597-200">sip</span></span>  <br/> |<span data-ttu-id="35597-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="35597-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="35597-202">1 uur</span><span class="sxs-lookup"><span data-stu-id="35597-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="35597-203">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="35597-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="35597-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="35597-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="35597-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="35597-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="35597-206">1 uur</span><span class="sxs-lookup"><span data-stu-id="35597-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="35597-207">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="35597-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="35597-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="35597-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="35597-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="35597-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="35597-210">1 uur</span><span class="sxs-lookup"><span data-stu-id="35597-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="35597-211">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="35597-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="35597-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="35597-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="35597-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="35597-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="35597-214">1 uur</span><span class="sxs-lookup"><span data-stu-id="35597-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="35597-215">Herhaal deze stappen om de volgende CNAME-record toe te voegen totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="35597-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="35597-216">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="35597-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="35597-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="35597-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="35597-218">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="35597-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="35597-219">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="35597-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="35597-220">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35597-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="35597-221">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="35597-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="35597-222">Voer de onderstaande stappen uit:</span><span class="sxs-lookup"><span data-stu-id="35597-222">Follow the steps below.</span></span>

1. <span data-ttu-id="35597-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="35597-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="35597-226">Selecteer **onder Domeinen**de optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="35597-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="35597-228">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="35597-228">Select **Add**.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="35597-230">Kies **TXT (Text)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="35597-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![Afbeelding van het te maken](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="35597-232">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="35597-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="35597-233">(Kies de **TTL-waarde** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="35597-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="35597-234">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="35597-234">**Record type**</span></span>|<span data-ttu-id="35597-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="35597-235">**Host**</span></span>|<span data-ttu-id="35597-236">**TXT-waarde**</span><span class="sxs-lookup"><span data-stu-id="35597-236">**TXT Value**</span></span>|<span data-ttu-id="35597-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="35597-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="35597-238">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="35597-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="35597-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="35597-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="35597-240">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="35597-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="35597-241">1 uur</span><span class="sxs-lookup"><span data-stu-id="35597-241">1 hour</span></span>  <br/> |

    ![Afbeelding van het te maken](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="35597-243">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="35597-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="35597-244">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="35597-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="35597-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="35597-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="35597-246">Voer de onderstaande stappen uit.</span><span class="sxs-lookup"><span data-stu-id="35597-246">Follow the steps below.</span></span>

1. <span data-ttu-id="35597-p113">Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="35597-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="35597-250">Selecteer **onder Domeinen**de optie DNS onder het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="35597-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="35597-252">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="35597-252">Select **Add**.</span></span>

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="35597-254">Kies **SRV (Service)** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="35597-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![Afbeelding van het te maken](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="35597-256">Maak de eerste SRV-record.</span><span class="sxs-lookup"><span data-stu-id="35597-256">Create the first SRV record.</span></span>

    <span data-ttu-id="35597-257">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="35597-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="35597-258">(Kies de waarden **Record en** **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="35597-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="35597-259">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="35597-259">**Record type**</span></span>|<span data-ttu-id="35597-260">**Naam**</span><span class="sxs-lookup"><span data-stu-id="35597-260">**Name**</span></span>|<span data-ttu-id="35597-261">**Doel**</span><span class="sxs-lookup"><span data-stu-id="35597-261">**Target**</span></span>|<span data-ttu-id="35597-262">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="35597-262">**Protocol**</span></span>|<span data-ttu-id="35597-263">**Service**</span><span class="sxs-lookup"><span data-stu-id="35597-263">**Service**</span></span>|<span data-ttu-id="35597-264">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="35597-264">**Priority**</span></span>|<span data-ttu-id="35597-265">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="35597-265">**Weight**</span></span>|<span data-ttu-id="35597-266">**Poort**</span><span class="sxs-lookup"><span data-stu-id="35597-266">**Port**</span></span>|<span data-ttu-id="35597-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="35597-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="35597-268">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="35597-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="35597-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="35597-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="35597-270">_tls</span><span class="sxs-lookup"><span data-stu-id="35597-270">_tls</span></span>  <br/> |<span data-ttu-id="35597-271">_sip</span><span class="sxs-lookup"><span data-stu-id="35597-271">_sip</span></span>  <br/> |<span data-ttu-id="35597-272">100</span><span class="sxs-lookup"><span data-stu-id="35597-272">100</span></span>  <br/> |<span data-ttu-id="35597-273">1</span><span class="sxs-lookup"><span data-stu-id="35597-273">1</span></span>  <br/> |<span data-ttu-id="35597-274">443</span><span class="sxs-lookup"><span data-stu-id="35597-274">443</span></span>  <br/> |<span data-ttu-id="35597-275">1 uur</span><span class="sxs-lookup"><span data-stu-id="35597-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="35597-276">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="35597-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="35597-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="35597-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="35597-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="35597-278">_tcp</span></span>  <br/> |<span data-ttu-id="35597-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="35597-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="35597-280">100</span><span class="sxs-lookup"><span data-stu-id="35597-280">100</span></span>  <br/> |<span data-ttu-id="35597-281">1</span><span class="sxs-lookup"><span data-stu-id="35597-281">1</span></span>  <br/> |<span data-ttu-id="35597-282">5061</span><span class="sxs-lookup"><span data-stu-id="35597-282">5061</span></span>  <br/> |<span data-ttu-id="35597-283">1 uur</span><span class="sxs-lookup"><span data-stu-id="35597-283">1 hour</span></span>  <br/> |

    ![Afbeelding van het te maken voor afbeelding van het gebruik](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="35597-285">Herhaal **stap 5** om de andere SRV-record te maken.</span><span class="sxs-lookup"><span data-stu-id="35597-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="35597-286">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="35597-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="35597-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="35597-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
