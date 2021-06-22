---
title: Het beleid Safe bijlagen instellen in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Meer informatie over het definiëren van Safe bijlagenbeleid om uw organisatie te beschermen tegen schadelijke bestanden in e-mail.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7220140c25ecf457b42514356e41aabdf5481bb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054333"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="363a0-103">Het beleid Safe bijlagen instellen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="363a0-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="363a0-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="363a0-104">**Applies to**</span></span>
- [<span data-ttu-id="363a0-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="363a0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="363a0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="363a0-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="363a0-107">Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](whats-new-in-defender-for-office-365.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="363a0-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="363a0-108">Als u een thuisgebruiker bent die informatie zoekt over het scannen van bijlagen in Outlook, gaat u naar [Geavanceerde Outlook.com-beveiliging.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="363a0-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="363a0-109">Safe Bijlagen is een functie in [Microsoft Defender](whats-new-in-defender-for-office-365.md) voor Office 365 die een virtuele omgeving gebruikt om bijlagen in binnenkomende e-mailberichten te controleren nadat ze zijn gescand door [anti-malwarebeveiliging in Exchange Online Protection (EOP),](anti-malware-protection.md)maar vóór de bezorging aan geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="363a0-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="363a0-110">Zie voor meer informatie [Safe Bijlagen in Microsoft Defender voor Office 365.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="363a0-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="363a0-111">Er is geen ingebouwd of standaardbeleid Safe bijlagen.</span><span class="sxs-lookup"><span data-stu-id="363a0-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="363a0-112">Als u Safe bijlagen van e-mailbijlagen wilt scannen, moet u een of meer Safe bijlagenbeleid maken, zoals in dit artikel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="363a0-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="363a0-113">U kunt Safe Bijlagen-beleid configureren in de Microsoft 365 Defender-portal of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Defender voor Office 365-invoegabonnementen).</span><span class="sxs-lookup"><span data-stu-id="363a0-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="363a0-114">De basiselementen van een Safe bijlagenbeleid zijn:</span><span class="sxs-lookup"><span data-stu-id="363a0-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="363a0-115">**Het beleid** voor veilige bijlagen: geeft de acties voor onbekende malwaredetecties op, of berichten met malwarebijlagen naar een opgegeven e-mailadres moeten worden verzonden en of berichten moeten worden verzonden als Safe Bijlagen scannen niet kan worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="363a0-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="363a0-116">**De veilige bijlageregel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is).</span><span class="sxs-lookup"><span data-stu-id="363a0-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="363a0-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u het Safe bijlagen in de portal Microsoft 365 Defender beheren:</span><span class="sxs-lookup"><span data-stu-id="363a0-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="363a0-118">Wanneer u een Safe-bijlagebeleid maakt, maakt u tegelijkertijd een veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="363a0-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="363a0-119">Wanneer u een Safe bijlagenbeleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de veilige bijlageregel.</span><span class="sxs-lookup"><span data-stu-id="363a0-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="363a0-120">Alle andere instellingen wijzigen het bijbehorende beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="363a0-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="363a0-121">Wanneer u een Safe bijlagebeleid verwijdert, worden de veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="363a0-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="363a0-122">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="363a0-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="363a0-123">Zie de sectie Use [Exchange Online PowerShell Safe standalone EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="363a0-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="363a0-124">In het gebied met algemene instellingen Safe bijlagen configureert u functies die niet afhankelijk zijn van Safe bijlagenbeleid.</span><span class="sxs-lookup"><span data-stu-id="363a0-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="363a0-125">Zie Safe Bijlagen in [SharePoint, OneDrive](turn-on-mdo-for-spo-odb-and-teams.md) en Microsoft Teams en Safe in Microsoft 365 E5 voor [instructies.](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="363a0-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="363a0-126">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="363a0-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="363a0-127">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="363a0-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="363a0-128">Als u rechtstreeks naar de pagina Safe **bijlagen** wilt gaan, gebruikt u <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="363a0-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="363a0-129">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="363a0-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="363a0-130">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="363a0-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="363a0-131">U hebt machtigingen nodig voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="363a0-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="363a0-132">Als u Safe Bijlagebeleid wilt maken, wijzigen en verwijderen, moet  u  lid zijn van de rollengroepen Organisatiebeheer of  Beveiligingsbeheerder in de Microsoft 365 Defender-portal  en lid zijn van de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="363a0-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="363a0-133">Als u alleen-lezen toegang wilt tot Safe-bijlagenbeleid, moet  u  lid zijn van de rollengroepen Globale lezer of Beveiligingslezer in de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="363a0-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="363a0-134">Zie Machtigingen [in de](permissions-microsoft-365-security-center.md) Microsoft 365 Defender portal en [Machtigingen in](/exchange/permissions-exo/permissions-exo)Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="363a0-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="363a0-135">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="363a0-135">**Notes**:</span></span>

  - <span data-ttu-id="363a0-136">Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in de _Microsoft 365 Defender-portal_ en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="363a0-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="363a0-137">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="363a0-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="363a0-138">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="363a0-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="363a0-139">Zie voor onze aanbevolen instellingen voor Safe bijlagenbeleid [de Safe Bijlagen.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="363a0-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="363a0-140">Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="363a0-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="363a0-141">Gebruik de Microsoft 365 Defender portal om een Safe bijlagen te maken</span><span class="sxs-lookup"><span data-stu-id="363a0-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="363a0-142">Als u een aangepast Safe-bijlagebeleid maakt in de Microsoft 365 Defender-portal, worden de veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen tegelijk gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="363a0-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="363a0-143">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingsbeleid & regels Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Safe Bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="363a0-143">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="363a0-144">Klik op **Safe pagina Bijlagen** op Pictogram Maken ![ ](../../media/m365-cc-sc-create-icon.png) **maken.**</span><span class="sxs-lookup"><span data-stu-id="363a0-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="363a0-145">De wizard van het beleid wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="363a0-145">The policy wizard opens.</span></span> <span data-ttu-id="363a0-146">Configureer **op de pagina** Naam uw beleid de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="363a0-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="363a0-147">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="363a0-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="363a0-148">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="363a0-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="363a0-149">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="363a0-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="363a0-150">Identificeer op **de pagina Gebruikers** en domeinen die wordt weergegeven de interne geadresseerden op wie het beleid van toepassing is (voorwaarden voor geadresseerden):</span><span class="sxs-lookup"><span data-stu-id="363a0-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="363a0-151">**Gebruikers**: de opgegeven postvakken, e-mailgebruikers or e-mailcontactpersonen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="363a0-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="363a0-152">**Groepen**: de opgegeven distributiegroepen, beveiligingsgroepen met e-mail of Microsoft 365-groepen binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="363a0-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="363a0-153">**Domeinen**: alle geadresseerden in de opgegeven [geaccepteerde domeinen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="363a0-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="363a0-154">Klik in het juiste vak, begin een waarde te typen en selecteer de gewenste waarde in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="363a0-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="363a0-155">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="363a0-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="363a0-156">Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen</span><span class="sxs-lookup"><span data-stu-id="363a0-156">To remove an existing value, click remove</span></span> ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="363a0-158">naast de waarde.</span><span class="sxs-lookup"><span data-stu-id="363a0-158">next to the value.</span></span>

   <span data-ttu-id="363a0-159">Voor gebruikers of groepen kunt u de meeste id's (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) gebruiken, maar de bijbehorende weergavenaam wordt weergegeven in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="363a0-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="363a0-160">Voer voor gebruikers een enkel sterretje (\*) in om alle beschikbare waarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="363a0-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="363a0-161">Meerdere waarden in dezelfde voorwaarde: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="363a0-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="363a0-162">Verschillende voorwaarden: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="363a0-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="363a0-163">**Deze gebruikers, groepen en domeinen uitsluiten**: als u uitzonderingen wilt toevoegen voor de interne geadresseerden op wie het beleid van toepassing is (uitzonderingen op ontvangers), selecteert u deze optie en configureert u de uitzonderingen.</span><span class="sxs-lookup"><span data-stu-id="363a0-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="363a0-164">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="363a0-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="363a0-165">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="363a0-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="363a0-166">Configureer **op Instellingen** pagina de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="363a0-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="363a0-167">**Safe Antwoord op onbekende malware bijlagen:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="363a0-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="363a0-168">**Uit:** Deze waarde wordt meestal niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="363a0-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="363a0-169">**Monitor**</span><span class="sxs-lookup"><span data-stu-id="363a0-169">**Monitor**</span></span>
     - <span data-ttu-id="363a0-170">**Blok:** Dit is de standaardwaarde en de aanbevolen waarde in standaard- en strikt [vooraf ingestelde beveiligingsbeleidsregels.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="363a0-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="363a0-171">**Vervangen**</span><span class="sxs-lookup"><span data-stu-id="363a0-171">**Replace**</span></span>
     - <span data-ttu-id="363a0-172">**Dynamische bezorging (voorbeeldfunctie)**</span><span class="sxs-lookup"><span data-stu-id="363a0-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="363a0-173">Deze waarden worden uitgelegd in [Safe instellingen voor bijlagenbeleid.](safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="363a0-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="363a0-174">Berichten omleiden met gedetecteerde **bijlagen:** Als u Omleiding inschakelen selecteert, kunt u een e-mailadres opgeven in het vak Berichten verzenden die **geblokkeerde,** bewaakte of vervangen bijlagen bevatten aan het opgegeven e-mailadresvak om berichten te verzenden die malwarebijlagen bevatten voor analyse en onderzoek.</span><span class="sxs-lookup"><span data-stu-id="363a0-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="363a0-175">De aanbeveling voor standaard- en strikte beleidsinstellingen is om omleiding in te stellen.</span><span class="sxs-lookup"><span data-stu-id="363a0-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="363a0-176">Zie de instellingen Safe [Bijlagen voor meer informatie.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="363a0-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="363a0-177">De detectiereactie Safe Bijlagen toepassen als scannen niet kan worden voltooid **(time-out** of fouten) : De actie die is opgegeven door **Safe Attachments unknown malware response** wordt toegepast op berichten, zelfs wanneer Safe het scannen van bijlagen niet kan worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="363a0-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="363a0-178">Als u deze optie hebt geselecteerd, selecteert u altijd **Omleiding inschakelen** en geeft u een e-mailadres op om berichten te verzenden die malwarebijlagen bevatten.</span><span class="sxs-lookup"><span data-stu-id="363a0-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="363a0-179">Anders kunnen berichten verloren gaan.</span><span class="sxs-lookup"><span data-stu-id="363a0-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="363a0-180">Wanneer je klaar bent, klik je op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="363a0-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="363a0-181">Controleer uw instellingen op de pagina **Controleren** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="363a0-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="363a0-182">U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="363a0-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="363a0-183">U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.</span><span class="sxs-lookup"><span data-stu-id="363a0-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="363a0-184">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="363a0-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="363a0-185">Klik op de bevestigingspagina die wordt weergegeven op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="363a0-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="363a0-186">Gebruik de Microsoft 365 Defender portal om de Safe bijlagen te bekijken</span><span class="sxs-lookup"><span data-stu-id="363a0-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="363a0-187">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingsbeleid & regels Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Safe Bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="363a0-187">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="363a0-188">Op de **Safe bijlagen worden** de volgende eigenschappen weergegeven in de lijst met beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="363a0-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="363a0-189">**Naam**</span><span class="sxs-lookup"><span data-stu-id="363a0-189">**Name**</span></span>
   - <span data-ttu-id="363a0-190">**Status**</span><span class="sxs-lookup"><span data-stu-id="363a0-190">**Status**</span></span>
   - <span data-ttu-id="363a0-191">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="363a0-191">**Priority**</span></span>

3. <span data-ttu-id="363a0-192">Wanneer u een beleid selecteert door op de naam te klikken, worden de beleidsinstellingen weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="363a0-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="363a0-193">Gebruik de Microsoft 365 Defender portal om het beleid voor bijlagen Safe wijzigen</span><span class="sxs-lookup"><span data-stu-id="363a0-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="363a0-194">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingsbeleid & regels Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Safe Bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="363a0-194">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="363a0-195">Selecteer op **Safe pagina Bijlagen** een beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="363a0-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="363a0-196">U kunt in de flyout met beleidsdetails in elke sectie de optie **Bewerken** selecteren om de instellingen in de sectie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="363a0-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="363a0-197">Zie de sectie Het Microsoft 365 Defender [](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) portal gebruiken om Safe bijlagenbeleid te maken eerder in dit artikel voor meer informatie over de instellingen.</span><span class="sxs-lookup"><span data-stu-id="363a0-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="363a0-198">Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteitsvolgorde wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="363a0-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="363a0-199">Het beleid voor bijlagen Safe in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="363a0-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="363a0-200">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingsbeleid & regels Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Safe Bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="363a0-200">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="363a0-201">Selecteer op **Safe pagina Bijlagen** een beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="363a0-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="363a0-202">Boven aan de flyout met beleidsdetails die wordt weergegeven, ziet u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="363a0-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="363a0-203">**Beleid uitgeschakeld**: als u het beleid wilt inschakelen, klikt u op ![Pictogram inschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Inschakelen** .</span><span class="sxs-lookup"><span data-stu-id="363a0-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="363a0-204">**Beleid ingeschakeld**: als u het beleid wilt uitschakelen, klikt u op ![Pictogram uitschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="363a0-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="363a0-205">Klik in het bevestigingsvenster dat wordt weergegeven op **Inschakelen** of **Uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="363a0-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="363a0-206">Klik in de flyout met beleidsdetails op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="363a0-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="363a0-207">Op de hoofdbeleidspagina wordt de waarde **Status** van het beleid weergegeven als **Ingeschakeld** of **Uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="363a0-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="363a0-208">De prioriteit van het Safe bijlagen instellen</span><span class="sxs-lookup"><span data-stu-id="363a0-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="363a0-209">Standaard krijgen Safe bijlagenbeleid een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="363a0-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="363a0-210">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="363a0-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="363a0-211">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="363a0-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="363a0-212">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="363a0-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="363a0-213">Safe Bijlagenbeleid wordt weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="363a0-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="363a0-214">**Opmerking:** In de Microsoft 365 Defender portal kunt u alleen de prioriteit van het Safe bijlagen wijzigen nadat u deze hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="363a0-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="363a0-215">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de veilige bijlageregel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="363a0-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="363a0-216">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **Prioriteitsnummer** niet rechtstreeks wijzigen in de Microsoft 365 Defender-portal).</span><span class="sxs-lookup"><span data-stu-id="363a0-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="363a0-217">Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="363a0-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="363a0-218">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingsbeleid & regels Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Safe Bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="363a0-218">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="363a0-219">Selecteer op **Safe pagina Bijlagen** een beleid in de lijst door op de naam te klikken.</span><span class="sxs-lookup"><span data-stu-id="363a0-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="363a0-220">Boven aan het flyout met beleidsdetails dat  wordt  weergegeven, ziet u Prioriteit verhogen of Prioriteit verlagen op basis van de huidige prioriteitswaarde en het aantal beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="363a0-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="363a0-221">Het beleid met **prioriteitswaarde** **0** heeft alleen de **optie Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="363a0-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="363a0-222">Het beleid met de laagste **prioriteitswaarde** (bijvoorbeeld **3)** heeft alleen de optie **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="363a0-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="363a0-223">Als u drie of meer beleidsregels hebt, hebben de  beleidsregels  tussen de waarden met de hoogste en laagste prioriteit zowel de opties Prioriteit verhogen als Prioriteit verlagen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="363a0-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="363a0-224">Klik op het ![pictogram Prioriteit verhogen](../../media/m365-cc-sc-increase-icon.png) **Prioriteit verhogen** of ![Pictogram Prioriteit verlagen](../../media/m365-cc-sc-decrease-icon.png) **Prioriteit verlagen** om de **Prioriteitswaarde** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="363a0-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="363a0-225">Wanneer u klaar bent, klikt u in de flyout met beleidsdetails op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="363a0-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="363a0-226">Gebruik de Microsoft 365 Defender portal om de Safe bijlagen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="363a0-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="363a0-227">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingsbeleid & regels Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Safe Bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="363a0-227">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="363a0-228">Selecteer op **Safe pagina Bijlagen** een aangepast beleid in de lijst door op de naam van het beleid te klikken.</span><span class="sxs-lookup"><span data-stu-id="363a0-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="363a0-229">Klik boven aan de flyout met beleidsdetails die wordt weergegeven, op het ![pictogram Meer acties](../../media/m365-cc-sc-more-actions-icon.png) **Meer acties** \> ![Pictogram Beleid verwijderen](../../media/m365-cc-sc-delete-icon.png) **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="363a0-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="363a0-230">Klik in het bevestigingsvenster dat wordt weergegeven op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="363a0-230">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="363a0-231">Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om het Safe bijlagen te configureren</span><span class="sxs-lookup"><span data-stu-id="363a0-231">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="363a0-232">Zoals eerder beschreven, bestaat Safe bijlagebeleid uit een beleid voor veilige bijlagen en een veilige bijlageregel.</span><span class="sxs-lookup"><span data-stu-id="363a0-232">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="363a0-233">In PowerShell is het verschil tussen beleidsregels voor veilige bijlagen en regels voor veilige bijlagen duidelijk.</span><span class="sxs-lookup"><span data-stu-id="363a0-233">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="363a0-234">U beheert beleidsregels voor veilige bijlagen met behulp van **\* de cmdlets -SafeAttachmentPolicy** en u beheert regels voor veilige bijlagen met de **\* cmdlets -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="363a0-234">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="363a0-235">In PowerShell maakt u eerst het beleid voor veilige bijlagen en vervolgens maakt u de veilige bijlageregel waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="363a0-235">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="363a0-236">In PowerShell wijzigt u de instellingen in het beleid voor veilige bijlagen en de regel voor veilige bijlagen afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="363a0-236">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="363a0-237">Wanneer u een veilig bijlagebeleid uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige bijlagen niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="363a0-237">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="363a0-238">PowerShell gebruiken om een Safe te maken</span><span class="sxs-lookup"><span data-stu-id="363a0-238">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="363a0-239">Het maken van Safe bijlagebeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="363a0-239">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="363a0-240">Maak het beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="363a0-240">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="363a0-241">Maak de veilige bijlageregel die het beleid voor veilige bijlagen aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="363a0-241">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="363a0-242">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="363a0-242">**Notes**:</span></span>

- <span data-ttu-id="363a0-243">U kunt een nieuwe veilige bijlageregel maken en er een bestaand, niet-verbonden beleid voor veilige bijlagen aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="363a0-243">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="363a0-244">Een veilige bijlageregel kan niet worden gekoppeld aan meer dan één beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="363a0-244">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="363a0-245">U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige bijlagen in PowerShell die pas beschikbaar zijn in de Microsoft 365 Defender portal nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="363a0-245">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="363a0-246">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="363a0-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="363a0-247">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="363a0-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="363a0-248">Een nieuw beleid voor veilige bijlagen dat u maakt in PowerShell, is niet zichtbaar in de Microsoft 365 Defender portal totdat u het beleid aan een veilige bijlageregel toewijst.</span><span class="sxs-lookup"><span data-stu-id="363a0-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="363a0-249">Stap 1: PowerShell gebruiken om een veilig bijlagebeleid te maken</span><span class="sxs-lookup"><span data-stu-id="363a0-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="363a0-250">Als u een beleid voor veilige bijlagen wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="363a0-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="363a0-251">In dit voorbeeld wordt een beleid voor veilige bijlagen met de naam Contoso All gemaakt met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="363a0-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="363a0-252">Blokkeer berichten die malware bevatten door documenten Safe scannen (we gebruiken de _parameter_ Actie niet en de standaardwaarde is `Block` ).</span><span class="sxs-lookup"><span data-stu-id="363a0-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="363a0-253">Omleiding is ingeschakeld en berichten die malware bevatten, worden naar sec-ops@contoso.com verzonden voor analyse en onderzoek.</span><span class="sxs-lookup"><span data-stu-id="363a0-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="363a0-254">Als Safe het scannen van bijlagen niet beschikbaar is of fouten ondervindt, levert u het bericht niet op (we gebruiken de parameter _ActionOnError_ niet en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="363a0-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="363a0-255">Zie [New-SafeAttachmentPolicy (Nieuw-SafeAttachmentPolicy)](/powershell/module/exchange/new-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="363a0-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="363a0-256">Stap 2: PowerShell gebruiken om een veilige bijlageregel te maken</span><span class="sxs-lookup"><span data-stu-id="363a0-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="363a0-257">Als u een veilige bijlageregel wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="363a0-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="363a0-258">In dit voorbeeld wordt een veilige bijlageregel met de naam Contoso All gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="363a0-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="363a0-259">De regel is gekoppeld aan het beleid voor veilige bijlagen met de naam Contoso All.</span><span class="sxs-lookup"><span data-stu-id="363a0-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="363a0-260">De regel is van toepassing op alle geadresseerden in het contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="363a0-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="363a0-261">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="363a0-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="363a0-262">De regel is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="363a0-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="363a0-263">Zie [New-SafeAttachmentRule voor](/powershell/module/exchange/new-safeattachmentrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="363a0-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="363a0-264">PowerShell gebruiken om beleidsregels voor veilige bijlagen weer te geven</span><span class="sxs-lookup"><span data-stu-id="363a0-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="363a0-265">Gebruik de volgende syntaxis als u bestaande beleidsregels voor veilige bijlagen wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="363a0-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="363a0-266">In dit voorbeeld wordt een overzichtslijst met alle beleidsregels voor veilige bijlagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="363a0-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="363a0-267">Dit voorbeeld retourneert gedetailleerde informatie voor het beleid voor veilige bijlagen met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="363a0-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="363a0-268">Zie [Get-SafeAttachmentPolicy (Get-SafeAttachmentPolicy)](/powershell/module/exchange/get-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="363a0-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="363a0-269">PowerShell gebruiken om regels voor veilige bijlagen weer te geven</span><span class="sxs-lookup"><span data-stu-id="363a0-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="363a0-270">Als u bestaande regels voor veilige bijlagen wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="363a0-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="363a0-271">In dit voorbeeld wordt een overzichtslijst met alle regels voor veilige bijlagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="363a0-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="363a0-272">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="363a0-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="363a0-273">Dit voorbeeld retourneert gedetailleerde informatie voor de veilige bijlageregel met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="363a0-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="363a0-274">Zie [Get-SafeAttachmentRule (Get-SafeAttachmentRule)](/powershell/module/exchange/get-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="363a0-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="363a0-275">PowerShell gebruiken om beleidsregels voor veilige bijlagen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="363a0-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="363a0-276">U kunt de naam van een beleid voor veilige bijlagen niet wijzigen in PowerShell (de cmdlet **Set-SafeAttachmentPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="363a0-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="363a0-277">Wanneer u de naam van een Safe bijlagebeleid in de Microsoft 365 Defender portal wijzigt, wijzigt u alleen de naam van de regel voor veilige _bijlagen._</span><span class="sxs-lookup"><span data-stu-id="363a0-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="363a0-278">Anders zijn dezelfde instellingen beschikbaar wanneer u een beleid voor veilige bijlagen maakt, zoals wordt beschreven in stap [1: PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) gebruiken om eerder in dit artikel een sectie voor het beleid voor veilige bijlagen te maken.</span><span class="sxs-lookup"><span data-stu-id="363a0-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="363a0-279">Als u een beleid voor veilige bijlagen wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="363a0-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="363a0-280">Zie [Set-SafeAttachmentPolicy (Set-SafeAttachmentPolicy)](/powershell/module/exchange/set-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="363a0-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="363a0-281">PowerShell gebruiken om regels voor veilige bijlagen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="363a0-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="363a0-282">De enige instelling die niet beschikbaar is wanneer u een veilige bijlageregel in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="363a0-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="363a0-283">Zie de volgende sectie als u bestaande regels voor veilige bijlagen wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="363a0-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="363a0-284">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals beschreven in stap [2: Gebruik PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) om eerder in dit artikel een sectie met veilige bijlageregel te maken.</span><span class="sxs-lookup"><span data-stu-id="363a0-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="363a0-285">Als u een veilige bijlageregel wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="363a0-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="363a0-286">Zie [Set-SafeAttachmentRule (Set-SafeAttachmentRule)](/powershell/module/exchange/set-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="363a0-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="363a0-287">PowerShell gebruiken om regels voor veilige bijlagen in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="363a0-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="363a0-288">Als u een veilige bijlageregel in PowerShell in- of uitschakelen, wordt het hele Safe-bijlagebeleid (de veilige bijlageregel en het toegewezen beleid voor veilige bijlagen) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="363a0-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="363a0-289">Als u een veilige bijlageregel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="363a0-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="363a0-290">In dit voorbeeld wordt de veilige bijlageregel marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="363a0-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="363a0-291">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="363a0-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="363a0-292">Zie [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule (Enable-SafeAttachmentRule en Disable-SafeAttachmentRule)](/powershell/module/exchange/disable-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="363a0-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="363a0-293">PowerShell gebruiken om de prioriteit van regels voor veilige bijlagen in te stellen</span><span class="sxs-lookup"><span data-stu-id="363a0-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="363a0-294">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="363a0-294">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="363a0-295">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="363a0-295">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="363a0-296">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="363a0-296">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="363a0-297">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="363a0-297">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="363a0-298">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="363a0-298">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="363a0-299">Als u de prioriteit van een veilige bijlageregel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="363a0-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="363a0-300">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="363a0-300">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="363a0-301">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="363a0-301">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="363a0-302">**Opmerking:** Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u de parameter _Prioriteit_ op de cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="363a0-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="363a0-303">Zie [Set-SafeAttachmentRule (Set-SafeAttachmentRule)](/powershell/module/exchange/set-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="363a0-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="363a0-304">PowerShell gebruiken om beleid voor veilige bijlagen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="363a0-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="363a0-305">Wanneer u PowerShell gebruikt om een beleid voor veilige bijlagen te verwijderen, wordt de bijbehorende regel voor veilige bijlagen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="363a0-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="363a0-306">Als u een beleid voor veilige bijlagen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="363a0-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="363a0-307">In dit voorbeeld wordt het beleid voor veilige bijlagen met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="363a0-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="363a0-308">Zie [Remove-SafeAttachmentPolicy (Remove-SafeAttachmentPolicy)](/powershell/module/exchange/remove-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="363a0-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="363a0-309">PowerShell gebruiken om regels voor veilige bijlagen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="363a0-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="363a0-310">Wanneer u PowerShell gebruikt om een veilige bijlageregel te verwijderen, wordt het bijbehorende beleid voor veilige bijlagen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="363a0-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="363a0-311">Als u een veilige bijlageregel in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="363a0-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="363a0-312">In dit voorbeeld wordt de veilige bijlageregel marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="363a0-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="363a0-313">Zie [Remove-SafeAttachmentRule (Remove-SafeAttachmentRule)](/powershell/module/exchange/remove-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="363a0-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="363a0-314">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="363a0-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="363a0-315">Als u wilt controleren of u het beleid voor bijlagen hebt gemaakt, gewijzigd of Safe verwijderd, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="363a0-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="363a0-316">Ga in Microsoft 365 Defender portal naar **E-mail** & samenwerkingsbeleid & regels Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Safe Bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="363a0-316">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="363a0-317">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="363a0-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="363a0-318">Als u meer details wilt weergeven, selecteert u het beleid in de lijst door op de naam te klikken en de details in de fly-out weer te geven.</span><span class="sxs-lookup"><span data-stu-id="363a0-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="363a0-319">Vervang Exchange Online PowerShell of Exchange Online Protection PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en controleer \<Name\> de instellingen:</span><span class="sxs-lookup"><span data-stu-id="363a0-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="363a0-320">Als u wilt controleren Safe bijlagen berichten scannen, controleert u de beschikbare Defender voor Office 365 rapporten.</span><span class="sxs-lookup"><span data-stu-id="363a0-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="363a0-321">Zie Rapporten weergeven voor [Defender](view-reports-for-mdo.md) voor Office 365 En Verkenner gebruiken in de [Microsoft 365 Defender portal voor meer informatie.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="363a0-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
