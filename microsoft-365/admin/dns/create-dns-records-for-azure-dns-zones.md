---
title: DNS-records maken voor Azure DNS-zones
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services in Azure DNS-zones voor Microsoft.
ms.openlocfilehash: 7104fb18a6581b7ebc853f938b85171ae1886cfd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629141"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="082fd-103">DNS-records maken voor Azure DNS-zones</span><span class="sxs-lookup"><span data-stu-id="082fd-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="082fd-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="082fd-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="082fd-105">Als Azure uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="082fd-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="082fd-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="082fd-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="082fd-107">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="082fd-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="082fd-108">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="082fd-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="082fd-109">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="082fd-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="082fd-110">Voeg de vier CNAME-records toe die voor Microsoft vereist zijn</span><span class="sxs-lookup"><span data-stu-id="082fd-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="082fd-111">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="082fd-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="082fd-112">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="082fd-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="082fd-113">Nadat u deze records bij Azure hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="082fd-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="082fd-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="082fd-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="082fd-117">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="082fd-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="082fd-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="082fd-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="082fd-119">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="082fd-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="082fd-120">Toen u zich aanmeldde voor Azure, hebt u een brongroep binnen een DNS-zone gemaakt en vervolgens uw domeinnaam toegewezen aan die brongroep.</span><span class="sxs-lookup"><span data-stu-id="082fd-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="082fd-121">Die domeinnaam is geregistreerd bij een externe domeinregistrar; Azure biedt geen domeinregistratieservices.</span><span class="sxs-lookup"><span data-stu-id="082fd-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="082fd-122">Als u DNS-records voor uw domein in Microsoft wilt verifiëren en maken, moet u eerst de naamservers van uw domeinregistrar wijzigen, zodat ze de Azure-naamservers gebruiken die aan uw brongroep zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="082fd-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="082fd-123">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="082fd-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="082fd-124">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="082fd-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="082fd-125">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="082fd-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="082fd-126">Hieronder wordt een voorbeeld van door Azure toegewezen nameservers weergegeven.</span><span class="sxs-lookup"><span data-stu-id="082fd-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="082fd-127">**Voornaamserver:** Gebruik de naamserverwaarde die door Azure is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="082fd-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="082fd-128">**Tweede naamserver:** Gebruik de naamserverwaarde die door Azure is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="082fd-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Afbeelding van het lint](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="082fd-130">U moet ten minste twee naamserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="082fd-130">You should use at least two name server records.</span></span> <span data-ttu-id="082fd-131">Als er andere naamservers op de website van uw domeinregistrar worden vermeld, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="082fd-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="082fd-132">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="082fd-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="082fd-133">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="082fd-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="082fd-134">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="082fd-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="082fd-135">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="082fd-135">Add a TXT record for verification</span></span>
<span data-ttu-id="082fd-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="082fd-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="082fd-137">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="082fd-137">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="082fd-138">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="082fd-138">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="082fd-p107">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="082fd-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="082fd-141">Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com )</span><span class="sxs-lookup"><span data-stu-id="082fd-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="082fd-142">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="082fd-142">You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="082fd-144">Typ **dns-zones**in de **zoekbalk** op de **dashboardpagina.**</span><span class="sxs-lookup"><span data-stu-id="082fd-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="082fd-145">Selecteer **dns-zones** onder het gedeelte **Services** in de resultatenweergave.</span><span class="sxs-lookup"><span data-stu-id="082fd-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="082fd-146">Zodra u bent omgeleid, selecteert u het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="082fd-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="082fd-148">Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**</span><span class="sxs-lookup"><span data-stu-id="082fd-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="082fd-150">Selecteer in het **gebied Record toevoegen in** de vakken voor de nieuwe recordset de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="082fd-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="082fd-151">(Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="082fd-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="082fd-152">**Naam**</span><span class="sxs-lookup"><span data-stu-id="082fd-152">**Name**</span></span>|<span data-ttu-id="082fd-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="082fd-153">**Type**</span></span>|<span data-ttu-id="082fd-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="082fd-154">**TTL**</span></span>|<span data-ttu-id="082fd-155">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="082fd-155">**TTL unit**</span></span>|<span data-ttu-id="082fd-156">**Value**</span><span class="sxs-lookup"><span data-stu-id="082fd-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="082fd-157">TXT</span><span class="sxs-lookup"><span data-stu-id="082fd-157">TXT</span></span>  <br/> |<span data-ttu-id="082fd-158">1</span><span class="sxs-lookup"><span data-stu-id="082fd-158">1</span></span>  <br/> |<span data-ttu-id="082fd-159">Uren</span><span class="sxs-lookup"><span data-stu-id="082fd-159">Hours</span></span>  <br/> |<span data-ttu-id="082fd-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="082fd-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="082fd-161">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="082fd-161">**Note:** This is an example.</span></span> <span data-ttu-id="082fd-162">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="082fd-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="082fd-163">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="082fd-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Afbeelding van het te maken van de afbeelding van het gebruik van Azure-Verifiëren 1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="082fd-165">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="082fd-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="082fd-166">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="082fd-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="082fd-167">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="082fd-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="082fd-168">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="082fd-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="082fd-169">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="082fd-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="082fd-170">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="082fd-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="082fd-171">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="082fd-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="082fd-172">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="082fd-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="082fd-p111">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="082fd-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="082fd-176">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="082fd-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="082fd-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="082fd-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="082fd-178">Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com )</span><span class="sxs-lookup"><span data-stu-id="082fd-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="082fd-179">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="082fd-179">You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="082fd-181">Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="082fd-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="082fd-183">Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**</span><span class="sxs-lookup"><span data-stu-id="082fd-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="082fd-185">Selecteer in het **gebied Record toevoegen in** de vakken voor de nieuwe recordset de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="082fd-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="082fd-186">(Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="082fd-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="082fd-187">**Naam**</span><span class="sxs-lookup"><span data-stu-id="082fd-187">**Name**</span></span>|<span data-ttu-id="082fd-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="082fd-188">**Type**</span></span>|<span data-ttu-id="082fd-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="082fd-189">**TTL**</span></span>|<span data-ttu-id="082fd-190">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="082fd-190">**TTL unit**</span></span>|<span data-ttu-id="082fd-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="082fd-191">**Preference**</span></span>|<span data-ttu-id="082fd-192">**Mail Exchange**</span><span class="sxs-lookup"><span data-stu-id="082fd-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="082fd-193">MX</span><span class="sxs-lookup"><span data-stu-id="082fd-193">MX</span></span>  <br/> |<span data-ttu-id="082fd-194">1</span><span class="sxs-lookup"><span data-stu-id="082fd-194">1</span></span>  <br/> |<span data-ttu-id="082fd-195">Uren</span><span class="sxs-lookup"><span data-stu-id="082fd-195">Hours</span></span>  <br/> |<span data-ttu-id="082fd-196">10</span><span class="sxs-lookup"><span data-stu-id="082fd-196">10</span></span>  <br/> <span data-ttu-id="082fd-197">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="082fd-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="082fd-198">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="082fd-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="082fd-199">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="082fd-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="082fd-200">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="082fd-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het bis](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="082fd-202">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="082fd-202">Select **OK**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="082fd-204">Als er andere MX-records worden vermeld in de sectie **MX Records,** moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="082fd-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="082fd-205">Selecteer eerst in het **gebied met DNS-zone** de **set MX Record**.</span><span class="sxs-lookup"><span data-stu-id="082fd-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het bis](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="082fd-207">Selecteer vervolgens de MX-record die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="082fd-207">Next, select the MX record you want to delete.</span></span>
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het bis](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="082fd-209">Selecteer het **menu Context (...)** en kies **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="082fd-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="082fd-211">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="082fd-211">Select **Save**.</span></span>
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van de knop 2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="082fd-213">Voeg de vier CNAME-records toe die voor Microsoft vereist zijn</span><span class="sxs-lookup"><span data-stu-id="082fd-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="082fd-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="082fd-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="082fd-215">Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com )</span><span class="sxs-lookup"><span data-stu-id="082fd-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="082fd-216">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="082fd-216">You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="082fd-218">Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="082fd-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="082fd-220">Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**</span><span class="sxs-lookup"><span data-stu-id="082fd-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="082fd-222">Voeg de eerste van de vier CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="082fd-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="082fd-223">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het **gebied Recordset toevoegen** in de vakken voor de nieuwe recordset.</span><span class="sxs-lookup"><span data-stu-id="082fd-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="082fd-224">(Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="082fd-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="082fd-225">**Naam**</span><span class="sxs-lookup"><span data-stu-id="082fd-225">**Name**</span></span>|<span data-ttu-id="082fd-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="082fd-226">**Type**</span></span>|<span data-ttu-id="082fd-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="082fd-227">**TTL**</span></span>|<span data-ttu-id="082fd-228">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="082fd-228">**TTL unit**</span></span>|<span data-ttu-id="082fd-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="082fd-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="082fd-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="082fd-230">autodiscover</span></span>  <br/> |<span data-ttu-id="082fd-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="082fd-231">CNAME</span></span>  <br/> |<span data-ttu-id="082fd-232">1</span><span class="sxs-lookup"><span data-stu-id="082fd-232">1</span></span>  <br/> |<span data-ttu-id="082fd-233">Uren</span><span class="sxs-lookup"><span data-stu-id="082fd-233">Hours</span></span>  <br/> |<span data-ttu-id="082fd-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="082fd-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="082fd-235">sip</span><span class="sxs-lookup"><span data-stu-id="082fd-235">sip</span></span>  <br/> |<span data-ttu-id="082fd-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="082fd-236">CNAME</span></span>  <br/> |<span data-ttu-id="082fd-237">1</span><span class="sxs-lookup"><span data-stu-id="082fd-237">1</span></span>  <br/> |<span data-ttu-id="082fd-238">Uren</span><span class="sxs-lookup"><span data-stu-id="082fd-238">Hours</span></span>  <br/> |<span data-ttu-id="082fd-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="082fd-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="082fd-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="082fd-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="082fd-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="082fd-241">CNAME</span></span>  <br/> |<span data-ttu-id="082fd-242">1</span><span class="sxs-lookup"><span data-stu-id="082fd-242">1</span></span>  <br/> |<span data-ttu-id="082fd-243">Uren</span><span class="sxs-lookup"><span data-stu-id="082fd-243">Hours</span></span>  <br/> |<span data-ttu-id="082fd-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="082fd-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het menu Voor Azure](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="082fd-246">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="082fd-246">Select **OK**.</span></span>
    
    ![Afbeelding van het te maken van afbeelding van het gebruik van Azure-afbeelding](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="082fd-248">Voeg de andere drie CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="082fd-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="082fd-249">Selecteer in het **gebied met DE DNS-zone** de optie **+ Recordset**.</span><span class="sxs-lookup"><span data-stu-id="082fd-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="082fd-250">Maak vervolgens in de lege recordset een record met de waarden uit de volgende rij in de tabel en selecteer opnieuw **OK** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="082fd-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="082fd-251">Herhaal deze procedure totdat u alle vier CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="082fd-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="082fd-252">(Optioneel) Voeg 2 CNAME-records toe voor MDM.</span><span class="sxs-lookup"><span data-stu-id="082fd-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="082fd-253">Als u Mobile Device Management (MDM) voor Microsoft hebt, moet u twee extra CNAME-records maken.</span><span class="sxs-lookup"><span data-stu-id="082fd-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="082fd-254">Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="082fd-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="082fd-255">(Als u geen MDM hebt, u deze stap overslaan.)</span><span class="sxs-lookup"><span data-stu-id="082fd-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="082fd-256">**Naam**</span><span class="sxs-lookup"><span data-stu-id="082fd-256">**Name**</span></span>|<span data-ttu-id="082fd-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="082fd-257">**Type**</span></span>|<span data-ttu-id="082fd-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="082fd-258">**TTL**</span></span>|<span data-ttu-id="082fd-259">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="082fd-259">**TTL unit**</span></span>|<span data-ttu-id="082fd-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="082fd-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="082fd-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="082fd-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="082fd-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="082fd-262">CNAME</span></span>  <br/> |<span data-ttu-id="082fd-263">1</span><span class="sxs-lookup"><span data-stu-id="082fd-263">1</span></span>  <br/> |<span data-ttu-id="082fd-264">Uren</span><span class="sxs-lookup"><span data-stu-id="082fd-264">Hours</span></span>  <br/> |<span data-ttu-id="082fd-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="082fd-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="082fd-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="082fd-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="082fd-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="082fd-267">CNAME</span></span>  <br/> |<span data-ttu-id="082fd-268">1</span><span class="sxs-lookup"><span data-stu-id="082fd-268">1</span></span>  <br/> |<span data-ttu-id="082fd-269">Uren</span><span class="sxs-lookup"><span data-stu-id="082fd-269">Hours</span></span>  <br/> |<span data-ttu-id="082fd-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="082fd-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="082fd-271">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="082fd-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="082fd-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="082fd-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="082fd-273">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="082fd-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="082fd-274">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="082fd-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="082fd-275">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="082fd-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="082fd-276">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="082fd-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="082fd-277">Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com )</span><span class="sxs-lookup"><span data-stu-id="082fd-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="082fd-278">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="082fd-278">You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="082fd-280">Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="082fd-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="082fd-282">Selecteer in het **gebied met DNS-zone** de **set TXT-record**.</span><span class="sxs-lookup"><span data-stu-id="082fd-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-afbeelding](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="082fd-284">Selecteer in het gebied **Recordset-eigenschappen** in de vakken voor de nieuwe recordset de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="082fd-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="082fd-285">(Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="082fd-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="082fd-286">**Naam**</span><span class="sxs-lookup"><span data-stu-id="082fd-286">**Name**</span></span>|<span data-ttu-id="082fd-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="082fd-287">**Type**</span></span>|<span data-ttu-id="082fd-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="082fd-288">**TTL**</span></span>|<span data-ttu-id="082fd-289">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="082fd-289">**TTL unit**</span></span>|<span data-ttu-id="082fd-290">**Value**</span><span class="sxs-lookup"><span data-stu-id="082fd-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="082fd-291">TXT</span><span class="sxs-lookup"><span data-stu-id="082fd-291">TXT</span></span>  <br/> |<span data-ttu-id="082fd-292">1</span><span class="sxs-lookup"><span data-stu-id="082fd-292">1</span></span>  <br/> |<span data-ttu-id="082fd-293">Uren</span><span class="sxs-lookup"><span data-stu-id="082fd-293">Hours</span></span>  <br/> |<span data-ttu-id="082fd-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="082fd-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="082fd-295">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="082fd-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-afbeelding](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="082fd-297">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="082fd-297">Select **Save**.</span></span>
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het menu 4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="082fd-299">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="082fd-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="082fd-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="082fd-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="082fd-301">Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com )</span><span class="sxs-lookup"><span data-stu-id="082fd-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="082fd-302">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="082fd-302">You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="082fd-304">Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="082fd-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="082fd-306">Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**</span><span class="sxs-lookup"><span data-stu-id="082fd-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="082fd-308">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="082fd-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="082fd-309">Selecteer in het **gebied Record toevoegen in** de vakken voor de nieuwe recordset de waarden uit de eerste rij in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="082fd-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="082fd-310">(Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="082fd-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="082fd-311">**Naam**</span><span class="sxs-lookup"><span data-stu-id="082fd-311">**Name**</span></span>|<span data-ttu-id="082fd-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="082fd-312">**Type**</span></span>|<span data-ttu-id="082fd-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="082fd-313">**TTL**</span></span>|<span data-ttu-id="082fd-314">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="082fd-314">**TTL unit**</span></span>|<span data-ttu-id="082fd-315">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="082fd-315">**Priority**</span></span>|<span data-ttu-id="082fd-316">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="082fd-316">**Weight**</span></span>|<span data-ttu-id="082fd-317">**Poort**</span><span class="sxs-lookup"><span data-stu-id="082fd-317">**Port**</span></span>|<span data-ttu-id="082fd-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="082fd-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="082fd-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="082fd-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="082fd-320">SRV</span><span class="sxs-lookup"><span data-stu-id="082fd-320">SRV</span></span>  <br/> |<span data-ttu-id="082fd-321">1</span><span class="sxs-lookup"><span data-stu-id="082fd-321">1</span></span>  <br/> |<span data-ttu-id="082fd-322">Uren</span><span class="sxs-lookup"><span data-stu-id="082fd-322">Hours</span></span>  <br/> |<span data-ttu-id="082fd-323">100</span><span class="sxs-lookup"><span data-stu-id="082fd-323">100</span></span>  <br/> |<span data-ttu-id="082fd-324">1</span><span class="sxs-lookup"><span data-stu-id="082fd-324">1</span></span>  <br/> |<span data-ttu-id="082fd-325">443</span><span class="sxs-lookup"><span data-stu-id="082fd-325">443</span></span>  <br/> |<span data-ttu-id="082fd-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="082fd-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="082fd-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="082fd-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="082fd-328">SRV</span><span class="sxs-lookup"><span data-stu-id="082fd-328">SRV</span></span>  <br/> |<span data-ttu-id="082fd-329">1</span><span class="sxs-lookup"><span data-stu-id="082fd-329">1</span></span>  <br/> |<span data-ttu-id="082fd-330">Uren</span><span class="sxs-lookup"><span data-stu-id="082fd-330">Hours</span></span>  <br/> |<span data-ttu-id="082fd-331">100</span><span class="sxs-lookup"><span data-stu-id="082fd-331">100</span></span>  <br/> |<span data-ttu-id="082fd-332">1</span><span class="sxs-lookup"><span data-stu-id="082fd-332">1</span></span>  <br/> |<span data-ttu-id="082fd-333">5061</span><span class="sxs-lookup"><span data-stu-id="082fd-333">5061</span></span>  <br/> |<span data-ttu-id="082fd-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="082fd-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="082fd-336">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="082fd-336">Select **OK**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="082fd-338">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="082fd-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="082fd-339">Typ of kopieer en plak de waarden uit de tweede rij van de tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="082fd-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="082fd-p120">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="082fd-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
