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
description: Meer informatie over hoe u uw gebruikers hun agenda's kunt laten delen met externe gebruikers voor vergaderingen en afspraken.
ms.openlocfilehash: 8204dc025f843953af13cba58fa0cf2e4d76de45
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760052"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="09bee-103">Agenda’s delen met externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="09bee-103">Share calendars with external users</span></span>

<span data-ttu-id="09bee-104">Het kan soms voorkomen dat uw gebruikers vergaderingen plannen met personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="09bee-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="09bee-105">Met Microsoft 365 kunt u het zoeken in agenda's voor deze personen vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="09bee-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="09bee-106">Dit zijn personen die beschikbaarheidsinfo moeten zien voor gebruikers in uw organisatie, maar geen gebruikersaccounts voor uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="09bee-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="09bee-107">U kunt het delen van agenda's inschakelen voor alle gebruikers in uw organisatie in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="09bee-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="09bee-108">Wanneer delen is ingeschakeld, kunnen gebruikers met Outlook Web App hun agenda's delen met iedereen binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="09bee-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="09bee-109">Personen binnen de organisatie kunnen de gedeelde agenda samen met hun eigen agenda weergeven.</span><span class="sxs-lookup"><span data-stu-id="09bee-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="09bee-110">Mensen buiten de organisatie ontvangen een URL die ze kunnen gebruiken om de agenda te bekijken.</span><span class="sxs-lookup"><span data-stu-id="09bee-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="09bee-111">Gebruikers in uw organisatie bepalen wanneer ze delen en wat u wilt delen.</span><span class="sxs-lookup"><span data-stu-id="09bee-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="09bee-112">Als u agenda's wilt delen met een organisatie die Exchange Server 2013 (een on-premises oplossing) gebruikt, moet de Exchange-beheerder een verificatierelatie met de cloud instellen.</span><span class="sxs-lookup"><span data-stu-id="09bee-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="09bee-113">Dit wordt Federatie genoemd en moet voldoen aan de minimale softwarevereisten.</span><span class="sxs-lookup"><span data-stu-id="09bee-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="09bee-114">Zie [Delen](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="09bee-114">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="09bee-115">Agenda delen inschakelen met het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="09bee-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="09bee-116">Ga in het Beheercentrum naar **instellingen** \> **organisatie-instellingen**.</span><span class="sxs-lookup"><span data-stu-id="09bee-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="09bee-117">Selecteer **agenda** op het tabblad **Services** .</span><span class="sxs-lookup"><span data-stu-id="09bee-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="09bee-118">Kies op de pagina **agenda** of gebruikers hun agenda willen laten delen met personen buiten uw organisatie die microsoft 365 of Exchange hebben.</span><span class="sxs-lookup"><span data-stu-id="09bee-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="09bee-119">Kies of u anonieme gebruikers (gebruikers zonder referenties) toegang wilt geven tot agenda's via een e-mail uitnodiging.</span><span class="sxs-lookup"><span data-stu-id="09bee-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="09bee-120">Kies het type agenda-informatie dat u beschikbaar wilt maken voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="09bee-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="09bee-121">U kunt alle gegevens toestaan of beperken tot alleen tijd of alleen tijd, onderwerp en locatie.</span><span class="sxs-lookup"><span data-stu-id="09bee-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="09bee-122">Mensen uitnodigen voor toegang tot agenda's</span><span class="sxs-lookup"><span data-stu-id="09bee-122">Invite people to access calendars</span></span>

<span data-ttu-id="09bee-123">Wanneer delen is ingeschakeld, kunnen agenda-eigenaren uitnodigingen voor specifieke gebruikers verlengen.</span><span class="sxs-lookup"><span data-stu-id="09bee-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="09bee-124">Zie [Uw agenda delen in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="09bee-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>