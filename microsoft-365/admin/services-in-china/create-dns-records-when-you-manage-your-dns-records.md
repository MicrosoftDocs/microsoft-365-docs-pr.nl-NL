---
title: DNS-records voor Office 365 maken wanneer u uw DNS-records beheert
f1.keywords:
- CSH
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
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Meer informatie over het maken van DNS-records voor Office 365, beheerd door 21Vianet wanneer u uw DNS-records beheert. '
monikerRange: o365-21vianet
ms.openlocfilehash: 8f252ba47fbd72f5a628a23567addcc84604fb3c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644817"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="0d47f-103">DNS-records voor Office 365 maken wanneer u uw DNS-records beheert</span><span class="sxs-lookup"><span data-stu-id="0d47f-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="0d47f-104">Voor uitgebreide instructies over het maken van DNS-records voor Office 365, beheerd door 21Vianet, waaronder de MX-record die nodig is voor e-mail routering, raadpleegt u [DNS-records maken bij een DNS-hosting provider voor Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0d47f-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="0d47f-105">Meer opties en enkele zaken waarvan u op de hoogte moet zijn:</span><span class="sxs-lookup"><span data-stu-id="0d47f-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="0d47f-106">Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="0d47f-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="0d47f-107">Zie [basisprincipes van DNS](../get-help-with-domains/dns-basics.md)voor beschrijvingen van de DNS-records.</span><span class="sxs-lookup"><span data-stu-id="0d47f-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="0d47f-108">Met sommige DNS-hosting providers kunt u niet alle vereiste recordtypen maken, waardoor [service beperkingen worden veroorzaakt wanneer uw hosting provider geen ondersteuning biedt voor SRV, CNAME, txt of omleiding](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="0d47f-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="0d47f-109">Als uw provider geen ondersteuning biedt voor SRV, TXT of CNAME-records, kunt u [het beste uw domein overzetten](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) naar een [provider die ondersteuning biedt voor alle vereiste recordtypen](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="0d47f-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="0d47f-110">Zie [de informatie verzamelen die u nodig hebt om DNS-records voor Office 365 te maken](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)als u wilt weten welke DNS-records zijn vereist en om de waarden te vinden voor elke record, waaronder de MX-record voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="0d47f-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span> <span data-ttu-id="0d47f-111">Zie [basisprincipes van DNS](../get-help-with-domains/dns-basics.md)voor beschrijvingen van de DNS-records.</span><span class="sxs-lookup"><span data-stu-id="0d47f-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

