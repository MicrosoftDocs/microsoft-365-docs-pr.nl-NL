---
title: Uw domeinregistrar zoeken
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Lees hier hoe u uw domeinregistrar en DNS-hostingprovider kunt vinden met behulp van de zoekpagina van InterNIC.
ms.openlocfilehash: 234578c5622a883296a001ce7f226627dd9d93b5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628456"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="32ac5-103">Uw domeinregistrar zoeken</span><span class="sxs-lookup"><span data-stu-id="32ac5-103">Find your domain registrar</span></span>

 <span data-ttu-id="32ac5-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="32ac5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="32ac5-105">Domeinregistrar</span><span class="sxs-lookup"><span data-stu-id="32ac5-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="32ac5-106">Uw domeinnaamregistrar vinden</span><span class="sxs-lookup"><span data-stu-id="32ac5-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="32ac5-107">Alleen domeinen die eindigen op *.COM*, *.NET* en *.EDU* werken met dit hulpprogramma.</span><span class="sxs-lookup"><span data-stu-id="32ac5-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="32ac5-108">Typ op de [zoekpagina van InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770) uw domein in het vak **Whois Search**.</span><span class="sxs-lookup"><span data-stu-id="32ac5-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="32ac5-109">Bijvoorbeeld *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="32ac5-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="32ac5-110">Selecteer de optie **Domain** en selecteer **Submit**.</span><span class="sxs-lookup"><span data-stu-id="32ac5-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="32ac5-111">Zoek op de pagina **Whois Search Results** het item **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="32ac5-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="32ac5-112">Hier staat de organisatie die fungeert als registrar voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="32ac5-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="32ac5-113">DNS-hostingprovider</span><span class="sxs-lookup"><span data-stu-id="32ac5-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="32ac5-114">Uw DNS-hostingprovider vinden</span><span class="sxs-lookup"><span data-stu-id="32ac5-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="32ac5-115">Alleen domeinen die eindigen op *.COM*, *.NET* en *.EDU* werken met dit hulpprogramma.</span><span class="sxs-lookup"><span data-stu-id="32ac5-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="32ac5-116">Typ op de [zoekpagina van InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770) uw domein in het vak **Whois Search**.</span><span class="sxs-lookup"><span data-stu-id="32ac5-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="32ac5-117">Bijvoorbeeld contoso.com.</span><span class="sxs-lookup"><span data-stu-id="32ac5-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="32ac5-118">Selecteer de optie **Domain** en selecteer **Submit**.</span><span class="sxs-lookup"><span data-stu-id="32ac5-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="32ac5-119">Zoek op de pagina **Whois Search Results** het item **Name Server**.</span><span class="sxs-lookup"><span data-stu-id="32ac5-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="32ac5-120">Kopieer de gegevens over de naamserver (NS) na de dubbele punt (:) en plak ze in het vak **Search** bovenaan op de pagina.</span><span class="sxs-lookup"><span data-stu-id="32ac5-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="32ac5-121">Selecteer **Nameserver** en selecteer **Submit**.</span><span class="sxs-lookup"><span data-stu-id="32ac5-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="32ac5-p105">Zoek op de pagina **Whois Search Results** het item **Registrar**. Hier staat de DNS-serviceprovider, de DNS-provider die eigenaar is van de naamserver voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="32ac5-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

