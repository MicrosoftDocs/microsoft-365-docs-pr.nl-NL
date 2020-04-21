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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij DNSMadeEasy voor Microsoft.
ms.openlocfilehash: dde060b6e03eebb89029b742402558e95031b1d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629681"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="945bf-103">DNS-records maken bij DNSMadeEasy voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="945bf-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="945bf-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="945bf-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="945bf-105">Als DNSMadeEasy uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="945bf-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="945bf-106">Nadat u deze records hebt toegevoegd bij DNSMadeEasy, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="945bf-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="945bf-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="945bf-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="945bf-108">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="945bf-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="945bf-109">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="945bf-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="945bf-110">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="945bf-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="945bf-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="945bf-111">Add a TXT record for verification</span></span>
<span data-ttu-id="945bf-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="945bf-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="945bf-113">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="945bf-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="945bf-114">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="945bf-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="945bf-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="945bf-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="945bf-117">Voor DNSMadeEasy-accounts is het domein dat u hebt toegevoegd, gekocht bij een afzonderlijke domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="945bf-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="945bf-118">DNSMadeEasy biedt geen domeinregistratieservices aan.</span><span class="sxs-lookup"><span data-stu-id="945bf-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="945bf-119">Uw vermogen om in te loggen bij DNSMadeEasy en de DNS-record te maken is voldoende bewijs van eigendom.</span><span class="sxs-lookup"><span data-stu-id="945bf-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="945bf-120">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="945bf-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="945bf-121">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="945bf-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="945bf-122">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="945bf-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="945bf-123">Selecteer op de pagina **Beheerde DNS** in het **+** gebied **TXT Records** het besturingselement ( Nieuw **toevoegen**).</span><span class="sxs-lookup"><span data-stu-id="945bf-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="945bf-124">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="945bf-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="945bf-125">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add TXT Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="945bf-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="945bf-126">**Naam**</span><span class="sxs-lookup"><span data-stu-id="945bf-126">**Name**</span></span> <br/> |<span data-ttu-id="945bf-127">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="945bf-127">**Value**</span></span> <br/> |<span data-ttu-id="945bf-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="945bf-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="945bf-129">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="945bf-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="945bf-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="945bf-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="945bf-131">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="945bf-131">**Note:** This is an example.</span></span> <span data-ttu-id="945bf-132">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="945bf-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="945bf-133">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="945bf-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="945bf-134">1800</span><span class="sxs-lookup"><span data-stu-id="945bf-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="945bf-135">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="945bf-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="945bf-136">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="945bf-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="945bf-137">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="945bf-137">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="945bf-138">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="945bf-138">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="945bf-139">Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="945bf-139">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="945bf-140">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="945bf-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="945bf-141">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="945bf-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="945bf-142">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="945bf-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="945bf-143">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="945bf-143">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="945bf-144">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="945bf-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="945bf-145">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="945bf-145">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="945bf-146">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="945bf-146">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="945bf-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="945bf-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="945bf-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="945bf-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="945bf-150">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="945bf-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="945bf-151">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="945bf-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![Afbeelding van het voorkomen van DNSMadeEasy-Bp-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="945bf-153">Selecteer op de pagina **Beheerde DNS** in het gebied **MX Records** het **besturingselement (+)** **(Nieuw toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="945bf-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="945bf-154">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="945bf-154">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken:DnsMadeEasy-BP-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="945bf-156">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add MX Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="945bf-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="945bf-157">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="945bf-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="945bf-158">**Naam**</span><span class="sxs-lookup"><span data-stu-id="945bf-158">**Name**</span></span>|<span data-ttu-id="945bf-159">**Server**</span><span class="sxs-lookup"><span data-stu-id="945bf-159">**Server**</span></span>|<span data-ttu-id="945bf-160">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="945bf-160">**MX Level**</span></span>|<span data-ttu-id="945bf-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="945bf-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="945bf-162">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="945bf-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="945bf-163">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="945bf-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="945bf-164">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="945bf-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="945bf-165">**Let op:** Haal \<uw domeinsleutel\> uit uw *Microsoft-account.*</span><span class="sxs-lookup"><span data-stu-id="945bf-165">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="945bf-166">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="945bf-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="945bf-167">10</span><span class="sxs-lookup"><span data-stu-id="945bf-167">10</span></span>  <br/> <span data-ttu-id="945bf-168">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="945bf-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="945bf-169">1800</span><span class="sxs-lookup"><span data-stu-id="945bf-169">1800</span></span>  <br/> |
   
    ![Afbeelding van het voorkomen van DNSMadeEasy-Bp-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="945bf-171">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="945bf-171">Select **Submit**.</span></span>
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="945bf-173">Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u deze door elk record te selecteren.</span><span class="sxs-lookup"><span data-stu-id="945bf-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Configureren-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="945bf-175">Wanneer alle records zijn geselecteerd, selecteert u **Geselecteerd verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="945bf-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Configureren-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="945bf-177">Selecteer **Verwijderen** om uw wijzigingen te bevestigen in het dialoogvenster **MX-records verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="945bf-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="945bf-179">Voeg de vijf CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="945bf-179">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="945bf-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="945bf-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="945bf-p110">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="945bf-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="945bf-183">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="945bf-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="945bf-184">Selecteer op de pagina **Beheerde DNS** in het gebied **CNAME Records** het besturingselement **(+)** **(Nieuw toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="945bf-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="945bf-185">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="945bf-185">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="945bf-187">Voeg de eerste van de vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="945bf-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="945bf-188">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add CNAME Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="945bf-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="945bf-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="945bf-189">**Name**</span></span>|<span data-ttu-id="945bf-190">**Alias to**</span><span class="sxs-lookup"><span data-stu-id="945bf-190">**Alias to**</span></span>|<span data-ttu-id="945bf-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="945bf-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="945bf-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="945bf-192">autodiscover</span></span>  <br/> |<span data-ttu-id="945bf-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="945bf-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="945bf-194">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="945bf-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="945bf-195">1800</span><span class="sxs-lookup"><span data-stu-id="945bf-195">1800</span></span>  <br/> |
    |<span data-ttu-id="945bf-196">sip</span><span class="sxs-lookup"><span data-stu-id="945bf-196">sip</span></span>  <br/> |<span data-ttu-id="945bf-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="945bf-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="945bf-198">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="945bf-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="945bf-199">1800</span><span class="sxs-lookup"><span data-stu-id="945bf-199">1800</span></span>  <br/> |
    |<span data-ttu-id="945bf-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="945bf-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="945bf-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="945bf-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="945bf-202">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="945bf-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="945bf-203">1800</span><span class="sxs-lookup"><span data-stu-id="945bf-203">1800</span></span>  <br/> |
    |<span data-ttu-id="945bf-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="945bf-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="945bf-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="945bf-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="945bf-206">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="945bf-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="945bf-207">1800</span><span class="sxs-lookup"><span data-stu-id="945bf-207">1800</span></span>  <br/> |
    |<span data-ttu-id="945bf-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="945bf-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="945bf-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="945bf-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="945bf-210">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="945bf-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="945bf-211">1800</span><span class="sxs-lookup"><span data-stu-id="945bf-211">1800</span></span>  <br/> |
   
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="945bf-213">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="945bf-213">Select **Submit**.</span></span>
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="945bf-215">Voeg elk van de andere vier CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="945bf-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="945bf-216">Selecteer in de sectie **CNAME Records** het **besturingselement (+)** **(Nieuw toevoegen),** een record maken met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Verzenden** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="945bf-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="945bf-217">Herhaal dit proces totdat u alle vijf CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="945bf-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="945bf-218">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="945bf-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="945bf-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="945bf-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="945bf-220">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="945bf-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="945bf-221">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="945bf-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="945bf-222">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="945bf-222">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="945bf-223">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="945bf-223">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="945bf-224">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="945bf-224">Need examples?</span></span> <span data-ttu-id="945bf-225">Bekijk deze [externe domeinnaamsysteemrecords voor Microsoft.](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)</span><span class="sxs-lookup"><span data-stu-id="945bf-225">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="945bf-226">Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="945bf-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="945bf-227">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="945bf-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="945bf-228">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="945bf-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="945bf-229">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="945bf-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="945bf-230">Selecteer op de pagina **Beheerde DNS** in het gebied **TXT Records** het **besturingselement (+)** **(Nieuw toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="945bf-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="945bf-231">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="945bf-231">(You may have to scroll down.)</span></span>
    
    ![Afbeelding van het te maken:Knopafbeelding-Afbeelding](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="945bf-233">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add TXT Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="945bf-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="945bf-234">**Naam**</span><span class="sxs-lookup"><span data-stu-id="945bf-234">**Name**</span></span>|<span data-ttu-id="945bf-235">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="945bf-235">**Value**</span></span>|<span data-ttu-id="945bf-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="945bf-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="945bf-237">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="945bf-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="945bf-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="945bf-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="945bf-239">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="945bf-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="945bf-240">1800</span><span class="sxs-lookup"><span data-stu-id="945bf-240">1800</span></span>  <br/> |
   
    ![Afbeelding van het te maken-de-afbeelding-4-2 van DNSMadeEasy-Bp](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="945bf-242">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="945bf-242">Select **Submit**.</span></span>
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-afbeelding](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="945bf-244">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="945bf-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="945bf-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="945bf-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="945bf-p113">Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="945bf-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="945bf-248">Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="945bf-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="945bf-249">Selecteer op de pagina **Beheerde DNS** in het gebied **SRV Records** het **besturingselement (+)** **(Nieuw toevoegen).**</span><span class="sxs-lookup"><span data-stu-id="945bf-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="945bf-250">(Mogelijk moet u omlaag schuiven)</span><span class="sxs-lookup"><span data-stu-id="945bf-250">(You may have to scroll down)</span></span>
    
    ![Afbeelding van het te maken:DnsMadeEasy-BP-Configureren-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="945bf-252">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="945bf-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="945bf-253">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add SRV Records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="945bf-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="945bf-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="945bf-254">**Name**</span></span>|<span data-ttu-id="945bf-255">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="945bf-255">**Priority**</span></span>|<span data-ttu-id="945bf-256">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="945bf-256">**Weight**</span></span>|<span data-ttu-id="945bf-257">**Poort**</span><span class="sxs-lookup"><span data-stu-id="945bf-257">**Port**</span></span>|<span data-ttu-id="945bf-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="945bf-258">**Host**</span></span>|<span data-ttu-id="945bf-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="945bf-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="945bf-260">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="945bf-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="945bf-261">100</span><span class="sxs-lookup"><span data-stu-id="945bf-261">100</span></span>  <br/> |<span data-ttu-id="945bf-262">1</span><span class="sxs-lookup"><span data-stu-id="945bf-262">1</span></span>  <br/> |<span data-ttu-id="945bf-263">443</span><span class="sxs-lookup"><span data-stu-id="945bf-263">443</span></span>  <br/> |<span data-ttu-id="945bf-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="945bf-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="945bf-265">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="945bf-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="945bf-266">1800</span><span class="sxs-lookup"><span data-stu-id="945bf-266">1800</span></span>  <br/> |
    |<span data-ttu-id="945bf-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="945bf-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="945bf-268">100</span><span class="sxs-lookup"><span data-stu-id="945bf-268">100</span></span>  <br/> |<span data-ttu-id="945bf-269">1</span><span class="sxs-lookup"><span data-stu-id="945bf-269">1</span></span>  <br/> |<span data-ttu-id="945bf-270">5061</span><span class="sxs-lookup"><span data-stu-id="945bf-270">5061</span></span>  <br/> |<span data-ttu-id="945bf-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="945bf-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="945bf-272">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="945bf-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="945bf-273">1800</span><span class="sxs-lookup"><span data-stu-id="945bf-273">1800</span></span>  <br/> |
   
    ![Afbeelding van het te maken-Bp-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="945bf-275">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="945bf-275">Select **Submit**.</span></span>
    
    ![Afbeelding van het te maken-Bp-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="945bf-277">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="945bf-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="945bf-278">Selecteer in de sectie **SRV Records** het **besturingselement (+)** **(Nieuw toevoegen),** een record maken met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Verzenden** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="945bf-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="945bf-279">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="945bf-279">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="945bf-280">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="945bf-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="945bf-281">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="945bf-281">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

