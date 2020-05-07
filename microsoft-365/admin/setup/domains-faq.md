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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Meer informatie over domeinen vindt u antwoorden op uw vragen in veelgestelde vragen.
ms.custom: okr_smb
ms.openlocfilehash: 09e811b64def4d507a9d825f95b9d22f910669bb
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140747"
---
# <a name="domains-faq"></a><span data-ttu-id="57e43-103">Veelgestelde vragen over domeinen</span><span class="sxs-lookup"><span data-stu-id="57e43-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="57e43-104">Het beheercentrum verandert.</span><span class="sxs-lookup"><span data-stu-id="57e43-104">The admin center is changing.</span></span> <span data-ttu-id="57e43-105">Als uw ervaring niet overeenkomt met de hier gepresenteerde details, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="57e43-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="57e43-106">Dit artikel bevat antwoorden op veelgestelde vragen over domeinen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="57e43-106">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="57e43-107">Als u geen antwoord op uw vraag kunt vinden, kunt u dit laten weten door een opmerking achter te laten. Deze wordt dan aan de lijst toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="57e43-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="57e43-108">Wat is MX-prioriteit?</span><span class="sxs-lookup"><span data-stu-id="57e43-108">What is MX priority?</span></span>

<span data-ttu-id="57e43-109">E-mail wordt bezorgd bij de Mail Exchange-server met het laagste voorkeursgetal (hoogste prioriteit), dus de MX-record die u gebruikt om e-mail te routeren, moet het laagste voorkeursgetal hebben, gewoonlijk 0 of met prioriteit  *Hoog*  .</span><span class="sxs-lookup"><span data-stu-id="57e43-109">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="57e43-110">Voor de meeste DNS-hostingproviders geldt dat u bij het maken van een MX-record het voorkeursgetal moet instellen.</span><span class="sxs-lookup"><span data-stu-id="57e43-110">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="57e43-111">Sommigen geven het vak het label  *voorkeur*  , anderen het label  *prioriteit*  .</span><span class="sxs-lookup"><span data-stu-id="57e43-111">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="57e43-112">Sommigen vereisen een getal, anderen vragen u  *Laag*  ,  *Gemiddeld*  of  *Hoog*  te selecteren.</span><span class="sxs-lookup"><span data-stu-id="57e43-112">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="57e43-113">Als u slechts één MX-record hebt, kunt u een willekeurige waarde voor prioriteit of voorkeur gebruiken.</span><span class="sxs-lookup"><span data-stu-id="57e43-113">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="57e43-114">Als u er meerdere hebt, dan moet u ervoor zorgen dat de MX-record voor e-mailroutering een hogere prioriteit heeft dan de record die wordt gebruikt om te valideren dat het domein van u is.</span><span class="sxs-lookup"><span data-stu-id="57e43-114">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="57e43-115">Hoe kan ik SPF-records voor mijn domein valideren?</span><span class="sxs-lookup"><span data-stu-id="57e43-115">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="57e43-116">Het is belangrijk dat u **slechts één TXT-record voor SPF**hebt of maakt.</span><span class="sxs-lookup"><span data-stu-id="57e43-116">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="57e43-117">Als u al een SPF-record hebt, moet u de nieuwe Office 365-waarden eraan toevoegen in plaats van een nieuwe te maken.</span><span class="sxs-lookup"><span data-stu-id="57e43-117">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="57e43-118">Nadat u uw SPF-record voor Microsoft-e-mail hebt toegevoegd of bijgewerkt, moet u controleren of de syntaxis correct is met een van deze hulpprogramma's:</span><span class="sxs-lookup"><span data-stu-id="57e43-118">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="57e43-119">Hulpprogramma's voor het testen van SPF-records</span><span class="sxs-lookup"><span data-stu-id="57e43-119">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="57e43-120">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="57e43-120">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="57e43-121">Dig webinterface</span><span class="sxs-lookup"><span data-stu-id="57e43-121">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="57e43-122">Hoe worden mijn DNS-records door Office 365 beheerd?</span><span class="sxs-lookup"><span data-stu-id="57e43-122">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="57e43-123">Er zijn twee opties voor DNS-beheer met Office 365:</span><span class="sxs-lookup"><span data-stu-id="57e43-123">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="57e43-124">U wijzigt uw ns-records (nameserver) en vervolgens zorgt Microsoft voor alle servicespecifieke records, zoals het instellen van uw MX-record voor e-mail.</span><span class="sxs-lookup"><span data-stu-id="57e43-124">You change your nameserver (NS) records, and then Microsoft takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="57e43-125">**(Aanbevolen)**</span><span class="sxs-lookup"><span data-stu-id="57e43-125">**(Recommended)**</span></span>
    
