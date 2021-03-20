---
title: DNS-records maken op web.com voor Microsoft
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services op web.com voor Microsoft.
ms.openlocfilehash: b667b2e69822fcd69babda7790a6468b640b073b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909980"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="4ced5-103">DNS-records maken op web.com voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="4ced5-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="4ced5-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="4ced5-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4ced5-105">Als web.com uw DNS-hostingprovider is, volgt u de stappen in dit artikel om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, en meer.</span><span class="sxs-lookup"><span data-stu-id="4ced5-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4ced5-106">Nadat u deze records hebt web.com, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="4ced5-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="4ced5-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4ced5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="4ced5-110">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="4ced5-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="4ced5-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="4ced5-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ced5-112">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="4ced5-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="4ced5-113">Wanneer u zich hebt aangemeld voor web.com, hebt u een domein toegevoegd met behulp van web.com **installatieproces.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="4ced5-114">Als u DNS-records voor uw domein in Microsoft wilt verifiëren en maken, moet u eerst de naamservers bij uw domeinregistrar wijzigen, zodat ze de naamservers van web.com gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4ced5-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="4ced5-115">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="4ced5-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="4ced5-116">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="4ced5-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="4ced5-117">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="4ced5-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="4ced5-118">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="4ced5-118">First nameserver</span></span>  <br/> |<span data-ttu-id="4ced5-119">Gebruik de naamserverwaarde die door de web.com.</span><span class="sxs-lookup"><span data-stu-id="4ced5-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="4ced5-120">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="4ced5-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="4ced5-121">Gebruik de naamserverwaarde die door de web.com.</span><span class="sxs-lookup"><span data-stu-id="4ced5-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="4ced5-122">U moet ten minste twee naamserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4ced5-122">You should use at least two name server records.</span></span> <span data-ttu-id="4ced5-123">Als er andere naamservers worden vermeld, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="4ced5-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="4ced5-124">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="4ced5-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4ced5-125">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4ced5-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="4ced5-126">Vervolgens zijn uw e-mail en andere services van Microsoft ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="4ced5-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4ced5-127">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="4ced5-127">Add a TXT record for verification</span></span>
<span data-ttu-id="4ced5-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4ced5-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4ced5-p104">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="4ced5-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ced5-p105">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="4ced5-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4ced5-133">Als u wilt beginnen, gaat u naar uw domeinenpagina op web.com via [deze koppeling.](https://checkout.web.com/manage-it/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="4ced5-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="4ced5-134">Meld u eerst aan.</span><span class="sxs-lookup"><span data-stu-id="4ced5-134">Log in first.</span></span>
  
2. <span data-ttu-id="4ced5-135">Selecteer op **de pagina Accountbeheer** de optie **Mijn domeinnamen.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="4ced5-136">Selecteer onder \*\*Manage \*my domain\*\*\*de optie **Geavanceerde DNS-records bewerken.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="4ced5-137">Klik op **de pagina Domeinnamen** onder Tekst **(TXT-records)** op **TXT-records bewerken** en selecteer vervolgens de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="4ced5-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="4ced5-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="4ced5-138">**Host**</span></span>|<span data-ttu-id="4ced5-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4ced5-139">**TTL**</span></span>|<span data-ttu-id="4ced5-140">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="4ced5-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="4ced5-141">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-141">3600</span></span>  <br/> |<span data-ttu-id="4ced5-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4ced5-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4ced5-143">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="4ced5-143">**Note:** This is an example.</span></span> <span data-ttu-id="4ced5-144">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="4ced5-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="4ced5-145">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="4ced5-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="4ced5-146">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="4ced5-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="4ced5-147">Wacht enkele minuten voordat u de nieuwe TXT-record verifieert, zodat de record die u zojuist hebt gemaakt, via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="4ced5-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4ced5-148">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="4ced5-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="4ced5-149">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="4ced5-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4ced5-150">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="4ced5-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4ced5-151">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="4ced5-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4ced5-152">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="4ced5-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4ced5-153">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="4ced5-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="4ced5-p108">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4ced5-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4ced5-157">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="4ced5-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4ced5-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4ced5-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4ced5-159">Als u wilt beginnen, gaat u naar uw domeinenpagina op web.com via [deze koppeling.](https://checkout.web.com/manage-it/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="4ced5-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="4ced5-160">Meld u eerst aan.</span><span class="sxs-lookup"><span data-stu-id="4ced5-160">Log in first.</span></span>
  
2. <span data-ttu-id="4ced5-161">Selecteer op **de pagina Accountbeheer** de optie **Mijn domeinnamen.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="4ced5-162">Selecteer onder \*\*Manage \*my domain\*\*\*de optie **Geavanceerde DNS-records bewerken.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="4ced5-163">Klik **onder Mail Servers (MX Records)** op **MX-records bewerken** en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="4ced5-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="4ced5-164">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4ced5-164">**Priority**</span></span>|<span data-ttu-id="4ced5-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4ced5-165">**TTL**</span></span>|<span data-ttu-id="4ced5-166">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="4ced5-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4ced5-167">1</span><span class="sxs-lookup"><span data-stu-id="4ced5-167">1</span></span>  <br/> <span data-ttu-id="4ced5-168">Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="4ced5-168">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="4ced5-169">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-169">3600</span></span>  <br/> |<span data-ttu-id="4ced5-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4ced5-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4ced5-171">**Opmerking:** Haal uw  *\<domain-key\>*  uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="4ced5-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="4ced5-172">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="4ced5-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="4ced5-173">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4ced5-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="4ced5-174">Als er andere MX-records worden weergegeven in de sectie **MX Records,** selecteert u het selectievakje naast de record onder Verwijderen **en** selecteert u **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="4ced5-175">Selecteer wijzigingen opslaan in het **bevestigingsscherm.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4ced5-176">De zes CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="4ced5-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="4ced5-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4ced5-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="4ced5-178">Als u wilt beginnen, gaat u naar uw domeinenpagina op web.com via [deze koppeling.](https://checkout.web.com/manage-it/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="4ced5-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="4ced5-179">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="4ced5-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="4ced5-180">Selecteer op **de pagina Accountbeheer** de optie **Mijn domeinnamen.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="4ced5-181">Selecteer onder \*\*Manage \*my domain\*\*\*de optie **Geavanceerde DNS-records bewerken.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="4ced5-182">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="4ced5-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="4ced5-183">Klik **onder Host Aliases (CNAME Records)** op **CNAME-records bewerken** en selecteer vervolgens de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="4ced5-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="4ced5-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="4ced5-184">**Alias**</span></span>|<span data-ttu-id="4ced5-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4ced5-185">**TTL**</span></span>|<span data-ttu-id="4ced5-186">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="4ced5-186">**Refers to Host Name**</span></span>|<span data-ttu-id="4ced5-187">**Andere host**</span><span class="sxs-lookup"><span data-stu-id="4ced5-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4ced5-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4ced5-188">autodiscover</span></span>  <br/> |<span data-ttu-id="4ced5-189">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-189">3600</span></span>  <br/> |<span data-ttu-id="4ced5-190">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="4ced5-190">@ (none)</span></span>  <br/> |<span data-ttu-id="4ced5-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4ced5-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="4ced5-192">sip</span><span class="sxs-lookup"><span data-stu-id="4ced5-192">sip</span></span>  <br/> |<span data-ttu-id="4ced5-193">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-193">3600</span></span>  <br/> |<span data-ttu-id="4ced5-194">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="4ced5-194">@ (none)</span></span>  <br/> |<span data-ttu-id="4ced5-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4ced5-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4ced5-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4ced5-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4ced5-197">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-197">3600</span></span>  <br/> |<span data-ttu-id="4ced5-198">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="4ced5-198">@ (none)</span></span>  <br/> | <span data-ttu-id="4ced5-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4ced5-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4ced5-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4ced5-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4ced5-201">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-201">3600</span></span>  <br/> |<span data-ttu-id="4ced5-202">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="4ced5-202">@ (none)</span></span>  <br/> |<span data-ttu-id="4ced5-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4ced5-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="4ced5-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4ced5-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4ced5-205">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-205">3600</span></span>  <br/> |<span data-ttu-id="4ced5-206">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="4ced5-206">@ (none)</span></span>  <br/> |<span data-ttu-id="4ced5-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4ced5-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="4ced5-208">msoid</span><span class="sxs-lookup"><span data-stu-id="4ced5-208">msoid</span></span>  <br/> |<span data-ttu-id="4ced5-209">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-209">3600</span></span>  <br/> |<span data-ttu-id="4ced5-210">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="4ced5-210">@ (none)</span></span>  <br/> |<span data-ttu-id="4ced5-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="4ced5-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="4ced5-212">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="4ced5-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="4ced5-213">Voeg als volgt de andere vijf CNAME-records toe:</span><span class="sxs-lookup"><span data-stu-id="4ced5-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4ced5-214">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="4ced5-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4ced5-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4ced5-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ced5-216">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="4ced5-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4ced5-217">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="4ced5-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4ced5-218">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ced5-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="4ced5-219">Voeg in plaats daarvan de vereiste Microsoft-waarden  toe aan de huidige record, zodat u één SPF-record hebt met beide sets waarden.</span><span class="sxs-lookup"><span data-stu-id="4ced5-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="4ced5-220">Als u wilt beginnen, gaat u naar uw domeinenpagina op web.com via [deze koppeling.](https://checkout.web.com/manage-it/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="4ced5-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="4ced5-221">Meld u eerst aan.</span><span class="sxs-lookup"><span data-stu-id="4ced5-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="4ced5-222">Selecteer op **de pagina Accountbeheer** de optie **Mijn domeinnamen.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="4ced5-223">Selecteer onder \*\*Manage \*my domain\*\*\*de optie **Geavanceerde DNS-records bewerken.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="4ced5-224">Klik op **de pagina Domeinnamen** onder Tekst **(TXT-records)** op **TXT-records bewerken** en selecteer vervolgens de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="4ced5-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="4ced5-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="4ced5-225">**Host**</span></span>|<span data-ttu-id="4ced5-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4ced5-226">**TTL**</span></span>|<span data-ttu-id="4ced5-227">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="4ced5-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="4ced5-228">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-228">3600</span></span>  <br/> |<span data-ttu-id="4ced5-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4ced5-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4ced5-230">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="4ced5-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="4ced5-231">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="4ced5-231">Select **Continue**.</span></span>

6. <span data-ttu-id="4ced5-232">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4ced5-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4ced5-233">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="4ced5-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4ced5-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4ced5-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ced5-235">Houd er rekening mee dat web.com verantwoordelijk is voor het beschikbaar maken van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="4ced5-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="4ced5-236">Als u verschillen ziet tussen de onderstaande stappen en de huidige web.com GUI(Grafische gebruikersinterface), gebruikt u de [web.com Community.](https://community.web.com.com/)</span><span class="sxs-lookup"><span data-stu-id="4ced5-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="4ced5-237">Als u wilt beginnen, gaat u naar uw domeinenpagina op web.com via [deze koppeling.](https://checkout.web.com/manage-it/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="4ced5-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="4ced5-238">Meld u eerst aan.</span><span class="sxs-lookup"><span data-stu-id="4ced5-238">Log in first.</span></span>
      
2. <span data-ttu-id="4ced5-239">Selecteer op **de pagina Accountbeheer** de optie **Mijn domeinnamen.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="4ced5-240">Selecteer onder \*\*Manage \*my domain\*\*\*de optie **Geavanceerde DNS-records bewerken.**</span><span class="sxs-lookup"><span data-stu-id="4ced5-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="4ced5-241">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="4ced5-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="4ced5-242">Klik **onder Service (SRV Records)** op **SRV-records bewerken** en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="4ced5-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="4ced5-243">**Service**</span><span class="sxs-lookup"><span data-stu-id="4ced5-243">**Service**</span></span>|<span data-ttu-id="4ced5-244">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="4ced5-244">**Protocol**</span></span>|<span data-ttu-id="4ced5-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4ced5-245">**TTL**</span></span>|<span data-ttu-id="4ced5-246">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="4ced5-246">**Priority**</span></span>|<span data-ttu-id="4ced5-247">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="4ced5-247">**Weight**</span></span>|<span data-ttu-id="4ced5-248">**Poort**</span><span class="sxs-lookup"><span data-stu-id="4ced5-248">**Port**</span></span>|<span data-ttu-id="4ced5-249">**Target**</span><span class="sxs-lookup"><span data-stu-id="4ced5-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4ced5-250">_sip</span><span class="sxs-lookup"><span data-stu-id="4ced5-250">_sip</span></span> |<span data-ttu-id="4ced5-251">_tls</span><span class="sxs-lookup"><span data-stu-id="4ced5-251">_tls</span></span> |<span data-ttu-id="4ced5-252">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-252">3600</span></span> | <span data-ttu-id="4ced5-253">100</span><span class="sxs-lookup"><span data-stu-id="4ced5-253">100</span></span>|<span data-ttu-id="4ced5-254">1</span><span class="sxs-lookup"><span data-stu-id="4ced5-254">1</span></span> |<span data-ttu-id="4ced5-255">443</span><span class="sxs-lookup"><span data-stu-id="4ced5-255">443</span></span> |<span data-ttu-id="4ced5-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4ced5-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="4ced5-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="4ced5-257">_sipfederationtls</span></span> |<span data-ttu-id="4ced5-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="4ced5-258">_tcp</span></span> |<span data-ttu-id="4ced5-259">3600</span><span class="sxs-lookup"><span data-stu-id="4ced5-259">3600</span></span> |<span data-ttu-id="4ced5-260">100</span><span class="sxs-lookup"><span data-stu-id="4ced5-260">100</span></span> |<span data-ttu-id="4ced5-261">1</span><span class="sxs-lookup"><span data-stu-id="4ced5-261">1</span></span> |<span data-ttu-id="4ced5-262">5061</span><span class="sxs-lookup"><span data-stu-id="4ced5-262">5061</span></span> | <span data-ttu-id="4ced5-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4ced5-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="4ced5-264">Voeg de andere SRV-record toe door de waarden uit de tweede rij van de tabel te kiezen.</span><span class="sxs-lookup"><span data-stu-id="4ced5-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="4ced5-265">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="4ced5-265">Select **Continue**.</span></span>

7. <span data-ttu-id="4ced5-266">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4ced5-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="4ced5-p116">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4ced5-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
