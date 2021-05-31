---
title: Uw domeinregistrar zoeken
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Lees hier hoe u uw domeinregistrar en DNS-hostingprovider kunt vinden met behulp van de zoekpagina van InterNIC.
ms.openlocfilehash: af883f53c8c45aee2594b0f5b8b9da57e5717f9e
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706392"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="31236-103">Uw domeinregistrar zoeken</span><span class="sxs-lookup"><span data-stu-id="31236-103">Find your domain registrar</span></span>

 <span data-ttu-id="31236-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="31236-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="31236-105">Domeinregistrar</span><span class="sxs-lookup"><span data-stu-id="31236-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="31236-106">Uw domeinnaamregistrar vinden</span><span class="sxs-lookup"><span data-stu-id="31236-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="31236-107">Alleen domeinen die eindigen op *.COM*, *.NET* en *.EDU* werken met dit hulpprogramma.</span><span class="sxs-lookup"><span data-stu-id="31236-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="31236-p101">Typ uw domein op de [zoekpagina van InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770) in het vak **Whois Search**, bijvoorbeeld *contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="31236-p101">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="31236-110">Selecteer de optie **Domain** en selecteer **Submit**.</span><span class="sxs-lookup"><span data-stu-id="31236-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="31236-p102">Zoek op de pagina **Whois Search Results** het item **Registrar**. Hier staat de organisatie die fungeert als registrarservice voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="31236-p102">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="31236-113">DNS-hostingprovider</span><span class="sxs-lookup"><span data-stu-id="31236-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="31236-114">Uw DNS-hostingprovider vinden</span><span class="sxs-lookup"><span data-stu-id="31236-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="31236-115">Alleen domeinen die eindigen op *.COM*, *.NET* en *.EDU* werken met dit hulpprogramma.</span><span class="sxs-lookup"><span data-stu-id="31236-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="31236-p103">Typ uw domein op de [zoekpagina van InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770) in het vak **Whois Search**, bijvoorbeeld contoso.com.</span><span class="sxs-lookup"><span data-stu-id="31236-p103">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="31236-118">Selecteer de optie **Domain** en selecteer **Submit**.</span><span class="sxs-lookup"><span data-stu-id="31236-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="31236-119">Zoek op de pagina **Whois Search Results** het item **Name Server**.</span><span class="sxs-lookup"><span data-stu-id="31236-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="31236-p104">Kopieer de gegevens van de naamserver (NS) na de dubbele punt (:) en plak ze in het vak **Search** bovenaan op de pagina. Selecteer **Nameserver** en vervolgens **Submit**.</span><span class="sxs-lookup"><span data-stu-id="31236-p104">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="31236-p105">Zoek op de pagina **Whois Search Results** het item **Registrar**. Hier staat de DNS-serviceprovider, de DNS-provider die eigenaar is van de naamserver voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="31236-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

