---
title: DNS-records maken bij Wix voor Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Wix voor Microsoft.
ms.openlocfilehash: 6f88cc65ae19f747a9fc3740ea1578f30d18b5e2
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048853"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="22be6-103">DNS-records maken bij Wix voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="22be6-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="22be6-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="22be6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="22be6-105">Als Wix uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="22be6-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="22be6-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="22be6-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="22be6-107">[Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="22be6-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="22be6-108">[Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="22be6-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="22be6-109">[Voeg de vijf CNAME-records toe die nodig zijn voor Microsoft.](#add-the-five-cname-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="22be6-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="22be6-110">[Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="22be6-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="22be6-111">[Voeg de twee SRV-records toe die nodig zijn voor Microsoft.](#add-the-two-srv-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="22be6-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="22be6-112">Nadat u deze records bij Wix hebt toegevoegd, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="22be6-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="22be6-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="22be6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="22be6-116">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="22be6-116">Add a TXT record for verification</span></span>
<span data-ttu-id="22be6-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="22be6-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="22be6-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="22be6-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="22be6-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="22be6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="22be6-122">Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="22be6-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="22be6-123">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="22be6-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="22be6-124">Selecteer op de pagina **Mijn domeinen** in het gebied **Geavanceerd** de knop **DNS bewerken.**</span><span class="sxs-lookup"><span data-stu-id="22be6-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="22be6-125">Selecteer **+ Voeg een andere toe** in de rij **TXT (Text)** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="22be6-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="22be6-126">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="22be6-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="22be6-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="22be6-127">**Host Name**</span></span> <br/> |<span data-ttu-id="22be6-128">**TXT-waarde**</span><span class="sxs-lookup"><span data-stu-id="22be6-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="22be6-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="22be6-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="22be6-130">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="22be6-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="22be6-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="22be6-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="22be6-132">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="22be6-132">**Note:** This is an example.</span></span> <span data-ttu-id="22be6-133">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="22be6-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="22be6-134">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="22be6-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="22be6-135">1 uur</span><span class="sxs-lookup"><span data-stu-id="22be6-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="22be6-136">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="22be6-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="22be6-137">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="22be6-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="22be6-138">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="22be6-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="22be6-139">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="22be6-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="22be6-140">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="22be6-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="22be6-141">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="22be6-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="22be6-142">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="22be6-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="22be6-143">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="22be6-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="22be6-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="22be6-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="22be6-147">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="22be6-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="22be6-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="22be6-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="22be6-149">Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="22be6-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="22be6-150">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="22be6-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="22be6-151">Selecteer **op** de pagina Mijn domeinen in het gebied **Postvakken** de koppeling **Uw MX-records configureren.**</span><span class="sxs-lookup"><span data-stu-id="22be6-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="22be6-152">Kies **Andere** in de vervolgkeuzelijst **Uw e-mailprovider.**</span><span class="sxs-lookup"><span data-stu-id="22be6-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="22be6-153">Selecteer **+ Voeg er nog een toe**.</span><span class="sxs-lookup"><span data-stu-id="22be6-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="22be6-154">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="22be6-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="22be6-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="22be6-155">**Host Name**</span></span>|<span data-ttu-id="22be6-156">**Points to**</span><span class="sxs-lookup"><span data-stu-id="22be6-156">**Points to**</span></span>|<span data-ttu-id="22be6-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="22be6-157">**Priority**</span></span>|<span data-ttu-id="22be6-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="22be6-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="22be6-159">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="22be6-159">Automatically populated</span></span> <br/> | <span data-ttu-id="22be6-160">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="22be6-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="22be6-161">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="22be6-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="22be6-162">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="22be6-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="22be6-163">0</span><span class="sxs-lookup"><span data-stu-id="22be6-163">0</span></span>  <br/> <span data-ttu-id="22be6-164">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="22be6-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="22be6-165">1 uur</span><span class="sxs-lookup"><span data-stu-id="22be6-165">1 Hour</span></span>|
   
6. <span data-ttu-id="22be6-166">Als er andere MX-records worden vermeld, verwijdert u elk van deze records.</span><span class="sxs-lookup"><span data-stu-id="22be6-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="22be6-167">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="22be6-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="22be6-168">Selecteer **OK**in het bevestigingsdialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="22be6-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="22be6-169">Voeg de vijf CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="22be6-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="22be6-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="22be6-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="22be6-p109">Ga via [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) naar de startpagina van Wix en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="22be6-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="22be6-173">Selecteer op de pagina **Mijn domeinen** in het gebied **Geavanceerd** de knop **DNS bewerken.**</span><span class="sxs-lookup"><span data-stu-id="22be6-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="22be6-174">Selecteer **+ Voeg een andere toe** in de rij **CNAME (Aliassen)** van de DNS-editor voor elke CNAME-record.</span><span class="sxs-lookup"><span data-stu-id="22be6-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="22be6-175">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="22be6-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="22be6-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="22be6-176">**Host Name**</span></span>|<span data-ttu-id="22be6-177">**Verwijst naar**</span><span class="sxs-lookup"><span data-stu-id="22be6-177">**Points to**</span></span>|<span data-ttu-id="22be6-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="22be6-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22be6-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="22be6-179">autodiscover</span></span>  <br/> |<span data-ttu-id="22be6-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="22be6-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="22be6-181">1 uur</span><span class="sxs-lookup"><span data-stu-id="22be6-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="22be6-182">sip</span><span class="sxs-lookup"><span data-stu-id="22be6-182">sip</span></span>  <br/> |<span data-ttu-id="22be6-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="22be6-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="22be6-184">1 uur</span><span class="sxs-lookup"><span data-stu-id="22be6-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="22be6-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="22be6-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="22be6-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="22be6-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="22be6-187">1 uur</span><span class="sxs-lookup"><span data-stu-id="22be6-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="22be6-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="22be6-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="22be6-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="22be6-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="22be6-190">1 uur</span><span class="sxs-lookup"><span data-stu-id="22be6-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="22be6-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="22be6-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="22be6-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="22be6-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="22be6-193">1 uur</span><span class="sxs-lookup"><span data-stu-id="22be6-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="22be6-194">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="22be6-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="22be6-195">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="22be6-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="22be6-196">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="22be6-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="22be6-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="22be6-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="22be6-198">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="22be6-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="22be6-199">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="22be6-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="22be6-200">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="22be6-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="22be6-201">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="22be6-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="22be6-202">Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="22be6-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="22be6-203">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="22be6-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="22be6-204">Selecteer op de pagina **Mijn domeinen** in het gebied **Geavanceerd** de knop **DNS bewerken.**</span><span class="sxs-lookup"><span data-stu-id="22be6-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="22be6-205">Selecteer **+ Voeg een andere toe** in de rij **TXT (Text)** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="22be6-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="22be6-206">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="22be6-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="22be6-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="22be6-207">**Host Name**</span></span>|<span data-ttu-id="22be6-208">**TXT-waarde**</span><span class="sxs-lookup"><span data-stu-id="22be6-208">**TXT Value**</span></span>|<span data-ttu-id="22be6-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="22be6-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22be6-210">[Laat dit leeg]</span><span class="sxs-lookup"><span data-stu-id="22be6-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="22be6-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="22be6-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="22be6-212">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="22be6-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="22be6-213">TXT</span><span class="sxs-lookup"><span data-stu-id="22be6-213">TXT</span></span>  <br/> | <span data-ttu-id="22be6-214">1 uur</span><span class="sxs-lookup"><span data-stu-id="22be6-214">1 Hour</span></span> |
   
5. <span data-ttu-id="22be6-215">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="22be6-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="22be6-216">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="22be6-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="22be6-217">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="22be6-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="22be6-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="22be6-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="22be6-219">Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="22be6-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="22be6-220">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="22be6-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="22be6-221">Selecteer op de pagina **Mijn domeinen** in het gebied **Geavanceerd** de knop **DNS bewerken.**</span><span class="sxs-lookup"><span data-stu-id="22be6-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="22be6-222">Selecteer **+ Voeg een andere toe** in de rij **SRV** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="22be6-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="22be6-223">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="22be6-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="22be6-224">**Service**</span><span class="sxs-lookup"><span data-stu-id="22be6-224">**Service**</span></span>|<span data-ttu-id="22be6-225">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="22be6-225">**Protocol**</span></span>|<span data-ttu-id="22be6-226">**Naam**</span><span class="sxs-lookup"><span data-stu-id="22be6-226">**Name**</span></span>|<span data-ttu-id="22be6-227">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="22be6-227">**Weight**</span></span>|<span data-ttu-id="22be6-228">**Poort**</span><span class="sxs-lookup"><span data-stu-id="22be6-228">**Port**</span></span>|<span data-ttu-id="22be6-229">**Doel**</span><span class="sxs-lookup"><span data-stu-id="22be6-229">**Target**</span></span>|<span data-ttu-id="22be6-230">**Priority**</span><span class="sxs-lookup"><span data-stu-id="22be6-230">**Priority**</span></span>|<span data-ttu-id="22be6-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="22be6-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="22be6-232">sip</span><span class="sxs-lookup"><span data-stu-id="22be6-232">sip</span></span>  |<span data-ttu-id="22be6-233">tls</span><span class="sxs-lookup"><span data-stu-id="22be6-233">tls</span></span>  |<span data-ttu-id="22be6-234">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="22be6-234">Automatically populated</span></span> |<span data-ttu-id="22be6-235">1</span><span class="sxs-lookup"><span data-stu-id="22be6-235">1</span></span>  |<span data-ttu-id="22be6-236">443</span><span class="sxs-lookup"><span data-stu-id="22be6-236">443</span></span>   |<span data-ttu-id="22be6-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="22be6-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="22be6-238">100</span><span class="sxs-lookup"><span data-stu-id="22be6-238">100</span></span> |<span data-ttu-id="22be6-239">1 uur</span><span class="sxs-lookup"><span data-stu-id="22be6-239">1 Hour</span></span> |
|<span data-ttu-id="22be6-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="22be6-240">sipfed</span></span>|<span data-ttu-id="22be6-241">tcp</span><span class="sxs-lookup"><span data-stu-id="22be6-241">tcp</span></span> |<span data-ttu-id="22be6-242">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="22be6-242">Automatically populated</span></span>|<span data-ttu-id="22be6-243">1</span><span class="sxs-lookup"><span data-stu-id="22be6-243">1</span></span> |<span data-ttu-id="22be6-244">5061</span><span class="sxs-lookup"><span data-stu-id="22be6-244">5061</span></span> |<span data-ttu-id="22be6-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="22be6-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="22be6-246">100</span><span class="sxs-lookup"><span data-stu-id="22be6-246">100</span></span> | <span data-ttu-id="22be6-247">1 uur</span><span class="sxs-lookup"><span data-stu-id="22be6-247">1 Hour</span></span> |
   
5. <span data-ttu-id="22be6-248">Selecteer de knop **DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="22be6-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="22be6-249">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="22be6-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="22be6-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="22be6-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

