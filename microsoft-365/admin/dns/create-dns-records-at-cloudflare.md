---
title: DNS-records maken bij Cloudflare voor Microsoft
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
description: Informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij Cloudflare voor Microsoft.
ms.openlocfilehash: 0a80cf059a3a69dcb8aa48251875410f35684286
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910376"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="71ed6-103">DNS-records maken bij Cloudflare voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="71ed6-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="71ed6-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="71ed6-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="71ed6-105">Als Cloudflare uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="71ed6-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="71ed6-106">Nadat u deze records bij Cloudflare hebt toevoegen, is uw domein ingesteld voor gebruik met Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="71ed6-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="71ed6-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="71ed6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="71ed6-110">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="71ed6-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="71ed6-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="71ed6-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="71ed6-112">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="71ed6-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="71ed6-113">Toen u zich voor Cloudflare registreerde, hebt u een domein toegevoegd met behulp van het Cloudflare **Setup**-proces.</span><span class="sxs-lookup"><span data-stu-id="71ed6-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="71ed6-114">Het domein dat u hebt toegevoegd, is gekocht bij Cloudflare of een afzonderlijke domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="71ed6-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="71ed6-115">Als u DNS-records wilt controleren en maken voor uw domein in Microsoft 365, moet u eerst de naamservers bij uw domeinregistrar wijzigen, zodat ze de naamservers van Cloudflare gebruiken.</span><span class="sxs-lookup"><span data-stu-id="71ed6-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="71ed6-116">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="71ed6-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="71ed6-117">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="71ed6-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="71ed6-118">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="71ed6-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="71ed6-119">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="71ed6-119">First nameserver</span></span>  <br/> |<span data-ttu-id="71ed6-120">Gebruik de door Cloudflare opgegeven waarde voor de naamserver.</span><span class="sxs-lookup"><span data-stu-id="71ed6-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="71ed6-121">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="71ed6-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="71ed6-122">Gebruik de door Cloudflare opgegeven waarde voor de naamserver.</span><span class="sxs-lookup"><span data-stu-id="71ed6-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="71ed6-123">U moet ten minste twee naamserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="71ed6-123">You should use at least two name server records.</span></span> <span data-ttu-id="71ed6-124">Als er andere naamservers worden vermeld, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="71ed6-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="71ed6-125">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="71ed6-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="71ed6-126">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="71ed6-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="71ed6-127">Vervolgens zijn uw e-mail en andere services van Microsoft ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="71ed6-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="71ed6-128">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="71ed6-128">Add a TXT record for verification</span></span>
<span data-ttu-id="71ed6-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="71ed6-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="71ed6-p105">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="71ed6-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71ed6-p106">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="71ed6-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="71ed6-p107">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="71ed6-p107">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="71ed6-136">Selecteer op **de startpagina** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="71ed6-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="71ed6-137">Selecteer DNS **op de** pagina Overzicht voor uw **domein.**</span><span class="sxs-lookup"><span data-stu-id="71ed6-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="71ed6-138">Klik op **de pagina DNS-beheer** op **Record toevoegen** en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="71ed6-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="71ed6-139">Type</span><span class="sxs-lookup"><span data-stu-id="71ed6-139">Type</span></span> | <span data-ttu-id="71ed6-140">Naam</span><span class="sxs-lookup"><span data-stu-id="71ed6-140">Name</span></span> | <span data-ttu-id="71ed6-141">Automatic TTL</span><span class="sxs-lookup"><span data-stu-id="71ed6-141">Automatic TTL</span></span> | <span data-ttu-id="71ed6-142">Content</span><span class="sxs-lookup"><span data-stu-id="71ed6-142">Content</span></span> |
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="71ed6-143">TXT</span><span class="sxs-lookup"><span data-stu-id="71ed6-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="71ed6-144">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-144">30 minutes</span></span>  <br/> |<span data-ttu-id="71ed6-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="71ed6-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="71ed6-146">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="71ed6-146">**Note:** This is an example.</span></span> <span data-ttu-id="71ed6-147">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="71ed6-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="71ed6-148">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="71ed6-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="71ed6-149">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="71ed6-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="71ed6-150">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="71ed6-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="71ed6-151">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en zoekt u naar de record.</span><span class="sxs-lookup"><span data-stu-id="71ed6-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="71ed6-152">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="71ed6-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="71ed6-153">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="71ed6-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="71ed6-154">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="71ed6-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="71ed6-155">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="71ed6-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="71ed6-156">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="71ed6-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="71ed6-p109">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="71ed6-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="71ed6-160">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="71ed6-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="71ed6-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="71ed6-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="71ed6-p110">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="71ed6-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="71ed6-164">Selecteer op **de startpagina** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="71ed6-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="71ed6-165">Selecteer DNS **op de** pagina Overzicht voor uw **domein.**</span><span class="sxs-lookup"><span data-stu-id="71ed6-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="71ed6-166">Klik op **de pagina DNS-beheer** op **Record toevoegen** en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="71ed6-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="71ed6-167">Type</span><span class="sxs-lookup"><span data-stu-id="71ed6-167">Type</span></span> | <span data-ttu-id="71ed6-168">Naam</span><span class="sxs-lookup"><span data-stu-id="71ed6-168">Name</span></span> | <span data-ttu-id="71ed6-169">E-mailserver</span><span class="sxs-lookup"><span data-stu-id="71ed6-169">Mail server</span></span> | <span data-ttu-id="71ed6-170">Priority</span><span class="sxs-lookup"><span data-stu-id="71ed6-170">Priority</span></span> | <span data-ttu-id="71ed6-171">TTL</span><span class="sxs-lookup"><span data-stu-id="71ed6-171">TTL</span></span> |
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="71ed6-172">MX</span><span class="sxs-lookup"><span data-stu-id="71ed6-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="71ed6-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="71ed6-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="71ed6-174">**Opmerking:** Haal uw  *\<domain-key\>*  uit uw Microsoft 365-account.</span><span class="sxs-lookup"><span data-stu-id="71ed6-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="71ed6-175">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="71ed6-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="71ed6-176">1</span><span class="sxs-lookup"><span data-stu-id="71ed6-176">1</span></span>  <br/> <span data-ttu-id="71ed6-177">Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="71ed6-177">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/>|<span data-ttu-id="71ed6-178">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="71ed6-179">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="71ed6-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="71ed6-180">Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u ze door het pictogram **Delete (X)** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="71ed6-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="71ed6-181">Selecteer verwijderen in het bevestigingsdialoogvenster **om** uw wijzigingen te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="71ed6-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="71ed6-182">De zes CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="71ed6-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="71ed6-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="71ed6-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="71ed6-p112">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="71ed6-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="71ed6-186">Selecteer op **de startpagina** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="71ed6-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="71ed6-187">Selecteer DNS **op de** pagina Overzicht voor uw **domein.**</span><span class="sxs-lookup"><span data-stu-id="71ed6-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="71ed6-188">Voeg de eerste van de vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="71ed6-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="71ed6-189">Klik op **de pagina DNS-beheer** op **Record toevoegen** en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="71ed6-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    | <span data-ttu-id="71ed6-190">Type</span><span class="sxs-lookup"><span data-stu-id="71ed6-190">Type</span></span> | <span data-ttu-id="71ed6-191">Naam</span><span class="sxs-lookup"><span data-stu-id="71ed6-191">Name</span></span> | <span data-ttu-id="71ed6-192">Doel</span><span class="sxs-lookup"><span data-stu-id="71ed6-192">Target</span></span> | <span data-ttu-id="71ed6-193">TTL</span><span class="sxs-lookup"><span data-stu-id="71ed6-193">TTL</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="71ed6-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="71ed6-194">CNAME</span></span>  <br/> |<span data-ttu-id="71ed6-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="71ed6-195">autodiscover</span></span>  <br/> |<span data-ttu-id="71ed6-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="71ed6-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="71ed6-197">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="71ed6-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="71ed6-198">CNAME</span></span>  <br/> |<span data-ttu-id="71ed6-199">sip</span><span class="sxs-lookup"><span data-stu-id="71ed6-199">sip</span></span>  <br/> |<span data-ttu-id="71ed6-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="71ed6-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="71ed6-201">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="71ed6-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="71ed6-202">CNAME</span></span>  <br/> |<span data-ttu-id="71ed6-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="71ed6-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="71ed6-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="71ed6-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="71ed6-205">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="71ed6-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="71ed6-206">CNAME</span></span>  <br/> |<span data-ttu-id="71ed6-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="71ed6-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="71ed6-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="71ed6-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="71ed6-209">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="71ed6-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="71ed6-210">CNAME</span></span>  <br/> |<span data-ttu-id="71ed6-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="71ed6-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="71ed6-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="71ed6-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="71ed6-213">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="71ed6-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="71ed6-214">CNAME</span></span>  <br/> |<span data-ttu-id="71ed6-215">msoid</span><span class="sxs-lookup"><span data-stu-id="71ed6-215">msoid</span></span>  <br/> |<span data-ttu-id="71ed6-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="71ed6-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="71ed6-217">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="71ed6-218">Selecteer het **pictogram DNS-verkeer** (oranje wolk wijzigen in grijs) om de Cloudflare-servers te omzeilen.</span><span class="sxs-lookup"><span data-stu-id="71ed6-218">Select the **DNS Traffic** icon (change orange cloud to grey) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="71ed6-219">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="71ed6-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="71ed6-220">Voeg als volgt de andere vijf CNAME-records toe:</span><span class="sxs-lookup"><span data-stu-id="71ed6-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="71ed6-221">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="71ed6-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="71ed6-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="71ed6-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="71ed6-223">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="71ed6-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="71ed6-224">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="71ed6-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="71ed6-225">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Microsoft 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="71ed6-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="71ed6-226">In plaats daarvan voegt u de vereiste Microsoft 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="71ed6-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="71ed6-227">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="71ed6-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="71ed6-228">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="71ed6-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="71ed6-229">Selecteer op **de startpagina** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="71ed6-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="71ed6-230">Selecteer DNS **op de** pagina Overzicht voor uw **domein.**</span><span class="sxs-lookup"><span data-stu-id="71ed6-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="71ed6-231">Klik op **de pagina DNS-beheer** op **Record toevoegen** en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="71ed6-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    | <span data-ttu-id="71ed6-232">Type</span><span class="sxs-lookup"><span data-stu-id="71ed6-232">Type</span></span> | <span data-ttu-id="71ed6-233">Naam</span><span class="sxs-lookup"><span data-stu-id="71ed6-233">Name</span></span> | <span data-ttu-id="71ed6-234">TTL</span><span class="sxs-lookup"><span data-stu-id="71ed6-234">TTL</span></span> | <span data-ttu-id="71ed6-235">Content</span><span class="sxs-lookup"><span data-stu-id="71ed6-235">Content</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="71ed6-236">TXT</span><span class="sxs-lookup"><span data-stu-id="71ed6-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="71ed6-237">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-237">30 minutes</span></span>  <br/> |<span data-ttu-id="71ed6-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="71ed6-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="71ed6-239">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="71ed6-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="71ed6-240">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="71ed6-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="71ed6-241">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="71ed6-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="71ed6-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="71ed6-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="71ed6-243">Houd er rekening mee dat Cloudflare verantwoordelijk is voor het beschikbaar stellen van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="71ed6-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="71ed6-244">Als u verschillen ziet tussen de onderstaande stappen en de huidige Cloudflare GUI (Grafische gebruikersinterface), kunt u gebruikmaken van de [Cloudflare-community.](https://community.cloudflare.com/)</span><span class="sxs-lookup"><span data-stu-id="71ed6-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="71ed6-245">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="71ed6-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="71ed6-246">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="71ed6-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="71ed6-247">Selecteer op **de startpagina** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="71ed6-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="71ed6-248">Selecteer DNS **op de** pagina Overzicht voor uw **domein.**</span><span class="sxs-lookup"><span data-stu-id="71ed6-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="71ed6-249">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="71ed6-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="71ed6-250">Klik op **de pagina DNS-beheer** op **Record toevoegen** en selecteer vervolgens de waarden in de eerste rij van de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="71ed6-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    | <span data-ttu-id="71ed6-251">Type</span><span class="sxs-lookup"><span data-stu-id="71ed6-251">Type</span></span> | <span data-ttu-id="71ed6-252">Service</span><span class="sxs-lookup"><span data-stu-id="71ed6-252">Service</span></span> | <span data-ttu-id="71ed6-253">Protocol</span><span class="sxs-lookup"><span data-stu-id="71ed6-253">Protocol</span></span> | <span data-ttu-id="71ed6-254">Naam</span><span class="sxs-lookup"><span data-stu-id="71ed6-254">Name</span></span> | <span data-ttu-id="71ed6-255">TTL</span><span class="sxs-lookup"><span data-stu-id="71ed6-255">TTL</span></span> | <span data-ttu-id="71ed6-256">Priority</span><span class="sxs-lookup"><span data-stu-id="71ed6-256">Priority</span></span> | <span data-ttu-id="71ed6-257">Gewicht</span><span class="sxs-lookup"><span data-stu-id="71ed6-257">Weight</span></span> | <span data-ttu-id="71ed6-258">Poort</span><span class="sxs-lookup"><span data-stu-id="71ed6-258">Port</span></span> | <span data-ttu-id="71ed6-259">Doel</span><span class="sxs-lookup"><span data-stu-id="71ed6-259">Target</span></span> |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="71ed6-260">SRV</span><span class="sxs-lookup"><span data-stu-id="71ed6-260">SRV</span></span>|<span data-ttu-id="71ed6-261">_sip</span><span class="sxs-lookup"><span data-stu-id="71ed6-261">_sip</span></span> |<span data-ttu-id="71ed6-262">TLS</span><span class="sxs-lookup"><span data-stu-id="71ed6-262">TLS</span></span> |<span data-ttu-id="71ed6-263">Gebruik uw *domain_name*; bijvoorbeeld contoso.com</span><span class="sxs-lookup"><span data-stu-id="71ed6-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="71ed6-264">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-264">30 minutes</span></span> | <span data-ttu-id="71ed6-265">100</span><span class="sxs-lookup"><span data-stu-id="71ed6-265">100</span></span>|<span data-ttu-id="71ed6-266">1</span><span class="sxs-lookup"><span data-stu-id="71ed6-266">1</span></span> |<span data-ttu-id="71ed6-267">443</span><span class="sxs-lookup"><span data-stu-id="71ed6-267">443</span></span> |<span data-ttu-id="71ed6-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="71ed6-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="71ed6-269">SRV</span><span class="sxs-lookup"><span data-stu-id="71ed6-269">SRV</span></span>|<span data-ttu-id="71ed6-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="71ed6-270">_sipfederationtls</span></span> | <span data-ttu-id="71ed6-271">TCP</span><span class="sxs-lookup"><span data-stu-id="71ed6-271">TCP</span></span>|<span data-ttu-id="71ed6-272">Gebruik uw *domain_name*; bijvoorbeeld contoso.com</span><span class="sxs-lookup"><span data-stu-id="71ed6-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="71ed6-273">30 minutes</span><span class="sxs-lookup"><span data-stu-id="71ed6-273">30 minutes</span></span> |<span data-ttu-id="71ed6-274">100</span><span class="sxs-lookup"><span data-stu-id="71ed6-274">100</span></span> |<span data-ttu-id="71ed6-275">1</span><span class="sxs-lookup"><span data-stu-id="71ed6-275">1</span></span> |<span data-ttu-id="71ed6-276">5061</span><span class="sxs-lookup"><span data-stu-id="71ed6-276">5061</span></span> | <span data-ttu-id="71ed6-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="71ed6-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="71ed6-278">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="71ed6-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="71ed6-279">Voeg de andere SRV-record toe door de waarden uit de tweede rij van de tabel te kiezen.</span><span class="sxs-lookup"><span data-stu-id="71ed6-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="71ed6-p117">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="71ed6-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
