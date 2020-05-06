---
title: DNS-records maken op web.com voor Microsoft
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
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op web.com voor Microsoft.
ms.openlocfilehash: a7567688ad9935b30c0749cb7aeffdbe128506ef
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048877"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="e0c7f-103">DNS-records maken op web.com voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0c7f-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="e0c7f-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e0c7f-105">Als web.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e0c7f-106">Nadat u deze records op web.com hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="e0c7f-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e0c7f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="e0c7f-110">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="e0c7f-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="e0c7f-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="e0c7f-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0c7f-112">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="e0c7f-113">Wanneer u zich hebt aangemeld voor web.com, hebt u een domein toegevoegd met behulp van het **web.com-installatieproces.**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="e0c7f-114">Als u DNS-records voor uw domein in Microsoft wilt verifiëren en maken, moet u eerst de naamservers van uw domeinregistrar wijzigen, zodat ze de naamservers van web.com gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="e0c7f-115">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="e0c7f-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="e0c7f-116">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="e0c7f-117">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="e0c7f-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="e0c7f-118">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="e0c7f-118">First nameserver</span></span>  <br/> |<span data-ttu-id="e0c7f-119">Gebruik de naamserverwaarde van web.com.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="e0c7f-120">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="e0c7f-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="e0c7f-121">Gebruik de naamserverwaarde van web.com.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="e0c7f-122">U moet ten minste twee naamserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-122">You should use at least two name server records.</span></span> <span data-ttu-id="e0c7f-123">Als er andere naamservers worden vermeld, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="e0c7f-124">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e0c7f-125">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e0c7f-126">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e0c7f-127">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="e0c7f-127">Add a TXT record for verification</span></span>
<span data-ttu-id="e0c7f-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e0c7f-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e0c7f-p104">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e0c7f-p105">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e0c7f-133">Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="e0c7f-134">Log dan eerst in.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-134">Log in first.</span></span>
  
2. <span data-ttu-id="e0c7f-135">Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="e0c7f-136">Selecteer onder \*\*Mijn domein beheren\*\*\*de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="e0c7f-137">Klik op de pagina **Domeinnamen** onder **Tekst (TXT Records)** op **TXT Records bewerken**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="e0c7f-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-138">**Host**</span></span>|<span data-ttu-id="e0c7f-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-139">**TTL**</span></span>|<span data-ttu-id="e0c7f-140">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="e0c7f-141">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-141">3600</span></span>  <br/> |<span data-ttu-id="e0c7f-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e0c7f-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e0c7f-143">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-143">**Note:** This is an example.</span></span> <span data-ttu-id="e0c7f-144">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="e0c7f-145">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="e0c7f-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="e0c7f-146">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="e0c7f-147">Wacht een paar minuten voordat u uw nieuwe TXT-record verifieert, zodat de record die u zojuist hebt gemaakt, kan worden bijgewerkt via internet.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e0c7f-148">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e0c7f-149">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e0c7f-150">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e0c7f-151">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e0c7f-152">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e0c7f-153">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e0c7f-p108">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e0c7f-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e0c7f-157">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="e0c7f-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e0c7f-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e0c7f-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e0c7f-159">Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="e0c7f-160">Log dan eerst in.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-160">Log in first.</span></span>
  
