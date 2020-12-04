---
title: Beleidsregels voor veilige koppelingen instellen in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie lezen over het weergeven, maken, wijzigen en verwijderen van beleidsregels voor veilige koppelingen en algemene instellingen voor veilige koppelingen in Microsoft Defender voor Office 365.
ms.openlocfilehash: 550be48d5f1cae490c53c8f4a9fcedb0b9f21f73
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572715"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="587ac-103">Beleidsregels voor veilige koppelingen instellen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="587ac-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="587ac-104">Dit artikel is bedoeld voor zakelijke klanten met [Microsoft Defender voor Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="587ac-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="587ac-105">Als u een thuisgebruiker bent die op zoek bent naar informatie over Safelinks in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="587ac-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="587ac-106">Veilige koppelingen is een functie in [Microsoft Defender voor Office 365](office-365-atp.md) met het scannen van inkomende e-mailberichten in de e-mail stroom, en de tijd waarop u kunt klikken op verificatie van url's en koppelingen in e-mailberichten en andere locaties.</span><span class="sxs-lookup"><span data-stu-id="587ac-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="587ac-107">Zie voor meer informatie [veilige koppelingen in Microsoft Defender voor Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="587ac-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="587ac-108">Er is geen ingebouwd of standaardbeleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="587ac-109">Als u op zoek bent naar het scannen van Url's, moet u een of meer beleidsregels voor veilige koppelingen maken, zoals wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="587ac-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="587ac-110">U kunt beleidsregels voor veilige koppelingen configureren in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="587ac-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="587ac-111">De basiselementen van een beleid voor veilige koppelingen zijn:</span><span class="sxs-lookup"><span data-stu-id="587ac-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="587ac-112">**Het beleid voor veilige** koppelingen: Schakel beveiliging van veilige koppelingen in, schakel de mogelijkheid om in realtime url's in te schakelen en geef aan of u wilt wachten tot de realtime-controle is voltooid voordat u het bericht bezorgt, de scanfunctie voor interne berichten opgeeft en opgeven of gebruikers de muisklik op de URL moeten volgen en opgeven of gebruikers op Trough kunnen klikken voor de oorspronkelijke URL.</span><span class="sxs-lookup"><span data-stu-id="587ac-112">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="587ac-113">**De regel voor veilige koppelingen**: Hiermee geeft u de prioriteit op voor de filters voor de prioriteit en de geadresseerden (waarvoor het beleid van toepassing is).</span><span class="sxs-lookup"><span data-stu-id="587ac-113">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="587ac-114">Het verschil tussen deze twee elementen is niet duidelijk wanneer u beleidsregels voor veilige koppelingen beheert in het beveiligings & nalevings centrum:</span><span class="sxs-lookup"><span data-stu-id="587ac-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="587ac-115">Wanneer u een beleid voor veilige koppelingen maakt, maakt u eigenlijk een regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen tegelijk met dezelfde naam.</span><span class="sxs-lookup"><span data-stu-id="587ac-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="587ac-116">Wanneer u een beleid voor veilige koppelingen wijzigt, worden de instellingen voor de naam, de prioriteit, ingeschakeld of uitgeschakeld en de filters voor geadresseerden gewijzigd in de regel voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="587ac-117">Alle andere instellingen wijzigen het bijbehorende beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="587ac-118">Wanneer u een beleid voor veilige koppelingen verwijdert, worden de regels voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="587ac-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="587ac-119">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="587ac-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="587ac-120">Zie voor meer informatie het artikel [Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken voor het configureren van beleidsregels voor veilige koppelingen](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="587ac-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="587ac-121">U configureert de algemene instellingen voor beveiliging van veilige koppelingen **buiten** het beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="587ac-122">Zie [algemene instellingen configureren voor veilige koppelingen in Microsoft Defender voor Office 365](configure-global-settings-for-safe-links.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="587ac-122">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="587ac-123">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="587ac-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="587ac-124">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="587ac-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="587ac-125">Als u rechtstreeks naar de pagina met **veilige koppelingen** wilt gaan, gebruikt u <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="587ac-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="587ac-126">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="587ac-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="587ac-127">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="587ac-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="587ac-128">Voordat u de procedures in dit artikel kunt uitvoeren, moet u beschikken over machtigingen voor beveiliging & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="587ac-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="587ac-129">Als u beleidsregels voor veilige koppelingen wilt maken, wijzigen en verwijderen, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="587ac-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="587ac-130">Voor alleen-lezen toegang tot beleid voor veilige koppelingen moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .</span><span class="sxs-lookup"><span data-stu-id="587ac-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="587ac-131">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="587ac-132">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="587ac-132">**Notes**:</span></span>

  - <span data-ttu-id="587ac-133">Door gebruikers toe te voegen aan de bijbehorende rol van Azure Active Directory in het Microsoft 365-Beheercentrum geeft u gebruikers de vereiste machtigingen in het beveiligings & nalevings centrum _en_ machtigingen voor andere functies in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="587ac-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="587ac-134">Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="587ac-135">De functiegroep **alleen weergeven voor Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de functie.</span><span class="sxs-lookup"><span data-stu-id="587ac-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="587ac-136">Zie [beleidsinstellingen voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)voor de aanbevolen instellingen voor beleidsregels voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-136">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="587ac-137">Maximaal 30 minuten toegestaan voor het toepassen van een nieuwe of bijgewerkte beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="587ac-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="587ac-138">[Nieuwe functies worden continu toegevoegd aan Microsoft Defender voor Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="587ac-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="587ac-139">Wanneer nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleid voor veilige koppelingen aanpassen.</span><span class="sxs-lookup"><span data-stu-id="587ac-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="587ac-140">Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="587ac-140">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="587ac-141">Als u een aangepast beleid voor veilige koppelingen maakt in de beveiligings & nalevings centrum, wordt de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen tegelijk gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="587ac-141">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="587ac-142">Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen** voor het beleid voor bedreigings beheer.</span><span class="sxs-lookup"><span data-stu-id="587ac-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="587ac-143">Klik op de pagina **veilige koppelingen** op **maken**.</span><span class="sxs-lookup"><span data-stu-id="587ac-143">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="587ac-144">De wizard **beleid voor nieuwe beleidsregels** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="587ac-144">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="587ac-145">Configureer de volgende instellingen op de pagina **naam van uw beleid** :</span><span class="sxs-lookup"><span data-stu-id="587ac-145">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="587ac-146">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="587ac-146">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="587ac-147">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="587ac-147">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="587ac-148">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="587ac-148">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="587ac-149">Configureer de volgende instellingen op de pagina **instellingen** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="587ac-149">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="587ac-150">**Selecteer de actie voor onbekende mogelijk schadelijke url's in berichten**: Selecteer **aan** om de bescherming van veilige koppelingen in te schakelen voor koppelingen in e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="587ac-150">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="587ac-151">**Selecteer de actie voor onbekende of mogelijk schadelijke url's in Microsoft teams**: Selecteer **aan om de bescherming van veilige** koppelingen in te schakelen voor koppelingen in teams.</span><span class="sxs-lookup"><span data-stu-id="587ac-151">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="587ac-152">Het **scannen van realtime-Url's toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden**: Selecteer deze instelling om de realtime scan van koppelingen in e-mailberichten in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="587ac-152">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="587ac-153">**Wacht totdat het scannen van url's is voltooid voordat u het bericht bezorgt**: Selecteer deze instelling om te wachten tot de realtime-URL wordt gescand voordat u het bericht aflevert.</span><span class="sxs-lookup"><span data-stu-id="587ac-153">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="587ac-154">**Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**: Selecteer deze instelling om het beleid voor veilige koppelingen toe te passen op berichten tussen interne afzenders en interne geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="587ac-154">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="587ac-155">**Gebruikers niet op klikken volgen**: laat deze instelling uitgeschakeld om de gebruiker te laten klikken op url's in e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="587ac-155">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="587ac-156">**Gebruikers niet toestaan door de oorspronkelijke URL** te klikken: Selecteer deze instelling om te voorkomen dat gebruikers op de oorspronkelijke URL van [waarschuwings pagina's](atp-safe-links.md#warning-pages-from-safe-links)klikken.</span><span class="sxs-lookup"><span data-stu-id="587ac-156">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="587ac-157">**Schrijf niet de volgende url's** opnieuw op: Hiermee kan de opgegeven url's worden geopend die anders worden geblokkeerd door veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-157">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="587ac-158">Typ in het vak de gewenste URL of waarde en klik vervolgens op</span><span class="sxs-lookup"><span data-stu-id="587ac-158">In the box, type the URL or value that you want, and then click</span></span> ![Knoppictogram toevoegen](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="587ac-160">.</span><span class="sxs-lookup"><span data-stu-id="587ac-160">.</span></span>

     <span data-ttu-id="587ac-161">Als u een bestaande vermelding wilt verwijderen, selecteert u deze en klikt u op</span><span class="sxs-lookup"><span data-stu-id="587ac-161">To remove an existing entry, select it and then click</span></span> ![Pictogramknop verwijderen](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="587ac-163">.</span><span class="sxs-lookup"><span data-stu-id="587ac-163">.</span></span>

     <span data-ttu-id="587ac-164">Zie de [invoer syntaxis voor de lijst ' de volgende url's niet herschrijven ' voor de](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)invoer syntaxis.</span><span class="sxs-lookup"><span data-stu-id="587ac-164">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="587ac-165">Zie [instellingen voor veilige koppelingen voor e-mailberichten](atp-safe-links.md#safe-links-settings-for-email-messages) en [instellingen voor veilige koppelingen voor Microsoft teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams)voor meer informatie over deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-165">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="587ac-166">Zie [beleidsinstellingen voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)voor de aanbevolen waarden voor de standaard-en strikte beleidsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-166">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="587ac-167">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="587ac-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="587ac-168">Op de pagina **toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="587ac-168">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="587ac-169">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="587ac-169">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="587ac-170">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="587ac-170">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="587ac-171">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="587ac-171">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="587ac-172">Klik op **een voorwaarde toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="587ac-172">Click **Add a condition**.</span></span> <span data-ttu-id="587ac-173">Selecteer een voorwaarde in de vervolgkeuzelijst die wordt weergegeven **als**:</span><span class="sxs-lookup"><span data-stu-id="587ac-173">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="587ac-174">**De ontvanger is**: geeft een of meer postvakken, e-mail gebruikers of e-mail contactpersonen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="587ac-174">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="587ac-175">**De ontvanger is lid van**: Hiermee geeft u een of meer groepen op in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-175">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="587ac-176">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-176">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="587ac-177">Wanneer u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzelijst weergegeven met een **van deze** vakken.</span><span class="sxs-lookup"><span data-stu-id="587ac-177">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="587ac-178">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="587ac-178">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="587ac-179">Klik in het vak en begin te typen om de lijst te filteren en een waarde te selecteren.</span><span class="sxs-lookup"><span data-stu-id="587ac-179">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="587ac-180">Als u extra waarden wilt toevoegen, klikt u op een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="587ac-180">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="587ac-181">Als u afzonderlijke vermeldingen wilt verwijderen **, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de waarde.</span><span class="sxs-lookup"><span data-stu-id="587ac-181">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="587ac-182">Als u de hele voorwaarde wilt verwijderen **, klikt u op** ![ pictogram verwijderen ](../../media/scc-remove-icon.png) in de voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="587ac-182">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="587ac-183">Als u een extra voorwaarde wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een resterende waarde onder **toegepast als**.</span><span class="sxs-lookup"><span data-stu-id="587ac-183">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="587ac-184">Als u uitzonderingen wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een uitzondering onder **behalve als**.</span><span class="sxs-lookup"><span data-stu-id="587ac-184">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="587ac-185">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="587ac-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="587ac-186">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="587ac-186">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="587ac-187">Controleer de instellingen op de pagina **uw instellingen bekijken** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="587ac-187">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="587ac-188">U kunt op de verschillende instellingen klikken om de **bewerking** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="587ac-188">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="587ac-189">Wanneer u klaar bent, klikt u op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="587ac-189">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="587ac-190">Het Beveiligingscentrum beveiligings & gebruiken om beleidsregels voor veilige koppelingen weer te geven</span><span class="sxs-lookup"><span data-stu-id="587ac-190">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="587ac-191">Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen** voor het beleid voor bedreigings beheer.</span><span class="sxs-lookup"><span data-stu-id="587ac-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="587ac-192">Selecteer een beleid in de lijst op de pagina **veilige koppelingen** en klik erop (niet het selectievakje inschakelen).</span><span class="sxs-lookup"><span data-stu-id="587ac-192">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="587ac-193">De beleidsdetails worden in een uitgelichte vlucht weergegeven</span><span class="sxs-lookup"><span data-stu-id="587ac-193">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="587ac-194">Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige koppelingen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="587ac-194">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="587ac-195">Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen** voor het beleid voor bedreigings beheer.</span><span class="sxs-lookup"><span data-stu-id="587ac-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="587ac-196">Selecteer een beleid in de lijst op de pagina **veilige koppelingen** en klik erop (niet het selectievakje inschakelen).</span><span class="sxs-lookup"><span data-stu-id="587ac-196">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="587ac-197">Klik in de beleidsdetails die worden weergegeven, op **beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="587ac-197">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="587ac-198">Welke van de beschikbare instellingen in de vlucht die wordt weergegeven, zijn identiek aan de instellingen die worden beschreven in de sectie [het beveiligings & gebruiken om de beleidsregels voor veilige koppelingen te maken](#use-the-security--compliance-center-to-create-safe-links-policies) .</span><span class="sxs-lookup"><span data-stu-id="587ac-198">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="587ac-199">Zie de volgende secties als u een beleid wilt in-of uitschakelen of de prioriteitsvolgorde voor beleidsregels wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="587ac-199">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="587ac-200">Beleidsregels voor veilige koppelingen in-of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="587ac-200">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="587ac-201">Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen** voor het beleid voor bedreigings beheer.</span><span class="sxs-lookup"><span data-stu-id="587ac-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="587ac-202">Let op de waarde in de kolom **status** :</span><span class="sxs-lookup"><span data-stu-id="587ac-202">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="587ac-203">Verplaats te wisselknop naar links om het beleid uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="587ac-203">Move the toggle to the left to disable the policy:</span></span> ![Beleid uitschakelen](../../media/scc-toggle-off.png)<span data-ttu-id="587ac-205">.</span><span class="sxs-lookup"><span data-stu-id="587ac-205">.</span></span>

   - <span data-ttu-id="587ac-206">Verplaats te wisselknop naar rechts om het beleid in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="587ac-206">Move the toggle to the right to enable the policy:</span></span> ![Beleid inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="587ac-208">.</span><span class="sxs-lookup"><span data-stu-id="587ac-208">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="587ac-209">De prioriteit voor beleidsregels voor veilige koppelingen instellen</span><span class="sxs-lookup"><span data-stu-id="587ac-209">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="587ac-210">Beleidsregels voor veilige koppelingen krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwe policies zijn een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="587ac-210">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="587ac-211">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="587ac-211">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="587ac-212">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="587ac-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="587ac-213">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="587ac-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="587ac-214">Beleidsregels voor veilige koppelingen worden weergegeven in de volgorde waarin ze worden verwerkt ( **het eerste** beleid heeft de waarde 0).</span><span class="sxs-lookup"><span data-stu-id="587ac-214">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="587ac-215">**Opmerking**: in het beveiligings & nalevings centrum kunt u de prioriteit van het beleid voor veilige koppelingen alleen wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="587ac-215">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="587ac-216">In PowerShell kunt u de standaardprioriteit negeren wanneer u de regel voor veilige koppelingen maakt (die van invloed kunnen zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="587ac-216">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="587ac-217">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="587ac-217">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="587ac-218">Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen** voor het beleid voor bedreigings beheer.</span><span class="sxs-lookup"><span data-stu-id="587ac-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="587ac-219">Selecteer een beleid in de lijst op de pagina **veilige koppelingen** en klik erop (niet het selectievakje inschakelen).</span><span class="sxs-lookup"><span data-stu-id="587ac-219">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="587ac-220">Klik in het venster Details van het beleid dat wordt weergegeven op de knop beschikbare prioriteit:</span><span class="sxs-lookup"><span data-stu-id="587ac-220">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="587ac-221">Voor het beleid voor veilige koppelingen met de **prioriteits** waarde **0** is slechts de knop **prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="587ac-221">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="587ac-222">Het beleid voor veilige koppelingen met de laagste **prioriteits** waarde (bijvoorbeeld **3**) is alleen beschikbaar voor de knop **prioriteit verhogen** .</span><span class="sxs-lookup"><span data-stu-id="587ac-222">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="587ac-223">Als u een beleidsregels voor veilige koppelingen hebt, kunt u beleidsregels gebruiken tussen de waarden voor de hoogste en laagste prioriteit, en de knoppen prioriteit **verhogen** en **prioriteit verlagen** .</span><span class="sxs-lookup"><span data-stu-id="587ac-223">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="587ac-224">Klik op **prioriteit verhogen** of **prioriteit verkleinen** om de **prioriteits** waarde te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="587ac-224">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="587ac-225">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="587ac-225">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="587ac-226">Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige koppelingen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="587ac-226">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="587ac-227">Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen** voor het beleid voor bedreigings beheer.</span><span class="sxs-lookup"><span data-stu-id="587ac-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="587ac-228">Selecteer een beleid in de lijst op de pagina **veilige koppelingen** en klik erop (niet het selectievakje inschakelen).</span><span class="sxs-lookup"><span data-stu-id="587ac-228">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="587ac-229">Ga naar de details van het beleid dat wordt weergegeven, klik op **beleid verwijderen** en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="587ac-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="587ac-230">Beleidsregels voor veilige koppelingen met Exchange Online PowerShell of zelfstandige EOP PowerShell configureren</span><span class="sxs-lookup"><span data-stu-id="587ac-230">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="587ac-231">Zoals hierboven beschreven, bestaat een beleid voor veilige koppelingen van een beleid voor veilige koppelingen en een regel voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-231">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="587ac-232">In PowerShell is het verschil tussen beleid voor veilige koppelingen en regels voor veilige koppelingen duidelijk.</span><span class="sxs-lookup"><span data-stu-id="587ac-232">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="587ac-233">U beheert beleidsregels voor veilige koppelingen met behulp van de **\* SafeLinksPolicy-** cmdlets en u beheert regels voor veilige koppelingen met behulp van de cmdlets voor **\* SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="587ac-233">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="587ac-234">In PowerShell maakt u eerst het beleid voor veilige koppelingen en vervolgens maakt u de regel voor veilige koppelingen waarmee het beleid wordt aangegeven waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="587ac-234">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="587ac-235">In PowerShell wijzigt u de instellingen in het beleid voor veilige koppelingen en de regel voor veilige koppelingen afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="587ac-235">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="587ac-236">Wanneer u een beleid voor veilige koppelingen uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige koppelingen niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="587ac-236">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="587ac-237">PowerShell gebruiken om beleid voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="587ac-237">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="587ac-238">Het maken van een beleid voor veilige koppelingen in PowerShell is een procedure die bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="587ac-238">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="587ac-239">Maak het beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-239">Create the safe links policy.</span></span>
2. <span data-ttu-id="587ac-240">Maak de regel voor veilige koppelingen die het beleid voor veilige koppelingen opgeeft waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="587ac-240">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="587ac-241">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="587ac-241">**Notes**:</span></span>

- <span data-ttu-id="587ac-242">U kunt een nieuwe regel voor veilige koppelingen maken en hieraan een bestaand, niet-gekoppeld beleid voor veilige koppelingen toewijzen.</span><span class="sxs-lookup"><span data-stu-id="587ac-242">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="587ac-243">Een regel voor veilige koppelingen kan niet worden gekoppeld aan meer dan één beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-243">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="587ac-244">U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige koppelingen in PowerShell die niet beschikbaar zijn in het beveiligings & nalevings centrum voordat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="587ac-244">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="587ac-245">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld_ `$false` in de **nieuwe SafeLinksRule-** cmdlet).</span><span class="sxs-lookup"><span data-stu-id="587ac-245">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="587ac-246">De prioriteit van het beleid instellen voor het maken _Priority_ van de _\<Number\>_ **nieuwe SafeLinksRule-** cmdlet (prioriteit).</span><span class="sxs-lookup"><span data-stu-id="587ac-246">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="587ac-247">Een nieuw beleid voor veilige koppelingen dat u in PowerShell maakt, is niet zichtbaar in het beveiligings & nalevings centrum tot u het beleid aan een regel voor veilige koppelingen toewijst.</span><span class="sxs-lookup"><span data-stu-id="587ac-247">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="587ac-248">Stap 1: PowerShell gebruiken om een beleid voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="587ac-248">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="587ac-249">Als u een beleid voor veilige koppelingen wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="587ac-249">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="587ac-250">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="587ac-250">**Notes**:</span></span>

- <span data-ttu-id="587ac-251">Zie de [invoer syntaxis voor de lijst ' de volgende url's niet herschrijven '](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)voor meer informatie over de syntaxis van de _DoNotRewriteUrls_ -parameter.</span><span class="sxs-lookup"><span data-stu-id="587ac-251">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="587ac-252">Zie het gedeelte [beleidsregels voor veilige koppelingen in PowerShell gebruiken](#use-powershell-to-modify-safe-links-policies) voor het wijzigen van de beleidsregels voor veilige koppelingen in dit artikel voor meer informatie over het gebruik van de parameter _DoNotRewriteUrls_ wanneer u bestaande beleidsregels voor veilige koppelingen wijzigt met behulp van de cmdlet **set-SafeLinksPolicy** .</span><span class="sxs-lookup"><span data-stu-id="587ac-252">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="587ac-253">In dit voorbeeld wordt een beleid voor veilige koppelingen gemaakt met de naam contoso all en de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="587ac-253">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="587ac-254">Schakel URL Scanning in en herschrijf u in e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="587ac-254">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="587ac-255">Het scannen van URL'S in teams inschakelen (alleen op voorbeeld).</span><span class="sxs-lookup"><span data-stu-id="587ac-255">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="587ac-256">Schakel realtime scanning van geklikt url's in, waaronder geklikt koppelingen die naar bestanden verwijzen.</span><span class="sxs-lookup"><span data-stu-id="587ac-256">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="587ac-257">Wacht totdat URL-Scan is voltooid voordat u het bericht aflevert.</span><span class="sxs-lookup"><span data-stu-id="587ac-257">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="587ac-258">Schakel URL Scanning in en herschrijf voor interne berichten.</span><span class="sxs-lookup"><span data-stu-id="587ac-258">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="587ac-259">Gebruikers klikken met betrekking tot beveiliging van veilige koppelingen bijhouden (de parameter _DoNotTrackUserClicks_ wordt niet gebruikt en de standaardwaarde is $False, wat betekent dat de gebruiker klikt op bijhouden).</span><span class="sxs-lookup"><span data-stu-id="587ac-259">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="587ac-260">Gebruikers kunnen niet naar de oorspronkelijke URL klikken.</span><span class="sxs-lookup"><span data-stu-id="587ac-260">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="587ac-261">Zie [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-261">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="587ac-262">Stap 2: PowerShell gebruiken om een regel voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="587ac-262">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="587ac-263">Gebruik de volgende syntaxis om een regel voor veilige koppelingen te maken:</span><span class="sxs-lookup"><span data-stu-id="587ac-263">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="587ac-264">In dit voorbeeld wordt een regel voor veilige koppelingen gemaakt met de naam contoso all met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="587ac-264">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="587ac-265">De regel is gekoppeld aan het beleid voor veilige koppelingen met de naam contoso all.</span><span class="sxs-lookup"><span data-stu-id="587ac-265">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="587ac-266">De regel geldt voor alle geadresseerden in het contoso.com-domein.</span><span class="sxs-lookup"><span data-stu-id="587ac-266">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="587ac-267">Aangezien we de _prioriteits_ parameter niet gebruiken, wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="587ac-267">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="587ac-268">De regel is ingeschakeld (de _ingeschakelde_ parameter wordt niet gebruikt en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="587ac-268">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="587ac-269">Zie [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-269">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="587ac-270">PowerShell gebruiken om beleidsregels voor veilige koppelingen weer te geven</span><span class="sxs-lookup"><span data-stu-id="587ac-270">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="587ac-271">Als u bestaande beleidsregels voor veilige koppelingen wilt bekijken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="587ac-271">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="587ac-272">In dit voorbeeld wordt een overzichtslijst weergegeven met alle beleidsregels voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-272">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="587ac-273">In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor het beleid voor veilige koppelingen met de naam contoso-leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="587ac-273">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="587ac-274">Zie [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-274">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="587ac-275">PowerShell gebruiken om regels voor veilige koppelingen weer te geven</span><span class="sxs-lookup"><span data-stu-id="587ac-275">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="587ac-276">Als u bestaande regels voor veilige koppelingen wilt bekijken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="587ac-276">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="587ac-277">In dit voorbeeld wordt een overzichtslijst weergegeven met alle regels voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="587ac-277">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="587ac-278">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="587ac-278">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="587ac-279">In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor de regel voor veilige koppelingen met de naam contoso-leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="587ac-279">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="587ac-280">Zie [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-280">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="587ac-281">Beleidsregels voor veilige koppelingen wijzigen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="587ac-281">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="587ac-282">U kunt de naam van een beleid voor veilige koppelingen in PowerShell niet wijzigen (de cmdlet **set-SafeLinksPolicy** heeft geen _naam_ parameter).</span><span class="sxs-lookup"><span data-stu-id="587ac-282">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="587ac-283">Wanneer u de naam van een beleid voor veilige koppelingen in het beveiligings & nalevings centrum wijzigt, kunt u alleen de naam van de _regel_ voor veilige koppelingen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="587ac-283">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="587ac-284">De enige extra overweging voor het wijzigen van het beleid voor veilige koppelingen in PowerShell is de beschikbare syntaxis voor de parameter _DoNotRewriteUrls_ (de [lijst ' de volgende url's niet herschrijven '](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="587ac-284">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="587ac-285">Als u waarden wilt toevoegen waarmee bestaande vermeldingen worden vervangen, gebruikt u de volgende syntaxis: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="587ac-285">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="587ac-286">Gebruik de volgende syntaxis om waarden toe te voegen of te verwijderen zonder dat dit invloed heeft op andere bestaande vermeldingen: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="587ac-286">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="587ac-287">U kunt ook dezelfde instellingen gebruiken als u een beleid voor veilige koppelingen maakt zoals wordt beschreven in de sectie [stap 1: PowerShell gebruiken om een beleid voor veilige koppelingen te maken](#step-1-use-powershell-to-create-a-safe-links-policy) eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="587ac-287">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="587ac-288">Als u een beleid voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="587ac-288">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="587ac-289">Zie [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-289">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="587ac-290">PowerShell gebruiken om regels voor veilige koppelingen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="587ac-290">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="587ac-291">De enige instelling die niet beschikbaar is wanneer u een regel voor veilige koppelingen in PowerShell wijzigt, is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="587ac-291">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="587ac-292">Zie de volgende sectie als u bestaande regels voor veilige koppelingen wilt in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="587ac-292">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="587ac-293">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals wordt beschreven in de sectie [stap 2: PowerShell gebruiken om een sectie voor veilige koppelingen te maken](#step-2-use-powershell-to-create-a-safe-links-rule) eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="587ac-293">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="587ac-294">Als u een regel voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="587ac-294">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="587ac-295">Zie [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-295">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="587ac-296">PowerShell gebruiken om regels voor veilige koppelingen in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="587ac-296">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="587ac-297">Door een regel voor veilige koppelingen in of uit te schakelen in PowerShell wordt het volledige beleid voor veilige koppelingen en het beleid voor veilige koppelingen uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="587ac-297">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="587ac-298">Gebruik de volgende syntaxis om een regel voor veilige koppelingen in PowerShell in of uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="587ac-298">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="587ac-299">In dit voorbeeld wordt de regel voor veilige koppelingen genaamd marketing afdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="587ac-299">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="587ac-300">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="587ac-300">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="587ac-301">Zie [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) en [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-301">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="587ac-302">PowerShell gebruiken voor het instellen van de prioriteit van regels voor veilige koppelingen</span><span class="sxs-lookup"><span data-stu-id="587ac-302">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="587ac-303">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="587ac-303">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="587ac-304">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="587ac-304">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="587ac-305">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="587ac-305">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="587ac-306">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="587ac-306">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="587ac-307">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="587ac-307">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="587ac-308">Als u de prioriteit wilt instellen van een regel voor veilige koppelingen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="587ac-308">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="587ac-309">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="587ac-309">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="587ac-310">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="587ac-310">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="587ac-311">**Opmerking**: als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u de parameter _Priority_ op de cmdlet **New-SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="587ac-311">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="587ac-312">Zie [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-312">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="587ac-313">Beleidsregels voor veilige koppelingen verwijderen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="587ac-313">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="587ac-314">Wanneer u met PowerShell een beleid voor veilige koppelingen verwijdert, wordt de bijbehorende regel voor veilige koppelingen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="587ac-314">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="587ac-315">Als u een beleid voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="587ac-315">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="587ac-316">In dit voorbeeld wordt het beleid voor veilige koppelingen met de naam marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="587ac-316">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="587ac-317">Zie [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-317">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="587ac-318">PowerShell gebruiken om regels voor veilige koppelingen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="587ac-318">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="587ac-319">Wanneer u PowerShell gebruikt om een regel voor veilige koppelingen te verwijderen, wordt het bijbehorende beleid voor veilige koppelingen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="587ac-319">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="587ac-320">Als u een regel voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="587ac-320">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="587ac-321">In dit voorbeeld wordt de regel voor veilige koppelingen met de naam marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="587ac-321">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="587ac-322">Zie [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="587ac-322">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="587ac-323">Als u wilt controleren of de optie voor veilige koppelingen berichten scant, controleert u de beschikbare rapporten voor Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="587ac-323">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="587ac-324">Voor meer informatie raadpleegt u [rapporten weergeven voor Defender voor Office 365](view-reports-for-atp.md) en [gebruikt u de Verkenner in het beveiligings & nalevings centrum](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="587ac-324">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="587ac-325">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="587ac-325">How do you know these procedures worked?</span></span>

<span data-ttu-id="587ac-326">Voer een van de volgende stappen uit om te controleren of u het beleid voor veilige koppelingen hebt gemaakt, gewijzigd of verwijderd:</span><span class="sxs-lookup"><span data-stu-id="587ac-326">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="587ac-327">Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen** voor het beleid voor bedreigings beheer.</span><span class="sxs-lookup"><span data-stu-id="587ac-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="587ac-328">Controleer de lijst met beleidsregels, de **status** waarden en de waarden van de **prioriteit** .</span><span class="sxs-lookup"><span data-stu-id="587ac-328">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="587ac-329">Als u meer informatie wilt bekijken, selecteert u het beleid in de lijst en bekijkt u de details in de vlucht.</span><span class="sxs-lookup"><span data-stu-id="587ac-329">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="587ac-330">In Exchange Online PowerShell of Exchange Online Protection PowerShell vervangt u \<Name\> de naam van het beleid of de regel door de volgende opdracht uit te voeren en de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="587ac-330">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
