---
title: Naamservers wijzigen voor het instellen van Microsoft 365 domeinregistrar
f1.keywords:
- CSH
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
description: Meer informatie over het toevoegen en instellen van uw domein in Microsoft 365 zodat uw services zoals e-mail en Skype voor Bedrijven Online uw eigen domeinnaam gebruiken.
ms.openlocfilehash: 7f1ade6cb3013126fb011fe9232b3b4c2e9a82d4
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683125"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="a515f-103">Naamservers wijzigen voor het instellen van Microsoft 365 domeinregistrar</span><span class="sxs-lookup"><span data-stu-id="a515f-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="a515f-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="a515f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a515f-105">Volg deze instructies voor het toevoegen en instellen van uw domein in Microsoft 365 zodat uw services zoals e-mail en Teams uw eigen domeinnaam gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a515f-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="a515f-106">Hiervoor verifieert u uw domein en wijzigt u de naamservers van uw domein in Microsoft 365 zodat de juiste DNS-records voor u kunnen worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="a515f-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="a515f-107">Volg deze stappen als in de volgende instructies uw situatie wordt beschreven:</span><span class="sxs-lookup"><span data-stu-id="a515f-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="a515f-108">U hebt uw eigen domein en wilt dit instellen voor het werken met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a515f-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="a515f-109">U wilt Microsoft 365 dns-records voor u beheren.</span><span class="sxs-lookup"><span data-stu-id="a515f-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="a515f-110">(Als u wilt, kunt u [uw eigen DNS-records beheren](../setup/add-domain.md).)</span><span class="sxs-lookup"><span data-stu-id="a515f-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="a515f-111">Een TXT- of MX-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="a515f-111">Add a TXT or MX record for verification</span></span>

> [!NOTE]
> <span data-ttu-id="a515f-p103">U hoeft standaard slechts een van deze records te maken. De voorkeur gaat uit naar het recordtype TXT, maar deze wordt niet door alle DNS-hostingproviders ondersteund. In dat geval kunt u in plaats hiervan een MX-record maken.</span><span class="sxs-lookup"><span data-stu-id="a515f-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="a515f-p104">Voordat u uw domein met Microsoft 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="a515f-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a515f-p105">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a515f-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="a515f-118">Zoek het gebied op de website van uw DNS-hostingprovider waar u een nieuwe record kunt maken</span><span class="sxs-lookup"><span data-stu-id="a515f-118">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="a515f-119">Meld u aan bij de website van uw DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="a515f-119">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="a515f-120">Selecteer uw domein.</span><span class="sxs-lookup"><span data-stu-id="a515f-120">Choose your domain.</span></span>
    
3. <span data-ttu-id="a515f-121">Zoek de pagina waarop u DNS-records voor uw domein kunt bewerken.</span><span class="sxs-lookup"><span data-stu-id="a515f-121">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="a515f-122">De record maken</span><span class="sxs-lookup"><span data-stu-id="a515f-122">Create the record</span></span>

