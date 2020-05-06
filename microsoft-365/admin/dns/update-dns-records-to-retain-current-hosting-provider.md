---
title: DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden
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
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Als u Microsoft hebt ingesteld om DNS-records voor uw aangepaste domein te beheren, vindt u informatie over het routeren van verkeer naar een bestaande openbare website die buiten Microsoft wordt gehost.
ms.openlocfilehash: 58b58479a2c880cc0193058abc328cc5feea4af1
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048829"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="8deb9-103">DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden</span><span class="sxs-lookup"><span data-stu-id="8deb9-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="8deb9-104">**Als u de Microsoft-records van uw domein beheert bij uw DNS-hostingprovider,** hoeft u zich geen zorgen te maken over de stappen in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="8deb9-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="8deb9-105">De website verandert niet van locatie en blijft gewoon bereikbaar.</span><span class="sxs-lookup"><span data-stu-id="8deb9-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="8deb9-106">**Als Microsoft uw DNS-records beheert**om verkeer te routeren naar een bestaande openbare website die buiten Microsoft wordt gehost, gaat u als volgt te werk nadat u uw domein aan Microsoft hebt toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="8deb9-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="8deb9-107">DNS-records bijwerken in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="8deb9-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="8deb9-108">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="8deb9-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="8deb9-109">Op de pagina **Domeinen** selecteert u in de lijst met domeinen het domein dat u voor uw website gebruikt en selecteert u vervolgens **DNS-instellingen** in het deelvenster Beheren.</span><span class="sxs-lookup"><span data-stu-id="8deb9-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="8deb9-110">Selecteer **+ Nieuwe aangepaste record** en typ het volgende:</span><span class="sxs-lookup"><span data-stu-id="8deb9-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="8deb9-111">Voor **DNS-type** voert u in: **A (adres)**</span><span class="sxs-lookup"><span data-stu-id="8deb9-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="8deb9-112">Typ het volgende voor **Hostnaam of alias**: **@**</span><span class="sxs-lookup"><span data-stu-id="8deb9-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="8deb9-113">Voor **IP-adres** typt u het statische IP-adres van uw website waar deze momenteel wordt gehost (bijvoorbeeld: 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="8deb9-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="8deb9-p102">Dit moet een  *statisch*  IP-adres van de website zijn, geen  *dynamisch*  IP-adres. Kijk op de site waar uw website wordt gehost om er zeker van te zijn dat u een statisch IP-adres kunt krijgen voor uw openbare website.</span><span class="sxs-lookup"><span data-stu-id="8deb9-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="8deb9-116">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8deb9-116">Select **Save**.</span></span> 
    
<span data-ttu-id="8deb9-117">U kunt eveneens een CNAME-record maken om klanten te helpen bij het zoeken van uw website.</span><span class="sxs-lookup"><span data-stu-id="8deb9-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="8deb9-118">Selecteer **+ Nieuwe aangepaste record** en typ het volgende:</span><span class="sxs-lookup"><span data-stu-id="8deb9-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="8deb9-119">Voor **DNS-type** voert u in: **CNAME (alias)**</span><span class="sxs-lookup"><span data-stu-id="8deb9-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="8deb9-120">Voor **Hostnaam of alias** typt u: **www**</span><span class="sxs-lookup"><span data-stu-id="8deb9-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="8deb9-121">Voor **Adres waarnaar wordt verwezen** typt u de FQDN (Fully Qualified Domain Name) voor uw website (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8deb9-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="8deb9-122">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="8deb9-122">Select **Save**.</span></span> 
    
<span data-ttu-id="8deb9-123">Ga ten slotte als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="8deb9-123">Finally, do the following:</span></span>
  
<span data-ttu-id="8deb9-124">[Werk de NS-records van uw domein bij](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) om naar Microsoft te wijzen.</span><span class="sxs-lookup"><span data-stu-id="8deb9-124">[Update your domain's NS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to point to Microsoft.</span></span> 
  
<span data-ttu-id="8deb9-125">Wanneer de NS-records zijn bijgewerkt om naar Microsoft te wijzen, is uw domein helemaal ingesteld.</span><span class="sxs-lookup"><span data-stu-id="8deb9-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="8deb9-126">E-mail wordt doorgestuurd naar Microsoft en het verkeer naar uw websiteadres blijft naar uw huidige websitehost gaan.</span><span class="sxs-lookup"><span data-stu-id="8deb9-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
