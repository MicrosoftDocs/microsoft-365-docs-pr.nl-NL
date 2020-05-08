---
title: DNS-records maken voor Office 365 wanneer u uw DNS-records beheert
f1.keywords:
- CSH
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
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Lees dat u DNS-records maakt voor Office 365 die door 21Vianet worden beheerd wanneer u uw DNS-records beheert. '
monikerRange: o365-21vianet
ms.openlocfilehash: f6ba0f891bbc207bf7d56c4527760a5c8caf90b0
ms.sourcegitcommit: d688a296dc2b094b70da55334c9a3ad91236cf6f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44155395"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="79558-103">DNS-records maken voor Office 365 wanneer u uw DNS-records beheert</span><span class="sxs-lookup"><span data-stu-id="79558-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="79558-104">Zie [DNS-records maken bij elke DNS-hostingprovider voor Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor gedetailleerde instructies voor Het maken van DNS-records voor Office 365, inclusief de MX-record die vereist is voor e-mailroutering.</span><span class="sxs-lookup"><span data-stu-id="79558-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="79558-105">Meer opties en een aantal dingen om rekening mee te houden:</span><span class="sxs-lookup"><span data-stu-id="79558-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="79558-106">Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="79558-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="79558-107">Zie [DNS-basisbeginselen](../get-help-with-domains/dns-basics.md)voor beschrijvingen van wat de DNS-records doen.</span><span class="sxs-lookup"><span data-stu-id="79558-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="79558-108">Sommige DNS-hostingproviders laten u niet alle vereiste recordtypen maken, wat servicebeperkingen veroorzaakt [wanneer uw hostingprovider geen SRV, CNAME, TXT of omleiding ondersteunt.](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="79558-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="79558-109">Als uw provider geen SRV-, TXT- of CNAME-records ondersteunt, raden we u aan [uw domein over](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) te dragen aan een provider die alle vereiste [recordtypen ondersteunt.](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="79558-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) to a [provider that supports all required record types](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="79558-110">Zie De gegevens verzamelen die [u nodig hebt om DNS-records voor Office 365 te maken,](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)als u wilt zien welke DNS-records nodig zijn en de waarden te vinden die voor elke record moeten worden gebruikt, inclusief de MX-record voor e-mail.</span><span class="sxs-lookup"><span data-stu-id="79558-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span> <span data-ttu-id="79558-111">Zie [DNS-basisbeginselen](../get-help-with-domains/dns-basics.md)voor beschrijvingen van wat de DNS-records doen.</span><span class="sxs-lookup"><span data-stu-id="79558-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

