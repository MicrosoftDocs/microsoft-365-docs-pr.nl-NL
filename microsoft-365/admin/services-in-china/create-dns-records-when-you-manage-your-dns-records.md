---
title: DNS-records maken voor Office 365 wanneer u uw DNS-records beheert
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
description: 'Informatie over het maken van DNS-records voor Office 365 beheerd door 21Vianet wanneer u uw DNS-records beheert. '
monikerRange: o365-21vianet
ms.openlocfilehash: 1eaa2bcc7263eaa12e53131246abd591006b0536
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914352"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="615f9-103">DNS-records maken voor Office 365 wanneer u uw DNS-records beheert</span><span class="sxs-lookup"><span data-stu-id="615f9-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="615f9-104">Zie DNS-records maken bij een DNS-hostingprovider voor [Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor gedetailleerde instructies over het maken van DNS-records voor Office 365 beheerd door 21Vianet, inclusief de MX-record die vereist is voor het routeren van e-mail.</span><span class="sxs-lookup"><span data-stu-id="615f9-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="615f9-105">Meer opties en een aantal dingen waar u rekening mee moet houden:</span><span class="sxs-lookup"><span data-stu-id="615f9-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="615f9-106">Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="615f9-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="615f9-107">Zie DNS-basisbeginselen voor beschrijvingen van wat de [DNS-records doen.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="615f9-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="615f9-108">Bij sommige DNS-hostingproviders kunt u niet alle vereiste recordtypen maken, waardoor servicebeperkingen worden veroorzaakt wanneer uw hostingprovider geen ondersteuning biedt voor [SRV, CNAME, TXT of omleiding.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="615f9-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="615f9-109">Als uw provider geen SRV-, TXT- of CNAME-records ondersteunt, raden we u aan uw domein over te dragen aan een provider die alle vereiste [recordtypen ondersteunt.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77) [](../get-help-with-domains/buy-a-domain-name.md)</span><span class="sxs-lookup"><span data-stu-id="615f9-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](../get-help-with-domains/buy-a-domain-name.md) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="615f9-110">Zie De benodigde gegevens verzamelen om DNS-records van [Office 365](../get-help-with-domains/information-for-dns-records.md)te maken als u wilt zien welke DNS-records nodig zijn en welke waarden voor elke record moeten worden gebruikt, inclusief de MX-record voor e-mail.</span><span class="sxs-lookup"><span data-stu-id="615f9-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](../get-help-with-domains/information-for-dns-records.md).</span></span> <span data-ttu-id="615f9-111">Zie DNS-basisbeginselen voor beschrijvingen van wat de [DNS-records doen.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="615f9-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
