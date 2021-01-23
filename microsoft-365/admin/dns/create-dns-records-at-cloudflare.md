---
title: DNS-records bij Cloudflare maken voor Microsoft
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
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Cloudflare voor Microsoft.
ms.openlocfilehash: 8d5dd7779f07fd42dd230ee33c40849da3519d26
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939270"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="99502-103">DNS-records bij Cloudflare maken voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="99502-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="99502-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="99502-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="99502-105">Als Cloudflare uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="99502-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="99502-106">Nadat u deze records bij Cloudflare hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft 365-Services.</span><span class="sxs-lookup"><span data-stu-id="99502-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="99502-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="99502-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="99502-110">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="99502-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="99502-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="99502-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="99502-112">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="99502-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="99502-113">Toen u zich voor Cloudflare registreerde, hebt u een domein toegevoegd met behulp van het Cloudflare **Setup**-proces.</span><span class="sxs-lookup"><span data-stu-id="99502-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="99502-114">Het domein dat u hebt toegevoegd is aangeschaft bij Cloudflare of een afzonderlijke domeinregistratie.</span><span class="sxs-lookup"><span data-stu-id="99502-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="99502-115">Als u DNS-records voor uw domein wilt controleren en maken in Microsoft 365, moet u eerst de naamservers van uw domeinregistratie wijzigen, zodat ze de naamservers van Cloudflare gebruiken.</span><span class="sxs-lookup"><span data-stu-id="99502-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="99502-116">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="99502-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="99502-117">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="99502-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="99502-118">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="99502-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="99502-119">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="99502-119">First nameserver</span></span>  <br/> |<span data-ttu-id="99502-120">Gebruik de door Cloudflare opgegeven waarde voor de naamserver.</span><span class="sxs-lookup"><span data-stu-id="99502-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="99502-121">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="99502-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="99502-122">Gebruik de door Cloudflare opgegeven waarde voor de naamserver.</span><span class="sxs-lookup"><span data-stu-id="99502-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="99502-123">U dient ten minste twee naamserver records te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="99502-123">You should use at least two name server records.</span></span> <span data-ttu-id="99502-124">Als er andere naamservers worden weergegeven, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="99502-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="99502-125">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="99502-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="99502-126">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="99502-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="99502-127">Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="99502-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="99502-128">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="99502-128">Add a TXT record for verification</span></span>
<span data-ttu-id="99502-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="99502-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="99502-p105">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="99502-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="99502-p106">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="99502-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="99502-p107">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="99502-p107">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="99502-136">Selecteer op de **Start** pagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="99502-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="99502-137">Selecteer op de pagina **Overview** voor uw domein de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="99502-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="99502-138">Klik op de pagina **DNS-beheer** op **record toevoegen** en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="99502-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="99502-139">Type</span><span class="sxs-lookup"><span data-stu-id="99502-139">Type</span></span> | <span data-ttu-id="99502-140">Naam</span><span class="sxs-lookup"><span data-stu-id="99502-140">Name</span></span> | <span data-ttu-id="99502-141">Automatic TTL</span><span class="sxs-lookup"><span data-stu-id="99502-141">Automatic TTL</span></span> | <span data-ttu-id="99502-142">Content</span><span class="sxs-lookup"><span data-stu-id="99502-142">Content</span></span> |
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="99502-143">TXT</span><span class="sxs-lookup"><span data-stu-id="99502-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="99502-144">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-144">30 minutes</span></span>  <br/> |<span data-ttu-id="99502-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="99502-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="99502-146">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="99502-146">**Note:** This is an example.</span></span> <span data-ttu-id="99502-147">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="99502-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="99502-148">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="99502-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="99502-149">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="99502-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="99502-150">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="99502-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="99502-151">Nu u de record hebt toegevoegd aan de site van uw domeinregistratie, gaat u terug naar Microsoft en gaat u naar de record.</span><span class="sxs-lookup"><span data-stu-id="99502-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="99502-152">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="99502-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="99502-153">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="99502-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="99502-154">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="99502-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="99502-155">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="99502-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="99502-156">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="99502-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="99502-p109">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="99502-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="99502-160">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="99502-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="99502-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="99502-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="99502-p110">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="99502-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="99502-164">Selecteer op de **Start** pagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="99502-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="99502-165">Selecteer op de pagina **Overview** voor uw domein de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="99502-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="99502-166">Klik op de pagina **DNS-beheer** op **record toevoegen** en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="99502-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="99502-167">Type</span><span class="sxs-lookup"><span data-stu-id="99502-167">Type</span></span> | <span data-ttu-id="99502-168">Naam</span><span class="sxs-lookup"><span data-stu-id="99502-168">Name</span></span> | <span data-ttu-id="99502-169">E-mail server</span><span class="sxs-lookup"><span data-stu-id="99502-169">Mail server</span></span> | <span data-ttu-id="99502-170">Priority</span><span class="sxs-lookup"><span data-stu-id="99502-170">Priority</span></span> | <span data-ttu-id="99502-171">TTL</span><span class="sxs-lookup"><span data-stu-id="99502-171">TTL</span></span> |
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="99502-172">MX</span><span class="sxs-lookup"><span data-stu-id="99502-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="99502-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="99502-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="99502-174">**Opmerking:** Ga  *\<domain-key\>*  naar uw Microsoft 365-account.</span><span class="sxs-lookup"><span data-stu-id="99502-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="99502-175">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="99502-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="99502-176">1</span><span class="sxs-lookup"><span data-stu-id="99502-176">1</span></span>  <br/> <span data-ttu-id="99502-177">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="99502-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="99502-178">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="99502-179">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="99502-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="99502-180">Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u ze door het pictogram **Delete (X)** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="99502-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="99502-181">Selecteer in het bevestigingsvenster de optie **verwijderen** om uw wijzigingen te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="99502-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="99502-182">De zes CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="99502-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="99502-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="99502-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="99502-p112">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="99502-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="99502-186">Selecteer op de **Start** pagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="99502-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="99502-187">Selecteer op de pagina **Overview** voor uw domein de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="99502-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="99502-188">Voeg de eerste van de vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="99502-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="99502-189">Klik op de pagina **DNS-beheer** op **record toevoegen** en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="99502-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    | <span data-ttu-id="99502-190">Type</span><span class="sxs-lookup"><span data-stu-id="99502-190">Type</span></span> | <span data-ttu-id="99502-191">Naam</span><span class="sxs-lookup"><span data-stu-id="99502-191">Name</span></span> | <span data-ttu-id="99502-192">Doel</span><span class="sxs-lookup"><span data-stu-id="99502-192">Target</span></span> | <span data-ttu-id="99502-193">TTL</span><span class="sxs-lookup"><span data-stu-id="99502-193">TTL</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="99502-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="99502-194">CNAME</span></span>  <br/> |<span data-ttu-id="99502-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="99502-195">autodiscover</span></span>  <br/> |<span data-ttu-id="99502-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="99502-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="99502-197">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="99502-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="99502-198">CNAME</span></span>  <br/> |<span data-ttu-id="99502-199">sip</span><span class="sxs-lookup"><span data-stu-id="99502-199">sip</span></span>  <br/> |<span data-ttu-id="99502-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="99502-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="99502-201">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="99502-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="99502-202">CNAME</span></span>  <br/> |<span data-ttu-id="99502-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="99502-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="99502-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="99502-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="99502-205">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="99502-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="99502-206">CNAME</span></span>  <br/> |<span data-ttu-id="99502-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="99502-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="99502-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="99502-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="99502-209">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="99502-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="99502-210">CNAME</span></span>  <br/> |<span data-ttu-id="99502-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="99502-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="99502-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="99502-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="99502-213">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="99502-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="99502-214">CNAME</span></span>  <br/> |<span data-ttu-id="99502-215">msoid</span><span class="sxs-lookup"><span data-stu-id="99502-215">msoid</span></span>  <br/> |<span data-ttu-id="99502-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="99502-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="99502-217">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="99502-218">Selecteer het pictogram van het **DNS-verkeer** (oranje wolk wijzigen in grijs) om de Cloudflare-servers te omzeilen.</span><span class="sxs-lookup"><span data-stu-id="99502-218">Select the **DNS Traffic** icon (change orange cloud to grey) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="99502-219">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="99502-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="99502-220">Voeg als volgt de andere vijf CNAME-records toe:</span><span class="sxs-lookup"><span data-stu-id="99502-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="99502-221">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="99502-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="99502-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="99502-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="99502-223">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="99502-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="99502-224">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="99502-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="99502-225">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Microsoft 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="99502-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="99502-226">In plaats daarvan voegt u de vereiste Microsoft 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="99502-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="99502-227">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="99502-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="99502-228">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="99502-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="99502-229">Selecteer op de **Start** pagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="99502-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="99502-230">Selecteer op de pagina **Overview** voor uw domein de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="99502-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="99502-231">Klik op de pagina **DNS-beheer** op **record toevoegen** en selecteer vervolgens de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="99502-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    | <span data-ttu-id="99502-232">Type</span><span class="sxs-lookup"><span data-stu-id="99502-232">Type</span></span> | <span data-ttu-id="99502-233">Naam</span><span class="sxs-lookup"><span data-stu-id="99502-233">Name</span></span> | <span data-ttu-id="99502-234">TTL</span><span class="sxs-lookup"><span data-stu-id="99502-234">TTL</span></span> | <span data-ttu-id="99502-235">Content</span><span class="sxs-lookup"><span data-stu-id="99502-235">Content</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="99502-236">TXT</span><span class="sxs-lookup"><span data-stu-id="99502-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="99502-237">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-237">30 minutes</span></span>  <br/> |<span data-ttu-id="99502-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="99502-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="99502-239">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="99502-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="99502-240">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="99502-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="99502-241">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="99502-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="99502-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="99502-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="99502-243">Houd er rekening mee dat Cloudflare verantwoordelijk is voor het beschikbaar stellen van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="99502-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="99502-244">In het geval van verschillen tussen de onderstaande stappen en de huidige Cloudflare-GUI (Graphical User Interface), kunt u de [Cloudflare-Community](https://community.cloudflare.com/)inzetten.</span><span class="sxs-lookup"><span data-stu-id="99502-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="99502-245">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="99502-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="99502-246">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="99502-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="99502-247">Selecteer op de **Start** pagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="99502-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="99502-248">Selecteer op de pagina **Overview** voor uw domein de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="99502-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="99502-249">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="99502-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="99502-250">Klik op de pagina **DNS-beheer** op **record toevoegen** en selecteer vervolgens de waarden uit de eerste rij van de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="99502-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    | <span data-ttu-id="99502-251">Type</span><span class="sxs-lookup"><span data-stu-id="99502-251">Type</span></span> | <span data-ttu-id="99502-252">Service</span><span class="sxs-lookup"><span data-stu-id="99502-252">Service</span></span> | <span data-ttu-id="99502-253">Protocol</span><span class="sxs-lookup"><span data-stu-id="99502-253">Protocol</span></span> | <span data-ttu-id="99502-254">Naam</span><span class="sxs-lookup"><span data-stu-id="99502-254">Name</span></span> | <span data-ttu-id="99502-255">TTL</span><span class="sxs-lookup"><span data-stu-id="99502-255">TTL</span></span> | <span data-ttu-id="99502-256">Priority</span><span class="sxs-lookup"><span data-stu-id="99502-256">Priority</span></span> | <span data-ttu-id="99502-257">Dikte</span><span class="sxs-lookup"><span data-stu-id="99502-257">Weight</span></span> | <span data-ttu-id="99502-258">Poort</span><span class="sxs-lookup"><span data-stu-id="99502-258">Port</span></span> | <span data-ttu-id="99502-259">Doel</span><span class="sxs-lookup"><span data-stu-id="99502-259">Target</span></span> |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="99502-260">SRV</span><span class="sxs-lookup"><span data-stu-id="99502-260">SRV</span></span>|<span data-ttu-id="99502-261">_sip</span><span class="sxs-lookup"><span data-stu-id="99502-261">_sip</span></span> |<span data-ttu-id="99502-262">TLS</span><span class="sxs-lookup"><span data-stu-id="99502-262">TLS</span></span> |<span data-ttu-id="99502-263">Gebruik uw *Domain_Name*; bijvoorbeeld: contoso.com</span><span class="sxs-lookup"><span data-stu-id="99502-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="99502-264">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-264">30 minutes</span></span> | <span data-ttu-id="99502-265">100</span><span class="sxs-lookup"><span data-stu-id="99502-265">100</span></span>|<span data-ttu-id="99502-266">1</span><span class="sxs-lookup"><span data-stu-id="99502-266">1</span></span> |<span data-ttu-id="99502-267">443</span><span class="sxs-lookup"><span data-stu-id="99502-267">443</span></span> |<span data-ttu-id="99502-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="99502-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="99502-269">SRV</span><span class="sxs-lookup"><span data-stu-id="99502-269">SRV</span></span>|<span data-ttu-id="99502-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="99502-270">_sipfederationtls</span></span> | <span data-ttu-id="99502-271">TCP</span><span class="sxs-lookup"><span data-stu-id="99502-271">TCP</span></span>|<span data-ttu-id="99502-272">Gebruik uw *Domain_Name*; bijvoorbeeld: contoso.com</span><span class="sxs-lookup"><span data-stu-id="99502-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="99502-273">30 minutes</span><span class="sxs-lookup"><span data-stu-id="99502-273">30 minutes</span></span> |<span data-ttu-id="99502-274">100</span><span class="sxs-lookup"><span data-stu-id="99502-274">100</span></span> |<span data-ttu-id="99502-275">1</span><span class="sxs-lookup"><span data-stu-id="99502-275">1</span></span> |<span data-ttu-id="99502-276">5061</span><span class="sxs-lookup"><span data-stu-id="99502-276">5061</span></span> | <span data-ttu-id="99502-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="99502-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="99502-278">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="99502-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="99502-279">Als u de andere SRV-record wilt toevoegen, kiest u de waarden uit de tweede rij van de tabel.</span><span class="sxs-lookup"><span data-stu-id="99502-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="99502-p117">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="99502-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
