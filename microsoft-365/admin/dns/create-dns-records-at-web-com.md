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
ms.openlocfilehash: ec1d0168fb8a9dfb30d47412146777bc88f90a46
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629249"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="fcb6f-103">DNS-records maken op web.com voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fcb6f-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="fcb6f-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fcb6f-105">Als web.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="fcb6f-106">Nadat u deze records op web.com hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="fcb6f-107">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)</span><span class="sxs-lookup"><span data-stu-id="fcb6f-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="fcb6f-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fcb6f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="fcb6f-111">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="fcb6f-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="fcb6f-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="fcb6f-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcb6f-113">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="fcb6f-114">Wanneer u zich hebt aangemeld voor web.com, hebt u een domein toegevoegd met behulp van het **web.com-installatieproces.**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="fcb6f-115">Als u DNS-records voor uw domein in Microsoft wilt verifiëren en maken, moet u eerst de naamservers van uw domeinregistrar wijzigen, zodat ze de naamservers van web.com gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-115">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="fcb6f-116">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="fcb6f-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="fcb6f-117">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="fcb6f-118">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="fcb6f-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="fcb6f-119">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="fcb6f-119">First nameserver</span></span>  <br/> |<span data-ttu-id="fcb6f-120">Gebruik de naamserverwaarde van web.com.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="fcb6f-121">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="fcb6f-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="fcb6f-122">Gebruik de naamserverwaarde van web.com.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="fcb6f-123">U moet ten minste twee naamserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-123">You should use at least two name server records.</span></span> <span data-ttu-id="fcb6f-124">Als er andere naamservers worden vermeld, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="fcb6f-125">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fcb6f-126">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="fcb6f-127">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fcb6f-128">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="fcb6f-128">Add a TXT record for verification</span></span>
<span data-ttu-id="fcb6f-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="fcb6f-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="fcb6f-130">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-130">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="fcb6f-131">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-131">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fcb6f-p105">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="fcb6f-134">Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="fcb6f-135">Log dan eerst in.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-135">Log in first.</span></span>
  
2. <span data-ttu-id="fcb6f-136">Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="fcb6f-137">Selecteer onder \*\*Mijn domein beheren\*\*\*de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="fcb6f-138">Klik op de pagina **Domeinnamen** onder **Tekst (TXT Records)** op **TXT Records bewerken**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="fcb6f-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-139">**Host**</span></span>|<span data-ttu-id="fcb6f-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-140">**TTL**</span></span>|<span data-ttu-id="fcb6f-141">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="fcb6f-142">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-142">3600</span></span>  <br/> |<span data-ttu-id="fcb6f-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fcb6f-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="fcb6f-144">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-144">**Note:** This is an example.</span></span> <span data-ttu-id="fcb6f-145">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="fcb6f-146">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="fcb6f-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="fcb6f-147">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="fcb6f-148">Wacht een paar minuten voordat u uw nieuwe TXT-record verifieert, zodat de record die u zojuist hebt gemaakt, kan worden bijgewerkt via internet.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fcb6f-149">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="fcb6f-150">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fcb6f-151">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="fcb6f-152">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="fcb6f-153">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="fcb6f-154">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="fcb6f-p108">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fcb6f-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="fcb6f-158">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="fcb6f-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="fcb6f-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="fcb6f-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="fcb6f-160">Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="fcb6f-161">Log dan eerst in.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-161">Log in first.</span></span>
  
