---
title: Agenda's delen met externe gebruikers
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: "Meer informatie over hoe u uw gebruikers hun agenda's laten delen met externe gebruikers voor vergaderingen en afspraken. "
ms.openlocfilehash: bd297fc2d684357d0500495e5a8263e5279efa39
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628038"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="9fc45-103">Agenda’s delen met externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="9fc45-103">Share calendars with external users</span></span>

<span data-ttu-id="9fc45-104">Het is vaak noodzakelijk om vergaderingen met mensen buiten uw organisatie te plannen.</span><span class="sxs-lookup"><span data-stu-id="9fc45-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="9fc45-105">Om het proces van het vinden van wederzijds aangename vergadertijden te vereenvoudigen, stelt Microsoft 365 u in staat om agenda's beschikbaar te maken voor 'externe gebruikers', degenen die vrije/drukke tijd moeten zien, maar geen gebruikersaccounts hebben voor uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="9fc45-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="9fc45-106">Agendadelen is een algemene instelling, wat betekent dat u, de beheerder, deze inschakelen voor alle gebruikers in de tenant.</span><span class="sxs-lookup"><span data-stu-id="9fc45-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="9fc45-107">Nadat delen is ingeschakeld, kunnen gebruikers Outlook Web App gebruiken om hun agenda's te delen met iemand binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="9fc45-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="9fc45-108">Mensen binnen de organisatie kunnen de gedeelde agenda naast die van henzelf bekijken.</span><span class="sxs-lookup"><span data-stu-id="9fc45-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="9fc45-109">Mensen buiten de organisatie ontvangen een URL die ze kunnen gebruiken om de agenda te bekijken.</span><span class="sxs-lookup"><span data-stu-id="9fc45-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="9fc45-110">Gebruikers beslissen wanneer ze willen delen, hoe veel ze willen delen en wanneer ze hun agenda privé willen houden.</span><span class="sxs-lookup"><span data-stu-id="9fc45-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fc45-p103">Als u agenda's wilt delen met een organisatie die Exchange Server 2013 (een on-premises oplossing) gebruikt, moet de Exchange-beheerder een verificatierelatie met de cloud instellen. Dit wordt ook wel 'federatie' genoemd en moet voldoen aan de minimale softwarevereisten. Zie [Delen](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9fc45-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="9fc45-114">Agendadelen inschakelen met het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="9fc45-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="9fc45-115">Ga in het beheercentrum naar de pagina **Instellingenservices** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">& invoegingen.</a></span><span class="sxs-lookup"><span data-stu-id="9fc45-115">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.</span></span> 
    
  
2. <span data-ttu-id="9fc45-116">Selecteer **Agenda**op de pagina **Invoegtoepassing &amp; Services** .</span><span class="sxs-lookup"><span data-stu-id="9fc45-116">On the **Services &amp; add-ins** page, select **Calendar**.</span></span>
  
3. <span data-ttu-id="9fc45-117">Kies op de **agendapagina** die wordt geopend of u uw gebruikers hun agenda's wilt laten delen met mensen buiten uw organisatie die Microsoft 365 of Exchange hebben.</span><span class="sxs-lookup"><span data-stu-id="9fc45-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="9fc45-118">Kies of u anonieme gebruikers (gebruikers zonder aanmeldingsgegevens) toegang wilt geven tot agenda's via een e-mailuitnodiging.</span><span class="sxs-lookup"><span data-stu-id="9fc45-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="9fc45-119">Kies welk type agenda-informatie u beschikbaar wilt maken voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9fc45-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="9fc45-120">U alle informatie toestaan of beperken tot alleen tijd of tijd, onderwerp en locatie.</span><span class="sxs-lookup"><span data-stu-id="9fc45-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="9fc45-121">Mensen uitnodigen voor toegang tot agenda's</span><span class="sxs-lookup"><span data-stu-id="9fc45-121">Invite people to access calendars</span></span>

<span data-ttu-id="9fc45-p105">Nadat delen voor de tenant is ingeschakeld, kunnen eigenaren van agenda's uitnodigingen uitbreiden tot specifieke gebruikers. Zie [Uw agenda delen in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="9fc45-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions.</span></span> 
  

