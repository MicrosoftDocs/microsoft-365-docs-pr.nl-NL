---
title: Microsoft bookings in-of uitschakelen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Meer informatie over het verkrijgen van toegang tot Microsoft bookings in Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126589"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="01fde-103">Microsoft bookings in-of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="01fde-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="01fde-104">U kunt bookings in-of uitschakelen voor uw gehele organisatie of voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="01fde-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="01fde-105">Wanneer u Bookings voor gebruikers inschakelt, kan hij of zij een Bookings pagina maken, een agenda maken en andere personen de tijd boek stellen.</span><span class="sxs-lookup"><span data-stu-id="01fde-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="01fde-106">De besturingselementen voor beheerders die in deze secties worden beschreven, zijn niet beschikbaar voor Office 365, beheerd door 21Vianet (China)-klanten.</span><span class="sxs-lookup"><span data-stu-id="01fde-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="01fde-107">Bookings in-of uitschakelen voor uw organisatie met behulp van het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="01fde-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="01fde-108">Meld u aan bij het Microsoft 365-Beheercentrum als globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="01fde-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="01fde-109">Ga in het Beheercentrum naar  **instellingen**   \> **org** en selecteer **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="01fde-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="01fde-110">Schakel het selectievakje in om **ervoor te zorgen dat uw organisatie** reserveringen in-of uitschakelt voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="01fde-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="01fde-111">Als u reserveringen uitschakelt, wordt alle toegang tot de service, waaronder het maken en beheren van Bookings pagina's, uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="01fde-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="01fde-112">Selecteer **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="01fde-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="01fde-113">Bookings in-of uitschakelen voor uw organisatie met behulp van PowerShell</span><span class="sxs-lookup"><span data-stu-id="01fde-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="01fde-114">[Maak verbinding met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) en voer de volgende opdracht uit om bookings in of uit te schakelen voor uw organisatie met behulp van de PowerShell [-cmdlet Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig).</span><span class="sxs-lookup"><span data-stu-id="01fde-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="01fde-115">Bookings uitschakelen voor individuele gebruikers</span><span class="sxs-lookup"><span data-stu-id="01fde-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="01fde-116">U kunt Bookings uitschakelen voor individuele gebruikers.</span><span class="sxs-lookup"><span data-stu-id="01fde-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="01fde-117">Ga naar het Microsoft 365-Beheercentrum en selecteer **gebruikers** met \> **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="01fde-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="01fde-118">Selecteer de gewenste gebruiker en selecteer vervolgens **licenties en apps**.</span><span class="sxs-lookup"><span data-stu-id="01fde-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="01fde-119">Vouw **apps** uit en wis het selectievakje voor Microsoft bookings.</span><span class="sxs-lookup"><span data-stu-id="01fde-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="01fde-120">Goedkeuring van personeelsleden vereisen voordat beschikbaarheidsinfo wordt gedeeld</span><span class="sxs-lookup"><span data-stu-id="01fde-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="01fde-121">Beheerders kunnen werknemers in hun organisatie vragen zich aan te melden voordat ze hun beschikbaarheidsgegevens delen via Bookings en voordat ze kunnen worden bookable via een reserverings pagina.</span><span class="sxs-lookup"><span data-stu-id="01fde-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="01fde-122">Deze instelling is beschikbaar in het Microsoft 365-Beheercentrum onder **instellingen voorinstellingen** \> **Settings** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="01fde-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="01fde-123">Wanneer deze instelling is ingeschakeld, vinden werknemers die zijn toegevoegd als medewerkers in de boekings agenda's, een koppeling goedkeuren/weigeren in de e-mail melding die ze ontvangen.</span><span class="sxs-lookup"><span data-stu-id="01fde-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="01fde-124">Deze functie wordt geleidelijk ter wereld ingevoerd voor klanten van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01fde-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="01fde-125">Als u deze optie niet ziet in het Microsoft 365-Beheercentrum, kom dan binnenkort terug.</span><span class="sxs-lookup"><span data-stu-id="01fde-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="01fde-126">Opties voor sociale delen blokkeren</span><span class="sxs-lookup"><span data-stu-id="01fde-126">Block social sharing options</span></span>

