---
title: Beleid voor veilige koppelingen instellen in Microsoft Defender voor Office 365
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
description: Beheerders kunnen informatie krijgen over het weergeven, maken, wijzigen en verwijderen van beleidsregels voor veilige koppelingen en globale instellingen voor veilige koppelingen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71ea33f1f6fbebf6d87a4b42ad3bd96a60597b90
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166265"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e6dbb-103">Beleid voor veilige koppelingen instellen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e6dbb-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e6dbb-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-104">**Applies to**</span></span>
- [<span data-ttu-id="e6dbb-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e6dbb-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="e6dbb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6dbb-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="e6dbb-107">Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="e6dbb-108">Als u een thuisgebruiker bent en op zoek bent naar informatie over Safelinks in Outlook, gaat u naar [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="e6dbb-109">Veilige koppelingen is een functie in Microsoft Defender voor [Office 365](office-365-atp.md) waarmee de URL wordt gescand van binnenkomende e-mailberichten in de e-mailstroom en het tijdstip van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="e6dbb-110">Zie Veilige koppelingen [in Microsoft Defender voor Office 365](atp-safe-links.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="e6dbb-111">Er is geen ingebouwd of standaardbeleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="e6dbb-112">Voor het scannen van URL's met veilige koppelingen moet u een of meer beleidsregels voor veilige koppelingen maken, zoals wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="e6dbb-113">U configureert de algemene instellingen voor beveiliging tegen veilige koppelingen **buiten het** beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="e6dbb-114">Zie Algemene instellingen [configureren voor veilige koppelingen in Microsoft Defender voor Office 365](configure-global-settings-for-safe-links.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="e6dbb-115">U kunt beleid voor veilige koppelingen configureren in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="e6dbb-116">De basiselementen van een beleid voor veilige koppelingen zijn:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="e6dbb-117">Het beleid voor veilige **koppelingen:** schakel beveiliging voor veilige koppelingen in, schakel HET scannen van realtime-URL's in, geef op of er moet worden gewacht totdat realtime scannen is voltooid voordat het bericht wordt verzonden, geef de scanfunctie voor interne berichten in, geef op of gebruikersklikken op URL's moeten worden bij te houden en geef op of gebruikers moeten klikken op een overbezorging tot de oorspronkelijke URL.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="e6dbb-118">**De regel voor veilige koppelingen:** hiermee geeft u de prioriteit- en geadresseerdefilters op (op wie het beleid van toepassing is).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="e6dbb-119">Het verschil tussen deze twee elementen is niet duidelijk wanneer u het beleid voor veilige koppelingen beheert in het & compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-119">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e6dbb-120">Wanneer u een beleid voor veilige koppelingen maakt, maakt u tegelijkertijd een regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-120">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="e6dbb-121">Wanneer u een beleid voor veilige koppelingen wijzigt, worden instellingen met betrekking tot de naam, prioriteit, in- of uitgeschakeld en geadresseerdenfilters de regel voor veilige koppelingen gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-121">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="e6dbb-122">Alle andere instellingen wijzigen het bijbehorende beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-122">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="e6dbb-123">Wanneer u een beleid voor veilige koppelingen verwijdert, worden de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-123">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="e6dbb-124">In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-124">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="e6dbb-125">Zie de sectie Exchange Online PowerShell of de zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) gebruiken om beleidsregels voor veilige koppelingen verderop in dit artikel te configureren.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-125">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e6dbb-126">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="e6dbb-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e6dbb-127">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e6dbb-128">Als u rechtstreeks naar de pagina **Veilige koppelingen wilt** gaan, gebruikt u <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="e6dbb-128">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="e6dbb-129">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e6dbb-130">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e6dbb-131">U moet machtigingen toegewezen krijgen voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e6dbb-132">Als u beleidsregels voor veilige koppelingen wilt maken, wijzigen  en  verwijderen, moet u lid zijn van  de rollengroepen Organisatiebeheer of Beveiligingsbeheerder in het beveiligings- &-compliancecentrum en lid zijn van de rollengroep Organisatiebeheer in Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="e6dbb-132">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="e6dbb-133">Voor alleen-lezen toegang tot beleidsregels voor veilige koppelingen  moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-133">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e6dbb-134">Zie Machtigingen in [het beveiligings-](permissions-in-the-security-and-compliance-center.md) en & en [machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="e6dbb-135">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e6dbb-136">Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-136">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  <span data-ttu-id="e6dbb-137">.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-137">.</span></span> <span data-ttu-id="e6dbb-138">- De **rollengroep Organisatiebeheer alleen-weergeven** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de functie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-138">- The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="e6dbb-139">Zie beleidsinstellingen voor veilige koppelingen voor onze [aanbevolen instellingen voor het beleid voor veilige koppelingen.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-139">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="e6dbb-140">Het kan 30 minuten duren voordat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="e6dbb-141">[Nieuwe functies worden voortdurend toegevoegd aan Microsoft Defender voor Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-141">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="e6dbb-142">Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleidsregels voor veilige koppelingen aanpassen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-142">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="e6dbb-143">Het beveiligings- & gebruiken om beleid voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="e6dbb-143">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="e6dbb-144">Als u een aangepast beleid voor veilige koppelingen maakt in het beveiligings- & compliancecentrum, worden de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen op hetzelfde moment met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-144">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="e6dbb-145">Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e6dbb-146">Klik op **de pagina Veilige** koppelingen op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-146">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="e6dbb-147">De **wizard Nieuw beleid voor veilige** koppelingen wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-147">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="e6dbb-148">Configureer **de volgende instellingen op** de pagina Uw beleid een naam geven:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="e6dbb-149">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-149">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="e6dbb-150">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-150">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="e6dbb-151">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e6dbb-152">Configureer **de volgende** instellingen op de pagina Instellingen die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-152">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e6dbb-153">**Selecteer de actie voor onbekende, mogelijk schadelijke URL's in** berichten: Selecteer **Aan** om beveiliging tegen veilige koppelingen in te stellen voor koppelingen in e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-153">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="e6dbb-154">**Selecteer de actie voor onbekende of mogelijk** schadelijke  URL's in Microsoft Teams: Selecteer Aan om beveiliging tegen veilige koppelingen in te stellen voor koppelingen in Teams.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-154">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="e6dbb-155">**Realtime-URL's scannen** op verdachte koppelingen en koppelingen naar bestanden: Selecteer deze instelling om het scannen van koppelingen in e-mailberichten in realtime mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-155">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="e6dbb-156">**Wacht totdat het scannen van de URL** is voltooid voordat het bericht wordt weergegeven. Selecteer deze instelling om te wachten totdat het scannen van realtime-URL's is voltooid voordat het bericht wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-156">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="e6dbb-157">**Veilige koppelingen toepassen op e-mailberichten** die binnen de organisatie worden verzonden: selecteer deze instelling om het beleid voor veilige koppelingen toe te passen op berichten tussen interne afzenders en interne geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-157">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="e6dbb-158">**Klikken door gebruikers niet bijhouden:** laat deze instelling uitgeschakeld om het bijhouden van klikken door gebruikers op URL's in e-mailberichten mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-158">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="e6dbb-159">**Niet toestaan dat gebruikers doorklikken** naar de oorspronkelijke URL: Selecteer deze instelling om te blokkeren dat gebruikers doorklikken naar de oorspronkelijke URL op waarschuwingspagina's. [](atp-safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-159">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="e6dbb-160">**Herschrijf de volgende URL's** niet: hiermee geeft u toegang tot de opgegeven URL's die anders worden geblokkeerd door veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-160">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="e6dbb-161">Typ in het vak de URL of waarde die u wilt gebruiken en klik vervolgens op</span><span class="sxs-lookup"><span data-stu-id="e6dbb-161">In the box, type the URL or value that you want, and then click</span></span> ![Knoppictogram Toevoegen](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="e6dbb-163">.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-163">.</span></span>

     <span data-ttu-id="e6dbb-164">Als u een bestaande vermelding wilt verwijderen, selecteert u deze en klikt u op</span><span class="sxs-lookup"><span data-stu-id="e6dbb-164">To remove an existing entry, select it and then click</span></span> ![Knoppictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="e6dbb-166">.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-166">.</span></span>

     <span data-ttu-id="e6dbb-167">Zie de syntaxis voor invoer voor de lijst 'De volgende URL's niet opnieuw [schrijven'.](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-167">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="e6dbb-168">Zie instellingen voor veilige [](atp-safe-links.md#safe-links-settings-for-email-messages) koppelingen voor e-mailberichten en instellingen voor veilige koppelingen voor Microsoft Teams voor meer [informatie over deze instellingen.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-168">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="e6dbb-169">Zie beleidsinstellingen voor veilige koppelingen voor meer informatie over de aanbevolen waarden voor standaard- [en strikte beleidsinstellingen.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-169">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="e6dbb-170">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e6dbb-171">Zoek op **de** pagina Toegepast op die wordt weergegeven de interne geadresseerden op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-171">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="e6dbb-172">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-172">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="e6dbb-173">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-173">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="e6dbb-174">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-174">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="e6dbb-175">Klik **op Voorwaarde toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-175">Click **Add a condition**.</span></span> <span data-ttu-id="e6dbb-176">Selecteer in de vervolgkeuzepkeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-176">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="e6dbb-177">**De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-177">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="e6dbb-178">**De geadresseerde is lid van:** Geeft een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-178">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="e6dbb-179">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-179">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="e6dbb-180">Nadat u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzekeuze verschijnen met een **Van deze** vakjes.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-180">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="e6dbb-181">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-181">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="e6dbb-182">Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-182">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="e6dbb-183">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-183">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="e6dbb-184">Als u afzonderlijke items wilt verwijderen, klikt **u op het pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-184">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="e6dbb-185">Als u de hele voorwaarde wilt verwijderen, klikt **u op het pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-185">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="e6dbb-186">Als u een extra voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-186">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="e6dbb-187">Als u uitzonderingen wilt toevoegen, klikt u **op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-187">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="e6dbb-188">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-188">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="e6dbb-189">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-189">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="e6dbb-190">Controleer de **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-190">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="e6dbb-191">U kunt bij **elke** instelling op Bewerken klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-191">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="e6dbb-192">Klik op Voltooien wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-192">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="e6dbb-193">Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige koppelingen weer te geven</span><span class="sxs-lookup"><span data-stu-id="e6dbb-193">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="e6dbb-194">Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-194">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e6dbb-195">Selecteer op **de** pagina Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-195">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="e6dbb-196">De beleidsdetails worden in een fly-out weergegeven</span><span class="sxs-lookup"><span data-stu-id="e6dbb-196">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="e6dbb-197">Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige koppelingen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="e6dbb-197">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="e6dbb-198">Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e6dbb-199">Selecteer op **de** pagina Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-199">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="e6dbb-200">Klik in het fly-out met beleidsdetails op **Beleid bewerken.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-200">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="e6dbb-201">De beschikbare instellingen in de fly out die worden weergegeven, zijn identiek aan de instellingen die worden beschreven in het compliancecentrum voor het gebruik van het [beveiligings- &](#use-the-security--compliance-center-to-create-safe-links-policies) om beleidsregels voor veilige koppelingen te maken.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-201">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="e6dbb-202">Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteit wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-202">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="e6dbb-203">Beleid voor veilige koppelingen in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="e6dbb-203">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="e6dbb-204">Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-204">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e6dbb-205">U ziet de waarde in de **kolom Status:**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-205">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="e6dbb-206">Verplaats te wisselknop naar links om het beleid uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-206">Move the toggle to the left to disable the policy:</span></span> ![Beleid uitschakelen](../../media/scc-toggle-off.png)<span data-ttu-id="e6dbb-208">.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-208">.</span></span>

   - <span data-ttu-id="e6dbb-209">Verplaats te wisselknop naar rechts om het beleid in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-209">Move the toggle to the right to enable the policy:</span></span> ![Beleid in-/uit](../../media/scc-toggle-on.png)<span data-ttu-id="e6dbb-211">.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-211">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="e6dbb-212">De prioriteit van beleidsregels voor veilige koppelingen instellen</span><span class="sxs-lookup"><span data-stu-id="e6dbb-212">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="e6dbb-213">Standaard krijgen beleidsregels voor veilige koppelingen een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-213">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="e6dbb-214">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-214">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="e6dbb-215">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-215">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="e6dbb-216">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-216">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="e6dbb-217">Beleidsregels voor veilige koppelingen worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-217">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="e6dbb-218">In het & compliancecentrum kunt u de prioriteit van het beleid voor veilige koppelingen alleen wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-218">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="e6dbb-219">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de regel voor veilige koppelingen maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-219">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="e6dbb-220">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-220">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="e6dbb-221">Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e6dbb-222">Selecteer op **de** pagina Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-222">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="e6dbb-223">Klik in de weergegeven beleidsdetails op de beschikbare prioriteitknop:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-223">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="e6dbb-224">Voor het beleid veilige koppelingen **met** prioriteitwaarde **0** is alleen **de** knop Prioriteit verlagen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-224">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="e6dbb-225">Voor het beleid veilige koppelingen met de **laagste** prioriteitswaarde (bijvoorbeeld **3)** is alleen de knop Prioriteit **verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-225">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="e6dbb-226">Als u drie of meer beleidsregels voor veilige koppelingen hebt,  zijn voor beleid tussen de hoogste en laagste prioriteit de knoppen Hogere prioriteit en Lagere **prioriteit** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-226">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="e6dbb-227">Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-227">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="e6dbb-228">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-228">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="e6dbb-229">Het beveiligings- & gebruiken om beleidsregels voor veilige koppelingen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="e6dbb-229">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="e6dbb-230">Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-230">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e6dbb-231">Selecteer op **de** pagina Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-231">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="e6dbb-232">Klik in het weergegeven beleidsdetails op Beleid verwijderen en klik vervolgens op **Ja** in het dialoogvenster met de waarschuwing dat wordt weergegeven. </span><span class="sxs-lookup"><span data-stu-id="e6dbb-232">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="e6dbb-233">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om beleidsregels voor veilige koppelingen te configureren</span><span class="sxs-lookup"><span data-stu-id="e6dbb-233">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="e6dbb-234">Zoals eerder is beschreven, bestaat een beleid voor veilige koppelingen uit een beleid voor veilige koppelingen en een regel voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-234">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="e6dbb-235">In PowerShell is het verschil tussen beleidsregels voor veilige koppelingen en regels voor veilige koppelingen duidelijk.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-235">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="e6dbb-236">U beheert beleidsregels voor veilige koppelingen met behulp van de cmdlets **\* -SafeLinksPolicy** en u beheert regels voor veilige koppelingen met behulp van de cmdlets **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-236">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="e6dbb-237">In PowerShell maakt u eerst het beleid voor veilige koppelingen en vervolgens maakt u de regel voor veilige koppelingen om aan te geven op welke beleidsregel de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-237">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="e6dbb-238">In PowerShell wijzigt u de instellingen in het beleid voor veilige koppelingen en de regel voor veilige koppelingen afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-238">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="e6dbb-239">Wanneer u een beleid voor veilige koppelingen uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige koppelingen niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-239">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="e6dbb-240">PowerShell gebruiken om beleidsregels voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="e6dbb-240">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="e6dbb-241">Het maken van een beleid voor veilige koppelingen in PowerShell bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-241">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="e6dbb-242">Maak het beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-242">Create the safe links policy.</span></span>
2. <span data-ttu-id="e6dbb-243">Maak de regel voor veilige koppelingen die het beleid voor veilige koppelingen aangeeft dat met de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-243">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="e6dbb-244">U kunt een nieuwe regel voor veilige koppelingen maken en een bestaand, niet-verbonden beleid voor veilige koppelingen aan de regel toewijzen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-244">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="e6dbb-245">Een regel voor veilige koppelingen kan niet worden gekoppeld aan meer dan één beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-245">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="e6dbb-246">U kunt de volgende instellingen configureren voor nieuw beleid voor veilige koppelingen in PowerShell die pas beschikbaar zijn in het beveiligings- & compliancecentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-246">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="e6dbb-247">Het nieuwe beleid maken dat is uitgeschakeld _(ingeschakeld_ `$false` op de cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-247">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="e6dbb-248">De prioriteit van het beleid instellen tijdens het maken _(prioriteit)_ _\<Number\>_ op de cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-248">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="e6dbb-249">Een nieuw beleid voor veilige koppelingen dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum wanneer u het beleid toewijst aan een regel voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-249">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="e6dbb-250">Stap 1: PowerShell gebruiken om een beleid voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="e6dbb-250">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="e6dbb-251">Gebruik de volgende syntaxis om een beleid voor veilige koppelingen te maken:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-251">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="e6dbb-252">Zie de syntaxis voor Invoer voor de lijst 'De volgende URL's niet herschrijven' voor meer informatie over de [syntaxis](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)van de invoer die moet worden gebruikt voor de parameter _DoNotRewriteUrls._</span><span class="sxs-lookup"><span data-stu-id="e6dbb-252">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="e6dbb-253">Voor aanvullende syntaxis die u kunt gebruiken voor de parameter _DoNotRewriteUrls_ wanneer u bestaande beleidsregels voor veilige koppelingen wijzigt met behulp van de cmdlet **Set-SafeLinksPolicy,** zie de sectie [PowerShell](#use-powershell-to-modify-safe-links-policies) gebruiken om beleidsregels voor veilige koppelingen verderop in dit artikel te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-253">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="e6dbb-254">In dit voorbeeld wordt een beleid voor veilige koppelingen met de naam Contoso All gemaakt met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-254">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="e6dbb-255">Schakel URL's scannen en herschrijven in e-mailberichten in.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-255">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="e6dbb-256">URL's scannen in teams in turn on (TAP Preview only).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-256">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="e6dbb-257">Schakel realtime scannen in van geklikte URL's, inclusief geklikte koppelingen die naar bestanden wijzen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-257">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="e6dbb-258">Wacht totdat het scannen van de URL is voltooid voordat het bericht wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-258">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="e6dbb-259">Schakel HET scannen en herschrijven van URL's in voor interne berichten.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-259">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="e6dbb-260">Klikken van gebruikers bijhouden met betrekking tot de beveiliging van veilige koppelingen (de parameter _DoNotTrackUserClicks_ wordt niet gebruikt en de standaardwaarde is $false, wat betekent dat klikken van gebruikers worden bij houden).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-260">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="e6dbb-261">Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-261">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="e6dbb-262">Zie [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-262">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="e6dbb-263">Stap 2: PowerShell gebruiken om een regel voor veilige koppelingen te maken</span><span class="sxs-lookup"><span data-stu-id="e6dbb-263">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="e6dbb-264">Gebruik de volgende syntaxis om een regel voor veilige koppelingen te maken:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-264">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="e6dbb-265">In dit voorbeeld wordt een regel voor veilige koppelingen gemaakt met de naam Contoso All met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-265">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="e6dbb-266">De regel is gekoppeld aan het beleid voor veilige koppelingen met de naam Contoso All.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-266">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="e6dbb-267">De regel is van toepassing op alle geadresseerden in contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-267">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="e6dbb-268">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-268">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="e6dbb-269">De regel is ingeschakeld (de parameter _Enabled_ wordt niet gebruikt en de standaardwaarde `$true` is).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-269">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="e6dbb-270">Zie [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-270">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="e6dbb-271">PowerShell gebruiken om beleidsregels voor veilige koppelingen weer te geven</span><span class="sxs-lookup"><span data-stu-id="e6dbb-271">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="e6dbb-272">Gebruik de volgende syntaxis om bestaand beleid voor veilige koppelingen te bekijken:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-272">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e6dbb-273">In dit voorbeeld wordt een overzichtslijst van alle beleidsregels voor veilige koppelingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-273">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="e6dbb-274">In dit voorbeeld wordt gedetailleerde informatie gegeven over het beleid voor veilige koppelingen, genaamd Contoso-leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-274">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="e6dbb-275">Zie [Get-SafeLinksPolicy voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-275">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="e6dbb-276">PowerShell gebruiken om regels voor veilige koppelingen weer te geven</span><span class="sxs-lookup"><span data-stu-id="e6dbb-276">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="e6dbb-277">Gebruik de volgende syntaxis als u bestaande regels voor veilige koppelingen wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-277">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e6dbb-278">In dit voorbeeld wordt een overzichtslijst van alle regels voor veilige koppelingen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-278">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="e6dbb-279">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-279">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="e6dbb-280">In dit voorbeeld wordt gedetailleerde informatie gegeven over de regel voor veilige koppelingen met de naam Contoso Leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-280">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="e6dbb-281">Zie [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-281">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="e6dbb-282">PowerShell gebruiken om beleidsregels voor veilige koppelingen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="e6dbb-282">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="e6dbb-283">U kunt de naam van een beleid voor veilige koppelingen in PowerShell niet wijzigen (de cmdlet **Set-SafeLinksPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="e6dbb-283">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="e6dbb-284">Wanneer u de naam van een beleid voor veilige koppelingen wijzigt in het beveiligings- & compliancecentrum, wijzigt u alleen de naam van de regel voor veilige _koppelingen._</span><span class="sxs-lookup"><span data-stu-id="e6dbb-284">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="e6dbb-285">De enige extra overweging voor het wijzigen van beleidsregels voor veilige koppelingen in PowerShell is de beschikbare syntaxis voor de parameter _DoNotRewriteUrls_ (de lijst 'De volgende URL's niet opnieuw [schrijven'):](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-285">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="e6dbb-286">Gebruik de volgende syntaxis om waarden op te voegen die eventuele bestaande items `"Entry1","Entry2,..."EntryN"` vervangen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-286">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="e6dbb-287">Gebruik de volgende syntaxis om waarden toe te voegen of te verwijderen zonder dat dit van invloed is op andere bestaande gegevens: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="e6dbb-287">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="e6dbb-288">Anders zijn dezelfde instellingen beschikbaar wanneer u een beleid voor veilige koppelingen maakt, zoals wordt beschreven in stap [1: Gebruik PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) om een beleidssectie voor veilige koppelingen te maken eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-288">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="e6dbb-289">Gebruik de volgende syntaxis om een beleid voor veilige koppelingen te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-289">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="e6dbb-290">Zie [Set-SafeLinksPolicy voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-290">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="e6dbb-291">PowerShell gebruiken om regels voor veilige koppelingen te wijzigen</span><span class="sxs-lookup"><span data-stu-id="e6dbb-291">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="e6dbb-292">De enige instelling die niet beschikbaar is wanneer u een regel voor veilige koppelingen wijzigt in PowerShell, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-292">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="e6dbb-293">Zie de volgende sectie als u bestaande regels voor veilige koppelingen wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-293">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="e6dbb-294">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt, zoals wordt beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) gebruiken om een sectie met regels voor veilige koppelingen te maken eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-294">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="e6dbb-295">Gebruik de volgende syntaxis om een regel voor veilige koppelingen te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-295">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="e6dbb-296">Zie [Set-SafeLinksRule voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-296">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="e6dbb-297">PowerShell gebruiken om regels voor veilige koppelingen in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="e6dbb-297">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="e6dbb-298">Als u een regel voor veilige koppelingen in PowerShell in- of uit schakelen, wordt het hele beleid voor veilige koppelingen (de regel voor veilige koppelingen en het toegewezen beleid voor veilige koppelingen) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-298">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="e6dbb-299">Gebruik de volgende syntaxis om een regel voor veilige koppelingen in PowerShell in of uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-299">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="e6dbb-300">In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-300">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="e6dbb-301">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-301">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="e6dbb-302">Zie [Enable-SafeLinksRule en Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) voor gedetailleerde syntaxis- en [parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="e6dbb-302">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="e6dbb-303">PowerShell gebruiken om de prioriteit van regels voor veilige koppelingen in te stellen</span><span class="sxs-lookup"><span data-stu-id="e6dbb-303">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="e6dbb-304">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-304">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="e6dbb-305">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-305">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="e6dbb-306">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-306">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="e6dbb-307">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-307">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="e6dbb-308">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-308">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="e6dbb-309">Gebruik de volgende syntaxis om de prioriteit van een regel voor veilige koppelingen in PowerShell in te stellen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-309">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="e6dbb-310">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-310">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="e6dbb-311">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="e6dbb-311">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="e6dbb-312">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-312">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="e6dbb-313">Zie [Set-SafeLinksRule voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-313">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="e6dbb-314">PowerShell gebruiken om beleidsregels voor veilige koppelingen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="e6dbb-314">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="e6dbb-315">Wanneer u PowerShell gebruikt om een beleid voor veilige koppelingen te verwijderen, wordt de bijbehorende regel voor veilige koppelingen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-315">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="e6dbb-316">Gebruik de volgende syntaxis om een beleid voor veilige koppelingen in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-316">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="e6dbb-317">In dit voorbeeld wordt het beleid voor veilige koppelingen met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-317">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="e6dbb-318">Zie [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-318">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="e6dbb-319">PowerShell gebruiken om regels voor veilige koppelingen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="e6dbb-319">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="e6dbb-320">Wanneer u PowerShell gebruikt om een regel voor veilige koppelingen te verwijderen, wordt het bijbehorende beleid voor veilige koppelingen niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-320">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="e6dbb-321">Gebruik de volgende syntaxis om een regel voor veilige koppelingen in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-321">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="e6dbb-322">In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-322">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="e6dbb-323">Zie [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-323">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="e6dbb-324">Als u wilt controleren of veilige koppelingen berichten scannen, controleert u de beschikbare Microsoft Defender voor Office 365-rapporten.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-324">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="e6dbb-325">Zie Rapporten voor Defender voor [Office 365](view-reports-for-atp.md) en Verkenner weergeven in het beveiligings- & [compliancecentrum voor](threat-explorer.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-325">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e6dbb-326">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="e6dbb-326">How do you know these procedures worked?</span></span>

<span data-ttu-id="e6dbb-327">Ga op een van de volgende stappen te werk om te controleren of u een beleid voor veilige koppelingen hebt gemaakt, gewijzigd of verwijderd:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-327">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="e6dbb-328">Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-328">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="e6dbb-329">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="e6dbb-329">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="e6dbb-330">Als u meer details wilt weergeven, selecteert u het beleid in de lijst en bekijkt u de details in de fly-out.</span><span class="sxs-lookup"><span data-stu-id="e6dbb-330">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="e6dbb-331">Vervang in Exchange Online PowerShell of Exchange Online Protection PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="e6dbb-331">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
