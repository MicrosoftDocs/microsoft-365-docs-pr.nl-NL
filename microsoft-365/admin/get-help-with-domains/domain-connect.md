---
title: Werken met domein verbinding
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Meer informatie over het werken met registratie van domein verbindingen ingeschakeld en uw domein toevoegen aan Microsoft 365.
ms.openlocfilehash: e907317ec5b606c2fe73232a73c9abdfce26feea
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645345"
---
# <a name="using-domain-connect"></a><span data-ttu-id="a0f4a-103">Werken met domein verbinding</span><span class="sxs-lookup"><span data-stu-id="a0f4a-103">Using Domain Connect</span></span>

 <span data-ttu-id="a0f4a-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="a0f4a-105">Met de [met de domein Connect](https://www.domainconnect.org/) ingeschakelde registraties kunt u uw domein toevoegen aan microsoft 365 in drie stappen die een paar minuten duren.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="a0f4a-106">In de wizard wordt bevestigd dat u de eigenaar van het domein bent en worden de records van uw domein automatisch ingesteld, zodat e-mail wordt bezorgd bij Microsoft 365 en andere Microsoft 365-Services, zoals teams, werken met uw domein.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0f4a-107">Start de wizard pas nadat u hebt gecontroleerd of pop-ups zijn toegestaan in uw browser.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="a0f4a-108">Domein Connect-service registraties integreren met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a0f4a-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="a0f4a-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="a0f4a-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="a0f4a-110">Uitvouwen</span><span class="sxs-lookup"><span data-stu-id="a0f4a-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="a0f4a-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="a0f4a-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="a0f4a-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="a0f4a-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="a0f4a-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="a0f4a-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="a0f4a-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="a0f4a-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="a0f4a-115">SecureServer of WildWestDomains (GoDaddy resellers met SecureServer DNS-hosting)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="a0f4a-116">MadDog-domeinen</span><span class="sxs-lookup"><span data-stu-id="a0f4a-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="a0f4a-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="a0f4a-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="a0f4a-118">Wat gebeurt er met mijn e-mail en website?</span><span class="sxs-lookup"><span data-stu-id="a0f4a-118">What happens to my email and website?</span></span>

<span data-ttu-id="a0f4a-119">Wanneer u klaar bent met de installatie, wordt de MX-record voor uw domein bijgewerkt zodat deze verwijst naar Microsoft 365 en alle e-mailberichten voor uw domein komen te staan bij Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="a0f4a-120">Zorg ervoor dat u gebruikers hebt toegevoegd en postvakken hebt ingesteld in Microsoft 365 voor iedereen die e-mail op uw domein ontvangt.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="a0f4a-121">Als uw bedrijf een website heeft, blijft die gewoon werken.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="a0f4a-122">De installatiestappen voor domein verbinding hebben geen invloed op uw website.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-122">The Domain Connect setup steps don't affect your website.</span></span>
