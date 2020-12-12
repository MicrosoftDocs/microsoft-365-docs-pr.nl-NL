---
title: DNS-records bij Wix maken voor Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Wix voor Microsoft.
ms.openlocfilehash: 01317f7e2da87b532c93f12269fd65b7d4fe2dd6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656877"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="c46f4-103">DNS-records bij Wix maken voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="c46f4-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="c46f4-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="c46f4-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c46f4-105">Als Wix uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="c46f4-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="c46f4-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="c46f4-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="c46f4-107">[Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="c46f4-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="c46f4-108">[Voeg een MX-record toe zodat e-mail voor uw domein bij Microsoft komt](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c46f4-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="c46f4-109">[Voeg de vijf CNAME-records toe die voor Microsoft vereist zijn](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c46f4-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="c46f4-110">[Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="c46f4-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="c46f4-111">[Voeg de twee SRV-records toe die voor Microsoft vereist zijn](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="c46f4-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="c46f4-112">Nadat u deze records bij Wix hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="c46f4-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="c46f4-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c46f4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c46f4-116">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="c46f4-116">Add a TXT record for verification</span></span>
<span data-ttu-id="c46f4-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="c46f4-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="c46f4-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="c46f4-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c46f4-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c46f4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="c46f4-122">WIX biedt geen ondersteuning voor DNS-vermeldingen voor subdomeinen.</span><span class="sxs-lookup"><span data-stu-id="c46f4-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="c46f4-123">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="c46f4-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c46f4-124">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="c46f4-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c46f4-125">Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="c46f4-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c46f4-126">Selecteer **+ een andere toevoegen** in de rij **txt (text)** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="c46f4-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c46f4-127">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="c46f4-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="c46f4-128">Host name</span><span class="sxs-lookup"><span data-stu-id="c46f4-128">Host Name</span></span> <br/> | <span data-ttu-id="c46f4-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="c46f4-129">TXT Value</span></span> <br/> | <span data-ttu-id="c46f4-130">TTL</span><span class="sxs-lookup"><span data-stu-id="c46f4-130">TTL</span></span> <br/> |
   |<span data-ttu-id="c46f4-131">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="c46f4-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="c46f4-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c46f4-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c46f4-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="c46f4-133">**Note:** This is an example.</span></span> <span data-ttu-id="c46f4-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="c46f4-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="c46f4-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="c46f4-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="c46f4-136">1 uur</span><span class="sxs-lookup"><span data-stu-id="c46f4-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="c46f4-137">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="c46f4-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c46f4-138">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="c46f4-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c46f4-139">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="c46f4-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c46f4-140">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="c46f4-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c46f4-141">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="c46f4-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c46f4-142">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="c46f4-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="c46f4-143">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="c46f4-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="c46f4-144">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="c46f4-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c46f4-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c46f4-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c46f4-148">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="c46f4-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c46f4-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="c46f4-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="c46f4-150">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="c46f4-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c46f4-151">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="c46f4-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c46f4-152">Selecteer op de pagina **My Domains** in het gebied **postvakken** de koppeling **uw MX records configureren** .</span><span class="sxs-lookup"><span data-stu-id="c46f4-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="c46f4-153">Kies in de vervolgkeuzelijst **uw e-mail provider** de optie **Overige** .</span><span class="sxs-lookup"><span data-stu-id="c46f4-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="c46f4-154">Selecteer **+ een andere toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c46f4-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="c46f4-155">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="c46f4-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c46f4-156">Host name</span><span class="sxs-lookup"><span data-stu-id="c46f4-156">Host Name</span></span> | <span data-ttu-id="c46f4-157">Verwijst naar</span><span class="sxs-lookup"><span data-stu-id="c46f4-157">Points to</span></span> | <span data-ttu-id="c46f4-158">Priority</span><span class="sxs-lookup"><span data-stu-id="c46f4-158">Priority</span></span> | <span data-ttu-id="c46f4-159">TTL</span><span class="sxs-lookup"><span data-stu-id="c46f4-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="c46f4-160">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="c46f4-160">Automatically populated</span></span> <br/> | <span data-ttu-id="c46f4-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c46f4-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c46f4-162">**Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="c46f4-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="c46f4-163">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="c46f4-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="c46f4-164">0</span><span class="sxs-lookup"><span data-stu-id="c46f4-164">0</span></span>  <br/> <span data-ttu-id="c46f4-165">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="c46f4-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="c46f4-166">1 uur</span><span class="sxs-lookup"><span data-stu-id="c46f4-166">1 Hour</span></span>|
   
6. <span data-ttu-id="c46f4-167">Als er andere MX-records worden vermeld, verwijdert u elke record.</span><span class="sxs-lookup"><span data-stu-id="c46f4-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="c46f4-168">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="c46f4-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="c46f4-169">Selecteer **OK** in het bevestigingsvenster.</span><span class="sxs-lookup"><span data-stu-id="c46f4-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c46f4-170">De vijf CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="c46f4-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c46f4-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="c46f4-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="c46f4-p109">Ga via [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) naar de startpagina van Wix en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="c46f4-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c46f4-174">Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="c46f4-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c46f4-175">Selecteer in de rij **CNAME (Aliases)** van de DNS-editor **een koppeling toevoegen** voor elke CNAME-record.</span><span class="sxs-lookup"><span data-stu-id="c46f4-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="c46f4-176">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="c46f4-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c46f4-177">Host name</span><span class="sxs-lookup"><span data-stu-id="c46f4-177">Host Name</span></span> | <span data-ttu-id="c46f4-178">Verwijst naar</span><span class="sxs-lookup"><span data-stu-id="c46f4-178">Points to</span></span> | <span data-ttu-id="c46f4-179">TTL</span><span class="sxs-lookup"><span data-stu-id="c46f4-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="c46f4-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c46f4-180">autodiscover</span></span>  <br/> |<span data-ttu-id="c46f4-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c46f4-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="c46f4-182">1 uur</span><span class="sxs-lookup"><span data-stu-id="c46f4-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="c46f4-183">sip</span><span class="sxs-lookup"><span data-stu-id="c46f4-183">sip</span></span>  <br/> |<span data-ttu-id="c46f4-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c46f4-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c46f4-185">1 uur</span><span class="sxs-lookup"><span data-stu-id="c46f4-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="c46f4-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c46f4-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c46f4-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c46f4-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="c46f4-188">1 uur</span><span class="sxs-lookup"><span data-stu-id="c46f4-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="c46f4-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c46f4-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c46f4-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c46f4-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="c46f4-191">1 uur</span><span class="sxs-lookup"><span data-stu-id="c46f4-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="c46f4-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c46f4-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c46f4-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c46f4-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="c46f4-194">1 uur</span><span class="sxs-lookup"><span data-stu-id="c46f4-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="c46f4-195">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="c46f4-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c46f4-196">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="c46f4-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c46f4-197">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="c46f4-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c46f4-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="c46f4-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c46f4-199">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="c46f4-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c46f4-200">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="c46f4-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c46f4-201">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c46f4-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c46f4-202">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="c46f4-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="c46f4-203">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="c46f4-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c46f4-204">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="c46f4-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c46f4-205">Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="c46f4-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c46f4-206">Selecteer **+ een andere toevoegen** in de rij **txt (text)** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="c46f4-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c46f4-207">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="c46f4-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c46f4-208">Host name</span><span class="sxs-lookup"><span data-stu-id="c46f4-208">Host Name</span></span> | <span data-ttu-id="c46f4-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="c46f4-209">TXT Value</span></span> | <span data-ttu-id="c46f4-210">TTL</span><span class="sxs-lookup"><span data-stu-id="c46f4-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="c46f4-211">[laat dit leeg]</span><span class="sxs-lookup"><span data-stu-id="c46f4-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="c46f4-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c46f4-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c46f4-213">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="c46f4-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="c46f4-214">TXT</span><span class="sxs-lookup"><span data-stu-id="c46f4-214">TXT</span></span>  <br/> | <span data-ttu-id="c46f4-215">1 uur</span><span class="sxs-lookup"><span data-stu-id="c46f4-215">1 Hour</span></span> |
   
5. <span data-ttu-id="c46f4-216">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="c46f4-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c46f4-217">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="c46f4-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c46f4-218">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="c46f4-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c46f4-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="c46f4-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="c46f4-220">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="c46f4-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="c46f4-221">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="c46f4-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c46f4-222">Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="c46f4-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="c46f4-223">Selecteer **+ een andere toevoegen** in de rij **SRV** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="c46f4-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="c46f4-224">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="c46f4-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="c46f4-225">Service</span><span class="sxs-lookup"><span data-stu-id="c46f4-225">Service</span></span> | <span data-ttu-id="c46f4-226">Protocol</span><span class="sxs-lookup"><span data-stu-id="c46f4-226">Protocol</span></span> | <span data-ttu-id="c46f4-227">Naam</span><span class="sxs-lookup"><span data-stu-id="c46f4-227">Name</span></span> | <span data-ttu-id="c46f4-228">Dikte</span><span class="sxs-lookup"><span data-stu-id="c46f4-228">Weight</span></span> | <span data-ttu-id="c46f4-229">Poort</span><span class="sxs-lookup"><span data-stu-id="c46f4-229">Port</span></span> | <span data-ttu-id="c46f4-230">Doel</span><span class="sxs-lookup"><span data-stu-id="c46f4-230">Target</span></span> | <span data-ttu-id="c46f4-231">Priority</span><span class="sxs-lookup"><span data-stu-id="c46f4-231">Priority</span></span> | <span data-ttu-id="c46f4-232">TTL</span><span class="sxs-lookup"><span data-stu-id="c46f4-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="c46f4-233">sip</span><span class="sxs-lookup"><span data-stu-id="c46f4-233">sip</span></span>  |<span data-ttu-id="c46f4-234">tls</span><span class="sxs-lookup"><span data-stu-id="c46f4-234">tls</span></span>  |<span data-ttu-id="c46f4-235">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="c46f4-235">Automatically populated</span></span> |<span data-ttu-id="c46f4-236">1</span><span class="sxs-lookup"><span data-stu-id="c46f4-236">1</span></span>  |<span data-ttu-id="c46f4-237">443</span><span class="sxs-lookup"><span data-stu-id="c46f4-237">443</span></span>   |<span data-ttu-id="c46f4-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c46f4-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="c46f4-239">100</span><span class="sxs-lookup"><span data-stu-id="c46f4-239">100</span></span> |<span data-ttu-id="c46f4-240">1 uur</span><span class="sxs-lookup"><span data-stu-id="c46f4-240">1 Hour</span></span> |
   |<span data-ttu-id="c46f4-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="c46f4-241">sipfed</span></span>|<span data-ttu-id="c46f4-242">tcp</span><span class="sxs-lookup"><span data-stu-id="c46f4-242">tcp</span></span> |<span data-ttu-id="c46f4-243">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="c46f4-243">Automatically populated</span></span>|<span data-ttu-id="c46f4-244">1</span><span class="sxs-lookup"><span data-stu-id="c46f4-244">1</span></span> |<span data-ttu-id="c46f4-245">5061</span><span class="sxs-lookup"><span data-stu-id="c46f4-245">5061</span></span> |<span data-ttu-id="c46f4-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c46f4-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="c46f4-247">100</span><span class="sxs-lookup"><span data-stu-id="c46f4-247">100</span></span> | <span data-ttu-id="c46f4-248">1 uur</span><span class="sxs-lookup"><span data-stu-id="c46f4-248">1 Hour</span></span> |
   
5. <span data-ttu-id="c46f4-249">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="c46f4-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="c46f4-250">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="c46f4-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c46f4-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c46f4-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
