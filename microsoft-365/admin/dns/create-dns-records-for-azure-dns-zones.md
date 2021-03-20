---
title: DNS-records maken voor Azure DNS-zones
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services in Azure DNS-zones voor Microsoft.
ms.openlocfilehash: be4baa80d0f96e92dc9dd9004054f29f12f6415b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916140"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="14e81-103">DNS-records maken voor Azure DNS-zones</span><span class="sxs-lookup"><span data-stu-id="14e81-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="14e81-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="14e81-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="14e81-105">Als Azure uw DNS-hostingprovider is, volgt u de stappen in dit artikel om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, en meer.</span><span class="sxs-lookup"><span data-stu-id="14e81-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="14e81-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="14e81-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="14e81-107">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="14e81-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="14e81-108">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="14e81-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="14e81-109">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="14e81-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="14e81-110">De vier CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="14e81-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="14e81-111">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="14e81-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="14e81-112">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="14e81-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="14e81-113">Nadat u deze records bij Azure hebt toevoegen, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="14e81-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14e81-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="14e81-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="14e81-117">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="14e81-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="14e81-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="14e81-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="14e81-119">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="14e81-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="14e81-120">Wanneer u zich hebt aangemeld voor Azure, hebt u een resourcegroep gemaakt in een DNS-zone en vervolgens uw domeinnaam toegewezen aan die resourcegroep.</span><span class="sxs-lookup"><span data-stu-id="14e81-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="14e81-121">Die domeinnaam is geregistreerd bij een externe domeinregistrar. Azure biedt geen domeinregistratieservices.</span><span class="sxs-lookup"><span data-stu-id="14e81-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="14e81-122">Als u DNS-records voor uw domein in Microsoft wilt verifiëren en maken, moet u eerst de naamservers bij uw domeinregistrar wijzigen, zodat ze de Azure-naamservers gebruiken die aan uw resourcegroep zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="14e81-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="14e81-123">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="14e81-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="14e81-124">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="14e81-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="14e81-125">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="14e81-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="14e81-126">Hieronder wordt een voorbeeld van azure toegewezen naamservers weergegeven.</span><span class="sxs-lookup"><span data-stu-id="14e81-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="14e81-127">**Voornaamserver:** Gebruik de naamserverwaarde die door Azure is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="14e81-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="14e81-128">**Tweede naamserver:** Gebruik de naamserverwaarde die door Azure is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="14e81-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="14e81-130">U moet ten minste twee naamserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="14e81-130">You should use at least two name server records.</span></span> <span data-ttu-id="14e81-131">Als er andere naamservers worden vermeld op de website van uw domeinregistrar, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="14e81-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="14e81-132">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="14e81-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="14e81-133">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="14e81-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="14e81-134">Vervolgens zijn uw e-mail en andere services van Microsoft ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="14e81-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="14e81-135">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="14e81-135">Add a TXT record for verification</span></span>
<span data-ttu-id="14e81-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="14e81-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="14e81-p106">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="14e81-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14e81-p107">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="14e81-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="14e81-141">Als u wilt beginnen, gaat u via deze [koppeling](https://portal.azure.com )naar uw domeinenpagina bij Azure.</span><span class="sxs-lookup"><span data-stu-id="14e81-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="14e81-142">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="14e81-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="14e81-144">Typ **dns-zones** met de zoekbalk op **de pagina Dashboard.** </span><span class="sxs-lookup"><span data-stu-id="14e81-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="14e81-145">Selecteer in de weergave resultaten **DNS-zones** onder het **gedeelte Services.**</span><span class="sxs-lookup"><span data-stu-id="14e81-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="14e81-146">Nadat u bent omgeleid, selecteert u het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="14e81-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="14e81-148">Selecteer op **de** pagina Instellingen voor uw domein in het **GEBIED DNS-zone** **de optie + Recordset.**</span><span class="sxs-lookup"><span data-stu-id="14e81-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="14e81-150">Selecteer in **het gebied Recordset** toevoegen in de vakken voor de nieuwe recordset de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="14e81-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="14e81-151">(Kies de **waarden Type** en **TTL-eenheid** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="14e81-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="14e81-152">**Naam**</span><span class="sxs-lookup"><span data-stu-id="14e81-152">**Name**</span></span>|<span data-ttu-id="14e81-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="14e81-153">**Type**</span></span>|<span data-ttu-id="14e81-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14e81-154">**TTL**</span></span>|<span data-ttu-id="14e81-155">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="14e81-155">**TTL unit**</span></span>|<span data-ttu-id="14e81-156">**Value**</span><span class="sxs-lookup"><span data-stu-id="14e81-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="14e81-157">TXT</span><span class="sxs-lookup"><span data-stu-id="14e81-157">TXT</span></span>  <br/> |<span data-ttu-id="14e81-158">1</span><span class="sxs-lookup"><span data-stu-id="14e81-158">1</span></span>  <br/> |<span data-ttu-id="14e81-159">Uren</span><span class="sxs-lookup"><span data-stu-id="14e81-159">Hours</span></span>  <br/> |<span data-ttu-id="14e81-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="14e81-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="14e81-161">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="14e81-161">**Note:** This is an example.</span></span> <span data-ttu-id="14e81-162">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="14e81-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="14e81-163">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="14e81-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="14e81-165">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="14e81-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="14e81-166">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="14e81-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="14e81-167">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="14e81-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="14e81-168">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="14e81-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="14e81-169">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="14e81-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="14e81-170">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="14e81-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="14e81-171">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="14e81-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="14e81-172">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="14e81-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="14e81-p111">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="14e81-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="14e81-176">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="14e81-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="14e81-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="14e81-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="14e81-178">Als u wilt beginnen, gaat u via deze [koppeling](https://portal.azure.com )naar uw domeinenpagina bij Azure.</span><span class="sxs-lookup"><span data-stu-id="14e81-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="14e81-179">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="14e81-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="14e81-181">Selecteer op **de pagina Dashboard** in het gebied Alle **resources** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="14e81-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="14e81-183">Selecteer op **de** pagina Instellingen voor uw domein in het **GEBIED DNS-zone** **de optie + Recordset.**</span><span class="sxs-lookup"><span data-stu-id="14e81-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="14e81-185">Selecteer in **het gebied Recordset** toevoegen in de vakken voor de nieuwe recordset de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="14e81-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="14e81-186">(Kies de **waarden Type** en **TTL-eenheid** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="14e81-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="14e81-187">**Naam**</span><span class="sxs-lookup"><span data-stu-id="14e81-187">**Name**</span></span>|<span data-ttu-id="14e81-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="14e81-188">**Type**</span></span>|<span data-ttu-id="14e81-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14e81-189">**TTL**</span></span>|<span data-ttu-id="14e81-190">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="14e81-190">**TTL unit**</span></span>|<span data-ttu-id="14e81-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="14e81-191">**Preference**</span></span>|<span data-ttu-id="14e81-192">**Mail Exchange**</span><span class="sxs-lookup"><span data-stu-id="14e81-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="14e81-193">MX</span><span class="sxs-lookup"><span data-stu-id="14e81-193">MX</span></span>  <br/> |<span data-ttu-id="14e81-194">1</span><span class="sxs-lookup"><span data-stu-id="14e81-194">1</span></span>  <br/> |<span data-ttu-id="14e81-195">Uren</span><span class="sxs-lookup"><span data-stu-id="14e81-195">Hours</span></span>  <br/> |<span data-ttu-id="14e81-196">10</span><span class="sxs-lookup"><span data-stu-id="14e81-196">10</span></span>  <br/> <span data-ttu-id="14e81-197">Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="14e81-197">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="14e81-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="14e81-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="14e81-199">**Opmerking:** Haal uw  *\<domain-key\>*  uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="14e81-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="14e81-200">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="14e81-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="14e81-202">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="14e81-202">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="14e81-204">Als er andere MX-records worden vermeld in de **sectie MX Records,** moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="14e81-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="14e81-205">Selecteer eerst in het **DNS-zonegebied** de **MX-recordset.**</span><span class="sxs-lookup"><span data-stu-id="14e81-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="14e81-207">Selecteer vervolgens de MX-record die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="14e81-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="14e81-209">Selecteer het **snelmenu (...)** en kies **verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="14e81-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="14e81-211">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="14e81-211">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="14e81-213">De vier CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="14e81-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="14e81-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="14e81-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="14e81-215">Als u wilt beginnen, gaat u via deze [koppeling](https://portal.azure.com )naar uw domeinenpagina bij Azure.</span><span class="sxs-lookup"><span data-stu-id="14e81-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="14e81-216">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="14e81-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="14e81-218">Selecteer op **de pagina Dashboard** in het gebied Alle **resources** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="14e81-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="14e81-220">Selecteer op **de** pagina Instellingen voor uw domein in het **GEBIED DNS-zone** **de optie + Recordset.**</span><span class="sxs-lookup"><span data-stu-id="14e81-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="14e81-222">Voeg de eerste van de vier CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="14e81-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="14e81-223">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied Add **record set** in de vakken voor de nieuwe recordset.</span><span class="sxs-lookup"><span data-stu-id="14e81-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="14e81-224">(Kies de **waarden Type** en **TTL-eenheid** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="14e81-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="14e81-225">**Naam**</span><span class="sxs-lookup"><span data-stu-id="14e81-225">**Name**</span></span>|<span data-ttu-id="14e81-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="14e81-226">**Type**</span></span>|<span data-ttu-id="14e81-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14e81-227">**TTL**</span></span>|<span data-ttu-id="14e81-228">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="14e81-228">**TTL unit**</span></span>|<span data-ttu-id="14e81-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="14e81-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14e81-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="14e81-230">autodiscover</span></span>  <br/> |<span data-ttu-id="14e81-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="14e81-231">CNAME</span></span>  <br/> |<span data-ttu-id="14e81-232">1</span><span class="sxs-lookup"><span data-stu-id="14e81-232">1</span></span>  <br/> |<span data-ttu-id="14e81-233">Uren</span><span class="sxs-lookup"><span data-stu-id="14e81-233">Hours</span></span>  <br/> |<span data-ttu-id="14e81-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="14e81-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="14e81-235">sip</span><span class="sxs-lookup"><span data-stu-id="14e81-235">sip</span></span>  <br/> |<span data-ttu-id="14e81-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="14e81-236">CNAME</span></span>  <br/> |<span data-ttu-id="14e81-237">1</span><span class="sxs-lookup"><span data-stu-id="14e81-237">1</span></span>  <br/> |<span data-ttu-id="14e81-238">Uren</span><span class="sxs-lookup"><span data-stu-id="14e81-238">Hours</span></span>  <br/> |<span data-ttu-id="14e81-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="14e81-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="14e81-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="14e81-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="14e81-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="14e81-241">CNAME</span></span>  <br/> |<span data-ttu-id="14e81-242">1</span><span class="sxs-lookup"><span data-stu-id="14e81-242">1</span></span>  <br/> |<span data-ttu-id="14e81-243">Uren</span><span class="sxs-lookup"><span data-stu-id="14e81-243">Hours</span></span>  <br/> |<span data-ttu-id="14e81-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="14e81-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="14e81-246">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="14e81-246">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="14e81-248">Voeg de andere drie CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="14e81-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="14e81-249">Selecteer in **het GEBIED DNS-zone** **de optie + Recordset**.</span><span class="sxs-lookup"><span data-stu-id="14e81-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="14e81-250">Maak vervolgens in de lege recordset een record met behulp van de waarden uit de volgende rij in de tabel en selecteer **nogmaals OK** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="14e81-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="14e81-251">Herhaal deze procedure totdat u alle vier CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="14e81-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="14e81-252">(Optioneel) Voeg 2 CNAME-records voor MDM toe.</span><span class="sxs-lookup"><span data-stu-id="14e81-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14e81-253">Als u Mobile Device Management (MDM) voor Microsoft hebt, moet u twee extra CNAME-records maken.</span><span class="sxs-lookup"><span data-stu-id="14e81-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="14e81-254">Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="14e81-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="14e81-255">(Als u geen MDM hebt, kunt u deze stap overslaan.)</span><span class="sxs-lookup"><span data-stu-id="14e81-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="14e81-256">**Naam**</span><span class="sxs-lookup"><span data-stu-id="14e81-256">**Name**</span></span>|<span data-ttu-id="14e81-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="14e81-257">**Type**</span></span>|<span data-ttu-id="14e81-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14e81-258">**TTL**</span></span>|<span data-ttu-id="14e81-259">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="14e81-259">**TTL unit**</span></span>|<span data-ttu-id="14e81-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="14e81-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14e81-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="14e81-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="14e81-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="14e81-262">CNAME</span></span>  <br/> |<span data-ttu-id="14e81-263">1</span><span class="sxs-lookup"><span data-stu-id="14e81-263">1</span></span>  <br/> |<span data-ttu-id="14e81-264">Uren</span><span class="sxs-lookup"><span data-stu-id="14e81-264">Hours</span></span>  <br/> |<span data-ttu-id="14e81-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="14e81-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="14e81-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="14e81-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="14e81-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="14e81-267">CNAME</span></span>  <br/> |<span data-ttu-id="14e81-268">1</span><span class="sxs-lookup"><span data-stu-id="14e81-268">1</span></span>  <br/> |<span data-ttu-id="14e81-269">Uren</span><span class="sxs-lookup"><span data-stu-id="14e81-269">Hours</span></span>  <br/> |<span data-ttu-id="14e81-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="14e81-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="14e81-271">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="14e81-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="14e81-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="14e81-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="14e81-273">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="14e81-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="14e81-274">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="14e81-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="14e81-275">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14e81-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="14e81-276">Voeg in plaats daarvan de vereiste Microsoft-waarden  toe aan de huidige record, zodat u één SPF-record hebt met beide sets waarden.</span><span class="sxs-lookup"><span data-stu-id="14e81-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="14e81-277">Als u wilt beginnen, gaat u via deze [koppeling](https://portal.azure.com )naar uw domeinenpagina bij Azure.</span><span class="sxs-lookup"><span data-stu-id="14e81-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="14e81-278">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="14e81-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="14e81-280">Selecteer op **de pagina Dashboard** in het gebied Alle **resources** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="14e81-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="14e81-282">Selecteer in **het GEBIED DNS-zone** de **TXT-recordset**.</span><span class="sxs-lookup"><span data-stu-id="14e81-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="14e81-284">Selecteer in **het gebied Eigenschappen** van recordset in de vakken voor de nieuwe recordset de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="14e81-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="14e81-285">(Kies de **waarden Type** en **TTL-eenheid** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="14e81-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="14e81-286">**Naam**</span><span class="sxs-lookup"><span data-stu-id="14e81-286">**Name**</span></span>|<span data-ttu-id="14e81-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="14e81-287">**Type**</span></span>|<span data-ttu-id="14e81-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14e81-288">**TTL**</span></span>|<span data-ttu-id="14e81-289">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="14e81-289">**TTL unit**</span></span>|<span data-ttu-id="14e81-290">**Value**</span><span class="sxs-lookup"><span data-stu-id="14e81-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="14e81-291">TXT</span><span class="sxs-lookup"><span data-stu-id="14e81-291">TXT</span></span>  <br/> |<span data-ttu-id="14e81-292">1</span><span class="sxs-lookup"><span data-stu-id="14e81-292">1</span></span>  <br/> |<span data-ttu-id="14e81-293">Uren</span><span class="sxs-lookup"><span data-stu-id="14e81-293">Hours</span></span>  <br/> |<span data-ttu-id="14e81-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="14e81-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="14e81-295">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="14e81-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="14e81-297">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="14e81-297">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="14e81-299">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="14e81-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="14e81-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="14e81-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="14e81-301">Als u wilt beginnen, gaat u via deze [koppeling](https://portal.azure.com )naar uw domeinenpagina bij Azure.</span><span class="sxs-lookup"><span data-stu-id="14e81-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="14e81-302">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="14e81-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="14e81-304">Selecteer op **de pagina Dashboard** in het gebied Alle **resources** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="14e81-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="14e81-306">Selecteer op **de** pagina Instellingen voor uw domein in het **GEBIED DNS-zone** **de optie + Recordset.**</span><span class="sxs-lookup"><span data-stu-id="14e81-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="14e81-308">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="14e81-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="14e81-309">Selecteer in **het gebied Recordset** toevoegen in de vakken voor de nieuwe recordset de waarden uit de eerste rij in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="14e81-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="14e81-310">(Kies de **waarden Type** en **TTL-eenheid** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="14e81-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="14e81-311">**Naam**</span><span class="sxs-lookup"><span data-stu-id="14e81-311">**Name**</span></span>|<span data-ttu-id="14e81-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="14e81-312">**Type**</span></span>|<span data-ttu-id="14e81-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14e81-313">**TTL**</span></span>|<span data-ttu-id="14e81-314">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="14e81-314">**TTL unit**</span></span>|<span data-ttu-id="14e81-315">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="14e81-315">**Priority**</span></span>|<span data-ttu-id="14e81-316">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="14e81-316">**Weight**</span></span>|<span data-ttu-id="14e81-317">**Poort**</span><span class="sxs-lookup"><span data-stu-id="14e81-317">**Port**</span></span>|<span data-ttu-id="14e81-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="14e81-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14e81-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="14e81-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="14e81-320">SRV</span><span class="sxs-lookup"><span data-stu-id="14e81-320">SRV</span></span>  <br/> |<span data-ttu-id="14e81-321">1</span><span class="sxs-lookup"><span data-stu-id="14e81-321">1</span></span>  <br/> |<span data-ttu-id="14e81-322">Uren</span><span class="sxs-lookup"><span data-stu-id="14e81-322">Hours</span></span>  <br/> |<span data-ttu-id="14e81-323">100</span><span class="sxs-lookup"><span data-stu-id="14e81-323">100</span></span>  <br/> |<span data-ttu-id="14e81-324">1</span><span class="sxs-lookup"><span data-stu-id="14e81-324">1</span></span>  <br/> |<span data-ttu-id="14e81-325">443</span><span class="sxs-lookup"><span data-stu-id="14e81-325">443</span></span>  <br/> |<span data-ttu-id="14e81-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="14e81-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="14e81-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="14e81-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="14e81-328">SRV</span><span class="sxs-lookup"><span data-stu-id="14e81-328">SRV</span></span>  <br/> |<span data-ttu-id="14e81-329">1</span><span class="sxs-lookup"><span data-stu-id="14e81-329">1</span></span>  <br/> |<span data-ttu-id="14e81-330">Uren</span><span class="sxs-lookup"><span data-stu-id="14e81-330">Hours</span></span>  <br/> |<span data-ttu-id="14e81-331">100</span><span class="sxs-lookup"><span data-stu-id="14e81-331">100</span></span>  <br/> |<span data-ttu-id="14e81-332">1</span><span class="sxs-lookup"><span data-stu-id="14e81-332">1</span></span>  <br/> |<span data-ttu-id="14e81-333">5061</span><span class="sxs-lookup"><span data-stu-id="14e81-333">5061</span></span>  <br/> |<span data-ttu-id="14e81-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="14e81-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="14e81-336">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="14e81-336">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="14e81-338">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="14e81-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="14e81-339">Typ of kopieer en plak de waarden uit de tweede rij van de tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="14e81-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="14e81-p120">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="14e81-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
