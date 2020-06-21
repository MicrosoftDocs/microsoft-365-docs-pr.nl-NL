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
description: Meer informatie over domeinen door antwoorden op uw vragen te vinden in VEELgestelde vragen.
ms.openlocfilehash: a52513130f9bbbf7c4cd25d4c4827e833700d992
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739152"
---
# <a name="domains-faq"></a><span data-ttu-id="cdf83-103">Veelgestelde vragen over domeinen</span><span class="sxs-lookup"><span data-stu-id="cdf83-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cdf83-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="cdf83-104">The admin center is changing.</span></span> <span data-ttu-id="cdf83-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="cdf83-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="cdf83-106">Dit artikel bevat antwoorden op veelgestelde vragen over domeinen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf83-106">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="cdf83-107">Als u geen antwoord op uw vraag kunt vinden, kunt u dit laten weten door een opmerking achter te laten. Deze wordt dan aan de lijst toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="cdf83-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="cdf83-108">Wat is MX-prioriteit?</span><span class="sxs-lookup"><span data-stu-id="cdf83-108">What is MX priority?</span></span>

<span data-ttu-id="cdf83-109">E-mail wordt bezorgd bij de Mail Exchange-server met het laagste voorkeursgetal (hoogste prioriteit), dus de MX-record die u gebruikt om e-mail te routeren, moet het laagste voorkeursgetal hebben, gewoonlijk 0 of met prioriteit  *Hoog*  .</span><span class="sxs-lookup"><span data-stu-id="cdf83-109">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="cdf83-110">Voor de meeste DNS-hostingproviders geldt dat u bij het maken van een MX-record het voorkeursgetal moet instellen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-110">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="cdf83-111">Sommigen geven het vak het label  *voorkeur*  , anderen het label  *prioriteit*  .</span><span class="sxs-lookup"><span data-stu-id="cdf83-111">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="cdf83-112">Sommigen vereisen een getal, anderen vragen u  *Laag*  ,  *Gemiddeld*  of  *Hoog*  te selecteren.</span><span class="sxs-lookup"><span data-stu-id="cdf83-112">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="cdf83-113">Als u slechts één MX-record hebt, kunt u een willekeurige waarde voor prioriteit of voorkeur gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cdf83-113">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="cdf83-114">Als u er meerdere hebt, dan moet u ervoor zorgen dat de MX-record voor e-mailroutering een hogere prioriteit heeft dan de record die wordt gebruikt om te valideren dat het domein van u is.</span><span class="sxs-lookup"><span data-stu-id="cdf83-114">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="cdf83-115">Hoe kan ik SPF-records voor mijn domein valideren?</span><span class="sxs-lookup"><span data-stu-id="cdf83-115">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="cdf83-116">Het is belangrijk dat u **slechts één TXT-record voor SPF hebt**of maakt.</span><span class="sxs-lookup"><span data-stu-id="cdf83-116">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="cdf83-117">Als u al een SPF-record hebt, moet u de nieuwe Office 365-waarden eraan toederen in plaats van er een nieuwe te maken.</span><span class="sxs-lookup"><span data-stu-id="cdf83-117">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="cdf83-118">Nadat u uw SPF-record voor Microsoft-e-mail hebt toegevoegd of bijgewerkt, moet u controleren of de syntaxis correct is met een van de volgende hulpprogramma's:</span><span class="sxs-lookup"><span data-stu-id="cdf83-118">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="cdf83-119">Hulpprogramma's voor het testen van SPF-records</span><span class="sxs-lookup"><span data-stu-id="cdf83-119">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="cdf83-120">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="cdf83-120">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="cdf83-121">Dig webinterface</span><span class="sxs-lookup"><span data-stu-id="cdf83-121">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="cdf83-122">Hoe worden mijn DNS-records door Office 365 beheerd?</span><span class="sxs-lookup"><span data-stu-id="cdf83-122">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="cdf83-123">Er zijn twee opties voor DNS-beheer met Office 365:</span><span class="sxs-lookup"><span data-stu-id="cdf83-123">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="cdf83-124">U wijzigt uw NS-records (nameserver) en vervolgens zorgt Microsoft voor alle servicespecifieke records, zoals het instellen van uw MX-record voor e-mail.</span><span class="sxs-lookup"><span data-stu-id="cdf83-124">You change your nameserver (NS) records, and then Microsoft takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="cdf83-125">**(Aanbevolen)**</span><span class="sxs-lookup"><span data-stu-id="cdf83-125">**(Recommended)**</span></span>
    
