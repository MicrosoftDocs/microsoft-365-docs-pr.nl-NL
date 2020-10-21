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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Leer de waarden/informatie vinden die u nodig hebt om DNS-records voor Microsoft 365 te maken. '
ms.openlocfilehash: eca9dbe4e40193f76538b639624b827177ff7772
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645309"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="e59ce-103">De gegevens verzamelen die u nodig hebt om DNS-records te maken</span><span class="sxs-lookup"><span data-stu-id="e59ce-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="e59ce-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="e59ce-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="e59ce-105">Stap 1: Zoek de TXT-recordwaarde en controleer of</span><span class="sxs-lookup"><span data-stu-id="e59ce-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e59ce-106">Ga in het Microsoft 365-Beheercentrum naar **Setup** de \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domeinen</a> instellen.</span><span class="sxs-lookup"><span data-stu-id="e59ce-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e59ce-107">Ga in het Beheercentrum naar de pagina **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domeinen</a> instellen.</span><span class="sxs-lookup"><span data-stu-id="e59ce-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e59ce-108">Ga in het Beheercentrum naar de pagina **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domeinen</a> instellen.</span><span class="sxs-lookup"><span data-stu-id="e59ce-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="e59ce-109">Selecteer uw domein op de pagina **domeinen** en selecteer vervolgens **Setup starten**.</span><span class="sxs-lookup"><span data-stu-id="e59ce-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="e59ce-110">U gaat terug naar de wizard voor het instellen van domeinen voor de specifieke waarde die u moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e59ce-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="e59ce-111">Selecteer op de pagina **domein verifiëren** de optie hier **TXT-record toevoegen**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="e59ce-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="e59ce-112">Kopieer de getoonde **txt-waarde** .</span><span class="sxs-lookup"><span data-stu-id="e59ce-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="e59ce-113">Dit ziet er als volgt uit: **MS = msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="e59ce-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="e59ce-114">Ga naar [DNS-records maken bij een DNS-hosting provider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer uw DNS-host in de lijst met registraties om de stapsgewijze instructies weer te geven.</span><span class="sxs-lookup"><span data-stu-id="e59ce-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="e59ce-115">Volg de stappen voor het maken van de TXT-record (of MX-record) bij uw DNS-host en Verifieer het domein weer in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e59ce-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="e59ce-116">Verwijder de TXT-record (of MX-record) van uw DNS-host wanneer het domein is geverifieerd in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e59ce-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="e59ce-117">Stap 2: zoeken naar de MX-recordwaarde voor e-mail en meer</span><span class="sxs-lookup"><span data-stu-id="e59ce-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e59ce-118">Ga in het Microsoft 365-Beheercentrum naar **Setup** de \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domeinen</a> instellen.</span><span class="sxs-lookup"><span data-stu-id="e59ce-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="e59ce-119">Ga in het Beheercentrum naar de pagina **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domeinen</a> instellen.</span><span class="sxs-lookup"><span data-stu-id="e59ce-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e59ce-120">Ga in het Beheercentrum naar de pagina **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domeinen</a> instellen.</span><span class="sxs-lookup"><span data-stu-id="e59ce-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="e59ce-121">Selecteer uw domein op de pagina **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="e59ce-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="e59ce-122">Onder **Vereiste DNS-instellingen** ziet u de DNS-records die u moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e59ce-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="e59ce-123">Deze informatie hebt u nodig bij het aanbrengen van wijzigingen bij uw DNS-host, dus het is handig om de waarden te kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="e59ce-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="e59ce-124">Welke groepen DNS-records op de pagina worden weergegeven, hangt af van uw keuzen die worden weergegeven onder **Domeindoel**.</span><span class="sxs-lookup"><span data-stu-id="e59ce-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="e59ce-125">Ga naar [DNS-records maken bij een DNS-hosting provider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer vervolgens uw DNS-host in de lijst met bronvermeldingen voor stapsgewijze instructies voor het toevoegen van records aan de website van de DNS-host.</span><span class="sxs-lookup"><span data-stu-id="e59ce-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="e59ce-126">Volg de stappen voor het maken van de records bij uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="e59ce-126">Follow the steps for creating the records at your DNS host.</span></span>
