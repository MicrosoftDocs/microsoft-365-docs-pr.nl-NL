---
title: Domeinverbinding gebruiken
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Meer informatie over het werken met registrars met Domeinconnect en het toevoegen van uw domein aan Microsoft 365.
ms.openlocfilehash: 6a86783ca880f6cb4ea833e4c2b659de4da5e5c1
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/24/2020
ms.locfileid: "43800009"
---
# <a name="using-domain-connect"></a><span data-ttu-id="5f780-103">Domeinverbinding gebruiken</span><span class="sxs-lookup"><span data-stu-id="5f780-103">Using Domain Connect</span></span>

 <span data-ttu-id="5f780-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="5f780-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="5f780-105">[Met](https://www.domainconnect.org/) registrars met Domain Connect u uw domein toevoegen aan Microsoft 365 in een proces in drie stappen dat minuten duurt.</span><span class="sxs-lookup"><span data-stu-id="5f780-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="5f780-106">In de wizard bevestigen we alleen dat u eigenaar bent van het domein en stellen we de records van uw domein automatisch in, zodat e-mail naar Microsoft 365 en andere Microsoft 365-services, zoals Teams, werkt met uw domein.</span><span class="sxs-lookup"><span data-stu-id="5f780-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f780-107">Start de wizard pas nadat u hebt gecontroleerd of pop-ups zijn toegestaan in uw browser.</span><span class="sxs-lookup"><span data-stu-id="5f780-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="5f780-108">Domain Connect-registrars die integreren met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f780-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="5f780-109">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="5f780-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="5f780-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="5f780-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="5f780-111">Godaddy</span><span class="sxs-lookup"><span data-stu-id="5f780-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="5f780-112">Wordpress</span><span class="sxs-lookup"><span data-stu-id="5f780-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="5f780-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="5f780-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="5f780-114">MediaTempel (MediaTempel)</span><span class="sxs-lookup"><span data-stu-id="5f780-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="5f780-115">SecureServer of WildWestDomains (GoDaddy resellers met SecureServer DNS-hosting)</span><span class="sxs-lookup"><span data-stu-id="5f780-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="5f780-116">MadDog Domeinen</span><span class="sxs-lookup"><span data-stu-id="5f780-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="5f780-117">CheapNames CheapNames</span><span class="sxs-lookup"><span data-stu-id="5f780-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="5f780-118">Wat gebeurt er met mijn e-mail en website?</span><span class="sxs-lookup"><span data-stu-id="5f780-118">What happens to my email and website?</span></span>

<span data-ttu-id="5f780-119">Nadat u klaar bent met de installatie, wordt de MX-record voor uw domein bijgewerkt om naar Microsoft 365 te wijzen en alle e-mail voor uw domein wordt naar Microsoft 365 gaan komen.</span><span class="sxs-lookup"><span data-stu-id="5f780-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="5f780-120">Zorg dat u in Office 365 gebruikers hebt toegevoegd en postvakken hebt geconfigureerd voor iedereen die een e-mailaccount in uw domein heeft.</span><span class="sxs-lookup"><span data-stu-id="5f780-120">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="5f780-121">Als uw bedrijf een website heeft, blijft die gewoon werken.</span><span class="sxs-lookup"><span data-stu-id="5f780-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="5f780-122">De installatiestappen Domain Connect hebben geen invloed op uw website.</span><span class="sxs-lookup"><span data-stu-id="5f780-122">The Domain Connect setup steps don't affect your website.</span></span>
