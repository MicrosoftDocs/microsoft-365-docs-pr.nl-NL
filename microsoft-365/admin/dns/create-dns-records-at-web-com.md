---
title: DNS-records bij web.com maken voor Microsoft
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
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op web.com voor Microsoft.
ms.openlocfilehash: 25df88e05e96e2394628bf89c8cc07af2d0eac1e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645753"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="73c87-103">DNS-records bij web.com maken voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="73c87-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="73c87-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="73c87-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="73c87-105">Als web.com uw DNS-hosting provider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor bedrijven online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="73c87-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="73c87-106">Nadat u deze records bij web.com hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="73c87-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="73c87-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="73c87-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="73c87-110">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="73c87-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="73c87-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="73c87-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="73c87-112">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="73c87-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="73c87-113">Toen u zich registreerde voor web.com, hebt u een domein toegevoegd door middel van het **installatie** proces van web.com.</span><span class="sxs-lookup"><span data-stu-id="73c87-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="73c87-114">Als u DNS-records voor uw domein wilt controleren en maken in Microsoft, moet u eerst de naamservers van uw domeinregistratie wijzigen, zodat ze de naamservers van web. com gebruiken.</span><span class="sxs-lookup"><span data-stu-id="73c87-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="73c87-115">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="73c87-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="73c87-116">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="73c87-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="73c87-117">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="73c87-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="73c87-118">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="73c87-118">First nameserver</span></span>  <br/> |<span data-ttu-id="73c87-119">Gebruik de naamserver-waarde van web.com.</span><span class="sxs-lookup"><span data-stu-id="73c87-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="73c87-120">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="73c87-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="73c87-121">Gebruik de naamserver-waarde van web.com.</span><span class="sxs-lookup"><span data-stu-id="73c87-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="73c87-122">U dient ten minste twee naamserver records te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="73c87-122">You should use at least two name server records.</span></span> <span data-ttu-id="73c87-123">Als er andere naamservers worden weergegeven, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="73c87-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="73c87-124">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="73c87-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="73c87-125">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="73c87-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="73c87-126">Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="73c87-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="73c87-127">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="73c87-127">Add a TXT record for verification</span></span>
<span data-ttu-id="73c87-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="73c87-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="73c87-p104">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="73c87-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="73c87-p105">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="73c87-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="73c87-133">Als u wilt beginnen, gaat u naar uw domeinen pagina bij web.com met behulp van [deze koppeling](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="73c87-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="73c87-134">Meld u eerst aan.</span><span class="sxs-lookup"><span data-stu-id="73c87-134">Log in first.</span></span>
  
2. <span data-ttu-id="73c87-135">Selecteer op de pagina **account beheer** de optie **mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="73c87-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="73c87-136">Selecteer onder \* \* beheren \* mijn domein \* \* \* de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="73c87-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="73c87-137">Klik op de pagina **Domain names** onder **Text (TXT records)** op **Edit TXT records**en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="73c87-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="73c87-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="73c87-138">**Host**</span></span>|<span data-ttu-id="73c87-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="73c87-139">**TTL**</span></span>|<span data-ttu-id="73c87-140">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="73c87-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="73c87-141">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-141">3600</span></span>  <br/> |<span data-ttu-id="73c87-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="73c87-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="73c87-143">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="73c87-143">**Note:** This is an example.</span></span> <span data-ttu-id="73c87-144">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="73c87-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="73c87-145">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="73c87-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="73c87-146">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="73c87-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="73c87-147">Wacht een paar minuten voordat u de nieuwe TXT-record verifieert, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="73c87-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="73c87-148">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="73c87-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="73c87-149">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="73c87-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="73c87-150">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="73c87-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="73c87-151">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="73c87-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="73c87-152">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="73c87-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="73c87-153">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="73c87-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="73c87-p108">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="73c87-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="73c87-157">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="73c87-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="73c87-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="73c87-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="73c87-159">Als u wilt beginnen, gaat u naar uw domeinen pagina bij web.com met behulp van [deze koppeling](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="73c87-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="73c87-160">Meld u eerst aan.</span><span class="sxs-lookup"><span data-stu-id="73c87-160">Log in first.</span></span>
  
2. <span data-ttu-id="73c87-161">Selecteer op de pagina **account beheer** de optie **mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="73c87-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="73c87-162">Selecteer onder \* \* beheren \* mijn domein \* \* \* de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="73c87-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="73c87-163">Klik onder **e-mail servers (MX records)** op **Edit MX records**en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="73c87-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="73c87-164">**Priority**</span><span class="sxs-lookup"><span data-stu-id="73c87-164">**Priority**</span></span>|<span data-ttu-id="73c87-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="73c87-165">**TTL**</span></span>|<span data-ttu-id="73c87-166">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="73c87-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="73c87-167">1</span><span class="sxs-lookup"><span data-stu-id="73c87-167">1</span></span>  <br/> <span data-ttu-id="73c87-168">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="73c87-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="73c87-169">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-169">3600</span></span>  <br/> |<span data-ttu-id="73c87-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="73c87-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="73c87-171">**Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="73c87-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="73c87-172">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="73c87-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="73c87-173">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="73c87-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="73c87-174">Als er andere MX-records worden vermeld in de sectie **MX records** , selecteert u het selectievakje naast de record onder **verwijderen**en selecteert u **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="73c87-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="73c87-175">Selecteer in het bevestigingsvenster de optie **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="73c87-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="73c87-176">De zes CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="73c87-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="73c87-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="73c87-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="73c87-178">Als u wilt beginnen, gaat u naar uw domeinen pagina bij web.com met behulp van [deze koppeling](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="73c87-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="73c87-179">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="73c87-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="73c87-180">Selecteer op de pagina **account beheer** de optie **mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="73c87-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="73c87-181">Selecteer onder \* \* beheren \* mijn domein \* \* \* de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="73c87-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="73c87-182">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="73c87-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="73c87-183">Klik onder **Host Aliases (CNAME records)** op **Edit CNAME records**en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="73c87-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="73c87-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="73c87-184">**Alias**</span></span>|<span data-ttu-id="73c87-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="73c87-185">**TTL**</span></span>|<span data-ttu-id="73c87-186">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="73c87-186">**Refers to Host Name**</span></span>|<span data-ttu-id="73c87-187">**Andere host**</span><span class="sxs-lookup"><span data-stu-id="73c87-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="73c87-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="73c87-188">autodiscover</span></span>  <br/> |<span data-ttu-id="73c87-189">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-189">3600</span></span>  <br/> |<span data-ttu-id="73c87-190">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="73c87-190">@ (none)</span></span>  <br/> |<span data-ttu-id="73c87-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="73c87-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="73c87-192">sip</span><span class="sxs-lookup"><span data-stu-id="73c87-192">sip</span></span>  <br/> |<span data-ttu-id="73c87-193">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-193">3600</span></span>  <br/> |<span data-ttu-id="73c87-194">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="73c87-194">@ (none)</span></span>  <br/> |<span data-ttu-id="73c87-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="73c87-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="73c87-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="73c87-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="73c87-197">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-197">3600</span></span>  <br/> |<span data-ttu-id="73c87-198">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="73c87-198">@ (none)</span></span>  <br/> | <span data-ttu-id="73c87-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="73c87-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="73c87-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="73c87-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="73c87-201">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-201">3600</span></span>  <br/> |<span data-ttu-id="73c87-202">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="73c87-202">@ (none)</span></span>  <br/> |<span data-ttu-id="73c87-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="73c87-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="73c87-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="73c87-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="73c87-205">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-205">3600</span></span>  <br/> |<span data-ttu-id="73c87-206">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="73c87-206">@ (none)</span></span>  <br/> |<span data-ttu-id="73c87-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="73c87-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="73c87-208">msoid</span><span class="sxs-lookup"><span data-stu-id="73c87-208">msoid</span></span>  <br/> |<span data-ttu-id="73c87-209">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-209">3600</span></span>  <br/> |<span data-ttu-id="73c87-210">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="73c87-210">@ (none)</span></span>  <br/> |<span data-ttu-id="73c87-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="73c87-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="73c87-212">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="73c87-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="73c87-213">Voeg als volgt de andere vijf CNAME-records toe:</span><span class="sxs-lookup"><span data-stu-id="73c87-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="73c87-214">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="73c87-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="73c87-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="73c87-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="73c87-216">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="73c87-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="73c87-217">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="73c87-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="73c87-218">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73c87-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="73c87-219">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="73c87-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="73c87-220">Als u wilt beginnen, gaat u naar uw domeinen pagina bij web.com met behulp van [deze koppeling](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="73c87-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="73c87-221">Meld u eerst aan.</span><span class="sxs-lookup"><span data-stu-id="73c87-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="73c87-222">Selecteer op de pagina **account beheer** de optie **mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="73c87-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="73c87-223">Selecteer onder \* \* beheren \* mijn domein \* \* \* de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="73c87-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="73c87-224">Klik op de pagina **Domain names** onder **Text (TXT records)** op **Edit TXT records**en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="73c87-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="73c87-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="73c87-225">**Host**</span></span>|<span data-ttu-id="73c87-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="73c87-226">**TTL**</span></span>|<span data-ttu-id="73c87-227">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="73c87-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="73c87-228">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-228">3600</span></span>  <br/> |<span data-ttu-id="73c87-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="73c87-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="73c87-230">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="73c87-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="73c87-231">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="73c87-231">Select **Continue**.</span></span>

6. <span data-ttu-id="73c87-232">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="73c87-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="73c87-233">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="73c87-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="73c87-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="73c87-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="73c87-235">Houd er rekening mee dat web.com verantwoordelijk is voor het beschikbaar stellen van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="73c87-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="73c87-236">In het geval van verschillen tussen de onderstaande stappen en de huidige web.com-GUI (Graphical User Interface), kunt u de [Web.com-community](https://community.web.com.com/)inzetten.</span><span class="sxs-lookup"><span data-stu-id="73c87-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="73c87-237">Als u wilt beginnen, gaat u naar uw domeinen pagina bij web.com met behulp van [deze koppeling](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="73c87-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="73c87-238">Meld u eerst aan.</span><span class="sxs-lookup"><span data-stu-id="73c87-238">Log in first.</span></span>
      
2. <span data-ttu-id="73c87-239">Selecteer op de pagina **account beheer** de optie **mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="73c87-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="73c87-240">Selecteer onder \* \* beheren \* mijn domein \* \* \* de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="73c87-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="73c87-241">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="73c87-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="73c87-242">Klik onder **service (SRV records)** op **Edit SRV records**en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="73c87-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="73c87-243">**Service**</span><span class="sxs-lookup"><span data-stu-id="73c87-243">**Service**</span></span>|<span data-ttu-id="73c87-244">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="73c87-244">**Protocol**</span></span>|<span data-ttu-id="73c87-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="73c87-245">**TTL**</span></span>|<span data-ttu-id="73c87-246">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="73c87-246">**Priority**</span></span>|<span data-ttu-id="73c87-247">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="73c87-247">**Weight**</span></span>|<span data-ttu-id="73c87-248">**Poort**</span><span class="sxs-lookup"><span data-stu-id="73c87-248">**Port**</span></span>|<span data-ttu-id="73c87-249">**Target**</span><span class="sxs-lookup"><span data-stu-id="73c87-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="73c87-250">_sip</span><span class="sxs-lookup"><span data-stu-id="73c87-250">_sip</span></span> |<span data-ttu-id="73c87-251">_tls</span><span class="sxs-lookup"><span data-stu-id="73c87-251">_tls</span></span> |<span data-ttu-id="73c87-252">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-252">3600</span></span> | <span data-ttu-id="73c87-253">100</span><span class="sxs-lookup"><span data-stu-id="73c87-253">100</span></span>|<span data-ttu-id="73c87-254">1</span><span class="sxs-lookup"><span data-stu-id="73c87-254">1</span></span> |<span data-ttu-id="73c87-255">443</span><span class="sxs-lookup"><span data-stu-id="73c87-255">443</span></span> |<span data-ttu-id="73c87-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="73c87-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="73c87-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="73c87-257">_sipfederationtls</span></span> |<span data-ttu-id="73c87-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="73c87-258">_tcp</span></span> |<span data-ttu-id="73c87-259">3600</span><span class="sxs-lookup"><span data-stu-id="73c87-259">3600</span></span> |<span data-ttu-id="73c87-260">100</span><span class="sxs-lookup"><span data-stu-id="73c87-260">100</span></span> |<span data-ttu-id="73c87-261">1</span><span class="sxs-lookup"><span data-stu-id="73c87-261">1</span></span> |<span data-ttu-id="73c87-262">5061</span><span class="sxs-lookup"><span data-stu-id="73c87-262">5061</span></span> | <span data-ttu-id="73c87-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="73c87-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="73c87-264">Als u de andere SRV-record wilt toevoegen, kiest u de waarden uit de tweede rij van de tabel.</span><span class="sxs-lookup"><span data-stu-id="73c87-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="73c87-265">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="73c87-265">Select **Continue**.</span></span>

7. <span data-ttu-id="73c87-266">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="73c87-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="73c87-p116">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="73c87-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
