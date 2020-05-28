---
title: DNS-records maken bij DNSMadeEasy voor Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij DNSMadeEasy voor Microsoft.
ms.openlocfilehash: db28ac0cb95bd86bc13a1a1ce47f273989aa4436
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400519"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="5fdea-103">DNS-records maken bij DNSMadeEasy voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="5fdea-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="5fdea-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="5fdea-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5fdea-105">Als DNSMadeEasy uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="5fdea-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5fdea-106">Nadat u deze records hebt toegevoegd bij DNSMadeEasy, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="5fdea-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="5fdea-p101">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5fdea-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5fdea-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="5fdea-110">Add a TXT record for verification</span></span>
<span data-ttu-id="5fdea-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5fdea-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5fdea-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="5fdea-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5fdea-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5fdea-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5fdea-116">Voor DNSMadeEasy-accounts is het domein dat u hebt toegevoegd, gekocht bij een afzonderlijke domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="5fdea-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="5fdea-117">DNSMadeEasy biedt geen domeinregistratieservices aan.</span><span class="sxs-lookup"><span data-stu-id="5fdea-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="5fdea-118">Uw vermogen om in te loggen bij DNSMadeEasy en de DNS-record te maken is voldoende bewijs van eigendom.</span><span class="sxs-lookup"><span data-stu-id="5fdea-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="5fdea-119">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="5fdea-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="5fdea-120">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5fdea-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5fdea-121">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5fdea-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5fdea-122">Selecteer op de pagina **Beheerde DNS** in het gebied **TXT Records** het **+** besturingselement ( Nieuw **toevoegen**).</span><span class="sxs-lookup"><span data-stu-id="5fdea-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="5fdea-123">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5fdea-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="5fdea-124">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add TXT Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5fdea-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="5fdea-125">**Naam**</span><span class="sxs-lookup"><span data-stu-id="5fdea-125">**Name**</span></span> <br/> |<span data-ttu-id="5fdea-126">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="5fdea-126">**Value**</span></span> <br/> |<span data-ttu-id="5fdea-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5fdea-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="5fdea-128">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="5fdea-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5fdea-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5fdea-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5fdea-130">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="5fdea-130">**Note:** This is an example.</span></span> <span data-ttu-id="5fdea-131">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="5fdea-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="5fdea-132">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="5fdea-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5fdea-133">1800</span><span class="sxs-lookup"><span data-stu-id="5fdea-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="5fdea-134">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5fdea-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="5fdea-135">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="5fdea-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5fdea-136">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="5fdea-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="5fdea-137">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="5fdea-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5fdea-138">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="5fdea-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5fdea-139">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="5fdea-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5fdea-140">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="5fdea-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5fdea-141">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="5fdea-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5fdea-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5fdea-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5fdea-145">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="5fdea-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5fdea-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5fdea-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5fdea-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5fdea-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5fdea-149">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5fdea-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="5fdea-150">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5fdea-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![Afbeelding van het voorkomen van DNSMadeEasy-Bp-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="5fdea-152">Selecteer op de pagina **Beheerde DNS** in het gebied **MX Records** het **besturingselement (+)** **(Nieuw toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="5fdea-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5fdea-153">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5fdea-153">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken:DnsMadeEasy-BP-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="5fdea-155">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add MX Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5fdea-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5fdea-156">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5fdea-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5fdea-157">**Naam**</span><span class="sxs-lookup"><span data-stu-id="5fdea-157">**Name**</span></span>|<span data-ttu-id="5fdea-158">**Server**</span><span class="sxs-lookup"><span data-stu-id="5fdea-158">**Server**</span></span>|<span data-ttu-id="5fdea-159">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="5fdea-159">**MX Level**</span></span>|<span data-ttu-id="5fdea-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5fdea-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5fdea-161">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="5fdea-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="5fdea-162">*\<domain-key\>*.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5fdea-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5fdea-163">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5fdea-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="5fdea-164">**Let op:** Haal uw \<*domain-key*\> van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="5fdea-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="5fdea-165">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="5fdea-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5fdea-166">10</span><span class="sxs-lookup"><span data-stu-id="5fdea-166">10</span></span>  <br/> <span data-ttu-id="5fdea-167">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="5fdea-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="5fdea-168">1800</span><span class="sxs-lookup"><span data-stu-id="5fdea-168">1800</span></span>  <br/> |
   
    ![Afbeelding van het voorkomen van DNSMadeEasy-Bp-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="5fdea-170">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5fdea-170">Select **Submit**.</span></span>
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="5fdea-172">Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u deze door elk record te selecteren.</span><span class="sxs-lookup"><span data-stu-id="5fdea-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Configureren-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="5fdea-174">Wanneer alle records zijn geselecteerd, selecteert u **Geselecteerd verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="5fdea-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Configureren-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="5fdea-176">Selecteer **Verwijderen** om uw wijzigingen te bevestigen in het dialoogvenster **MX-records verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="5fdea-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5fdea-178">Voeg de vijf CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="5fdea-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5fdea-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5fdea-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5fdea-p110">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5fdea-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5fdea-182">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5fdea-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5fdea-183">Selecteer op de pagina **Beheerde DNS** in het gebied **CNAME Records** het besturingselement **(+)** **(Nieuw toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="5fdea-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5fdea-184">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5fdea-184">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="5fdea-186">Voeg de eerste van de vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="5fdea-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="5fdea-187">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add CNAME Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5fdea-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="5fdea-188">**Name**</span><span class="sxs-lookup"><span data-stu-id="5fdea-188">**Name**</span></span>|<span data-ttu-id="5fdea-189">**Alias to**</span><span class="sxs-lookup"><span data-stu-id="5fdea-189">**Alias to**</span></span>|<span data-ttu-id="5fdea-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5fdea-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5fdea-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5fdea-191">autodiscover</span></span>  <br/> |<span data-ttu-id="5fdea-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="5fdea-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="5fdea-193">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5fdea-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5fdea-194">1800</span><span class="sxs-lookup"><span data-stu-id="5fdea-194">1800</span></span>  <br/> |
    |<span data-ttu-id="5fdea-195">sip</span><span class="sxs-lookup"><span data-stu-id="5fdea-195">sip</span></span>  <br/> |<span data-ttu-id="5fdea-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5fdea-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5fdea-197">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5fdea-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5fdea-198">1800</span><span class="sxs-lookup"><span data-stu-id="5fdea-198">1800</span></span>  <br/> |
    |<span data-ttu-id="5fdea-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5fdea-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5fdea-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5fdea-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5fdea-201">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5fdea-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5fdea-202">1800</span><span class="sxs-lookup"><span data-stu-id="5fdea-202">1800</span></span>  <br/> |
    |<span data-ttu-id="5fdea-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5fdea-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5fdea-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="5fdea-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="5fdea-205">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5fdea-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5fdea-206">1800</span><span class="sxs-lookup"><span data-stu-id="5fdea-206">1800</span></span>  <br/> |
    |<span data-ttu-id="5fdea-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5fdea-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5fdea-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5fdea-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="5fdea-209">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5fdea-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5fdea-210">1800</span><span class="sxs-lookup"><span data-stu-id="5fdea-210">1800</span></span>  <br/> |
   
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="5fdea-212">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5fdea-212">Select **Submit**.</span></span>
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="5fdea-214">Voeg elk van de andere vier CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="5fdea-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="5fdea-215">Selecteer in de sectie **CNAME Records** het **besturingselement (+)** **(Nieuw toevoegen),** een record maken met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Verzenden** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="5fdea-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="5fdea-216">Herhaal dit proces totdat u alle vijf CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5fdea-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5fdea-217">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="5fdea-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5fdea-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5fdea-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fdea-219">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="5fdea-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5fdea-220">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="5fdea-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5fdea-221">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5fdea-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="5fdea-222">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="5fdea-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="5fdea-223">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="5fdea-223">Need examples?</span></span> <span data-ttu-id="5fdea-224">Bekijk deze [Externe Domain Name System-records voor Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="5fdea-224">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="5fdea-225">Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5fdea-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="5fdea-226">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="5fdea-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="5fdea-227">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5fdea-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5fdea-228">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5fdea-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5fdea-229">Selecteer op de pagina **Beheerde DNS** in het gebied **TXT Records** het **besturingselement (+)** **(Nieuw toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="5fdea-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5fdea-230">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="5fdea-230">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken:Knopafbeelding-Afbeelding](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="5fdea-232">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add TXT Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5fdea-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="5fdea-233">**Naam**</span><span class="sxs-lookup"><span data-stu-id="5fdea-233">**Name**</span></span>|<span data-ttu-id="5fdea-234">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="5fdea-234">**Value**</span></span>|<span data-ttu-id="5fdea-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5fdea-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5fdea-236">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="5fdea-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5fdea-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5fdea-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5fdea-238">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="5fdea-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="5fdea-239">1800</span><span class="sxs-lookup"><span data-stu-id="5fdea-239">1800</span></span>  <br/> |
   
    ![Afbeelding van het te maken-de-afbeelding-4-2 van DNSMadeEasy-Bp](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="5fdea-241">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5fdea-241">Select **Submit**.</span></span>
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-afbeelding](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5fdea-243">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="5fdea-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5fdea-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5fdea-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5fdea-p113">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5fdea-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5fdea-247">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="5fdea-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5fdea-248">Selecteer op de pagina **Beheerde DNS** in het gebied **SRV Records** het **besturingselement (+)** **(Nieuw toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="5fdea-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5fdea-249">(Mogelijk moet u omlaag schuiven)</span><span class="sxs-lookup"><span data-stu-id="5fdea-249">(You may have to scroll down)</span></span>
    
    ![Afbeelding van het te maken:DnsMadeEasy-BP-Configureren-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="5fdea-251">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="5fdea-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="5fdea-252">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add SRV Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="5fdea-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="5fdea-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="5fdea-253">**Name**</span></span>|<span data-ttu-id="5fdea-254">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="5fdea-254">**Priority**</span></span>|<span data-ttu-id="5fdea-255">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="5fdea-255">**Weight**</span></span>|<span data-ttu-id="5fdea-256">**Poort**</span><span class="sxs-lookup"><span data-stu-id="5fdea-256">**Port**</span></span>|<span data-ttu-id="5fdea-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="5fdea-257">**Host**</span></span>|<span data-ttu-id="5fdea-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5fdea-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5fdea-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="5fdea-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="5fdea-260">100</span><span class="sxs-lookup"><span data-stu-id="5fdea-260">100</span></span>  <br/> |<span data-ttu-id="5fdea-261">1</span><span class="sxs-lookup"><span data-stu-id="5fdea-261">1</span></span>  <br/> |<span data-ttu-id="5fdea-262">443</span><span class="sxs-lookup"><span data-stu-id="5fdea-262">443</span></span>  <br/> |<span data-ttu-id="5fdea-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5fdea-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5fdea-264">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5fdea-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5fdea-265">1800</span><span class="sxs-lookup"><span data-stu-id="5fdea-265">1800</span></span>  <br/> |
    |<span data-ttu-id="5fdea-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="5fdea-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5fdea-267">100</span><span class="sxs-lookup"><span data-stu-id="5fdea-267">100</span></span>  <br/> |<span data-ttu-id="5fdea-268">1</span><span class="sxs-lookup"><span data-stu-id="5fdea-268">1</span></span>  <br/> |<span data-ttu-id="5fdea-269">5061</span><span class="sxs-lookup"><span data-stu-id="5fdea-269">5061</span></span>  <br/> |<span data-ttu-id="5fdea-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5fdea-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="5fdea-271">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="5fdea-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5fdea-272">1800</span><span class="sxs-lookup"><span data-stu-id="5fdea-272">1800</span></span>  <br/> |
   
    ![Afbeelding van het te maken-Bp-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="5fdea-274">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="5fdea-274">Select **Submit**.</span></span>
    
    ![Afbeelding van het te maken-Bp-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="5fdea-276">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="5fdea-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="5fdea-277">Selecteer in de sectie **SRV Records** het **besturingselement (+)** **(Nieuw toevoegen),** een record maken met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Verzenden** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="5fdea-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="5fdea-p114">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5fdea-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

