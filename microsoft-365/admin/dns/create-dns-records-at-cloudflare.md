---
title: DNS-records maken bij Cloudflare voor Microsoft
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Cloudflare voor Microsoft.
ms.openlocfilehash: f04e4b4a29085a3ddd9b388c7178c1cd638445ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629705"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="df253-103">DNS-records maken bij Cloudflare voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="df253-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="df253-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="df253-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="df253-105">Als Cloudflare uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="df253-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="df253-106">Nadat u deze records bij Cloudflare hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="df253-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="df253-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)</span><span class="sxs-lookup"><span data-stu-id="df253-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="df253-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df253-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="df253-111">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="df253-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="df253-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="df253-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="df253-113">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="df253-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="df253-114">Toen u zich voor Cloudflare registreerde, hebt u een domein toegevoegd met behulp van het Cloudflare **Setup**-proces.</span><span class="sxs-lookup"><span data-stu-id="df253-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="df253-115">Het door u toegevoegde domein was aangeschaft bij een afzonderlijke domeinregistrar; Cloudflare biedt geen domeinregistratieservices.</span><span class="sxs-lookup"><span data-stu-id="df253-115">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services.</span></span> <span data-ttu-id="df253-116">Als u DNS-records voor uw domein wilt verifiëren en maken in Microsoft 365, moet u eerst de naamservers van uw domeinregistrar wijzigen, zodat ze de naamservers van Cloudflare gebruiken.</span><span class="sxs-lookup"><span data-stu-id="df253-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="df253-117">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="df253-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="df253-118">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="df253-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="df253-119">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="df253-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="df253-120">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="df253-120">First nameserver</span></span>  <br/> |<span data-ttu-id="df253-121">Gebruik de door Cloudflare opgegeven waarde voor de naamserver.</span><span class="sxs-lookup"><span data-stu-id="df253-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="df253-122">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="df253-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="df253-123">Gebruik de door Cloudflare opgegeven waarde voor de naamserver.</span><span class="sxs-lookup"><span data-stu-id="df253-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="df253-124">U moet ten minste twee naamserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="df253-124">You should use at least two name server records.</span></span> <span data-ttu-id="df253-125">Als er andere naamservers worden vermeld, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="df253-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="df253-126">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="df253-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="df253-127">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="df253-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="df253-128">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="df253-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="df253-129">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="df253-129">Add a TXT record for verification</span></span>
<span data-ttu-id="df253-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="df253-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="df253-131">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="df253-131">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="df253-132">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="df253-132">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df253-p106">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="df253-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="df253-135">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="df253-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="df253-136">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="df253-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="df253-137">Selecteer **op** de startpagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="df253-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="df253-138">Selecteer **DNS**op de pagina **Overzicht** voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="df253-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="df253-139">Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="df253-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="df253-140">**Type**</span><span class="sxs-lookup"><span data-stu-id="df253-140">**Type**</span></span>|<span data-ttu-id="df253-141">**Name**</span><span class="sxs-lookup"><span data-stu-id="df253-141">**Name**</span></span>|<span data-ttu-id="df253-142">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="df253-142">**Automatic TTL**</span></span>|<span data-ttu-id="df253-143">**Content**</span><span class="sxs-lookup"><span data-stu-id="df253-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="df253-144">TXT</span><span class="sxs-lookup"><span data-stu-id="df253-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="df253-145">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-145">30 minutes</span></span>  <br/> |<span data-ttu-id="df253-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="df253-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="df253-147">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df253-147">**Note:** This is an example.</span></span> <span data-ttu-id="df253-148">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="df253-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="df253-149">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="df253-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="df253-150">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df253-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="df253-151">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="df253-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="df253-152">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en zoekt u naar de record.</span><span class="sxs-lookup"><span data-stu-id="df253-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="df253-153">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="df253-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="df253-154">Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="df253-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="df253-155">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="df253-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="df253-156">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="df253-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="df253-157">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="df253-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="df253-p109">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df253-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="df253-161">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="df253-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="df253-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="df253-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="df253-p110">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="df253-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="df253-165">Selecteer **op** de startpagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="df253-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="df253-166">Selecteer **DNS**op de pagina **Overzicht** voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="df253-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="df253-167">Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="df253-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="df253-168">**Type**</span><span class="sxs-lookup"><span data-stu-id="df253-168">**Type**</span></span>|<span data-ttu-id="df253-169">**Name**</span><span class="sxs-lookup"><span data-stu-id="df253-169">**Name**</span></span>|<span data-ttu-id="df253-170">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="df253-170">**Mail server**</span></span>|<span data-ttu-id="df253-171">**Priority**</span><span class="sxs-lookup"><span data-stu-id="df253-171">**Priority**</span></span>|<span data-ttu-id="df253-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df253-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df253-173">MX</span><span class="sxs-lookup"><span data-stu-id="df253-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="df253-174">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df253-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="df253-175">**Let op:** Haal uw \* \<domeinsleutel\> \* op van uw Microsoft 365-account.</span><span class="sxs-lookup"><span data-stu-id="df253-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="df253-176">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="df253-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="df253-177">1</span><span class="sxs-lookup"><span data-stu-id="df253-177">1</span></span>  <br/> <span data-ttu-id="df253-178">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="df253-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="df253-179">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="df253-180">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df253-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="df253-181">Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u ze door het pictogram **Delete (X)** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="df253-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="df253-182">Selecteer **Verwijderen in** het bevestigingsdialoogvenster om uw wijzigingen te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="df253-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="df253-183">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="df253-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="df253-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="df253-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="df253-p112">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="df253-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="df253-187">Selecteer **op** de startpagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="df253-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="df253-188">Selecteer **DNS**op de pagina **Overzicht** voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="df253-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="df253-189">Voeg de eerste van de vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="df253-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="df253-190">Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="df253-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="df253-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="df253-191">**Type**</span></span>|<span data-ttu-id="df253-192">**Naam**</span><span class="sxs-lookup"><span data-stu-id="df253-192">**Name**</span></span>|<span data-ttu-id="df253-193">**Doel**</span><span class="sxs-lookup"><span data-stu-id="df253-193">**Target**</span></span>|<span data-ttu-id="df253-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df253-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df253-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="df253-195">CNAME</span></span>  <br/> |<span data-ttu-id="df253-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="df253-196">autodiscover</span></span>  <br/> |<span data-ttu-id="df253-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df253-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="df253-198">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="df253-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="df253-199">CNAME</span></span>  <br/> |<span data-ttu-id="df253-200">sip</span><span class="sxs-lookup"><span data-stu-id="df253-200">sip</span></span>  <br/> |<span data-ttu-id="df253-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df253-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="df253-202">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="df253-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="df253-203">CNAME</span></span>  <br/> |<span data-ttu-id="df253-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="df253-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="df253-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df253-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="df253-206">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="df253-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="df253-207">CNAME</span></span>  <br/> |<span data-ttu-id="df253-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="df253-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="df253-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="df253-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="df253-210">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="df253-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="df253-211">CNAME</span></span>  <br/> |<span data-ttu-id="df253-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="df253-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="df253-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="df253-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="df253-214">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="df253-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="df253-215">CNAME</span></span>  <br/> |<span data-ttu-id="df253-216">msoid</span><span class="sxs-lookup"><span data-stu-id="df253-216">msoid</span></span>  <br/> |<span data-ttu-id="df253-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="df253-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="df253-218">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="df253-219">Selecteer het **pictogram DNS-verkeer** (oranje wolk) om de Cloudflare-servers te omzeilen.</span><span class="sxs-lookup"><span data-stu-id="df253-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="df253-220">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df253-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="df253-221">Voeg als volgt de andere vijf CNAME-records toe:</span><span class="sxs-lookup"><span data-stu-id="df253-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="df253-222">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="df253-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="df253-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="df253-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="df253-224">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="df253-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="df253-225">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="df253-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="df253-226">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df253-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="df253-227">Voeg in plaats daarvan de vereiste Microsoft 365-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="df253-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="df253-228">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="df253-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="df253-229">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="df253-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="df253-230">Selecteer **op** de startpagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="df253-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="df253-231">Selecteer **DNS**op de pagina **Overzicht** voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="df253-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="df253-232">Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="df253-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="df253-233">**Type**</span><span class="sxs-lookup"><span data-stu-id="df253-233">**Type**</span></span>|<span data-ttu-id="df253-234">**Naam**</span><span class="sxs-lookup"><span data-stu-id="df253-234">**Name**</span></span>|<span data-ttu-id="df253-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df253-235">**TTL**</span></span>|<span data-ttu-id="df253-236">**Content**</span><span class="sxs-lookup"><span data-stu-id="df253-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df253-237">TXT</span><span class="sxs-lookup"><span data-stu-id="df253-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="df253-238">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-238">30 minutes</span></span>  <br/> |<span data-ttu-id="df253-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="df253-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="df253-240">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="df253-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="df253-241">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df253-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="df253-242">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="df253-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="df253-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="df253-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="df253-244">Houd er rekening mee dat Cloudflare verantwoordelijk is voor het beschikbaar maken van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="df253-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="df253-245">Als u discrepanties ziet tussen de onderstaande stappen en de huidige Cloudflare GUI (Graphical User Interface), u gebruikmaken van de [Cloudflare-community.](https://community.cloudflare.com/)</span><span class="sxs-lookup"><span data-stu-id="df253-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="df253-246">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="df253-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="df253-247">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="df253-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="df253-248">Selecteer **op** de startpagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="df253-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="df253-249">Selecteer **DNS**op de pagina **Overzicht** voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="df253-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="df253-250">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="df253-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="df253-251">Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer de waarden uit de eerste rij van de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="df253-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="df253-252">**Type**</span><span class="sxs-lookup"><span data-stu-id="df253-252">**Type**</span></span>|<span data-ttu-id="df253-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="df253-253">**Service**</span></span>|<span data-ttu-id="df253-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="df253-254">**Protocol**</span></span>|<span data-ttu-id="df253-255">**Naam**</span><span class="sxs-lookup"><span data-stu-id="df253-255">**Name**</span></span>|<span data-ttu-id="df253-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df253-256">**TTL**</span></span>|<span data-ttu-id="df253-257">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="df253-257">**Priority**</span></span>|<span data-ttu-id="df253-258">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="df253-258">**Weight**</span></span>|<span data-ttu-id="df253-259">**Poort**</span><span class="sxs-lookup"><span data-stu-id="df253-259">**Port**</span></span>|<span data-ttu-id="df253-260">**Doel**</span><span class="sxs-lookup"><span data-stu-id="df253-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df253-261">SRV</span><span class="sxs-lookup"><span data-stu-id="df253-261">SRV</span></span>|<span data-ttu-id="df253-262">_sip</span><span class="sxs-lookup"><span data-stu-id="df253-262">_sip</span></span> |<span data-ttu-id="df253-263">TLS</span><span class="sxs-lookup"><span data-stu-id="df253-263">TLS</span></span> |<span data-ttu-id="df253-264">Gebruik uw *domain_name*; contoso.com bijvoorbeeld</span><span class="sxs-lookup"><span data-stu-id="df253-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="df253-265">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-265">30 minutes</span></span> | <span data-ttu-id="df253-266">100</span><span class="sxs-lookup"><span data-stu-id="df253-266">100</span></span>|<span data-ttu-id="df253-267">1</span><span class="sxs-lookup"><span data-stu-id="df253-267">1</span></span> |<span data-ttu-id="df253-268">443</span><span class="sxs-lookup"><span data-stu-id="df253-268">443</span></span> |<span data-ttu-id="df253-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df253-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="df253-270">SRV</span><span class="sxs-lookup"><span data-stu-id="df253-270">SRV</span></span>|<span data-ttu-id="df253-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="df253-271">_sipfederationtls</span></span> | <span data-ttu-id="df253-272">TCP</span><span class="sxs-lookup"><span data-stu-id="df253-272">TCP</span></span>|<span data-ttu-id="df253-273">Gebruik uw *domain_name*; contoso.com bijvoorbeeld</span><span class="sxs-lookup"><span data-stu-id="df253-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="df253-274">30 minutes</span><span class="sxs-lookup"><span data-stu-id="df253-274">30 minutes</span></span> |<span data-ttu-id="df253-275">100</span><span class="sxs-lookup"><span data-stu-id="df253-275">100</span></span> |<span data-ttu-id="df253-276">1</span><span class="sxs-lookup"><span data-stu-id="df253-276">1</span></span> |<span data-ttu-id="df253-277">5061</span><span class="sxs-lookup"><span data-stu-id="df253-277">5061</span></span> | <span data-ttu-id="df253-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df253-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="df253-279">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df253-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="df253-280">Voeg de andere SRV-record toe door de waarden uit de tweede rij van de tabel te kiezen.</span><span class="sxs-lookup"><span data-stu-id="df253-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="df253-p117">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df253-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