2. <span data-ttu-id="57e43-126">U voegt DNS-records voor e-mail en andere Office 365-services bij uw DNS-host zelf toe.</span><span class="sxs-lookup"><span data-stu-id="57e43-126">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="57e43-127">**(Alleen voor experts)**</span><span class="sxs-lookup"><span data-stu-id="57e43-127">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="57e43-128">Office 365 maakt en host de DNS-records</span><span class="sxs-lookup"><span data-stu-id="57e43-128">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="57e43-129">**Voordelen**</span><span class="sxs-lookup"><span data-stu-id="57e43-129">**Advantages**</span></span> 
- <span data-ttu-id="57e43-130">U hoeft niet bang te zijn om fouten te maken bij de waarden die u invoert voor de DNS-records voor Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="57e43-130">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="57e43-131">U hebt meer flexibiliteit bij het kiezen van een domeinregistrar en DNS-host.</span><span class="sxs-lookup"><span data-stu-id="57e43-131">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="57e43-132">U kunt elke provider gebruiken waarbij u uw naamserverrecords kunt wijzigen, zelfs als de provider niet alle vereiste recordtypen ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="57e43-132">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="57e43-133">Wanneer Office 365 nieuwe DNS-records toevoegt, hoeft u geen updates uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="57e43-133">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="57e43-134">Nadelen</span><span class="sxs-lookup"><span data-stu-id="57e43-134">Disadvantages</span></span> 
- <span data-ttu-id="57e43-135">U kunt uw DNS-records niet wijzigen om e-mail buiten Office 365 te hosten.</span><span class="sxs-lookup"><span data-stu-id="57e43-135">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="57e43-136">Als u al een openbare website met uw domein gebruikt voor het adres, zoals www.fourthcoffee.com, moet u mensen vanuit Office 365 naar dat adres doorverwijzen.</span><span class="sxs-lookup"><span data-stu-id="57e43-136">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="57e43-137">Het instellen van omleiding vereist een statisch IP-adres, dat niet altijd gemakkelijk beschikbaar is voor openbare websites.</span><span class="sxs-lookup"><span data-stu-id="57e43-137">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="57e43-138">- Als uw huidige domeinregistrar u niet toestaat om de naamserverrecords van uw domein te wijzigen, moet u overschakelen naar een andere registrar om deze DNS-beheeroptie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="57e43-138">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="57e43-139">U beheert de DNS-records zelf</span><span class="sxs-lookup"><span data-stu-id="57e43-139">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="57e43-140">Voordelen</span><span class="sxs-lookup"><span data-stu-id="57e43-140">Advantages</span></span>
- <span data-ttu-id="57e43-141">U beheert de DNS-records voor Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="57e43-141">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="57e43-142">Als u een openbare website hebt met uw domein als het adres, zoals www.fourthcoffee.com, hoeft u geen omleiding te gebruiken om ervoor te zorgen dat mensen uw website nog kunnen bereiken nadat u uw domein hebt ingesteld in Office 365.</span><span class="sxs-lookup"><span data-stu-id="57e43-142">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="57e43-143">U hebt de flexibiliteit om e-mail ergens anders te hosten, bijvoorbeeld op een lokale Exchange-server.</span><span class="sxs-lookup"><span data-stu-id="57e43-143">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="57e43-144">Nadelen</span><span class="sxs-lookup"><span data-stu-id="57e43-144">Disadvantages</span></span>
<span data-ttu-id="57e43-145">U moet de DNS-records voor Office 365-services zelf instellen (tenzij u een GoDaddy-domein hebt).</span><span class="sxs-lookup"><span data-stu-id="57e43-145">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="57e43-146">Als uw huidige DNS-host niet alle vereiste recordtypen voor Microsoft 365 ondersteunt, zijn sommige functies niet beschikbaar en moet u mogelijk overschakelen naar een andere DNS-host.</span><span class="sxs-lookup"><span data-stu-id="57e43-146">If your current DNS host doesn't support all of the required record types for Microsoft 365, some features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="57e43-147">Als Office 365 vereisten voor DNS-records verandert of nieuwe services toevoegt, moet u de updates zelf uitvoeren bij uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="57e43-147">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="57e43-148">Wat is een domeinnaam?</span><span class="sxs-lookup"><span data-stu-id="57e43-148">What is a domain name?</span></span>