<span data-ttu-id="a515f-123">Voer een van de volgende handelingen uit, afhankelijk van of u een TXT-record of een MX-record maakt:</span><span class="sxs-lookup"><span data-stu-id="a515f-123">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="a515f-124">**Als u een TXT-record maakt, gebruikt u deze waarden:**</span><span class="sxs-lookup"><span data-stu-id="a515f-124">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a515f-125">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="a515f-125">**Record Type**</span></span> <br/> |<span data-ttu-id="a515f-126">**Alias** of **Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="a515f-126">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="a515f-127">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="a515f-127">**Value**</span></span> <br/> |<span data-ttu-id="a515f-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a515f-128">**TTL**</span></span> <br/> |
|<span data-ttu-id="a515f-129">TXT</span><span class="sxs-lookup"><span data-stu-id="a515f-129">TXT</span></span>  <br/> |<span data-ttu-id="a515f-130">Voer een van de volgende handelingen uit: Typ **@** of laat het veld leeg, of typ de naam van uw domein.</span><span class="sxs-lookup"><span data-stu-id="a515f-130">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="a515f-131">> [!NOTE]> Verschillende DNS-hosts hebben verschillende vereisten voor dit veld.</span><span class="sxs-lookup"><span data-stu-id="a515f-131">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="a515f-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a515f-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a515f-133">> [!NOTE]> Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="a515f-133">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="a515f-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a515f-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="a515f-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="a515f-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a515f-136">Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.</span><span class="sxs-lookup"><span data-stu-id="a515f-136">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="a515f-137">**Als u een MX-record maakt, gebruikt u deze waarden:**</span><span class="sxs-lookup"><span data-stu-id="a515f-137">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a515f-138">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="a515f-138">**Record Type**</span></span>|<span data-ttu-id="a515f-139">**Alias** of **Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="a515f-139">**Alias** or **Host Name**</span></span>|<span data-ttu-id="a515f-140">**Value**</span><span class="sxs-lookup"><span data-stu-id="a515f-140">**Value**</span></span>|<span data-ttu-id="a515f-141">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a515f-141">**Priority**</span></span>|<span data-ttu-id="a515f-142">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a515f-142">**TTL**</span></span>|
|<span data-ttu-id="a515f-143">MX</span><span class="sxs-lookup"><span data-stu-id="a515f-143">MX</span></span>|<span data-ttu-id="a515f-144">Typ **@** of uw domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="a515f-144">Type either **@** or your domain name.</span></span> |<span data-ttu-id="a515f-145">MS=ms *XXXXXXXX* > [!NOTE]> Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="a515f-145">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="a515f-146">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a515f-146">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="a515f-147">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="a515f-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a515f-148">Gebruik een lagere prioriteit dan de prioriteit voor bestaande MX-records voor **Prioriteit** om conflicten met de MX-record voor de e-mailstroom te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="a515f-148">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="a515f-149">Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="a515f-149">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="a515f-150">Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.</span><span class="sxs-lookup"><span data-stu-id="a515f-150">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="a515f-151">De record opslaan</span><span class="sxs-lookup"><span data-stu-id="a515f-151">Save the record</span></span>

