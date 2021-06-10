---
title: De gegevens verzamelen die u nodig hebt om DNS-records te maken
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
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Verzamel de waarden/gegevens die u nodig hebt om DNS-records te maken om uw domein te verbinden met uw Microsoft 365 abonnement.
ms.openlocfilehash: e65d53269f5fb8625b12c4eb22f78516818045be
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635724"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="63a72-103">De gegevens verzamelen die u nodig hebt om DNS-records te maken</span><span class="sxs-lookup"><span data-stu-id="63a72-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="63a72-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="63a72-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="63a72-105">Stap 1: De TXT-recordwaarde zoeken en controleren</span><span class="sxs-lookup"><span data-stu-id="63a72-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="63a72-106">Ga in Microsoft 365 beheercentrum naar de pagina **Domeinen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> instellen.</span><span class="sxs-lookup"><span data-stu-id="63a72-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="63a72-107">Ga in het beheercentrum naar de **pagina Domeinen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a> instellen.</span><span class="sxs-lookup"><span data-stu-id="63a72-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="63a72-108">Ga in het beheercentrum naar de **pagina Domeinen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a> instellen.</span><span class="sxs-lookup"><span data-stu-id="63a72-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="63a72-109">Selecteer op **de pagina** Domeinen uw domein en selecteer vervolgens **Setup starten.**</span><span class="sxs-lookup"><span data-stu-id="63a72-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="63a72-110">U gaat terug naar de wizard voor het instellen van domeinen voor de specifieke waarde die u moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="63a72-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="63a72-111">Selecteer op **de pagina** Domein verifiëren de optie In plaats daarvan **een TXT-record toevoegen** en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="63a72-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="63a72-112">Kopieer de **weergegeven TXT-waarde.**</span><span class="sxs-lookup"><span data-stu-id="63a72-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="63a72-113">Het ziet er zo uit: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="63a72-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="63a72-114">Ga naar DNS-records maken bij een [DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer uw DNS-host in de lijst met registrars om de stapsgewijs instructies te bekijken.</span><span class="sxs-lookup"><span data-stu-id="63a72-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="63a72-115">Volg de stappen voor het maken van de TXT-record (of MX-record) bij uw DNS-host en controleer vervolgens het domein weer in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63a72-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="63a72-116">Verwijder de TXT-record (of MX-record) van uw DNS-host zodra het domein is geverifieerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63a72-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="63a72-117">Stap 2: De MX-recordwaarde voor e-mail zoeken en meer</span><span class="sxs-lookup"><span data-stu-id="63a72-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="63a72-118">Ga in Microsoft 365 beheercentrum naar de pagina **Domeinen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> instellen.</span><span class="sxs-lookup"><span data-stu-id="63a72-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="63a72-119">Ga in het beheercentrum naar de **pagina Domeinen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a> instellen.</span><span class="sxs-lookup"><span data-stu-id="63a72-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="63a72-120">Ga in het beheercentrum naar de **pagina Domeinen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a> instellen.</span><span class="sxs-lookup"><span data-stu-id="63a72-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="63a72-121">Selecteer uw domein op de pagina **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="63a72-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="63a72-122">Onder **Vereiste DNS-instellingen** ziet u de DNS-records die u moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="63a72-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="63a72-123">Deze informatie hebt u nodig bij het aanbrengen van wijzigingen bij uw DNS-host, dus het is handig om de waarden te kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="63a72-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="63a72-124">Welke groepen DNS-records op de pagina worden weergegeven, hangt af van uw keuzen die worden weergegeven onder **Domeindoel**.</span><span class="sxs-lookup"><span data-stu-id="63a72-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="63a72-125">Ga naar DNS-records maken bij een [DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer vervolgens uw DNS-host in de lijst met registrars om stapsgewijs instructies te zien voor het toevoegen van records op de website van die DNS-host.</span><span class="sxs-lookup"><span data-stu-id="63a72-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="63a72-126">Volg de stappen voor het maken van de records bij uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="63a72-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="63a72-127">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="63a72-127">Related content</span></span>

<span data-ttu-id="63a72-128">[Veelgestelde vragen over domeinen](../setup/domains-faq.yml) (artikel)</span><span class="sxs-lookup"><span data-stu-id="63a72-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="63a72-129">[Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](find-and-fix-issues.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="63a72-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="63a72-130">[Domeinen beheren](index.yml) (koppelingspagina)</span><span class="sxs-lookup"><span data-stu-id="63a72-130">[Manage domains](index.yml) (link page)</span></span>