<span data-ttu-id="01fde-127">Beheerders kunnen bepalen hoe boekings pagina's worden gedeeld op sociale netwerken.</span><span class="sxs-lookup"><span data-stu-id="01fde-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="01fde-128">Deze instelling is beschikbaar in het Microsoft 365-Beheercentrum onder **instellingen voorinstellingen** \> **Settings** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="01fde-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="01fde-129">Deze functie wordt geleidelijk ter wereld ingevoerd voor klanten van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01fde-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="01fde-130">Als u deze optie niet ziet in het Microsoft 365-Beheercentrum, kom dan binnenkort terug.</span><span class="sxs-lookup"><span data-stu-id="01fde-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="01fde-131">Alleen geselecteerde gebruikers toestaan om boekings agenda's te maken</span><span class="sxs-lookup"><span data-stu-id="01fde-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="01fde-132">Door beleidsbeperkingen te gebruiken, kunt u instellen dat gebruikers met een licentie geen Bookings-agenda's kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="01fde-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="01fde-133">U dient eerst Bookings te activeren voor de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="01fde-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="01fde-134">Alle gebruikers in uw organisatie hebben wel een boekings licentie, maar alleen de gebruikers in het beleid kunnen Bookings-agenda's maken en volledig bepalen wie er toegang heeft tot de agenda's die ze maken.</span><span class="sxs-lookup"><span data-stu-id="01fde-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="01fde-135">Gebruikers die deel uitmaken van dit beleid, kunnen nieuwe boekings agenda's maken en kunnen als werknemers aan de gewenste capaciteit (waaronder de rol van de beheerder) worden toegevoegd aan bestaande Bookings-agenda's.</span><span class="sxs-lookup"><span data-stu-id="01fde-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="01fde-136">Gebruikers die geen deel uitmaken van dit beleid, kunnen geen nieuwe boekings agenda's maken en er wordt een foutbericht weergegeven wanneer ze dit proberen.</span><span class="sxs-lookup"><span data-stu-id="01fde-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="01fde-137">U moet de volgende opdrachten uitvoeren met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01fde-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="01fde-138">Zie [verbinding maken met Exchange Online PowerShell (verbinding maken met Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)) voor meer informatie over het uitvoeren van cmdlets voor Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="01fde-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01fde-139">In de volgende stappen wordt ervan uitgegaan dat er geen ander postvak beleid van Outlook Web app (OWA) in uw organisatie is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="01fde-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="01fde-140">Maak een nieuw postvak beleid voor gebruikers die toestemming hebben om Bookings-agenda's te maken.</span><span class="sxs-lookup"><span data-stu-id="01fde-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="01fde-141">(Het maken van een agenda via Bookings is standaard toegestaan voor nieuw postvak beleid.)</span><span class="sxs-lookup"><span data-stu-id="01fde-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="01fde-142">Zie [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="01fde-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="01fde-143">Wijs dit beleid toe aan de relevante gebruikers door deze opdracht uit te voeren voor elke gebruiker die u wilt machtigen om Bookings-agenda's te maken.</span><span class="sxs-lookup"><span data-stu-id="01fde-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="01fde-144">Zie [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="01fde-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="01fde-145">Optioneel: Voer deze opdracht uit als u de reserveringen wilt uitschakelen voor alle andere gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="01fde-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="01fde-146">Zie [set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="01fde-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="01fde-147">Raadpleeg de volgende onderwerpen voor meer informatie over het gebruik van OWA-postvak beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="01fde-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="01fde-148">Een postvak beleid voor de webversie van Outlook maken in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="01fde-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="01fde-149">Beleidsregels voor het postvak van de webversie van Outlook op een postvak in Exchange Online toepassen of verwijderen</span><span class="sxs-lookup"><span data-stu-id="01fde-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
