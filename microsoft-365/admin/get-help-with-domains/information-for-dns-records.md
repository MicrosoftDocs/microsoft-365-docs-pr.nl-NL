---
title: De informatie verzamelen die u nodig hebt om DNS-records voor Office 365 te maken
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
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Lees hier de waarden/informatie die u nodig hebt om DNS-records voor Office 365 te maken. '
ms.custom: okr_smb
ms.openlocfilehash: 2490532894ef00bab5de3f406b0c104529423382
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210378"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="3cc39-103">De informatie verzamelen die u nodig hebt om DNS-records voor Office 365 te maken</span><span class="sxs-lookup"><span data-stu-id="3cc39-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="3cc39-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="3cc39-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="3cc39-105">Stap 1: De TXT-recordwaarde zoeken en verifiëren</span><span class="sxs-lookup"><span data-stu-id="3cc39-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="3cc39-106">Ga in het Microsoft 365-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Setup-domeinen.</a> **Setup**</span><span class="sxs-lookup"><span data-stu-id="3cc39-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker range="o365-germany"

1. <span data-ttu-id="3cc39-107">Ga in het beheercentrum naar deze pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen.</a></span><span class="sxs-lookup"><span data-stu-id="3cc39-107">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3cc39-108">Ga in het beheercentrum naar deze pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen.</a></span><span class="sxs-lookup"><span data-stu-id="3cc39-108">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="3cc39-109">Selecteer **op** de pagina Domeinen uw domein en selecteer **Vervolgens Installatie starten**.</span><span class="sxs-lookup"><span data-stu-id="3cc39-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="3cc39-110">U gaat terug naar de wizard voor het instellen van domeinen voor de specifieke waarde die u moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="3cc39-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="3cc39-111">Selecteer **op** de pagina Domein verifiëren in **plaats daarvan Een TXT-record toevoegen**en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3cc39-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="3cc39-112">Kopieer de **getoonde TXT-waarde.**</span><span class="sxs-lookup"><span data-stu-id="3cc39-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="3cc39-113">Het ziet er als volgt uit: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="3cc39-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="3cc39-114">Ga naar [DNS-records maken bij elke DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer uw DNS-host in de lijst met registrars om de stapsgewijze instructies te bekijken.</span><span class="sxs-lookup"><span data-stu-id="3cc39-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="3cc39-115">Volg de stappen voor het maken van de TXT-record (of MX-record) bij uw DNS-host en verifieer het domein vervolgens in Office 365.</span><span class="sxs-lookup"><span data-stu-id="3cc39-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="3cc39-116">Verwijder de TXT-record (of MX-record) van uw DNS-host zodra het domein is geverifieerd in Office 365.</span><span class="sxs-lookup"><span data-stu-id="3cc39-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="3cc39-117">Stap 2: Zoek de MX-recordwaarde voor e-mail en meer</span><span class="sxs-lookup"><span data-stu-id="3cc39-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="3cc39-118">Ga in het Microsoft 365-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Setup-domeinen.</a> **Setup**</span><span class="sxs-lookup"><span data-stu-id="3cc39-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
::: moniker range="o365-germany"

1. <span data-ttu-id="3cc39-119">Ga in het beheercentrum naar deze pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen.</a></span><span class="sxs-lookup"><span data-stu-id="3cc39-119">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3cc39-120">Ga in het beheercentrum naar deze pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen.</a></span><span class="sxs-lookup"><span data-stu-id="3cc39-120">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="3cc39-121">Selecteer uw domein op de pagina **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="3cc39-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="3cc39-122">Onder **Vereiste DNS-instellingen** ziet u de DNS-records die u moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="3cc39-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="3cc39-123">Deze informatie hebt u nodig bij het aanbrengen van wijzigingen bij uw DNS-host, dus het is handig om de waarden te kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="3cc39-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="3cc39-124">Welke groepen DNS-records op de pagina worden weergegeven, hangt af van uw keuzen die worden weergegeven onder **Domeindoel**.</span><span class="sxs-lookup"><span data-stu-id="3cc39-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="3cc39-125">Ga naar [DNS-records maken bij elke DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer vervolgens uw DNS-host in de lijst met registrars om stapsgewijze instructies te zien voor het toevoegen van records op de website van die DNS-host.</span><span class="sxs-lookup"><span data-stu-id="3cc39-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="3cc39-126">Volg de stappen voor het maken van de records bij uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="3cc39-126">Follow the steps for creating the records at your DNS host.</span></span>