2. <span data-ttu-id="e0c7f-161">Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="e0c7f-162">Selecteer onder \*\*Mijn domein beheren\*\*\*de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="e0c7f-163">Klik **onder Mail Servers (MX Records)** op MX Records **bewerken**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="e0c7f-164">**Priority**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-164">**Priority**</span></span>|<span data-ttu-id="e0c7f-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-165">**TTL**</span></span>|<span data-ttu-id="e0c7f-166">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="e0c7f-167">1</span><span class="sxs-lookup"><span data-stu-id="e0c7f-167">1</span></span>  <br/> <span data-ttu-id="e0c7f-168">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="e0c7f-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="e0c7f-169">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-169">3600</span></span>  <br/> |<span data-ttu-id="e0c7f-170">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e0c7f-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e0c7f-171">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="e0c7f-172">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="e0c7f-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="e0c7f-173">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="e0c7f-174">Als er andere MX-records worden vermeld in de sectie **MX Records,** schakelt u het selectievakje naast de record onder **Verwijderen**in en schakelt **u Opslaan in.**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="e0c7f-175">Selecteer **wijzigingen opslaan**in het bevestigingsscherm .</span><span class="sxs-lookup"><span data-stu-id="e0c7f-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e0c7f-176">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0c7f-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e0c7f-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e0c7f-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e0c7f-178">Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="e0c7f-179">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="e0c7f-180">Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="e0c7f-181">Selecteer onder \*\*Mijn domein beheren\*\*\*de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="e0c7f-182">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="e0c7f-183">Klik **onder Host Aliassen (CNAME Records)** op **CNAME Records bewerken**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="e0c7f-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-184">**Alias**</span></span>|<span data-ttu-id="e0c7f-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-185">**TTL**</span></span>|<span data-ttu-id="e0c7f-186">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-186">**Refers to Host Name**</span></span>|<span data-ttu-id="e0c7f-187">**Andere host**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e0c7f-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e0c7f-188">autodiscover</span></span>  <br/> |<span data-ttu-id="e0c7f-189">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-189">3600</span></span>  <br/> |<span data-ttu-id="e0c7f-190">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="e0c7f-190">@ (none)</span></span>  <br/> |<span data-ttu-id="e0c7f-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e0c7f-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="e0c7f-192">sip</span><span class="sxs-lookup"><span data-stu-id="e0c7f-192">sip</span></span>  <br/> |<span data-ttu-id="e0c7f-193">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-193">3600</span></span>  <br/> |<span data-ttu-id="e0c7f-194">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="e0c7f-194">@ (none)</span></span>  <br/> |<span data-ttu-id="e0c7f-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e0c7f-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e0c7f-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e0c7f-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e0c7f-197">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-197">3600</span></span>  <br/> |<span data-ttu-id="e0c7f-198">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="e0c7f-198">@ (none)</span></span>  <br/> | <span data-ttu-id="e0c7f-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e0c7f-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e0c7f-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e0c7f-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e0c7f-201">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-201">3600</span></span>  <br/> |<span data-ttu-id="e0c7f-202">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="e0c7f-202">@ (none)</span></span>  <br/> |<span data-ttu-id="e0c7f-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e0c7f-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="e0c7f-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e0c7f-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e0c7f-205">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-205">3600</span></span>  <br/> |<span data-ttu-id="e0c7f-206">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="e0c7f-206">@ (none)</span></span>  <br/> |<span data-ttu-id="e0c7f-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e0c7f-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="e0c7f-208">msoid</span><span class="sxs-lookup"><span data-stu-id="e0c7f-208">msoid</span></span>  <br/> |<span data-ttu-id="e0c7f-209">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-209">3600</span></span>  <br/> |<span data-ttu-id="e0c7f-210">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="e0c7f-210">@ (none)</span></span>  <br/> |<span data-ttu-id="e0c7f-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="e0c7f-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="e0c7f-212">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="e0c7f-213">Voeg als volgt de andere vijf CNAME-records toe:</span><span class="sxs-lookup"><span data-stu-id="e0c7f-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e0c7f-214">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="e0c7f-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e0c7f-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e0c7f-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0c7f-216">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e0c7f-217">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e0c7f-218">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e0c7f-219">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="e0c7f-220">Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="e0c7f-221">Log dan eerst in.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="e0c7f-222">Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="e0c7f-223">Selecteer onder \*\*Mijn domein beheren\*\*\*de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="e0c7f-224">Klik op de pagina **Domeinnamen** onder **Tekst (TXT Records)** op **TXT Records bewerken**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="e0c7f-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-225">**Host**</span></span>|<span data-ttu-id="e0c7f-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-226">**TTL**</span></span>|<span data-ttu-id="e0c7f-227">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e0c7f-228">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-228">3600</span></span>  <br/> |<span data-ttu-id="e0c7f-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e0c7f-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e0c7f-230">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="e0c7f-231">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-231">Select **Continue**.</span></span>

