---
title: E-mailgebruikers beheren in standalone EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Meer informatie over het beheren van e-mailgebruikers in Exchange Online Protection (EOP), inclusief het gebruik van directorysynchronisatie, EAC en PowerShell om gebruikers te beheren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d82170499bcfa6465164ca2644eea43c2558ad18
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616832"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="5cd2f-103">E-mailgebruikers beheren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="5cd2f-103">Manage mail users in standalone EOP</span></span>

<span data-ttu-id="5cd2f-104">In zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken zijn e-mailgebruikers het fundamentele type gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="5cd2f-105">Een e-mailgebruiker heeft accountreferenties in uw zelfstandige EOP-organisatie en heeft toegang tot bronnen (machtigingen hebben toegewezen).</span><span class="sxs-lookup"><span data-stu-id="5cd2f-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="5cd2f-106">Het e-mailadres van een e-mailgebruiker is extern (bijvoorbeeld in uw on-premises e-mailomgeving).</span><span class="sxs-lookup"><span data-stu-id="5cd2f-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="5cd2f-107">Wanneer u een e-mailgebruiker maakt, is het bijbehorende gebruikersaccount beschikbaar in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5cd2f-108">Wanneer u een gebruikersaccount maakt in het Microsoft 365-beheercentrum, u dat account niet gebruiken om een e-mailgebruiker te maken.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="5cd2f-109">De aanbevolen methode voor het maken en beheren van e-mailgebruikers in standalone EOP is het gebruik van adreslijstsynchronisatie zoals beschreven in de [mapsynchronisatie gebruiken om e-mailgebruikers](#use-directory-synchronization-to-manage-mail-users) later in dit onderwerp te beheren.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="5cd2f-110">Voor zelfstandige EOP-organisaties met een klein aantal gebruikers u e-mailgebruikers toevoegen en beheren in het Exchange-beheercentrum (EAC) of in standalone EOP PowerShell zoals beschreven in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5cd2f-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="5cd2f-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5cd2f-112">Zie [Exchange-beheercentrum in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum (EAC) wilt openen.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="5cd2f-113">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5cd2f-114">Wanneer u e-mailgebruikers maakt in EOP PowerShell, u throttling tegenkomen.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="5cd2f-115">Ook gebruiken de EOP PowerShell-cmdlets een batchverwerkingsmethode die resulteert in een propagatievertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="5cd2f-116">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="5cd2f-117">In het bijzonder hebt u de rollen voor het maken van e-mailontvangers (maken) en e-mailontvangers (wijzigen) nodig, die standaard zijn toegewezen aan de rolgroepen OrganizationManagement (global admins) en RecipientManagement.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="5cd2f-118">Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de EAC voor meer informatie [de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="5cd2f-119">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="5cd2f-120">Heb je problemen?</span><span class="sxs-lookup"><span data-stu-id="5cd2f-120">Having problems?</span></span> <span data-ttu-id="5cd2f-121">Vraag om hulp in de Exchange-forums.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="5cd2f-122">Ga naar het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="5cd2f-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="5cd2f-123">Het Exchange-beheercentrum gebruiken om e-mailgebruikers te beheren</span><span class="sxs-lookup"><span data-stu-id="5cd2f-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="5cd2f-124">De EAC gebruiken om e-mailgebruikers te maken</span><span class="sxs-lookup"><span data-stu-id="5cd2f-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="5cd2f-125">Ga in de EAC naar **Contactpersonen voor geadresseerden** \> **Contacts**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="5cd2f-126">Klik op **Nieuw** ![ pictogram ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="5cd2f-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="5cd2f-127">Configureer de volgende instellingen op de **pagina Nieuwe e-mailgebruikers** die wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="5cd2f-128">Instellingen die zijn gemarkeerd met een <sup>\*</sup> zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="5cd2f-129">**Voornaam**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-129">**First name**</span></span>

   - <span data-ttu-id="5cd2f-130">**Initialen**: De middelste initiaal van de persoon.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="5cd2f-131">**Achternaam**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-131">**Last name**</span></span>

   - <span data-ttu-id="5cd2f-132"><sup>\*</sup>**Weergavenaam**: In dit vak worden standaard de waarden weergegeven uit de vakken **Voornaam,** **Initialen**en **Achternaam.**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="5cd2f-133">U deze waarde accepteren of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-133">You can accept this value or change it.</span></span> <span data-ttu-id="5cd2f-134">De waarde moet uniek zijn en heeft een maximale lengte van 64 tekens.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="5cd2f-135"><sup>\*</sup>**Alias**: Voer een unieke alias in met maximaal 64 tekens voor de gebruiker</span><span class="sxs-lookup"><span data-stu-id="5cd2f-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="5cd2f-136">**Extern e-mailadres**: Voer het e-mailadres van de gebruiker in.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="5cd2f-137">Het domein moet extern zijn aan uw cloudorganisatie.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="5cd2f-138"><sup>\*</sup>**Gebruikersnaam**: Voer het account in dat de persoon gebruikt om zich aan te melden bij de service.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="5cd2f-139">De gebruikersnaam bestaat uit een gebruikersnaam aan de linkerkant van het at (@) symbool (@) en een domein aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="5cd2f-140"><sup>\*</sup>**Nieuw wachtwoord** en <sup>\*</sup> **Wachtwoord bevestigen**: Voer het accountwachtwoord in en voer deze opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="5cd2f-141">Controleer of het wachtwoord voldoet aan de vereisten voor wachtwoordduur, complexiteit en geschiedenis van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="5cd2f-142">Wanneer u klaar bent, klikt u op **Opslaan** om de e-mailgebruiker te maken.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="5cd2f-143">De EAC gebruiken om e-mailgebruikers te wijzigen</span><span class="sxs-lookup"><span data-stu-id="5cd2f-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="5cd2f-144">Ga in de EAC naar **Contactpersonen voor ontvangers** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="5cd2f-145">Selecteer de e-mailgebruiker die u wilt wijzigen en **klik** op ![ pictogram Bewerken ](../../media/ITPro-EAC-AddIcon.png) bewerken .</span><span class="sxs-lookup"><span data-stu-id="5cd2f-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="5cd2f-146">Klik op de pagina eigenschappen van e-mailgebruikers die wordt geopend op een van de volgende tabbladen om eigenschappen weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="5cd2f-147">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="5cd2f-148">Algemeen</span><span class="sxs-lookup"><span data-stu-id="5cd2f-148">General</span></span>

<span data-ttu-id="5cd2f-149">Gebruik het tabblad **Algemeen** om basisgegevens over de e-mailgebruiker weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="5cd2f-150">**Voornaam**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-150">**First name**</span></span>

- <span data-ttu-id="5cd2f-151">**Initialen**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-151">**Initials**</span></span>

- <span data-ttu-id="5cd2f-152">**Achternaam**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-152">**Last name**</span></span>

- <span data-ttu-id="5cd2f-153">**Weergavenaam**: deze naam wordt weergegeven in het adresboek van uw organisatie, op het aan: en van: regels in e-mail en in de lijst met contactpersonen in de EAC.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="5cd2f-154">Deze naam mag geen lege spaties bevatten voor of na de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="5cd2f-155">**Gebruikersnaam**: dit is het account van de gebruiker in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="5cd2f-156">U deze waarde hier niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="5cd2f-157">Contactgegevens</span><span class="sxs-lookup"><span data-stu-id="5cd2f-157">Contact information</span></span>

<span data-ttu-id="5cd2f-158">Gebruik het tabblad **Contactgegevens** om de contactgegevens van de gebruiker weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="5cd2f-159">De informatie op deze pagina wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="5cd2f-160">**Street**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-160">**Street**</span></span>
- <span data-ttu-id="5cd2f-161">**Plaats**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-161">**City**</span></span>
- <span data-ttu-id="5cd2f-162">**Staat/provincie**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-162">**State/Province**</span></span>
- <span data-ttu-id="5cd2f-163">**Postcode**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="5cd2f-164">**Land/regio**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-164">**Country/Region**</span></span>
- <span data-ttu-id="5cd2f-165">**Telefoon werk**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-165">**Work phone**</span></span>
- <span data-ttu-id="5cd2f-166">**Mobiele telefoon**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-166">**Mobile phone**</span></span>
- <span data-ttu-id="5cd2f-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-167">**Fax**</span></span>
- <span data-ttu-id="5cd2f-168">**Meer opties**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-168">**More options**</span></span>

  - <span data-ttu-id="5cd2f-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-169">**Office**</span></span>
  - <span data-ttu-id="5cd2f-170">**Telefoon thuis**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-170">**Home phone**</span></span>
  - <span data-ttu-id="5cd2f-171">**Webpagina**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-171">**Web page**</span></span>
  - <span data-ttu-id="5cd2f-172">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="5cd2f-173">Organisatie</span><span class="sxs-lookup"><span data-stu-id="5cd2f-173">Organization</span></span>

<span data-ttu-id="5cd2f-174">Gebruik het tabblad **Organisatie** om gedetailleerde informatie op te nemen over de rol van de gebruiker in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="5cd2f-175">**Title**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-175">**Title**</span></span>
- <span data-ttu-id="5cd2f-176">**Afdeling**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-176">**Department**</span></span>
- <span data-ttu-id="5cd2f-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="5cd2f-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="5cd2f-178">De EAC gebruiken om e-mailgebruikers te verwijderen</span><span class="sxs-lookup"><span data-stu-id="5cd2f-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="5cd2f-179">Ga in de EAC naar **Contactpersonen voor ontvangers** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="5cd2f-180">Selecteer de e-mailgebruiker die u wilt verwijderen en **klik** op ![ pictogram Verwijderen verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="5cd2f-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="5cd2f-181">PowerShell gebruiken om e-mailgebruikers te beheren</span><span class="sxs-lookup"><span data-stu-id="5cd2f-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="5cd2f-182">Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers weer te geven</span><span class="sxs-lookup"><span data-stu-id="5cd2f-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="5cd2f-183">Voer de volgende opdracht uit om een overzichtslijst van alle e-mailgebruikers in standalone EOP PowerShell terug te sturen:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="5cd2f-184">Als u gedetailleerde informatie over een specifieke e-mailgebruiker wilt weergeven, vervangt u \<MailUserIdentity\> de naam, alias of accountnaam van de e-mailgebruiker en voert u de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="5cd2f-185">Zie [Ophalen](https://docs.microsoft.com/powershell/module/exchange/get-recipient) en [Gebruiker](https://docs.microsoft.com/powershell/module/exchange/get-user)ophalen voor gedetailleerde syntaxis en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="5cd2f-186">Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te maken</span><span class="sxs-lookup"><span data-stu-id="5cd2f-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="5cd2f-187">Als u e-mailgebruikers wilt maken in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="5cd2f-188">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-188">**Notes**:</span></span>

- <span data-ttu-id="5cd2f-189">De parameter _Naam_ is vereist, heeft een maximale lengte van 64 tekens en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="5cd2f-190">Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _Name_ gebruikt voor de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="5cd2f-191">Als u de parameter _Alias_ niet gebruikt, wordt de linkerkant van de parameter _MicrosoftOnlneServicesID_ gebruikt voor de alias.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlneServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="5cd2f-192">Als u de parameter _ExternalEmailAddress_ niet gebruikt, wordt de _MicrosoftOnlineServicesID-waarde_ gebruikt voor het externe e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="5cd2f-193">In dit voorbeeld wordt een e-mailgebruiker gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="5cd2f-194">De naam is JeffreyZeng en de display naam is Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="5cd2f-195">De voornaam is Jeffrey en de achternaam is Zeng.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="5cd2f-196">De alias is Jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="5cd2f-197">Het externe e-mailadres wordt jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="5cd2f-198">De accountnaam is jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="5cd2f-199">Het wachtwoord is Pa$ $word1.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="5cd2f-200">Zie [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="5cd2f-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="5cd2f-201">Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te wijzigen</span><span class="sxs-lookup"><span data-stu-id="5cd2f-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="5cd2f-202">Als u bestaande e-mailgebruikers in zelfstandige EOP PowerShell wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="5cd2f-203">In dit voorbeeld wordt het externe e-mailadres voor Pilar Pinilla ingesteld.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="5cd2f-204">In dit voorbeeld wordt de eigenschap Bedrijf voor alle e-mailgebruikers ingesteld op Contoso.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="5cd2f-205">Zie [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="5cd2f-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="5cd2f-206">Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te verwijderen</span><span class="sxs-lookup"><span data-stu-id="5cd2f-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="5cd2f-207">Als u e-mailgebruikers in zelfstandige EOP PowerShell wilt verwijderen, vervangt u \<MailUserIdentity\> de naam, alias of accountnaam van de e-mailgebruiker en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="5cd2f-208">In dit voorbeeld wordt de e-mailgebruiker voor Jeffrey Zeng verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="5cd2f-209">Zie [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)voor gedetailleerde syntaxis- en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="5cd2f-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="5cd2f-210">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="5cd2f-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="5cd2f-211">Als u wilt controleren of u e-mailgebruikers hebt gemaakt, gewijzigd of verwijderd in zelfstandige EOP, gebruikt u een van de volgende procedures:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="5cd2f-212">Ga in de EAC naar **Contactpersonen voor ontvangers** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="5cd2f-213">Controleer of de e-mailgebruiker wordt vermeld (of niet wordt vermeld).</span><span class="sxs-lookup"><span data-stu-id="5cd2f-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="5cd2f-214">Selecteer de e-mailgebruiker en bekijk de informatie in het deelvenster Details of **klik** op pictogram Bewerken bewerken ![ om de instellingen weer te ](../../media/ITPro-EAC-AddIcon.png) geven.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="5cd2f-215">Voer in standalone EOP PowerShell de volgende opdracht uit om te controleren of de e-mailgebruiker wordt vermeld (of niet wordt vermeld):</span><span class="sxs-lookup"><span data-stu-id="5cd2f-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="5cd2f-216">Vervang \<MailUserIdentity\> de naam, alias of accountnaam van de e-mailgebruiker en voer de volgende opdrachten uit om de instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="5cd2f-217">Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren</span><span class="sxs-lookup"><span data-stu-id="5cd2f-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="5cd2f-218">In standalone EOP is directorysynchronisatie beschikbaar voor klanten met on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="5cd2f-219">U deze accounts synchroniseren met Azure Active Directory (Azure AD), waar kopieën van de accounts in de cloud worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="5cd2f-220">Wanneer u uw bestaande gebruikersaccounts synchroniseert met Azure Active Directory, u deze gebruikers bekijken in het deelvenster **Geadresseerden** van het Exchange-beheercentrum (EAC) of in zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="5cd2f-221">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-221">**Notes**:</span></span>

- <span data-ttu-id="5cd2f-222">Als u adreslijstsynchronisatie gebruikt om uw ontvangers te beheren, u nog steeds gebruikers toevoegen en beheren in het Microsoft 365-beheercentrum, maar worden ze niet gesynchroniseerd met uw on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="5cd2f-223">Dit komt omdat directorysynchronisatie alleen ontvangers van uw on-premises Active Directory synchroniseert met de cloud.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="5cd2f-224">Het gebruik van adreslijstsynchronisatie wordt aanbevolen voor gebruik met de volgende functies:</span><span class="sxs-lookup"><span data-stu-id="5cd2f-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="5cd2f-225">**Lijsten met veilige afzenders van Outlook en lijsten met geblokkeerde afzenders**: Wanneer deze lijsten worden gesynchroniseerd met de service, hebben deze lijsten voorrang op spamfiltering in de service.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="5cd2f-226">Hiermee kunnen gebruikers hun eigen lijst met veilige afzenders en lijst met geblokkeerde afzenders beheren met afzonderlijke afzender- en domeinvermeldingen.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="5cd2f-227">Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="5cd2f-228">**Directory Based Edge Blocking (DBEB)**: Zie [Directory Based Edge Blocking gebruiken om berichten die naar ongeldige ontvangers worden verzonden, te weigeren voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)meer informatie over DBEB.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="5cd2f-229">**Toegang van eindgebruikers tot quarantaine**: Om toegang te krijgen tot hun berichten in quarantaine, moeten ontvangers een geldige gebruikersnaam en wachtwoord in de service hebben.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="5cd2f-230">Zie Berichten [in quarantaine zoeken en vrijgeven als gebruiker voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)meer informatie over quarantaine.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="5cd2f-231">**Regels voor e-mailstroom (ook wel transportregels genoemd):** Wanneer u adreslijstsynchronisatie gebruikt, worden uw bestaande Active Directory-gebruikers en -groepen automatisch geüpload naar de cloud en u vervolgens regels voor e-mailstroom maken die specifieke gebruikers en/of groepen targeten zonder deze handmatig toe te voegen in de service.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="5cd2f-232">Houd er rekening mee dat [dynamische distributiegroepen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) niet kunnen worden gesynchroniseerd via adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="5cd2f-233">De benodigde machtigingen ophalen en voorbereiden op adreslijstsynchronisatie, zoals beschreven in [Wat is hybride identiteit met Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="5cd2f-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="5cd2f-234">Mappen synchroniseren met Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="5cd2f-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="5cd2f-235">Activeer adreslijstsynchronisatie zoals beschreven in [Azure AD Connect-synchronisatie: synchronisatie begrijpen en aanpassen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="5cd2f-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="5cd2f-236">Installeer en configureer een on-premises computer om AAD Connect uit te voeren zoals beschreven in [Vereisten voor Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="5cd2f-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="5cd2f-237">[Selecteer welk installatietype u wilt gebruiken voor Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="5cd2f-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="5cd2f-238">Express</span><span class="sxs-lookup"><span data-stu-id="5cd2f-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="5cd2f-239">Aangepaste</span><span class="sxs-lookup"><span data-stu-id="5cd2f-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="5cd2f-240">Pass-through-verificatie</span><span class="sxs-lookup"><span data-stu-id="5cd2f-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="5cd2f-241">Wanneer u de wizard Configuratie van het Azure Active Directory-synchronisatiegereedschap hebt voltooid, wordt het **MSOL_AD_SYNC-account** gemaakt in uw Active Directory-forest.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-241">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="5cd2f-242">Dit account wordt gebruikt om uw on-premises Active Directory-gegevens te lezen en te synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-242">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="5cd2f-243">Als u ervoor wilt dat adreslijstsynchronisatie correct werkt, moet u ervoor zorgen dat TCP 443 op uw lokale adreslijstsynchronisatieserver is geopend.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-243">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="5cd2f-244">Controleer na het configureren van uw synchronisatie of AAD Connect correct synchroniseert.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="5cd2f-245">Ga in de EAC naar **Contactpersonen geadresseerden** \> **Contacts** en bekijk dat de lijst met gebruikers correct is gesynchroniseerd vanuit uw on-premises omgeving.</span><span class="sxs-lookup"><span data-stu-id="5cd2f-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
