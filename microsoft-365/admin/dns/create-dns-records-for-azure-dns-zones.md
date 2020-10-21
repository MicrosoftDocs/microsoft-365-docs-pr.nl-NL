---
title: DNS-records voor Azure DNS-zones maken
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
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Azure DNS-zones voor Microsoft.
ms.openlocfilehash: 40fadb81ebd0ae5385bbbdad727b1c579142b227
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645669"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="341fc-103">DNS-records voor Azure DNS-zones maken</span><span class="sxs-lookup"><span data-stu-id="341fc-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="341fc-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="341fc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="341fc-105">Als Azure uw DNS-hosting provider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor bedrijven online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="341fc-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="341fc-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="341fc-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="341fc-107">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="341fc-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="341fc-108">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="341fc-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="341fc-109">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="341fc-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="341fc-110">De vier CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="341fc-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="341fc-111">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="341fc-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="341fc-112">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="341fc-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="341fc-113">Nadat u deze records bij Azure hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="341fc-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="341fc-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="341fc-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="341fc-117">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="341fc-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="341fc-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="341fc-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="341fc-119">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="341fc-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="341fc-120">Toen u zich registreerde voor Azure, hebt u een resourcegroep gemaakt in een DNS-zone en hebt u vervolgens uw domeinnaam aan die resourcegroep toegewezen.</span><span class="sxs-lookup"><span data-stu-id="341fc-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="341fc-121">Deze domeinnaam is geregistreerd bij een externe domeinregistratie; Azure biedt geen Domain Registration Services.</span><span class="sxs-lookup"><span data-stu-id="341fc-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="341fc-122">Als u DNS-records voor uw domein wilt controleren en maken in Microsoft, moet u eerst de naamservers van uw domeinregistratie wijzigen, zodat ze de Azure naamservers gebruiken die aan de resourcegroep is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="341fc-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="341fc-123">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="341fc-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="341fc-124">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="341fc-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="341fc-125">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="341fc-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="341fc-126">Hieronder ziet u een voorbeeld van de aan Azure toegewezen naamservers.</span><span class="sxs-lookup"><span data-stu-id="341fc-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="341fc-127">**Eerste naamserver:** Gebruik de waarde van name server die is toegewezen door Azure.</span><span class="sxs-lookup"><span data-stu-id="341fc-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="341fc-128">**Tweede naamserver:** Gebruik de waarde van name server die is toegewezen door Azure.</span><span class="sxs-lookup"><span data-stu-id="341fc-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Afbeelding van Azure-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="341fc-130">U dient ten minste twee naamserver records te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="341fc-130">You should use at least two name server records.</span></span> <span data-ttu-id="341fc-131">Als er andere naamservers worden weergegeven op de website van uw domeinregistratie, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="341fc-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="341fc-132">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="341fc-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="341fc-133">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="341fc-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="341fc-134">Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="341fc-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="341fc-135">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="341fc-135">Add a TXT record for verification</span></span>
<span data-ttu-id="341fc-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="341fc-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="341fc-p106">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="341fc-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="341fc-p107">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="341fc-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="341fc-141">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Azure met [deze koppeling](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="341fc-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="341fc-142">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="341fc-142">You'll be prompted to log in first.</span></span>
    
    ![1-1-](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="341fc-144">Gebruik de **zoekbalk** op de **Dashboard** -pagina en typ **DNS zones**.</span><span class="sxs-lookup"><span data-stu-id="341fc-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="341fc-145">Selecteer in de weergave resultaten de optie **DNS zones** onder het onderdeel **Services** .</span><span class="sxs-lookup"><span data-stu-id="341fc-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="341fc-146">Als u het domein hebt doorgestuurd, selecteert u het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="341fc-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![1-2-](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="341fc-148">Selecteer op de pagina **instellingen** voor uw domein in het gebied **DNS-zone** de optie **+ record set**.</span><span class="sxs-lookup"><span data-stu-id="341fc-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![1-3-](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="341fc-150">Selecteer in het gebied **Add Record set** de waarden uit de volgende tabel in de vakken voor de nieuwe recordset.</span><span class="sxs-lookup"><span data-stu-id="341fc-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="341fc-151">(Kies in de vervolgkeuzelijsten de waarden **type** en **TTL** .)</span><span class="sxs-lookup"><span data-stu-id="341fc-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="341fc-152">**Naam**</span><span class="sxs-lookup"><span data-stu-id="341fc-152">**Name**</span></span>|<span data-ttu-id="341fc-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="341fc-153">**Type**</span></span>|<span data-ttu-id="341fc-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="341fc-154">**TTL**</span></span>|<span data-ttu-id="341fc-155">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="341fc-155">**TTL unit**</span></span>|<span data-ttu-id="341fc-156">**Value**</span><span class="sxs-lookup"><span data-stu-id="341fc-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="341fc-157">TXT</span><span class="sxs-lookup"><span data-stu-id="341fc-157">TXT</span></span>  <br/> |<span data-ttu-id="341fc-158">1</span><span class="sxs-lookup"><span data-stu-id="341fc-158">1</span></span>  <br/> |<span data-ttu-id="341fc-159">Uren</span><span class="sxs-lookup"><span data-stu-id="341fc-159">Hours</span></span>  <br/> |<span data-ttu-id="341fc-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="341fc-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="341fc-161">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="341fc-161">**Note:** This is an example.</span></span> <span data-ttu-id="341fc-162">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="341fc-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="341fc-163">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="341fc-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Controle van Azure 1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="341fc-165">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="341fc-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="341fc-166">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="341fc-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="341fc-167">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="341fc-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="341fc-168">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="341fc-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="341fc-169">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="341fc-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="341fc-170">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="341fc-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="341fc-171">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="341fc-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="341fc-172">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="341fc-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="341fc-p111">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="341fc-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="341fc-176">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="341fc-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="341fc-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="341fc-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="341fc-178">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Azure met [deze koppeling](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="341fc-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="341fc-179">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="341fc-179">You'll be prompted to log in first.</span></span>
    
    ![1-1-](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="341fc-181">Selecteer op de pagina **Dashboard** , in het gebied **all resources** , het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="341fc-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![1-2-](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="341fc-183">Selecteer op de pagina **instellingen** voor uw domein in het gebied **DNS-zone** de optie **+ record set**.</span><span class="sxs-lookup"><span data-stu-id="341fc-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![1-3-](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="341fc-185">Selecteer in het gebied **Add Record set** de waarden uit de volgende tabel in de vakken voor de nieuwe recordset.</span><span class="sxs-lookup"><span data-stu-id="341fc-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="341fc-186">(Kies in de vervolgkeuzelijsten de waarden **type** en **TTL** .)</span><span class="sxs-lookup"><span data-stu-id="341fc-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="341fc-187">**Naam**</span><span class="sxs-lookup"><span data-stu-id="341fc-187">**Name**</span></span>|<span data-ttu-id="341fc-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="341fc-188">**Type**</span></span>|<span data-ttu-id="341fc-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="341fc-189">**TTL**</span></span>|<span data-ttu-id="341fc-190">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="341fc-190">**TTL unit**</span></span>|<span data-ttu-id="341fc-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="341fc-191">**Preference**</span></span>|<span data-ttu-id="341fc-192">**E-mail uitwisselen**</span><span class="sxs-lookup"><span data-stu-id="341fc-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="341fc-193">MX</span><span class="sxs-lookup"><span data-stu-id="341fc-193">MX</span></span>  <br/> |<span data-ttu-id="341fc-194">1</span><span class="sxs-lookup"><span data-stu-id="341fc-194">1</span></span>  <br/> |<span data-ttu-id="341fc-195">Uren</span><span class="sxs-lookup"><span data-stu-id="341fc-195">Hours</span></span>  <br/> |<span data-ttu-id="341fc-196">10</span><span class="sxs-lookup"><span data-stu-id="341fc-196">10</span></span>  <br/> <span data-ttu-id="341fc-197">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="341fc-197">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="341fc-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="341fc-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="341fc-199">**Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="341fc-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="341fc-200">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="341fc-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![2-1-](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="341fc-202">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="341fc-202">Select **OK**.</span></span>
    
    ![2-2-](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="341fc-204">Als er andere MX-records worden vermeld in de sectie **MX records** , moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="341fc-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="341fc-205">Selecteer eerst de **MX-recordset**in het gebied **DNS zone** .</span><span class="sxs-lookup"><span data-stu-id="341fc-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![2-3-](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="341fc-207">Vervolgens selecteert u de MX-record die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="341fc-207">Next, select the MX record you want to delete.</span></span>
    
    ![2-4-](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="341fc-209">Selecteer het **context menu (...)** en kies vervolgens **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="341fc-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![2-5-](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="341fc-211">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="341fc-211">Select **Save**.</span></span>
    
    ![2-6-](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="341fc-213">De vier CNAME-records toevoegen die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="341fc-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="341fc-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="341fc-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="341fc-215">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Azure met [deze koppeling](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="341fc-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="341fc-216">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="341fc-216">You'll be prompted to log in first.</span></span>
    
    ![1-1-](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="341fc-218">Selecteer op de pagina **Dashboard** , in het gebied **all resources** , het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="341fc-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![1-2-](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="341fc-220">Selecteer op de pagina **instellingen** voor uw domein in het gebied **DNS-zone** de optie **+ record set**.</span><span class="sxs-lookup"><span data-stu-id="341fc-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![1-3-](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="341fc-222">Voeg de eerste van de vier CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="341fc-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="341fc-223">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add Record set** in de vakken voor de nieuwe recordset.</span><span class="sxs-lookup"><span data-stu-id="341fc-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="341fc-224">(Kies in de vervolgkeuzelijsten de waarden **type** en **TTL** .)</span><span class="sxs-lookup"><span data-stu-id="341fc-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="341fc-225">**Naam**</span><span class="sxs-lookup"><span data-stu-id="341fc-225">**Name**</span></span>|<span data-ttu-id="341fc-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="341fc-226">**Type**</span></span>|<span data-ttu-id="341fc-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="341fc-227">**TTL**</span></span>|<span data-ttu-id="341fc-228">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="341fc-228">**TTL unit**</span></span>|<span data-ttu-id="341fc-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="341fc-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="341fc-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="341fc-230">autodiscover</span></span>  <br/> |<span data-ttu-id="341fc-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="341fc-231">CNAME</span></span>  <br/> |<span data-ttu-id="341fc-232">1</span><span class="sxs-lookup"><span data-stu-id="341fc-232">1</span></span>  <br/> |<span data-ttu-id="341fc-233">Uren</span><span class="sxs-lookup"><span data-stu-id="341fc-233">Hours</span></span>  <br/> |<span data-ttu-id="341fc-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="341fc-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="341fc-235">sip</span><span class="sxs-lookup"><span data-stu-id="341fc-235">sip</span></span>  <br/> |<span data-ttu-id="341fc-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="341fc-236">CNAME</span></span>  <br/> |<span data-ttu-id="341fc-237">1</span><span class="sxs-lookup"><span data-stu-id="341fc-237">1</span></span>  <br/> |<span data-ttu-id="341fc-238">Uren</span><span class="sxs-lookup"><span data-stu-id="341fc-238">Hours</span></span>  <br/> |<span data-ttu-id="341fc-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="341fc-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="341fc-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="341fc-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="341fc-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="341fc-241">CNAME</span></span>  <br/> |<span data-ttu-id="341fc-242">1</span><span class="sxs-lookup"><span data-stu-id="341fc-242">1</span></span>  <br/> |<span data-ttu-id="341fc-243">Uren</span><span class="sxs-lookup"><span data-stu-id="341fc-243">Hours</span></span>  <br/> |<span data-ttu-id="341fc-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="341fc-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![3-1-](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="341fc-246">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="341fc-246">Select **OK**.</span></span>
    
    ![3-2-](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="341fc-248">Voeg de andere drie CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="341fc-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="341fc-249">Selecteer in het gebied **DNS zone** de optie **+ record set**.</span><span class="sxs-lookup"><span data-stu-id="341fc-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="341fc-250">Maak vervolgens een record met behulp van de waarden uit de volgende rij in de tabel en selecteer **OK** om de record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="341fc-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="341fc-251">Herhaal deze procedure totdat u alle vier CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="341fc-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="341fc-252">Option Twee CNAME-records voor MDM toevoegen.</span><span class="sxs-lookup"><span data-stu-id="341fc-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="341fc-253">Als u over MDM (Mobile Device Management) voor Microsoft beschikt, moet u twee extra CNAME-records maken.</span><span class="sxs-lookup"><span data-stu-id="341fc-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="341fc-254">Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="341fc-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="341fc-255">(Als u geen MDM hebt, kunt u deze stap overslaan.)</span><span class="sxs-lookup"><span data-stu-id="341fc-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="341fc-256">**Naam**</span><span class="sxs-lookup"><span data-stu-id="341fc-256">**Name**</span></span>|<span data-ttu-id="341fc-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="341fc-257">**Type**</span></span>|<span data-ttu-id="341fc-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="341fc-258">**TTL**</span></span>|<span data-ttu-id="341fc-259">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="341fc-259">**TTL unit**</span></span>|<span data-ttu-id="341fc-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="341fc-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="341fc-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="341fc-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="341fc-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="341fc-262">CNAME</span></span>  <br/> |<span data-ttu-id="341fc-263">1</span><span class="sxs-lookup"><span data-stu-id="341fc-263">1</span></span>  <br/> |<span data-ttu-id="341fc-264">Uren</span><span class="sxs-lookup"><span data-stu-id="341fc-264">Hours</span></span>  <br/> |<span data-ttu-id="341fc-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="341fc-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="341fc-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="341fc-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="341fc-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="341fc-267">CNAME</span></span>  <br/> |<span data-ttu-id="341fc-268">1</span><span class="sxs-lookup"><span data-stu-id="341fc-268">1</span></span>  <br/> |<span data-ttu-id="341fc-269">Uren</span><span class="sxs-lookup"><span data-stu-id="341fc-269">Hours</span></span>  <br/> |<span data-ttu-id="341fc-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="341fc-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="341fc-271">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="341fc-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="341fc-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="341fc-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="341fc-273">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="341fc-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="341fc-274">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="341fc-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="341fc-275">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="341fc-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="341fc-276">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="341fc-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="341fc-277">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Azure met [deze koppeling](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="341fc-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="341fc-278">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="341fc-278">You'll be prompted to log in first.</span></span>
    
    ![1-1-](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="341fc-280">Selecteer op de pagina **Dashboard** , in het gebied **all resources** , het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="341fc-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![1-2-](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="341fc-282">Selecteer in het gebied **DNS zone** de **txt recordset**.</span><span class="sxs-lookup"><span data-stu-id="341fc-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![4-1-](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="341fc-284">Selecteer in het gebied **eigenschappenset** van de record de waarden uit de volgende tabel in de vakken voor de nieuwe record set.</span><span class="sxs-lookup"><span data-stu-id="341fc-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="341fc-285">(Kies in de vervolgkeuzelijsten de waarden **type** en **TTL** .)</span><span class="sxs-lookup"><span data-stu-id="341fc-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="341fc-286">**Naam**</span><span class="sxs-lookup"><span data-stu-id="341fc-286">**Name**</span></span>|<span data-ttu-id="341fc-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="341fc-287">**Type**</span></span>|<span data-ttu-id="341fc-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="341fc-288">**TTL**</span></span>|<span data-ttu-id="341fc-289">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="341fc-289">**TTL unit**</span></span>|<span data-ttu-id="341fc-290">**Value**</span><span class="sxs-lookup"><span data-stu-id="341fc-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="341fc-291">TXT</span><span class="sxs-lookup"><span data-stu-id="341fc-291">TXT</span></span>  <br/> |<span data-ttu-id="341fc-292">1</span><span class="sxs-lookup"><span data-stu-id="341fc-292">1</span></span>  <br/> |<span data-ttu-id="341fc-293">Uren</span><span class="sxs-lookup"><span data-stu-id="341fc-293">Hours</span></span>  <br/> |<span data-ttu-id="341fc-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="341fc-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="341fc-295">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="341fc-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![4-2-](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="341fc-297">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="341fc-297">Select **Save**.</span></span>
    
    ![4-3-](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="341fc-299">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="341fc-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="341fc-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="341fc-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="341fc-301">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Azure met [deze koppeling](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="341fc-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="341fc-302">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="341fc-302">You'll be prompted to log in first.</span></span>
    
    ![1-1-](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="341fc-304">Selecteer op de pagina **Dashboard** , in het gebied **all resources** , het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="341fc-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![1-2-](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="341fc-306">Selecteer op de pagina **instellingen** voor uw domein in het gebied **DNS-zone** de optie **+ record set**.</span><span class="sxs-lookup"><span data-stu-id="341fc-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![1-3-](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="341fc-308">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="341fc-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="341fc-309">Selecteer in het gebied **Add Record set** de waarden uit de eerste rij in de volgende tabel in de vakken voor de nieuwe recordset.</span><span class="sxs-lookup"><span data-stu-id="341fc-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="341fc-310">(Kies in de vervolgkeuzelijsten de waarden **type** en **TTL** .)</span><span class="sxs-lookup"><span data-stu-id="341fc-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="341fc-311">**Naam**</span><span class="sxs-lookup"><span data-stu-id="341fc-311">**Name**</span></span>|<span data-ttu-id="341fc-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="341fc-312">**Type**</span></span>|<span data-ttu-id="341fc-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="341fc-313">**TTL**</span></span>|<span data-ttu-id="341fc-314">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="341fc-314">**TTL unit**</span></span>|<span data-ttu-id="341fc-315">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="341fc-315">**Priority**</span></span>|<span data-ttu-id="341fc-316">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="341fc-316">**Weight**</span></span>|<span data-ttu-id="341fc-317">**Poort**</span><span class="sxs-lookup"><span data-stu-id="341fc-317">**Port**</span></span>|<span data-ttu-id="341fc-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="341fc-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="341fc-319">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="341fc-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="341fc-320">SRV</span><span class="sxs-lookup"><span data-stu-id="341fc-320">SRV</span></span>  <br/> |<span data-ttu-id="341fc-321">1</span><span class="sxs-lookup"><span data-stu-id="341fc-321">1</span></span>  <br/> |<span data-ttu-id="341fc-322">Uren</span><span class="sxs-lookup"><span data-stu-id="341fc-322">Hours</span></span>  <br/> |<span data-ttu-id="341fc-323">100</span><span class="sxs-lookup"><span data-stu-id="341fc-323">100</span></span>  <br/> |<span data-ttu-id="341fc-324">1</span><span class="sxs-lookup"><span data-stu-id="341fc-324">1</span></span>  <br/> |<span data-ttu-id="341fc-325">443</span><span class="sxs-lookup"><span data-stu-id="341fc-325">443</span></span>  <br/> |<span data-ttu-id="341fc-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="341fc-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="341fc-327">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="341fc-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="341fc-328">SRV</span><span class="sxs-lookup"><span data-stu-id="341fc-328">SRV</span></span>  <br/> |<span data-ttu-id="341fc-329">1</span><span class="sxs-lookup"><span data-stu-id="341fc-329">1</span></span>  <br/> |<span data-ttu-id="341fc-330">Uren</span><span class="sxs-lookup"><span data-stu-id="341fc-330">Hours</span></span>  <br/> |<span data-ttu-id="341fc-331">100</span><span class="sxs-lookup"><span data-stu-id="341fc-331">100</span></span>  <br/> |<span data-ttu-id="341fc-332">1</span><span class="sxs-lookup"><span data-stu-id="341fc-332">1</span></span>  <br/> |<span data-ttu-id="341fc-333">5061</span><span class="sxs-lookup"><span data-stu-id="341fc-333">5061</span></span>  <br/> |<span data-ttu-id="341fc-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="341fc-334">sipfed.online.lync.com</span></span>  <br/> 

    ![5-1-](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="341fc-336">Selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="341fc-336">Select **OK**.</span></span>
    
    ![5-2-](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="341fc-338">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="341fc-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="341fc-339">Typ of kopieer en plak de waarden uit de tweede rij van de tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="341fc-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="341fc-p120">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="341fc-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
