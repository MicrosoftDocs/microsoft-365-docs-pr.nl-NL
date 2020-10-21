---
title: Veelgestelde vragen over domeinen
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Meer informatie over domeinen vindt u in antwoorden op uw veelgestelde vragen.
ms.openlocfilehash: b51b5fe56bbae56dd473dd831ec91e629d9233f3
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644577"
---
# <a name="domains-faq"></a><span data-ttu-id="2a5f7-103">Veelgestelde vragen over domeinen</span><span class="sxs-lookup"><span data-stu-id="2a5f7-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="2a5f7-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-104">The admin center is changing.</span></span> <span data-ttu-id="2a5f7-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="2a5f7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="2a5f7-106">Dit artikel bevat antwoorden op veelgestelde vragen over domeinen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="2a5f7-107">Als u geen antwoord op uw vraag kunt vinden, kunt u dit laten weten door een opmerking achter te laten. Deze wordt dan aan de lijst toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="2a5f7-108">In dit artikel</span><span class="sxs-lookup"><span data-stu-id="2a5f7-108">In this article</span></span>

- [<span data-ttu-id="2a5f7-109">Wat is MX-prioriteit?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="2a5f7-110">Hoe kan ik SPF-records voor mijn domein valideren?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="2a5f7-111">Wat is een domeinnaam?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="2a5f7-112">Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="2a5f7-113">Hoe kan ik het standaarddomein instellen of wijzigen in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="2a5f7-114">Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="2a5f7-115">Hoe kan ik een domein van Microsoft 365 overbrengen naar een andere host?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-115">How do I transfer a domain from Microsoft 365 to another host?</span></span>](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [<span data-ttu-id="2a5f7-116">Waarom heb ik een domein met de naam onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-116">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="2a5f7-117">Waarom heb ik een onmicrosoft.de-domein?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-117">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="2a5f7-118">Hoe controleer ik de status van een non-profit of onderwijs?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-118">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="2a5f7-119">Wat is MX-prioriteit?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-119">What is MX priority?</span></span>

<span data-ttu-id="2a5f7-120">E-mail wordt bezorgd bij de Mail Exchange-server met het laagste voorkeursgetal (hoogste prioriteit), dus de MX-record die u gebruikt om e-mail te routeren, moet het laagste voorkeursgetal hebben, gewoonlijk 0 of met prioriteit  *Hoog*  .</span><span class="sxs-lookup"><span data-stu-id="2a5f7-120">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="2a5f7-121">Voor de meeste DNS-hostingproviders geldt dat u bij het maken van een MX-record het voorkeursgetal moet instellen.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-121">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="2a5f7-122">Sommigen geven het vak het label  *voorkeur*  , anderen het label  *prioriteit*  .</span><span class="sxs-lookup"><span data-stu-id="2a5f7-122">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="2a5f7-123">Sommigen vereisen een getal, anderen vragen u  *Laag*  ,  *Gemiddeld*  of  *Hoog*  te selecteren.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-123">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="2a5f7-124">Als u slechts één MX-record hebt, kunt u een willekeurige waarde voor prioriteit of voorkeur gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-124">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="2a5f7-125">Als u er meerdere hebt, dan moet u ervoor zorgen dat de MX-record voor e-mailroutering een hogere prioriteit heeft dan de record die wordt gebruikt om te valideren dat het domein van u is.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-125">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="2a5f7-126">Hoe kan ik SPF-records voor mijn domein valideren?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-126">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="2a5f7-127">Het is belangrijk dat u  **maar één TXT-record voor SPF**hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-127">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="2a5f7-128">Als u al een SPF-record hebt, moet u de nieuwe Microsoft 365-waarden toevoegen aan de record, en niet een nieuwe maken.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-128">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="2a5f7-129">Wanneer u de SPF-record voor Microsoft-e-mail hebt toegevoegd of bijgewerkt, controleert u of de syntaxis in een van de volgende hulpprogramma's correct is:</span><span class="sxs-lookup"><span data-stu-id="2a5f7-129">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="2a5f7-130">Hulpprogramma's voor het testen van SPF-records</span><span class="sxs-lookup"><span data-stu-id="2a5f7-130">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="2a5f7-131">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="2a5f7-131">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="2a5f7-132">Dig webinterface</span><span class="sxs-lookup"><span data-stu-id="2a5f7-132">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="2a5f7-133">Wat is een domeinnaam?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-133">What is a domain name?</span></span>

<span data-ttu-id="2a5f7-p103">Een domein is een unieke naam die na het **@** -teken wordt weergegeven in een e-mailadres en na **www.** in een webadres. Meestal bestaat deze uit de naam van uw organisatie en een standaard-internetachtervoegsel, zoals  *uwbedrijf.com*  of  *universiteit.edu*  .</span><span class="sxs-lookup"><span data-stu-id="2a5f7-p103">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="2a5f7-137">Met behulp van een aangepast domein zoals '**rob \@ contoso.com**' met Microsoft 365 kunt u geloofwaardigheid en herkenning voor uw merk opbouwen.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-137">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="2a5f7-138">U kunt [een domein kopen in Microsoft 365 en we stellen dit automatisch in](../get-help-with-domains/buy-a-domain-name.md)of u kunt een domein kopen of ophalen dat u al hebt gekocht bij een domeinregistratie.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-138">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="2a5f7-139">Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-139">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="2a5f7-140">Als u uw eigen DNS-records beheert en uw DNS-host geen ondersteuning biedt voor alle DNS-records die in Microsoft 365 zijn vereist, werken sommige functies van Microsoft 365 niet.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-140">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="2a5f7-141">U wordt aangeraden uw domein over te zetten naar een registrar die ondersteuning biedt voor alle vereiste DNS-records.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-141">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="2a5f7-142">Providers die ondersteuning bieden voor alle vereiste DNS-records:</span><span class="sxs-lookup"><span data-stu-id="2a5f7-142">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="2a5f7-143">Dynadot</span><span class="sxs-lookup"><span data-stu-id="2a5f7-143">Dynadot</span></span>
    
- <span data-ttu-id="2a5f7-144">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="2a5f7-144">eNomCentral</span></span>
    
- <span data-ttu-id="2a5f7-145">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="2a5f7-145">Europe Registry</span></span>
    
- <span data-ttu-id="2a5f7-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="2a5f7-146">GoDaddy</span></span>
    
- <span data-ttu-id="2a5f7-147">Hover</span><span class="sxs-lookup"><span data-stu-id="2a5f7-147">Hover</span></span>
    
- <span data-ttu-id="2a5f7-148">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="2a5f7-148">MyHosting.com</span></span>
    
- <span data-ttu-id="2a5f7-149">Name.com</span><span class="sxs-lookup"><span data-stu-id="2a5f7-149">Name.com</span></span>
    
- <span data-ttu-id="2a5f7-150">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="2a5f7-150">Nearly Free Speech</span></span>
    
- <span data-ttu-id="2a5f7-151">Nettica</span><span class="sxs-lookup"><span data-stu-id="2a5f7-151">Nettica</span></span>
    
- <span data-ttu-id="2a5f7-152">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="2a5f7-152">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="2a5f7-153">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="2a5f7-153">Network Solutions</span></span>
    
- <span data-ttu-id="2a5f7-154">Register.com</span><span class="sxs-lookup"><span data-stu-id="2a5f7-154">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="2a5f7-155">Hoe kan ik het standaarddomein instellen of wijzigen in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-155">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="2a5f7-156">U moet minimaal één aangepast domein aan Microsoft 365 hebben toegevoegd voordat u een standaarddomein kunt kiezen.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-156">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="2a5f7-157">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="2a5f7-158">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2a5f7-159">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="2a5f7-160">Selecteer op de pagina **Domains** het domein dat u als standaard wilt instellen voor nieuwe e-mailadressen.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-160">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="2a5f7-161">Selecteer **Als standaard instellen**.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-161">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="2a5f7-162">U kunt de naam van uw initiële  *.onmicrosoft.com*  -domein niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-162">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="2a5f7-163">U kunt de naam van uw initiële  *. ononmicrosoft.de*  -domein niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-163">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="2a5f7-164">U kunt de naam van uw initiële  *. onpartner.onmschina.cn*  -domein niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-164">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="2a5f7-165">Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-165">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="2a5f7-166">Ja.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-166">Yes.</span></span> <span data-ttu-id="2a5f7-167">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van de registratieserver.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-167">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="2a5f7-168">Als u Microsoft uw DNS-instellingen met NS-records wilt laten beheren, of als u het domein van Microsoft hebt gekocht, kunt u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-168">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="2a5f7-169">Ja!</span><span class="sxs-lookup"><span data-stu-id="2a5f7-169">Yes!</span></span> <span data-ttu-id="2a5f7-170">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van de registratieserver.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-170">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="2a5f7-171">Als u Microsoft uw DNS-instellingen met NS-records wilt laten beheren, of als u het domein van Microsoft hebt gekocht, kunt u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-171">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="2a5f7-172">Ja!</span><span class="sxs-lookup"><span data-stu-id="2a5f7-172">Yes!</span></span> <span data-ttu-id="2a5f7-173">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van de registratieserver.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-173">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="2a5f7-174">Als u 21Vianet uw DNS-instellingen met NS-records beheert, kunt u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-174">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="2a5f7-175">Meestal kunt u maximaal 900 domeinen toevoegen aan uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-175">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="2a5f7-176">U kunt bijvoorbeeld de domeinen contoso.com en contosomarketing.com toevoegen, en vervolgens de subdomeinen www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com enzovoort.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-176">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="2a5f7-177">Wanneer u een subdomein toevoegt, wordt dit automatisch gecontroleerd op basis van het bovenliggende domein dat wordt geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-177">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="2a5f7-178">Als u meerdere domeinen toevoegt aan Microsoft 365, kunt u alle services (zoals e-mail) hosten in elk van de domeinen die u hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-178">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="2a5f7-179">*Wanneer u uw e-mailadres wijzigt in Microsoft 365, worden alle e-mailberichten die naar het domein worden verzonden, doorgestuurd naar Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="2a5f7-179">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="2a5f7-180">Als u een contoso.com-domein hebt toegevoegd aan een Microsoft 365-abonnement, kunt u ook de subdomein-xyz.contoso.com toevoegen aan een andere Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-180">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="2a5f7-181">Wanneer u het subdomein toevoegt, wordt u gevraagd een TXT-record toe te voegen aan de DNS-hosting provider.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-181">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a><span data-ttu-id="2a5f7-182">Hoe kan ik een domein van Microsoft 365 overbrengen naar een andere host?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-182">How do I transfer a domain from Microsoft 365 to another host?</span></span>

<span data-ttu-id="2a5f7-183">Zie [een domein van Microsoft overbrengen naar een andere host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)voor de procedure voor het overdragen van een domein.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-183">For the procedure to transfer a domain, see [Transfer a domain from Microsoft to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span></span>

## <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="2a5f7-184">Testfase van Microsoft 365 uitvoeren vanaf mijn aangepaste domein</span><span class="sxs-lookup"><span data-stu-id="2a5f7-184">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="2a5f7-185">Voor de procedure voor het testen van de Microsoft 365-e-mail functionaliteit van een aangepast domein naar een Microsoft 365-postvak, raadpleegt u [Microsoft 365 van mijn aangepaste domein testen](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="2a5f7-185">For the procedure to pilot Microsoft 365 email functionality from a custom domain to a Microsoft 365 mailbox, see [Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="2a5f7-186">Waarom heb ik een domein met de naam onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-186">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="2a5f7-187">Microsoft 365 maakt een domein voor u, zoals *contoso.onmicrosoft.com*, wanneer u zich aanmeldt bij de service.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-187">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="2a5f7-188">De gebruikers-ID die u maakt wanneer u zich registreert, omvat het domein, bijvoorbeeld *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-188">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="2a5f7-189">**Als u uw e-mail wilt weergeven als *Alan \@ contoso.com*:** [Koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg de stappen in [uw gebruikers en domein toevoegen aan Microsoft 365](add-domain.md) als u het al bent.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-189">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="2a5f7-190">**U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.**</span><span class="sxs-lookup"><span data-stu-id="2a5f7-190">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="2a5f7-191">Als u tijdens het registreren bijvoorbeeld in eerste instantie fourthcoffee.onmicrosoft.com hebt gekozen, kunt u deze naam niet meer wijzigen in fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-191">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="2a5f7-192">Als u een ander onmicrosoft.com-domein wilt gebruiken, moet u een nieuw abonnement beginnen met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-192">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="2a5f7-193">**U kunt de URL van uw team site niet wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="2a5f7-193">**You can't rename your team site URL.**</span></span> <span data-ttu-id="2a5f7-194">De URL van uw team site is gebaseerd op de onmicrosoft.com-domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-194">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="2a5f7-195">Helaas kunt u de naam van de team site niet wijzigen vanwege de manier waarop SharePoint Online Architecture werkt.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-195">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="2a5f7-196">**U kunt uw onmicrosoft-domein niet verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="2a5f7-196">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="2a5f7-197">Microsoft 365 moet aan de slag gaan, omdat dit wordt gebruikt achter de scènes voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-197">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="2a5f7-198">U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-198">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="2a5f7-p114">U kunt het onmicrosoft.com-domein blijven gebruiken, ook nadat u uw domein hebt toegevoegd. Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-p114">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="2a5f7-201">Waarom heb ik een onmicrosoft.de-domein?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-201">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="2a5f7-202">Microsoft 365 maakt een domein voor u, zoals *contoso.onmicrosoft.de*, wanneer u zich aanmeldt bij de service.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-202">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="2a5f7-203">De gebruikers-ID die u maakt wanneer u zich registreert, omvat het domein, bijvoorbeeld *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-203">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="2a5f7-204">**Ga als volgt te werk als u uw e-mail wilt weergeven als *Alan@contoso.de*:** [het domein kopen](../get-help-with-domains/buy-a-domain-name.md) of voer de stappen uit in [uw gebruikers en domein toevoegen aan Microsoft 365](add-domain.md) als u de e-mail al hebt gekocht.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-204">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="2a5f7-205">**U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.**</span><span class="sxs-lookup"><span data-stu-id="2a5f7-205">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="2a5f7-206">Als het eerste domein dat u hebt gekozen bijvoorbeeld fourthcoffee.onmicrosoft.de, kunt u dit niet wijzigen in fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-206">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="2a5f7-207">Als u een ander onmicrosoft.de-domein wilt gebruiken, moet u een nieuw abonnement beginnen met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-207">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="2a5f7-208">**U kunt de URL van uw team site niet wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="2a5f7-208">**You can't rename your team site URL.**</span></span> <span data-ttu-id="2a5f7-209">De URL van uw team site is gebaseerd op de onmicrosoft.de-domeinnaam. Helaas kunt u de naam van de team site niet wijzigen vanwege de manier waarop SharePoint Online Architecture werkt.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-209">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="2a5f7-210">**U kunt uw onmicrosoft-domein niet verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="2a5f7-210">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="2a5f7-211">Microsoft 365 moet aan de slag gaan, omdat dit wordt gebruikt achter de scènes voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-211">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="2a5f7-212">U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-212">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="2a5f7-213">U kunt het initiële ononmicrosoft.de-domein blijven gebruiken, zelfs nadat u uw domein hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-213">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="2a5f7-214">Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-214">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="2a5f7-215">Hoe controleer ik de status van een non-profit of onderwijs?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-215">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="2a5f7-216">Selecteer **Setup** in het [Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/admin-home) om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-216">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="2a5f7-217">(Zorg ervoor dat u zich eerst aanmeldt bij Microsoft 365.)</span><span class="sxs-lookup"><span data-stu-id="2a5f7-217">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="2a5f7-218">Als u de beheerder van uw school wilt worden, selecteert u de optie  **een beheerder worden** in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-218">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="2a5f7-219">U wordt gevraagd om een TXT DNS-record toe te voegen op de website van de DNS-host voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-219">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="2a5f7-220">Waarom?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-220">Why?</span></span> <span data-ttu-id="2a5f7-221">Door u aan te melden bij de DNS-host en een record voor uw domein toe te voegen, meldt u Microsoft 365 dat u de eigenaar van de domeinnaam bent.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-221">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="2a5f7-222">Nadat u de record hebt toegevoegd, gaat u terug naar de Microsoft 365-Portal en bevestigt u dat u deze hebt toegevoegd, zodat micro 365 Soft kan controleren.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-222">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="2a5f7-223">Hebt u een non-profit organisatie en wilt u Microsoft 365 aanschaffen?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-223">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="2a5f7-224">[Zorg ervoor dat uw organisatie in aanmerking komt](https://www.microsoft.com/en-us/nonprofits/eligibility) en registreert voor de service.</span><span class="sxs-lookup"><span data-stu-id="2a5f7-224">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="2a5f7-225">Wilt u meer weten over de beheerder voor uw school?</span><span class="sxs-lookup"><span data-stu-id="2a5f7-225">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="2a5f7-226">[Meer informatie hierover](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="2a5f7-226">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>