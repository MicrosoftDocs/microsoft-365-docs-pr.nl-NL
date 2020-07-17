---
title: Veelgestelde vragen over domeinen
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
description: Meer informatie over domeinen door antwoorden te vinden op uw veelgestelde vragen.
ms.openlocfilehash: c588586ddd3d57fdbe78d7751131f61e6aa53eba
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068101"
---
# <a name="domains-faq"></a><span data-ttu-id="c261d-103">Veelgestelde vragen over domeinen</span><span class="sxs-lookup"><span data-stu-id="c261d-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c261d-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="c261d-104">The admin center is changing.</span></span> <span data-ttu-id="c261d-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c261d-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c261d-106">Dit artikel bevat antwoorden op veelgestelde vragen over domeinen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c261d-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="c261d-107">Als u geen antwoord op uw vraag kunt vinden, kunt u dit laten weten door een opmerking achter te laten. Deze wordt dan aan de lijst toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="c261d-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="c261d-108">In dit artikel</span><span class="sxs-lookup"><span data-stu-id="c261d-108">In this article</span></span>

- [<span data-ttu-id="c261d-109">Wat is MX-prioriteit?</span><span class="sxs-lookup"><span data-stu-id="c261d-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="c261d-110">Hoe kan ik SPF-records voor mijn domein valideren?</span><span class="sxs-lookup"><span data-stu-id="c261d-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="c261d-111">Wat is een domeinnaam?</span><span class="sxs-lookup"><span data-stu-id="c261d-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="c261d-112">Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?</span><span class="sxs-lookup"><span data-stu-id="c261d-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="c261d-113">Hoe stel ik het standaarddomein in of wijzig ik deze in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c261d-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="c261d-114">Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c261d-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="c261d-115">Waarom heb ik een domein met de naam onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="c261d-115">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="c261d-116">Waarom heb ik een 'onmicrosoft.de'-domein?</span><span class="sxs-lookup"><span data-stu-id="c261d-116">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="c261d-117">Hoe verifieer ik mijn status zonder winstoogoogs naar een opleiding?</span><span class="sxs-lookup"><span data-stu-id="c261d-117">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="c261d-118">Wat is MX-prioriteit?</span><span class="sxs-lookup"><span data-stu-id="c261d-118">What is MX priority?</span></span>

<span data-ttu-id="c261d-119">E-mail wordt bezorgd bij de Mail Exchange-server met het laagste voorkeursgetal (hoogste prioriteit), dus de MX-record die u gebruikt om e-mail te routeren, moet het laagste voorkeursgetal hebben, gewoonlijk 0 of met prioriteit  *Hoog*  .</span><span class="sxs-lookup"><span data-stu-id="c261d-119">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="c261d-120">Voor de meeste DNS-hostingproviders geldt dat u bij het maken van een MX-record het voorkeursgetal moet instellen.</span><span class="sxs-lookup"><span data-stu-id="c261d-120">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="c261d-121">Sommigen geven het vak het label  *voorkeur*  , anderen het label  *prioriteit*  .</span><span class="sxs-lookup"><span data-stu-id="c261d-121">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="c261d-122">Sommigen vereisen een getal, anderen vragen u  *Laag*  ,  *Gemiddeld*  of  *Hoog*  te selecteren.</span><span class="sxs-lookup"><span data-stu-id="c261d-122">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="c261d-123">Als u slechts één MX-record hebt, kunt u een willekeurige waarde voor prioriteit of voorkeur gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c261d-123">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="c261d-124">Als u er meerdere hebt, dan moet u ervoor zorgen dat de MX-record voor e-mailroutering een hogere prioriteit heeft dan de record die wordt gebruikt om te valideren dat het domein van u is.</span><span class="sxs-lookup"><span data-stu-id="c261d-124">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="c261d-125">Hoe kan ik SPF-records voor mijn domein valideren?</span><span class="sxs-lookup"><span data-stu-id="c261d-125">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="c261d-126">Het is belangrijk dat u **slechts één TXT-record voor SPF hebt**of maakt.</span><span class="sxs-lookup"><span data-stu-id="c261d-126">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="c261d-127">Als u al een SPF-record hebt, moet u de nieuwe Microsoft 365-waarden eraan toederen in plaats van er een nieuwe te maken.</span><span class="sxs-lookup"><span data-stu-id="c261d-127">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="c261d-128">Nadat u uw SPF-record voor Microsoft-e-mail hebt toegevoegd of bijgewerkt, moet u controleren of de syntaxis correct is met een van de volgende hulpprogramma's:</span><span class="sxs-lookup"><span data-stu-id="c261d-128">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="c261d-129">Hulpprogramma's voor het testen van SPF-records</span><span class="sxs-lookup"><span data-stu-id="c261d-129">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="c261d-130">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="c261d-130">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="c261d-131">Dig webinterface</span><span class="sxs-lookup"><span data-stu-id="c261d-131">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="c261d-132">Wat is een domeinnaam?</span><span class="sxs-lookup"><span data-stu-id="c261d-132">What is a domain name?</span></span>

<span data-ttu-id="c261d-p103">Een domein is een unieke naam die na het **@** -teken wordt weergegeven in een e-mailadres en na **www.** in een webadres. Meestal bestaat deze uit de naam van uw organisatie en een standaard-internetachtervoegsel, zoals  *uwbedrijf.com*  of  *universiteit.edu*  .</span><span class="sxs-lookup"><span data-stu-id="c261d-p103">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="c261d-136">Het gebruik van een aangepast domein zoals "**rob \@ contoso.com**" met Microsoft 365 kan helpen bij het opbouwen van geloofwaardigheid en erkenning voor uw merk.</span><span class="sxs-lookup"><span data-stu-id="c261d-136">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="c261d-137">U [een domein kopen in Microsoft 365 en we stellen het automatisch in,](../get-help-with-domains/buy-a-domain-name.md)of u er een kopen of meenemen die u al bezit van een domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="c261d-137">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="c261d-138">Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?</span><span class="sxs-lookup"><span data-stu-id="c261d-138">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="c261d-139">Als u uw eigen DNS-records beheert en uw DNS-host niet alle DNS-records ondersteunt die Microsoft 365 nodig heeft, werken sommige Microsoft 365-functies niet.</span><span class="sxs-lookup"><span data-stu-id="c261d-139">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="c261d-140">U wordt aangeraden uw domein over te zetten naar een registrar die ondersteuning biedt voor alle vereiste DNS-records.</span><span class="sxs-lookup"><span data-stu-id="c261d-140">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="c261d-141">Providers die ondersteuning bieden voor alle vereiste DNS-records:</span><span class="sxs-lookup"><span data-stu-id="c261d-141">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="c261d-142">Dynadot</span><span class="sxs-lookup"><span data-stu-id="c261d-142">Dynadot</span></span>
    
- <span data-ttu-id="c261d-143">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="c261d-143">eNomCentral</span></span>
    
- <span data-ttu-id="c261d-144">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="c261d-144">Europe Registry</span></span>
    
- <span data-ttu-id="c261d-145">Godaddy</span><span class="sxs-lookup"><span data-stu-id="c261d-145">GoDaddy</span></span>
    
- <span data-ttu-id="c261d-146">Hover</span><span class="sxs-lookup"><span data-stu-id="c261d-146">Hover</span></span>
    
- <span data-ttu-id="c261d-147">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="c261d-147">MyHosting.com</span></span>
    
- <span data-ttu-id="c261d-148">Name.com</span><span class="sxs-lookup"><span data-stu-id="c261d-148">Name.com</span></span>
    
- <span data-ttu-id="c261d-149">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="c261d-149">Nearly Free Speech</span></span>
    
- <span data-ttu-id="c261d-150">Nettica</span><span class="sxs-lookup"><span data-stu-id="c261d-150">Nettica</span></span>
    
- <span data-ttu-id="c261d-151">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="c261d-151">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="c261d-152">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="c261d-152">Network Solutions</span></span>
    
- <span data-ttu-id="c261d-153">Register.com</span><span class="sxs-lookup"><span data-stu-id="c261d-153">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="c261d-154">Hoe stel ik het standaarddomein in of wijzig ik deze in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c261d-154">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="c261d-155">U moet ten minste één aangepast domein hebben dat u aan Microsoft 365 hebt toegevoegd voordat u een standaarddomein kiezen.</span><span class="sxs-lookup"><span data-stu-id="c261d-155">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c261d-156">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="c261d-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c261d-157">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="c261d-157">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c261d-158">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="c261d-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="c261d-159">Selecteer op de pagina **Domeinen** het domein dat u wilt instellen als standaard voor nieuwe e-mailadressen.</span><span class="sxs-lookup"><span data-stu-id="c261d-159">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="c261d-160">Selecteer **Als standaard instellen**.</span><span class="sxs-lookup"><span data-stu-id="c261d-160">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="c261d-161">U kunt de naam van uw initiële  *.onmicrosoft.com*  -domein niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c261d-161">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="c261d-162">U de naam van uw oorspronkelijke *.onmicrosoft.de-domein* niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c261d-162">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="c261d-163">U de naam van uw oorspronkelijke *.partner.onmschina.cn-domein* niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c261d-163">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="c261d-164">Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c261d-164">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="c261d-165">Ja.</span><span class="sxs-lookup"><span data-stu-id="c261d-165">Yes.</span></span> <span data-ttu-id="c261d-166">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="c261d-166">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="c261d-167">Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein bij Microsoft hebt gekocht, u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c261d-167">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="c261d-168">Ja!</span><span class="sxs-lookup"><span data-stu-id="c261d-168">Yes!</span></span> <span data-ttu-id="c261d-169">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="c261d-169">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="c261d-170">Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein bij Microsoft hebt gekocht, u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c261d-170">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="c261d-171">Ja!</span><span class="sxs-lookup"><span data-stu-id="c261d-171">Yes!</span></span> <span data-ttu-id="c261d-172">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="c261d-172">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="c261d-173">Als u 21Vianet uw DNS-instellingen laat beheren met NS-records, u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c261d-173">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="c261d-174">Normaal gesproken u maximaal 900 domeinen toevoegen aan uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="c261d-174">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="c261d-175">U kunt bijvoorbeeld de domeinen contoso.com en contosomarketing.com toevoegen, en vervolgens de subdomeinen www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com enzovoort.</span><span class="sxs-lookup"><span data-stu-id="c261d-175">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="c261d-176">Wanneer u een subdomein toevoegt, wordt deze automatisch geverifieerd op basis van het bovenliggende domein dat wordt geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="c261d-176">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="c261d-177">Wanneer u meerdere domeinen toevoegt aan Microsoft 365, u een van de services (zoals e-mail) hosten op een van de domeinen die u hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="c261d-177">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="c261d-178">*Wanneer u uw e-mail wijzigt naar Microsoft 365, door de MX-record van een domein bij te werken, begint ALLE e-mail die naar dat domein wordt verzonden, naar Microsoft 365 te komen.*</span><span class="sxs-lookup"><span data-stu-id="c261d-178">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="c261d-179">Als u een contoso.com domein hebt toegevoegd aan een Microsoft 365-abonnement, u het subdomein ook toevoegen xyz.contoso.com aan een andere Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="c261d-179">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="c261d-180">Wanneer u het subdomein toevoegt, wordt u gevraagd een TXT-record toe te voegen aan de DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="c261d-180">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="c261d-181">Waarom heb ik een domein met de naam onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="c261d-181">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="c261d-182">Microsoft 365 maakt een domein voor u, zoals *contoso.onmicrosoft.com,* wanneer u zich aanmeldt bij de service.</span><span class="sxs-lookup"><span data-stu-id="c261d-182">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="c261d-183">De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="c261d-183">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="c261d-184">**Als u uw e-mail eruit wilt laten zien als *alan \@ contoso.com:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Microsoft [365](add-domain.md) als u het al bezit.</span><span class="sxs-lookup"><span data-stu-id="c261d-184">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="c261d-185">**U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.**</span><span class="sxs-lookup"><span data-stu-id="c261d-185">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="c261d-186">Als u tijdens het registreren bijvoorbeeld in eerste instantie fourthcoffee.onmicrosoft.com hebt gekozen, kunt u deze naam niet meer wijzigen in fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="c261d-186">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="c261d-187">Als u een ander onmicrosoft.com domein wilt gebruiken, moet u een nieuw abonnement starten met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c261d-187">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="c261d-188">**U de naam van de URL van uw teamsite niet wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="c261d-188">**You can't rename your team site URL.**</span></span> <span data-ttu-id="c261d-189">De URL van uw teamsite is gebaseerd op uw onmicrosoft.com domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="c261d-189">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="c261d-190">Vanwege de manier waarop de SharePoint Online-architectuur werkt, u de naam van de teamsite helaas niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c261d-190">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="c261d-191">**U kunt uw onmicrosoft-domein niet verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="c261d-191">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="c261d-192">Microsoft 365 moet het rond houden omdat het achter de schermen wordt gebruikt voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c261d-192">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="c261d-193">U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="c261d-193">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="c261d-p114">U kunt het onmicrosoft.com-domein blijven gebruiken, ook nadat u uw domein hebt toegevoegd. Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.</span><span class="sxs-lookup"><span data-stu-id="c261d-p114">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="c261d-196">Waarom heb ik een 'onmicrosoft.de'-domein?</span><span class="sxs-lookup"><span data-stu-id="c261d-196">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="c261d-197">Microsoft 365 maakt een domein voor u, zoals *contoso.onmicrosoft.de,* wanneer u zich aanmeldt bij de service.</span><span class="sxs-lookup"><span data-stu-id="c261d-197">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="c261d-198">De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="c261d-198">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="c261d-199">**Als u uw e-mail eruit wilt laten zien als *alan@contoso.de:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Microsoft [365](add-domain.md) als u het al bezit.</span><span class="sxs-lookup"><span data-stu-id="c261d-199">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="c261d-200">**U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.**</span><span class="sxs-lookup"><span data-stu-id="c261d-200">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="c261d-201">Als het oorspronkelijke domein dat u hebt gekozen bijvoorbeeld fourthcoffee.onmicrosoft.de, u het niet wijzigen om te worden fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="c261d-201">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="c261d-202">Als u een ander onmicrosoft.de domein wilt gebruiken, moet u een nieuw abonnement starten met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c261d-202">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="c261d-203">**U de naam van de URL van uw teamsite niet wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="c261d-203">**You can't rename your team site URL.**</span></span> <span data-ttu-id="c261d-204">De URL van uw teamsite is gebaseerd op uw onmicrosoft.de domeinnaam. Vanwege de manier waarop de SharePoint Online-architectuur werkt, u de naam van de teamsite helaas niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c261d-204">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="c261d-205">**U kunt uw onmicrosoft-domein niet verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="c261d-205">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="c261d-206">Microsoft 365 moet het rond houden omdat het achter de schermen wordt gebruikt voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c261d-206">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="c261d-207">U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="c261d-207">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="c261d-208">U de initiële onmicrosoft.de domein blijven gebruiken, zelfs nadat u uw domein hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="c261d-208">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="c261d-209">Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.</span><span class="sxs-lookup"><span data-stu-id="c261d-209">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="c261d-210">Hoe verifieer ik mijn status zonder winstoogoogs naar een opleiding?</span><span class="sxs-lookup"><span data-stu-id="c261d-210">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="c261d-211">Selecteer **Setup** in het [beheercentrum](https://docs.microsoft.com/microsoft-365/admin/admin-home) om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="c261d-211">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="c261d-212">(Meld u eerst aan bij Microsoft 365.)</span><span class="sxs-lookup"><span data-stu-id="c261d-212">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="c261d-213">Als u beheerder van uw school wilt worden, selecteert u de optie **Een beheerder worden** in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c261d-213">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="c261d-214">U wordt gevraagd om een TXT DNS-record toe te voegen op de DNS-hostwebsite voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="c261d-214">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="c261d-215">Waarom?</span><span class="sxs-lookup"><span data-stu-id="c261d-215">Why?</span></span> <span data-ttu-id="c261d-216">Omdat u door u aan te melden bij de DNS-host en een record voor uw domein toe te voegen, aan Microsoft 365 bewijst dat u eigenaar bent van de domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="c261d-216">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="c261d-217">Nadat u de record hebt toegevoegd, gaat u terug naar de Microsoft 365-portal en bevestigt u dat u deze hebt toegevoegd, zodat Microsoft 365 deze kan controleren.</span><span class="sxs-lookup"><span data-stu-id="c261d-217">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="c261d-218">Heb je een non-profitorganisatie en wil je Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="c261d-218">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="c261d-219">[Zorg ervoor dat uw organisatie in aanmerking komt](https://www.microsoft.com/en-us/nonprofits/eligibility) en meld u vervolgens aan voor de service.</span><span class="sxs-lookup"><span data-stu-id="c261d-219">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="c261d-220">Wilt u meer weten over het worden van de admin voor uw school?</span><span class="sxs-lookup"><span data-stu-id="c261d-220">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="c261d-221">[Leer er alles over.](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)</span><span class="sxs-lookup"><span data-stu-id="c261d-221">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>