2. <span data-ttu-id="cdf83-126">U voegt DNS-records voor e-mail en andere Office 365-services bij uw DNS-host zelf toe.</span><span class="sxs-lookup"><span data-stu-id="cdf83-126">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="cdf83-127">**(Alleen voor experts)**</span><span class="sxs-lookup"><span data-stu-id="cdf83-127">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="cdf83-128">Office 365 maakt en host de DNS-records</span><span class="sxs-lookup"><span data-stu-id="cdf83-128">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="cdf83-129">**Voordelen**</span><span class="sxs-lookup"><span data-stu-id="cdf83-129">**Advantages**</span></span> 
- <span data-ttu-id="cdf83-130">U hoeft niet bang te zijn om fouten te maken bij de waarden die u invoert voor de DNS-records voor Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="cdf83-130">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="cdf83-131">U hebt meer flexibiliteit bij het kiezen van een domeinregistrar en DNS-host.</span><span class="sxs-lookup"><span data-stu-id="cdf83-131">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="cdf83-132">U kunt elke provider gebruiken waarbij u uw naamserverrecords kunt wijzigen, zelfs als de provider niet alle vereiste recordtypen ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="cdf83-132">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="cdf83-133">Wanneer Office 365 nieuwe DNS-records toevoegt, hoeft u geen updates uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="cdf83-133">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="cdf83-134">Nadelen</span><span class="sxs-lookup"><span data-stu-id="cdf83-134">Disadvantages</span></span> 
- <span data-ttu-id="cdf83-135">U kunt uw DNS-records niet wijzigen om e-mail buiten Office 365 te hosten.</span><span class="sxs-lookup"><span data-stu-id="cdf83-135">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="cdf83-136">Als u al een openbare website met uw domein gebruikt voor het adres, zoals www.fourthcoffee.com, moet u mensen vanaf Office 365 doorverwijzen naar dat adres.</span><span class="sxs-lookup"><span data-stu-id="cdf83-136">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="cdf83-137">Het instellen van omleiding vereist een statisch IP-adres, dat niet altijd gemakkelijk beschikbaar is voor openbare websites.</span><span class="sxs-lookup"><span data-stu-id="cdf83-137">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="cdf83-138">- Als uw huidige domeinregistrar u niet toestaat om de naamserverrecords van uw domein te wijzigen, moet u overschakelen naar een andere registrar om deze DNS-beheeroptie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cdf83-138">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="cdf83-139">U beheert de DNS-records zelf</span><span class="sxs-lookup"><span data-stu-id="cdf83-139">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="cdf83-140">Voordelen</span><span class="sxs-lookup"><span data-stu-id="cdf83-140">Advantages</span></span>
- <span data-ttu-id="cdf83-141">U beheert de DNS-records voor Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="cdf83-141">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="cdf83-142">Als u een openbare website hebt met uw domein als het adres, zoals www.fourthcoffee.com, hoeft u geen omleiding te gebruiken om ervoor te zorgen dat mensen uw website nog kunnen bereiken nadat u uw domein hebt ingesteld in Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf83-142">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="cdf83-143">U hebt de flexibiliteit om e-mail ergens anders te hosten, bijvoorbeeld op een lokale Exchange-server.</span><span class="sxs-lookup"><span data-stu-id="cdf83-143">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="cdf83-144">Nadelen</span><span class="sxs-lookup"><span data-stu-id="cdf83-144">Disadvantages</span></span>
<span data-ttu-id="cdf83-145">U moet de DNS-records voor Office 365-services zelf instellen (tenzij u een GoDaddy-domein hebt).</span><span class="sxs-lookup"><span data-stu-id="cdf83-145">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="cdf83-146">Als uw huidige DNS-host niet alle vereiste recordtypen voor Microsoft 365 ondersteunt, zijn sommige functies niet beschikbaar en moet u mogelijk overschakelen naar een andere DNS-host.</span><span class="sxs-lookup"><span data-stu-id="cdf83-146">If your current DNS host doesn't support all of the required record types for Microsoft 365, some features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="cdf83-147">Als Office 365 vereisten voor DNS-records verandert of nieuwe services toevoegt, moet u de updates zelf uitvoeren bij uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="cdf83-147">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="cdf83-148">Wat is een domeinnaam?</span><span class="sxs-lookup"><span data-stu-id="cdf83-148">What is a domain name?</span></span>


