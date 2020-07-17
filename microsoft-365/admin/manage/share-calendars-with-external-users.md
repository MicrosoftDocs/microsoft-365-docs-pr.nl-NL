---
title: Agenda's delen met externe gebruikers
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: "Meer informatie over hoe u uw gebruikers hun agenda's laten delen met externe gebruikers voor vergaderingen en afspraken. "
ms.openlocfilehash: 972e8376ae3d71b11205d4a6611dc6900c063ffe
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780059"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="c2c1f-103">Agenda’s delen met externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="c2c1f-103">Share calendars with external users</span></span>

<span data-ttu-id="c2c1f-104">Het is vaak noodzakelijk om vergaderingen met mensen buiten uw organisatie te plannen.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="c2c1f-105">Om het proces van het vinden van onderling aanvaardbare vergadertijden te vereenvoudigen, stelt Microsoft 365 u in staat om agenda's beschikbaar te maken voor "externe gebruikers", degenen die vrije/drukke tijd moeten zien, maar geen gebruikersaccounts hebben voor uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="c2c1f-106">Het delen van agenda's is een algemene instelling, wat betekent dat u, de beheerder, deze inschakelen voor alle gebruikers in de tenant.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="c2c1f-107">Nadat delen is ingeschakeld, kunnen gebruikers Outlook Web App gebruiken om hun agenda's te delen met iemand binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="c2c1f-108">Mensen binnen de organisatie kunnen de gedeelde agenda naast die van henzelf bekijken.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="c2c1f-109">Mensen buiten de organisatie ontvangen een URL die ze kunnen gebruiken om de agenda te bekijken.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="c2c1f-110">Gebruikers beslissen wanneer ze willen delen, hoe veel ze willen delen en wanneer ze hun agenda privé willen houden.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2c1f-p103">Als u agenda's wilt delen met een organisatie die Exchange Server 2013 (een on-premises oplossing) gebruikt, moet de Exchange-beheerder een verificatierelatie met de cloud instellen. Dit wordt ook wel 'federatie' genoemd en moet voldoen aan de minimale softwarevereisten. Zie [Delen](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="c2c1f-114">Agenda-delen inschakelen met het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="c2c1f-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c2c1f-115">Ga in het beheercentrum naar **Settings** \> **Instellingen Organisatie-instellingen**.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-115">In the admin center, go to **Settings** \> **Org Settings**.</span></span> 
    
2. <span data-ttu-id="c2c1f-116">Selecteer **Agenda**op het tabblad **Services** .</span><span class="sxs-lookup"><span data-stu-id="c2c1f-116">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="c2c1f-117">Kies op de **pagina Agenda** die wordt geopend of u uw gebruikers hun agenda's wilt laten delen met mensen buiten uw organisatie die Microsoft 365 of Exchange hebben.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="c2c1f-118">Kies of u anonieme gebruikers (gebruikers zonder aanmeldingsreferenties) toegang wilt geven tot agenda's via een e-mailuitnodiging.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="c2c1f-119">Kies welk type agenda-informatie beschikbaar moet worden gesteld aan gebruikers.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="c2c1f-120">U alle informatie toestaan, of beperken tot tijd alleen of tijd, onderwerp en locatie alleen.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="c2c1f-121">Mensen uitnodigen voor toegang tot agenda's</span><span class="sxs-lookup"><span data-stu-id="c2c1f-121">Invite people to access calendars</span></span>

<span data-ttu-id="c2c1f-p105">Nadat delen voor de tenant is ingeschakeld, kunnen eigenaren van agenda's uitnodigingen uitbreiden tot specifieke gebruikers. Zie [Uw agenda delen in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c2c1f-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span> 
  
