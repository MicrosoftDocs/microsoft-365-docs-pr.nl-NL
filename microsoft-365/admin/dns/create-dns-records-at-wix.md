---
title: DNS-records maken bij Wix voor Microsoft
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
description: Informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij Wix voor Microsoft.
ms.openlocfilehash: 3ec2ea0dc24e1872ba22e591fae96b39a9a0deee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916104"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="1606b-103">DNS-records maken bij Wix voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="1606b-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="1606b-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="1606b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1606b-105">Als Wix uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="1606b-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="1606b-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="1606b-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="1606b-107">[Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="1606b-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="1606b-108">[Voeg een MX-record toe, zodat e-mail](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)voor uw domein naar Microsoft komt.</span><span class="sxs-lookup"><span data-stu-id="1606b-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="1606b-109">[Voeg de vijf CNAME-records toe die vereist zijn voor Microsoft.](#add-the-five-cname-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="1606b-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="1606b-110">[Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="1606b-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="1606b-111">[Voeg de twee SRV-records toe die vereist zijn voor Microsoft.](#add-the-two-srv-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="1606b-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="1606b-112">Nadat u deze records bij Wix hebt toevoegen, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="1606b-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="1606b-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1606b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1606b-116">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="1606b-116">Add a TXT record for verification</span></span>
<span data-ttu-id="1606b-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="1606b-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="1606b-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="1606b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1606b-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1606b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="1606b-122">WIX biedt geen ondersteuning voor DNS-vermeldingen voor subdomeinen.</span><span class="sxs-lookup"><span data-stu-id="1606b-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="1606b-123">Als u wilt beginnen, gaat u via deze [koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)naar uw domeinenpagina bij Wix.</span><span class="sxs-lookup"><span data-stu-id="1606b-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="1606b-124">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1606b-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1606b-125">Selecteer op **de pagina** Mijn domeinen in het gebied **Geavanceerd** de knop **DNS** bewerken.</span><span class="sxs-lookup"><span data-stu-id="1606b-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="1606b-126">Selecteer **+ Voeg een andere optie** toe in de rij **TXT (Tekst)** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="1606b-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="1606b-127">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="1606b-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="1606b-128">Hostnaam</span><span class="sxs-lookup"><span data-stu-id="1606b-128">Host Name</span></span> <br/> | <span data-ttu-id="1606b-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="1606b-129">TXT Value</span></span> <br/> | <span data-ttu-id="1606b-130">TTL</span><span class="sxs-lookup"><span data-stu-id="1606b-130">TTL</span></span> <br/> |
   |<span data-ttu-id="1606b-131">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="1606b-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="1606b-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1606b-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1606b-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="1606b-133">**Note:** This is an example.</span></span> <span data-ttu-id="1606b-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="1606b-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="1606b-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="1606b-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="1606b-136">1 uur</span><span class="sxs-lookup"><span data-stu-id="1606b-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="1606b-137">Selecteer de **knop DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="1606b-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="1606b-138">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1606b-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1606b-139">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="1606b-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="1606b-140">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="1606b-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1606b-141">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="1606b-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="1606b-142">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="1606b-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="1606b-143">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="1606b-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="1606b-144">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="1606b-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1606b-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1606b-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1606b-148">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="1606b-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1606b-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="1606b-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="1606b-150">Als u wilt beginnen, gaat u via deze [koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)naar uw domeinenpagina bij Wix.</span><span class="sxs-lookup"><span data-stu-id="1606b-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="1606b-151">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1606b-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1606b-152">Selecteer op **de pagina** Mijn domeinen in het gebied **Postvakken** de koppeling **Uw MX-records configureren.**</span><span class="sxs-lookup"><span data-stu-id="1606b-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="1606b-153">Kies **Overige** in **de vervolgkeuzelijst** Van uw e-mailprovider.</span><span class="sxs-lookup"><span data-stu-id="1606b-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="1606b-154">Selecteer **+ Een andere toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1606b-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="1606b-155">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="1606b-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="1606b-156">Hostnaam</span><span class="sxs-lookup"><span data-stu-id="1606b-156">Host Name</span></span> | <span data-ttu-id="1606b-157">Wijst naar</span><span class="sxs-lookup"><span data-stu-id="1606b-157">Points to</span></span> | <span data-ttu-id="1606b-158">Priority</span><span class="sxs-lookup"><span data-stu-id="1606b-158">Priority</span></span> | <span data-ttu-id="1606b-159">TTL</span><span class="sxs-lookup"><span data-stu-id="1606b-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="1606b-160">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="1606b-160">Automatically populated</span></span> <br/> | <span data-ttu-id="1606b-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1606b-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1606b-162">**Opmerking:** Haal uw  *\<domain-key\>*  uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="1606b-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="1606b-163">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="1606b-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="1606b-164">0</span><span class="sxs-lookup"><span data-stu-id="1606b-164">0</span></span>  <br/> <span data-ttu-id="1606b-165">Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="1606b-165">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> | <span data-ttu-id="1606b-166">1 uur</span><span class="sxs-lookup"><span data-stu-id="1606b-166">1 Hour</span></span>|
   
6. <span data-ttu-id="1606b-167">Als er andere MX-records worden vermeld, verwijdert u elk van deze records.</span><span class="sxs-lookup"><span data-stu-id="1606b-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="1606b-168">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="1606b-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="1606b-169">Selecteer OK in het **bevestigingsdialoogvenster.**</span><span class="sxs-lookup"><span data-stu-id="1606b-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1606b-170">De vijf CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="1606b-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1606b-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="1606b-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="1606b-p109">Ga via [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) naar de startpagina van Wix en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="1606b-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="1606b-174">Selecteer op **de pagina** Mijn domeinen in het gebied **Geavanceerd** de knop **DNS** bewerken.</span><span class="sxs-lookup"><span data-stu-id="1606b-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="1606b-175">Selecteer **+ Voeg een andere optie** toe in de rij **CNAME (Aliases)** van de DNS-editor voor elke CNAME-record.</span><span class="sxs-lookup"><span data-stu-id="1606b-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="1606b-176">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="1606b-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="1606b-177">Hostnaam</span><span class="sxs-lookup"><span data-stu-id="1606b-177">Host Name</span></span> | <span data-ttu-id="1606b-178">Wijst naar</span><span class="sxs-lookup"><span data-stu-id="1606b-178">Points to</span></span> | <span data-ttu-id="1606b-179">TTL</span><span class="sxs-lookup"><span data-stu-id="1606b-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="1606b-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1606b-180">autodiscover</span></span>  <br/> |<span data-ttu-id="1606b-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1606b-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="1606b-182">1 uur</span><span class="sxs-lookup"><span data-stu-id="1606b-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="1606b-183">sip</span><span class="sxs-lookup"><span data-stu-id="1606b-183">sip</span></span>  <br/> |<span data-ttu-id="1606b-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1606b-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1606b-185">1 uur</span><span class="sxs-lookup"><span data-stu-id="1606b-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="1606b-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1606b-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1606b-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1606b-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="1606b-188">1 uur</span><span class="sxs-lookup"><span data-stu-id="1606b-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="1606b-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1606b-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1606b-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1606b-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="1606b-191">1 uur</span><span class="sxs-lookup"><span data-stu-id="1606b-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="1606b-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1606b-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1606b-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1606b-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="1606b-194">1 uur</span><span class="sxs-lookup"><span data-stu-id="1606b-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="1606b-195">Selecteer de **knop DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="1606b-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="1606b-196">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1606b-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1606b-197">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="1606b-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1606b-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="1606b-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1606b-199">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="1606b-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1606b-200">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="1606b-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1606b-201">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1606b-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1606b-202">Voeg in plaats daarvan de vereiste Microsoft-waarden  toe aan de huidige record, zodat u één SPF-record hebt met beide sets waarden.</span><span class="sxs-lookup"><span data-stu-id="1606b-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="1606b-203">Als u wilt beginnen, gaat u via deze [koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)naar uw domeinenpagina bij Wix.</span><span class="sxs-lookup"><span data-stu-id="1606b-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="1606b-204">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1606b-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1606b-205">Selecteer op **de pagina** Mijn domeinen in het gebied **Geavanceerd** de knop **DNS** bewerken.</span><span class="sxs-lookup"><span data-stu-id="1606b-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="1606b-206">Selecteer **+ Voeg een andere optie** toe in de rij **TXT (Tekst)** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="1606b-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="1606b-207">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="1606b-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="1606b-208">Hostnaam</span><span class="sxs-lookup"><span data-stu-id="1606b-208">Host Name</span></span> | <span data-ttu-id="1606b-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="1606b-209">TXT Value</span></span> | <span data-ttu-id="1606b-210">TTL</span><span class="sxs-lookup"><span data-stu-id="1606b-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="1606b-211">[laat dit leeg]</span><span class="sxs-lookup"><span data-stu-id="1606b-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="1606b-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1606b-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1606b-213">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="1606b-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="1606b-214">TXT</span><span class="sxs-lookup"><span data-stu-id="1606b-214">TXT</span></span>  <br/> | <span data-ttu-id="1606b-215">1 uur</span><span class="sxs-lookup"><span data-stu-id="1606b-215">1 Hour</span></span> |
   
5. <span data-ttu-id="1606b-216">Selecteer de **knop DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="1606b-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="1606b-217">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1606b-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1606b-218">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="1606b-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1606b-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="1606b-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="1606b-220">Als u wilt beginnen, gaat u via deze [koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)naar uw domeinenpagina bij Wix.</span><span class="sxs-lookup"><span data-stu-id="1606b-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="1606b-221">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1606b-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="1606b-222">Selecteer op **de pagina** Mijn domeinen in het gebied **Geavanceerd** de knop **DNS** bewerken.</span><span class="sxs-lookup"><span data-stu-id="1606b-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="1606b-223">Selecteer **+ Een andere optie** toevoegen in de rij **SRV** van de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="1606b-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="1606b-224">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:</span><span class="sxs-lookup"><span data-stu-id="1606b-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="1606b-225">Service</span><span class="sxs-lookup"><span data-stu-id="1606b-225">Service</span></span> | <span data-ttu-id="1606b-226">Protocol</span><span class="sxs-lookup"><span data-stu-id="1606b-226">Protocol</span></span> | <span data-ttu-id="1606b-227">Naam</span><span class="sxs-lookup"><span data-stu-id="1606b-227">Name</span></span> | <span data-ttu-id="1606b-228">Gewicht</span><span class="sxs-lookup"><span data-stu-id="1606b-228">Weight</span></span> | <span data-ttu-id="1606b-229">Poort</span><span class="sxs-lookup"><span data-stu-id="1606b-229">Port</span></span> | <span data-ttu-id="1606b-230">Doel</span><span class="sxs-lookup"><span data-stu-id="1606b-230">Target</span></span> | <span data-ttu-id="1606b-231">Priority</span><span class="sxs-lookup"><span data-stu-id="1606b-231">Priority</span></span> | <span data-ttu-id="1606b-232">TTL</span><span class="sxs-lookup"><span data-stu-id="1606b-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="1606b-233">sip</span><span class="sxs-lookup"><span data-stu-id="1606b-233">sip</span></span>  |<span data-ttu-id="1606b-234">tls</span><span class="sxs-lookup"><span data-stu-id="1606b-234">tls</span></span>  |<span data-ttu-id="1606b-235">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="1606b-235">Automatically populated</span></span> |<span data-ttu-id="1606b-236">1</span><span class="sxs-lookup"><span data-stu-id="1606b-236">1</span></span>  |<span data-ttu-id="1606b-237">443</span><span class="sxs-lookup"><span data-stu-id="1606b-237">443</span></span>   |<span data-ttu-id="1606b-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1606b-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="1606b-239">100</span><span class="sxs-lookup"><span data-stu-id="1606b-239">100</span></span> |<span data-ttu-id="1606b-240">1 uur</span><span class="sxs-lookup"><span data-stu-id="1606b-240">1 Hour</span></span> |
   |<span data-ttu-id="1606b-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="1606b-241">sipfed</span></span>|<span data-ttu-id="1606b-242">tcp</span><span class="sxs-lookup"><span data-stu-id="1606b-242">tcp</span></span> |<span data-ttu-id="1606b-243">Automatisch ingevuld</span><span class="sxs-lookup"><span data-stu-id="1606b-243">Automatically populated</span></span>|<span data-ttu-id="1606b-244">1</span><span class="sxs-lookup"><span data-stu-id="1606b-244">1</span></span> |<span data-ttu-id="1606b-245">5061</span><span class="sxs-lookup"><span data-stu-id="1606b-245">5061</span></span> |<span data-ttu-id="1606b-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1606b-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="1606b-247">100</span><span class="sxs-lookup"><span data-stu-id="1606b-247">100</span></span> | <span data-ttu-id="1606b-248">1 uur</span><span class="sxs-lookup"><span data-stu-id="1606b-248">1 Hour</span></span> |
   
5. <span data-ttu-id="1606b-249">Selecteer de **knop DNS opslaan** boven aan de DNS-editor.</span><span class="sxs-lookup"><span data-stu-id="1606b-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="1606b-250">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1606b-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1606b-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1606b-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
