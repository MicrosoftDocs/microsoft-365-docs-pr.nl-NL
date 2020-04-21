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
ms.openlocfilehash: 08a4e505f4e2a50b3e92cae00b62415e6d02551f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629117"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="fefaa-103">DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden</span><span class="sxs-lookup"><span data-stu-id="fefaa-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="fefaa-104">**Als u de Microsoft-records van uw domein beheert bij uw DNS-hostingprovider,** hoeft u zich geen zorgen te maken over de stappen in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="fefaa-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="fefaa-105">De website verandert niet van locatie en blijft gewoon bereikbaar.</span><span class="sxs-lookup"><span data-stu-id="fefaa-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="fefaa-106">**Als Microsoft uw DNS-records beheert**om verkeer te routeren naar een bestaande openbare website die buiten Microsoft wordt gehost, gaat u als volgt te werk nadat u uw domein aan Microsoft hebt toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="fefaa-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="fefaa-107">DNS-records bijwerken in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="fefaa-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="fefaa-108">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="fefaa-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="fefaa-109">Op de pagina **Domeinen** selecteert u in de lijst met domeinen het domein dat u voor uw website gebruikt en selecteert u vervolgens **DNS-instellingen** in het deelvenster Beheren.</span><span class="sxs-lookup"><span data-stu-id="fefaa-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="fefaa-110">Selecteer **+ Nieuwe aangepaste record** en typ het volgende:</span><span class="sxs-lookup"><span data-stu-id="fefaa-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="fefaa-111">Voor **DNS-type** voert u in: **A (adres)**</span><span class="sxs-lookup"><span data-stu-id="fefaa-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="fefaa-112">Typ het volgende voor **Hostnaam of alias**: **@**</span><span class="sxs-lookup"><span data-stu-id="fefaa-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="fefaa-113">Voor **IP-adres** typt u het statische IP-adres van uw website waar deze momenteel wordt gehost (bijvoorbeeld: 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="fefaa-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="fefaa-p102">Dit moet een  *statisch*  IP-adres van de website zijn, geen  *dynamisch*  IP-adres. Kijk op de site waar uw website wordt gehost om er zeker van te zijn dat u een statisch IP-adres kunt krijgen voor uw openbare website.</span><span class="sxs-lookup"><span data-stu-id="fefaa-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="fefaa-116">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-116">Select **Save**.</span></span> 
    
<span data-ttu-id="fefaa-117">U kunt eveneens een CNAME-record maken om klanten te helpen bij het zoeken van uw website.</span><span class="sxs-lookup"><span data-stu-id="fefaa-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="fefaa-118">Selecteer **+ Nieuwe aangepaste record** en typ het volgende:</span><span class="sxs-lookup"><span data-stu-id="fefaa-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="fefaa-119">Voor **DNS-type** voert u in: **CNAME (alias)**</span><span class="sxs-lookup"><span data-stu-id="fefaa-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="fefaa-120">Voor **Hostnaam of alias** typt u: **www**</span><span class="sxs-lookup"><span data-stu-id="fefaa-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="fefaa-121">Voor **Adres waarnaar wordt verwezen** typt u de FQDN (Fully Qualified Domain Name) voor uw website (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fefaa-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="fefaa-122">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fefaa-122">Select **Save**.</span></span> 
    
<span data-ttu-id="fefaa-123">Ga ten slotte als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="fefaa-123">Finally, do the following:</span></span>
  
<span data-ttu-id="fefaa-124">[Werk de NS-records van uw domein bij](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) om naar Microsoft te wijzen.</span><span class="sxs-lookup"><span data-stu-id="fefaa-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Microsoft.</span></span> 
  
<span data-ttu-id="fefaa-125">Wanneer de NS-records zijn bijgewerkt om naar Microsoft te wijzen, is uw domein helemaal ingesteld.</span><span class="sxs-lookup"><span data-stu-id="fefaa-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="fefaa-126">E-mail wordt doorgestuurd naar Microsoft en het verkeer naar uw websiteadres blijft naar uw huidige websitehost gaan.</span><span class="sxs-lookup"><span data-stu-id="fefaa-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
