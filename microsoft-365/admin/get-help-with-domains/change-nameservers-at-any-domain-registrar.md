---
title: Naamservers wijzigen om Microsoft 365 in te stellen bij elke domeinregistrar
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Meer informatie over het toevoegen en instellen van uw domein in Microsoft 365, zodat uw services zoals e-mail en Skype voor Bedrijven Online uw eigen domeinnaam gebruiken.
ms.openlocfilehash: 16e8699c1c8588a4368f04078fea44c165c13e29
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399990"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="910a1-103">Naamservers wijzigen om Microsoft 365 in te stellen bij elke domeinregistrar</span><span class="sxs-lookup"><span data-stu-id="910a1-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="910a1-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="910a1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="910a1-105">Controleer [Eerst uw domein instellen (hostspecifieke instructies)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) om te zien of we instructies hebben voor uw registrar.</span><span class="sxs-lookup"><span data-stu-id="910a1-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="910a1-106">Volg deze instructies om uw domein toe te voegen en in te stellen in Microsoft 365, zodat uw services zoals e-mail en Skype voor Bedrijven Online uw eigen domeinnaam gebruiken.</span><span class="sxs-lookup"><span data-stu-id="910a1-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="910a1-107">Om dit te doen, verifieert u uw domein en wijzigt u vervolgens de naamservers van uw domein in Microsoft 365, zodat de juiste DNS-records voor u kunnen worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="910a1-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="910a1-108">Voer de volgende stappen uit als in de volgende instructies uw situatie wordt beschreven:</span><span class="sxs-lookup"><span data-stu-id="910a1-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="910a1-109">U hebt uw eigen domein en wilt het instellen om te werken met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="910a1-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="910a1-110">U wilt dat Microsoft 365 uw DNS-records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="910a1-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="910a1-111">(Als u wilt, kunt u [uw eigen DNS-records beheren](../setup/add-domain.md).)</span><span class="sxs-lookup"><span data-stu-id="910a1-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="910a1-112">Een TXT- of MX-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="910a1-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="910a1-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="910a1-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="910a1-p103">U hoeft standaard slechts een van deze records te maken. De voorkeur gaat uit naar het recordtype TXT, maar deze wordt niet door alle DNS-hostingproviders ondersteund. In dat geval kunt u in plaats hiervan een MX-record maken.</span><span class="sxs-lookup"><span data-stu-id="910a1-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="910a1-p104">Voordat u uw domein met Microsoft 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="910a1-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="910a1-p105">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="910a1-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="910a1-120">Zoek het gebied op de website van uw DNS-hostingprovider waar u een nieuwe record maken</span><span class="sxs-lookup"><span data-stu-id="910a1-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="910a1-121">Meld u aan bij de website van uw DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="910a1-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="910a1-122">Selecteer uw domein.</span><span class="sxs-lookup"><span data-stu-id="910a1-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="910a1-123">Zoek de pagina waarop u DNS-records voor uw domein kunt bewerken.</span><span class="sxs-lookup"><span data-stu-id="910a1-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="910a1-124">De record maken</span><span class="sxs-lookup"><span data-stu-id="910a1-124">Create the record</span></span>

<span data-ttu-id="910a1-125">Voer een van de volgende handelingen uit, afhankelijk van of u een TXT-record of een MX-record maakt:</span><span class="sxs-lookup"><span data-stu-id="910a1-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="910a1-126">**Als u een TXT-record maakt, gebruikt u deze waarden:**</span><span class="sxs-lookup"><span data-stu-id="910a1-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="910a1-127">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="910a1-127">**Record Type**</span></span> <br/> |<span data-ttu-id="910a1-128">**Alias** of **Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="910a1-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="910a1-129">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="910a1-129">**Value**</span></span> <br/> |<span data-ttu-id="910a1-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="910a1-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="910a1-131">TXT</span><span class="sxs-lookup"><span data-stu-id="910a1-131">TXT</span></span>  <br/> |<span data-ttu-id="910a1-132">Voer een van de volgende handelingen uit: Typ **@** of laat het veld leeg, of typ de naam van uw domein.</span><span class="sxs-lookup"><span data-stu-id="910a1-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="910a1-133">> [!NOTE]> Verschillende DNS-hosts hebben verschillende vereisten voor dit veld.</span><span class="sxs-lookup"><span data-stu-id="910a1-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="910a1-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="910a1-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="910a1-135">> [!NOTE]> Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="910a1-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="910a1-136">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="910a1-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="910a1-137">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="910a1-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="910a1-138">Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.</span><span class="sxs-lookup"><span data-stu-id="910a1-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="910a1-139">**Als u een MX-record maakt, gebruikt u deze waarden:**</span><span class="sxs-lookup"><span data-stu-id="910a1-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="910a1-140">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="910a1-140">**Record Type**</span></span>|<span data-ttu-id="910a1-141">**Alias** of **Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="910a1-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="910a1-142">**Value**</span><span class="sxs-lookup"><span data-stu-id="910a1-142">**Value**</span></span>|<span data-ttu-id="910a1-143">**Priority**</span><span class="sxs-lookup"><span data-stu-id="910a1-143">**Priority**</span></span>|<span data-ttu-id="910a1-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="910a1-144">**TTL**</span></span>|
|<span data-ttu-id="910a1-145">MX</span><span class="sxs-lookup"><span data-stu-id="910a1-145">MX</span></span>|<span data-ttu-id="910a1-146">Typ **@** of uw domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="910a1-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="910a1-147">MS=ms *XXXXXXXX* > [!NOTE]> Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="910a1-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="910a1-148">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="910a1-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="910a1-149">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="910a1-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="910a1-150">Gebruik een lagere prioriteit dan de prioriteit voor bestaande MX-records voor **Prioriteit** om conflicten met de MX-record voor de e-mailstroom te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="910a1-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="910a1-151">Zie [Wat is MX-prioriteit?](../setup/domains-faq.md#what-is-mx-priority) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="910a1-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="910a1-152">Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.</span><span class="sxs-lookup"><span data-stu-id="910a1-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="910a1-153">De record opslaan</span><span class="sxs-lookup"><span data-stu-id="910a1-153">Save the record</span></span>

