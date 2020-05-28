---
title: DNS-records maken bij Bluehost voor Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Bluehost voor Microsoft.
ms.openlocfilehash: 7b241c4635ecc4a8092702f95d19df7ed94ce1cd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400555"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="e9c29-103">DNS-records maken bij Bluehost voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="e9c29-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="e9c29-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="e9c29-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e9c29-105">Als Bluehost uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="e9c29-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e9c29-106">Nadat u deze records bij Bluehost hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="e9c29-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="e9c29-p101">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9c29-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e9c29-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="e9c29-110">Add a TXT record for verification</span></span>
<span data-ttu-id="e9c29-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e9c29-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e9c29-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="e9c29-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9c29-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e9c29-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e9c29-116">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="e9c29-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="e9c29-117">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e9c29-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e9c29-118">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="e9c29-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="e9c29-119">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="e9c29-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="e9c29-120">Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="e9c29-120">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="e9c29-121">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e9c29-122">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="e9c29-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e9c29-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="e9c29-123">**Host Record**</span></span> <br/> |<span data-ttu-id="e9c29-124">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e9c29-124">**TTL**</span></span> <br/> |<span data-ttu-id="e9c29-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="e9c29-125">**Type**</span></span> <br/> |<span data-ttu-id="e9c29-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="e9c29-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="e9c29-127">14400</span><span class="sxs-lookup"><span data-stu-id="e9c29-127">14400</span></span>  <br/> |<span data-ttu-id="e9c29-128">TXT</span><span class="sxs-lookup"><span data-stu-id="e9c29-128">TXT</span></span>  <br/> |<span data-ttu-id="e9c29-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e9c29-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e9c29-130">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e9c29-130">**Note:** This is an example.</span></span> <span data-ttu-id="e9c29-131">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="e9c29-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e9c29-132">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="e9c29-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="e9c29-133">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="e9c29-134">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e9c29-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e9c29-135">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.</span><span class="sxs-lookup"><span data-stu-id="e9c29-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="e9c29-136">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="e9c29-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e9c29-137">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="e9c29-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e9c29-138">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="e9c29-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e9c29-139">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e9c29-140">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e9c29-p106">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9c29-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e9c29-144">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="e9c29-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e9c29-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e9c29-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e9c29-146">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="e9c29-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="e9c29-147">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e9c29-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e9c29-148">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="e9c29-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="e9c29-149">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="e9c29-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="e9c29-150">Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="e9c29-150">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="e9c29-151">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e9c29-152">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="e9c29-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e9c29-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="e9c29-153">**Host Record**</span></span>|<span data-ttu-id="e9c29-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e9c29-154">**TTL**</span></span>|<span data-ttu-id="e9c29-155">**Type**</span><span class="sxs-lookup"><span data-stu-id="e9c29-155">**Type**</span></span>|<span data-ttu-id="e9c29-156">**Points To**</span><span class="sxs-lookup"><span data-stu-id="e9c29-156">**Points To**</span></span>|<span data-ttu-id="e9c29-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="e9c29-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e9c29-158">14400</span><span class="sxs-lookup"><span data-stu-id="e9c29-158">14400</span></span>  <br/> |<span data-ttu-id="e9c29-159">MX</span><span class="sxs-lookup"><span data-stu-id="e9c29-159">MX</span></span>  <br/> | <span data-ttu-id="e9c29-160">*\<domain-key\>*.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e9c29-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="e9c29-161">**Let op:** Haal uw \<*domain-key*\> van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="e9c29-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="e9c29-162">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="e9c29-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="e9c29-163">0</span><span class="sxs-lookup"><span data-stu-id="e9c29-163">0</span></span>  <br/> <span data-ttu-id="e9c29-164">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="e9c29-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Type kiezen in de vervolgkeuzelijst](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="e9c29-166">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-166">Select **add record**.</span></span>
    
    ![Selecteer Record toevoegen](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="e9c29-168">Als het gedeelte **MX (Mail Exchanger)** andere MX-records bevat, verwijdert u deze.</span><span class="sxs-lookup"><span data-stu-id="e9c29-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="e9c29-169">Selecteer **Verwijderen** voor een van de andere MX-records.</span><span class="sxs-lookup"><span data-stu-id="e9c29-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![Verwijderen selecteren voor elke extra MX-record](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="e9c29-171">Selecteer **OK**in het bevestigingsdialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="e9c29-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Selecteer OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="e9c29-173">Verwijder op dezelfde manier alle andere MX-records die al worden vermeld.</span><span class="sxs-lookup"><span data-stu-id="e9c29-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e9c29-174">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="e9c29-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e9c29-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e9c29-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e9c29-176">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="e9c29-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="e9c29-177">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e9c29-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e9c29-178">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="e9c29-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="e9c29-179">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="e9c29-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="e9c29-180">Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="e9c29-180">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="e9c29-181">Zoek in de sectie **A-records** de rij voor de **record voor automatisch ontdekken** en selecteer vervolgens **verwijderen** voor die rij.</span><span class="sxs-lookup"><span data-stu-id="e9c29-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="e9c29-182">U moet de bestaande **record voor automatisch ontdekken** verwijderen *voordat* u de **autodiscoverrecord** toevoegt die door Microsoft vereist is.</span><span class="sxs-lookup"><span data-stu-id="e9c29-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="e9c29-183">U kunt in Bluehost geen twee **autodiscover** -records tegelijk behouden.</span><span class="sxs-lookup"><span data-stu-id="e9c29-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Selecteren Verwijderen](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="e9c29-185">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-185">Select **OK**.</span></span>
    
    ![Selecteer OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="e9c29-187">Maak de eerste van de zes CNAME-records.</span><span class="sxs-lookup"><span data-stu-id="e9c29-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="e9c29-188">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e9c29-189">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="e9c29-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e9c29-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="e9c29-190">**Host Record**</span></span>|<span data-ttu-id="e9c29-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e9c29-191">**TTL**</span></span>|<span data-ttu-id="e9c29-192">**Type**</span><span class="sxs-lookup"><span data-stu-id="e9c29-192">**Type**</span></span>|<span data-ttu-id="e9c29-193">**Points To**</span><span class="sxs-lookup"><span data-stu-id="e9c29-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e9c29-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e9c29-194">autodiscover</span></span>  <br/> |<span data-ttu-id="e9c29-195">14400</span><span class="sxs-lookup"><span data-stu-id="e9c29-195">14400</span></span>  <br/> |<span data-ttu-id="e9c29-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="e9c29-196">CNAME</span></span>  <br/> |<span data-ttu-id="e9c29-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e9c29-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="e9c29-198">sip</span><span class="sxs-lookup"><span data-stu-id="e9c29-198">sip</span></span>  <br/> |<span data-ttu-id="e9c29-199">14400</span><span class="sxs-lookup"><span data-stu-id="e9c29-199">14400</span></span>  <br/> |<span data-ttu-id="e9c29-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="e9c29-200">CNAME</span></span>  <br/> |<span data-ttu-id="e9c29-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9c29-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e9c29-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e9c29-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e9c29-203">14400</span><span class="sxs-lookup"><span data-stu-id="e9c29-203">14400</span></span>  <br/> |<span data-ttu-id="e9c29-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="e9c29-204">CNAME</span></span>  <br/> |<span data-ttu-id="e9c29-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9c29-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e9c29-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e9c29-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e9c29-207">14400</span><span class="sxs-lookup"><span data-stu-id="e9c29-207">14400</span></span>  <br/> |<span data-ttu-id="e9c29-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="e9c29-208">CNAME</span></span>  <br/> |<span data-ttu-id="e9c29-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e9c29-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="e9c29-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e9c29-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e9c29-211">14400</span><span class="sxs-lookup"><span data-stu-id="e9c29-211">14400</span></span>  <br/> |<span data-ttu-id="e9c29-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="e9c29-212">CNAME</span></span>  <br/> |<span data-ttu-id="e9c29-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e9c29-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![De eerste CNAME-record maken](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="e9c29-215">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-215">Select **add record**.</span></span>
    
    ![Selecteer Record toevoegen](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="e9c29-217">Voeg als volgt de andere vijf CNAME-records toe:</span><span class="sxs-lookup"><span data-stu-id="e9c29-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="e9c29-218">Maak nog steeds in de sectie **DNS-record toevoegen** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Record toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="e9c29-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="e9c29-219">Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e9c29-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e9c29-220">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="e9c29-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e9c29-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e9c29-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9c29-222">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="e9c29-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e9c29-223">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="e9c29-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e9c29-224">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9c29-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e9c29-225">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="e9c29-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="e9c29-226">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="e9c29-226">Need examples?</span></span> <span data-ttu-id="e9c29-227">Bekijk deze [Externe Domain Name System-records voor Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="e9c29-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="e9c29-228">Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e9c29-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="e9c29-229">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="e9c29-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="e9c29-230">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e9c29-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e9c29-231">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="e9c29-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="e9c29-232">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="e9c29-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="e9c29-233">Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="e9c29-233">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="e9c29-234">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e9c29-235">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="e9c29-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="e9c29-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="e9c29-236">**Host Record**</span></span>|<span data-ttu-id="e9c29-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e9c29-237">**TTL**</span></span>|<span data-ttu-id="e9c29-238">**Type**</span><span class="sxs-lookup"><span data-stu-id="e9c29-238">**Type**</span></span>|<span data-ttu-id="e9c29-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="e9c29-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e9c29-240">14400</span><span class="sxs-lookup"><span data-stu-id="e9c29-240">14400</span></span>  <br/> |<span data-ttu-id="e9c29-241">TXT</span><span class="sxs-lookup"><span data-stu-id="e9c29-241">TXT</span></span>  <br/> |<span data-ttu-id="e9c29-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e9c29-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="e9c29-243">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="e9c29-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![De Waarde TXT kopiëren](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="e9c29-245">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-245">Select **add record**.</span></span>
    
    ![Selecteer Record toevoegen](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e9c29-247">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="e9c29-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e9c29-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e9c29-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e9c29-249">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="e9c29-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="e9c29-250">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e9c29-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="e9c29-251">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="e9c29-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="e9c29-252">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="e9c29-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="e9c29-253">Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="e9c29-253">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="e9c29-254">Maak als volgt de eerste van de twee SRV-records.</span><span class="sxs-lookup"><span data-stu-id="e9c29-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="e9c29-255">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e9c29-256">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="e9c29-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e9c29-257">**Service**</span><span class="sxs-lookup"><span data-stu-id="e9c29-257">**Service**</span></span>|<span data-ttu-id="e9c29-258">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="e9c29-258">**Protocol**</span></span>|<span data-ttu-id="e9c29-259">**Host**</span><span class="sxs-lookup"><span data-stu-id="e9c29-259">**Host**</span></span>|<span data-ttu-id="e9c29-260">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e9c29-260">**TTL**</span></span>|<span data-ttu-id="e9c29-261">**Type**</span><span class="sxs-lookup"><span data-stu-id="e9c29-261">**Type**</span></span>|<span data-ttu-id="e9c29-262">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="e9c29-262">**Priority**</span></span>|<span data-ttu-id="e9c29-263">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="e9c29-263">**Weight**</span></span>|<span data-ttu-id="e9c29-264">**Poort**</span><span class="sxs-lookup"><span data-stu-id="e9c29-264">**Port**</span></span>|<span data-ttu-id="e9c29-265">**Points To**</span><span class="sxs-lookup"><span data-stu-id="e9c29-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e9c29-266">_sip</span><span class="sxs-lookup"><span data-stu-id="e9c29-266">_sip</span></span>  <br/> |<span data-ttu-id="e9c29-267">_tls</span><span class="sxs-lookup"><span data-stu-id="e9c29-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="e9c29-268">14400</span><span class="sxs-lookup"><span data-stu-id="e9c29-268">14400</span></span>  <br/> |<span data-ttu-id="e9c29-269">SRV</span><span class="sxs-lookup"><span data-stu-id="e9c29-269">SRV</span></span>  <br/> |<span data-ttu-id="e9c29-270">100</span><span class="sxs-lookup"><span data-stu-id="e9c29-270">100</span></span>  <br/> |<span data-ttu-id="e9c29-271">1</span><span class="sxs-lookup"><span data-stu-id="e9c29-271">1</span></span>  <br/> |<span data-ttu-id="e9c29-272">443</span><span class="sxs-lookup"><span data-stu-id="e9c29-272">443</span></span>  <br/> |<span data-ttu-id="e9c29-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9c29-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e9c29-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e9c29-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="e9c29-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="e9c29-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="e9c29-276">14400</span><span class="sxs-lookup"><span data-stu-id="e9c29-276">14400</span></span>  <br/> |<span data-ttu-id="e9c29-277">SRV</span><span class="sxs-lookup"><span data-stu-id="e9c29-277">SRV</span></span>  <br/> |<span data-ttu-id="e9c29-278">100</span><span class="sxs-lookup"><span data-stu-id="e9c29-278">100</span></span>  <br/> |<span data-ttu-id="e9c29-279">1</span><span class="sxs-lookup"><span data-stu-id="e9c29-279">1</span></span>  <br/> |<span data-ttu-id="e9c29-280">5061</span><span class="sxs-lookup"><span data-stu-id="e9c29-280">5061</span></span>  <br/> |<span data-ttu-id="e9c29-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e9c29-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![De waarde voor de nieuwe record kopiëren](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="e9c29-283">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e9c29-283">Select **add record**.</span></span>
    
    ![Selecteer Record toevoegen](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="e9c29-285">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="e9c29-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="e9c29-286">Maak nog steeds in de sectie **DNS-record toevoegen** een record met de waarden uit de andere rij in de tabel en selecteer vervolgens opnieuw **Record toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="e9c29-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e9c29-p114">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e9c29-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

