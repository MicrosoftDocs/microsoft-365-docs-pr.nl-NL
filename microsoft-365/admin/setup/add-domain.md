---
title: Een domein toevoegen aan Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.openlocfilehash: 86ca8f986624ad37f780961cb58923ea0a1b2308
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857377"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="3145e-104">Een domein toevoegen aan Office 365</span><span class="sxs-lookup"><span data-stu-id="3145e-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="3145e-105">**[Raadpleeg de veelgestelde vragen over domeinen](domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="3145e-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="3145e-106">*Als u domeinen wilt toevoegen, wijzigen of **verwijderen, moet** u een **globale beheerder** van een [bedrijfs- of ondernemingsplan zijn.](https://products.office.com/business/office) Deze wijzigingen zijn van invloed op de hele tenant, *aangepaste beheerders* of *gewone gebruikers* kunnen deze wijzigingen niet aanbrengen.*</span><span class="sxs-lookup"><span data-stu-id="3145e-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="3145e-107">Volg deze stappen om een domein toe te voegen, in te stellen of door te gaan met het instellen van een domein.</span><span class="sxs-lookup"><span data-stu-id="3145e-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3145e-108">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="3145e-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="3145e-109">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="3145e-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3145e-110">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="3145e-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="3145e-111">Ga naar de pagina > **Instellingendomeinen.** **Settings**</span><span class="sxs-lookup"><span data-stu-id="3145e-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="3145e-112">Selecteer **Domein toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3145e-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="3145e-113">Voer de naam in van het domein dat u wilt toevoegen en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3145e-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="3145e-114">Kies hoe u wilt controleren of u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="3145e-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="3145e-115">Als uw domein is geregistreerd&amp;bij GoDaddy of 11, selecteert u **Aanmelden volgende** > **Next** en stelt Office 365 uw records [automatisch in.](../get-help-with-domains/domain-connect.md)</span><span class="sxs-lookup"><span data-stu-id="3145e-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Office 365 [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="3145e-116">U kunt een e-mailbericht met een verificatiecode laten verzenden naar de geregistreerde contactpersoon voor het domein.</span><span class="sxs-lookup"><span data-stu-id="3145e-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="3145e-117">Als u de e-mail niet herkent of hebt, u de derde optie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3145e-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="3145e-118">U kunt een TXT-record gebruiken om uw domein te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="3145e-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="3145e-119">Selecteer dit en selecteer **Volgende** om instructies te bekijken voor het toevoegen van deze DNS-record aan de website van uw registrar.</span><span class="sxs-lookup"><span data-stu-id="3145e-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="3145e-120">Dit kan tot 30 minuten duren voordat u de record hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="3145e-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="3145e-121">Kies hoe u de DNS-wijzigingen wilt aanbrengen die nodig zijn om Office uw domein te laten gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3145e-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="3145e-122">Kies **De DNS-records voor mij toevoegen** als u wilt dat Office uw DNS automatisch configureert.</span><span class="sxs-lookup"><span data-stu-id="3145e-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="3145e-123">Kies **Ik voeg de DNS-records zelf toe** als u alleen specifieke Office 365-services aan uw domein wilt koppelen of als u dit nu wilt overslaan en dit later wilt doen.</span><span class="sxs-lookup"><span data-stu-id="3145e-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="3145e-124">**Kies deze optie als u precies weet wat u doet.**</span><span class="sxs-lookup"><span data-stu-id="3145e-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="3145e-125">Als u ervoor kiest om *zelf DNS-records toe* te voegen, selecteert u **Volgende** en ziet u een pagina met alle records die u moet toevoegen aan de website van uw registrars om uw domein in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3145e-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="3145e-126">Als uw domeinregistrar niet wordt herkend door de portal, kunt u [deze algemene instructies volgen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="3145e-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="3145e-127">Bekijk onze lijst met [hostspecifieke instructies](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) om uw host te vinden en volg de stappen om alle records toe te voegen die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="3145e-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="3145e-128">Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="3145e-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="3145e-129">Als u wilt wachten tot later, schuift u naar de onderkant en selecteert **u Deze stap overslaan**.</span><span class="sxs-lookup"><span data-stu-id="3145e-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="3145e-130">Selecteer **Voltooien** - je bent klaar!</span><span class="sxs-lookup"><span data-stu-id="3145e-130">Select **Finish** - you're done!</span></span> 

## <a name="related-articles"></a><span data-ttu-id="3145e-131">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="3145e-131">Related articles</span></span>

[<span data-ttu-id="3145e-132">Veelgestelde vragen over domeinen</span><span class="sxs-lookup"><span data-stu-id="3145e-132">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="3145e-133">Wat is een domein?</span><span class="sxs-lookup"><span data-stu-id="3145e-133">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="3145e-134">Een domeinnaam kopen in Office 365</span><span class="sxs-lookup"><span data-stu-id="3145e-134">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="3145e-135">Uw domein instellen (host-specifieke instructies)</span><span class="sxs-lookup"><span data-stu-id="3145e-135">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="3145e-136">Hulp krijgen bij Office 365-domeinen</span><span class="sxs-lookup"><span data-stu-id="3145e-136">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.yml)