<span data-ttu-id="910a1-154">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="910a1-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="910a1-155">Wanneer in Microsoft 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="910a1-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="910a1-156">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="910a1-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="910a1-157">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="910a1-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="910a1-158">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="910a1-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="910a1-159">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="910a1-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="910a1-p109">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="910a1-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="910a1-163">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="910a1-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="910a1-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="910a1-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="910a1-165">Wanneer u bij de laatste stap van de wizard domeinensetup in Microsoft 365 komt, blijft er nog één taak over.</span><span class="sxs-lookup"><span data-stu-id="910a1-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="910a1-166">Als u uw domein wilt instellen met Microsoft 365-services, zoals e-mail, wijzigt u de naamserver-records (of NS) van uw domein bij uw domeinregistrar om te wijzen op de primaire en secundaire naamservers van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="910a1-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="910a1-167">Omdat Microsoft 365 uw DNS host, worden vervolgens de vereiste DNS-records voor uw services automatisch voor u ingesteld.</span><span class="sxs-lookup"><span data-stu-id="910a1-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="910a1-168">U kunt de naamserverrecords zelf bijwerken door de stappen in de Help-inhoud te volgen die uw domeinregistrar op de website heeft geplaatst.</span><span class="sxs-lookup"><span data-stu-id="910a1-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="910a1-169">Als u niet bekend bent met DNS, neemt u contact op met de ondersteuning van de domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="910a1-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="910a1-170">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, volgt u deze stappen:</span><span class="sxs-lookup"><span data-stu-id="910a1-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="910a1-171">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="910a1-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="910a1-172">Maak twee naamserverrecords, of bewerk de bestaande naamserverrecords zodat ze overeenkomen met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="910a1-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="910a1-173">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="910a1-173">First nameserver</span></span>  <br/> |<span data-ttu-id="910a1-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="910a1-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="910a1-175">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="910a1-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="910a1-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="910a1-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="910a1-177">U moet ten minste twee nameserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="910a1-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="910a1-178">Als er andere naamservers worden vermeld, u deze verwijderen of wijzigen in **ns3.bdm.microsoftonline.com** en **ns4.bdm.microsoftonline.com.**</span><span class="sxs-lookup"><span data-stu-id="910a1-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="910a1-179">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="910a1-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="910a1-180">Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft 365-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="910a1-180">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="910a1-181">Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig.</span><span class="sxs-lookup"><span data-stu-id="910a1-181">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="910a1-182">De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt.</span><span class="sxs-lookup"><span data-stu-id="910a1-182">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="910a1-183">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="910a1-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="910a1-184">Maak twee naamserverrecords, of bewerk de bestaande naamserverrecords zodat ze overeenkomen met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="910a1-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="910a1-185">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="910a1-185">First nameserver</span></span>  <br/> |<span data-ttu-id="910a1-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="910a1-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="910a1-187">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="910a1-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="910a1-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="910a1-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="910a1-189">U moet ten minste twee nameserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="910a1-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="910a1-190">Als er andere naamservers worden vermeld, u deze verwijderen of wijzigen in **ns3.dns.partner.microsoftonline.cn** en **ns4.dns.partner.microsoftonline.cn.**</span><span class="sxs-lookup"><span data-stu-id="910a1-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="910a1-191">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="910a1-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="910a1-192">Wanneer u de NS-records van uw domein wijzigt om te wijzen op de Office 365 die wordt beheerd door 21Vianet-naamservers, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="910a1-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="910a1-193">Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig.</span><span class="sxs-lookup"><span data-stu-id="910a1-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="910a1-194">De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt.</span><span class="sxs-lookup"><span data-stu-id="910a1-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="910a1-195">Hierna volgt een voorbeeld van extra stappen die mogelijk zijn vereist voor de hosting van e-mail en websites:</span><span class="sxs-lookup"><span data-stu-id="910a1-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="910a1-196">Verplaats alle e-mailadressen die uw domein gebruiken naar Microsoft 365 voordat u uw NS-records wijzigt.</span><span class="sxs-lookup"><span data-stu-id="910a1-196">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="910a1-197">Wilt u een domein toevoegen dat momenteel wordt gebruikt met een websiteadres, zoals www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="910a1-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="910a1-198">U onderstaande stappen nemen terwijl u het domein toevoegt om de website gehost te houden waar de site nu wordt gehost, zodat mensen nog steeds naar de website kunnen gaan nadat u de NS-records van het domein hebt gewijzigd om naar Microsoft 365 te wijzen.</span><span class="sxs-lookup"><span data-stu-id="910a1-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="910a1-199">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="910a1-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="910a1-200">Selecteer een domein op de pagina Domeinen.</span><span class="sxs-lookup"><span data-stu-id="910a1-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="910a1-201">Selecteer **onder DNS-instellingen** **Aangepaste records**en kies Vervolgens Nieuwe aangepaste **record**.</span><span class="sxs-lookup"><span data-stu-id="910a1-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="910a1-202">Selecteer het type DNS-record dat u wilt toevoegen en typ de gegevens voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="910a1-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="910a1-203">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="910a1-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="910a1-204">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="910a1-204">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="910a1-205">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="910a1-205">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  

