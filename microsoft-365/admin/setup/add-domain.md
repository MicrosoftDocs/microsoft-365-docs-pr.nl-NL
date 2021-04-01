---
title: Een domein toevoegen aan Microsoft 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Voeg uw domein toe aan Microsoft 365 in het Microsoft 365-beheercentrum door een DNS-record toe te voegen aan uw DNS-host. Met de installatiewizard loopt u door het proces.
ms.openlocfilehash: 747de5f61dc9fce53f82f52b65f701572a56f8d4
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470879"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="51f00-104">Een domein toevoegen aan Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51f00-104">Add a domain to Microsoft 365</span></span>

 <span data-ttu-id="51f00-105">**[Raadpleeg de veelgestelde vragen over domeinen](domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="51f00-105">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="51f00-106">*Als u domeinen wilt toevoegen, wijzigen of verwijderen, **moet** u een **globale beheerder** van een bedrijfs- of [ondernemingsplan zijn.](https://products.office.com/business/office) Deze wijzigingen zijn van invloed op de hele tenant, *aangepaste beheerders* of *gewone* gebruikers kunnen deze wijzigingen niet aanbrengen.*</span><span class="sxs-lookup"><span data-stu-id="51f00-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="51f00-107">Volg deze stappen om een domein toe te voegen, in te stellen of te blijven instellen.</span><span class="sxs-lookup"><span data-stu-id="51f00-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="51f00-108">Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="51f00-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="51f00-109">Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="51f00-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="51f00-110">Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="51f00-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="51f00-111">Ga naar de **pagina**  >  **Instellingendomeinen.**</span><span class="sxs-lookup"><span data-stu-id="51f00-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="51f00-112">Selecteer **Domein toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="51f00-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="51f00-113">Voer de naam in van het domein dat u wilt toevoegen en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="51f00-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="51f00-114">Kies hoe u wilt controleren of u de eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="51f00-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="51f00-115">Als uw domeinregistrar [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365)gebruikt, worden uw [records](../get-help-with-domains/domain-connect.md) automatisch ingesteld door u aan te melden bij uw registrar en de verbinding met Microsoft 365 te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="51f00-115">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="51f00-116">U wordt teruggegeven aan het beheercentrum en Microsoft controleert vervolgens automatisch uw domein.</span><span class="sxs-lookup"><span data-stu-id="51f00-116">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="51f00-117">U kunt een TXT-record gebruiken om uw domein te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="51f00-117">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="51f00-118">Selecteer dit en selecteer **Volgende om** instructies te zien voor het toevoegen van deze DNS-record aan de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="51f00-118">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="51f00-119">Dit kan tot 30 minuten duren voordat u de record hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="51f00-119">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="51f00-120">U kunt een tekstbestand toevoegen aan de website van uw domein.</span><span class="sxs-lookup"><span data-stu-id="51f00-120">You can add a text file to your domain's website.</span></span> <span data-ttu-id="51f00-121">Selecteer en download het TXT-bestand in de installatiewizard en upload het bestand vervolgens naar de map op het hoogste niveau van uw website.</span><span class="sxs-lookup"><span data-stu-id="51f00-121">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="51f00-122">Het pad naar het bestand moet er ongeveer hetzelfde uitzien als: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="51f00-122">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="51f00-123">We bevestigen dat u de eigenaar bent van het domein door het bestand op uw website te zoeken.</span><span class="sxs-lookup"><span data-stu-id="51f00-123">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="51f00-124">Kies hoe u de DNS-wijzigingen wilt aanbrengen die microsoft nodig heeft om uw domein te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="51f00-124">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="51f00-125">Kies **Add the DNS records for me** if your registrar supports Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft will set up your [records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51f00-125">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="51f00-126">Kies **Ik voeg de DNS-records** zelf toe als u alleen specifieke Microsoft 365-services wilt toevoegen aan uw domein of als u dit voor nu wilt overslaan en dit later wilt doen.</span><span class="sxs-lookup"><span data-stu-id="51f00-126">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="51f00-127">**Kies deze optie als u precies weet wat u doet.**</span><span class="sxs-lookup"><span data-stu-id="51f00-127">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="51f00-128">Als u zelf *DNS-records*  wilt toevoegen, selecteert u **Volgende** en ziet u een pagina met alle records die u moet toevoegen aan de website van uw registrars om uw domein in te stellen.</span><span class="sxs-lookup"><span data-stu-id="51f00-128">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="51f00-129">Als uw domeinregistrar niet wordt herkend door de portal, kunt u [deze algemene instructies volgen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="51f00-129">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="51f00-130">Bekijk onze lijst met [hostspecifieke instructies](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) om uw host te vinden en volg de stappen om alle records toe te voegen die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="51f00-130">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="51f00-131">Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="51f00-131">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="51f00-132">Als u later wilt wachten, deselecteert u alle services en klikt u  op Doorgaan **of** kiest u in de vorige domeinverbindingsstap Meer opties en selecteert u Dit voor **nu overslaan.**</span><span class="sxs-lookup"><span data-stu-id="51f00-132">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="51f00-133">Selecteer **Voltooien-** u bent klaar!</span><span class="sxs-lookup"><span data-stu-id="51f00-133">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="51f00-134">Aangepaste DNS-records toevoegen of bewerken</span><span class="sxs-lookup"><span data-stu-id="51f00-134">Add or edit custom DNS records</span></span>

<span data-ttu-id="51f00-135">Volg de onderstaande stappen om een aangepaste record toe te voegen voor een website of service van derden.</span><span class="sxs-lookup"><span data-stu-id="51f00-135">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="51f00-136">Meld u aan bij het Microsoft-beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="51f00-136">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="51f00-137">Ga naar de **pagina**   >  **Instellingendomeinen.**</span><span class="sxs-lookup"><span data-stu-id="51f00-137">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="51f00-138">Selecteer een domein op de pagina **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="51f00-138">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="51f00-139">Selecteer **onder DNS-instellingen** aangepaste **records**; selecteer vervolgens **Nieuwe aangepaste record.**</span><span class="sxs-lookup"><span data-stu-id="51f00-139">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="51f00-140">Selecteer het type DNS-record dat u wilt toevoegen en typ de gegevens voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="51f00-140">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="51f00-141">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="51f00-141">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="51f00-142">Registrars met Domain Connect</span><span class="sxs-lookup"><span data-stu-id="51f00-142">Registrars with Domain Connect</span></span>

<span data-ttu-id="51f00-143">[Met domain](https://www.domainconnect.org/) connect-registrars kunt u uw domein toevoegen aan Microsoft 365 in een proces in drie stappen dat minuten duurt.</span><span class="sxs-lookup"><span data-stu-id="51f00-143">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="51f00-144">In de wizard bevestigen we dat u de eigenaar bent van het domein en vervolgens automatisch de records van uw domein, zodat e-mail naar Microsoft 365 en andere Microsoft 365-services, zoals Teams, met uw domein werkt.</span><span class="sxs-lookup"><span data-stu-id="51f00-144">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="51f00-145">Start de wizard pas nadat u hebt gecontroleerd of pop-ups zijn toegestaan in uw browser.</span><span class="sxs-lookup"><span data-stu-id="51f00-145">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="51f00-146">Domain Connect-registrars die integreren met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51f00-146">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="51f00-147">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="51f00-147">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="51f00-148">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="51f00-148">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="51f00-149">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="51f00-149">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="51f00-150">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="51f00-150">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="51f00-151">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="51f00-151">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="51f00-152">Plesk</span><span class="sxs-lookup"><span data-stu-id="51f00-152">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="51f00-153">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="51f00-153">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="51f00-154">SecureServer of WildWestDomains (GoDaddy-resellers met SecureServer DNS-hosting)</span><span class="sxs-lookup"><span data-stu-id="51f00-154">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="51f00-155">Voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="51f00-155">Examples:</span></span>
        - [<span data-ttu-id="51f00-156">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="51f00-156">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="51f00-157">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="51f00-157">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="51f00-158">Wat gebeurt er met mijn e-mail en website?</span><span class="sxs-lookup"><span data-stu-id="51f00-158">What happens to my email and website?</span></span>

<span data-ttu-id="51f00-159">Nadat u klaar bent met de installatie, wordt de MX-record voor uw domein bijgewerkt om te wijzen naar Microsoft 365 en wordt alle e-mail voor uw domein naar Microsoft 365 verzonden.</span><span class="sxs-lookup"><span data-stu-id="51f00-159">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="51f00-160">Zorg ervoor dat u gebruikers hebt toegevoegd en postvakken hebt ingesteld in Microsoft 365 voor iedereen die e-mail op uw domein ontvangt.</span><span class="sxs-lookup"><span data-stu-id="51f00-160">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="51f00-161">Als uw bedrijf een website heeft, blijft die gewoon werken.</span><span class="sxs-lookup"><span data-stu-id="51f00-161">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="51f00-162">De installatiestappen voor Domain Connect hebben geen invloed op uw website.</span><span class="sxs-lookup"><span data-stu-id="51f00-162">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="51f00-163">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="51f00-163">Related articles</span></span>

[<span data-ttu-id="51f00-164">Veelgestelde vragen over domeinen</span><span class="sxs-lookup"><span data-stu-id="51f00-164">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="51f00-165">Wat is een domein?</span><span class="sxs-lookup"><span data-stu-id="51f00-165">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="51f00-166">Een domeinnaam kopen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51f00-166">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="51f00-167">Uw domein instellen (host-specifieke instructies)</span><span class="sxs-lookup"><span data-stu-id="51f00-167">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)