6. <span data-ttu-id="e0c7f-232">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e0c7f-233">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0c7f-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e0c7f-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e0c7f-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0c7f-235">Houd er rekening mee dat web.com verantwoordelijk is voor het beschikbaar maken van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="e0c7f-236">Als u discrepanties ziet tussen de onderstaande stappen en de huidige web.com GUI(Grafische gebruikersinterface), u gebruikmaken van de [web.com Community.](https://community.web.com.com/)</span><span class="sxs-lookup"><span data-stu-id="e0c7f-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="e0c7f-237">Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="e0c7f-238">Log dan eerst in.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-238">Log in first.</span></span>
      
2. <span data-ttu-id="e0c7f-239">Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="e0c7f-240">Selecteer onder \*\*Mijn domein beheren\*\*\*de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="e0c7f-241">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="e0c7f-242">Klik **onder Service (SRV Records)** op **SRV-records bewerken**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="e0c7f-243">**Service**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-243">**Service**</span></span>|<span data-ttu-id="e0c7f-244">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-244">**Protocol**</span></span>|<span data-ttu-id="e0c7f-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-245">**TTL**</span></span>|<span data-ttu-id="e0c7f-246">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-246">**Priority**</span></span>|<span data-ttu-id="e0c7f-247">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-247">**Weight**</span></span>|<span data-ttu-id="e0c7f-248">**Poort**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-248">**Port**</span></span>|<span data-ttu-id="e0c7f-249">**Target**</span><span class="sxs-lookup"><span data-stu-id="e0c7f-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e0c7f-250">_sip</span><span class="sxs-lookup"><span data-stu-id="e0c7f-250">_sip</span></span> |<span data-ttu-id="e0c7f-251">_tls</span><span class="sxs-lookup"><span data-stu-id="e0c7f-251">_tls</span></span> |<span data-ttu-id="e0c7f-252">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-252">3600</span></span> | <span data-ttu-id="e0c7f-253">100</span><span class="sxs-lookup"><span data-stu-id="e0c7f-253">100</span></span>|<span data-ttu-id="e0c7f-254">1</span><span class="sxs-lookup"><span data-stu-id="e0c7f-254">1</span></span> |<span data-ttu-id="e0c7f-255">443</span><span class="sxs-lookup"><span data-stu-id="e0c7f-255">443</span></span> |<span data-ttu-id="e0c7f-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e0c7f-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="e0c7f-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e0c7f-257">_sipfederationtls</span></span> |<span data-ttu-id="e0c7f-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="e0c7f-258">_tcp</span></span> |<span data-ttu-id="e0c7f-259">3600</span><span class="sxs-lookup"><span data-stu-id="e0c7f-259">3600</span></span> |<span data-ttu-id="e0c7f-260">100</span><span class="sxs-lookup"><span data-stu-id="e0c7f-260">100</span></span> |<span data-ttu-id="e0c7f-261">1</span><span class="sxs-lookup"><span data-stu-id="e0c7f-261">1</span></span> |<span data-ttu-id="e0c7f-262">5061</span><span class="sxs-lookup"><span data-stu-id="e0c7f-262">5061</span></span> | <span data-ttu-id="e0c7f-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e0c7f-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="e0c7f-264">Voeg de andere SRV-record toe door de waarden uit de tweede rij van de tabel te kiezen.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="e0c7f-265">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-265">Select **Continue**.</span></span>

7. <span data-ttu-id="e0c7f-266">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e0c7f-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="e0c7f-p116">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e0c7f-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