<span data-ttu-id="a515f-152">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="a515f-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="a515f-153">Wanneer in Microsoft 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="a515f-153">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="a515f-154">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="a515f-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a515f-155">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="a515f-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="a515f-156">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="a515f-156">On the **Setup** page, select **Start setup**.</span></span>
 
  
4. <span data-ttu-id="a515f-157">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="a515f-157">On the **Verify domain** page, select **Verify**.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a515f-p109">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a515f-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a515f-161">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="a515f-161">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="a515f-162">Wanneer u bij de laatste stap van de wizard Domeinen instellen in Microsoft 365, hebt u nog één taak over.</span><span class="sxs-lookup"><span data-stu-id="a515f-162">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="a515f-163">Als u uw domein wilt instellen met Microsoft 365-services, zoals e-mail, wijzigt u de naamserverrecords van uw domein (of NS) bij uw domeinregistrar om te wijzen naar de Microsoft 365 primaire en secundaire naamservers.</span><span class="sxs-lookup"><span data-stu-id="a515f-163">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="a515f-164">Omdat u Microsoft 365 DNS host, worden de vereiste DNS-records voor uw services automatisch voor u ingesteld.</span><span class="sxs-lookup"><span data-stu-id="a515f-164">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="a515f-165">U kunt de naamserverrecords zelf bijwerken door de stappen in de Help-inhoud te volgen die uw domeinregistrar op de website heeft geplaatst.</span><span class="sxs-lookup"><span data-stu-id="a515f-165">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="a515f-166">Als u niet bekend bent met DNS, neemt u contact op met de ondersteuning van de domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="a515f-166">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="a515f-167">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, volgt u deze stappen:</span><span class="sxs-lookup"><span data-stu-id="a515f-167">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="a515f-168">Zoek het gebied op de website van de domeinregistrar waar u de naamservers voor uw domein of een gebied kunt wijzigen waar u aangepaste naamservers kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a515f-168">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="a515f-169">Maak naamserverrecords of bewerk de bestaande naamserverrecords om aan de volgende waarden te komen:</span><span class="sxs-lookup"><span data-stu-id="a515f-169">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="a515f-170">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="a515f-170">First nameserver</span></span>  <br/> |<span data-ttu-id="a515f-171">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a515f-171">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a515f-172">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="a515f-172">Second nameserver</span></span>  <br/> |<span data-ttu-id="a515f-173">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a515f-173">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a515f-174">Derde naamserver</span><span class="sxs-lookup"><span data-stu-id="a515f-174">Third nameserver</span></span>  <br/> |<span data-ttu-id="a515f-175">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a515f-175">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a515f-176">Vierde naamserver</span><span class="sxs-lookup"><span data-stu-id="a515f-176">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="a515f-177">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a515f-177">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="a515f-178">Het is het beste om alle vier records toe te voegen, maar als uw registrar slechts twee records ondersteunt, voegt u ns1.bdm.microsoftonline.com **en** **ns2.bdm.microsoftonline.com.**</span><span class="sxs-lookup"><span data-stu-id="a515f-178">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="a515f-179">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="a515f-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="a515f-180">Wanneer u de NS-records van uw domein wijzigt om te wijzen naar de Microsoft 365 naamservers, worden alle services beïnvloed die momenteel aan uw domein zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="a515f-180">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="a515f-181">Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig.</span><span class="sxs-lookup"><span data-stu-id="a515f-181">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="a515f-182">De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt.</span><span class="sxs-lookup"><span data-stu-id="a515f-182">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="a515f-183">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a515f-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="a515f-184">Maak twee naamserverrecords, of bewerk de bestaande naamserverrecords zodat ze overeenkomen met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="a515f-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="a515f-185">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="a515f-185">First nameserver</span></span>  <br/> |<span data-ttu-id="a515f-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="a515f-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="a515f-187">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="a515f-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="a515f-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="a515f-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="a515f-189">U moet ten minste twee naamserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a515f-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="a515f-190">Als er andere naamservers worden vermeld, kunt u deze verwijderen of wijzigen in ns3.dns.partner.microsoftonline.cn **en** **ns4.dns.partner.microsoftonline.cn.**</span><span class="sxs-lookup"><span data-stu-id="a515f-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="a515f-191">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="a515f-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="a515f-192">Wanneer u de NS-records van uw domein wijzigt om te wijzen naar de Office 365 beheerd door 21Vianet-naamservers, worden alle services beïnvloed die momenteel aan uw domein zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="a515f-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="a515f-193">Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig.</span><span class="sxs-lookup"><span data-stu-id="a515f-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="a515f-194">De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt.</span><span class="sxs-lookup"><span data-stu-id="a515f-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="a515f-195">Hierna volgt een voorbeeld van extra stappen die mogelijk zijn vereist voor de hosting van e-mail en websites:</span><span class="sxs-lookup"><span data-stu-id="a515f-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="a515f-196">Verplaats alle e-mailadressen die uw domein gebruiken naar Microsoft 365 voordat u uw NS-records wijzigt.</span><span class="sxs-lookup"><span data-stu-id="a515f-196">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="a515f-197">Wilt u een domein toevoegen dat momenteel wordt gebruikt met een websiteadres, zoals www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="a515f-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="a515f-198">U kunt onderstaande stappen ondernemen terwijl u het domein toevoegt om de website gehost te houden op de locatie waar de site nu wordt gehost, zodat personen nog steeds naar de website kunnen gaan nadat u de NS-records van het domein hebt gewijzigd om te wijzen naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a515f-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="a515f-199">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="a515f-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="a515f-200">Selecteer een domein op de pagina **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="a515f-200">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="a515f-201">Selecteer op de pagina domeindetails het **tabblad DNS-records.**</span><span class="sxs-lookup"><span data-stu-id="a515f-201">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="a515f-202">Selecteer **Record toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a515f-202">Select **Add record**.</span></span>

