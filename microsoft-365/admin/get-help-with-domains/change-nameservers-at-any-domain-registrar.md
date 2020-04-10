---
title: Naamservers wijzigen voor het instellen van Office 365 bij een domeinregistrar
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Meer informatie over het toevoegen en instellen van uw domein in Office 365, zodat uw services zoals e-mail en Skype voor Bedrijven Online uw eigen domeinnaam gebruiken.
ms.custom: okr_smb
ms.openlocfilehash: 838025002443ec35787ea91775c60d3829545af4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210490"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a><span data-ttu-id="6f72a-103">Naamservers wijzigen voor het instellen van Office 365 bij een domeinregistrar</span><span class="sxs-lookup"><span data-stu-id="6f72a-103">Change nameservers to set up Office 365 with any domain registrar</span></span>

 <span data-ttu-id="6f72a-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="6f72a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6f72a-105">Controleer [Eerst uw domein instellen (hostspecifieke instructies)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) om te zien of we instructies hebben voor uw registrar.</span><span class="sxs-lookup"><span data-stu-id="6f72a-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="6f72a-106">Volg deze instructies om uw domein toe te voegen aan Office 365 en in te stellen, zodat services als e-mail en Skype voor Bedrijven Online gebruikmaken van uw eigen domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="6f72a-106">Follow these instructions to add and set up your domain in Office 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="6f72a-107">Hiervoor moet u uw domein verifiëren en de naamservers van uw domein wijzigen in Office 365, zodat de juiste DNS-records voor u kunnen worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="6f72a-107">To do this, you'll verify your domain, and then change your domain's nameservers to Office 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="6f72a-108">Voer de volgende stappen uit als in de volgende instructies uw situatie wordt beschreven:</span><span class="sxs-lookup"><span data-stu-id="6f72a-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="6f72a-109">U hebt een eigen domein en wilt dit configureren voor gebruik met Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f72a-109">You have your own domain and want to set it up to work with Office 365.</span></span>
    
- <span data-ttu-id="6f72a-p102">U wilt Office 365 de DNS-records voor u laten beheren. (Als u wilt, kunt u [uw eigen DNS-records beheren](../setup/add-domain.md).)</span><span class="sxs-lookup"><span data-stu-id="6f72a-p102">You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="6f72a-112">Een TXT- of MX-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="6f72a-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="6f72a-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6f72a-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="6f72a-p103">U hoeft standaard slechts een van deze records te maken. De voorkeur gaat uit naar het recordtype TXT, maar deze wordt niet door alle DNS-hostingproviders ondersteund. In dat geval kunt u in plaats hiervan een MX-record maken.</span><span class="sxs-lookup"><span data-stu-id="6f72a-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="6f72a-p104">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="6f72a-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f72a-p105">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="6f72a-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="6f72a-120">Zoek het gebied op de website van uw DNS-hostingprovider waar u een nieuwe record maken</span><span class="sxs-lookup"><span data-stu-id="6f72a-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="6f72a-121">Meld u aan bij de website van uw DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="6f72a-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="6f72a-122">Selecteer uw domein.</span><span class="sxs-lookup"><span data-stu-id="6f72a-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="6f72a-123">Zoek de pagina waarop u DNS-records voor uw domein kunt bewerken.</span><span class="sxs-lookup"><span data-stu-id="6f72a-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="6f72a-124">De record maken</span><span class="sxs-lookup"><span data-stu-id="6f72a-124">Create the record</span></span>

