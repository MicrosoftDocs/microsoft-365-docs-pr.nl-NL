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
ms.openlocfilehash: 40ae52cfce53c3fa14253a94e72f1a2bccda9a86
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929825"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0d241-103">Beleidsregels Safe Koppelingen instellen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0d241-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0d241-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="0d241-104">**Applies to**</span></span>
- [<span data-ttu-id="0d241-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0d241-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0d241-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d241-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="0d241-107">Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](defender-for-office-365.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="0d241-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="0d241-108">Als u een thuisgebruiker bent die informatie zoekt over Safelinks in Outlook, gaat u naar [Advanced Outlook.com-beveiliging.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="0d241-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="0d241-109">Safe Koppelingen is een functie in [Microsoft Defender voor Office 365](defender-for-office-365.md) waarmee url's worden gescand van binnenkomende e-mailberichten in de e-mailstroom en de tijd van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties.</span><span class="sxs-lookup"><span data-stu-id="0d241-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="0d241-110">Zie Koppelingen in Microsoft Defender voor Safe voor [meer Office 365.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="0d241-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="0d241-111">Er is geen ingebouwd of standaardkoppelingsbeleid Safe koppelingen.</span><span class="sxs-lookup"><span data-stu-id="0d241-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="0d241-112">Als u Safe koppelingen van URL's wilt scannen, moet u een of meer Safe Koppelingenbeleid maken, zoals in dit artikel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="0d241-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="0d241-113">U configureert de algemene instellingen voor Safe koppelingen **buiten** Safe koppelingenbeleid.</span><span class="sxs-lookup"><span data-stu-id="0d241-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="0d241-114">Zie Algemene instellingen [configureren voor Safe koppelingen in Microsoft Defender](configure-global-settings-for-safe-links.md)voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="0d241-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="0d241-115">U kunt Safe Koppelingen-beleid configureren in de Microsoft 365 Defender-portal of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).</span><span class="sxs-lookup"><span data-stu-id="0d241-115">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="0d241-116">De basiselementen van een Safe koppelingenbeleid zijn:</span><span class="sxs-lookup"><span data-stu-id="0d241-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="0d241-117">Het beleid voor veilige **koppelingen:** schakel Safe Koppelingenbeveiliging in, schakel realtime URL-scan in, geef op of het scannen in realtime moet worden voltooid voordat het bericht wordt verzonden, schakel het scannen van interne berichten in, geef op of gebruikers klikken op URL's moeten bijhouden en geef op of gebruikers mogen klikken op de oorspronkelijke URL.</span><span class="sxs-lookup"><span data-stu-id="0d241-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="0d241-118">**De regel veilige koppelingen:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is).</span><span class="sxs-lookup"><span data-stu-id="0d241-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d241-119">Beheerders moeten rekening houden met de verschillende configuratie-instellingen voor SafeLinks.</span><span class="sxs-lookup"><span data-stu-id="0d241-119">Admins should consider the different configuration settings for SafeLinks.</span></span> <span data-ttu-id="0d241-120">Een van de beschikbare opties is het opnemen van gebruikersgegevens in SafeLinks.</span><span class="sxs-lookup"><span data-stu-id="0d241-120">One of the available options is to include user identifiable information in SafeLinks.</span></span> <span data-ttu-id="0d241-121">Met deze functie kunnen *Beveiligingsops-teams* mogelijke gebruikerscompromitteerden onderzoeken, corrigerende actie ondernemen en dure inbreuken beperken.</span><span class="sxs-lookup"><span data-stu-id="0d241-121">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="0d241-122">Het verschil tussen deze twee elementen is niet duidelijk wanneer u de Safe koppelingen in de portal Microsoft 365 Defender beheert:</span><span class="sxs-lookup"><span data-stu-id="0d241-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="0d241-123">Wanneer u een Safe koppelingenbeleid maakt, maakt u tegelijkertijd een veilige koppelingsregel en het bijbehorende beleid voor veilige koppelingen met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="0d241-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="0d241-124">Wanneer u een Safe koppelingenbeleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de regel voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="0d241-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="0d241-125">Alle andere instellingen wijzigen het beleid voor gekoppelde veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="0d241-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="0d241-126">Wanneer u een Safe koppelingenbeleid verwijdert, worden de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0d241-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="0d241-127">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="0d241-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="0d241-128">Zie de sectie Gebruik Exchange Online PowerShell of zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) voor het configureren Safe koppelingenbeleid verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0d241-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0d241-129">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="0d241-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0d241-130">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="0d241-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="0d241-131">Als u rechtstreeks naar de pagina Safe **koppelingen wilt** gaan, gebruikt <https://security.microsoft.com/safelinksv2> u .</span><span class="sxs-lookup"><span data-stu-id="0d241-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="0d241-132">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d241-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0d241-133">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d241-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0d241-134">U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0d241-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0d241-135">Als u beleidsregels voor Safe-koppelingen wilt maken, wijzigen en  verwijderen,  moet u lid zijn van de rollengroepen Organisatiebeheer  of Beveiligingsbeheerder in de Microsoft 365 Defender-portal  en lid zijn van de rollengroep Organisatiebeheer in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d241-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="0d241-136">Voor alleen-lezen toegang tot Safe koppelingenbeleid, moet u lid  zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="0d241-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="0d241-137">Zie Machtigingen [in de](permissions-in-the-security-and-compliance-center.md) Defender Microsoft 365 portal en [Machtigingen in](/exchange/permissions-exo/permissions-exo)Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d241-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="0d241-138">Als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol in het Microsoft 365-beheercentrum, krijgen  gebruikers de vereiste machtigingen in de Microsoft 365 Defender-portal en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d241-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0d241-139">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0d241-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="0d241-140">.</span><span class="sxs-lookup"><span data-stu-id="0d241-140">.</span></span> <span data-ttu-id="0d241-141">- De **rollengroep Alleen-weergeven voor** organisatiebeheer [in](/Exchange/permissions-exo/permissions-exo#role-groups) Exchange Online biedt ook alleen-lezen toegang tot de functie.</span><span class="sxs-lookup"><span data-stu-id="0d241-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="0d241-142">Zie voor onze aanbevolen instellingen voor Safe [Koppelingenbeleid Safe Beleidsinstellingen voor koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="0d241-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="0d241-143">Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="0d241-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="0d241-144">[Er worden voortdurend nieuwe functies toegevoegd aan Microsoft Defender voor Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="0d241-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="0d241-145">Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande Safe koppelingenbeleid aanpassen.</span><span class="sxs-lookup"><span data-stu-id="0d241-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="0d241-146">Gebruik de Microsoft 365 Defender-portal om beleidsregels voor koppelingen Safe maken</span><span class="sxs-lookup"><span data-stu-id="0d241-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="0d241-147">Als u een aangepast Safe-koppelingenbeleid maakt in de Microsoft 365 Defender-portal, worden de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen tegelijk gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="0d241-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="0d241-148">Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** \> **bedreigingsbeleid Safe** \> **Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="0d241-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="0d241-149">Klik op **Safe pagina Koppelingen** op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="0d241-149">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="0d241-150">De **wizard Nieuw Safe koppelingen wordt** geopend.</span><span class="sxs-lookup"><span data-stu-id="0d241-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="0d241-151">Configureer **op de pagina** Naam uw beleid de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="0d241-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="0d241-152">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="0d241-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="0d241-153">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="0d241-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="0d241-154">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0d241-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0d241-155">Configureer **op Instellingen** pagina die wordt weergegeven de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="0d241-155">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0d241-156">**Selecteer de actie voor onbekende potentieel schadelijke URL's in** berichten: Selecteer **Aan** om Safe koppelingen in te stellen voor koppelingen in e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="0d241-156">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="0d241-157">Selecteer de actie voor onbekende of potentieel schadelijke **URL's** in Microsoft Teams : Selecteer **Aan** om de beveiliging van koppelingen in te Safe koppelingen in Teams.</span><span class="sxs-lookup"><span data-stu-id="0d241-157">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="0d241-158">**Realtime URL-scan toepassen** op verdachte koppelingen en koppelingen die naar bestanden wijzen: Selecteer deze instelling om het scannen van koppelingen in e-mailberichten in realtime mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="0d241-158">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="0d241-159">**Wacht totdat URL-scannen is** voltooid voordat het bericht wordt weergegeven: Selecteer deze instelling om te wachten totdat het scannen van url's in realtime is voltooid voordat het bericht wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0d241-159">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="0d241-160">**Gebruik Safe koppelingen naar** e-mailberichten die binnen de organisatie worden verzonden: Selecteer deze instelling om het Safe Koppelingen-beleid toe te passen op berichten tussen interne afzenders en interne geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="0d241-160">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="0d241-161">**Gebruikersklikken niet bijhouden:** laat deze instelling niet geselecteerd om het bijhouden van gebruikersklikken op URL's in e-mailberichten in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0d241-161">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="0d241-162">**Gebruikers mogen niet doorklikken** naar de oorspronkelijke URL: Selecteer deze instelling om te blokkeren dat gebruikers doorklikken naar de oorspronkelijke URL op [waarschuwingspagina's.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="0d241-162">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="0d241-163">**De volgende URL's niet** opnieuw schrijven: Hiermee krijgt u toegang tot de opgegeven URL's die anders door Safe worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="0d241-163">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="0d241-164">Typ in het vak de URL of waarde die u wilt gebruiken en klik op</span><span class="sxs-lookup"><span data-stu-id="0d241-164">In the box, type the URL or value that you want, and then click</span></span> ![Knoppictogram toevoegen](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="0d241-166">.</span><span class="sxs-lookup"><span data-stu-id="0d241-166">.</span></span>

     <span data-ttu-id="0d241-167">Als u een bestaand item wilt verwijderen, selecteert u deze en klikt u op</span><span class="sxs-lookup"><span data-stu-id="0d241-167">To remove an existing entry, select it and then click</span></span> ![Pictogram knop Verwijderen](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="0d241-169">.</span><span class="sxs-lookup"><span data-stu-id="0d241-169">.</span></span>

     <span data-ttu-id="0d241-170">Zie De syntaxis van de vermelding voor de lijst 'De volgende URL's niet opnieuw [schrijven'.](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="0d241-170">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="0d241-171">Zie voor meer informatie over deze [instellingen de instellingen Safe Koppelingen](safe-links.md#safe-links-settings-for-email-messages) voor e-mailberichten en Safe Koppelingen voor [Microsoft Teams.](safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="0d241-171">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="0d241-172">Zie voor meer informatie over de aanbevolen waarden voor standaard- en strikte beleidsinstellingen [Safe Beleidsinstellingen koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="0d241-172">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="0d241-173">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0d241-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0d241-174">Op de **pagina Toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="0d241-174">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="0d241-175">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="0d241-175">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0d241-176">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="0d241-176">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0d241-177">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="0d241-177">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="0d241-178">Klik **op Een voorwaarde toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="0d241-178">Click **Add a condition**.</span></span> <span data-ttu-id="0d241-179">Selecteer in de vervolgkeuzekeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**</span><span class="sxs-lookup"><span data-stu-id="0d241-179">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="0d241-180">**De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="0d241-180">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="0d241-181">**De geadresseerde is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="0d241-181">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="0d241-182">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0d241-182">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="0d241-183">Nadat u de voorwaarde hebt geselecteerd, wordt er een bijbehorende vervolgkeuze weergegeven met een **Van deze vakjes.**</span><span class="sxs-lookup"><span data-stu-id="0d241-183">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="0d241-184">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="0d241-184">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="0d241-185">Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.</span><span class="sxs-lookup"><span data-stu-id="0d241-185">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="0d241-186">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="0d241-186">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="0d241-187">Als u afzonderlijke items wilt verwijderen, klikt **u op Pictogram** Verwijderen verwijderen op de ![ ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="0d241-187">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="0d241-188">Als u de hele voorwaarde wilt verwijderen, klikt **u op Pictogram** Verwijderen in de ![ ](../../media/scc-remove-icon.png) voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="0d241-188">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="0d241-189">Als u een extra voorwaarde wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.</span><span class="sxs-lookup"><span data-stu-id="0d241-189">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="0d241-190">Als u uitzonderingen wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**.</span><span class="sxs-lookup"><span data-stu-id="0d241-190">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="0d241-191">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="0d241-191">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0d241-192">Wanneer u gereed bent, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0d241-192">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0d241-193">Controleer uw **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0d241-193">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="0d241-194">U kunt op **Bewerken op elke** instelling klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0d241-194">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0d241-195">Wanneer u klaar bent, klikt u op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="0d241-195">When you're finished, click **Finish**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="0d241-196">Gebruik de Microsoft 365 Defender-portal om het beleid voor koppelingen Safe weergeven</span><span class="sxs-lookup"><span data-stu-id="0d241-196">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="0d241-197">Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** \> **bedreigingsbeleid Safe** \> **Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="0d241-197">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="0d241-198">Selecteer op **Safe pagina Koppelingen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="0d241-198">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="0d241-199">De beleidsdetails worden weergegeven in een fly-out</span><span class="sxs-lookup"><span data-stu-id="0d241-199">The policy details appear in a fly out</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="0d241-200">Gebruik de Microsoft 365 Defender-portal om het beleid voor koppelingen Safe wijzigen</span><span class="sxs-lookup"><span data-stu-id="0d241-200">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="0d241-201">Ga in Microsoft 365 Defender-portal naar \***Beleidsregels &** \> **bedreigingsbeleid** \> **Safe Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="0d241-201">In the Microsoft 365 Defender portal, go to \***Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="0d241-202">Selecteer op **Safe pagina Koppelingen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="0d241-202">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="0d241-203">Klik in de beleidsdetails die worden weergegeven op **Beleid bewerken.**</span><span class="sxs-lookup"><span data-stu-id="0d241-203">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="0d241-204">De beschikbare instellingen in de fly-out die worden weergegeven, zijn identiek aan de instellingen die worden beschreven in de sectie Het Microsoft 365 Defender gebruiken om Safe [koppelingenbeleid te](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) maken.</span><span class="sxs-lookup"><span data-stu-id="0d241-204">The available settings in the fly out that appears are identical to those described in the [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="0d241-205">Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteitsvolgorde wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="0d241-205">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="0d241-206">Beleidsregels voor koppelingen in- Safe uitschakelen</span><span class="sxs-lookup"><span data-stu-id="0d241-206">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="0d241-207">Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** \> **bedreigingsbeleid Safe** \> **Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="0d241-207">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="0d241-208">Let op de waarde in de **kolom Status:**</span><span class="sxs-lookup"><span data-stu-id="0d241-208">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="0d241-209">Verplaats te wisselknop naar links om het beleid uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="0d241-209">Move the toggle to the left to disable the policy:</span></span> ![Beleid uitschakelen](../../media/scc-toggle-off.png)<span data-ttu-id="0d241-211">.</span><span class="sxs-lookup"><span data-stu-id="0d241-211">.</span></span>

   - <span data-ttu-id="0d241-212">Verplaats te wisselknop naar rechts om het beleid in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="0d241-212">Move the toggle to the right to enable the policy:</span></span> ![Beleid in-/uit-](../../media/scc-toggle-on.png)<span data-ttu-id="0d241-214">.</span><span class="sxs-lookup"><span data-stu-id="0d241-214">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="0d241-215">De prioriteit instellen van Safe koppelingenbeleid</span><span class="sxs-lookup"><span data-stu-id="0d241-215">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="0d241-216">Standaard krijgen Safe koppelingenbeleid een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere agenten hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="0d241-216">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="0d241-217">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="0d241-217">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0d241-218">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="0d241-218">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="0d241-219">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="0d241-219">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="0d241-220">Safe Koppelingenbeleid wordt weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **waarde** Prioriteit 0).</span><span class="sxs-lookup"><span data-stu-id="0d241-220">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="0d241-221">In de Microsoft 365 Defender-portal kunt u alleen de prioriteit van het Safe koppelingen wijzigen nadat u deze hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0d241-221">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="0d241-222">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de regel veilige koppelingen maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="0d241-222">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="0d241-223">Als u de prioriteit van een beleid wilt wijzigen, verplaatst u het  beleid omhoog of omlaag in de lijst (u kunt het prioriteitsnummer niet rechtstreeks wijzigen in de portal Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="0d241-223">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span>

1. <span data-ttu-id="0d241-224">Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** \> **bedreigingsbeleid Safe** \> **Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="0d241-224">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="0d241-225">Selecteer op **Safe pagina Koppelingen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="0d241-225">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="0d241-226">Klik in de beleidsdetails die worden weergegeven op de beschikbare prioriteitsknop:</span><span class="sxs-lookup"><span data-stu-id="0d241-226">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="0d241-227">Het Safe koppelingenbeleid met **prioriteitswaarde** **0** heeft alleen de **knop Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="0d241-227">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="0d241-228">Het Safe beleid met de  laagste prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="0d241-228">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="0d241-229">Als u drie of meer Safe koppelingenbeleid hebt, zijn beleidsregels tussen  de  waarden met de hoogste en laagste prioriteit zowel de knoppen Prioriteit verhogen als Prioriteit verlagen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="0d241-229">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="0d241-230">Klik **op Prioriteit verhogen of** Prioriteit verlagen **om** de waarde Prioriteit **te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0d241-230">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="0d241-231">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0d241-231">When you're finished, click **Close**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="0d241-232">Gebruik de Microsoft 365 Defender-portal om het beleid voor koppelingen Safe verwijderen</span><span class="sxs-lookup"><span data-stu-id="0d241-232">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="0d241-233">Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** \> **bedreigingsbeleid Safe** \> **Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="0d241-233">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="0d241-234">Selecteer op **Safe pagina Koppelingen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="0d241-234">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="0d241-235">Klik in de beleidsdetails die worden weergegeven op Beleid verwijderen **en** klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0d241-235">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="0d241-236">Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om Safe koppelingenbeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="0d241-236">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="0d241-237">Zoals eerder beschreven, Safe beleid voor koppelingen bestaat uit een beleid voor veilige koppelingen en een regel voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="0d241-237">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="0d241-238">In PowerShell is het verschil tussen beleidsregels voor veilige koppelingen en regels voor veilige koppelingen duidelijk.</span><span class="sxs-lookup"><span data-stu-id="0d241-238">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="0d241-239">U beheert beleidsregels voor veilige koppelingen met behulp van **\* de cmdlets -SafeLinksPolicy** en u beheert regels voor veilige koppelingen met behulp van **\* de cmdlets -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="0d241-239">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="0d241-240">In PowerShell maakt u eerst het beleid voor veilige koppelingen en vervolgens maakt u de regel voor veilige koppelingen waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="0d241-240">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="0d241-241">In PowerShell wijzigt u de instellingen in het beleid voor veilige koppelingen en de regel voor veilige koppelingen afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="0d241-241">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="0d241-242">Wanneer u een beleid voor veilige koppelingen uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige koppelingen niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="0d241-242">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="0d241-243">PowerShell gebruiken om Safe koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="0d241-243">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="0d241-244">Het maken Safe beleid voor koppelingen in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="0d241-244">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0d241-245">Maak het beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="0d241-245">Create the safe links policy.</span></span>
2. <span data-ttu-id="0d241-246">Maak de regel veilige koppelingen die het beleid voor veilige koppelingen aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="0d241-246">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="0d241-247">U kunt een nieuwe regel voor veilige koppelingen maken en er een bestaand, niet-verbonden beleid voor veilige koppelingen aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="0d241-247">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="0d241-248">Een veilige koppelingsregel kan niet worden gekoppeld aan meer dan één beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="0d241-248">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="0d241-249">U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige koppelingen in PowerShell die pas beschikbaar zijn in de portal Microsoft 365 Defender nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="0d241-249">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="0d241-250">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **Nieuw-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="0d241-250">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="0d241-251">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="0d241-251">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="0d241-252">Een nieuw beleid voor veilige koppelingen dat u in PowerShell maakt, is niet zichtbaar in de Microsoft 365 Defender-portal totdat u het beleid toewijst aan een regel voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="0d241-252">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="0d241-253">Stap 1: PowerShell gebruiken om een beleid voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="0d241-253">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="0d241-254">Gebruik de volgende syntaxis om een beleid voor veilige koppelingen te maken:</span><span class="sxs-lookup"><span data-stu-id="0d241-254">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="0d241-255">Zie De [syntaxis](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)van de vermelding voor de volgende URL's niet opnieuw schrijven voor meer informatie over de syntaxis van de invoer die u wilt gebruiken voor de parameter _DoNotRewriteUrls._</span><span class="sxs-lookup"><span data-stu-id="0d241-255">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="0d241-256">Zie de sectie [PowerShell](#use-powershell-to-modify-safe-links-policies) gebruiken om beleidsregels voor veilige koppelingen te wijzigen verderop in dit artikel voor aanvullende syntaxis die u kunt gebruiken voor de parameter _DoNotRewriteUrls_ wanneer u bestaande beleidsregels voor veilige koppelingen wijzigt met de cmdlet **Set-SafeLinksPolicy.**</span><span class="sxs-lookup"><span data-stu-id="0d241-256">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="0d241-257">In dit voorbeeld wordt een beleid voor veilige koppelingen met de naam Contoso All gemaakt met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="0d241-257">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="0d241-258">Schakel URL's scannen en herschrijven in e-mailberichten in.</span><span class="sxs-lookup"><span data-stu-id="0d241-258">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="0d241-259">URL's scannen in Teams in (alleen TAP Preview).</span><span class="sxs-lookup"><span data-stu-id="0d241-259">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="0d241-260">Schakel realtime scannen in van geklikte URL's, inclusief geklikte koppelingen die naar bestanden wijzen.</span><span class="sxs-lookup"><span data-stu-id="0d241-260">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="0d241-261">Wacht totdat URL-scannen is voltooid voordat u het bericht bezorgt.</span><span class="sxs-lookup"><span data-stu-id="0d241-261">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="0d241-262">Schakel URL's scannen en herschrijven in voor interne berichten.</span><span class="sxs-lookup"><span data-stu-id="0d241-262">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="0d241-263">Gebruikersklikken bijhouden met betrekking tot Safe Koppelingenbeveiliging (we gebruiken de parameter _DoNotTrackUserClicks_ niet en de standaardwaarde is $false, wat betekent dat gebruikersklikken worden bijgepuurd).</span><span class="sxs-lookup"><span data-stu-id="0d241-263">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="0d241-264">Gebruikers mogen niet doorklikken naar de oorspronkelijke URL.</span><span class="sxs-lookup"><span data-stu-id="0d241-264">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="0d241-265">Zie [Nieuw-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="0d241-265">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="0d241-266">Stap 2: PowerShell gebruiken om een regel voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="0d241-266">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="0d241-267">Als u een regel voor veilige koppelingen wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0d241-267">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="0d241-268">In dit voorbeeld wordt een veilige koppelingsregel met de naam Contoso All gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="0d241-268">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="0d241-269">De regel is gekoppeld aan het beleid voor veilige koppelingen met de naam Contoso All.</span><span class="sxs-lookup"><span data-stu-id="0d241-269">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="0d241-270">De regel is van toepassing op alle geadresseerden in het contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="0d241-270">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="0d241-271">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="0d241-271">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="0d241-272">De regel is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="0d241-272">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="0d241-273">Zie [Nieuw-SafeLinksRule](/powershell/module/exchange/new-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="0d241-273">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="0d241-274">PowerShell gebruiken om beleidsregels voor veilige koppelingen weer te geven</span><span class="sxs-lookup"><span data-stu-id="0d241-274">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="0d241-275">Gebruik de volgende syntaxis als u bestaand beleid voor veilige koppelingen wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="0d241-275">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0d241-276">In dit voorbeeld wordt een overzichtslijst met alle beleidsregels voor veilige koppelingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0d241-276">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="0d241-277">Dit voorbeeld retourneert gedetailleerde informatie voor het beleid voor veilige koppelingen met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="0d241-277">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="0d241-278">Zie [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="0d241-278">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="0d241-279">PowerShell gebruiken om regels voor veilige koppelingen weer te geven</span><span class="sxs-lookup"><span data-stu-id="0d241-279">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="0d241-280">Als u bestaande regels voor veilige koppelingen wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0d241-280">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0d241-281">In dit voorbeeld wordt een overzichtslijst met alle regels voor veilige koppelingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0d241-281">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="0d241-282">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="0d241-282">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="0d241-283">Dit voorbeeld retourneert gedetailleerde informatie voor de regel voor veilige koppelingen met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="0d241-283">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="0d241-284">Zie [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="0d241-284">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="0d241-285">PowerShell gebruiken om beleidsregels voor veilige koppelingen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="0d241-285">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="0d241-286">U kunt de naam van een beleid voor veilige koppelingen niet wijzigen in PowerShell (de cmdlet **Set-SafeLinksPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="0d241-286">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0d241-287">Wanneer u de naam van een Safe koppelingenbeleid in de Microsoft 365 Defender-portal wijzigt, wijzigt u alleen de naam van de regel voor veilige _koppelingen._</span><span class="sxs-lookup"><span data-stu-id="0d241-287">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="0d241-288">De enige extra overweging voor het wijzigen van beleidsregels voor veilige koppelingen in PowerShell is de beschikbare syntaxis voor de parameter _DoNotRewriteUrls_ (de lijst 'De volgende URL's niet [herschrijven'):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="0d241-288">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="0d241-289">Als u waarden wilt toevoegen die bestaande vermeldingen vervangen, gebruikt u de volgende syntaxis: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="0d241-289">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="0d241-290">Als u waarden wilt toevoegen of verwijderen zonder dat dit van invloed is op andere bestaande vermeldingen, gebruikt u de volgende syntaxis: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="0d241-290">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="0d241-291">Anders zijn dezelfde instellingen beschikbaar wanneer u een beleid voor veilige koppelingen maakt, zoals beschreven in stap [1: PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) gebruiken om eerder in dit artikel een beleidssectie voor veilige koppelingen te maken.</span><span class="sxs-lookup"><span data-stu-id="0d241-291">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="0d241-292">Als u een beleid voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0d241-292">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0d241-293">Zie [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="0d241-293">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="0d241-294">PowerShell gebruiken om regels voor veilige koppelingen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="0d241-294">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="0d241-295">De enige instelling die niet beschikbaar is wanneer u een regel voor veilige koppelingen in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="0d241-295">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0d241-296">Zie de volgende sectie als u bestaande regels voor veilige koppelingen wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="0d241-296">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="0d241-297">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) gebruiken om eerder in dit artikel een sectie met veilige koppelingen te maken.</span><span class="sxs-lookup"><span data-stu-id="0d241-297">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="0d241-298">Als u een regel voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0d241-298">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0d241-299">Zie [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="0d241-299">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="0d241-300">PowerShell gebruiken om regels voor veilige koppelingen in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="0d241-300">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="0d241-301">Als u een regel voor veilige koppelingen in PowerShell in- of uitschakelen, wordt het hele Safe-koppelingenbeleid (de regel voor veilige koppelingen en het toegewezen beleid voor veilige koppelingen) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0d241-301">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="0d241-302">Als u een regel voor veilige koppelingen in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0d241-302">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="0d241-303">In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0d241-303">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="0d241-304">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0d241-304">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="0d241-305">Zie Enable-SafeLinksRule and Disable-SafeLinksRule [(Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule)](/powershell/module/exchange/disable-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="0d241-305">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="0d241-306">PowerShell gebruiken om de prioriteit van regels voor veilige koppelingen in te stellen</span><span class="sxs-lookup"><span data-stu-id="0d241-306">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="0d241-307">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="0d241-307">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="0d241-308">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="0d241-308">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="0d241-309">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0d241-309">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="0d241-310">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="0d241-310">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="0d241-311">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="0d241-311">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0d241-312">Als u de prioriteit van een regel voor veilige koppelingen in PowerShell wilt instellen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0d241-312">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0d241-313">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="0d241-313">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="0d241-314">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="0d241-314">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="0d241-315">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de **cmdlet Nieuw-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="0d241-315">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="0d241-316">Zie [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="0d241-316">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="0d241-317">PowerShell gebruiken om beleidsregels voor veilige koppelingen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="0d241-317">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="0d241-318">Wanneer u PowerShell gebruikt om een beleid voor veilige koppelingen te verwijderen, wordt de bijbehorende regel voor veilige koppelingen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0d241-318">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="0d241-319">Als u een beleid voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0d241-319">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0d241-320">In dit voorbeeld wordt het beleid voor veilige koppelingen met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0d241-320">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0d241-321">Zie [Remove-SafeLinksPolicy (Verwijderen-SafeLinksPolicy)](/powershell/module/exchange/remove-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="0d241-321">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="0d241-322">PowerShell gebruiken om regels voor veilige koppelingen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="0d241-322">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="0d241-323">Wanneer u PowerShell gebruikt om een veilige koppelingsregel te verwijderen, wordt het bijbehorende beleid voor veilige koppelingen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0d241-323">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="0d241-324">Als u een regel voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0d241-324">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="0d241-325">In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0d241-325">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="0d241-326">Zie [Remove-SafeLinksRule voor](/powershell/module/exchange/remove-safelinksrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="0d241-326">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="0d241-327">Als u wilt controleren Safe koppelingen berichten scannen, controleert u de beschikbare Microsoft Defender voor Office 365 rapporten.</span><span class="sxs-lookup"><span data-stu-id="0d241-327">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="0d241-328">Zie Rapporten voor [Defender voor](view-reports-for-mdo.md) Office 365 en Explorer gebruiken in de portal Microsoft 365 Defender voor meer [informatie.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="0d241-328">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0d241-329">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="0d241-329">How do you know these procedures worked?</span></span>

<span data-ttu-id="0d241-330">Als u wilt controleren of u beleidsregels voor koppelingen hebt gemaakt, gewijzigd of Safe hebt verwijderd, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="0d241-330">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="0d241-331">Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** \> **bedreigingsbeleid** \> **Safe Koppelingen.**</span><span class="sxs-lookup"><span data-stu-id="0d241-331">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="0d241-332">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="0d241-332">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="0d241-333">Als u meer details wilt weergeven, selecteert u het beleid in de lijst en bekijkt u de details in de fly-out.</span><span class="sxs-lookup"><span data-stu-id="0d241-333">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="0d241-334">Vervang Exchange Online PowerShell of Exchange Online Protection PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en controleer \<Name\> de instellingen:</span><span class="sxs-lookup"><span data-stu-id="0d241-334">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```