<span data-ttu-id="57e43-p106">Een domein is een unieke naam die na het **@** -teken wordt weergegeven in een e-mailadres en na **www.** in een webadres. Meestal bestaat deze uit de naam van uw organisatie en een standaard-internetachtervoegsel, zoals  *uwbedrijf.com*  of  *universiteit.edu*  .</span><span class="sxs-lookup"><span data-stu-id="57e43-p106">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="57e43-152">Het gebruik van een aangepast domein zoals "**rob\@contoso.com**" met Office 365 kan helpen bij het opbouwen van geloofwaardigheid en erkenning voor uw merk.</span><span class="sxs-lookup"><span data-stu-id="57e43-152">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="57e43-153">U kunt [een domein kopen in Office 365, waarna het automatisch wordt ingesteld](../get-help-with-domains/buy-a-domain-name.md). U kunt ook een domein kopen bij een domeinregistrar of een domein gebruiken dat u al hebt.</span><span class="sxs-lookup"><span data-stu-id="57e43-153">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="57e43-154">Kan ik een domein dat ik van Microsoft heb gekocht, overdragen aan een andere provider?</span><span class="sxs-lookup"><span data-stu-id="57e43-154">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="57e43-155">Ja, maar u een Office 365-domein pas 60 dagen nadat u het hebt gekocht met Office 365 overdragen naar een andere registrar.</span><span class="sxs-lookup"><span data-stu-id="57e43-155">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="57e43-156">Houd er rekening mee dat een *Whois-query* een door Office 365 gekochte domeinregistrar wordt weergegeven als Wild West Domains LLC.</span><span class="sxs-lookup"><span data-stu-id="57e43-156">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="57e43-157">Er moet echter alleen contact worden opgenomen met Office 365 met betrekking tot uw office 365-domein.</span><span class="sxs-lookup"><span data-stu-id="57e43-157">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="57e43-158">Volg de stappen hieronder om de code op te halen op Office 365. Ga vervolgens naar de website van de andere domeinregistrar om het overzetten van uw domeinnaam naar die registrar in te stellen.</span><span class="sxs-lookup"><span data-stu-id="57e43-158">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="57e43-159">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="57e43-159">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="57e43-160">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="57e43-160">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="57e43-161">Ga in het beheercentrum naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Instellingenlicenties.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="57e43-161">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="57e43-162">Selecteer **op** de pagina Domeinen het Office 365-domein dat u naar een andere domeinregistrar wilt overbrengen en selecteer **vervolgens Domeinoverdracht** > **inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="57e43-162">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="57e43-163">Volg de stappen om het overzetten van uw domein voor te bereiden.</span><span class="sxs-lookup"><span data-stu-id="57e43-163">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="57e43-164">Als u de code hebt opgehaald, gaat u naar de website van de domeinregistrar waar u voortaan de domeinnaam wilt beheren en volgt u de aanwijzingen voor het overzetten van een domein (zoek op de website voor hulp).</span><span class="sxs-lookup"><span data-stu-id="57e43-164">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="57e43-165">Als u de code opnieuw wilt zien, selecteert u op de pagina **Domeininstellingen** in Office 365 de optie **Autorisatiecode voor domeinoverdracht weergeven.**</span><span class="sxs-lookup"><span data-stu-id="57e43-165">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="57e43-166">Nadat de overdracht is voltooid, verlengt u uw domein bij de nieuwe domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="57e43-166">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="57e43-167">Als u het proces wilt voltooien, gaat u terug naar de pagina **Domeinen van** het beheercentrum en selecteert u **Volledige domeinoverdracht**.</span><span class="sxs-lookup"><span data-stu-id="57e43-167">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="57e43-168">*Opmerking: Houd er rekening mee dat office 365-gekochte domeinen niet in aanmerking komen voor wijzigingen in naamserver of het overdragen van het domein tussen Office 365-tenants.  Als een van deze vereist is, moet de domeinregistratie worden overgedragen aan een andere registrar.*</span><span class="sxs-lookup"><span data-stu-id="57e43-168">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="57e43-169">Hoe kan ik wijzigen hoe mijn DNS-records in Office 365 worden beheerd?</span><span class="sxs-lookup"><span data-stu-id="57e43-169">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="57e43-170">DNS-beheer overdragen aan een DNS-host buiten Office 365</span><span class="sxs-lookup"><span data-stu-id="57e43-170">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="57e43-171">Meld u aan bij de domeinregistrar voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="57e43-171">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="57e43-p108">Ga naar het gedeelte op de website van uw registrar waar u naamserverrecords kunt bijwerken en werk de naamservers bij zodat ze verwijzen naar de DNS-host voor uw domein. (De DNS-host is vaak de domeinregistrar.)</span><span class="sxs-lookup"><span data-stu-id="57e43-p108">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host. (The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="57e43-174">Volg een koppeling om naar de wizard domeinensetup te gaan:</span><span class="sxs-lookup"><span data-stu-id="57e43-174">Follow a link to go to the domains setup wizard:</span></span>

::: moniker range="o365-worldwide"

4. <span data-ttu-id="57e43-175">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="57e43-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

4. <span data-ttu-id="57e43-176">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="57e43-176">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

4. <span data-ttu-id="57e43-177">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="57e43-177">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
5. <span data-ttu-id="57e43-178">Selecteer **op** de pagina Domeinen het domein dat u overschakelt en selecteer **DNS-beheer.**</span><span class="sxs-lookup"><span data-stu-id="57e43-178">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="57e43-179">Selecteer in de wizard Domeinen instellen op de pagina **Uw onlineservices instellen** de optie **Ik beheer mijn eigen DNS-records**en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="57e43-179">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="57e43-180">Voeg de DNS-records die door de wizard worden voorgesteld toe aan de pagina **DNS-instellingen bijwerken** aan de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="57e43-180">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="57e43-181">Nadat u de records hebt toegevoegd, gaat u terug naar Office 365 en selecteert **u Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="57e43-181">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="57e43-182">DNS-beheer overdragen aan Office 365</span><span class="sxs-lookup"><span data-stu-id="57e43-182">Change DNS management to Office 365</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="57e43-183">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen..</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="57e43-183">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page..</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="57e43-184">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="57e43-184">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="57e43-185">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="57e43-185">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="57e43-186">Selecteer **op** de pagina Domeinen het domein dat u overschakelt en selecteer **DNS-beheer.**</span><span class="sxs-lookup"><span data-stu-id="57e43-186">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="57e43-187">Selecteer in de wizard Domeinen instellen op de pagina **Uw onlineservices instellen** de optie **Mijn onlineservices voor mij instellen. (Aanbevolen)** en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="57e43-187">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="57e43-188">Als u het domein nog niet hebt gecontroleerd, volg dan de stappen om dat eerst te doen.</span><span class="sxs-lookup"><span data-stu-id="57e43-188">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="57e43-p109">Op de pagina **DNS-instellingen bijwerken** ziet u de naamservers voor Office 365. Ga naar de domeinregistrar voor uw domein en wijzig de naamservers in de Office 365-naamservers.</span><span class="sxs-lookup"><span data-stu-id="57e43-p109">On the **Update DNS settings** page, we list the nameservers for Office 365. Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="57e43-191">Als u de naamservers hebt bijgewerkt, **wacht u minstens een uur**.</span><span class="sxs-lookup"><span data-stu-id="57e43-191">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="57e43-192">Selecteer vervolgens terug in de wizard in Office 365 de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="57e43-192">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="57e43-193">Wat gebeurt er als mijn DNS-provider geen ondersteuning biedt voor bepaalde recordtypen?</span><span class="sxs-lookup"><span data-stu-id="57e43-193">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="57e43-p111">Als u zelf uw DNS-records beheert en uw DNS-hosting geen ondersteuning biedt voor alle DNS-records die nodig zijn voor Office 365, werken sommige functies van Office 365 niet. U wordt aangeraden uw domein over te zetten naar een registrar die ondersteuning biedt voor alle vereiste DNS-records.</span><span class="sxs-lookup"><span data-stu-id="57e43-p111">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work. We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="57e43-196">Providers die ondersteuning bieden voor alle vereiste DNS-records:</span><span class="sxs-lookup"><span data-stu-id="57e43-196">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="57e43-197">Dynadot</span><span class="sxs-lookup"><span data-stu-id="57e43-197">Dynadot</span></span>
    
- <span data-ttu-id="57e43-198">eNomCentraal</span><span class="sxs-lookup"><span data-stu-id="57e43-198">eNomCentral</span></span>
    
- <span data-ttu-id="57e43-199">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="57e43-199">Europe Registry</span></span>
    
- <span data-ttu-id="57e43-200">Godaddy</span><span class="sxs-lookup"><span data-stu-id="57e43-200">GoDaddy</span></span>
    
- <span data-ttu-id="57e43-201">Hover</span><span class="sxs-lookup"><span data-stu-id="57e43-201">Hover</span></span>
    
- <span data-ttu-id="57e43-202">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="57e43-202">MyHosting.com</span></span>
    
- <span data-ttu-id="57e43-203">Name.com</span><span class="sxs-lookup"><span data-stu-id="57e43-203">Name.com</span></span>
    
- <span data-ttu-id="57e43-204">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="57e43-204">Nearly Free Speech</span></span>
    
- <span data-ttu-id="57e43-205">Nettica</span><span class="sxs-lookup"><span data-stu-id="57e43-205">Nettica</span></span>
    
- <span data-ttu-id="57e43-206">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="57e43-206">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="57e43-207">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="57e43-207">Network Solutions</span></span>
    
- <span data-ttu-id="57e43-208">Register.com</span><span class="sxs-lookup"><span data-stu-id="57e43-208">Register.com</span></span>
    
 <span data-ttu-id="57e43-209">**Als SRV-records niet worden ondersteund**, zijn de volgende functies van Office 365 niet beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="57e43-209">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="57e43-210">Integratie van de chatfunctie van Skype voor Bedrijven Online en aanwezigheidsgegevens met Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="57e43-210">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="57e43-211">Externe communicatie (federatie) met gebruikers van Skype voor Bedrijven Online in andere organisaties.</span><span class="sxs-lookup"><span data-stu-id="57e43-211">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="57e43-212">Openbare internetverbinding (Public Internet Connectivity (PIC)) met gebruikers van Skype voor Bedrijven Online die zijn aangemeld met een Microsoft-account (voorheen Windows Live ID).</span><span class="sxs-lookup"><span data-stu-id="57e43-212">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="57e43-213">**Als meerdere CNAME-records niet worden ondersteund,** moet u kiezen tussen de volgende functies voor Skype voor Bedrijven Online:</span><span class="sxs-lookup"><span data-stu-id="57e43-213">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="57e43-214">E-maildesktopclients en mobiele clients kunnen Automatisch opsporen gebruiken om automatisch de Exchange Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.</span><span class="sxs-lookup"><span data-stu-id="57e43-214">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="57e43-215">Desktopclients van Skype voor Bedrijven Online kunnen Automatisch opsporen gebruiken om automatisch de Skype voor Bedrijven Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.</span><span class="sxs-lookup"><span data-stu-id="57e43-215">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="57e43-216">Mobiele clients van Skype voor Bedrijven Online kunnen Automatisch opsporen gebruiken om automatisch de Skype voor Bedrijven Online-service te vinden, zodat gebruikers zich kunnen aanmelden zonder dat ze een servernaam hoeven in te voeren.</span><span class="sxs-lookup"><span data-stu-id="57e43-216">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
 <span data-ttu-id="57e43-p112">**Als SPF/TXT-records niet worden ondersteund**, kunnen andere personen mogelijk uw domein gebruiken om spam of andere schadelijke e-mail te verzenden. Door SPF-records worden de servers geïdentificeerd die zijn geautoriseerd om e-mail vanaf uw domein te verzenden.</span><span class="sxs-lookup"><span data-stu-id="57e43-p112">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email. SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="57e43-219">Hoe stel of wijzig ik het standaarddomein in Office 365?</span><span class="sxs-lookup"><span data-stu-id="57e43-219">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="57e43-220">U moet minimaal één aangepast domein aan Office 365 hebben toegevoegd voordat u een standaarddomein kunt kiezen.</span><span class="sxs-lookup"><span data-stu-id="57e43-220">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="57e43-221">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="57e43-221">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="57e43-222">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="57e43-222">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="57e43-223">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="57e43-223">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="57e43-224">Selecteer **op** de pagina Domeinen het domein dat u wilt instellen als standaardvoor nieuwe e-mailadressen.</span><span class="sxs-lookup"><span data-stu-id="57e43-224">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="57e43-225">Selecteer **Als standaard instellen**.</span><span class="sxs-lookup"><span data-stu-id="57e43-225">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="57e43-226">U kunt de naam van uw initiële  *.onmicrosoft.com*  -domein niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="57e43-226">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="57e43-227">U de naam van uw oorspronkelijke *.onmicrosoft.de* domein niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="57e43-227">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="57e43-228">U de naam van uw initiële *.partner.onmschina.cn* domein niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="57e43-228">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="57e43-229">Kan ik aangepaste subdomeinen of meerdere domeinen toevoegen aan Office 365?</span><span class="sxs-lookup"><span data-stu-id="57e43-229">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="57e43-230">Ja!</span><span class="sxs-lookup"><span data-stu-id="57e43-230">Yes!</span></span> <span data-ttu-id="57e43-231">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="57e43-231">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="57e43-232">Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein van Microsoft hebt gekocht, u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="57e43-232">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="57e43-233">Ja!</span><span class="sxs-lookup"><span data-stu-id="57e43-233">Yes!</span></span> <span data-ttu-id="57e43-234">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="57e43-234">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="57e43-235">Als u Microsoft uw DNS-instellingen laat beheren met NS-records of als u het domein van Microsoft hebt gekocht, u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="57e43-235">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="57e43-236">Ja!</span><span class="sxs-lookup"><span data-stu-id="57e43-236">Yes!</span></span> <span data-ttu-id="57e43-237">Als u subdomeinen wilt toevoegen, moet u uw eigen DNS-instellingen beheren op de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="57e43-237">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="57e43-238">Als u 21Vianet uw DNS-instellingen laat beheren met NS-records, u geen subdomeinen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="57e43-238">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="57e43-239">Doorgaans u maximaal 900 domeinen toevoegen aan uw Office 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="57e43-239">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="57e43-240">U kunt bijvoorbeeld de domeinen contoso.com en contosomarketing.com toevoegen, en vervolgens de subdomeinen www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com enzovoort.</span><span class="sxs-lookup"><span data-stu-id="57e43-240">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="57e43-241">Wanneer u een subdomein toevoegt, wordt dit automatisch geverifieerd op basis van het bovenliggende domein dat wordt geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="57e43-241">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="57e43-p116">Als u meerdere domeinen aan Office 365 toevoegt, kunt u alle services (zoals e-mail) in elk van die domeinen hosten.  *Wanneer u uw e-mailadres overzet naar Office 365 door de MX-record van uw domein bij te werken, komt alle e-mail die naar dat domein wordt verzonden, binnen in Office 365.*</span><span class="sxs-lookup"><span data-stu-id="57e43-p116">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.  *When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="57e43-244">Als u al een contoso.com-domein aan een Office 365-tenant hebt toegevoegd, u ook de subdomeinxyz.contoso.com toevoegen aan een andere Office 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="57e43-244">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="57e43-245">Bij het toevoegen van het subdomein wordt u gevraagd om een TXT-record toe te voegen aan de DNS-hostingprovider.</span><span class="sxs-lookup"><span data-stu-id="57e43-245">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="57e43-246">Waarom heb ik een domein met de naam onmicrosoft.com?</span><span class="sxs-lookup"><span data-stu-id="57e43-246">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="57e43-247">Office 365 maakt een domein voor u, zoals *contoso.onmicrosoft.com*wanneer u zich aanmeldt bij de service.</span><span class="sxs-lookup"><span data-stu-id="57e43-247">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="57e43-248">De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.com.*</span><span class="sxs-lookup"><span data-stu-id="57e43-248">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="57e43-249">**Als u uw e-mail wilt laten lijken op *alan\@contoso.com:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Office [365](add-domain.md) als u het al bezit.</span><span class="sxs-lookup"><span data-stu-id="57e43-249">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="57e43-p119">**U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.** Als u tijdens het registreren bijvoorbeeld in eerste instantie fourthcoffee.onmicrosoft.com hebt gekozen, kunt u deze naam niet meer wijzigen in fabrikam.onmicrosoft.com. Als u een ander onmicrosoft.com-domein wilt gebruiken, moet u een nieuw abonnement nemen op Office 365.</span><span class="sxs-lookup"><span data-stu-id="57e43-p119">**You can't rename the onmicrosoft domain after sign-up.** For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com. To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="57e43-253">**U de naam van de URL van uw teamsite niet wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="57e43-253">**You can't rename your team site URL.**</span></span> <span data-ttu-id="57e43-254">De URL van uw teamsite is gebaseerd op uw onmicrosoft.com domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="57e43-254">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="57e43-255">Helaas u de naam van de teamsite niet wijzigen vanwege de manier waarop de SharePoint Online-architectuur werkt.</span><span class="sxs-lookup"><span data-stu-id="57e43-255">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="57e43-p121">**U kunt uw onmicrosoft-domein niet verwijderen.** Dit domein wordt achter de schermen gebruikt voor uw abonnement. U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="57e43-p121">**You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="57e43-p122">U kunt het onmicrosoft.com-domein blijven gebruiken, ook nadat u uw domein hebt toegevoegd. Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.</span><span class="sxs-lookup"><span data-stu-id="57e43-p122">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="57e43-261">Waarom heb ik een domein 'onmicrosoft.de'?</span><span class="sxs-lookup"><span data-stu-id="57e43-261">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="57e43-262">Office 365 maakt een domein voor u, zoals *contoso.onmicrosoft.de*wanneer u zich aanmeldt bij de service.</span><span class="sxs-lookup"><span data-stu-id="57e43-262">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="57e43-263">De gebruikersnaam die u maakt wanneer u zich aanmeldt, bevat het domein, zoals *alan@contoso.onmicrosoft.de.*</span><span class="sxs-lookup"><span data-stu-id="57e43-263">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="57e43-264">**Als u uw e-mail wilt laten lijken *op alan@contoso.de:*** [koop het domein](../get-help-with-domains/buy-a-domain-name.md) of volg gewoon de stappen in Uw gebruikers en domein toevoegen aan Office [365](add-domain.md) als u het al bezit.</span><span class="sxs-lookup"><span data-stu-id="57e43-264">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="57e43-265">**U kunt de naam van het onmicrosoft-domein niet meer wijzigen nadat u zich hebt geregistreerd.**</span><span class="sxs-lookup"><span data-stu-id="57e43-265">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="57e43-266">Als het oorspronkelijke domein dat u hebt gekozen bijvoorbeeld fourthcoffee.onmicrosoft.de is, u het niet wijzigen om fabrikam.onmicrosoft.de te zijn.</span><span class="sxs-lookup"><span data-stu-id="57e43-266">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="57e43-267">Als u een ander onmicrosoft.de-domein wilt gebruiken, moet u een nieuw abonnement starten met Office 365.</span><span class="sxs-lookup"><span data-stu-id="57e43-267">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="57e43-268">**U de naam van de URL van uw teamsite niet wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="57e43-268">**You can't rename your team site URL.**</span></span> <span data-ttu-id="57e43-269">De URL van uw teamsite is gebaseerd op uw onmicrosoft.de domeinnaam. Helaas u de naam van de teamsite niet wijzigen vanwege de manier waarop de SharePoint Online-architectuur werkt.</span><span class="sxs-lookup"><span data-stu-id="57e43-269">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="57e43-p126">**U kunt uw onmicrosoft-domein niet verwijderen.** Dit domein wordt achter de schermen gebruikt voor uw abonnement. U hoeft het domein echter zelf niet te gebruiken nadat u een aangepast domein hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="57e43-p126">**You can't remove your onmicrosoft domain.** Office 365 needs to keep it around because it's used behind the scenes for your subscription. But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="57e43-273">U het oorspronkelijke onmicrosoft.de domein blijven gebruiken, zelfs nadat u uw domein hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="57e43-273">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="57e43-274">Dit domein werkt nog steeds voor e-mail en andere services, dus de keuze is aan u.</span><span class="sxs-lookup"><span data-stu-id="57e43-274">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="57e43-275">Hoe kan ik mijn non-profit- of onderwijsstatus verifiëren?</span><span class="sxs-lookup"><span data-stu-id="57e43-275">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="57e43-276">Selecteer **Instellen** in het [beheercentrum](https://docs.microsoft.com/microsoft-365/admin/admin-home) om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="57e43-276">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="57e43-277">(Zorg ervoor dat u zich eerst aanmeldt bij Office 365.)</span><span class="sxs-lookup"><span data-stu-id="57e43-277">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="57e43-278">Als u de beheerder voor uw school wilt worden, selecteert u de optie **Beheerder worden** in Office 365.</span><span class="sxs-lookup"><span data-stu-id="57e43-278">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="57e43-279">U wordt gevraagd een TXT DNS-record toe te voegen op de DNS-hostwebsite voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="57e43-279">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="57e43-280">Waarom?</span><span class="sxs-lookup"><span data-stu-id="57e43-280">Why?</span></span> <span data-ttu-id="57e43-281">Want door u aan te melden bij de DNS-host en een record voor uw domein toe te voegen, bewijst u aan Office 365 dat u eigenaar bent van de domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="57e43-281">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="57e43-282">Nadat u de record hebt toegevoegd, gaat u terug naar de Office 365-portal en bevestigt u dat u deze hebt toegevoegd, zodat Office 365 deze kan controleren.</span><span class="sxs-lookup"><span data-stu-id="57e43-282">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="57e43-283">Heb je een non-profitorganisatie en wil je Office 365?</span><span class="sxs-lookup"><span data-stu-id="57e43-283">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="57e43-284">[Zorg ervoor dat uw organisatie in aanmerking komt](https://www.microsoft.com/en-us/nonprofits/eligibility) en meld u dan aan voor de service.</span><span class="sxs-lookup"><span data-stu-id="57e43-284">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="57e43-285">Wilt u meer weten over het worden van de beheerder voor uw school?</span><span class="sxs-lookup"><span data-stu-id="57e43-285">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="57e43-286">[Meer informatie over het](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="57e43-286">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="57e43-287">Kan ik Office 365 besturen met slechts een paar e-mailadressen uit mijn aangepaste domein?</span><span class="sxs-lookup"><span data-stu-id="57e43-287">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="57e43-288">Dat kan, maar er zijn beperkingen:</span><span class="sxs-lookup"><span data-stu-id="57e43-288">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="57e43-289">Uw huidige e-mailprovider moet e-mail doorsturen.</span><span class="sxs-lookup"><span data-stu-id="57e43-289">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="57e43-290">U moet uw DNS-records met Office 365 beheren bij uw DNS-hostingprovider, in plaats van dat Office 365 deze records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="57e43-290">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="57e43-291">Zie Uw domein toevoegen aan Office 365 wanneer u uw eigen DNS-records wilt beheren voor meer informatie over dit:</span><span class="sxs-lookup"><span data-stu-id="57e43-291">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="57e43-292">Sommige Office 365-functies zijn niet beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="57e43-292">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="57e43-293">Gebruikers kunnen geen gratis/drukke informatie zien voor de gebruikers die zich op de andere e-mailprovider bevinden.</span><span class="sxs-lookup"><span data-stu-id="57e43-293">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="57e43-294">Beheerders kunnen de accounts van iedereen niet vanaf één plek beheren.</span><span class="sxs-lookup"><span data-stu-id="57e43-294">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="57e43-295">Gebruikers kunnen office 365-spamfiltering mogelijk niet gebruiken</span><span class="sxs-lookup"><span data-stu-id="57e43-295">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="57e43-296">Een Office 365-pilot instellen</span><span class="sxs-lookup"><span data-stu-id="57e43-296">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="57e43-297">Aanmelden bij het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="57e43-297">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="57e43-298">Meld u aan bij Office 365 met uw werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="57e43-298">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="57e43-299">Ga naar \> **Instellingendomeinen**. **Settings**</span><span class="sxs-lookup"><span data-stu-id="57e43-299">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="57e43-300">Controleren of u eigenaar bent van het domein dat u wilt gebruiken</span><span class="sxs-lookup"><span data-stu-id="57e43-300">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="57e43-301">Selecteer **op** de pagina Domeinen de optie **Domein toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="57e43-301">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="57e43-302">Typ in het deelvenster het domein in dit voorbeeld cohowinery.com en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="57e43-302">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="57e43-303">Volg op de pagina **Domein verifiëren** de stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="57e43-303">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="57e43-304">Selecteer in de vervolgkeuzelijst uw DNS-hostingprovider en volg de instructies om aan te geven dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="57e43-304">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="57e43-305">Selecteer **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="57e43-305">Select **Verify**.</span></span> <span data-ttu-id="57e43-306">Het duurt enkele minuten tot 72 uur voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="57e43-306">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="57e43-307">Wanneer de verificatie is geslaagd, wordt u gevraagd uw DNS-records te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="57e43-307">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="57e43-308">Het domein markeren als gedeeld in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="57e43-308">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="57e43-309">Ga naar het **Exchange-beheercentrum** (EAC).</span><span class="sxs-lookup"><span data-stu-id="57e43-309">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="57e43-310">Selecteer **geaccepteerde domeinen**in de sectie **E-mailstroom** .</span><span class="sxs-lookup"><span data-stu-id="57e43-310">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="57e43-311">Dubbelklik op het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="57e43-311">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="57e43-312">Selecteer **Intern relais**in het venster dat wordt geopend .</span><span class="sxs-lookup"><span data-stu-id="57e43-312">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="57e43-313">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="57e43-313">Select **Save**.</span></span> <span data-ttu-id="57e43-314">Deze instelling kan enkele minuten nodig hebben om van kracht te worden.</span><span class="sxs-lookup"><span data-stu-id="57e43-314">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="57e43-315">Deblokkering van de bestaande e-mailserver optioneel deblokkeren</span><span class="sxs-lookup"><span data-stu-id="57e43-315">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="57e43-316">Office 365 gebruikt Exchange Online Protection (EOP) voor spambescherming.</span><span class="sxs-lookup"><span data-stu-id="57e43-316">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="57e43-317">Als EOP detecteert een groot volume van spam wordt doorgestuurd door uw huidige mail server, kan het blokkeren, die zou voorkomen dat doorsturen werkt.</span><span class="sxs-lookup"><span data-stu-id="57e43-317">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="57e43-318">Als u zeker bent van de spambeveiliging die uw andere e-mailprovider gebruikt, u hun server op de witte lijst plaatsen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="57e43-318">If you are confident with the spam protection your other email provider uses, you can whitelist their server in Office 365.</span></span> <span data-ttu-id="57e43-319">Hierdoor kunnen echter ook spam die via uw oorspronkelijke server binnenkomen, door naar de Office 365-postvakken komen en u niet beoordelen hoe goed Office 365 spam voorkomt.</span><span class="sxs-lookup"><span data-stu-id="57e43-319">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="57e43-320">Ga naar Exchange admin center (EAC).</span><span class="sxs-lookup"><span data-stu-id="57e43-320">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="57e43-321">Selecteer **in**EAC Beveiliging en selecteer **vervolgens het filter Verbinding**.</span><span class="sxs-lookup"><span data-stu-id="57e43-321">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="57e43-322">Selecteer **+** in de **lijst IP-toestaan**het IP-adres van de e-mailserver dat u ophalen van uw huidige e-mailprovider en voeg deze toe.</span><span class="sxs-lookup"><span data-stu-id="57e43-322">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="57e43-323">Gebruikersaccounts maken en het primaire (antwoordadres) instellen</span><span class="sxs-lookup"><span data-stu-id="57e43-323">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="57e43-324">Ga naar het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="57e43-324">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="57e43-325">Selecteer op de linkernavigatiebalk de optie **Actieve gebruikers** **gebruikers** \> .</span><span class="sxs-lookup"><span data-stu-id="57e43-325">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="57e43-326">Maak de gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="57e43-326">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="57e43-327">Selecteer voor elk account **+ (Nieuw)** en vul de vereiste informatie in.</span><span class="sxs-lookup"><span data-stu-id="57e43-327">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="57e43-328">Om de e-mail van de gebruiker hetzelfde te houden als nu, moet het veld **Gebruikersnaam** exact hetzelfde zijn als het bestaande e-mailadres van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="57e43-328">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="57e43-329">Selecteer naast Gebruikersnaam uw aangepaste domeinnaam in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="57e43-329">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="57e43-330">Selecteer **Sluiten maken** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="57e43-330">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="57e43-331">DNS-records bijwerken bij uw DNS-hostingprovider</span><span class="sxs-lookup"><span data-stu-id="57e43-331">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="57e43-332">Meld u aan bij de website van uw DNS-hostingprovider en volg de [DNS-records maken bij elke DNS-hostingprovider voor Office 365-stappen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="57e43-332">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="57e43-333">**Maak de volgende uitzonderingen:**</span><span class="sxs-lookup"><span data-stu-id="57e43-333">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="57e43-334">Maak geen nieuwe MX-record of wijzig uw bestaande MX-record niet.</span><span class="sxs-lookup"><span data-stu-id="57e43-334">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="57e43-335">Als u al een SPF-record (Sender Policy Framework) hebt voor uw vorige e-mailprovider, voegt u in plaats van een nieuwe SPF-record (TXT) voor Exchange Online te maken, voeg u 'include:spf.protection.outlook.com' toe aan de huidige TXT-record.</span><span class="sxs-lookup"><span data-stu-id="57e43-335">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="57e43-336">Bijvoorbeeld, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="57e43-336">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="57e43-337">Als u nog geen SPF-record hebt, wijzigt u de record die wordt aanbevolen door Office 365 om het domein voor uw huidige e-mailprovider op te nemen, plus spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="57e43-337">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="57e43-338">Hiermee worden uitgaande berichten van beide e-mailsystemen geautoriseerd.</span><span class="sxs-lookup"><span data-stu-id="57e43-338">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="57e43-339">E-mail doorsturen instellen bij uw huidige provider</span><span class="sxs-lookup"><span data-stu-id="57e43-339">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="57e43-340">Stel bij uw huidige e-mailprovider het doorsturen voor uw gebruikers-e-mailaccounts in naar uw onmicrosoft.com-domein:</span><span class="sxs-lookup"><span data-stu-id="57e43-340">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="57e43-341">Het postvak van gebruiker A moet worden doorgestuurd naar usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="57e43-341">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="57e43-342">Het postvak van gebruiker B moet doorsturen naar userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="57e43-342">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="57e43-343">Wanneer u deze stap voltooit:</span><span class="sxs-lookup"><span data-stu-id="57e43-343">When you complete this step:</span></span>
        
    5. <span data-ttu-id="57e43-344">Alle e-mail die naar usera@yourcompany.com en userb@yourcompany.com wordt verzonden, is beschikbaar in Office 365.</span><span class="sxs-lookup"><span data-stu-id="57e43-344">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="57e43-345">Opmerkingen:</span><span class="sxs-lookup"><span data-stu-id="57e43-345">Notes:</span></span>
        
        - <span data-ttu-id="57e43-346">Neem contact op met uw huidige e-mailprovider voor de exacte stappen voor het instellen van doorstuur.</span><span class="sxs-lookup"><span data-stu-id="57e43-346">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="57e43-347">U hoeft geen kopie van berichten bij de huidige e-mailprovider te bewaren.</span><span class="sxs-lookup"><span data-stu-id="57e43-347">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="57e43-348">De meeste providers sturen e-mail door en laten het antwoordadres van de afzender intact, zodat de antwoorden naar de oorspronkelijke afzender gaan.</span><span class="sxs-lookup"><span data-stu-id="57e43-348">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="57e43-349">E-mailstroom testen</span><span class="sxs-lookup"><span data-stu-id="57e43-349">Test mail flow</span></span>
    
    1. <span data-ttu-id="57e43-350">Meld u aan bij Outlook Web App met de referenties van gebruiker A.</span><span class="sxs-lookup"><span data-stu-id="57e43-350">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="57e43-351">Voer de volgende tests uit:</span><span class="sxs-lookup"><span data-stu-id="57e43-351">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="57e43-352">Lokale Microsoft-e-mail testen.</span><span class="sxs-lookup"><span data-stu-id="57e43-352">Test local Microsoft email.</span></span> <span data-ttu-id="57e43-353">Stuur bijvoorbeeld een e-mail naar gebruiker B. Deze e-mail moet onmiddellijk worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="57e43-353">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="57e43-354">In dit scenario wordt het bericht niet doorgestuurd naar het postvak van gebruiker B op uw oorspronkelijke server, omdat het postvak in Office 365 als lokaal wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="57e43-354">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="57e43-355">Test e-mail naar iemand die zich op het andere e-mailsysteem bevindt.</span><span class="sxs-lookup"><span data-stu-id="57e43-355">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="57e43-356">Stuur bijvoorbeeld een e-mail naar gebruiker C. Deze e-mail moet worden bezorgd in het postvak van gebruiker C op uw oorspronkelijke e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="57e43-356">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="57e43-357">Controleer vanaf een extern account of van het e-mailaccount van een werknemer op het andere e-mailsysteem of het doorsturen correct is ingesteld op het andere e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="57e43-357">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="57e43-358">Stuur bijvoorbeeld vanuit het oorspronkelijke serveraccount van gebruiker C of een Hotmail-account gebruiker A een e-mail en controleer of deze in het Office 365-postvak van gebruiker A wordt aangeleverd.</span><span class="sxs-lookup"><span data-stu-id="57e43-358">For example, from User C's original server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="57e43-359">Postvakinhoud verplaatsen</span><span class="sxs-lookup"><span data-stu-id="57e43-359">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="57e43-360">Aangezien er slechts twee gebruikers te verplaatsen, en aangezien gebruiker A en gebruiker B zijn beide met behulp van Outlook al, de e-mail kan worden verplaatst door het openen van de oude . PST-bestand in het nieuwe Outlook-profiel en het kopiëren van de berichten, agenda-items, contactpersonen, enz.</span><span class="sxs-lookup"><span data-stu-id="57e43-360">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="57e43-361">Eenmaal georganiseerd op de juiste locaties in het Office 365-postvak, kunnen de items allemaal worden geopend vanaf elk apparaat, overal.</span><span class="sxs-lookup"><span data-stu-id="57e43-361">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="57e43-362">Wanneer er meer postvakken bij betrokken zijn of als de werknemers Outlook nog niet gebruiken, u de migratiehulpprogramma's gebruiken die beschikbaar zijn in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="57e43-362">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="57e43-363">Ga om aan de slag naar het Exchange-beheercentrum en volg de aanwijzingen in E-mail migreren van een IMAP-server naar Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="57e43-363">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
