---
title: Microsoft Bookings in- of uitschakelen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Lees hoe u toegang krijgt tot Microsoft Bookings in Microsoft 365.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913764"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="53513-103">Microsoft Bookings in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="53513-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="53513-104">Boekingen kunnen worden in- of uitgeschakeld voor uw hele organisatie of voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="53513-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="53513-105">Wanneer u Bookings voor gebruikers int, kunnen ze een bookings-pagina maken, een agenda maken en andere personen toestaan om tijd met hen te boeken.</span><span class="sxs-lookup"><span data-stu-id="53513-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="53513-106">De beheerbesturingselementen die in deze secties worden beschreven, zijn niet beschikbaar voor Office 365 Beheerd door klanten van 21Vianet (China).</span><span class="sxs-lookup"><span data-stu-id="53513-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="53513-107">Bookings in- of uitschakelen voor uw organisatie met behulp van het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="53513-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="53513-108">Meld u als globale beheerder aan bij het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="53513-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="53513-109">Ga in het beheercentrum naar  **Instellingen**   \> **Organisatie-instellingen** en selecteer **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="53513-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="53513-110">Schakel het selectievakje in voor **Toestaan dat uw organisatie Bookings** gebruikt om Bookings voor uw organisatie in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="53513-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="53513-111">Als u Bookings uit schakelt, wordt alle toegang tot de service uitgeschakeld, inclusief het maken en beheren van Bookings-pagina's.</span><span class="sxs-lookup"><span data-stu-id="53513-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="53513-112">Selecteer **Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="53513-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="53513-113">Bookings in- of uitschakelen voor uw organisatie met PowerShell</span><span class="sxs-lookup"><span data-stu-id="53513-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="53513-114">Als u Bookings voor uw organisatie wilt in- of uitschakelen met behulp van de PowerShell-cmdlet [Set-OrganizationConfig,](/powershell/module/exchange/set-organizationconfig)Verbinding maken met [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en de volgende opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="53513-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="53513-115">Bookings in- of uitschakelen voor individuele gebruikers</span><span class="sxs-lookup"><span data-stu-id="53513-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="53513-116">U kunt Bookings uitschakelen voor afzonderlijke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="53513-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="53513-117">Ga naar het Microsoft 365-beheercentrum en selecteer **gebruikers** \> **actieve gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="53513-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="53513-118">Selecteer de gewenste gebruiker en selecteer **vervolgens Licenties en apps.**</span><span class="sxs-lookup"><span data-stu-id="53513-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="53513-119">Vouw **Apps uit** en het selectievakje voor Microsoft Bookings uit.</span><span class="sxs-lookup"><span data-stu-id="53513-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="53513-120">Goedkeuring van personeel vereisen voordat u gratis/drukke informatie deelt</span><span class="sxs-lookup"><span data-stu-id="53513-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="53513-121">Beheerders kunnen werknemers in hun organisatie verplichten zich aan te geven voordat hun beschikbaarheidsgegevens worden gedeeld via Bookings en voordat ze kunnen worden geboekt via een boekingspagina.</span><span class="sxs-lookup"><span data-stu-id="53513-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="53513-122">Deze instelling is beschikbaar in het Microsoft 365-beheercentrum onder **Instellingen** \> **Instellingen** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="53513-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="53513-123">Wanneer deze instelling is ingeschakeld, vinden werknemers die zijn toegevoegd als personeel in boekingsagenda's een koppeling Goedkeuren/weigeren in de e-mailmelding die ze ontvangen.</span><span class="sxs-lookup"><span data-stu-id="53513-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="53513-124">Deze functie wordt geleidelijk wereldwijd uitgerold voor Klanten van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53513-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="53513-125">Als u deze optie niet ziet in het Microsoft 365-beheercentrum, gaat u snel terug.</span><span class="sxs-lookup"><span data-stu-id="53513-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="53513-126">Opties voor sociaal delen blokkeren</span><span class="sxs-lookup"><span data-stu-id="53513-126">Block social sharing options</span></span>

<span data-ttu-id="53513-127">Beheerders kunnen bepalen hoe boekingspagina's worden gedeeld op sociale netwerken.</span><span class="sxs-lookup"><span data-stu-id="53513-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="53513-128">Deze instelling is beschikbaar in het Microsoft 365-beheercentrum onder **Instellingen** \> **Instellingen** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="53513-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="53513-129">Deze functie wordt geleidelijk wereldwijd uitgerold voor Klanten van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53513-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="53513-130">Als u deze optie niet ziet in het Microsoft 365-beheercentrum, gaat u snel terug.</span><span class="sxs-lookup"><span data-stu-id="53513-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="53513-131">Alleen geselecteerde gebruikers toestaan Bookings-agenda's te maken</span><span class="sxs-lookup"><span data-stu-id="53513-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="53513-132">Met beleidsbeperkingen kunt u voorkomen dat gebruikers met een licentie Bookings-agenda's kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="53513-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="53513-133">U moet eerst Bookings inschakelen voor uw hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="53513-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="53513-134">Alle gebruikers in uw organisatie hebben Bookings-licenties, maar alleen gebruikers die in het beleid zijn opgenomen, kunnen Bookings-agenda's maken en hebben volledige controle over wie toegang heeft tot de agenda's die ze maken.</span><span class="sxs-lookup"><span data-stu-id="53513-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="53513-135">Gebruikers die in dit beleid zijn opgenomen, kunnen nieuwe Bookings-agenda's maken en kunnen als personeel in elke capaciteit (inclusief de beheerdersrol) worden toegevoegd aan bestaande Bookings-agenda's.</span><span class="sxs-lookup"><span data-stu-id="53513-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="53513-136">Gebruikers die niet in dit beleid zijn opgenomen, kunnen geen nieuwe Bookings-agenda's maken en ontvangen een foutbericht als ze dit proberen.</span><span class="sxs-lookup"><span data-stu-id="53513-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="53513-137">U moet de volgende opdrachten uitvoeren met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53513-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="53513-138">Zie Verbinding maken met Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)voor meer informatie over het uitvoeren van Exchange Online-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="53513-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53513-139">In de onderstaande stappen wordt ervan uitgenomen dat er geen ander OWA-postvakbeleid (Outlook Web App) is gemaakt in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="53513-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="53513-140">Maak een nieuw postvakbeleid voor gebruikers die Bookings-agenda's mogen maken.</span><span class="sxs-lookup"><span data-stu-id="53513-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="53513-141">(Het maken van een Boekingskalender is standaard toegestaan door nieuw postvakbeleid.)</span><span class="sxs-lookup"><span data-stu-id="53513-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="53513-142">Zie [New-OwaMailboxPolicy voor meer informatie.](/powershell/module/exchange/new-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="53513-142">For more information, see [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="53513-143">Wijs dit beleid toe aan de relevante gebruikers door deze opdracht uit te voeren voor elke gebruiker die u toestemming wilt geven om Bookings-agenda's te maken.</span><span class="sxs-lookup"><span data-stu-id="53513-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="53513-144">Zie [Set-CASMailbox voor](/powershell/module/exchange/set-casmailbox)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="53513-144">For more information, see [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="53513-145">Optioneel: Voer deze opdracht uit als u Bookings wilt uitschakelen voor alle andere gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="53513-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="53513-146">Zie [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="53513-146">For more information, see [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="53513-147">Zie de volgende onderwerpen voor meer informatie over OWA-postvakbeleid:</span><span class="sxs-lookup"><span data-stu-id="53513-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="53513-148">Een beleid voor postvak in Outlook op het web maken in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="53513-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="53513-149">Een beleid voor outlook op het webpostvak toepassen of verwijderen op een postvak in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="53513-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)