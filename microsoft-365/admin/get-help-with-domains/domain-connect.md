---
title: Domain Connect gebruiken
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Meer informatie over het werken met registrars met domeinverbinding en uw domein toevoegen aan Microsoft 365.
ms.openlocfilehash: 59e2f94fe83f87a5426064e49f0441356fbd732e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809964"
---
# <a name="using-domain-connect"></a><span data-ttu-id="906df-103">Domain Connect gebruiken</span><span class="sxs-lookup"><span data-stu-id="906df-103">Using Domain Connect</span></span>

 <span data-ttu-id="906df-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="906df-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="906df-105">[Met registrars met domain connect](https://www.domainconnect.org/) u uw domein toevoegen aan Microsoft 365 in een proces in drie stappen dat minuten duurt.</span><span class="sxs-lookup"><span data-stu-id="906df-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="906df-106">In de wizard bevestigen we alleen dat u eigenaar bent van het domein en vervolgens automatisch de records van uw domein instelt, zodat e-mail naar Microsoft 365 en andere Microsoft 365-services, zoals Teams, met uw domein werkt.</span><span class="sxs-lookup"><span data-stu-id="906df-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="906df-107">Start de wizard pas nadat u hebt gecontroleerd of pop-ups zijn toegestaan in uw browser.</span><span class="sxs-lookup"><span data-stu-id="906df-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="906df-108">Domain Connect-registrars die integreren met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="906df-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="906df-109">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="906df-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="906df-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="906df-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="906df-111">Godaddy</span><span class="sxs-lookup"><span data-stu-id="906df-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="906df-112">Wordpress</span><span class="sxs-lookup"><span data-stu-id="906df-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="906df-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="906df-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="906df-114">Mediatempel</span><span class="sxs-lookup"><span data-stu-id="906df-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="906df-115">SecureServer of WildWestDomains (GoDaddy resellers met SecureServer DNS hosting)</span><span class="sxs-lookup"><span data-stu-id="906df-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="906df-116">MadDog Domeinen</span><span class="sxs-lookup"><span data-stu-id="906df-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="906df-117">Goedkope namen</span><span class="sxs-lookup"><span data-stu-id="906df-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="906df-118">Wat gebeurt er met mijn e-mail en website?</span><span class="sxs-lookup"><span data-stu-id="906df-118">What happens to my email and website?</span></span>

<span data-ttu-id="906df-119">Nadat u de installatie hebt voltooid, wordt de MX-record voor uw domein bijgewerkt om naar Microsoft 365 te wijzen en alle e-mail voor uw domein begint naar Microsoft 365 te komen.</span><span class="sxs-lookup"><span data-stu-id="906df-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="906df-120">Zorg dat u in Office 365 gebruikers hebt toegevoegd en postvakken hebt geconfigureerd voor iedereen die een e-mailaccount in uw domein heeft.</span><span class="sxs-lookup"><span data-stu-id="906df-120">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="906df-121">Als uw bedrijf een website heeft, blijft die gewoon werken.</span><span class="sxs-lookup"><span data-stu-id="906df-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="906df-122">De installatiestappen van Domain Connect hebben geen invloed op uw website.</span><span class="sxs-lookup"><span data-stu-id="906df-122">The Domain Connect setup steps don't affect your website.</span></span>
