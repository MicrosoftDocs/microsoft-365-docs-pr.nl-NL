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
description: Schakel het delen van agenda's in Microsoft 365 beheercentrum in, zodat gebruikers hun agenda's kunnen delen met iedereen binnen of buiten de organisatie.
ms.openlocfilehash: 6f4c215403e16ac6658619e50e6115606f106397
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582714"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="4ed18-103">Agenda’s delen met externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="4ed18-103">Share calendars with external users</span></span>

<span data-ttu-id="4ed18-104">Het is soms nodig dat uw gebruikers vergaderingen plannen met personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4ed18-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="4ed18-105">Als u het zoeken naar algemene vergadertijden wilt vereenvoudigen, Microsoft 365 u agenda's beschikbaar maken voor deze personen.</span><span class="sxs-lookup"><span data-stu-id="4ed18-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="4ed18-106">Dit zijn personen die vrije en drukke tijden moeten zien voor gebruikers in uw organisatie, maar geen gebruikersaccounts hebben voor uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="4ed18-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="4ed18-107">U kunt delen van agenda's inschakelen voor alle gebruikers in uw organisatie in Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="4ed18-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4ed18-108">Wanneer delen is ingeschakeld, kunnen uw gebruikers Outlook Web App agenda's delen met iedereen binnen of buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="4ed18-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="4ed18-109">Personen binnen de organisatie kunnen de gedeelde agenda samen met hun eigen agenda bekijken.</span><span class="sxs-lookup"><span data-stu-id="4ed18-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="4ed18-110">Mensen buiten de organisatie ontvangen een URL die ze kunnen gebruiken om de agenda te bekijken.</span><span class="sxs-lookup"><span data-stu-id="4ed18-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="4ed18-111">Gebruikers in uw organisatie bepalen wanneer ze willen delen en hoeveel ze moeten delen.</span><span class="sxs-lookup"><span data-stu-id="4ed18-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="4ed18-112">Als u agenda's wilt delen met een organisatie die Exchange Server 2013 (een on-premises oplossing) gebruikt, moet de Exchange-beheerder een verificatierelatie met de cloud instellen.</span><span class="sxs-lookup"><span data-stu-id="4ed18-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="4ed18-113">Dit wordt federatie genoemd en moet voldoen aan minimale softwarevereisten.</span><span class="sxs-lookup"><span data-stu-id="4ed18-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="4ed18-114">Zie [Delen](/exchange/sharing-exchange-2013-help) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4ed18-114">See [Sharing](/exchange/sharing-exchange-2013-help) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="4ed18-115">Agenda delen inschakelen via het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="4ed18-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="4ed18-116">Ga in het beheercentrum naar **Instellingen** \> **Organisatie Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="4ed18-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="4ed18-117">Selecteer agenda **op het** tabblad **Services.**</span><span class="sxs-lookup"><span data-stu-id="4ed18-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="4ed18-118">Kies op **de** pagina Agenda of u wilt dat gebruikers hun agenda's kunnen delen met personen buiten uw organisatie die Microsoft 365 of Exchange.</span><span class="sxs-lookup"><span data-stu-id="4ed18-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="4ed18-119">Kies of u anonieme gebruikers (gebruikers zonder referenties) toegang wilt geven tot agenda's via een e-mailuitnodiging.</span><span class="sxs-lookup"><span data-stu-id="4ed18-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="4ed18-120">Kies welk type agendagegevens u beschikbaar wilt maken voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="4ed18-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="4ed18-121">U kunt alle gegevens toestaan of beperken tot alleen tijd of tijd, onderwerp en locatie.</span><span class="sxs-lookup"><span data-stu-id="4ed18-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="4ed18-122">Mensen uitnodigen voor toegang tot agenda's</span><span class="sxs-lookup"><span data-stu-id="4ed18-122">Invite people to access calendars</span></span>

<span data-ttu-id="4ed18-123">Wanneer delen is ingeschakeld, kunnen agenda-eigenaren uitnodigingen uitbreiden naar specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="4ed18-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="4ed18-124">Zie [Uw agenda delen in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="4ed18-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>

## <a name="related-content"></a><span data-ttu-id="4ed18-125">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="4ed18-125">Related content</span></span>

<span data-ttu-id="4ed18-126">[Extern delen in- of uitschakelen voor een site](/sharepoint/change-external-sharing-site) (artikel)</span><span class="sxs-lookup"><span data-stu-id="4ed18-126">[Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site) (article)</span></span>

<span data-ttu-id="4ed18-127">[Overzicht van het Microsoft 365-beheercentrum](../../business-video/admin-center-overview.md) (video)</span><span class="sxs-lookup"><span data-stu-id="4ed18-127">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)</span></span>

<span data-ttu-id="4ed18-128">[E-mail en agenda's beheren (koppelingspagina)](../email/index.yml)</span><span class="sxs-lookup"><span data-stu-id="4ed18-128">[Manage email and calendars](../email/index.yml) (link page)</span></span>