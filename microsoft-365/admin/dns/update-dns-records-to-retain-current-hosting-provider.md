---
title: DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Meer informatie over het routeren van verkeer naar een bestaande openbare website die buiten Microsoft wordt gehost, als u Microsoft de DNS-records voor uw aangepaste domein wilt laten beheren.
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645561"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="9a2f2-103">DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden</span><span class="sxs-lookup"><span data-stu-id="9a2f2-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="9a2f2-104">**Als u de Microsoft-records van uw domein beheert op uw DNS-hosting provider**, hoeft u zich geen zorgen te maken over de stappen in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="9a2f2-105">De website verandert niet van locatie en blijft gewoon bereikbaar.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="9a2f2-106">**Als uw DNS-records door Microsoft worden beheerd**om verkeer naar een bestaande openbare website buiten Microsoft te routeren nadat u uw domein aan Microsoft hebt toegevoegd, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="9a2f2-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="9a2f2-107">DNS-records bijwerken in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="9a2f2-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="9a2f2-108">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="9a2f2-109">Selecteer het domein op de pagina **domeinen** en kies vervolgens **DNS-records**.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="9a2f2-110">Selecteer **aangepaste records**onder **DNS-instellingen**.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-110">Under **DNS settings**, select **Custom Records**.</span></span>

4. <span data-ttu-id="9a2f2-111">Selecteer **+ Nieuwe aangepaste record** en typ het volgende:</span><span class="sxs-lookup"><span data-stu-id="9a2f2-111">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="9a2f2-112">Voor **DNS-type** voert u in: **A (adres)**</span><span class="sxs-lookup"><span data-stu-id="9a2f2-112">For **DNS type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="9a2f2-113">Typ het volgende voor **Hostnaam of alias**: **@**</span><span class="sxs-lookup"><span data-stu-id="9a2f2-113">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="9a2f2-114">Voor **IP-adres** typt u het statische IP-adres van uw website waar deze momenteel wordt gehost (bijvoorbeeld: 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="9a2f2-114">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="9a2f2-p102">Dit moet een  *statisch*  IP-adres van de website zijn, geen  *dynamisch*  IP-adres. Kijk op de site waar uw website wordt gehost om er zeker van te zijn dat u een statisch IP-adres kunt krijgen voor uw openbare website.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
5. <span data-ttu-id="9a2f2-117">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-117">Select **Save**.</span></span> 
    
<span data-ttu-id="9a2f2-118">U kunt eveneens een CNAME-record maken om klanten te helpen bij het zoeken van uw website.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-118">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="9a2f2-119">Selecteer **+ Nieuwe aangepaste record** en typ het volgende:</span><span class="sxs-lookup"><span data-stu-id="9a2f2-119">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="9a2f2-120">Voor **DNS-type** voert u in: **CNAME (alias)**</span><span class="sxs-lookup"><span data-stu-id="9a2f2-120">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="9a2f2-121">Voor **Hostnaam of alias** typt u: **www**</span><span class="sxs-lookup"><span data-stu-id="9a2f2-121">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="9a2f2-122">Voor **Adres waarnaar wordt verwezen** typt u de FQDN (Fully Qualified Domain Name) voor uw website (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9a2f2-122">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="9a2f2-123">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-123">Select **Save**.</span></span> 
    
<span data-ttu-id="9a2f2-124">Ga ten slotte als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="9a2f2-124">Finally, do the following:</span></span>
  
<span data-ttu-id="9a2f2-125">[Werk de DNS-records van uw domein](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) voor zodat ze verwijzen naar Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-125">[Update your domain's NS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to point to Microsoft.</span></span> 
  
<span data-ttu-id="9a2f2-126">Wanneer de NS-records zijn bijgewerkt zodat ze verwijzen naar Microsoft, is uw domein allemaal ingesteld.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-126">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="9a2f2-127">E-mail wordt naar Microsoft gerouteerd en verkeer naar uw websiteadres gaat verder naar uw huidige website-host.</span><span class="sxs-lookup"><span data-stu-id="9a2f2-127">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