<span data-ttu-id="cdf83-149">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span><span class="sxs-lookup"><span data-stu-id="cdf83-149">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="cdf83-150">in web addresses.</span><span class="sxs-lookup"><span data-stu-id="cdf83-150">in web addresses.</span></span> <span data-ttu-id="cdf83-151">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="cdf83-151">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="cdf83-152">Het gebruik van een aangepast domein zoals "**rob \@ contoso.com**" met Office 365 kan helpen bij het opbouwen van geloofwaardigheid en erkenning voor uw merk.</span><span class="sxs-lookup"><span data-stu-id="cdf83-152">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="cdf83-153">U kunt [een domein kopen in Office 365, waarna het automatisch wordt ingesteld](../get-help-with-domains/buy-a-domain-name.md). U kunt ook een domein kopen bij een domeinregistrar of een domein gebruiken dat u al hebt.</span><span class="sxs-lookup"><span data-stu-id="cdf83-153">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="cdf83-154">Kan ik een domein dat ik van Microsoft heb gekocht, overzetten naar een andere provider?</span><span class="sxs-lookup"><span data-stu-id="cdf83-154">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="cdf83-155">Ja, maar u een Office 365-domein pas 60 dagen nadat u het hebt gekocht met Office 365, overzetten naar een andere registrar.</span><span class="sxs-lookup"><span data-stu-id="cdf83-155">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="cdf83-156">Houd er rekening mee dat in een *Whois-query* een door Office 365 gekochte domeinregistrar wordt weergegeven als Wild West Domains LLC.</span><span class="sxs-lookup"><span data-stu-id="cdf83-156">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="cdf83-157">Er moet echter alleen contact worden opgenomen met Office 365 met betrekking tot uw door Office 365 gekochte domein.</span><span class="sxs-lookup"><span data-stu-id="cdf83-157">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="cdf83-158">Volg de stappen hieronder om de code op te halen op Office 365. Ga vervolgens naar de website van de andere domeinregistrar om het overzetten van uw domeinnaam naar die registrar in te stellen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-158">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cdf83-159">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cdf83-159">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cdf83-160">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cdf83-160">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cdf83-161">Ga in het beheercentrum naar de pagina **Licenties voor instellingen.** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a></span><span class="sxs-lookup"><span data-stu-id="cdf83-161">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="cdf83-162">Selecteer op de pagina **Domeinen** het Office 365-domein dat u naar een andere domeinregistrar wilt overbrengen en selecteer **vervolgens**  >  **Domeinoverdracht Inschakelen domeinoverdracht**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-162">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="cdf83-163">Volg de stappen om het overzetten van uw domein voor te bereiden.</span><span class="sxs-lookup"><span data-stu-id="cdf83-163">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="cdf83-164">Als u de code hebt opgehaald, gaat u naar de website van de domeinregistrar waar u voortaan de domeinnaam wilt beheren en volgt u de aanwijzingen voor het overzetten van een domein (zoek op de website voor hulp).</span><span class="sxs-lookup"><span data-stu-id="cdf83-164">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="cdf83-165">Als u de code opnieuw moet zien, selecteert u op de pagina **Domeininstellingen** in Office 365 **de machtigingscode weergeven voor domeinoverdracht**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-165">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="cdf83-166">Nadat de overdracht is voltooid, verlengt u uw domein bij de nieuwe domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="cdf83-166">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="cdf83-167">Als u het proces wilt voltooien, gaat u terug naar de pagina **Domeinen** van het beheercentrum en selecteert u **Domeinoverdracht voltooien**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-167">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="cdf83-168">*Opmerking: u houdt er rekening mee dat door Office 365 gekochte domeinen niet in aanmerking komen voor wijzigingen in de naamserver of het domein tussen Office 365-tenants.  Als een van deze vereist is, moet de domeinregistratie worden overgedragen aan een andere registrar.*</span><span class="sxs-lookup"><span data-stu-id="cdf83-168">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="cdf83-169">Hoe kan ik wijzigen hoe mijn DNS-records in Office 365 worden beheerd?</span><span class="sxs-lookup"><span data-stu-id="cdf83-169">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="cdf83-170">DNS-beheer overdragen aan een DNS-host buiten Office 365</span><span class="sxs-lookup"><span data-stu-id="cdf83-170">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="cdf83-171">Meld u aan bij de domeinregistrar voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="cdf83-171">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="cdf83-172">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span><span class="sxs-lookup"><span data-stu-id="cdf83-172">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span></span> <span data-ttu-id="cdf83-173">(The DNS host is often the domain registrar.)</span><span class="sxs-lookup"><span data-stu-id="cdf83-173">(The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="cdf83-174">Volg een koppeling om naar de wizard Domeininstellingen te gaan:</span><span class="sxs-lookup"><span data-stu-id="cdf83-174">Follow a link to go to the domains setup wizard:</span></span>

::: moniker range="o365-worldwide"

4. <span data-ttu-id="cdf83-175">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cdf83-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

4. <span data-ttu-id="cdf83-176">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cdf83-176">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

4. <span data-ttu-id="cdf83-177">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cdf83-177">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
5. <span data-ttu-id="cdf83-178">Selecteer op de pagina **Domeinen** het domein dat u overstapt en selecteer **DNS-beheer.**</span><span class="sxs-lookup"><span data-stu-id="cdf83-178">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="cdf83-179">Selecteer in de wizard Domeininstellingen instellen op de pagina **Uw online services instellen** de optie Ik beheer mijn eigen **DNS-records**en selecteer **vervolgens Volgende**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-179">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="cdf83-180">Voeg de DOOR de wizard voorgestelde DNS-records toe aan de pagina **DNS-instellingen bijwerken** aan de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="cdf83-180">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="cdf83-181">Nadat u de records hebt toegevoegd, gaat u terug naar Office 365 en selecteert **u Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-181">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="cdf83-182">DNS-beheer overdragen aan Office 365</span><span class="sxs-lookup"><span data-stu-id="cdf83-182">Change DNS management to Office 365</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cdf83-183">Ga in het beheercentrum **Settings** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a> instellingen..</span><span class="sxs-lookup"><span data-stu-id="cdf83-183">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page..</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cdf83-184">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cdf83-184">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cdf83-185">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cdf83-185">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="cdf83-186">Selecteer op de pagina **Domeinen** het domein dat u overstapt en selecteer **DNS-beheer**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-186">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="cdf83-187">Selecteer in de wizard Domeininstellingen instellen op de pagina **Uw online services instellen** de optie Mijn online services voor mij **instellen. (Aanbevolen)** en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-187">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="cdf83-188">Als u het domein nog niet hebt gecontroleerd, volg dan de stappen om dat eerst te doen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-188">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="cdf83-189">On the **Update DNS settings** page, we list the nameservers for Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf83-189">On the **Update DNS settings** page, we list the nameservers for Office 365.</span></span> <span data-ttu-id="cdf83-190">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span><span class="sxs-lookup"><span data-stu-id="cdf83-190">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="cdf83-191">Als u de naamservers hebt bijgewerkt, **wacht u minstens een uur**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-191">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="cdf83-192">Selecteer vervolgens terug in de wizard in Office 365 de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-192">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="cdf83-193">Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?</span><span class="sxs-lookup"><span data-stu-id="cdf83-193">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="cdf83-194">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span><span class="sxs-lookup"><span data-stu-id="cdf83-194">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span></span> <span data-ttu-id="cdf83-195">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span><span class="sxs-lookup"><span data-stu-id="cdf83-195">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="cdf83-196">Providers die ondersteuning bieden voor alle vereiste DNS-records:</span><span class="sxs-lookup"><span data-stu-id="cdf83-196">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="cdf83-197">Dynadot</span><span class="sxs-lookup"><span data-stu-id="cdf83-197">Dynadot</span></span>
    
