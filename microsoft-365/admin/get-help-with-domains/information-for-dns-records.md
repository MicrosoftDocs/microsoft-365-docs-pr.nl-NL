---
title: De informatie verzamelen die u nodig hebt om DNS-records voor Office 365 te maken
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
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Meer informatie over de waarden/informatie die u nodig hebt om DNS-records voor Office 365 te maken. '
ms.custom: okr_smb
ms.openlocfilehash: 7b995aedc21305367e4a6621781e138d0d60efd1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807418"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="6ebd6-103">De informatie verzamelen die u nodig hebt om DNS-records voor Office 365 te maken</span><span class="sxs-lookup"><span data-stu-id="6ebd6-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="6ebd6-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="6ebd6-105">Stap 1: De txt-recordwaarde zoeken en controleren</span><span class="sxs-lookup"><span data-stu-id="6ebd6-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="6ebd6-106">Ga in het Microsoft 365-beheercentrum naar de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">pagina</a> **Domeinen instellen.** \></span><span class="sxs-lookup"><span data-stu-id="6ebd6-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="6ebd6-107">Als u Office 365 Germany gebruikt, gaat u naar deze pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen.</a></span><span class="sxs-lookup"><span data-stu-id="6ebd6-107">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="6ebd6-108">Als u Office 365 gebruikt dat wordt beheerd door 21Vianet, gaat u naar deze pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen.</a></span><span class="sxs-lookup"><span data-stu-id="6ebd6-108">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6ebd6-109">Selecteer op de pagina **Domeinen** uw domein en selecteer **vervolgens Start-instelling**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="6ebd6-110">U gaat terug naar de wizard voor het instellen van domeinen voor de specifieke waarde die u moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="6ebd6-111">Selecteer op de **pagina Domein verifiëren** in plaats daarvan een **TXT-record toevoegen**en selecteer **Vervolgens**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="6ebd6-112">Kopieer de getoonde **TXT-waarde.**</span><span class="sxs-lookup"><span data-stu-id="6ebd6-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="6ebd6-113">Het ziet er als volgt uit: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="6ebd6-114">Ga naar [DNS-records maken bij elke DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer uw DNS-host in de lijst met registrars om de stapsgewijze instructies te bekijken.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="6ebd6-115">Volg de stappen voor het maken van de TXT-record (of MX-record) bij uw DNS-host en verifieer het domein vervolgens in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="6ebd6-116">Verwijder de TXT-record (of MX-record) uit uw DNS-host zodra het domein is geverifieerd in Office 365.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="6ebd6-117">Stap 2: Zoek de MX-recordwaarde voor e-mail en meer</span><span class="sxs-lookup"><span data-stu-id="6ebd6-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="6ebd6-118">Ga in het Microsoft 365-beheercentrum naar de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">pagina</a> **Domeinen instellen.** \></span><span class="sxs-lookup"><span data-stu-id="6ebd6-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="6ebd6-119">Als u Office 365 Germany gebruikt, gaat u naar deze pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen.</a></span><span class="sxs-lookup"><span data-stu-id="6ebd6-119">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="6ebd6-120">Als u Office 365 gebruikt dat wordt beheerd door 21Vianet, gaat u naar deze pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen.</a></span><span class="sxs-lookup"><span data-stu-id="6ebd6-120">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6ebd6-121">Selecteer uw domein op de pagina **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="6ebd6-122">Onder **Vereiste DNS-instellingen** ziet u de DNS-records die u moet toevoegen.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="6ebd6-123">Deze informatie hebt u nodig bij het aanbrengen van wijzigingen bij uw DNS-host, dus het is handig om de waarden te kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="6ebd6-124">Welke groepen DNS-records op de pagina worden weergegeven, hangt af van uw keuzen die worden weergegeven onder **Domeindoel**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="6ebd6-125">Ga naar [DNS-records maken bij elke DNS-hostingprovider](create-dns-records-at-any-dns-hosting-provider.md)en selecteer vervolgens uw DNS-host in de lijst met registrars om stapsgewijze instructies te zien voor het toevoegen van records op de website van die DNS-host.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="6ebd6-126">Volg de stappen voor het maken van de records bij uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-126">Follow the steps for creating the records at your DNS host.</span></span>