2. <span data-ttu-id="fcb6f-162">Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="fcb6f-163">Selecteer onder \*\*Mijn domein beheren\*\*\*de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="fcb6f-164">Klik **onder Mail Servers (MX Records)** op MX Records **bewerken**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="fcb6f-165">**Priority**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-165">**Priority**</span></span>|<span data-ttu-id="fcb6f-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-166">**TTL**</span></span>|<span data-ttu-id="fcb6f-167">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="fcb6f-168">1</span><span class="sxs-lookup"><span data-stu-id="fcb6f-168">1</span></span>  <br/> <span data-ttu-id="fcb6f-169">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="fcb6f-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="fcb6f-170">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-170">3600</span></span>  <br/> |<span data-ttu-id="fcb6f-171">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fcb6f-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="fcb6f-172">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="fcb6f-173">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="fcb6f-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="fcb6f-174">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="fcb6f-175">Als er andere MX-records worden vermeld in de sectie **MX Records,** schakelt u het selectievakje naast de record onder **Verwijderen**in en schakelt **u Opslaan in.**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="fcb6f-176">Selecteer **wijzigingen opslaan**in het bevestigingsscherm .</span><span class="sxs-lookup"><span data-stu-id="fcb6f-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="fcb6f-177">Voeg de zes CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fcb6f-177">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="fcb6f-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="fcb6f-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="fcb6f-179">Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="fcb6f-180">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="fcb6f-181">Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="fcb6f-182">Selecteer onder \*\*Mijn domein beheren\*\*\*de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="fcb6f-183">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="fcb6f-184">Klik **onder Host Aliassen (CNAME Records)** op **CNAME Records bewerken**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="fcb6f-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-185">**Alias**</span></span>|<span data-ttu-id="fcb6f-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-186">**TTL**</span></span>|<span data-ttu-id="fcb6f-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-187">**Refers to Host Name**</span></span>|<span data-ttu-id="fcb6f-188">**Andere host**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fcb6f-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="fcb6f-189">autodiscover</span></span>  <br/> |<span data-ttu-id="fcb6f-190">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-190">3600</span></span>  <br/> |<span data-ttu-id="fcb6f-191">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="fcb6f-191">@ (none)</span></span>  <br/> |<span data-ttu-id="fcb6f-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="fcb6f-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="fcb6f-193">sip</span><span class="sxs-lookup"><span data-stu-id="fcb6f-193">sip</span></span>  <br/> |<span data-ttu-id="fcb6f-194">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-194">3600</span></span>  <br/> |<span data-ttu-id="fcb6f-195">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="fcb6f-195">@ (none)</span></span>  <br/> |<span data-ttu-id="fcb6f-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fcb6f-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fcb6f-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fcb6f-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="fcb6f-198">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-198">3600</span></span>  <br/> |<span data-ttu-id="fcb6f-199">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="fcb6f-199">@ (none)</span></span>  <br/> | <span data-ttu-id="fcb6f-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fcb6f-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="fcb6f-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="fcb6f-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="fcb6f-202">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-202">3600</span></span>  <br/> |<span data-ttu-id="fcb6f-203">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="fcb6f-203">@ (none)</span></span>  <br/> |<span data-ttu-id="fcb6f-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="fcb6f-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="fcb6f-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="fcb6f-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="fcb6f-206">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-206">3600</span></span>  <br/> |<span data-ttu-id="fcb6f-207">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="fcb6f-207">@ (none)</span></span>  <br/> |<span data-ttu-id="fcb6f-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fcb6f-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="fcb6f-209">msoid</span><span class="sxs-lookup"><span data-stu-id="fcb6f-209">msoid</span></span>  <br/> |<span data-ttu-id="fcb6f-210">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-210">3600</span></span>  <br/> |<span data-ttu-id="fcb6f-211">@ (geen)</span><span class="sxs-lookup"><span data-stu-id="fcb6f-211">@ (none)</span></span>  <br/> |<span data-ttu-id="fcb6f-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="fcb6f-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="fcb6f-213">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="fcb6f-214">Voeg als volgt de andere vijf CNAME-records toe:</span><span class="sxs-lookup"><span data-stu-id="fcb6f-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="fcb6f-215">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="fcb6f-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="fcb6f-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="fcb6f-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcb6f-217">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="fcb6f-218">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="fcb6f-219">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="fcb6f-220">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="fcb6f-221">Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="fcb6f-222">Log dan eerst in.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="fcb6f-223">Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="fcb6f-224">Selecteer onder \*\*Mijn domein beheren\*\*\*de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="fcb6f-225">Klik op de pagina **Domeinnamen** onder **Tekst (TXT Records)** op **TXT Records bewerken**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="fcb6f-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-226">**Host**</span></span>|<span data-ttu-id="fcb6f-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-227">**TTL**</span></span>|<span data-ttu-id="fcb6f-228">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="fcb6f-229">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-229">3600</span></span>  <br/> |<span data-ttu-id="fcb6f-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="fcb6f-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="fcb6f-231">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="fcb6f-232">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-232">Select **Continue**.</span></span>