<span data-ttu-id="6f72a-125">Voer een van de volgende handelingen uit, afhankelijk van of u een TXT-record of een MX-record maakt:</span><span class="sxs-lookup"><span data-stu-id="6f72a-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="6f72a-126">**Als u een TXT-record maakt, gebruikt u deze waarden:**</span><span class="sxs-lookup"><span data-stu-id="6f72a-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6f72a-127">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="6f72a-127">**Record Type**</span></span> <br/> |<span data-ttu-id="6f72a-128">**Alias** of **Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="6f72a-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="6f72a-129">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="6f72a-129">**Value**</span></span> <br/> |<span data-ttu-id="6f72a-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6f72a-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="6f72a-131">TXT</span><span class="sxs-lookup"><span data-stu-id="6f72a-131">TXT</span></span>  <br/> |<span data-ttu-id="6f72a-132">Voer een van de volgende handelingen uit: Typ **@** of laat het veld leeg, of typ de naam van uw domein.</span><span class="sxs-lookup"><span data-stu-id="6f72a-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="6f72a-133">> [!NOTE]> Verschillende DNS-hosts hebben verschillende vereisten voor dit veld.</span><span class="sxs-lookup"><span data-stu-id="6f72a-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="6f72a-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6f72a-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6f72a-p106">> [!NOTE]> Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="6f72a-p106">> [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="6f72a-138">Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.</span><span class="sxs-lookup"><span data-stu-id="6f72a-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="6f72a-139">**Als u een MX-record maakt, gebruikt u deze waarden:**</span><span class="sxs-lookup"><span data-stu-id="6f72a-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6f72a-140">**Recordtype**</span><span class="sxs-lookup"><span data-stu-id="6f72a-140">**Record Type**</span></span>|<span data-ttu-id="6f72a-141">**Alias** of **Hostnaam**</span><span class="sxs-lookup"><span data-stu-id="6f72a-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="6f72a-142">**Value**</span><span class="sxs-lookup"><span data-stu-id="6f72a-142">**Value**</span></span>|<span data-ttu-id="6f72a-143">**Priority**</span><span class="sxs-lookup"><span data-stu-id="6f72a-143">**Priority**</span></span>|<span data-ttu-id="6f72a-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6f72a-144">**TTL**</span></span>|
|<span data-ttu-id="6f72a-145">MX</span><span class="sxs-lookup"><span data-stu-id="6f72a-145">MX</span></span>|<span data-ttu-id="6f72a-146">Typ **@** of uw domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="6f72a-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="6f72a-p107">MS=ms *XXXXXXXX* > [!NOTE]> Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="6f72a-p107">MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="6f72a-150">Gebruik een lagere prioriteit dan de prioriteit voor bestaande MX-records voor **Prioriteit** om conflicten met de MX-record voor de e-mailstroom te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="6f72a-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="6f72a-151">Zie [Wat is MX-prioriteit?](../setup/domains-faq.md#what-is-mx-priority) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="6f72a-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="6f72a-152">Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.</span><span class="sxs-lookup"><span data-stu-id="6f72a-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="6f72a-153">De record opslaan</span><span class="sxs-lookup"><span data-stu-id="6f72a-153">Save the record</span></span>

<span data-ttu-id="6f72a-154">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="6f72a-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="6f72a-155">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="6f72a-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="6f72a-156">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="6f72a-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6f72a-157">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="6f72a-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="6f72a-158">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="6f72a-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="6f72a-159">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="6f72a-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6f72a-p109">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6f72a-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="6f72a-163">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="6f72a-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="6f72a-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="6f72a-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="6f72a-p110">Wanneer u de laatste stap van de wizard voor het instellen van domeinen in Office 365 hebt bereikt, moet u nog één taak uitvoeren. Om uw domein in te stellen met Office 365-services, zoals e-mail, wijzigt u de naamserverrecords van uw domein (of NS-records) bij uw domeinregistrar zodat deze naar de primaire en secundaire naamservers van Office 365 wijzen. Omdat uw DNS wordt gehost door Office 365, worden de voor uw services vereiste records vervolgens automatisch voor u ingesteld. U kunt de naamserverrecords zelf bijwerken door de stappen in de Help-inhoud te volgen die uw domeinregistrar op de website heeft geplaatst. Als u niet bekend bent met DNS, neemt u contact op met de ondersteuning van de domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="6f72a-p110">When you get to the last step of the domains setup wizard in Office 365, you have one task remaining. To set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary nameservers. Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you. You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website. If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="6f72a-170">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, volgt u deze stappen:</span><span class="sxs-lookup"><span data-stu-id="6f72a-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="6f72a-171">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6f72a-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="6f72a-172">Maak twee naamserverrecords, of bewerk de bestaande naamserverrecords zodat ze overeenkomen met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="6f72a-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="6f72a-173">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="6f72a-173">First nameserver</span></span>  <br/> |<span data-ttu-id="6f72a-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6f72a-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6f72a-175">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="6f72a-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="6f72a-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6f72a-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="6f72a-177">U moet ten minste twee nameserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6f72a-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="6f72a-178">Als er andere naamservers worden vermeld, u deze verwijderen of wijzigen in **ns3.bdm.microsoftonline.com** en **ns4.bdm.microsoftonline.com.**</span><span class="sxs-lookup"><span data-stu-id="6f72a-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="6f72a-179">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="6f72a-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="6f72a-p112">Wanneer u de NS-records van uw domein wijzigt zodat deze wijzen naar de naamservers van Office 365, is dit van invloed op alle services die momenteel aan uw domein zijn gekoppeld. Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig. De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt.</span><span class="sxs-lookup"><span data-stu-id="6f72a-p112">When you change your domain's NS records to point to the Office 365 nameservers, all the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="6f72a-183">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6f72a-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="6f72a-184">Maak twee naamserverrecords, of bewerk de bestaande naamserverrecords zodat ze overeenkomen met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="6f72a-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="6f72a-185">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="6f72a-185">First nameserver</span></span>  <br/> |<span data-ttu-id="6f72a-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="6f72a-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="6f72a-187">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="6f72a-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="6f72a-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="6f72a-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="6f72a-189">U moet ten minste twee nameserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6f72a-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="6f72a-190">Als er andere naamservers worden vermeld, u deze verwijderen of wijzigen in **ns3.dns.partner.microsoftonline.cn** en **ns4.dns.partner.microsoftonline.cn.**</span><span class="sxs-lookup"><span data-stu-id="6f72a-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="6f72a-191">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="6f72a-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="6f72a-192">Wanneer u de NS-records van uw domein wijzigt om te wijzen op de Office 365 die wordt beheerd door 21Vianet-naamservers, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="6f72a-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="6f72a-193">Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig.</span><span class="sxs-lookup"><span data-stu-id="6f72a-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="6f72a-194">De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt.</span><span class="sxs-lookup"><span data-stu-id="6f72a-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="6f72a-195">Hierna volgt een voorbeeld van extra stappen die mogelijk zijn vereist voor de hosting van e-mail en websites:</span><span class="sxs-lookup"><span data-stu-id="6f72a-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="6f72a-196">Verplaats alle e-mailadressen die uw domein gebruiken naar Office 365 voordat u uw NS-records wijzigt.</span><span class="sxs-lookup"><span data-stu-id="6f72a-196">Move all email addresses that use your domain to Office 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="6f72a-197">Wilt u een domein toevoegen dat momenteel wordt gebruikt met een websiteadres, zoals www.fourthcoffee.com?</span><span class="sxs-lookup"><span data-stu-id="6f72a-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="6f72a-198">U onderstaande stappen uitvoeren terwijl u het domein toevoegt om de website gehost te houden waar de site nu wordt gehost, zodat mensen nog steeds naar de website kunnen gaan nadat u de NS-records van het domein hebt gewijzigd om naar Office 365 te wijzen.</span><span class="sxs-lookup"><span data-stu-id="6f72a-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Office 365.</span></span>

1. <span data-ttu-id="6f72a-199">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="6f72a-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="6f72a-200">Selecteer een domein op de pagina Domeinen.</span><span class="sxs-lookup"><span data-stu-id="6f72a-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="6f72a-201">Selecteer **onder DNS-instellingen** **Aangepaste records**en kies Vervolgens Nieuwe aangepaste **record**.</span><span class="sxs-lookup"><span data-stu-id="6f72a-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="6f72a-202">Selecteer het type DNS-record dat u wilt toevoegen en typ de gegevens voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="6f72a-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="6f72a-203">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6f72a-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6f72a-p116">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="6f72a-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  