5. <span data-ttu-id="a515f-203">Selecteer in **het deelvenster Een aangepaste DNS-record** toevoegen in de vervolgkeuzelijst **Type** de optie **A (adres).**</span><span class="sxs-lookup"><span data-stu-id="a515f-203">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="a515f-204">Typ in **het vak Hostnaam** of Alias **@** .</span><span class="sxs-lookup"><span data-stu-id="a515f-204">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="a515f-205">Typ in **het vak IP-adres** het statische IP-adres voor de website waarop het momenteel wordt gehost.</span><span class="sxs-lookup"><span data-stu-id="a515f-205">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="a515f-206">Bijvoorbeeld 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="a515f-206">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="a515f-207">Dit moet een statisch _IP-adres_ voor de website zijn, geen _dynamisch_ IP-adres.</span><span class="sxs-lookup"><span data-stu-id="a515f-207">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="a515f-208">Neem contact op met de site die uw website host om te controleren of u een statisch IP-adres voor uw openbare website kunt krijgen.</span><span class="sxs-lookup"><span data-stu-id="a515f-208">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="a515f-209">Als u de TTL-instelling voor de record wilt wijzigen, selecteert u een nieuwe tijdsduur in de **vervolgkeuzelijst TTL.**</span><span class="sxs-lookup"><span data-stu-id="a515f-209">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="a515f-210">Ga anders verder met stap 9.</span><span class="sxs-lookup"><span data-stu-id="a515f-210">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="a515f-211">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a515f-211">Select **Save**.</span></span> 
    
<span data-ttu-id="a515f-212">U kunt eveneens een CNAME-record maken om klanten te helpen bij het zoeken van uw website.</span><span class="sxs-lookup"><span data-stu-id="a515f-212">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="a515f-213">Selecteer **Record toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a515f-213">Select **Add record**.</span></span>

3.  <span data-ttu-id="a515f-214">Selecteer in **het deelvenster Een aangepaste DNS-record** toevoegen in de vervolgkeuzelijst **Type** de optie **CNAME (Alias).**</span><span class="sxs-lookup"><span data-stu-id="a515f-214">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="a515f-215">Typ www in het vak Hostnaam **of** **Alias.**</span><span class="sxs-lookup"><span data-stu-id="a515f-215">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="a515f-216">Typ in **het vak** Adrespunten de volledig gekwalificeerde domeinnaam (FQDN) voor uw website.</span><span class="sxs-lookup"><span data-stu-id="a515f-216">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="a515f-217">U kunt bijvoorbeeld **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="a515f-217">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="a515f-218">Als u de TTL-instelling voor de record wilt wijzigen, selecteert u een nieuwe tijdsduur in de **vervolgkeuzelijst TTL.**</span><span class="sxs-lookup"><span data-stu-id="a515f-218">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="a515f-219">Ga anders verder met stap 6.</span><span class="sxs-lookup"><span data-stu-id="a515f-219">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="a515f-220">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a515f-220">Select **Save**.</span></span>

<span data-ttu-id="a515f-221">Nadat de naamserverrecords zijn bijgewerkt om naar Microsoft te wijzen, is uw domeinconfiguratie voltooid.</span><span class="sxs-lookup"><span data-stu-id="a515f-221">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="a515f-222">E-mail wordt doorgeleid naar Microsoft en het verkeer naar uw websiteadres blijft naar uw huidige websitehost gaan.'</span><span class="sxs-lookup"><span data-stu-id="a515f-222">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="a515f-223">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a515f-223">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a515f-224">Vervolgens zijn uw e-mail en andere services van Microsoft ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="a515f-224">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="a515f-225">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a515f-225">Related content</span></span>

<span data-ttu-id="a515f-226">[DNS-records toevoegen om uw domein te verbinden](create-dns-records-at-any-dns-hosting-provider.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a515f-226">[Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="a515f-227">[Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](find-and-fix-issues.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a515f-227">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="a515f-228">[Domeinen beheren](index.yml) (koppelingspagina)</span><span class="sxs-lookup"><span data-stu-id="a515f-228">[Manage domains](index.yml) (link page)</span></span>