6. <span data-ttu-id="fcb6f-233">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="fcb6f-234">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="fcb6f-234">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="fcb6f-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="fcb6f-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcb6f-236">Houd er rekening mee dat web.com verantwoordelijk is voor het beschikbaar maken van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="fcb6f-237">Als u discrepanties ziet tussen de onderstaande stappen en de huidige web.com GUI(Grafische gebruikersinterface), u gebruikmaken van de [web.com Community.](https://community.web.com.com/)</span><span class="sxs-lookup"><span data-stu-id="fcb6f-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="fcb6f-238">Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="fcb6f-239">Log dan eerst in.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-239">Log in first.</span></span>
      
2. <span data-ttu-id="fcb6f-240">Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="fcb6f-241">Selecteer onder \*\*Mijn domein beheren\*\*\*de optie **Geavanceerde DNS-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="fcb6f-242">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="fcb6f-243">Klik **onder Service (SRV Records)** op **SRV-records bewerken**en selecteer de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="fcb6f-244">**Service**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-244">**Service**</span></span>|<span data-ttu-id="fcb6f-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-245">**Protocol**</span></span>|<span data-ttu-id="fcb6f-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-246">**TTL**</span></span>|<span data-ttu-id="fcb6f-247">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-247">**Priority**</span></span>|<span data-ttu-id="fcb6f-248">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-248">**Weight**</span></span>|<span data-ttu-id="fcb6f-249">**Poort**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-249">**Port**</span></span>|<span data-ttu-id="fcb6f-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="fcb6f-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fcb6f-251">_sip</span><span class="sxs-lookup"><span data-stu-id="fcb6f-251">_sip</span></span> |<span data-ttu-id="fcb6f-252">_tls</span><span class="sxs-lookup"><span data-stu-id="fcb6f-252">_tls</span></span> |<span data-ttu-id="fcb6f-253">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-253">3600</span></span> | <span data-ttu-id="fcb6f-254">100</span><span class="sxs-lookup"><span data-stu-id="fcb6f-254">100</span></span>|<span data-ttu-id="fcb6f-255">1</span><span class="sxs-lookup"><span data-stu-id="fcb6f-255">1</span></span> |<span data-ttu-id="fcb6f-256">443</span><span class="sxs-lookup"><span data-stu-id="fcb6f-256">443</span></span> |<span data-ttu-id="fcb6f-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fcb6f-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="fcb6f-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="fcb6f-258">_sipfederationtls</span></span> |<span data-ttu-id="fcb6f-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="fcb6f-259">_tcp</span></span> |<span data-ttu-id="fcb6f-260">3600</span><span class="sxs-lookup"><span data-stu-id="fcb6f-260">3600</span></span> |<span data-ttu-id="fcb6f-261">100</span><span class="sxs-lookup"><span data-stu-id="fcb6f-261">100</span></span> |<span data-ttu-id="fcb6f-262">1</span><span class="sxs-lookup"><span data-stu-id="fcb6f-262">1</span></span> |<span data-ttu-id="fcb6f-263">5061</span><span class="sxs-lookup"><span data-stu-id="fcb6f-263">5061</span></span> | <span data-ttu-id="fcb6f-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fcb6f-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="fcb6f-265">Voeg de andere SRV-record toe door de waarden uit de tweede rij van de tabel te kiezen.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="fcb6f-266">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-266">Select **Continue**.</span></span>

7. <span data-ttu-id="fcb6f-267">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fcb6f-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="fcb6f-p116">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fcb6f-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
