---
title: Beleidsregels Safe Koppelingen instellen in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het weergeven, maken, wijzigen en verwijderen van Safe Koppelingenbeleid en algemene Safe Koppelingen-instellingen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d1e0257fd124a53b2191ad8025ce42dc13a2e23e
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096766"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f4b2e-103">Beleidsregels Safe Koppelingen instellen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f4b2e-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f4b2e-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-104">**Applies to**</span></span>
- [<span data-ttu-id="f4b2e-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f4b2e-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f4b2e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4b2e-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="f4b2e-107">Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](defender-for-office-365.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="f4b2e-108">Als u een thuisgebruiker bent die informatie zoekt over Safelinks in Outlook, gaat u naar [Advanced Outlook.com-beveiliging.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="f4b2e-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="f4b2e-109">Safe Koppelingen in [Microsoft Defender voor Office 365](defender-for-office-365.md) biedt URL-scan van binnenkomende e-mailberichten in de e-mailstroom en het tijdstip van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="f4b2e-110">Zie Koppelingen in Microsoft Defender voor Safe voor [meer Office 365.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="f4b2e-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="f4b2e-111">Er is geen ingebouwd of standaardkoppelingsbeleid Safe koppelingen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="f4b2e-112">Als u Safe koppelingen van URL's wilt scannen, moet u een of meer Safe Koppelingenbeleid maken, zoals in dit artikel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="f4b2e-113">U configureert de algemene instellingen voor Safe koppelingen **buiten** Safe koppelingenbeleid.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="f4b2e-114">Zie Algemene instellingen [configureren voor Safe koppelingen in Microsoft Defender](configure-global-settings-for-safe-links.md)voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="f4b2e-115">Beheerders moeten rekening houden met de verschillende configuratie-instellingen voor Safe koppelingen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="f4b2e-116">Een van de beschikbare opties is het opnemen van gebruikersgegevens in Safe Koppelingen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="f4b2e-117">Met deze functie kunnen *Beveiligingsops-teams* mogelijke gebruikerscompromitteerden onderzoeken, corrigerende actie ondernemen en dure inbreuken beperken.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="f4b2e-118">U kunt Safe Koppelingen-beleid configureren in de Microsoft 365 Defender-portal of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="f4b2e-119">De basiselementen van een Safe koppelingenbeleid zijn:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="f4b2e-120">Het beleid voor veilige **koppelingen:** schakel Safe Koppelingenbeveiliging in, schakel realtime URL-scan in, geef op of het scannen in realtime moet worden voltooid voordat het bericht wordt verzonden, schakel het scannen van interne berichten in, geef op of gebruikers klikken op URL's moeten bijhouden en geef op of gebruikers mogen klikken op de oorspronkelijke URL.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="f4b2e-121">**De regel veilige koppelingen:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="f4b2e-122">Het verschil tussen deze twee elementen is niet duidelijk wanneer u het beleid Safe Koppelingen in de Microsoft 365 Defender beheren:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-122">The difference between these two elements isn't obvious when you manage Safe Links policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="f4b2e-123">Wanneer u een Safe koppelingenbeleid maakt, maakt u tegelijkertijd een veilige koppelingsregel en het bijbehorende beleid voor veilige koppelingen met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="f4b2e-124">Wanneer u een Safe koppelingenbeleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de regel voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="f4b2e-125">Alle andere instellingen wijzigen het beleid voor gekoppelde veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="f4b2e-126">Wanneer u een Safe koppelingenbeleid verwijdert, worden de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="f4b2e-127">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="f4b2e-128">Zie de sectie Gebruik Exchange Online PowerShell of zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) voor het configureren Safe koppelingenbeleid verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4b2e-129">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="f4b2e-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f4b2e-130">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="f4b2e-131">Als u rechtstreeks naar de pagina Safe **koppelingen wilt** gaan, gebruikt <https://security.microsoft.com/safelinksv2> u .</span><span class="sxs-lookup"><span data-stu-id="f4b2e-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="f4b2e-132">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f4b2e-133">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f4b2e-134">U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f4b2e-135">Als u beleidsregels voor Safe-koppelingen wilt maken, wijzigen en  verwijderen,  moet u lid zijn van de rollengroepen Organisatiebeheer of Beveiligingsbeheerder in de Microsoft 365 Defender-portal en lid zijn van de rollengroep Organisatiebeheer in Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="f4b2e-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="f4b2e-136">Voor alleen-lezen toegang tot Safe koppelingenbeleid, moet u lid  zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f4b2e-137">Zie Machtigingen [in de](permissions-microsoft-365-security-center.md) Microsoft 365 Defender portal en [Machtigingen in](/exchange/permissions-exo/permissions-exo)Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="f4b2e-138">Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in de _Microsoft 365 Defender-portal_ en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f4b2e-139">Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="f4b2e-140">.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-140">.</span></span> <span data-ttu-id="f4b2e-141">- De **rollengroep Alleen-weergeven voor** organisatiebeheer [in](/Exchange/permissions-exo/permissions-exo#role-groups) Exchange Online biedt ook alleen-lezen toegang tot de functie.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="f4b2e-142">Zie voor onze aanbevolen instellingen voor Safe [Koppelingenbeleid Safe Beleidsinstellingen voor koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="f4b2e-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="f4b2e-143">Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="f4b2e-144">[Er worden voortdurend nieuwe functies toegevoegd aan Microsoft Defender voor Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="f4b2e-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="f4b2e-145">Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande Safe koppelingenbeleid aanpassen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="f4b2e-146">Gebruik de Microsoft 365 Defender portal om Safe koppelingenbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="f4b2e-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="f4b2e-147">Als u een aangepast Safe koppelingenbeleid maakt in de Microsoft 365 Defender portal, worden de regels voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen tegelijk gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="f4b2e-148">Ga in Microsoft 365 Defender portal naar De sectie **Beleidsregels & beleidsregels** voor bedreigingsbeleid \>  \>  \> **Safe Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f4b2e-149">Klik op **Safe pagina Koppelingen** op Pictogram Maken ![ ](../../media/m365-cc-sc-create-icon.png) **maken.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="f4b2e-150">De **wizard Nieuw Safe koppelingen wordt** geopend.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="f4b2e-151">Configureer **op de pagina** Naam uw beleid de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="f4b2e-152">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="f4b2e-153">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="f4b2e-154">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f4b2e-155">Identificeer op **de pagina Gebruikers** en domeinen die wordt weergegeven de interne geadresseerden op wie het beleid van toepassing is (voorwaarden voor geadresseerden):</span><span class="sxs-lookup"><span data-stu-id="f4b2e-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="f4b2e-156">**Gebruikers**: de opgegeven postvakken, e-mailgebruikers or e-mailcontactpersonen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="f4b2e-157">**Groepen**: de opgegeven distributiegroepen, beveiligingsgroepen met e-mail of Microsoft 365-groepen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="f4b2e-158">**Domeinen**: alle geadresseerden in de opgegeven [geaccepteerde domeinen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="f4b2e-159">Klik in het juiste vak, begin een waarde te typen en selecteer de gewenste waarde in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="f4b2e-160">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="f4b2e-161">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="f4b2e-161">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="f4b2e-163">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-163">next to the value.</span></span>

   <span data-ttu-id="f4b2e-164">Voor gebruikers of groepen kunt u de meeste id's (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) gebruiken, maar de bijbehorende weergavenaam wordt weergegeven in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="f4b2e-165">Voer voor gebruikers een enkel sterretje (\*) in om alle beschikbare waarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="f4b2e-166">Meerdere waarden in dezelfde voorwaarde: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="f4b2e-167">Verschillende voorwaarden: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="f4b2e-168">**Deze gebruikers, groepen** en domeinen uitsluiten: Als u uitzonderingen wilt toevoegen voor de interne geadresseerden waar het beleid op van toepassing is (uitzonderingen voor geadresseerden), selecteert u deze optie en configureert u de uitzonderingen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recipient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="f4b2e-169">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="f4b2e-170">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f4b2e-171">Configureer **de volgende** instellingen op de pagina Beveiligingsinstellingen die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="f4b2e-172">**Selecteer de actie voor onbekende potentieel schadelijke URL's in** berichten: Selecteer **Aan** om Safe koppelingen in te stellen voor koppelingen in e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="f4b2e-173">Als u deze instelling in wilt stellen, zijn de volgende instellingen beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="f4b2e-174">**Realtime URL-scan toepassen** op verdachte koppelingen en koppelingen die naar bestanden wijzen: Selecteer deze optie om het scannen van koppelingen in e-mailberichten in realtime in te stellen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="f4b2e-175">Als u deze instelling in de volgende instelling in zet, is deze beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="f4b2e-176">**Wacht totdat URL-scannen is** voltooid voordat u het bericht bezorgt: Selecteer deze optie om te wachten totdat het scannen van url's in realtime is voltooid voordat het bericht wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="f4b2e-177">**De Safe koppelingen** toepassen op e-mailberichten die binnen de organisatie zijn verzonden: Selecteer deze optie om het Safe Koppelingen-beleid toe te passen op berichten tussen interne afzenders en interne geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="f4b2e-178">Selecteer de actie voor onbekende of potentieel schadelijke **URL's** in Microsoft Teams : Selecteer **Aan** om de beveiliging van koppelingen in te Safe koppelingen in Teams.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="f4b2e-179">**Gebruikersklikken niet bijhouden:** laat deze instelling niet geselecteerd om het bijhouden van gebruikersklikken op URL's in e-mailberichten in te stellen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="f4b2e-180">**Gebruikers mogen niet doorklikken** naar de oorspronkelijke URL: Selecteer deze optie om te blokkeren dat gebruikers doorklikken naar de oorspronkelijke URL op [waarschuwingspagina's.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="f4b2e-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="f4b2e-181">**De volgende URL's niet** opnieuw schrijven: Hiermee krijgt u toegang tot de opgegeven URL's die anders door Safe worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="f4b2e-182">Typ in het vak de URL of waarde die u wilt gebruiken en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="f4b2e-183">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="f4b2e-184">Als u een bestaand item wilt verwijderen, klikt u op</span><span class="sxs-lookup"><span data-stu-id="f4b2e-184">To remove an existing entry, click</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="f4b2e-186">naast het item.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-186">next to the entry.</span></span>

     <span data-ttu-id="f4b2e-187">Zie De syntaxis van de vermelding voor de lijst 'De volgende URL's niet opnieuw [schrijven'.](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="f4b2e-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="f4b2e-188">Zie voor meer informatie over deze [instellingen de instellingen Safe Koppelingen](safe-links.md#safe-links-settings-for-email-messages) voor e-mailberichten en Safe Koppelingen voor [Microsoft Teams.](safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="f4b2e-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="f4b2e-189">Zie voor meer informatie over de aanbevolen waarden voor standaard- en strikte beleidsinstellingen [Safe Beleidsinstellingen koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="f4b2e-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="f4b2e-190">Wanneer je klaar bent, klik je op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f4b2e-191">Selecteer op **de** pagina Melding die wordt weergegeven een van de volgende waarden voor Hoe wilt u uw gebruikers **op de hoogte stellen?**:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="f4b2e-192">**De standaardmeldingstekst gebruiken**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="f4b2e-193">**Aangepaste meldingstekst gebruiken:** als u deze waarde selecteert (de lengte mag niet groter zijn dan 200 tekens), worden de volgende instellingen weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-193">**Use custom notification text**: If you select this value (the length cannot exceed 200 characters), the following settings appear:</span></span>
     - <span data-ttu-id="f4b2e-194">**Gebruik Microsoft Translator voor automatische lokalisatie**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="f4b2e-195">**Aangepaste meldingstekst:** Voer de aangepaste meldingstekst in dit vak in.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="f4b2e-196">Wanneer je klaar bent, klik je op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f4b2e-197">Controleer uw instellingen op de pagina **Controleren** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="f4b2e-198">U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="f4b2e-199">U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="f4b2e-200">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="f4b2e-201">Klik op de bevestigingspagina die wordt weergegeven op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="f4b2e-202">Gebruik de Microsoft 365 Defender portal om de Safe koppelingen weer te Safe</span><span class="sxs-lookup"><span data-stu-id="f4b2e-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="f4b2e-203">Ga in Microsoft 365 Defender portal naar De sectie **Beleidsregels & beleidsregels** voor bedreigingsbeleid \>  \>  \> **Safe Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f4b2e-204">Op de **Safe pagina Koppelingen** worden de volgende eigenschappen weergegeven in de lijst met Safe Koppelingenbeleid:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="f4b2e-205">**Naam**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-205">**Name**</span></span>
   - <span data-ttu-id="f4b2e-206">**Status**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-206">**Status**</span></span>
   - <span data-ttu-id="f4b2e-207">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-207">**Priority**</span></span>

3. <span data-ttu-id="f4b2e-208">Wanneer u een beleid selecteert door op de naam te klikken, worden de beleidsinstellingen weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="f4b2e-209">Gebruik de Microsoft 365 Defender portal om het beleid voor koppelingen Safe wijzigen</span><span class="sxs-lookup"><span data-stu-id="f4b2e-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="f4b2e-210">Ga in Microsoft 365 Defender portal naar De sectie **Beleidsregels & beleidsregels** voor bedreigingsbeleid \>  \>  \> **Safe Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f4b2e-211">Selecteer op **Safe pagina Koppelingen** een beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="f4b2e-212">U kunt in de flyout met beleidsdetails in elke sectie de optie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="f4b2e-213">Zie de vorige portal De [](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) portal Microsoft 365 Defender gebruiken om Safe koppelingenbeleid te maken in dit artikel voor meer informatie over de instellingen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="f4b2e-214">Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteitsvolgorde wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="f4b2e-215">Beleidsregels voor koppelingen in- Safe uitschakelen</span><span class="sxs-lookup"><span data-stu-id="f4b2e-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="f4b2e-216">Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & \> **beleidsregels** voor bedreigingsbeleidsregels Safe \>  \>  \> **Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f4b2e-217">Selecteer op **Safe pagina Koppelingen** een beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="f4b2e-218">Boven aan de flyout met beleidsdetails die wordt weergegeven, ziet u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="f4b2e-219">**Beleid uitgeschakeld**: als u het beleid wilt inschakelen, klikt u op ![Pictogram inschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Inschakelen** .</span><span class="sxs-lookup"><span data-stu-id="f4b2e-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="f4b2e-220">**Beleid ingeschakeld**: als u het beleid wilt uitschakelen, klikt u op ![Pictogram uitschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="f4b2e-221">Klik in het bevestigingsvenster dat wordt weergegeven op **Inschakelen** of **Uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="f4b2e-222">Klik in de flyout met beleidsdetails op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="f4b2e-223">Op de hoofdbeleidspagina wordt de waarde **Status** van het beleid weergegeven als **Ingeschakeld** of **Uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="f4b2e-224">De prioriteit instellen van Safe koppelingenbeleid</span><span class="sxs-lookup"><span data-stu-id="f4b2e-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="f4b2e-225">Standaard krijgen Safe koppelingen een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="f4b2e-226">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f4b2e-227">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="f4b2e-228">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **Prioriteitsnummer** niet rechtstreeks wijzigen in de Microsoft 365 Defender-portal).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="f4b2e-229">Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="f4b2e-230">**Opmerking**:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-230">**Note**:</span></span>

- <span data-ttu-id="f4b2e-231">In de Microsoft 365 Defender portal kunt u alleen de prioriteit van het Safe koppelingen wijzigen nadat u deze hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="f4b2e-232">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de regel veilige koppelingen maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="f4b2e-233">Safe Koppelingenbeleid wordt verwerkt in de volgorde waarin ze worden weergegeven (het eerste beleid heeft de **waarde** Prioriteit 0).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="f4b2e-234">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="f4b2e-235">Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & \> **beleidsregels** voor bedreigingsbeleidsregels Safe \>  \>  \> **Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f4b2e-236">Selecteer op **Safe pagina Koppelingen** een beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="f4b2e-237">Boven aan de flyout met beleidsgegevens die wordt weergegeven, ziet u **Prioriteit verhogen** of **Prioriteit verlagen** op basis van de huidige prioriteitswaarde en het aantal aangepaste beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="f4b2e-238">Het beleid met **prioriteitswaarde** **0** heeft alleen de **optie Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="f4b2e-239">Het beleid met de laagste **prioriteitswaarde** (bijvoorbeeld **3)** heeft alleen de optie **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="f4b2e-240">Als u drie of meer beleidsregels hebt, hebben de  beleidsregels  tussen de waarden met de hoogste en laagste prioriteit zowel de opties Prioriteit verhogen als Prioriteit verlagen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="f4b2e-241">Klik op het ![pictogram Prioriteit verhogen](../../media/m365-cc-sc-increase-icon.png) **Prioriteit verhogen** of ![Pictogram Prioriteit verlagen](../../media/m365-cc-sc-decrease-icon.png) **Prioriteit verlagen** om de **Prioriteitswaarde** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="f4b2e-242">Wanneer u klaar bent, klikt u in de flyout met beleidsdetails op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="f4b2e-243">Gebruik de Microsoft 365 Defender portal om het beleid voor koppelingen Safe verwijderen</span><span class="sxs-lookup"><span data-stu-id="f4b2e-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="f4b2e-244">Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & \> **beleidsregels** voor bedreigingsbeleidsregels Safe \>  \>  \> **Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="f4b2e-245">Selecteer op **Safe pagina Koppelingen** een beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="f4b2e-246">Klik boven aan de flyout met beleidsdetails die wordt weergegeven, op het ![pictogram Meer acties](../../media/m365-cc-sc-more-actions-icon.png) **Meer acties** \> ![Pictogram Beleid verwijderen](../../media/m365-cc-sc-delete-icon.png) **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="f4b2e-247">Klik in het bevestigingsvenster dat wordt weergegeven op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="f4b2e-248">Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om Safe koppelingenbeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="f4b2e-248">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="f4b2e-249">Zoals eerder beschreven, Safe beleid voor koppelingen bestaat uit een beleid voor veilige koppelingen en een regel voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-249">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="f4b2e-250">In PowerShell is het verschil tussen beleidsregels voor veilige koppelingen en regels voor veilige koppelingen duidelijk.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-250">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="f4b2e-251">U beheert beleidsregels voor veilige koppelingen met behulp van **\* de cmdlets -SafeLinksPolicy** en u beheert regels voor veilige koppelingen met behulp van **\* de cmdlets -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-251">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="f4b2e-252">In PowerShell maakt u eerst het beleid voor veilige koppelingen en vervolgens maakt u de regel voor veilige koppelingen waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-252">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="f4b2e-253">In PowerShell wijzigt u de instellingen in het beleid voor veilige koppelingen en de regel voor veilige koppelingen afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-253">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="f4b2e-254">Wanneer u een beleid voor veilige koppelingen uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige koppelingen niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-254">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="f4b2e-255">PowerShell gebruiken om Safe koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="f4b2e-255">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="f4b2e-256">Het maken Safe beleid voor koppelingen in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-256">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f4b2e-257">Maak het beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-257">Create the safe links policy.</span></span>
2. <span data-ttu-id="f4b2e-258">Maak de regel veilige koppelingen die het beleid voor veilige koppelingen aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-258">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f4b2e-259">U kunt een nieuwe regel voor veilige koppelingen maken en er een bestaand, niet-verbonden beleid voor veilige koppelingen aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-259">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="f4b2e-260">Een veilige koppelingsregel kan niet worden gekoppeld aan meer dan één beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-260">A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id="f4b2e-261">U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige koppelingen in PowerShell die pas beschikbaar zijn in de Microsoft 365 Defender portal nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-261">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id="f4b2e-262">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **Nieuw-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="f4b2e-263">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="f4b2e-264">Een nieuw beleid voor veilige koppelingen dat u in PowerShell maakt, is pas zichtbaar in de Microsoft 365 Defender portal als u het beleid aan een regel voor veilige koppelingen toewijst.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="f4b2e-265">Stap 1: PowerShell gebruiken om een beleid voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="f4b2e-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="f4b2e-266">Gebruik de volgende syntaxis om een beleid voor veilige koppelingen te maken:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="f4b2e-267">Zie De [syntaxis](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)van de vermelding voor de volgende URL's niet opnieuw schrijven voor meer informatie over de syntaxis van de invoer die u wilt gebruiken voor de parameter _DoNotRewriteUrls._</span><span class="sxs-lookup"><span data-stu-id="f4b2e-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="f4b2e-268">Zie de sectie [PowerShell](#use-powershell-to-modify-safe-links-policies) gebruiken om beleidsregels voor veilige koppelingen te wijzigen verderop in dit artikel voor aanvullende syntaxis die u kunt gebruiken voor de parameter _DoNotRewriteUrls_ wanneer u bestaande beleidsregels voor veilige koppelingen wijzigt met de cmdlet **Set-SafeLinksPolicy.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="f4b2e-269">In dit voorbeeld wordt een beleid voor veilige koppelingen met de naam Contoso All gemaakt met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="f4b2e-270">Schakel URL's scannen en herschrijven in e-mailberichten in.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="f4b2e-271">URL's scannen in Teams in (alleen TAP Preview).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="f4b2e-272">Schakel realtime scannen in van geklikte URL's, inclusief geklikte koppelingen die naar bestanden wijzen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="f4b2e-273">Wacht totdat URL-scannen is voltooid voordat u het bericht bezorgt.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="f4b2e-274">Schakel URL's scannen en herschrijven in voor interne berichten.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="f4b2e-275">Gebruikersklikken bijhouden met betrekking tot Safe Koppelingenbeveiliging (we gebruiken de parameter _DoNotTrackUserClicks_ niet en de standaardwaarde is $false, wat betekent dat gebruikersklikken worden bijgepuurd).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="f4b2e-276">Gebruikers mogen niet doorklikken naar de oorspronkelijke URL.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="f4b2e-277">Zie [Nieuw-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="f4b2e-278">Stap 2: PowerShell gebruiken om een regel voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="f4b2e-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="f4b2e-279">Als u een regel voor veilige koppelingen wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="f4b2e-280">In dit voorbeeld wordt een veilige koppelingsregel met de naam Contoso All gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="f4b2e-281">De regel is gekoppeld aan het beleid voor veilige koppelingen met de naam Contoso All.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="f4b2e-282">De regel is van toepassing op alle geadresseerden in het contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="f4b2e-283">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="f4b2e-284">De regel is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="f4b2e-285">Zie [Nieuw-SafeLinksRule](/powershell/module/exchange/new-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="f4b2e-286">PowerShell gebruiken om beleidsregels voor veilige koppelingen weer te geven</span><span class="sxs-lookup"><span data-stu-id="f4b2e-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="f4b2e-287">Gebruik de volgende syntaxis als u bestaand beleid voor veilige koppelingen wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f4b2e-288">In dit voorbeeld wordt een overzichtslijst met alle beleidsregels voor veilige koppelingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="f4b2e-289">Dit voorbeeld retourneert gedetailleerde informatie voor het beleid voor veilige koppelingen met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="f4b2e-290">Zie [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="f4b2e-291">PowerShell gebruiken om regels voor veilige koppelingen weer te geven</span><span class="sxs-lookup"><span data-stu-id="f4b2e-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="f4b2e-292">Als u bestaande regels voor veilige koppelingen wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f4b2e-293">In dit voorbeeld wordt een overzichtslijst met alle regels voor veilige koppelingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="f4b2e-294">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="f4b2e-295">Dit voorbeeld retourneert gedetailleerde informatie voor de regel voor veilige koppelingen met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="f4b2e-296">Zie [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="f4b2e-297">PowerShell gebruiken om beleidsregels voor veilige koppelingen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="f4b2e-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="f4b2e-298">U kunt de naam van een beleid voor veilige koppelingen niet wijzigen in PowerShell (de cmdlet **Set-SafeLinksPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="f4b2e-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f4b2e-299">Wanneer u de naam van een Safe koppelingenbeleid in de Microsoft 365 Defender portal wijzigt, wijzigt u alleen de naam van de regel voor veilige _koppelingen._</span><span class="sxs-lookup"><span data-stu-id="f4b2e-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="f4b2e-300">De enige extra overweging voor het wijzigen van beleidsregels voor veilige koppelingen in PowerShell is de beschikbare syntaxis voor de parameter _DoNotRewriteUrls_ (de lijst 'De volgende URL's niet [herschrijven'):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="f4b2e-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="f4b2e-301">Als u waarden wilt toevoegen die bestaande vermeldingen vervangen, gebruikt u de volgende syntaxis: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="f4b2e-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="f4b2e-302">Als u waarden wilt toevoegen of verwijderen zonder dat dit van invloed is op andere bestaande vermeldingen, gebruikt u de volgende syntaxis: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="f4b2e-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="f4b2e-303">Anders zijn dezelfde instellingen beschikbaar wanneer u een beleid voor veilige koppelingen maakt, zoals beschreven in stap [1: PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) gebruiken om eerder in dit artikel een beleidssectie voor veilige koppelingen te maken.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="f4b2e-304">Als u een beleid voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f4b2e-305">Zie [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="f4b2e-306">PowerShell gebruiken om regels voor veilige koppelingen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="f4b2e-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="f4b2e-307">De enige instelling die niet beschikbaar is wanneer u een regel voor veilige koppelingen in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f4b2e-308">Zie de volgende sectie als u bestaande regels voor veilige koppelingen wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="f4b2e-309">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) gebruiken om eerder in dit artikel een sectie met veilige koppelingen te maken.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="f4b2e-310">Als u een regel voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f4b2e-311">Zie [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="f4b2e-312">PowerShell gebruiken om regels voor veilige koppelingen in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="f4b2e-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="f4b2e-313">Als u een regel voor veilige koppelingen in PowerShell in- of uitschakelen, wordt het hele Safe-koppelingenbeleid (de regel voor veilige koppelingen en het toegewezen beleid voor veilige koppelingen) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="f4b2e-314">Als u een regel voor veilige koppelingen in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="f4b2e-315">In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f4b2e-316">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f4b2e-317">Zie Enable-SafeLinksRule and Disable-SafeLinksRule [(Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule)](/powershell/module/exchange/disable-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="f4b2e-318">PowerShell gebruiken om de prioriteit van regels voor veilige koppelingen in te stellen</span><span class="sxs-lookup"><span data-stu-id="f4b2e-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="f4b2e-319">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-319">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f4b2e-320">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-320">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f4b2e-321">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-321">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f4b2e-322">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-322">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f4b2e-323">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-323">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f4b2e-324">Als u de prioriteit van een regel voor veilige koppelingen in PowerShell wilt instellen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f4b2e-325">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-325">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="f4b2e-326">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="f4b2e-326">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="f4b2e-327">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de **cmdlet Nieuw-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="f4b2e-328">Zie [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="f4b2e-329">PowerShell gebruiken om beleidsregels voor veilige koppelingen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="f4b2e-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="f4b2e-330">Wanneer u PowerShell gebruikt om een beleid voor veilige koppelingen te verwijderen, wordt de bijbehorende regel voor veilige koppelingen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="f4b2e-331">Als u een beleid voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f4b2e-332">In dit voorbeeld wordt het beleid voor veilige koppelingen met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f4b2e-333">Zie [Remove-SafeLinksPolicy (Verwijderen-SafeLinksPolicy)](/powershell/module/exchange/remove-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="f4b2e-334">PowerShell gebruiken om regels voor veilige koppelingen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="f4b2e-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="f4b2e-335">Wanneer u PowerShell gebruikt om een veilige koppelingsregel te verwijderen, wordt het bijbehorende beleid voor veilige koppelingen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="f4b2e-336">Als u een regel voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="f4b2e-337">In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f4b2e-338">Zie [Remove-SafeLinksRule voor](/powershell/module/exchange/remove-safelinksrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="f4b2e-339">Als u wilt controleren Safe koppelingen berichten scannen, controleert u de beschikbare Microsoft Defender voor Office 365 rapporten.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="f4b2e-340">Zie Rapporten weergeven voor [Defender](view-reports-for-mdo.md) voor Office 365 En Verkenner gebruiken in de [Microsoft 365 Defender portal voor meer informatie.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="f4b2e-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f4b2e-341">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="f4b2e-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="f4b2e-342">Als u wilt controleren of u beleidsregels voor koppelingen hebt gemaakt, gewijzigd of Safe hebt verwijderd, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="f4b2e-343">Ga in Microsoft 365 Defender portal naar **Beleidsregels &** \> **bedreigingsbeleid** \> **Safe Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="f4b2e-344">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="f4b2e-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="f4b2e-345">Als u meer details wilt weergeven, selecteert u het beleid in de lijst en bekijkt u de details in de fly-out.</span><span class="sxs-lookup"><span data-stu-id="f4b2e-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="f4b2e-346">Vervang Exchange Online PowerShell of Exchange Online Protection PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en controleer \<Name\> de instellingen:</span><span class="sxs-lookup"><span data-stu-id="f4b2e-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
