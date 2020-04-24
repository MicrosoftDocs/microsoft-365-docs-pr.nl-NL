---
title: Een domein toevoegen aan Office 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Voeg uw domein toe aan Office 365 in het Microsoft 365-beheercentrum door een DNS-record toe te voegen aan uw DNS-host. De setup wizard begeleidt u door het proces.
ms.openlocfilehash: a77526efc526073e17b535612213202ad22d5657
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/24/2020
ms.locfileid: "43800021"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="0a7b4-104">Een domein toevoegen aan Office 365</span><span class="sxs-lookup"><span data-stu-id="0a7b4-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="0a7b4-105">**[Raadpleeg de veelgestelde vragen over domeinen](domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="0a7b4-106">*Als u domeinen wilt toevoegen, wijzigen of **verwijderen, moet** u een **globale beheerder** van een [bedrijfs- of ondernemingsplan zijn.](https://products.office.com/business/office) Deze wijzigingen zijn van invloed op de hele tenant, *aangepaste beheerders* of *gewone gebruikers* kunnen deze wijzigingen niet aanbrengen.*</span><span class="sxs-lookup"><span data-stu-id="0a7b4-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="0a7b4-107">Volg deze stappen om een domein toe te voegen, in te stellen of door te gaan met het instellen van een domein.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0a7b4-108">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="0a7b4-109">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0a7b4-110">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="0a7b4-111">Ga naar de pagina > **Setup-domeinen.** **Setup**</span><span class="sxs-lookup"><span data-stu-id="0a7b4-111">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="0a7b4-112">Selecteer **Domein toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="0a7b4-113">Voer de naam in van het domein dat u wilt toevoegen en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="0a7b4-114">Kies hoe u wilt controleren of u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="0a7b4-115">Als uw domein is geregistreerd&amp;bij GoDaddy of 11, selecteert u **Aanmelden** > **volgende** en stelt Microsoft uw records[automatisch in.](../get-help-with-domains/domain-connect.md)</span><span class="sxs-lookup"><span data-stu-id="0a7b4-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft[will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="0a7b4-116">U kunt een e-mailbericht met een verificatiecode laten verzenden naar de geregistreerde contactpersoon voor het domein.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="0a7b4-117">Als u de e-mail niet herkent of hebt, u de derde optie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="0a7b4-118">U kunt een TXT-record gebruiken om uw domein te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="0a7b4-119">Selecteer dit en selecteer **Volgende** om instructies te bekijken voor het toevoegen van deze DNS-record aan de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="0a7b4-120">Dit kan tot 30 minuten duren voordat u de record hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="0a7b4-121">Kies hoe u de DNS-wijzigingen wilt aanbrengen die nodig zijn om Office uw domein te laten gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="0a7b4-122">Kies **De DNS-records voor mij toevoegen** als u wilt dat Office uw DNS automatisch configureert.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="0a7b4-123">Kies **Ik voeg de DNS-records zelf toe** als u alleen specifieke Office 365-services aan uw domein wilt koppelen of als u dit nu wilt overslaan en dit later wilt doen.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="0a7b4-124">**Kies deze optie als u precies weet wat u doet.**</span><span class="sxs-lookup"><span data-stu-id="0a7b4-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="0a7b4-125">Als u ervoor kiest om *zelf DNS-records toe* te voegen, selecteert u **Volgende** en ziet u een pagina met alle records die u moet toevoegen aan de website van uw registrars om uw domein in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="0a7b4-126">Als uw domeinregistrar niet wordt herkend door de portal, kunt u [deze algemene instructies volgen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="0a7b4-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="0a7b4-127">Bekijk onze lijst met [hostspecifieke instructies](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) om uw host te vinden en volg de stappen om alle records toe te voegen die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="0a7b4-128">Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="0a7b4-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="0a7b4-129">Als u wilt wachten tot later, schuift u naar de onderkant en selecteert **u Deze stap overslaan**.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="0a7b4-130">Selecteer **Voltooien** - je bent klaar!</span><span class="sxs-lookup"><span data-stu-id="0a7b4-130">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="0a7b4-131">Aangepaste DNS-records toevoegen of bewerken</span><span class="sxs-lookup"><span data-stu-id="0a7b4-131">Add or edit custom DNS records</span></span>

<span data-ttu-id="0a7b4-132">Volg de onderstaande stappen om een aangepaste record toe te voegen voor een website of service van derden.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-132">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="0a7b4-133">Meld u aan bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>het Microsoft-beheercentrum op .</span><span class="sxs-lookup"><span data-stu-id="0a7b4-133">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0a7b4-134">Ga naar de pagina  > **Instellingendomeinen.** **Settings**</span><span class="sxs-lookup"><span data-stu-id="0a7b4-134">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="0a7b4-135">Selecteer een domein op de pagina **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-135">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="0a7b4-136">Selecteer onder **DNS-instellingen** **aangepaste records**; selecteer vervolgens **Nieuwe aangepaste record**.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-136">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="0a7b4-137">Selecteer het type DNS-record dat u wilt toevoegen en typ de gegevens voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-137">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="0a7b4-138">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-138">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="0a7b4-139">Registrars met Domain Connect</span><span class="sxs-lookup"><span data-stu-id="0a7b4-139">Registrars with Domain Connect</span></span>

<span data-ttu-id="0a7b4-140">[Met](https://www.domainconnect.org/) registrars met Domain Connect u uw domein toevoegen aan Microsoft 365 in een proces in drie stappen dat minuten duurt.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-140">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="0a7b4-141">In de wizard bevestigen we alleen dat u eigenaar bent van het domein en stellen we de records van uw domein automatisch in, zodat e-mail naar Microsoft 365 en andere Microsoft 365-services, zoals Teams, werkt met uw domein.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-141">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a7b4-142">Start de wizard pas nadat u hebt gecontroleerd of pop-ups zijn toegestaan in uw browser.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-142">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="0a7b4-143">Domain Connect-registrars die integreren met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a7b4-143">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="0a7b4-144">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="0a7b4-144">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="0a7b4-145">123Reg</span><span class="sxs-lookup"><span data-stu-id="0a7b4-145">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="0a7b4-146">Godaddy</span><span class="sxs-lookup"><span data-stu-id="0a7b4-146">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="0a7b4-147">Wordpress</span><span class="sxs-lookup"><span data-stu-id="0a7b4-147">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="0a7b4-148">Plesk</span><span class="sxs-lookup"><span data-stu-id="0a7b4-148">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="0a7b4-149">MediaTempel (MediaTempel)</span><span class="sxs-lookup"><span data-stu-id="0a7b4-149">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="0a7b4-150">SecureServer of WildWestDomains (GoDaddy resellers met SecureServer DNS-hosting)</span><span class="sxs-lookup"><span data-stu-id="0a7b4-150">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="0a7b4-151">MadDog Domeinen</span><span class="sxs-lookup"><span data-stu-id="0a7b4-151">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="0a7b4-152">CheapNames CheapNames</span><span class="sxs-lookup"><span data-stu-id="0a7b4-152">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="0a7b4-153">Wat gebeurt er met mijn e-mail en website?</span><span class="sxs-lookup"><span data-stu-id="0a7b4-153">What happens to my email and website?</span></span>

<span data-ttu-id="0a7b4-154">Nadat u klaar bent met de installatie, wordt de MX-record voor uw domein bijgewerkt om naar Microsoft 365 te wijzen en alle e-mail voor uw domein wordt naar Microsoft 365 gaan komen.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-154">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="0a7b4-155">Zorg dat u in Office 365 gebruikers hebt toegevoegd en postvakken hebt geconfigureerd voor iedereen die een e-mailaccount in uw domein heeft.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-155">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="0a7b4-156">Als uw bedrijf een website heeft, blijft die gewoon werken.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-156">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="0a7b4-157">De installatiestappen Domain Connect hebben geen invloed op uw website.</span><span class="sxs-lookup"><span data-stu-id="0a7b4-157">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0a7b4-158">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="0a7b4-158">Related articles</span></span>

[<span data-ttu-id="0a7b4-159">Veelgestelde vragen over domeinen</span><span class="sxs-lookup"><span data-stu-id="0a7b4-159">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="0a7b4-160">Wat is een domein?</span><span class="sxs-lookup"><span data-stu-id="0a7b4-160">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="0a7b4-161">Een domeinnaam kopen in Office 365</span><span class="sxs-lookup"><span data-stu-id="0a7b4-161">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="0a7b4-162">Uw domein instellen (host-specifieke instructies)</span><span class="sxs-lookup"><span data-stu-id="0a7b4-162">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="0a7b4-163">Hulp krijgen bij domeinen</span><span class="sxs-lookup"><span data-stu-id="0a7b4-163">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