- <span data-ttu-id="cdf83-198">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="cdf83-198">eNomCentral</span></span>
    
- <span data-ttu-id="cdf83-199">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="cdf83-199">Europe Registry</span></span>
    
- <span data-ttu-id="cdf83-200">Godaddy</span><span class="sxs-lookup"><span data-stu-id="cdf83-200">GoDaddy</span></span>
    
- <span data-ttu-id="cdf83-201">Hover</span><span class="sxs-lookup"><span data-stu-id="cdf83-201">Hover</span></span>
    
- <span data-ttu-id="cdf83-202">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="cdf83-202">MyHosting.com</span></span>
    
- <span data-ttu-id="cdf83-203">Name.com</span><span class="sxs-lookup"><span data-stu-id="cdf83-203">Name.com</span></span>
    
- <span data-ttu-id="cdf83-204">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="cdf83-204">Nearly Free Speech</span></span>
    
- <span data-ttu-id="cdf83-205">Nettica</span><span class="sxs-lookup"><span data-stu-id="cdf83-205">Nettica</span></span>
    
- <span data-ttu-id="cdf83-206">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="cdf83-206">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="cdf83-207">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="cdf83-207">Network Solutions</span></span>
    
- <span data-ttu-id="cdf83-208">Register.com</span><span class="sxs-lookup"><span data-stu-id="cdf83-208">Register.com</span></span>
    
 <span data-ttu-id="cdf83-209">**Als SRV-records niet worden ondersteund**, zijn de volgende functies van Office 365 niet beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="cdf83-209">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="cdf83-210">Integratie van de chatfunctie van Skype voor Bedrijven Online en aanwezigheidsgegevens met Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="cdf83-210">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="cdf83-211">Externe communicatie (federatie) met gebruikers van Skype voor Bedrijven Online in andere organisaties.</span><span class="sxs-lookup"><span data-stu-id="cdf83-211">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="cdf83-212">Openbare internetverbinding (Public Internet Connectivity (PIC)) met gebruikers van Skype voor Bedrijven Online die zijn aangemeld met een Microsoft-account (voorheen Windows Live ID).</span><span class="sxs-lookup"><span data-stu-id="cdf83-212">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="cdf83-213">**Als meerdere CNAME-records niet worden ondersteund,** moet u kiezen tussen de volgende functies voor Skype voor Bedrijven Online:</span><span class="sxs-lookup"><span data-stu-id="cdf83-213">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="cdf83-214">E-maildesktopclients en mobiele clients kunnen Automatisch opsporen gebruiken om automatisch de Exchange Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.</span><span class="sxs-lookup"><span data-stu-id="cdf83-214">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="cdf83-215">Desktopclients van Skype voor Bedrijven Online kunnen Automatisch opsporen gebruiken om automatisch de Skype voor Bedrijven Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.</span><span class="sxs-lookup"><span data-stu-id="cdf83-215">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="cdf83-216">Mobiele clients van Skype voor Bedrijven Online kunnen Automatisch opsporen gebruiken om automatisch de Skype voor Bedrijven Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.</span><span class="sxs-lookup"><span data-stu-id="cdf83-216">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>

