---
title: Wat is het doel van de CNAME-record MSOID voor Office 365?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Meer informatie over de CNAME-record 'MSOID' in Office 365 die u naar de beste server voor verificatieprocessen leidt, zodat u sneller antwoord krijgt.
monikerRange: o365-21vianet
ms.openlocfilehash: a1d587abc9db03c9a1f7c5f66711fde3648a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914304"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="74212-103">Wat is het doel van de CNAME-record MSOID voor Office 365?</span><span class="sxs-lookup"><span data-stu-id="74212-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="74212-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="74212-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="74212-105">Het volgende geldt alleen voor \*\*Office 365 beheerd door 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="74212-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="74212-p101">U vraagt zich misschien af waarom u een CNAME-record voor MSOID moet toevoegen in Office 365. Dit is een record die u moet toevoegen voor alle aangepaste domeinen, ongeacht het abonnement dat u gebruikt. Waarom hebt u deze record nodig? Het is een beetje een technisch verhaal, maar het komt erop neer dat u wordt doorgestuurd naar de beste server voor bepaalde verificatieprocessen, zodat u sneller een reactie krijgt.</span><span class="sxs-lookup"><span data-stu-id="74212-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="74212-p102">Technische informatie: wanneer u een clienttoepassing uitvoert die werkt met Office 365, zoals Skype voor Bedrijven Online, Outlook, Windows PowerShell of Microsoft AzureActive Directory-synchronisatie, moeten uw referenties worden geverifieerd. In Office 365 wordt een CNAME-record gebruikt om te verwijzen naar het juiste verificatie-eindpunt voor uw locatie. Op deze manier kan de snelheid van verificaties worden verhoogd.</span><span class="sxs-lookup"><span data-stu-id="74212-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="74212-p103">Als deze CNAME-record voor uw domein ontbreekt, wordt door deze toepassingen een standaardeindpunt voor verificatie in de Verenigde Staten gebruikt. Hierdoor verloopt de verificatie mogelijk trager. Als deze CNAME-record niet correct wordt geconfigureerd, bijvoorbeeld wanneer het adres bij **Adres waarnaar wordt verwezen** een typefout bevat, kan er geen verificatie worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="74212-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="74212-114">**Als Office 365 dns-records** van uw domein beheert, Office 365 deze CNAME-record voor u in.</span><span class="sxs-lookup"><span data-stu-id="74212-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="74212-115">**Als u DNS-records voor uw domein** bij uw DNS-host beheert, maakt u deze record zelf door de instructies voor uw [DNS-host te volgen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="74212-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
<span data-ttu-id="74212-116">Als u een Office 365-implementatie plant en meer wilt weten over alle DNS-records die u mogelijk moet toevoegen of bijwerken, leest u deze in [Reference: External Domain Name System records for Office 365](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="74212-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](../../enterprise/external-domain-name-system-records.md).</span></span>
