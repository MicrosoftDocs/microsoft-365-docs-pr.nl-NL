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
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Meer informatie over het beheren van e-mailgebruikers in Exchange Online Protection (EOP), met inbegrip van adreslijstsynchronisatie, EAC en PowerShell om gebruikers te beheren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910616"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="b2cd8-103">E-mailgebruikers beheren in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="b2cd8-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b2cd8-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-104">**Applies to**</span></span>
-  [<span data-ttu-id="b2cd8-105">Zelfstandige Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b2cd8-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="b2cd8-106">In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken zijn e-mailgebruikers het basistype van het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="b2cd8-107">Een e-mailgebruiker heeft accountreferenties in uw zelfstandige EOP-organisatie en heeft toegang tot resources (er zijn machtigingen toegewezen).</span><span class="sxs-lookup"><span data-stu-id="b2cd8-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="b2cd8-108">Het e-mailadres van een e-mailgebruiker is extern (bijvoorbeeld in uw on-premises e-mailomgeving).</span><span class="sxs-lookup"><span data-stu-id="b2cd8-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="b2cd8-109">Wanneer u een e-mailgebruiker maakt, is het bijbehorende gebruikersaccount beschikbaar in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b2cd8-110">Wanneer u een gebruikersaccount maakt in het Microsoft 365-beheercentrum, kunt u dat account niet gebruiken om een e-mailgebruiker te maken.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="b2cd8-111">De aanbevolen methode voor het maken en beheren van e-mailgebruikers in zelfstandige EOP is het gebruik van adreslijstsynchronisatie zoals beschreven in de sectie [Adreslijstsynchronisatie](#use-directory-synchronization-to-manage-mail-users) gebruiken om e-mailgebruikers verderop in dit artikel te beheren.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="b2cd8-112">Voor zelfstandige EOP-organisaties met een klein aantal gebruikers kunt u e-mailgebruikers toevoegen en beheren in het Exchange-beheercentrum (EAC) of in zelfstandige EOP PowerShell, zoals in dit artikel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b2cd8-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="b2cd8-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b2cd8-114">Zie Exchange-beheercentrum in zelfstandige [EOP](exchange-admin-center-in-exchange-online-protection-eop.md)om het Exchange-beheercentrum (EAC) te openen.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="b2cd8-115">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b2cd8-116">Wanneer u e-mailgebruikers maakt in EOP PowerShell, ondervindt u mogelijk beperking.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="b2cd8-117">De EOP PowerShell-cmdlets gebruiken ook een batchverwerkingsmethode die resulteert in een doorloopvertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="b2cd8-118">U moet machtigingen krijgen toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="b2cd8-119">U hebt met  name de rollen E-mailontvangers (maken) en E-mailontvangers (wijzigen) nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer **(globale** beheerders) en  **Geadresseerdenbeheer.**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="b2cd8-120">Zie Machtigingen in zelfstandige [EOP](feature-permissions-in-eop.md) en Gebruik de EAC om de lijst met [leden in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="b2cd8-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="b2cd8-121">Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in [dit artikel.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="b2cd8-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b2cd8-122">Hebt u problemen?</span><span class="sxs-lookup"><span data-stu-id="b2cd8-122">Having problems?</span></span> <span data-ttu-id="b2cd8-123">Vraag om hulp in de Exchange-forums.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="b2cd8-124">Ga naar [het Exchange Online Protection-forum.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="b2cd8-124">Visit the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="b2cd8-125">Het Exchange-beheercentrum gebruiken om e-mailgebruikers te beheren</span><span class="sxs-lookup"><span data-stu-id="b2cd8-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="b2cd8-126">EAC gebruiken om e-mailgebruikers te maken</span><span class="sxs-lookup"><span data-stu-id="b2cd8-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="b2cd8-127">Ga in het EAC naar **Contactpersonen voor** \> **geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="b2cd8-128">Klik **op Nieuw** nieuw pictogram ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="b2cd8-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="b2cd8-129">Configureer **de volgende instellingen** op de pagina Nieuwe e-mailgebruiker die wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="b2cd8-130">Instellingen die zijn gemarkeerd met <sup>\*</sup> een zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="b2cd8-131">**Voornaam**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-131">**First name**</span></span>

   - <span data-ttu-id="b2cd8-132">**Initialen:** de middelste initialen van de persoon.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="b2cd8-133">**Achternaam**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-133">**Last name**</span></span>

   - <span data-ttu-id="b2cd8-134"><sup>\*</sup>**Weergavenaam:** In dit vak worden standaard de waarden weergegeven uit de vakken **Voornaam,** **Initialen** en **Achternaam.**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="b2cd8-135">U kunt deze waarde accepteren of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-135">You can accept this value or change it.</span></span> <span data-ttu-id="b2cd8-136">De waarde moet uniek zijn en een maximale lengte van 64 tekens hebben.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="b2cd8-137"><sup>\*</sup>**Alias:** Voer een unieke alias in met maximaal 64 tekens voor de gebruiker</span><span class="sxs-lookup"><span data-stu-id="b2cd8-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="b2cd8-138">**Extern e-mailadres:** Voer het e-mailadres van de gebruiker in.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="b2cd8-139">Het domein moet extern zijn voor uw cloudorganisatie.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="b2cd8-140"><sup>\*</sup>**Gebruikers-id:** Voer het account in dat de persoon gebruikt om zich aan te melden bij de service.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="b2cd8-141">De gebruikers-id bestaat uit een gebruikersnaam aan de linkerkant van het @-symbool (@) en een domein aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="b2cd8-142"><sup>\*</sup>**Nieuw wachtwoord** en <sup>\*</sup> **Wachtwoord bevestigen:** Voer het accountwachtwoord in en voer het opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="b2cd8-143">Controleer of het wachtwoord voldoet aan de wachtwoordlengte, complexiteit en geschiedenisvereisten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="b2cd8-144">Wanneer u klaar bent, klikt u op **Opslaan om** de e-mailgebruiker te maken.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="b2cd8-145">EAC gebruiken om e-mailgebruikers te wijzigen</span><span class="sxs-lookup"><span data-stu-id="b2cd8-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="b2cd8-146">Ga in het EAC naar **Contactpersonen voor** \> **geadresseerden.**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="b2cd8-147">Selecteer de e-mailgebruiker die u wilt wijzigen en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/ITPro-EAC-AddIcon.png) bewerken.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="b2cd8-148">Klik op de pagina eigenschappen van e-mailgebruikers die wordt geopend op een van de volgende tabbladen om eigenschappen weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="b2cd8-149">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="b2cd8-150">Algemeen</span><span class="sxs-lookup"><span data-stu-id="b2cd8-150">General</span></span>

<span data-ttu-id="b2cd8-151">Gebruik het **tabblad** Algemeen om basisgegevens over de e-mailgebruiker weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="b2cd8-152">**Voornaam**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-152">**First name**</span></span>

- <span data-ttu-id="b2cd8-153">**Initialen**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-153">**Initials**</span></span>

- <span data-ttu-id="b2cd8-154">**Achternaam**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-154">**Last name**</span></span>

- <span data-ttu-id="b2cd8-155">**Weergavenaam:** Deze naam wordt weergegeven in het adresboek van uw organisatie, op de regels Aan: en Van: in e-mail en in de lijst met contactpersonen in het EAC.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="b2cd8-156">Deze naam mag geen lege spaties voor of na de weergavenaam bevatten.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="b2cd8-157">**Gebruikers-id:** dit is het account van de gebruiker in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="b2cd8-158">U kunt deze waarde hier niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="b2cd8-159">Contactgegevens</span><span class="sxs-lookup"><span data-stu-id="b2cd8-159">Contact information</span></span>

<span data-ttu-id="b2cd8-160">Gebruik het **tabblad Contactgegevens** om de contactgegevens van de gebruiker weer te geven of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="b2cd8-161">De informatie op deze pagina wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="b2cd8-162">**Straat**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-162">**Street**</span></span>
- <span data-ttu-id="b2cd8-163">**Plaats**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-163">**City**</span></span>
- <span data-ttu-id="b2cd8-164">**Staat/provincie**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-164">**State/Province**</span></span>
- <span data-ttu-id="b2cd8-165">**Postcode**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="b2cd8-166">**Land/regio**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-166">**Country/Region**</span></span>
- <span data-ttu-id="b2cd8-167">**Telefoon werk**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-167">**Work phone**</span></span>
- <span data-ttu-id="b2cd8-168">**Mobiele telefoon**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-168">**Mobile phone**</span></span>
- <span data-ttu-id="b2cd8-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-169">**Fax**</span></span>
- <span data-ttu-id="b2cd8-170">**Meer opties**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-170">**More options**</span></span>

  - <span data-ttu-id="b2cd8-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-171">**Office**</span></span>
  - <span data-ttu-id="b2cd8-172">**Telefoon thuis**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-172">**Home phone**</span></span>
  - <span data-ttu-id="b2cd8-173">**Webpagina**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-173">**Web page**</span></span>
  - <span data-ttu-id="b2cd8-174">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="b2cd8-175">Organisatie</span><span class="sxs-lookup"><span data-stu-id="b2cd8-175">Organization</span></span>

<span data-ttu-id="b2cd8-176">Gebruik het **tabblad Organisatie** om gedetailleerde informatie over de rol van de gebruiker in de organisatie op te nemen.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="b2cd8-177">**Title**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-177">**Title**</span></span>
- <span data-ttu-id="b2cd8-178">**Afdeling**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-178">**Department**</span></span>
- <span data-ttu-id="b2cd8-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="b2cd8-180">EAC gebruiken om e-mailgebruikers te verwijderen</span><span class="sxs-lookup"><span data-stu-id="b2cd8-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="b2cd8-181">Ga in het EAC naar **Contactpersonen voor** \> **geadresseerden.**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="b2cd8-182">Selecteer de e-mailgebruiker die u wilt verwijderen en klik vervolgens **op Pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="b2cd8-183">PowerShell gebruiken om e-mailgebruikers te beheren</span><span class="sxs-lookup"><span data-stu-id="b2cd8-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="b2cd8-184">Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers weer te geven</span><span class="sxs-lookup"><span data-stu-id="b2cd8-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="b2cd8-185">Voer de volgende opdracht uit als u een overzichtslijst wilt retourneren van alle e-mailgebruikers in zelfstandige EOP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="b2cd8-186">Als u gedetailleerde informatie over een specifieke e-mailgebruiker wilt weergeven, vervangt u de naam, alias of accountnaam van de e-mailgebruiker en voert u \<MailUserIdentity\> de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="b2cd8-187">Zie Get-Recipient and Get-User [(Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User)](/powershell/module/exchange/get-user)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-187">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User](/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="b2cd8-188">Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te maken</span><span class="sxs-lookup"><span data-stu-id="b2cd8-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="b2cd8-189">Als u e-mailgebruikers wilt maken in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="b2cd8-190">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-190">**Notes**:</span></span>

- <span data-ttu-id="b2cd8-191">De _parameter_ Naam is vereist, heeft een maximale lengte van 64 tekens en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="b2cd8-192">Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _Naam_ gebruikt voor de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="b2cd8-193">Als u de _parameter Alias_ niet gebruikt, wordt de linkerkant van de _parameter MicrosoftOnlineServicesID_ gebruikt voor de alias.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="b2cd8-194">Als u de parameter _ExternalEmailAddress_ niet gebruikt, wordt de _waarde MicrosoftOnlineServicesID_ gebruikt voor het externe e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="b2cd8-195">In dit voorbeeld wordt een e-mailgebruiker gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="b2cd8-196">De naam is JeffreyZeng en de weergavenaam is Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="b2cd8-197">De voornaam is Jeffrey en de achternaam is Zeng.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="b2cd8-198">De alias is jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="b2cd8-199">Het externe e-mailadres is jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="b2cd8-200">De accountnaam is jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="b2cd8-201">Het wachtwoord is Pa$$word 1.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="b2cd8-202">Zie [New-EOPMailUser (Nieuw-EOPMailUser) voor](/powershell/module/exchange/new-eopmailuser)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-202">For detailed syntax and parameter information, see [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="b2cd8-203">Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te wijzigen</span><span class="sxs-lookup"><span data-stu-id="b2cd8-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="b2cd8-204">Als u bestaande e-mailgebruikers wilt wijzigen in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="b2cd8-205">In dit voorbeeld wordt het externe e-mailadres voor Pilar Pinilla instellen.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="b2cd8-206">In dit voorbeeld stelt u de eigenschap Bedrijf voor alle e-mailgebruikers in op Contoso.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="b2cd8-207">Zie [Set-EOPMailUser voor](/powershell/module/exchange/set-eopmailuser)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-207">For detailed syntax and parameter information, see [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="b2cd8-208">Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te verwijderen</span><span class="sxs-lookup"><span data-stu-id="b2cd8-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="b2cd8-209">Als u e-mailgebruikers in zelfstandige EOP PowerShell wilt verwijderen, vervangt u door de naam, alias of accountnaam van de e-mailgebruiker en voer u \<MailUserIdentity\> de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="b2cd8-210">In dit voorbeeld wordt de e-mailgebruiker voor Jeffrey Zeng verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="b2cd8-211">Zie [Remove-EOPMailUser (Verwijderen-EOPMailUser)](/powershell/module/exchange/remove-eopmailuser)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b2cd8-212">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="b2cd8-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="b2cd8-213">Als u wilt controleren of u e-mailgebruikers hebt gemaakt, gewijzigd of verwijderd in zelfstandige EOP, gebruikt u een van de volgende procedures:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="b2cd8-214">Ga in het EAC naar **Contactpersonen voor** \> **geadresseerden.**</span><span class="sxs-lookup"><span data-stu-id="b2cd8-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="b2cd8-215">Controleer of de e-mailgebruiker wordt vermeld (of niet wordt vermeld).</span><span class="sxs-lookup"><span data-stu-id="b2cd8-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="b2cd8-216">Selecteer de e-mailgebruiker en bekijk de informatie in het deelvenster Details of klik op **Pictogram** ![ Bewerken bewerken om de instellingen weer te ](../../media/ITPro-EAC-AddIcon.png) geven.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="b2cd8-217">Voer in zelfstandige EOP PowerShell de volgende opdracht uit om te controleren of de e-mailgebruiker wordt vermeld (of niet wordt vermeld):</span><span class="sxs-lookup"><span data-stu-id="b2cd8-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="b2cd8-218">Vervang \<MailUserIdentity\> deze door de naam, alias of accountnaam van de e-mailgebruiker en voer de volgende opdrachten uit om de instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="b2cd8-219">Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren</span><span class="sxs-lookup"><span data-stu-id="b2cd8-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="b2cd8-220">In zelfstandige EOP is adreslijstsynchronisatie beschikbaar voor klanten met on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="b2cd8-221">U kunt deze accounts synchroniseren met Azure Active Directory (Azure AD), waar kopieën van de accounts worden opgeslagen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="b2cd8-222">Wanneer u uw bestaande **gebruikersaccounts** synchroniseert met Azure Active Directory, kunt u deze gebruikers bekijken in het deelvenster Geadresseerden van het Exchange-beheercentrum (EAC) of in zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="b2cd8-223">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-223">**Notes**:</span></span>

- <span data-ttu-id="b2cd8-224">Als u adreslijstsynchronisatie gebruikt om uw geadresseerden te beheren, kunt u nog steeds gebruikers toevoegen en beheren in het Microsoft 365-beheercentrum, maar ze worden niet gesynchroniseerd met uw on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="b2cd8-225">Dit komt omdat adreslijstsynchronisatie alleen geadresseerden synchroniseert van uw on-premises Active Directory naar de cloud.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="b2cd8-226">Het gebruik van adreslijstsynchronisatie wordt aanbevolen voor gebruik met de volgende functies:</span><span class="sxs-lookup"><span data-stu-id="b2cd8-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="b2cd8-227">**Lijsten met veilige afzenders** van Outlook en lijsten met geblokkeerde afzenders: wanneer deze worden gesynchroniseerd met de service, hebben deze lijsten voorrang op spamfilters in de service.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="b2cd8-228">Hierdoor kunnen gebruikers hun eigen lijst met veilige afzenders en lijst met geblokkeerde afzenders beheren met afzonderlijke afzenders en domeingegevens.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="b2cd8-229">Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="b2cd8-230">**Directory Based Edge Blocking (DBEB)**: Zie Directory Based Edge Blocking (Directory Based Edge Blocking) voor meer informatie over DBEB om berichten te weigeren die naar [ongeldige geadresseerden zijn verzonden.](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)</span><span class="sxs-lookup"><span data-stu-id="b2cd8-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="b2cd8-231">**Toegang van eindgebruikers tot quarantaine:** geadresseerden moeten een geldige gebruikers-id en een geldig wachtwoord in de service hebben om toegang te krijgen tot hun in quarantaine geplaatste berichten.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="b2cd8-232">Zie Berichten in quarantaine zoeken en vrijgeven als gebruiker voor [meer informatie over quarantaine.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="b2cd8-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="b2cd8-233">Regels voor e-mailstroom (ook wel transportregels **genoemd)**: Wanneer u adreslijstsynchronisatie gebruikt, worden uw bestaande Active Directory-gebruikers en -groepen automatisch geüpload naar de cloud en kunt u vervolgens regels voor de e-mailstroom maken die gericht zijn op specifieke gebruikers en/of groepen zonder ze handmatig toe te voegen aan de service.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="b2cd8-234">Dynamische [distributiegroepen kunnen](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) niet worden gesynchroniseerd via adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-234">Note that [dynamic distribution groups](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="b2cd8-235">Krijg de benodigde machtigingen en bereid u voor op adreslijstsynchronisatie, zoals beschreven in [Wat is hybride identiteit met Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="b2cd8-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="b2cd8-236">Mappen synchroniseren met Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="b2cd8-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="b2cd8-237">Adreslijstsynchronisatie activeren zoals beschreven in [Azure AD Connect-synchronisatie: Synchronisatie](/azure/active-directory/hybrid/how-to-connect-sync-whatis)begrijpen en aanpassen.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="b2cd8-238">Installeer en configureer een on-premises computer om AAD Connect uit te voeren, zoals beschreven in [Vereisten voor Azure AD Connect.](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="b2cd8-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="b2cd8-239">[Selecteer welk installatietype u wilt gebruiken voor Azure AD Connect:](/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="b2cd8-239">[Select which installation type to use for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="b2cd8-240">Express</span><span class="sxs-lookup"><span data-stu-id="b2cd8-240">Express</span></span>](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="b2cd8-241">Aangepast</span><span class="sxs-lookup"><span data-stu-id="b2cd8-241">Custom</span></span>](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="b2cd8-242">Pass-through-verificatie</span><span class="sxs-lookup"><span data-stu-id="b2cd8-242">Pass-through authentication</span></span>](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="b2cd8-243">Wanneer u de configuratiewizard van het Azure Active Directory-synchronisatieprogramma hebt uitgevoerd, **wordt MSOL_AD_SYNC** account gemaakt in uw Active Directory-forest.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-243">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="b2cd8-244">Dit account wordt gebruikt om uw on-premises Active Directory-gegevens te lezen en te synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-244">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="b2cd8-245">Zorg ervoor dat TCP 443 op uw lokale adreslijstsynchronisatieserver is geopend om ervoor te zorgen dat adreslijstsynchronisatie correct werkt.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-245">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="b2cd8-246">Controleer na het configureren van de synchronisatie of AAD Connect correct wordt gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="b2cd8-247">Ga in het EAC naar **Contactpersonen** voor geadresseerden en bekijk of de lijst met gebruikers correct is \>  gesynchroniseerd vanuit uw on-premises omgeving.</span><span class="sxs-lookup"><span data-stu-id="b2cd8-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>