- <span data-ttu-id="cdf83-217">Microsoft Teams-federatie met Skype voor Bedrijven, on-premises of online.</span><span class="sxs-lookup"><span data-stu-id="cdf83-217">Microsoft Teams federation with Skype for Business, either on-premises or online.</span></span> <span data-ttu-id="cdf83-218">Zie [Het netwerk van uw organisatie voorbereiden voor Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cdf83-218">For more information, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>
    
 <span data-ttu-id="cdf83-219">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span><span class="sxs-lookup"><span data-stu-id="cdf83-219">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span></span> <span data-ttu-id="cdf83-220">SPF records work by identifying the servers that are authorized to send email from your domain.</span><span class="sxs-lookup"><span data-stu-id="cdf83-220">SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="cdf83-221">Hoe stel ik het standaarddomein in Of wijzig ik het in Office 365?</span><span class="sxs-lookup"><span data-stu-id="cdf83-221">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="cdf83-222">U moet minimaal één aangepast domein aan Office 365 hebben toegevoegd voordat u een standaarddomein kunt kiezen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-222">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cdf83-223">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cdf83-223">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cdf83-224">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cdf83-224">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cdf83-225">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cdf83-225">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="cdf83-226">Selecteer op de pagina **Domeinen** het domein dat u wilt instellen als standaard voor nieuwe e-mailadressen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-226">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="cdf83-227">Selecteer **Als standaard instellen**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-227">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="cdf83-228">U kunt de naam van uw initiële  *.onmicrosoft.com*  -domein niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-228">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="cdf83-229">U de naam van uw oorspronkelijke *.onmicrosoft.de-domein* niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-229">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="cdf83-230">U de naam van uw oorspronkelijke *.partner.onmschina.cn-domein* niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-230">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="cdf83-231">Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Office 365?</span><span class="sxs-lookup"><span data-stu-id="cdf83-231">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="cdf83-232">Ja!</span><span class="sxs-lookup"><span data-stu-id="cdf83-232">Yes!</span></span> <span data-ttu-id="cdf83-233">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="cdf83-233">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="cdf83-234">Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein bij Microsoft hebt gekocht, u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-234">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="cdf83-235">Ja!</span><span class="sxs-lookup"><span data-stu-id="cdf83-235">Yes!</span></span> <span data-ttu-id="cdf83-236">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="cdf83-236">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="cdf83-237">Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein bij Microsoft hebt gekocht, u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-237">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="cdf83-238">Ja!</span><span class="sxs-lookup"><span data-stu-id="cdf83-238">Yes!</span></span> <span data-ttu-id="cdf83-239">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="cdf83-239">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="cdf83-240">Als u 21Vianet uw DNS-instellingen laat beheren met NS-records, u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-240">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="cdf83-241">U doorgaans maximaal 900 domeinen toevoegen aan uw Office 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="cdf83-241">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="cdf83-242">U kunt bijvoorbeeld de domeinen contoso.com en contosomarketing.com toevoegen, en vervolgens de subdomeinen www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com enzovoort.</span><span class="sxs-lookup"><span data-stu-id="cdf83-242">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="cdf83-243">Wanneer u een subdomein toevoegt, wordt deze automatisch geverifieerd op basis van het bovenliggende domein dat wordt geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="cdf83-243">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="cdf83-244">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span><span class="sxs-lookup"><span data-stu-id="cdf83-244">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="cdf83-245">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span><span class="sxs-lookup"><span data-stu-id="cdf83-245">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="cdf83-246">Als u al een contoso.com domein hebt toegevoegd aan een Office 365-tenant, u het subdomein xyz.contoso.com ook toevoegen aan een andere Office 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="cdf83-246">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="cdf83-247">Wanneer u het subdomein toevoegt, wordt u gevraagd om een TXT-record toe te voegen aan de DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="cdf83-247">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="cdf83-248">Waarom heb ik een domein met de naam onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="cdf83-248">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="cdf83-249">Office 365 maakt een domein voor u, zoals *contoso.onmicrosoft.com,* wanneer u zich aanmeldt bij de service.</span><span class="sxs-lookup"><span data-stu-id="cdf83-249">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="cdf83-250">De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="cdf83-250">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="cdf83-251">**Als u uw e-mail eruit wilt laten zien als *alan \@ contoso.com:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Office [365](add-domain.md) als u het al bezit.</span><span class="sxs-lookup"><span data-stu-id="cdf83-251">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="cdf83-252">**You can't rename the onmicrosoft domain after sign-up.**</span><span class="sxs-lookup"><span data-stu-id="cdf83-252">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="cdf83-253">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="cdf83-253">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="cdf83-254">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf83-254">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="cdf83-255">**U de naam van de URL van uw teamsite niet wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="cdf83-255">**You can't rename your team site URL.**</span></span> <span data-ttu-id="cdf83-256">De URL van uw teamsite is gebaseerd op uw onmicrosoft.com domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="cdf83-256">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="cdf83-257">Vanwege de manier waarop de SharePoint Online-architectuur werkt, u de naam van de teamsite helaas niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-257">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="cdf83-258">**You can't remove your onmicrosoft domain.**</span><span class="sxs-lookup"><span data-stu-id="cdf83-258">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="cdf83-259">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span><span class="sxs-lookup"><span data-stu-id="cdf83-259">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="cdf83-260">But you don't have to use the domain yourself after you've added a custom domain.</span><span class="sxs-lookup"><span data-stu-id="cdf83-260">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="cdf83-261">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span><span class="sxs-lookup"><span data-stu-id="cdf83-261">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="cdf83-262">It still works for email and other services, so it's your choice.</span><span class="sxs-lookup"><span data-stu-id="cdf83-262">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="cdf83-263">Waarom heb ik een 'onmicrosoft.de'-domein?</span><span class="sxs-lookup"><span data-stu-id="cdf83-263">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="cdf83-264">Office 365 maakt een domein voor u, zoals *contoso.onmicrosoft.de,* wanneer u zich aanmeldt bij de service.</span><span class="sxs-lookup"><span data-stu-id="cdf83-264">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="cdf83-265">De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="cdf83-265">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="cdf83-266">**Als u uw e-mail eruit wilt laten zien als *alan@contoso.de:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Office [365](add-domain.md) als u het al bezit.</span><span class="sxs-lookup"><span data-stu-id="cdf83-266">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="cdf83-267">**U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.**</span><span class="sxs-lookup"><span data-stu-id="cdf83-267">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="cdf83-268">Als het oorspronkelijke domein dat u hebt gekozen bijvoorbeeld fourthcoffee.onmicrosoft.de, u het niet wijzigen om te worden fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="cdf83-268">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="cdf83-269">Als u een ander onmicrosoft.de domein wilt gebruiken, moet u een nieuw abonnement starten met Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf83-269">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="cdf83-270">**U de naam van de URL van uw teamsite niet wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="cdf83-270">**You can't rename your team site URL.**</span></span> <span data-ttu-id="cdf83-271">De URL van uw teamsite is gebaseerd op uw onmicrosoft.de domeinnaam. Vanwege de manier waarop de SharePoint Online-architectuur werkt, u de naam van de teamsite helaas niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-271">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="cdf83-272">**You can't remove your onmicrosoft domain.**</span><span class="sxs-lookup"><span data-stu-id="cdf83-272">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="cdf83-273">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span><span class="sxs-lookup"><span data-stu-id="cdf83-273">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="cdf83-274">But you don't have to use the domain yourself after you've added a custom domain.</span><span class="sxs-lookup"><span data-stu-id="cdf83-274">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="cdf83-275">U de initiële onmicrosoft.de domein blijven gebruiken, zelfs nadat u uw domein hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="cdf83-275">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="cdf83-276">Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.</span><span class="sxs-lookup"><span data-stu-id="cdf83-276">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="cdf83-277">Hoe verifieer ik mijn status zonder winstoogoogs naar een opleiding?</span><span class="sxs-lookup"><span data-stu-id="cdf83-277">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="cdf83-278">Selecteer **Setup** in het [beheercentrum](https://docs.microsoft.com/microsoft-365/admin/admin-home) om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="cdf83-278">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="cdf83-279">(Moet je eerst aanmelden bij Office 365.)</span><span class="sxs-lookup"><span data-stu-id="cdf83-279">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="cdf83-280">Als u beheerder van uw school wilt worden, selecteert u de optie **Een beheerder in** Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf83-280">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="cdf83-281">U wordt gevraagd om een TXT DNS-record toe te voegen op de DNS-hostwebsite voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="cdf83-281">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="cdf83-282">Waarom?</span><span class="sxs-lookup"><span data-stu-id="cdf83-282">Why?</span></span> <span data-ttu-id="cdf83-283">Omdat u door u aan te melden bij de DNS-host en een record voor uw domein toe te voegen, aan Office 365 bewijst dat u eigenaar bent van de domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="cdf83-283">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="cdf83-284">Nadat u de record hebt toegevoegd, gaat u terug naar de Office 365-portal en bevestigt u dat u deze hebt toegevoegd, zodat Office 365 deze kan controleren.</span><span class="sxs-lookup"><span data-stu-id="cdf83-284">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="cdf83-285">Hebt u een non-profitorganisatie en wilt u Office 365 ophalen?</span><span class="sxs-lookup"><span data-stu-id="cdf83-285">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="cdf83-286">[Zorg ervoor dat uw organisatie in aanmerking komt](https://www.microsoft.com/en-us/nonprofits/eligibility) en meld u vervolgens aan voor de service.</span><span class="sxs-lookup"><span data-stu-id="cdf83-286">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="cdf83-287">Wilt u meer weten over het worden van de admin voor uw school?</span><span class="sxs-lookup"><span data-stu-id="cdf83-287">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="cdf83-288">[Leer er alles over.](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)</span><span class="sxs-lookup"><span data-stu-id="cdf83-288">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="cdf83-289">Kan ik Office 365 besturen met slechts een paar e-mailadressen uit mijn aangepaste domein?</span><span class="sxs-lookup"><span data-stu-id="cdf83-289">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="cdf83-290">Dat kan, maar er zijn beperkingen:</span><span class="sxs-lookup"><span data-stu-id="cdf83-290">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="cdf83-291">Uw huidige e-mailprovider moet e-mail doorsturen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-291">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="cdf83-292">U moet uw DNS-records met Office 365 beheren bij uw DNS-hostingprovider, in plaats van dat Office 365 deze records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="cdf83-292">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="cdf83-293">Zie Uw domein toevoegen aan Office 365 wanneer u uw eigen DNS-records wilt beheren voor meer informatie over dit inhoudt.</span><span class="sxs-lookup"><span data-stu-id="cdf83-293">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="cdf83-294">Sommige Office 365-functies zijn niet beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="cdf83-294">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="cdf83-295">Gebruikers kunnen geen gratis/drukke informatie zien voor de gebruikers die zich op de andere e-mailprovider bevinden.</span><span class="sxs-lookup"><span data-stu-id="cdf83-295">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="cdf83-296">Beheerders kunnen de accounts van niet vanaf één plek beheren.</span><span class="sxs-lookup"><span data-stu-id="cdf83-296">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="cdf83-297">Gebruikers kunnen mogelijk geen Office 365-spamfilter gebruiken</span><span class="sxs-lookup"><span data-stu-id="cdf83-297">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="cdf83-298">Een Office 365-pilot instellen</span><span class="sxs-lookup"><span data-stu-id="cdf83-298">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="cdf83-299">Aanmelden bij het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="cdf83-299">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="cdf83-300">Meld u aan bij Office 365 met uw werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="cdf83-300">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="cdf83-301">Ga **Settings** naar \> **Instellingendomeinen**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-301">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="cdf83-302">Controleren of u eigenaar bent van het domein dat u wilt gebruiken</span><span class="sxs-lookup"><span data-stu-id="cdf83-302">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="cdf83-303">Selecteer **domein toevoegen**op de pagina **Domeinen** .</span><span class="sxs-lookup"><span data-stu-id="cdf83-303">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="cdf83-304">Typ in het deelvenster het domein in dit voorbeeld cohowinery.com en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-304">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="cdf83-305">Volg **op** de pagina Domein verifiëren de stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="cdf83-305">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="cdf83-306">Selecteer in de vervolgkeuzelijst uw DNS-hostingprovider en volg de instructies om aan te geven dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="cdf83-306">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="cdf83-307">Selecteer **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-307">Select **Verify**.</span></span> <span data-ttu-id="cdf83-308">Het duurt tussen een paar minuten en 72 uur voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="cdf83-308">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="cdf83-309">Wanneer de verificatie is geslaagd, wordt u gevraagd uw DNS-records te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-309">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="cdf83-310">Het domein markeren als gedeeld in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cdf83-310">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="cdf83-311">Ga naar het **Exchange-beheercentrum** (EAC).</span><span class="sxs-lookup"><span data-stu-id="cdf83-311">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="cdf83-312">Selecteer **geaccepteerde domeinen**in de sectie **E-mailstroom** .</span><span class="sxs-lookup"><span data-stu-id="cdf83-312">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="cdf83-313">Dubbelklik op het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-313">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="cdf83-314">Selecteer **Intern relais**in het venster dat wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="cdf83-314">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="cdf83-315">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-315">Select **Save**.</span></span> <span data-ttu-id="cdf83-316">Deze instelling kan enkele minuten nodig hebben om van kracht te worden.</span><span class="sxs-lookup"><span data-stu-id="cdf83-316">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="cdf83-317">De blokkering van de bestaande e-mailserver des te deblokkeren</span><span class="sxs-lookup"><span data-stu-id="cdf83-317">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="cdf83-318">Office 365 gebruikt Exchange Online Protection (EOP) voor spambescherming.</span><span class="sxs-lookup"><span data-stu-id="cdf83-318">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="cdf83-319">Als EOP detecteert dat een groot aantal spam wordt doorgestuurd door uw huidige e-mailserver, kan deze worden geblokkeerd, waardoor doorsturen niet werkt.</span><span class="sxs-lookup"><span data-stu-id="cdf83-319">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="cdf83-320">Als u vertrouwen hebt in de spambescherming die uw andere e-mailprovider gebruikt, u hun server toevoegen aan een lijst met toegestaneen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf83-320">If you are confident with the spam protection your other email provider uses, you can add their server to an allow list in Office 365.</span></span> <span data-ttu-id="cdf83-321">Hierdoor kan echter ook spam via uw oorspronkelijke server worden geleverd via de Office 365-postvakken en u niet beoordelen hoe goed Office 365 spam voorkomt.</span><span class="sxs-lookup"><span data-stu-id="cdf83-321">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="cdf83-322">Ga naar Exchange admin center (EAC).</span><span class="sxs-lookup"><span data-stu-id="cdf83-322">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="cdf83-323">Selecteer in EAC **Beveiliging**en selecteer **Vervolgens Verbindingsfilter**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-323">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="cdf83-324">Selecteer in de **lijst IP Toestaan**het IP-adres van de **+** e-mailserver dat u van uw huidige e-mailprovider krijgen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-324">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="cdf83-325">Gebruikersaccounts maken en het primaire (reply-to) adres instellen</span><span class="sxs-lookup"><span data-stu-id="cdf83-325">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="cdf83-326">Ga naar het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cdf83-326">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="cdf83-327">Selecteer op de linkernavigatiebalk **De** optie \> **Actieve gebruikers van**gebruikers .</span><span class="sxs-lookup"><span data-stu-id="cdf83-327">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="cdf83-328">Maak de gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="cdf83-328">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="cdf83-329">Selecteer voor elk account **+ (Nieuw)** en vul de vereiste informatie in.</span><span class="sxs-lookup"><span data-stu-id="cdf83-329">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="cdf83-330">Om de e-mail van de gebruiker hetzelfde te houden als nu, moet het veld **Gebruikersnaam** exact hetzelfde zijn als het bestaande e-mailadres van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cdf83-330">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="cdf83-331">Selecteer naast gebruikersnaam uw aangepaste domeinnaam in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="cdf83-331">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="cdf83-332">Selecteer **Sluiten** \> **maken**.</span><span class="sxs-lookup"><span data-stu-id="cdf83-332">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="cdf83-333">DNS-records bijwerken bij uw DNS-hostingprovider</span><span class="sxs-lookup"><span data-stu-id="cdf83-333">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="cdf83-334">Meld u aan bij de website van uw DNS-hostingprovider en volg de [DNS-records maken bij elke DNS-hostingprovider voor Office 365-stappen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="cdf83-334">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="cdf83-335">**Maak de volgende uitzonderingen:**</span><span class="sxs-lookup"><span data-stu-id="cdf83-335">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="cdf83-336">Maak geen nieuwe MX-record en wijzig uw bestaande MX-record niet.</span><span class="sxs-lookup"><span data-stu-id="cdf83-336">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="cdf83-337">Als u al een SPF-record (Sender Policy Framework) hebt voor uw vorige e-mailprovider, voegt u in plaats van een nieuwe SPF-record (TXT) voor Exchange Online op te maken, gewoon 'include:spf.protection.outlook.com' toe aan de huidige TXT-record.</span><span class="sxs-lookup"><span data-stu-id="cdf83-337">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="cdf83-338">Bijvoorbeeld, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="cdf83-338">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="cdf83-339">Als u nog geen SPF-record hebt, wijzigt u de door Office 365 aanbevolen record om het domein voor uw huidige e-mailprovider op te nemen, plus spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cdf83-339">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="cdf83-340">Dit machtigt uitgaande berichten van beide e-mailsystemen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-340">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="cdf83-341">E-mail doorsturen instellen bij uw huidige provider</span><span class="sxs-lookup"><span data-stu-id="cdf83-341">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="cdf83-342">Stel bij uw huidige e-mailprovider doorsturen in voor uw gebruikers-e-mailaccounts naar uw onmicrosoft.com domein:</span><span class="sxs-lookup"><span data-stu-id="cdf83-342">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="cdf83-343">Het postvak van gebruiker A moet doorsturen naar usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="cdf83-343">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="cdf83-344">Het postvak van gebruiker B moet doorsturen naar userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="cdf83-344">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="cdf83-345">Wanneer u deze stap voltooit:</span><span class="sxs-lookup"><span data-stu-id="cdf83-345">When you complete this step:</span></span>
        
    5. <span data-ttu-id="cdf83-346">Alle e-mails die naar usera@yourcompany.com en userb@yourcompany.com worden verzonden, zijn beschikbaar in Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdf83-346">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="cdf83-347">Opmerkingen:</span><span class="sxs-lookup"><span data-stu-id="cdf83-347">Notes:</span></span>
        
        - <span data-ttu-id="cdf83-348">Neem contact op met uw huidige e-mailprovider voor de exacte stappen voor het instellen van doorsturen.</span><span class="sxs-lookup"><span data-stu-id="cdf83-348">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="cdf83-349">U hoeft geen kopie van berichten bij de huidige e-mailprovider te bewaren.</span><span class="sxs-lookup"><span data-stu-id="cdf83-349">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="cdf83-350">De meeste providers sturen e-mail door en laten het antwoordadres van de afzender intact, zodat de antwoorden naar de oorspronkelijke afzender gaan.</span><span class="sxs-lookup"><span data-stu-id="cdf83-350">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="cdf83-351">E-mailstroom testen</span><span class="sxs-lookup"><span data-stu-id="cdf83-351">Test mail flow</span></span>
    
    1. <span data-ttu-id="cdf83-352">Meld u aan bij Outlook Web App met de referenties van gebruiker A.</span><span class="sxs-lookup"><span data-stu-id="cdf83-352">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="cdf83-353">Voer de volgende tests uit:</span><span class="sxs-lookup"><span data-stu-id="cdf83-353">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="cdf83-354">Test lokale Microsoft-e-mail.</span><span class="sxs-lookup"><span data-stu-id="cdf83-354">Test local Microsoft email.</span></span> <span data-ttu-id="cdf83-355">Stuur bijvoorbeeld een e-mail naar gebruiker B. Deze e-mail moet onmiddellijk worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="cdf83-355">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="cdf83-356">In dit scenario wordt het bericht niet doorgestuurd naar het postvak van gebruiker B op uw oorspronkelijke server, omdat het postvak in Office 365 lokaal is.</span><span class="sxs-lookup"><span data-stu-id="cdf83-356">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="cdf83-357">Test e-mail naar iemand die op het andere e-mailsysteem staat.</span><span class="sxs-lookup"><span data-stu-id="cdf83-357">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="cdf83-358">Stuur bijvoorbeeld een e-mail naar gebruiker C. Deze e-mail moet worden bezorgd in het postvak van gebruiker C op uw oorspronkelijke e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="cdf83-358">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="cdf83-359">Controleer vanaf een extern account of van het e-mailaccount van een werknemer op het andere e-mailsysteem of doorsturen correct is ingesteld op het andere e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="cdf83-359">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="cdf83-360">Stuur gebruiker A bijvoorbeeld vanuit het oorspronkelijke serveraccount van gebruiker C of een Hotmail-account een e-mail en controleer of deze binnenkomt in het Office 365-postvak van gebruiker A.</span><span class="sxs-lookup"><span data-stu-id="cdf83-360">For example, from User C's original server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="cdf83-361">Inhoud van postvakken verplaatsen</span><span class="sxs-lookup"><span data-stu-id="cdf83-361">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="cdf83-362">Aangezien er slechts twee gebruikers te verplaatsen, en aangezien gebruiker A en gebruiker B zijn beide met behulp van Outlook al, de e-mail kan worden verplaatst door het openen van de oude . PST-bestand in het nieuwe Outlook-profiel en het kopiëren van de berichten, agenda-items, contactpersonen, enz.</span><span class="sxs-lookup"><span data-stu-id="cdf83-362">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="cdf83-363">Eenmaal georganiseerd op de juiste locaties in het Office 365-postvak, zijn de items allemaal toegankelijk vanaf elk apparaat, overal.</span><span class="sxs-lookup"><span data-stu-id="cdf83-363">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="cdf83-364">Wanneer er meer postvakken bij betrokken zijn of als de werknemers Outlook nog niet gebruiken, u de migratiehulpprogramma's gebruiken die beschikbaar zijn in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cdf83-364">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="cdf83-365">Ga naar Exchange-beheercentrum en volg de aanwijzingen in E-mail migreren van een IMAP-server naar Exchange Online-postvakken om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="cdf83-365">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
