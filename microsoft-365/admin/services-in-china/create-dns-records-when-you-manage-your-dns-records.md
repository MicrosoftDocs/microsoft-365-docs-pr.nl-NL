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
ms.openlocfilehash: b81ab3442e7087c4b7ee9bb3b5e5c2160d724986
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211995"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="99fa0-103">DNS-records maken voor Office 365 wanneer u uw DNS-records beheert</span><span class="sxs-lookup"><span data-stu-id="99fa0-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="99fa0-104">Zie [DNS-records maken bij elke DNS-hostingprovider voor Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor gedetailleerde instructies voor Het maken van DNS-records voor Office 365, inclusief de MX-record die vereist is voor e-mailroutering.</span><span class="sxs-lookup"><span data-stu-id="99fa0-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="99fa0-105">Meer opties en een aantal dingen om rekening mee te houden:</span><span class="sxs-lookup"><span data-stu-id="99fa0-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="99fa0-106">Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="99fa0-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="99fa0-107">Zie [DNS-basisbeginselen](../get-help-with-domains/dns-basics.md)voor beschrijvingen van wat de DNS-records doen.</span><span class="sxs-lookup"><span data-stu-id="99fa0-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="99fa0-108">Sommige DNS-hostingproviders laten u niet alle vereiste recordtypen maken, wat servicebeperkingen veroorzaakt [wanneer uw hostingprovider geen SRV, CNAME, TXT of omleiding ondersteunt.](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="99fa0-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="99fa0-109">Als uw provider geen SRV-, TXT- of CNAME-records ondersteunt, raden we u aan [uw domein over](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) te dragen aan een provider die alle vereiste [recordtypen ondersteunt.](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="99fa0-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) to a [provider that supports all required record types](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="99fa0-110">Zie De gegevens verzamelen die [u nodig hebt om DNS-records voor Office 365 te maken,](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)als u wilt zien welke DNS-records nodig zijn en de waarden te vinden die voor elke record moeten worden gebruikt, inclusief de MX-record voor e-mail.</span><span class="sxs-lookup"><span data-stu-id="99fa0-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e).</span></span> <span data-ttu-id="99fa0-111">Zie [DNS-basisbeginselen](../get-help-with-domains/dns-basics.md)voor beschrijvingen van wat de DNS-records doen.</span><span class="sxs-lookup"><span data-stu-id="99fa0-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

