---
title: E-mailgebruikers beheren in standalone EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Meer informatie over het beheren van gebruikers van e-mailberichten in Exchange Online Protection (EOP), waaronder het gebruik van adreslijstsynchronisatie, SBV en PowerShell voor het beheren van gebruikers.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 56e6f8955b5993fb4b5064aa92cdde80a4c67ffe
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201781"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="6965d-103">E-mailgebruikers beheren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="6965d-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6965d-104">Gebruikers van een zelfstandige Exchange Online Protection-organisatie (EOP) zonder postvakken van Exchange, zijn e-mail gebruikers het fundamentele type gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="6965d-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="6965d-105">Een e-mail gebruiker heeft accountreferenties in uw zelfstandige EOP-organisatie en kan toegang krijgen tot bronnen (machtigingen toegewezen).</span><span class="sxs-lookup"><span data-stu-id="6965d-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="6965d-106">Het e-mailadres van een e-mail gebruiker is extern (bijvoorbeeld in uw on-premises e-mail omgeving).</span><span class="sxs-lookup"><span data-stu-id="6965d-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="6965d-107">Wanneer u een e-mail gebruiker maakt, is het bijbehorende gebruikersaccount beschikbaar in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="6965d-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6965d-108">Wanneer u een gebruikersaccount maakt in het Microsoft 365-Beheercentrum, kunt u dit account niet gebruiken om een e-mail gebruiker te maken.</span><span class="sxs-lookup"><span data-stu-id="6965d-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="6965d-109">De aanbevolen methode voor het maken en beheren van e-mail gebruikers in standalone EOP is door gebruik te maken van adreslijstsynchronisatie, zoals beschreven in de sectie [e-mail gebruikers van de sectie e-mailadressen beheren](#use-directory-synchronization-to-manage-mail-users) .</span><span class="sxs-lookup"><span data-stu-id="6965d-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="6965d-110">Voor zelfstandige EOP-organisaties met een klein aantal gebruikers, kunt u e-mail gebruikers toevoegen en beheren in het Exchange-Beheercentrum (Microsoft) of in een zelfstandige EOP-PowerShell zoals in dit onderwerp wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="6965d-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6965d-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="6965d-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6965d-112">U opent het Exchange-Beheercentrum door het Exchange- [Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="6965d-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="6965d-113">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6965d-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6965d-114">Wanneer u e-mail gebruikers maakt in EOP PowerShell, kan dat leiden tot vertraging.</span><span class="sxs-lookup"><span data-stu-id="6965d-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="6965d-115">Daarnaast wordt in de EOP PowerShell-cmdlets een batch verwerkingsmethode gebruikt die de vertraging van een paar minuten oplevert voordat de resultaten van de opdrachten zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="6965d-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="6965d-116">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="6965d-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="6965d-117">Specifiek hebt u de e-mailadressen voor e-mail geadresseerden (maken) en e-mail geadresseerden (wijzigen) nodig die standaard zijn toegewezen aan de de organizationmanagement (algemene beheerders) en RecipientManagement rollen groepen.</span><span class="sxs-lookup"><span data-stu-id="6965d-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="6965d-118">Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="6965d-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="6965d-119">Zie toetscombinaties [voor het Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="6965d-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="6965d-120">Problemen?</span><span class="sxs-lookup"><span data-stu-id="6965d-120">Having problems?</span></span> <span data-ttu-id="6965d-121">Hulp vragen op de Exchange-forums.</span><span class="sxs-lookup"><span data-stu-id="6965d-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="6965d-122">Bezoek het forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="6965d-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="6965d-123">Het Exchange-Beheercentrum gebruiken voor het beheren van e-mail gebruikers</span><span class="sxs-lookup"><span data-stu-id="6965d-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="6965d-124">Het Exchange-Beheercentrum gebruiken om e-mail gebruikers te maken</span><span class="sxs-lookup"><span data-stu-id="6965d-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="6965d-125">Ga in het Exchange-beheer **Recipients** centrum naar \> **contacten** met geadresseerden</span><span class="sxs-lookup"><span data-stu-id="6965d-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="6965d-126">Klik op **Nieuw** ![ pictogram nieuw ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6965d-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="6965d-127">Configureer de volgende instellingen op de pagina **nieuwe e-mail gebruiker** die wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="6965d-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="6965d-128">Instellingen die zijn gemarkeerd met een <sup>\*</sup> zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="6965d-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="6965d-129">**Voornaam**</span><span class="sxs-lookup"><span data-stu-id="6965d-129">**First name**</span></span>

   - <span data-ttu-id="6965d-130">**Initialen**: de initiaal van de persoon.</span><span class="sxs-lookup"><span data-stu-id="6965d-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="6965d-131">**Achternaam**</span><span class="sxs-lookup"><span data-stu-id="6965d-131">**Last name**</span></span>

   - <span data-ttu-id="6965d-132"><sup>\*</sup>**Weergavenaam**: in dit vak worden standaard de waarden in de vakken **voornaam**, **initialen**en **Achternaam** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6965d-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="6965d-133">U kunt deze waarde accepteren of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6965d-133">You can accept this value or change it.</span></span> <span data-ttu-id="6965d-134">De waarde moet uniek zijn en mag maximaal 64 tekens lang zijn.</span><span class="sxs-lookup"><span data-stu-id="6965d-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="6965d-135"><sup>\*</sup>**Alias**: Voer een unieke alias in met tot 64 tekens voor de gebruiker</span><span class="sxs-lookup"><span data-stu-id="6965d-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="6965d-136">**Extern e-mailadres**: Voer het e-mailadres van de gebruiker in.</span><span class="sxs-lookup"><span data-stu-id="6965d-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="6965d-137">Het domein moet buiten de Cloud organisatie liggen.</span><span class="sxs-lookup"><span data-stu-id="6965d-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="6965d-138"><sup>\*</sup>**Gebruikers-id**: Voer het account in dat door de persoon wordt gebruikt om u aan te melden bij de service.</span><span class="sxs-lookup"><span data-stu-id="6965d-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="6965d-139">De gebruikers-ID bestaat uit een gebruikersnaam aan de linkerkant van het apenstaartje (@) en een domein aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="6965d-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="6965d-140"><sup>\*</sup>**Nieuw wachtwoord** en <sup>\*</sup> **Bevestig uw wachtwoord**: Voer het accountwachtwoord in en voer deze opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="6965d-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="6965d-141">Controleer of het wachtwoord voldoet aan de vereisten voor de lengte en complexiteit van het wachtwoord en de geschiedenis van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6965d-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="6965d-142">Wanneer u klaar bent, klikt u op **Opslaan** om de e-mail gebruiker te maken.</span><span class="sxs-lookup"><span data-stu-id="6965d-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="6965d-143">Het Exchange-Beheercentrum gebruiken om e-mail gebruikers te wijzigen</span><span class="sxs-lookup"><span data-stu-id="6965d-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="6965d-144">Ga in het Exchange-beheer **Recipients** centrum naar \> **contactpersonen**met geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="6965d-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="6965d-145">Selecteer de e-mail gebruiker die u wilt wijzigen en klik vervolgens **Edit** op het ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="6965d-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="6965d-146">Op de pagina met de gebruikerseigenschappen van de e-mail die wordt geopend, klikt u op een van de volgende tabbladen om de eigenschappen weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6965d-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="6965d-147">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="6965d-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="6965d-148">Algemeen</span><span class="sxs-lookup"><span data-stu-id="6965d-148">General</span></span>

<span data-ttu-id="6965d-149">Gebruik het tabblad **Algemeen** om basisinformatie over de e-mail gebruiker weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6965d-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="6965d-150">**Voornaam**</span><span class="sxs-lookup"><span data-stu-id="6965d-150">**First name**</span></span>

- <span data-ttu-id="6965d-151">**Initialen**</span><span class="sxs-lookup"><span data-stu-id="6965d-151">**Initials**</span></span>

- <span data-ttu-id="6965d-152">**Achternaam**</span><span class="sxs-lookup"><span data-stu-id="6965d-152">**Last name**</span></span>

- <span data-ttu-id="6965d-153">**Weergavenaam**: deze naam wordt weergegeven in het adresboek van uw organisatie, op de regel aan: en van: en in de lijst met contactpersonen in het Exchange-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="6965d-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="6965d-154">Deze naam mag geen lege spaties voor of na de weergavenaam bevatten.</span><span class="sxs-lookup"><span data-stu-id="6965d-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="6965d-155">**Gebruikers-id**: dit is het account van de gebruiker in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6965d-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="6965d-156">U kunt deze waarde hier niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6965d-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="6965d-157">Contact gegevens</span><span class="sxs-lookup"><span data-stu-id="6965d-157">Contact information</span></span>

<span data-ttu-id="6965d-158">Gebruik het tabblad **contact gegevens** om de contact gegevens van de gebruiker weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6965d-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="6965d-159">De informatie op deze pagina wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="6965d-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="6965d-160">**Naam**</span><span class="sxs-lookup"><span data-stu-id="6965d-160">**Street**</span></span>
- <span data-ttu-id="6965d-161">**Plaats**</span><span class="sxs-lookup"><span data-stu-id="6965d-161">**City**</span></span>
- <span data-ttu-id="6965d-162">**Provincie**</span><span class="sxs-lookup"><span data-stu-id="6965d-162">**State/Province**</span></span>
- <span data-ttu-id="6965d-163">**Postcode**</span><span class="sxs-lookup"><span data-stu-id="6965d-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="6965d-164">**Land/regio**</span><span class="sxs-lookup"><span data-stu-id="6965d-164">**Country/Region**</span></span>
- <span data-ttu-id="6965d-165">**Telefoon werk**</span><span class="sxs-lookup"><span data-stu-id="6965d-165">**Work phone**</span></span>
- <span data-ttu-id="6965d-166">**Mobiele telefoon**</span><span class="sxs-lookup"><span data-stu-id="6965d-166">**Mobile phone**</span></span>
- <span data-ttu-id="6965d-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="6965d-167">**Fax**</span></span>
- <span data-ttu-id="6965d-168">**Meer opties**</span><span class="sxs-lookup"><span data-stu-id="6965d-168">**More options**</span></span>

  - <span data-ttu-id="6965d-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="6965d-169">**Office**</span></span>
  - <span data-ttu-id="6965d-170">**Telefoon thuis**</span><span class="sxs-lookup"><span data-stu-id="6965d-170">**Home phone**</span></span>
  - <span data-ttu-id="6965d-171">**Webpagina**</span><span class="sxs-lookup"><span data-stu-id="6965d-171">**Web page**</span></span>
  - <span data-ttu-id="6965d-172">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="6965d-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="6965d-173">Organisatie</span><span class="sxs-lookup"><span data-stu-id="6965d-173">Organization</span></span>

<span data-ttu-id="6965d-174">Via het tabblad **organisatie** kunt u gedetailleerde informatie over de rol van de gebruiker in de organisatie opnemen.</span><span class="sxs-lookup"><span data-stu-id="6965d-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="6965d-175">**Title**</span><span class="sxs-lookup"><span data-stu-id="6965d-175">**Title**</span></span>
- <span data-ttu-id="6965d-176">**Afdeling**</span><span class="sxs-lookup"><span data-stu-id="6965d-176">**Department**</span></span>
- <span data-ttu-id="6965d-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="6965d-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="6965d-178">Het Exchange-Beheercentrum gebruiken om e-mail gebruikers te verwijderen</span><span class="sxs-lookup"><span data-stu-id="6965d-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="6965d-179">Ga in het Exchange-beheer **Recipients** centrum naar \> **contactpersonen**met geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="6965d-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="6965d-180">Selecteer de e-mail gebruiker die u wilt verwijderen en **Klik op het** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="6965d-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="6965d-181">PowerShell gebruiken voor het beheren van e-mail gebruikers</span><span class="sxs-lookup"><span data-stu-id="6965d-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="6965d-182">Standalone EOP PowerShell gebruiken om e-mail gebruikers weer te geven</span><span class="sxs-lookup"><span data-stu-id="6965d-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="6965d-183">Voer de volgende opdracht uit als u een overzicht wilt weergeven van alle e-mail gebruikers in een zelfstandige EOP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6965d-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="6965d-184">Als u gedetailleerde informatie over een specifieke e-mail gebruiker wilt bekijken, vervangt u \<MailUserIdentity\> de naam, alias of accountnaam van de e-mail gebruiker en voert u de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="6965d-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="6965d-185">Zie [Get-verplaatsings-](https://docs.microsoft.com/powershell/module/exchange/get-recipient) en [Get-gebruiker](https://docs.microsoft.com/powershell/module/exchange/get-user)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="6965d-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="6965d-186">Standalone EOP PowerShell gebruiken om e-mail gebruikers te maken</span><span class="sxs-lookup"><span data-stu-id="6965d-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="6965d-187">Gebruik de volgende syntaxis om e-mail gebruikers te maken in zelfstandige EOP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6965d-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="6965d-188">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="6965d-188">**Notes**:</span></span>

- <span data-ttu-id="6965d-189">De _naam_ parameter is vereist, mag maximaal 64 tekens lang zijn en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="6965d-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="6965d-190">Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _name_ gebruikt voor de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="6965d-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="6965d-191">Als u de parameter _alias_ niet gebruikt, wordt de linkerkant van de _MicrosoftOnlineServicesID_ -parameter gebruikt voor de alias.</span><span class="sxs-lookup"><span data-stu-id="6965d-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="6965d-192">Als u de parameter _ExternalEmailAddress_ niet gebruikt, wordt de _MicrosoftOnlineServicesID_ -waarde gebruikt voor het externe e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="6965d-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="6965d-193">In het volgende voorbeeld wordt een e-mail gebruiker gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="6965d-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="6965d-194">De naam is JeffreyZeng en de weergavenaam is Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="6965d-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="6965d-195">De voornaam is Jeffrey en de naam van de achternaam is Zeng.</span><span class="sxs-lookup"><span data-stu-id="6965d-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="6965d-196">De alias is jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="6965d-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="6965d-197">Het externe e-mailadres is jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="6965d-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="6965d-198">De accountnaam is jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="6965d-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="6965d-199">Het wachtwoord is PA $ $word 1.</span><span class="sxs-lookup"><span data-stu-id="6965d-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="6965d-200">Zie [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="6965d-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="6965d-201">Zelfstandige EOP PowerShell gebruiken voor het wijzigen van e-mail gebruikers</span><span class="sxs-lookup"><span data-stu-id="6965d-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="6965d-202">Gebruik de volgende syntaxis om bestaande e-mail gebruikers van zelfstandige EOP PowerShell te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="6965d-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="6965d-203">In dit voorbeeld wordt het externe e-mailadres voor Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="6965d-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="6965d-204">In dit voorbeeld wordt de eigenschap Company voor alle e-mail gebruikers ingesteld op contoso.</span><span class="sxs-lookup"><span data-stu-id="6965d-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="6965d-205">Zie [set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="6965d-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="6965d-206">Standalone EOP PowerShell gebruiken om e-mail gebruikers te verwijderen</span><span class="sxs-lookup"><span data-stu-id="6965d-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="6965d-207">Als u e-mail gebruikers wilt verwijderen uit zelfstandige EOP PowerShell, vervangt u \<MailUserIdentity\> de naam, alias of accountnaam van de e-mail gebruiker en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="6965d-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="6965d-208">In dit voorbeeld wordt de e-mail gebruiker verwijderd voor Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="6965d-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="6965d-209">Zie [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="6965d-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6965d-210">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="6965d-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="6965d-211">Ga op een van de volgende manieren te werk om te controleren of u e-mail gebruikers met een zelfstandige EOP hebt gemaakt, gewijzigd of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6965d-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="6965d-212">Ga in het Exchange-beheer **Recipients** centrum naar \> **contactpersonen**met geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="6965d-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="6965d-213">Controleer of de e-mail gebruiker wordt weergegeven (of niet wordt weergegeven).</span><span class="sxs-lookup"><span data-stu-id="6965d-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="6965d-214">Selecteer e-mail gebruiker en Bekijk de informatie in het detailvenster of Klik **Edit** op ![ bewerkingspictogram bewerken ](../../media/ITPro-EAC-AddIcon.png) om de instellingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="6965d-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="6965d-215">Voer in standalone EOP PowerShell de volgende opdracht uit om te controleren of de e-mail gebruiker wordt weergegeven (of wordt niet weergegeven):</span><span class="sxs-lookup"><span data-stu-id="6965d-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="6965d-216">Vervang de \<MailUserIdentity\> naam, alias of accountnaam van de e-mail gebruiker en voer de volgende opdrachten uit om de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="6965d-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="6965d-217">Adreslijstsynchronisatie gebruiken voor het beheren van e-mail gebruikers</span><span class="sxs-lookup"><span data-stu-id="6965d-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="6965d-218">Directory-synchronisatie via zelfstandige EOP is beschikbaar voor klanten met een on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6965d-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="6965d-219">U kunt deze accounts synchroniseren met Azure Active Directory (Azure AD), waar kopieën van de accounts in de cloud worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="6965d-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="6965d-220">Wanneer u uw bestaande gebruikersaccounts synchroniseert met Azure Active Directory, kunt u deze gebruikers weergeven in het deelvenster **geadresseerden** van het Exchange-Beheercentrum (SBV) of in een zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6965d-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="6965d-221">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="6965d-221">**Notes**:</span></span>

- <span data-ttu-id="6965d-222">Als u adreslijstsynchronisatie gebruikt om geadresseerden te beheren, kunt u nog steeds gebruikers toevoegen en beheren in het Microsoft 365-Beheercentrum, maar deze worden niet gesynchroniseerd met uw on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6965d-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="6965d-223">Dit komt omdat adreslijstsynchronisatie alleen geadresseerden van uw on-premises Active Directory synchroniseert naar de Cloud.</span><span class="sxs-lookup"><span data-stu-id="6965d-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="6965d-224">Het gebruik van adreslijstsynchronisatie wordt aanbevolen voor gebruik met de volgende functies:</span><span class="sxs-lookup"><span data-stu-id="6965d-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="6965d-225">Lijsten met **veilige afzenders van Outlook en geblokkeerde lijsten van afzenders**: wanneer u de service synchroniseert, hebben deze lijsten voorrang op het filteren van ongewenste e-mail in de service.</span><span class="sxs-lookup"><span data-stu-id="6965d-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="6965d-226">Hiermee kunnen gebruikers hun eigen lijst met veilige afzenders en lijst met geblokkeerde afzenders beheren met individuele items voor de afzender en het domein.</span><span class="sxs-lookup"><span data-stu-id="6965d-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="6965d-227">Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6965d-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="6965d-228">**Op mappen gebaseerde rand blokkeren (DBEB)**: Zie voor meer informatie over DBEB voor meer informatie over [het gebruik van op mappen gebaseerde blokken blokkeren om berichten die naar ongeldige geadresseerden zijn verzonden, af te](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)wijzen.</span><span class="sxs-lookup"><span data-stu-id="6965d-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="6965d-229">**Eindgebruikers toegang tot Quarantine**: de geadresseerden moeten een geldige gebruikers-id en een geldig wachtwoord in de service hebben om toegang te krijgen tot de berichten in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="6965d-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="6965d-230">Zie geplaatste [berichten in quarantaine plaatsen en vrijgeven als een gebruiker](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)voor meer informatie over quarantaine.</span><span class="sxs-lookup"><span data-stu-id="6965d-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="6965d-231">**Regels voor e-mail stroom (ook wel transport-regels genoemd)**: wanneer u adreslijstsynchronisatie gebruikt, worden uw bestaande Active Directory-gebruikers en-groepen automatisch geüpload naar de Cloud, en kunt u vervolgens een e-mail stroom regel maken die specifieke gebruikers en/of groepen bedoelt, zonder dat u ze handmatig hoeft toe te voegen aan de service.</span><span class="sxs-lookup"><span data-stu-id="6965d-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="6965d-232">Houd er rekening mee dat [dynamische distributiegroepen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) niet kunnen worden gesynchroniseerd via adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="6965d-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="6965d-233">Zorg dat u de benodigde machtigingen hebt en voorbereiding voor adreslijstsynchronisatie, zoals wordt beschreven in [Wat is hybride identiteit met Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="6965d-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="6965d-234">Directory's synchroniseren met Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="6965d-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="6965d-235">Active Directory-synchronisatie activeren zoals beschreven in [Azure AD Connect-synchronisatie: de synchronisatie begrijpen en aanpassen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="6965d-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="6965d-236">Installeer en configureer een on-premises computer om AAD Connect uit te voeren, zoals is beschreven in [vereisten voor Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="6965d-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="6965d-237">[Selecteer welk type installatie u wilt gebruiken in azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span><span class="sxs-lookup"><span data-stu-id="6965d-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="6965d-238">Express</span><span class="sxs-lookup"><span data-stu-id="6965d-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="6965d-239">Gemaakte</span><span class="sxs-lookup"><span data-stu-id="6965d-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="6965d-240">Pass-through-verificatie</span><span class="sxs-lookup"><span data-stu-id="6965d-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="6965d-241">Wanneer u de wizard Configuratie van Azure Active Directory-synchronisatie hebt voltooid, wordt het **MSOL_AD_Sync** -account gemaakt in het Active Directory-forest.</span><span class="sxs-lookup"><span data-stu-id="6965d-241">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="6965d-242">Dit account wordt gebruikt voor het lezen en synchroniseren van uw on-premises Active Directory-informatie.</span><span class="sxs-lookup"><span data-stu-id="6965d-242">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="6965d-243">Zorg ervoor dat de TCP 443 op de lokale adreslijstsynchronisatie server is geopend, zodat de adreslijstsynchronisatie naar behoren werkt.</span><span class="sxs-lookup"><span data-stu-id="6965d-243">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="6965d-244">Voordat u de synchronisatie hebt geconfigureerd, controleert u of de AAD-verbinding correct wordt gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="6965d-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="6965d-245">Ga in het Exchange-beheer **Recipients** centrum naar \> **contactpersonen** van geadresseerden en bekijk dat de lijst met gebruikers correct is gesynchroniseerd vanuit uw on-premises omgeving.</span><span class="sxs-lookup"><span data-stu-id="6965d-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
