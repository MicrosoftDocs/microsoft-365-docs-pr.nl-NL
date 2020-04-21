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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Bluehost voor Microsoft.
ms.openlocfilehash: a39e44794ad0d8c66cd0786f88642541c6978a8c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629717"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="a8c55-103">DNS-records maken bij Bluehost voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8c55-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="a8c55-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="a8c55-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a8c55-105">Als Bluehost uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a8c55-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a8c55-106">Nadat u deze records bij Bluehost hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="a8c55-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="a8c55-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="a8c55-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8c55-108">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="a8c55-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a8c55-109">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="a8c55-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a8c55-110">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="a8c55-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a8c55-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="a8c55-111">Add a TXT record for verification</span></span>
<span data-ttu-id="a8c55-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a8c55-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a8c55-113">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="a8c55-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="a8c55-114">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="a8c55-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8c55-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a8c55-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a8c55-117">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="a8c55-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="a8c55-118">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="a8c55-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a8c55-119">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="a8c55-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="a8c55-120">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="a8c55-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="a8c55-121">Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="a8c55-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="a8c55-122">Typ of kopieer en plak de waarden uit de volgende tabel op de pagina \*\* DNS-zoneeditor \*\* in het gebied **DNS-record toevoegen** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="a8c55-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a8c55-123">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="a8c55-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a8c55-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="a8c55-124">**Host Record**</span></span> <br/> |<span data-ttu-id="a8c55-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8c55-125">**TTL**</span></span> <br/> |<span data-ttu-id="a8c55-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="a8c55-126">**Type**</span></span> <br/> |<span data-ttu-id="a8c55-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="a8c55-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="a8c55-128">14400</span><span class="sxs-lookup"><span data-stu-id="a8c55-128">14400</span></span>  <br/> |<span data-ttu-id="a8c55-129">TXT</span><span class="sxs-lookup"><span data-stu-id="a8c55-129">TXT</span></span>  <br/> |<span data-ttu-id="a8c55-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a8c55-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a8c55-131">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="a8c55-131">**Note:** This is an example.</span></span> <span data-ttu-id="a8c55-132">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="a8c55-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="a8c55-133">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="a8c55-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="a8c55-134">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="a8c55-135">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="a8c55-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a8c55-136">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.</span><span class="sxs-lookup"><span data-stu-id="a8c55-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="a8c55-137">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="a8c55-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a8c55-138">Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="a8c55-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a8c55-139">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="a8c55-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="a8c55-140">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="a8c55-141">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a8c55-142">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="a8c55-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a8c55-143">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="a8c55-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a8c55-144">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="a8c55-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a8c55-145">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="a8c55-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a8c55-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a8c55-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a8c55-147">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="a8c55-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="a8c55-148">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="a8c55-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a8c55-149">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="a8c55-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="a8c55-150">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="a8c55-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="a8c55-151">Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="a8c55-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="a8c55-152">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a8c55-153">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="a8c55-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a8c55-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="a8c55-154">**Host Record**</span></span>|<span data-ttu-id="a8c55-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8c55-155">**TTL**</span></span>|<span data-ttu-id="a8c55-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="a8c55-156">**Type**</span></span>|<span data-ttu-id="a8c55-157">**Points To**</span><span class="sxs-lookup"><span data-stu-id="a8c55-157">**Points To**</span></span>|<span data-ttu-id="a8c55-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a8c55-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a8c55-159">14400</span><span class="sxs-lookup"><span data-stu-id="a8c55-159">14400</span></span>  <br/> |<span data-ttu-id="a8c55-160">MX</span><span class="sxs-lookup"><span data-stu-id="a8c55-160">MX</span></span>  <br/> | <span data-ttu-id="a8c55-161">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a8c55-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="a8c55-162">**Let op:** Haal \<uw domeinsleutel\> uit uw *Microsoft-account.*</span><span class="sxs-lookup"><span data-stu-id="a8c55-162">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="a8c55-163">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="a8c55-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a8c55-164">0</span><span class="sxs-lookup"><span data-stu-id="a8c55-164">0</span></span>  <br/> <span data-ttu-id="a8c55-165">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="a8c55-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Type kiezen in de vervolgkeuzelijst](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="a8c55-167">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-167">Select **add record**.</span></span>
    
    ![Selecteer Record toevoegen](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="a8c55-169">Als het gedeelte **MX (Mail Exchanger)** andere MX-records bevat, verwijdert u deze.</span><span class="sxs-lookup"><span data-stu-id="a8c55-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="a8c55-170">Selecteer **Verwijderen** voor een van de andere MX-records.</span><span class="sxs-lookup"><span data-stu-id="a8c55-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Verwijderen selecteren voor elke extra MX-record](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="a8c55-172">Selecteer **OK**in het bevestigingsdialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="a8c55-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Selecteer OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="a8c55-174">Verwijder op dezelfde manier alle andere MX-records die al worden vermeld.</span><span class="sxs-lookup"><span data-stu-id="a8c55-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a8c55-175">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8c55-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a8c55-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a8c55-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a8c55-177">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="a8c55-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="a8c55-178">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="a8c55-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a8c55-179">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="a8c55-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="a8c55-180">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="a8c55-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="a8c55-181">Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="a8c55-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="a8c55-182">Zoek in de sectie **A-records** de rij voor de **record voor automatisch ontdekken** en selecteer vervolgens **verwijderen** voor die rij.</span><span class="sxs-lookup"><span data-stu-id="a8c55-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="a8c55-183">U moet de bestaande **record voor automatisch ontdekken** verwijderen *voordat* u de **autodiscoverrecord** toevoegt die door Microsoft vereist is.</span><span class="sxs-lookup"><span data-stu-id="a8c55-183">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="a8c55-184">U kunt in Bluehost geen twee **autodiscover** -records tegelijk behouden.</span><span class="sxs-lookup"><span data-stu-id="a8c55-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Selecteren Verwijderen](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="a8c55-186">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-186">Select **OK**.</span></span>
    
    ![Selecteer OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="a8c55-188">Maak de eerste van de zes CNAME-records.</span><span class="sxs-lookup"><span data-stu-id="a8c55-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="a8c55-189">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="a8c55-190">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="a8c55-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a8c55-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="a8c55-191">**Host Record**</span></span>|<span data-ttu-id="a8c55-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8c55-192">**TTL**</span></span>|<span data-ttu-id="a8c55-193">**Type**</span><span class="sxs-lookup"><span data-stu-id="a8c55-193">**Type**</span></span>|<span data-ttu-id="a8c55-194">**Points To**</span><span class="sxs-lookup"><span data-stu-id="a8c55-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a8c55-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a8c55-195">autodiscover</span></span>  <br/> |<span data-ttu-id="a8c55-196">14400</span><span class="sxs-lookup"><span data-stu-id="a8c55-196">14400</span></span>  <br/> |<span data-ttu-id="a8c55-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="a8c55-197">CNAME</span></span>  <br/> |<span data-ttu-id="a8c55-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a8c55-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a8c55-199">sip</span><span class="sxs-lookup"><span data-stu-id="a8c55-199">sip</span></span>  <br/> |<span data-ttu-id="a8c55-200">14400</span><span class="sxs-lookup"><span data-stu-id="a8c55-200">14400</span></span>  <br/> |<span data-ttu-id="a8c55-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="a8c55-201">CNAME</span></span>  <br/> |<span data-ttu-id="a8c55-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a8c55-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a8c55-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a8c55-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a8c55-204">14400</span><span class="sxs-lookup"><span data-stu-id="a8c55-204">14400</span></span>  <br/> |<span data-ttu-id="a8c55-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="a8c55-205">CNAME</span></span>  <br/> |<span data-ttu-id="a8c55-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a8c55-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a8c55-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a8c55-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a8c55-208">14400</span><span class="sxs-lookup"><span data-stu-id="a8c55-208">14400</span></span>  <br/> |<span data-ttu-id="a8c55-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="a8c55-209">CNAME</span></span>  <br/> |<span data-ttu-id="a8c55-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a8c55-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a8c55-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a8c55-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a8c55-212">14400</span><span class="sxs-lookup"><span data-stu-id="a8c55-212">14400</span></span>  <br/> |<span data-ttu-id="a8c55-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="a8c55-213">CNAME</span></span>  <br/> |<span data-ttu-id="a8c55-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a8c55-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![De eerste CNAME-record maken](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="a8c55-216">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-216">Select **add record**.</span></span>
    
    ![Selecteer Record toevoegen](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="a8c55-218">Voeg als volgt de andere vijf CNAME-records toe:</span><span class="sxs-lookup"><span data-stu-id="a8c55-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="a8c55-219">Maak nog steeds in de sectie **DNS-record toevoegen** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Record toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="a8c55-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="a8c55-220">Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a8c55-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a8c55-221">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="a8c55-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a8c55-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a8c55-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8c55-223">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="a8c55-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a8c55-224">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="a8c55-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a8c55-225">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8c55-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a8c55-226">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="a8c55-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="a8c55-227">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="a8c55-227">Need examples?</span></span> <span data-ttu-id="a8c55-228">Bekijk deze [externe domeinnaamsysteemrecords voor Microsoft.](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)</span><span class="sxs-lookup"><span data-stu-id="a8c55-228">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="a8c55-229">Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a8c55-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="a8c55-230">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="a8c55-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="a8c55-231">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="a8c55-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a8c55-232">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="a8c55-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="a8c55-233">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="a8c55-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="a8c55-234">Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="a8c55-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="a8c55-235">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="a8c55-236">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="a8c55-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="a8c55-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="a8c55-237">**Host Record**</span></span>|<span data-ttu-id="a8c55-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8c55-238">**TTL**</span></span>|<span data-ttu-id="a8c55-239">**Type**</span><span class="sxs-lookup"><span data-stu-id="a8c55-239">**Type**</span></span>|<span data-ttu-id="a8c55-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="a8c55-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a8c55-241">14400</span><span class="sxs-lookup"><span data-stu-id="a8c55-241">14400</span></span>  <br/> |<span data-ttu-id="a8c55-242">TXT</span><span class="sxs-lookup"><span data-stu-id="a8c55-242">TXT</span></span>  <br/> |<span data-ttu-id="a8c55-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a8c55-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="a8c55-244">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="a8c55-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![De Waarde TXT kopiëren](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="a8c55-246">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-246">Select **add record**.</span></span>
    
    ![Selecteer Record toevoegen](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a8c55-248">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8c55-248">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a8c55-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a8c55-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a8c55-250">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="a8c55-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="a8c55-251">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="a8c55-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="a8c55-252">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="a8c55-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="a8c55-253">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="a8c55-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="a8c55-254">Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="a8c55-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="a8c55-255">Maak als volgt de eerste van de twee SRV-records.</span><span class="sxs-lookup"><span data-stu-id="a8c55-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="a8c55-256">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="a8c55-257">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="a8c55-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a8c55-258">**Service**</span><span class="sxs-lookup"><span data-stu-id="a8c55-258">**Service**</span></span>|<span data-ttu-id="a8c55-259">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="a8c55-259">**Protocol**</span></span>|<span data-ttu-id="a8c55-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="a8c55-260">**Host**</span></span>|<span data-ttu-id="a8c55-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8c55-261">**TTL**</span></span>|<span data-ttu-id="a8c55-262">**Type**</span><span class="sxs-lookup"><span data-stu-id="a8c55-262">**Type**</span></span>|<span data-ttu-id="a8c55-263">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="a8c55-263">**Priority**</span></span>|<span data-ttu-id="a8c55-264">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="a8c55-264">**Weight**</span></span>|<span data-ttu-id="a8c55-265">**Poort**</span><span class="sxs-lookup"><span data-stu-id="a8c55-265">**Port**</span></span>|<span data-ttu-id="a8c55-266">**Points To**</span><span class="sxs-lookup"><span data-stu-id="a8c55-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a8c55-267">_sip</span><span class="sxs-lookup"><span data-stu-id="a8c55-267">_sip</span></span>  <br/> |<span data-ttu-id="a8c55-268">_tls</span><span class="sxs-lookup"><span data-stu-id="a8c55-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="a8c55-269">14400</span><span class="sxs-lookup"><span data-stu-id="a8c55-269">14400</span></span>  <br/> |<span data-ttu-id="a8c55-270">SRV</span><span class="sxs-lookup"><span data-stu-id="a8c55-270">SRV</span></span>  <br/> |<span data-ttu-id="a8c55-271">100</span><span class="sxs-lookup"><span data-stu-id="a8c55-271">100</span></span>  <br/> |<span data-ttu-id="a8c55-272">1</span><span class="sxs-lookup"><span data-stu-id="a8c55-272">1</span></span>  <br/> |<span data-ttu-id="a8c55-273">443</span><span class="sxs-lookup"><span data-stu-id="a8c55-273">443</span></span>  <br/> |<span data-ttu-id="a8c55-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a8c55-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a8c55-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a8c55-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a8c55-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="a8c55-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="a8c55-277">14400</span><span class="sxs-lookup"><span data-stu-id="a8c55-277">14400</span></span>  <br/> |<span data-ttu-id="a8c55-278">SRV</span><span class="sxs-lookup"><span data-stu-id="a8c55-278">SRV</span></span>  <br/> |<span data-ttu-id="a8c55-279">100</span><span class="sxs-lookup"><span data-stu-id="a8c55-279">100</span></span>  <br/> |<span data-ttu-id="a8c55-280">1</span><span class="sxs-lookup"><span data-stu-id="a8c55-280">1</span></span>  <br/> |<span data-ttu-id="a8c55-281">5061</span><span class="sxs-lookup"><span data-stu-id="a8c55-281">5061</span></span>  <br/> |<span data-ttu-id="a8c55-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a8c55-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![De waarde voor de nieuwe record kopiëren](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="a8c55-284">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a8c55-284">Select **add record**.</span></span>
    
    ![Selecteer Record toevoegen](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="a8c55-286">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="a8c55-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="a8c55-287">Maak nog steeds in de sectie **DNS-record toevoegen** een record met de waarden uit de andere rij in de tabel en selecteer vervolgens opnieuw **Record toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="a8c55-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="a8c55-288">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="a8c55-288">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a8c55-289">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="a8c55-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a8c55-290">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="a8c55-290">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

