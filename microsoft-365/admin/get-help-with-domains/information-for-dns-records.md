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
ms.openlocfilehash: def9fbe201e158f1e071a67caeaf29ed26732f97
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256841"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="aba00-103">De gegevens verzamelen die u nodig hebt om DNS-records te maken</span><span class="sxs-lookup"><span data-stu-id="aba00-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="aba00-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="aba00-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="aba00-105">Stap 1: De TXT-recordwaarde zoeken en controleren</span><span class="sxs-lookup"><span data-stu-id="aba00-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="aba00-106">Ga in Microsoft 365-beheercentrum naar de pagina **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domeinen.</a></span><span class="sxs-lookup"><span data-stu-id="aba00-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="aba00-107">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="aba00-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="aba00-108">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="aba00-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="aba00-109">Selecteer op **de pagina** Domeinen uw domein en selecteer vervolgens **Setup starten.**</span><span class="sxs-lookup"><span data-stu-id="aba00-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="aba00-110">U gaat terug naar de wizard voor het instellen van domeinen voor de specifieke waarde die u moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="aba00-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="aba00-111">Selecteer op **de pagina Domeinverificatie** de optie **Een TXT-record toevoegen** aan de DNS-records van het domein en selecteer vervolgens **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="aba00-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="aba00-112">Kopieer de **weergegeven TXT-waarde.**</span><span class="sxs-lookup"><span data-stu-id="aba00-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="aba00-113">Het ziet er zo uit: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="aba00-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="aba00-114">Ga naar [DNS-records toevoegen om uw domein te verbinden](create-dns-records-at-any-dns-hosting-provider.md)en volg de stappen om records toe te voegen op de website van uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="aba00-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="aba00-115">Volg de stappen voor het maken van de TXT-record (of MX-record) bij uw DNS-host en controleer vervolgens het domein weer in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aba00-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="aba00-116">Verwijder de TXT-record (of MX-record) van uw DNS-host zodra het domein is geverifieerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aba00-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="aba00-117">Stap 2: De MX-recordwaarde voor e-mail zoeken en meer</span><span class="sxs-lookup"><span data-stu-id="aba00-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="aba00-118">Ga in Microsoft 365-beheercentrum naar de pagina **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domeinen.</a></span><span class="sxs-lookup"><span data-stu-id="aba00-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="aba00-119">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="aba00-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="aba00-120">Ga in het beheercentrum naar **Instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="aba00-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="aba00-121">Selecteer uw domein op de pagina **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="aba00-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="aba00-122">Kies **Manage DNS**, select More Options **Add** your own  >  **DNS** and select **Continue** to see the DNS records to add.</span><span class="sxs-lookup"><span data-stu-id="aba00-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="aba00-123">Deze informatie hebt u nodig bij het aanbrengen van wijzigingen bij uw DNS-host, dus het is handig om de waarden te kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="aba00-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="aba00-124">Welke groepen DNS-records op de pagina worden weergegeven, hangt af van uw keuzen die worden weergegeven onder **Domeindoel**.</span><span class="sxs-lookup"><span data-stu-id="aba00-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="aba00-125">Ga naar [DNS-records toevoegen om uw domein te verbinden](create-dns-records-at-any-dns-hosting-provider.md)en volg de stappen om records toe te voegen op de website van uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="aba00-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="aba00-126">Volg de stappen voor het maken van de records bij uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="aba00-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="aba00-127">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="aba00-127">Related content</span></span>

<span data-ttu-id="aba00-128">[Veelgestelde vragen over domeinen](../setup/domains-faq.yml) (artikel)</span><span class="sxs-lookup"><span data-stu-id="aba00-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="aba00-129">[Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](find-and-fix-issues.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="aba00-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="aba00-130">[Domeinen beheren](index.yml) (koppelingspagina)</span><span class="sxs-lookup"><span data-stu-id="aba00-130">[Manage domains](index.yml) (link page)</span></span>