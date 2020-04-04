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
description: Als u Office 365 hebt ingesteld om DNS-records voor uw aangepaste domein te beheren, leest u het verkeer naar een bestaande openbare website die buiten Office 365 wordt gehost.
ms.openlocfilehash: 3e71925f9b50e5520bd383aa5318db513202f6ec
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142537"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="d77ab-103">DNS-records bijwerken als u uw website bij uw huidige hostingprovider wilt houden</span><span class="sxs-lookup"><span data-stu-id="d77ab-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="d77ab-p101">**Als u de Office 365-records van uw domein beheert bij uw DNS-hostingprovider**, hoeft u zich geen zorgen te maken over de stappen in dit onderwerp. De website verandert niet van locatie en blijft gewoon bereikbaar.</span><span class="sxs-lookup"><span data-stu-id="d77ab-p101">**If you manage your domain's Office 365 records at your DNS hosting provider**, you don't have to worry about the steps in this topic. Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="d77ab-106">**Als uw DNS-records worden beheerd in Office 365**, voert u de volgende stappen uit om verkeer naar een bestaande openbare website buiten Office 365 te routeren nadat u uw domein aan Office 365 hebt toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="d77ab-106">**If Office 365 manages your DNS records**, to route traffic to an existing public website hosted outside of Office 365, after you add your domain to Office 365, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="d77ab-107">DNS-records bijwerken in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="d77ab-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="d77ab-108">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Setup-domeinen.</a> **Setup**</span><span class="sxs-lookup"><span data-stu-id="d77ab-108">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="d77ab-109">Op de pagina **Domeinen** selecteert u in de lijst met domeinen het domein dat u voor uw website gebruikt en selecteert u vervolgens **DNS-instellingen** in het deelvenster Beheren.</span><span class="sxs-lookup"><span data-stu-id="d77ab-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="d77ab-110">Selecteer **+ Nieuwe aangepaste record** en typ het volgende:</span><span class="sxs-lookup"><span data-stu-id="d77ab-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="d77ab-111">Voor **DNS-type** voert u in: **A (adres)**</span><span class="sxs-lookup"><span data-stu-id="d77ab-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="d77ab-112">Typ het volgende voor **Hostnaam of alias**: **@**</span><span class="sxs-lookup"><span data-stu-id="d77ab-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="d77ab-113">Voor **IP-adres** typt u het statische IP-adres van uw website waar deze momenteel wordt gehost (bijvoorbeeld: 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="d77ab-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="d77ab-p102">Dit moet een  *statisch*  IP-adres van de website zijn, geen  *dynamisch*  IP-adres. Kijk op de site waar uw website wordt gehost om er zeker van te zijn dat u een statisch IP-adres kunt krijgen voor uw openbare website.</span><span class="sxs-lookup"><span data-stu-id="d77ab-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="d77ab-116">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d77ab-116">Select **Save**.</span></span> 
    
<span data-ttu-id="d77ab-117">U kunt eveneens een CNAME-record maken om klanten te helpen bij het zoeken van uw website.</span><span class="sxs-lookup"><span data-stu-id="d77ab-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="d77ab-118">Selecteer **+ Nieuwe aangepaste record** en typ het volgende:</span><span class="sxs-lookup"><span data-stu-id="d77ab-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="d77ab-119">Voor **DNS-type** voert u in: **CNAME (alias)**</span><span class="sxs-lookup"><span data-stu-id="d77ab-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="d77ab-120">Voor **Hostnaam of alias** typt u: **www**</span><span class="sxs-lookup"><span data-stu-id="d77ab-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="d77ab-121">Voor **Adres waarnaar wordt verwezen** typt u de FQDN (Fully Qualified Domain Name) voor uw website (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d77ab-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="d77ab-122">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d77ab-122">Select **Save**.</span></span> 
    
<span data-ttu-id="d77ab-123">Ga ten slotte als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="d77ab-123">Finally, do the following:</span></span>
  
<span data-ttu-id="d77ab-124">[Werk de DNS-records van uw domein bij](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) om ze te laten verwijzen naar Office 365.</span><span class="sxs-lookup"><span data-stu-id="d77ab-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Office 365.</span></span> 
  
<span data-ttu-id="d77ab-p103">Nadat de NS-records zijn bijgewerkt en verwijzen naar Office 365, is uw domein klaar voor gebruik. E-mail wordt doorgestuurd naar Office 365 en verkeer naar uw websiteadres wordt omgeleid naar uw huidige websitehost.</span><span class="sxs-lookup"><span data-stu-id="d77ab-p103">When the NS records have been updated to point to Office 365, your domain is all set up. Email will be routed to Office 365, and traffic to your website address will continue to go to your current website host.</span></span>
 
