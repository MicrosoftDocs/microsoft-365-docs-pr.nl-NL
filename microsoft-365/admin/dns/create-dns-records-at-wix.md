---
title: DNS-records bij Wix maken voor Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Wix voor Microsoft.
ms.openlocfilehash: fcc0f8e8187e22dde68149e0f2a80073312bff7f
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814442"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="974f7-103">DNS-records bij Wix maken voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="974f7-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="974f7-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="974f7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="974f7-105">Als Wix uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="974f7-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="974f7-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="974f7-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="974f7-107">[Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="974f7-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="974f7-108">[Voeg een MX-record toe zodat e-mail voor uw domein bij Microsoft komt](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="974f7-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="974f7-109">[Voeg de vijf CNAME-records toe die voor Microsoft vereist zijn](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="974f7-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="974f7-110">[Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="974f7-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="974f7-111">[Voeg de twee SRV-records toe die voor Microsoft vereist zijn](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="974f7-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="974f7-112">Nadat u deze records bij Wix hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="974f7-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="974f7-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="974f7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="974f7-116">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="974f7-116">Add a TXT record for verification</span></span>
<span data-ttu-id="974f7-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="974f7-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="974f7-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="974f7-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="974f7-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="974f7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="974f7-122">WIX biedt geen ondersteuning voor DNS-vermeldingen voor subdomeinen.</span><span class="sxs-lookup"><span data-stu-id="974f7-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="974f7-123">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="974f7-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="974f7-124">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="974f7-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="974f7-125">Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="974f7-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="974f7-126">Selecteer **+ een andere toevoegen** in de rij **txt (text)** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="974f7-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="974f7-127">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="974f7-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="974f7-128">Host name</span><span class="sxs-lookup"><span data-stu-id="974f7-128">Host Name</span></span> <br/> | <span data-ttu-id="974f7-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="974f7-129">TXT Value</span></span> <br/> | <span data-ttu-id="974f7-130">TTL</span><span class="sxs-lookup"><span data-stu-id="974f7-130">TTL</span></span> <br/> |
   |<span data-ttu-id="974f7-131">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="974f7-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="974f7-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="974f7-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="974f7-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="974f7-133">**Note:** This is an example.</span></span> <span data-ttu-id="974f7-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="974f7-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="974f7-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="974f7-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="974f7-136">1 uur</span><span class="sxs-lookup"><span data-stu-id="974f7-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="974f7-137">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="974f7-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="974f7-138">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="974f7-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="974f7-139">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="974f7-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="974f7-140">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="974f7-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="974f7-141">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="974f7-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="974f7-142">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="974f7-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="974f7-143">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="974f7-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="974f7-144">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="974f7-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="974f7-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="974f7-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="974f7-148">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="974f7-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="974f7-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="974f7-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="974f7-150">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="974f7-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="974f7-151">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="974f7-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="974f7-152">Selecteer op de pagina **My Domains** in het gebied **postvakken** de koppeling **uw MX records configureren** .</span><span class="sxs-lookup"><span data-stu-id="974f7-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="974f7-153">Kies in de vervolgkeuzelijst **uw e-mail provider** de optie **Overige** .</span><span class="sxs-lookup"><span data-stu-id="974f7-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="974f7-154">Selecteer **+ een andere toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="974f7-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="974f7-155">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="974f7-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="974f7-156">Host name</span><span class="sxs-lookup"><span data-stu-id="974f7-156">Host Name</span></span> | <span data-ttu-id="974f7-157">Verwijst naar</span><span class="sxs-lookup"><span data-stu-id="974f7-157">Points to</span></span> | <span data-ttu-id="974f7-158">Priority</span><span class="sxs-lookup"><span data-stu-id="974f7-158">Priority</span></span> | <span data-ttu-id="974f7-159">TTL</span><span class="sxs-lookup"><span data-stu-id="974f7-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="974f7-160">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="974f7-160">Automatically populated</span></span> <br/> | <span data-ttu-id="974f7-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="974f7-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="974f7-162">**Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="974f7-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="974f7-163">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="974f7-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="974f7-164">0</span><span class="sxs-lookup"><span data-stu-id="974f7-164">0</span></span>  <br/> <span data-ttu-id="974f7-165">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="974f7-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="974f7-166">1 uur</span><span class="sxs-lookup"><span data-stu-id="974f7-166">1 Hour</span></span>|
   
6. <span data-ttu-id="974f7-167">Als er andere MX-records worden vermeld, verwijdert u elke record.</span><span class="sxs-lookup"><span data-stu-id="974f7-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="974f7-168">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="974f7-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="974f7-169">Selecteer **OK**in het bevestigingsvenster.</span><span class="sxs-lookup"><span data-stu-id="974f7-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="974f7-170">De vijf CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="974f7-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="974f7-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="974f7-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="974f7-p109">Ga via [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) naar de startpagina van Wix en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="974f7-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="974f7-174">Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="974f7-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="974f7-175">Selecteer in de rij **CNAME (Aliases)** van de DNS-editor **een koppeling toevoegen** voor elke CNAME-record.</span><span class="sxs-lookup"><span data-stu-id="974f7-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="974f7-176">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="974f7-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="974f7-177">Host name</span><span class="sxs-lookup"><span data-stu-id="974f7-177">Host Name</span></span> | <span data-ttu-id="974f7-178">Verwijst naar</span><span class="sxs-lookup"><span data-stu-id="974f7-178">Points to</span></span> | <span data-ttu-id="974f7-179">TTL</span><span class="sxs-lookup"><span data-stu-id="974f7-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="974f7-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="974f7-180">autodiscover</span></span>  <br/> |<span data-ttu-id="974f7-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="974f7-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="974f7-182">1 uur</span><span class="sxs-lookup"><span data-stu-id="974f7-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="974f7-183">sip</span><span class="sxs-lookup"><span data-stu-id="974f7-183">sip</span></span>  <br/> |<span data-ttu-id="974f7-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="974f7-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="974f7-185">1 uur</span><span class="sxs-lookup"><span data-stu-id="974f7-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="974f7-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="974f7-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="974f7-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="974f7-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="974f7-188">1 uur</span><span class="sxs-lookup"><span data-stu-id="974f7-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="974f7-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="974f7-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="974f7-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="974f7-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="974f7-191">1 uur</span><span class="sxs-lookup"><span data-stu-id="974f7-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="974f7-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="974f7-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="974f7-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="974f7-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="974f7-194">1 uur</span><span class="sxs-lookup"><span data-stu-id="974f7-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="974f7-195">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="974f7-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="974f7-196">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="974f7-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="974f7-197">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="974f7-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="974f7-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="974f7-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="974f7-199">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="974f7-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="974f7-200">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="974f7-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="974f7-201">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="974f7-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="974f7-202">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="974f7-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="974f7-203">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="974f7-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="974f7-204">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="974f7-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="974f7-205">Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="974f7-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="974f7-206">Selecteer **+ een andere toevoegen** in de rij **txt (text)** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="974f7-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="974f7-207">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="974f7-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="974f7-208">Host name</span><span class="sxs-lookup"><span data-stu-id="974f7-208">Host Name</span></span> | <span data-ttu-id="974f7-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="974f7-209">TXT Value</span></span> | <span data-ttu-id="974f7-210">TTL</span><span class="sxs-lookup"><span data-stu-id="974f7-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="974f7-211">[laat dit leeg]</span><span class="sxs-lookup"><span data-stu-id="974f7-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="974f7-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="974f7-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="974f7-213">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="974f7-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="974f7-214">TXT</span><span class="sxs-lookup"><span data-stu-id="974f7-214">TXT</span></span>  <br/> | <span data-ttu-id="974f7-215">1 uur</span><span class="sxs-lookup"><span data-stu-id="974f7-215">1 Hour</span></span> |
   
5. <span data-ttu-id="974f7-216">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="974f7-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="974f7-217">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="974f7-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="974f7-218">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="974f7-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="974f7-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="974f7-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="974f7-220">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="974f7-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="974f7-221">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="974f7-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="974f7-222">Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** .</span><span class="sxs-lookup"><span data-stu-id="974f7-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="974f7-223">Selecteer **+ een andere toevoegen** in de rij **SRV** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="974f7-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="974f7-224">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="974f7-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="974f7-225">Service</span><span class="sxs-lookup"><span data-stu-id="974f7-225">Service</span></span> | <span data-ttu-id="974f7-226">Protocol</span><span class="sxs-lookup"><span data-stu-id="974f7-226">Protocol</span></span> | <span data-ttu-id="974f7-227">Naam</span><span class="sxs-lookup"><span data-stu-id="974f7-227">Name</span></span> | <span data-ttu-id="974f7-228">Dikte</span><span class="sxs-lookup"><span data-stu-id="974f7-228">Weight</span></span> | <span data-ttu-id="974f7-229">Poort</span><span class="sxs-lookup"><span data-stu-id="974f7-229">Port</span></span> | <span data-ttu-id="974f7-230">Doel</span><span class="sxs-lookup"><span data-stu-id="974f7-230">Target</span></span> | <span data-ttu-id="974f7-231">Priority</span><span class="sxs-lookup"><span data-stu-id="974f7-231">Priority</span></span> | <span data-ttu-id="974f7-232">TTL</span><span class="sxs-lookup"><span data-stu-id="974f7-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="974f7-233">sip</span><span class="sxs-lookup"><span data-stu-id="974f7-233">sip</span></span>  |<span data-ttu-id="974f7-234">tls</span><span class="sxs-lookup"><span data-stu-id="974f7-234">tls</span></span>  |<span data-ttu-id="974f7-235">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="974f7-235">Automatically populated</span></span> |<span data-ttu-id="974f7-236">1</span><span class="sxs-lookup"><span data-stu-id="974f7-236">1</span></span>  |<span data-ttu-id="974f7-237">443</span><span class="sxs-lookup"><span data-stu-id="974f7-237">443</span></span>   |<span data-ttu-id="974f7-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="974f7-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="974f7-239">100</span><span class="sxs-lookup"><span data-stu-id="974f7-239">100</span></span> |<span data-ttu-id="974f7-240">1 uur</span><span class="sxs-lookup"><span data-stu-id="974f7-240">1 Hour</span></span> |
   |<span data-ttu-id="974f7-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="974f7-241">sipfed</span></span>|<span data-ttu-id="974f7-242">tcp</span><span class="sxs-lookup"><span data-stu-id="974f7-242">tcp</span></span> |<span data-ttu-id="974f7-243">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="974f7-243">Automatically populated</span></span>|<span data-ttu-id="974f7-244">1</span><span class="sxs-lookup"><span data-stu-id="974f7-244">1</span></span> |<span data-ttu-id="974f7-245">5061</span><span class="sxs-lookup"><span data-stu-id="974f7-245">5061</span></span> |<span data-ttu-id="974f7-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="974f7-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="974f7-247">100</span><span class="sxs-lookup"><span data-stu-id="974f7-247">100</span></span> | <span data-ttu-id="974f7-248">1 uur</span><span class="sxs-lookup"><span data-stu-id="974f7-248">1 Hour</span></span> |
   
5. <span data-ttu-id="974f7-249">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="974f7-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="974f7-250">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="974f7-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="974f7-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="974f7-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
